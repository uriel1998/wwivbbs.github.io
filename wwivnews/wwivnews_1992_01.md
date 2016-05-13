```

              ±±±Ü     ±±±Ü  ±±±Ü     ±±±Ü  ±±±±Ü ±±Ü         ±±Ü
               ±±Û     ±±Ûß   ±±Û     ±±Ûß   ±±Ûß  ±±Û       ±±Ûß
               ±±Û     ±±Û    ±±Û     ±±Û    ±±Û    ±±Û     ±±Ûß
               ±±Û ±±Ü ±±Û    ±±Û ±±Ü ±±Û    ±±Û     ±±Û   ±±Ûß
               ±±Û ±±Û ±±Û    ±±Û ±±Û ±±Û    ±±Û      ±±Û ±±Ûß
               ±±Û ±±Û ±±Û    ±±Û ±±Û ±±Û    ±±Û       ±±±±Ûß
               ±±±±±±±±±±Û    ±±±±±±±±±±Û   ±±±±Û       ±±Ûß
                ßßßßßßßßßß     ßßßßßßßßßß    ßßßß        ßß
                     ±±±±±Ü±±Ü ±±±±±±Ü ±±Ü   ±±Ü ±±±±±±Ü
                     ±±Û±±Û±±Û ±±Ûßßßß ±±Û±±Ü±±Û ±±Ûßßßß
             ±±±±±±Ü ±±Û±±Û±±Û ±±±±Ü   ±±Û±±Û±±Û ±±±±±±Ü ±±±±±±Ü
              ßßßßßß ±±Û±±Û±±Û ±±Ûßß   ±±Û±±Û±±Û  ßßß±±Û  ßßßßßß
                     ±±Û±±±±±Û ±±±±±±Ü ±±±±±±±±Û ±±±±±±Û
                     ßß ßßßßß  ßßßßßß  ßßßßßßßß  ßßßßßß

                               Volume 2, Issue 1
                                 January 1992

                               Table of Contents
                               ~~~~~~~~~~~~~~~~~
WWFNET Review................................................Quantum 1@6300
Wayne Mail!......................................................Random 1@1
Multi-Line WWIV Mailing List............................East Bay Ray 1@9964
The Editor's Corner.....................................East Bay Ray 1@9964
Latest Versions..............................................WWIVNEWS Staff
Acknowledgements.............................................WWIVNEWS Staff
===============================================================================

      ----------------------------------------------------------------
     WWFNET  -  Utilities to send/receive/request files through WWIVnet
      ----------------------------------------------------------------

  For a few months I've been working on a set of utilities to allow SysOps
to send files to each other via WWIVnet. Although rampant use of such a tool
would be frowned upon, there are some situations where it may be very
welcome. I decided to take it on because it of the local environment that my
BBS is a part of.

  There are three BBS's, nodes @6300, @5804, and @6301 in this area that are
run by myself (#1@6300/#1@5804), and Malbee (#1@6301). @6300 and @6301 are not
in the same local dialing area, thus direct file transfers can be costly.
@5804 is in the local dialing area of each of them, so by passing data through
it, no additional costs are incurred.



           @6301- - - - - - - tollcall- - - - - - - - @6300
              \        Not Connected via WWIVnet       /
                \                                    /
                  \                                /
                    \                            /
                  local call              local call
             Connected via WWIVnet    Connected via WWIVnet
                          \                /
                            \            /
                              \        /
                                \    / 
                                @5804


  This being understood, I thought, "wouldn't it be neat if there were a
utility to make it easy for Malbee and I to send files to each other, through
WWIVnet?" It would have to be simple to install, user friendly, and generally
wonderful. So,.. I wrote WWFNET

   Hopefully, this goal has been fully accomplished. I'll leave that decision
up to you, the potential user. It's been through several beta versions, with a
small group of SysOps testing it (not that I didn't welcome a larger group, it
just worked out that way). I think most of the bugs have been squashed and it
does actually work. As of this writing, it's available as version 2.1 in a ZIP
archive named WWFNET21.ZIP.

  WWFNET runs as a chain and as part of the nightly event. Not only can files
be sent from one BBS to another, but one BBS can send a "request" to another
BBS, asking it to send a certain file back. Files to be sent can also be queued
to be sent late at night, when BBS activity is lower. When a file is sent to
another BBS's, an email message is also sent, notifying the other SysOp of
it's arrival.

  It consists of a few programs, a config file, some user modifiable batch
files, and a "WWIVlike" menu file that is also alterable. The documentaion
gives installation instructions and a sample configuration file. It uses the
EXTERNAL.NET feaures of WWIVnet, does not use any message bases and the file
size is unlimited.

  It's a shareware product, but I'm not very greedy so anything is negotiable.
In any event, I'll answer any questions people may have about it, even if
they don't send me money, gifts, and material things. Afterall, this is a
hobby.

  Use of WWFNET should be restricted to clusters of BBS's where all SysOps
in a connect path are willing to pass such traffic. Because files tend to
be larger than email/post messages, this policy is fair to the other SysOps in
the net. I imagine that a SysOp would get quite annoyed if his/her BBS were
passing this type of traffic without knowing about it. Especially if it was
costing him/her money.

It's available on my BBS, in the 'NEW-UPLOADS' file area, named "WWFNET21.ZIP"


                                      Enjoy,

                                             ==Info=Rail== @6300  Snarfable
                                             (603)382-3966 3-9600 HST

                                             ____    __   _
                                              | 0|___||. (_)uantum
                                             _| _| : : }   `
                                              -(O)-==-o\ 73's KA1YLG
                                             ==Info=Rail==
===============================================================================


To all WWIVnet sysops:  (Thu Dec 19 18:08:56 1991)
Random #1 @1
Thu Dec 19 18:08:56 1991
RE: WWIVnet

Hello,

Before the horrible rumors start in too much, I thought I'd let everyone
know what is going on.

First, the GCs and ACs are going to be adding WWIV reg nums into the
bbslist files.  So, when convenient, please send mail to your AC/GC
giving your WWIV reg num.  There is really no great hurry about this,
anytime in the next month or so will do.  However, do not expect to see
your reg # actually appear in your bbslist file, as net27 and earlier
will throw away reg #'s in partial BBSlist updates.

Which means, yes, net28 will be out in the next month or so.  Also, I
expect WWIV v4.21 to be out in the first quarter next year.

What's new in net28:

network3 analysis is speeded up by about a factor of three.

The net software will route messages through servers more than it did in
the past.

Reg #'s in the bbslist files will be correctly handled (instead of
ignored, as they are now).

Storage type 2 has been expanded to support >1MB files.  Currently, if
any .DAT file in your MSGS directory goes over 1MB, it's going to at
least lose messages, maybe trash some of them.  net28 will store them in
an expanded (but compatible) format.  WWIV v4.21 will correctly support
these files also.  v4.20 and earlier won't correctly read the new
expanded format (but they won't read any >1MB storage type 2 file
anyway, so nothing's lost).

net28 supports short response messages (so-and-so read your mail on
messages).  WWIV v4.21 sends these out over the net (previous versions
don't).  So, if you notice in your netdat*.log files that the net
software threw away a type 15 message from me, that was it; don't worry
about it.  Net28 will correctly receive those.

As some of you may have heard, the Link people recently had a bunch of
systems trashed by a badly formatted message.  net28 fixes the bug that
caused that.

v4.21 new features (so far) include:

Support for >1MB storage type 2 files and the short response messages
sent over the net.

Completely re-done interrupt handling.  A few people have been having
problems with SCSI adapters trying to use the same interrupts as WWIV,
and it didn't work.  v4.21 uses only one interrupt vector (v4.20 used
three), and in v4.21, the interrupt is dynamically selected from unused
vectors (instead of being hard-coded values).

It will allow you to forward mail (from the mail read prompt) over the
network.

The list of disallowed device filenames (CON, PRN, etc) is gotten from
the system device table, for more protection.  Also, .ARC files are
scanned for invalid filenames in addition to .ZIP files (NOTE: if anyone
has the format for other archive types [ARJ, LZH, etc], please send me
some structures or code to list the filenames in them, and I'll have
v4.21 check those too).

Batch uploading with Ymodem-G is fixed.

Lots of little bugs and oversights were fixed.

If you get a lot of junk mail from someone, you can hit 'P' from the
mail read prompt and purge all mail waiting from that user.

You can uedit search for a realname.

I'm also working on Bimodem.

But, the part you probably really wanted to know about: Yes, to be in
WWIVnet in the future, you will have to have registered WWIV.  Also, in
order to use the net software (net28 or later) in other networks, you
will have to have registered WWIV.  The readme.net file in net28 is
basically:

/****************************************************************************/

Up until now, the WWIVnet software has been distributed freely to
everyone.  Starting with net28, the net software is distributed much
like the WWIV software itself.

NOTE: If you have already registered WWIV and have a WWIV registration
number, read no further.  You can continue using the WWIVnet software as
you have before.  This change affects only people who have NOT
registered WWIV.

The WWIV and WWIVnet software is distributed as shareware, which means
(in this case) that you can use the WWIV and WWIVnet software for up to
two months before deciding whether or not to register WWIV.  If, at the
end of the two month period, you decide to register WWIV, please see the
'read.me' file in the WWIV .ZIP file for information on how to register.
If at the end of two months you decide NOT to register WWIV (and hence
not use WWIV software for your BBS), you must stop using the WWIV and
WWIVnet software.

If/when you register WWIV (and receive a WWIV registration number), you
have also registered the WWIVnet software, and may use the WWIV and
WWIVnet software on your system as you wish -- as a standalone BBS, in
WWIVnet, or in a private network.

If you are running a BBS that is in no way based on WWIV software, but
that uses the WWIVnet software, then a similar registration procedure
applies.  You can use the WWIVnet software for a two month trial period.
If you decide to continue using the WWIVnet software after the two month
trial period, then you must register the WWIVnet software for $20.  If
you do not register the WWIVnet software at the end of the two month
trial period, you must stop using the WWIVnet software.

Thus, there are two ways you can legally continue to use the WWIVnet
software after the two month trial period.  Either register WWIV, or (if
you are running BBS software that is in no way based on WWIV software),
register the WWIVnet software for $20.

If you are using BBS software that is in no way based on WWIV software,
and wish to use the WWIVnet software, please use the form 'netreg.frm'
to register the WWIVnet software.

/****************************************************************************/

And no, net servers (REAL, DEDICATED net servers) will not have to have
a reg number, and @6xx pseudo-nodes will not have to have separate reg
#'s.

It's going to take a while for me to get organized to handle all this,
so the registration requirement isn't going to actually take effect very
soon.  When it does actualy take effect (probably in 1-2 months), the
two month countdown will start then.  So, if you aren't currently
registered, you have about 3-4 months to do so.

$F4 1@1
===============================================================================


                         Multi-Line WWIV Mailing List
                            by East Bay Ray 1@9964


        It seems like every day that some new sysop comes up and asks
either a) where he can get a multi-line version of WWIV, or where he can
find a mod that will convert WWIV to multiline.  Well, to put it bluntly:
        THERE CURRENTLY EXISTS NO MULTI-LINE WWIV, MOD OR PROGRAM.

        However, many many people would like such a program.  I have
already started on the creation of my own multi-line WWIV.  I posted the
first of the routines (none of which were complicated at all, or really
accomplished anything major) on the WWIV Modification Net.  This mailing
list will be much like a networked subboard.  Every time the mail pouch
gets full here, with suggestions, or source code, or whatever, I will send
a piece of mail to everyone on the list with the newsletter.  Don't worry,
the e-mail is sent in the same fashion as posts are:  all destination
systems in a single network message packet.

        When you feel you have something to respond to, or just some input
into the newsletter, [A]uto-Reply to the newsletter and your input will be
placed into the next version of the newsletter.  I understand that the
first couple of releases will be a bit dry of input barring mine, but after
that, I think it will be a great success.

        What does all this accomplish?  Well, if you are not a C
programmer, then basically you input ideas into the project.  You say what
features would be nice in a multi-line WWIV, such as multi-line chat,
several lines being able to receive WWIVnet calls at the same time (good
for servers!), etc., etc.  If you are a C programmer, then you are
encouraged to contribute code to the project.  I will be working
dilligently on modifying the current v4.20e source code to be multi-line.
And you will have played a part in its creation!

        E-mail WWIVSERV@9964 if you wish to join this mailing list.  The title
doesn't matter, but the first line of the message should read:

SUBSCRIBE 1

(of course, all other WWIVSERV commands apply as well) 

Enclosed below (between the "---cut here---" lines) is a DEBUG script for
creating the decoder needed to use the mailing list.  Place the lines
between the two "--- cut here ---" lines into an ASCII file DE500.SCR.
Then execute the following DOS command:
        DEBUG < DE500.SCR


--- cut here ---
NDE500.COM
A100
JMP 14A

E102 'Copyright (c) 1992 by Jeff Garzik'

A14A
MOV     AX, 4C00
INT     21

RCX
50
W
Q

--- cut here ---

===============================================================================


                              The Editor's Corner
                            by East Bay Ray 1@9964

        Submissions are definately down here at WWIVNews headquarters, but
I decided to go ahead and release another one anyway.  I haven't been able
to keep track of all the news, but then again, no one is submitting much of
anything anymore.  There is one new column here, at least.  "Latest Versions"
is intended to be a list of software that supports WWIV and/or WWIVnet
directly, and lists the current versions of each.  If you recently authored
a new program, or updated an old one, please send in the name, version #,
and A SHORT DESCRIPTION of your program to me at 1@9964.
        Finally, apologies to all for lack of formatting.  I just switched
from using MicroStar, which is the text editor provided with the Turbo
Pascal Editor Toolbox, to QEdit.  QEdit seems more flexible, but at the
present time I still haven't mastered all its features.  Bear with me!
===============================================================================


                               Latest Versions
                        (at the time of publication)

WWIV Software by Wayne Bell 1@1
-------------------------------
WWIV                       4.20e       WWIVnet                    27
FIX                        5           

WWIV Accessories
----------------
Call-Back Verifier         1.20        CyberSpace                 1.07
FileList                   1.0         FSED                       1.13
Gold System                3.0         Go-Snarf                   1.6
One ZIP                    1.01        Snarf                      1.02
Tolkein's UEDIT            1.20        USERSTAT                   2.0
Eclipse                    2.0         WOMR (BBS Module)          2.00
ZEdit                      1.2f        WWIVEdit                   2.2

WWIVnet Accessories
-------------------
8B's AC/GC List Generator  2.01        8B's Extended LNET         1.0
8B's NetUtil               2.20        WWIVSERV                   0.8á
Jim Wire's CLOUT           2.28        WNCI                       0.90
WWIVLink Network Software  1.05        MyRegion                   09/1991
Network Editor             1.33        NetSEX                     1.00
SendZIP                    1.10        The Node Creator           0.92á
===============================================================================


                               Acknowledgements

    WWIV (c) 1988 by Wayne Bell.
    All other products mentioned are either registered trademarks or
      copyrighted by their respectives manufacturers.
===============================================================================


                                    The End


```
