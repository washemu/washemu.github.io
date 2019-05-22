---
layout: post
title: "SNICKER WARS EPISODE I: THE PHANTOM EMULATOR"
date: 2019-05-22 00:42:00 -0700
---

Once again, the snickerblog is back after 6 months of inactivity.  Luckily,
WashingtonDC hasn't been nearly as dead, as I've been making a commitment to
regular commits to the github.  I'm generally the sort of person who prefers
getting work done over talking about how much work I'm doing.  Maybe I should be
doing more to evangelize WashingtonDC, but ultimately I'm still afraid of doing
too much advertising too early; my worst nightmare would be for it to be one of
those vaporware emulators that makes a big splash on /r/emulation but ultimately
never accomplishes anything.

WashingtonDC has made great strides in the past year towards becoming a viable
Dreamcast emulator.  A number of new games are booting, including both Sonic
Adventures, Guilty Gear X, and more.  Things are running a bit faster, to the
point that some games can consistently run at fullspeed on my shiny new Intel i9
9900k CPU  Those of you running slower computers need not fear - I intend for
WashingtonDC to eventually be usable on potatoes, so I'm holding on to the 7
year-old AMD Bulldozer build which used to serve as my primary PC so I can use
it for performance testing.  Even more important, however, is that it finally
has working audio!  You can see below a video I recorded of City Escape from
Sonic Adventure 2 running.  That video's already a few weeks old, and I've
already fixed several of the missing sound effects and boosted performance a
bit.

[![YouTube video of City Escape.  Click on the image!](https://img.youtube.com/vi/AXRB1BodeDk/0.jpg)](https://youtu.be/AXRB1BodeDk)

I think WashingtonDC's finally approaching the point where it will be viable as
a platform for playing Dreamcast games.  In retrospect, the release deadline I
came up with last year (11/27/2018, the 20th anniversary of Dreamcast's launch)
was way off the mark, but I think I can have a release of sorts in time for the
20th anniversary of Dreamcast's North American launch on 9/9/2019.  In the more
immediate future I'm going to get to work on improving documentation and getting
together a compatibility database so it's usable at that date.

The snickerblog itself is undergoing a rennovation as I try to migrate over from
raw HTML to jekyll.  This has been a bit of a mess and has resulted in it
looking more disshevled than usual due to my lack of experience working with
HTML, Ruby, and Jekyll.  Once I have this under control I'll be able to update
the Snickerblog more often.  I already have a few posts planned out further
detailing what's changed since the last snickerblog update in November.  Going
forward I want to improve communication and start to attract a userbase.

The snickerblog has also relocated to washemu.org, as you're probably already
aware.  This will be the new permanent home of the snickerblog and
WashingtonDC's official website.  I also have a shiny new
snickerbockers@washemu.org e-mail address, thus breaking my dependence on
GMail's stupid datamining operation.  @sbockers on twitter is still my only
point-of-contact for social networking.

There's an offical WashingtonDC Discord server now; you can find an invite to it
at the top of this page.  I'm somewhat abivalent about Discord's rapid rise to
prominence as the internet's new favorite chatroom app; it's a fun place to
shitpost and organize online gaming sessions, but it's also a completely closed
system.  I thought about opening up a channel on some IRC network somewhere
instead, but I ultimately decided against it because my priority is to make it
easier for people to follow the progress of WashingtonDC, not to try (and fail)
to prop up a dying messaging service.  Anyways, I don't expect Discord to last
more than a few years.  There have been dozens of other messaging services
sitting atop that same throne over the past two decades, but nobody's ever
managed to stay at the top for long (see AIM, MSN, Xfire, Skype, etc).

I'm going to be at Fanime-con in San Jose, California this weekend.  This means that I probably
won't be able to make any more commits to WashingtonDC for the next week.  When
I get back to work, my first priority will be to fix a texture caching bug which
is causing a major performance hit in Guilty Gear X, and then after that I'm
going to be looking into implementing audio channel attenuation in the AICA.  I
always try to force myself to get at least one commit a week in even when I
really don't want to, so I hate being unable to get anything done this week, but
I'll be back to my usual commit schedule next week starting on either Tuesday
or Wednesday.

I've also been making a Jet Set Radio costume for Fanime, which I may or
may not post pictures of depending on how self-conscious I feel...
