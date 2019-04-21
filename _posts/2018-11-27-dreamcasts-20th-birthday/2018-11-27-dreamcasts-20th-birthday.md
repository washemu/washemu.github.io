---
layout: post
title: Dreamcast's 20th birthday
date: 2018-11-27 20:34:00 -0700
---
Today's the big anniversary: Dreamcast was released in Japan twenty years
ago on November 27, 1998.  For some reason this makes me feel like I'm
having a mid-life crisis, which is weird because I'm only 8 years older
than the Dreamcast.  I feel much better about Genesis turning 30 (that
also happened this year!) since I wasn't even born until a couple years
later.  I guess there's something unnervinf about being able to remember
hearing about Dreamcast back when it was the future instead of the
distant past.

Unfortunately, I didn't manage to stick to my plan to have a release of
WashingtonDC ready in time for the 20th anniversary.  AICA turned out to
be more complicated than I anticipated, and I'm just now getting the
snickerbockers/aica_audio branch to a state where things are starting to
work out.  I've made some major progress since the last snickerblog update
and as a result there are several more games booting in addition to the
ones shown there.  Right now that branch has emulation of the audio
hardware, but no actual audio output This means that Dreamcast programs
think they're playing audio, but in reality the samples they generate get
discarded insted of being sent to an audio backend on the host machine.
I'm going to clean up a few more things and then merge the branch to
master before I get started on the audio backend.  After that, I still
need to work on getting the ARM7 fully integrated with the JIT, figuring
out what the UI will be like and implementing VMUs before I can actually
have an early release ready.
