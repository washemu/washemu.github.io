---
layout: post
title: "Regression Testing WashingtonDC"
date: 2017-12-10 16:17:00 -0800 
---

One of the difficult things about starting my emulator was trying to
test it without having anything to test against.  During the early stages
there wasn't any software I could boot, and I didn't even have any form of
visual feedback from the emulator until I had been working on it for six
months.  By my count there are 236 opcodes in the SuperH-4 instructin set,
and most of them get used during the boot process.  If one of those
opcodes is wrong, the emulated software might loop forever (best-case
scenario), or it might call the wrong function, or it might write a
garbage-value somewhere and corrupt its own state.  In the latter two
cases it's very difficult to figure out what went wrong because the
root-cause of a bug could be very far removed from its symptons.  Worse
still, without any form of feedback from the emulated software I might
not even know that something did go wrong.

The obvious solution is to write test programs that can detect when
something is wrong, but in order for that to work I'd need a way to load
them into the emulator and a way to get feedback from them.  Loading them
can be accomplished by writing a test program that replaces the firmware
image, but then I still need a way to get feedback from them; there's no
way to get feedback from emulated software until the emulator is
functional enough to support the mechanisms that software would use to
send feedback, and I needed test programs to help get the emulator
to that state.

My solution to this was to make a couple of unit-test programs which
would link against WashingtonDC's .o files, initialize some of the
hardware, artificially inject sh4 code into the memory via an sh4
assembler library I wrote, execute that code, and then inspect the CPU's
registers to see if they matched the intended final values.  This
resulted in three separate tests: sh4mem_test, sh4inst_test, sh4div_test,
sh4tmu_test, and sh4asm_test (which tested the assembler library).  These
four tests helped root out several bugs so I could move WashingtonDC
along.

Since they all needed to link against WashingtonDC as a library, they had
to be refactored every time WashingtonDC's internal APIs changes.  This
was an especially arduous task in the case of sh4inst_test, which
had swollen to be more than 10000 lines of code as I kept adding more and
more testcases.  Sometime after I got the firmware booting, I decided the
work needed to keep them running was greater than the benefit I got from
them so I let them die of bitrot, and eventually I deleted them from git.

Recently, I've been getting ready to make some major changes to the sh4
to support a JIT recompiler, and also to make the existing interpreter
faster.  This motivated me to bring back the unit_tests, only this time I
have the infrastructure needed to build real test roms for the Dreamcast.
My current approach is to have the roms do complicated operations and
print the results to the serial port.  The tests are designed so that if
anything goes wrong the output will change.  I have a couple perl scripts
which launch WashingtonDC with the given test roms and compare the output
to captures taken from the same roms running on a real Dreamcast.  If
there are any discrepancies then the perl script knows something is wrong
and it raises an error.

This scheme sounds primitive but it works much better than the old
unit_tests scheme did because it's actually comparing WashingtonDC against
a real Dreamcast instead of comparing it against my estimations of what a
real Dreamcast would have done.  I'm just getting started but I've
already found and fixed two bugs which the old sh4inst_test was missing.
I was worried initially that this would turn out to be a pedantic waste of
time since WashingtonDC can already run a few games and I didn't think
there would be any basic instruction bugs which wouldn't prevent something
complicated like Crazy Taxi from booting; this assumption could not have
been more incorrect.

I think the best part of the new test roms is that since they're real
Dreamcast programs, they'll never die of bitrot like the old unit_tests
did.  I can keep making whatever major architectural changes I want to
WashingtonDC and that will never require a major refactor of the test
roms.  I don't really even need to keep the source code around (not that
I would ever get rid of it).
