```

                Ú¿Ú¿Ú¿Ú¿Ú¿Ú¿ÚÄÄÄÄ¿Ú¿  Ú¿ÚÄ¿ Ú¿ÚÄÄÄÄ¿Ú¿Ú¿Ú¿ÚÄÄÄÄ¿
  ÉÍÍÍÍÍÍÍÍÍÍÍÍÍ³³³³³³³³³³³³ÀÄ¿ÚÄÙ³³  ³³³ À¿³³³ÚÄÄÄÙ³³³³³³³ÚÄÄÄÙÍÍÍÍÍÍÍÍÍÍÍÍÍ»
  º  Volume 3   ³³³³³³³³³³³³  ³³  ÀÅ¿ÚÅÙ³  ÀÙ³³ÀÄÄÄ¿³³³³³³³ÀÄÄÄ¿ Nov/Dec/Jan º
  º Issue 7/8/9 ³³³³³³³³³³³³  ³³   ³³³³ ³Ú¿  ³³ÚÄÄÄÙ³³³³³³ÀÄÄÄ¿³  1992/1993  º
  ÈÍÍÍÍÍÍÍÍÍÍÍÍÍ³ÀÙÀÙ³³ÀÙÀÙ³ÚÄÙÀÄ¿ ÀÅÅÙ ³³À¿ ³³ÀÄÄÄ¿³ÀÙÀÙ³ÚÄÄÄÙ³ÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
            ³   ÀÄÄÄÄÙÀÄÄÄÄÙÀÄÄÄÄÙ  ÀÙ  ÀÙ ÀÄÙÀÄÄÄÄÙÀÄÄÄÄÙÀÄÄÄÄÙ   ³
            ³ Serving WWIV Sysops & Users Across All WWIV Networks ³
            ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ
                           ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
                           ³This Month's Features³
ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³ Random Factors.......................................Wayne Bell (1@1)       ³
³                                                                             ³
³ Hack Attempts & Common Sense.........................Erik S. Klein (1@2082) ³
³                                                                             ³
³ Inside UEDIT.........................................Tolkien (1@3456)       ³
³                                                                             ³
³ PKWARE's Hacked Versions of PKZIP Listing............PKWARE Inc.            ³
³                                                                             ³
³ TechnOTES............................................WWIVnews Staff         ³
³                                                                             ³
³ Squashing Those Gluttony .GIF's (Part 3).............Spackle (1@19955)      ³
³                                                                             ³
³ Filo's Mod of the Month..............................Filo (1@5252)          ³
³                                                                             ³
³ WWIVnet-Compatible Network Listing (1/7/93)..........Red Dwarf (1@6264)     ³
³                                                                             ³
³ Dateline: @#$*()#!...................................Omega Man (1@5282)     ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³               Random Factors                ³
               ³   Creative Commentary by Wayne Bell (1@1)   ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

Lots of creative comments this issue:

NET32
ÄÄÄÄÄ

As most people know by now, net32 has been released. Even though it may not 
look like much, it actually has quite a few things fixed/upgraded/added.

New net32 features: 

 - Support for WWIV v4.22 (which most people probably don't care about yet)

 - Deletion of duplicate posts (but not duplicate E-Mail)

 - Multitasking support (file locking is now fully supported)
 
 - E-mail gating (if you are in multiple networks)

Fixes: 
 - Sub auto-reqs had a bug in previous versions, where if you received 
   multiple requests (add or drop) for the same sub in the same net packet, 
   some systems would be erroneously dropped from the n*.net file. That is 
   fixed in net32.
   
Problems:   

 - There have been some problems reported with net32, though. These mostly
   relate to the increased memory usage of net32 (due to v4.22 support).
   Some of the rumors say this has to do with net compression, so if you're 
   having a problem, try having your connect(s) turn off compression.

WWIV v4.22
ÄÄÄÄÄÄÄÄÄÄ

As most of you already know, my BBS phone number (Amber, @1) was changed on 
Thursday, Dec 24, 1992. The new phone number is 310-798-9993. If this is news
to you, make a note of this change as the release date for WWIV v4.22 will be 
Sat, Jan 23rd at 6:00 PM PST. All v4.22 files will be made available for 
download after that time.

The .ZIP files for v4.22 are:

WWIV422 .ZIP - 338k - compiled version, no docs.
WWIV422S.ZIP - 352k - source version, no docs.
421A-422.ZIP - 234k - upgrade from v4.21a to v4.22 (VERY long)
WWA1-422.ZIP - 182k - accessory pack part 1 (docs + ESM)
WWA2-422.ZIP - 279k - accessory pack part 2 (WWIVedit 2.5).

(Obviously, you don't need all of them.)

All files are zipped with pkzip v1.10, and have -AV codes on them, so
when you unzip the files, you should see "-AV" after every file, and a
note at the bottom saying:

Authentic files Verified!   # XLD658   WWIV Software Services

The 'README.422' file in WWIV422.zip, WWIV422s.zip and 421A-422.zip
describes the changes to v4.22 (from v4.21a).

v4.22 SIDE NOTES
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

A lot of people have been asking about this one: v4.22 WILL include a no-frills
mini-editor for external strings. It will not be very fancy, but it'll do for
those who choose not to use another ESM.

In response to a query from the WWIVnews Editor, the quoting elements of the 
code are still not accessible by the internal editor. There are, however, mods
out there to enable this feature if you really think it's necessary.

Regarding userrec's that are non-standard, such as those modded by GOLDSYS, 
INIT will only convert stock user lists. If you have a non-standard one, you'll
have to update the included convert.c program and run it.

Finally, no real progress was made this version regarding the fax detection 
routines.  Apparently, most modems don't really support that kind of operation.

REGISTRATION FEES
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

For those of you who haven't registered the source yet, as of Feb 1, 1993 the 
registration fee for WWIV will increase to $80. This includes having a disk 
mailed to you (so the increase is $25, from $55 to $80).

If you have already registered WWIV, or do register before Feb 1, 1993 (that 
is, postmarked on or before Jan 31), this will NOT affect you. If you are 
already registered, you will see no change in source code access, or anything.

This change in source registration policy will have no affect on WWIVnet 
registrations. Also, if you are in the WWIV installment plan, and have made 
your first installment before Feb 1, 1993, the price increase will not affect
you.

PKZIP 2.04c & WWIV
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

As some of us sysops have already found out, there are many changes to the new
version (v2.04c) of PKZIP/PKUNZIP.

Unfortunately, in Phil Katz's attempt to speed-up screen-writes, he bypasses
DOS and calls INT 29. This works fine locally, but remote callers SEE NOTHING
on their screen when viewing/listing/extracting or adding to a TEMP archive.
Bummer!

Yes, the PKWARE folks are aware of the problem, and until they release an
update fixing this (actually, they said they will add a command-line switch to
not allow this DOS by-pass), and "fix" some other problems that have been
reported, you might try the following work-around:

1) Run INIT.

2) Select option 6.

3) Add to the end of each ZIP command-line ">NUL" (without the quotes). 

Remote users will now be able to view the output as before.

NOTE:  for pkzip 2.04C (or later), you NEED to have "-o" on your extraction
commandline, for security reasons.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³        Hack Attempts & Common Sense         ³
               ³           Erik S. Klein (1@2082)            ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

[Editor's nOTE: A couple of weeks back, Erik posted a detailed hacking report
on the Group 4 discussion sub. While the methods employed may seem rather
lame to most experienced sysops and users, the fact that they were successful
teaches us all a very valuable lesson about how fragile system security can
be when we allow those who are untrained in such procedures to act in our
stead.]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The following is EXTREMELY IMPORTANT information!  It should be read
carefully and acted upon.

     This document is to inform you about a rather obnoxious hacker who
     has been making SUCCESSFUL attempts at local WWIV boards. The
     following is his M.O.:

     First he will call the BBS in question and establish an account -
     or several if possible. He will perform whatever activities are
     considered "normal" on that board such as downloading files,
     playing onliners and such. This is, presumably, to throw the SysOps
     off the scent later. The phone number, name and other information
     he gives are, of course, bogus.

     Next he will somehow get the phone number of the OTHER phone
     line(s) at the SysOps home. In most cases this is as easy as
     calling information since most SysOps use their real names and
     their exchange gives a means of comparison where there are many
     "John Smiths."

     He will then call the board to be hacked at a time when he thinks
     the Sysop is not there and try and page the Sysop for a chat.

     If the chat is unsuccessful then he will call the voice phone
     number and tell any FEMALE who answers (our local WWIV SysOps are
     all males) that she needs to press the F9 key to "unlock" or "fix"
     the board. This boy is very cool, calm and persuasive. He has
     talked at least one wife and one daughter into actually PRESSING
     THE KEY!  He only began failing after word got out. (Before our
     local WWIV community realized what was up he was calling my place
     VERY often; almost daily. It got so bad for a while that I thought
     my wife was having an affair!)

     Once he has Temp SysOp he just does a //edit on CONFIG.DAT to get
     the SysOp password and does a //UEDIT to get the SysOp's password
     (for later use). He now has free and ready access to DOS whenever
     he calls. He can drop down and ZIP up whatever he wants and
     download it at his leisure. He can then delete or edit any affected
     logs and be gone without a trace. The one sure thing he gets from
     this is a COMPLETE USER LIST with PASSWORDS. In San Antonio he HAS
     used this to log on as others, for what it's worth. On boards where
     the machine is not dedicated to the BBS the potential for damage is
     impressive.

It is pretty obvious that this guy knows WWIV pretty well. It is also
obvious what needs to be done about him. 

1) Sysops MUST let their families, friends, roommates, and even their pets
   know NEVER to press any keys for strangers without consulting you first. 
   It is amazing how few Sysops actually restrict their families use of their
   boards!

2) A little more security should be placed in the CONFIG.DAT file. Wayne should
   consider possibly encrypting the Sysop Password(s) in future releases of 
   WWIV. 
   
3) Another San Antonio Sysop recommended that secondary password protection be 
   placed on commands such as //edit and //uedit. This is a REALLY good idea 
   and several mods exist out there for additional Sysop passwords.
   
4) Sysops should change their passwords often. This is the easiest way to 
   foil hackers who have already used this hack method with success. Some 
   hackers will lay low with their information for quite some time before 
   actually using it to their "advantage", and a frequent password change will
   usually render their success a moot point.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

[Editor's nOTE: The bottom line on this particular hacking method is pretty
obvious. Hackers using this method are taking advantage of a simple lapse in 
common sense on the part of the Sysop regarding the use of cohabitants as
"co-sysops". Sysops, make sure those sharing your living space are either made
aware of all aspects of BBS security and know what to do in an "emergency", or 
that the BBS is off-limits unless *you, yourself* have instructed them
to do something. If the person(s) in question are rather computer-illiterate,
the latter option is probably the safest. After all, it's better to have a
board that's down temporarily for a small but safe reason than one that's down
for a rather big and stupid one.]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³               Inside UEDIT                  ³
               ³Guest Creative Commentary by Tolkien (1@3456)³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

UEDIT is a standalone program, a superset of the functions of the built-in
uedit function that WWIV possesses. But more than just an editor, it's also
a userlist *manager*, with a vast array of capabilities far beyond the
internal uedit function.

Because of the (irritating) array of userrec structures out there, UEDIT now
supports five all in one executable: stock 4.21A userrecs with 32 msg bases or
64 msg bases, both of those with the FROM mod installed (which I highly
recommend, since it's a useful thing for UEDIT to search on), and my own
userrec structure.

If your userrec structure is not one of these, do not despair; all is not
lost. Ethereal Cereal released a modification that allows you to put "extra"
userrec stuff in a separate file, USER2.LST. I suggest doing this, but leaving
the FROM information in USER.LST, so that UEDIT can use this information to
search on - and move everything *else* non-standard (if anything) into
USER2.LST. You need not specify which userrec structure you use - UEDIT
figures this out by itself by reading the size of your userrec structure from
CONFIG.DAT. Originally I did have it necessary to specify which structure to
use on the command line, but I decided that was too much of a pain, so it's
all taken care of for you now.

The first thing you notice when you run it is the interface - mouseable, with
support for extended EGA/VGA 43- and 50-line video modes; it will use a mouse
if you have one installed and a mouse driver resident. If not, no big deal;
it works equally well without a mouse, with mnemonic key commands for all
functions and help always available at the press of a key. UEDIT adjusts
itself automatically to use the extended EGA/VGA modes if you are currently
using one. The colors highlight important information.

The initial screen you see is what I call browse mode. On this screen are
two windows, one containing a scrollable list of the users' handles and user
numbers. The other window details some of the more critical information
about the user on which the cursor is located. Users with a security level of
100 or greater are shown in one color, users who haven't called in over 90
days (or a number of days you specify yourself) are shown in another color.
"Normal" callers are shown in yet another color. It works just as you would
expect: the page down key scrolls you down a screenfull of users, page up does
the opposite. Home bring you to the #1 account, End brings you to the last
account. Deleted callers are shown in red.

Hitting the ENTER key brings you into what I call edit mode. Here is where you
can edit all of the various fields for that caller, including city, state,
and address if your userrec has them included. You can also edit a zillion
fields that the internal uedit function of WWIV does not allow: the colors,
the macros, logons, posts, time spent on the board, you name it. You move
from field to field with TAB or ENTER or if you use a mouse you can just click
on the field you wish to edit.

The core of the various non-editing functions that UEDIT can perform is
contained in the search engine (which, along with all other commands, is
available from edit or browse mode, so you can use whichever is most
comfortable to you at the time). The search screen allows you to enter a range
of security levels, download security levels, days since called, age, sex,
status (deleted, normal, inactive or all of the above). You can search by ARs
and/or by DARs, and you can use one AR to exclude callers from showing as a
match. An example of what the search engine can do is to find all male
undeleted callers, age 17-20, with a zipcode containing '631', who last called
some time from 30 to 60 days ago, with an AR of 'A', or 'B' and a security
level of 30-50. You can also specify realname, handle, street, city/state,
and note substrings to search for.

While the search engine sounds complicated, it needs to be seen to understand
just how easy it is to use. And *finding* the specified callers is just the
beginning. Once you have defined a search specification, you can then perform
actions on those callers. For instance, you can redefine their colors, or
reset their QSCAN pointers, or delete them, or print some information about
those callers to a file (detailed or brief information). Or just plain count
how many callers match that specification, just for information.

Besides these abilities, UEDIT also possesses a few others: a memory-efficient
drop to DOS which leaves only a resident 7-10k kernel in memory, the ability
to add a specified number of new user accounts (for instance, if you know
someone is going to call and you wish to get their account ready), or you
can swap the location of two accounts (to move your friend to a lower user
number, for instance). You can rewrite WWIV's NAMES.LST file properly with
a keypress. There's a one-key command to jump straight to the #1 account from
anywhere. There is a command to save a "favorite" search specification (your
most-often-used one) to disk, and another command to retrieve a saved search
specification from disk, so you needn't retype it constantly.

All of this is available when UEDIT is fully loaded. However, you can also
perform some command line operations, notably a user purge, for deleting aged
accounts automatically as part of your daily event. Of course, you can specify
a range of security levels, etc., to narrow down your purge. Some of the actual
UEDIT interface colors and settings may also be overridden with command line
parameters. A list of the available command line parameters and a brief
description is available by running the standard UEDIT /?.

When WWIV v4.22 comes out, all of the userrec compatibility problems will be
solved, since the userrec struct that will be used for 4.22 is much more
modifiable without sacrificing compatibility, and has much more depth as well.
UEDIT will, of course, support that userrec fully when it becomes standard.
Kudos to Wayne for doing the userrec upgrade. At this point in time, rather
than modifying your userrec, you might as well wait for WWIV v4.22's "super
userrec".

Nigh three years in the making now, UEDIT has changed greatly. I wrote it to
do a few useful things originally and, by request mainly, have added
capabilities as time has gone on. By the time you read this, the current
version will be v2.01. For those of you who have over about 200 users, this is
a fairly indispensable utility. Once you've used UEDIT and explored its
capabilities, you will wonder how you ever lived without it.

Is it free? No way. Hundreds of hours of development time went into writing
this program. It's commercial-grade software at this point, albeit for a
limited market. The shareware cost is $20, with no upgrade fees ever. Those
who registered previous versions (for $15) do not pay the difference, of
course.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

[Editor's nOTE: Tolkien is working on a UEDIT update for the forthcoming WWIV
4.22 release, and a follow-up article detailing any major changes will appear 
in a future issue of WWIVnews.]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³  PKWARE's Hacked Versions of PKZIP Listing  ³
               ³           Courtesy of PKWare Inc.           ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

[Editor's nOTE: WWIVnet's PKZip watchdog, Allen Turner (1@9965), was unable
due to personal time constraints to do a follow-up article on his PKWare
update from last September. When his schedule permits, a follow-up will 
appear in a future issue of WWIVnews, hopefully with a brief interview with
Phil Katz on just what the hell was *really* going on with 2.04c prior to
its release. In the meantime, the following was posted on the PKWare BBS
just prior to 2.04c's general release to the public in an effort to help
sysops and users identify and eliminate hacked versions of PKZip that have
appeared over the past few months.]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

        In a attempt to clarify the situation with fake release versions of 
        PKZIP, we are releasing this list of known hacks. If you have 
        any information as to the original source of any of these hacks, 
        please either leave mail for the sysop on the PKWARE BBS 
        (414-354-8670), or call us at 414-354-8699.

        Known PKZIP related hacks as of 9/30/92:

        Name                    Information
        -------------------------------------------------------------------
        PKZIP120                Early hack of 1.1
        PKZIP20B                Hack of 1.1 
        PKZIP_V2.EXE            Trojan, will erase hard drives
        PKZ201.ZIP              Hack of 1.93
        PKZ201.EXE                   "
        PKX201.EXE                   "
        PKZ210F.EXE             Unknown
        PKZIPV2                 Trojan, will erase hard drives
        PKUNZIP.COM             Unknown
        PKZIP203.EXE            Unknown
        PUTAV 1.93              Fake putav program (trojan)
        PKZIP 1.99              Unknown
        PKZIP 2.02              Unknown
        PKZIP 2.2               Trojan destroys hard drives
        PKZ305.EXE              Hack of 1.93, fake AV.

        General guidelines for detecting a hack:

        The real PKZIP 2 will use a method of compression called
        "Deflating".  There are FOUR methods of Deflating plus a
        NO compression option: -ex -en -ef -es -e0.

        PKWARE's AV code is: PKW655.  The AV method used by PKZIP 1.10 and
        1.93 is different from that used for PKZIP 2.  

        The PKZIP 2 documentation is completely new.  All hacks shown
        above either have no documentation or a slightly modified version
        of the PKZIP 1.0 docs.

        PKZIP 2 will be distributed in a self-extracting (EXE) file.
        PKWARE software would never be distributed as a .ZIP file or any
        other archive format.
        
        PKZIP 2 will be sent to registered users before it is posted
        by PKWARE.  PKZIP 2 will be available on PKWARE BBS as soon
        as the upgrades have been shipped.

        PKWARE Inc. Phone numbers and address will be on the real PKZIP 2:

        PKWARE Inc.
        9025 N. Deerwood Dr.
        Brown Deer, WI  53223
        (414)354-8699
        (414)354-8559 FAX
        (414)354-8670 BBS

        PKWARE BBS offers 14.4K Dual Standard modems (v.32/v.42bis) 
        on all nodes.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³                 TechnOTES                   ³
               ³        Compiled by the WWIVnews Staff       ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

...On-The-Fly compression was the household buzzword for '92. Compression
utils such as Stacker, SuperStor and XtraDrive brought new life to old, smaller
hard drives previously doomed to extinction in today's Windows-hungry computing
environments. The technique has proven it's worth so successfully that 
Microsoft will finally offer its own compressor with release 6.0 of DOS, which
at last report will be a licensed version of XtraDrive.

...There's always a yin for every yang it seems. With all the hoopla over 
higher on-the-fly file compression ratios, it may come as no surprise that
the promise of cheaper ways to increase drive space comes the promise that 
you will definitely fill those drives. Especially if what you're filling that
empty space happens to be those pesky, semi-uncompressable .GIF files.

...In recent months, prices have started to drop on sheet-fed full-page 
desktop scanners and video capture boards. For under $1300 mail-order, one
can purchase a 300 DPI color scanner and real-time video capture board with
dual-source wiping capabilities. These prices are for what is now considered
the "low end" of the imaging utility spectrum, which has increased to 300
DPI or better in required minimum resolution. Previous prices for 300 DPI
are now the asking price for peripherals that manipulate no less than 800 DPI,
which itself is becoming the low-end minimum resolution for usage in multimedia
support peripherals and professional image digitizing.

...But for the .GIF freaks, Windows background enthusiasts, and low-end desktop
publishers, 300 DPI is more than satisfactory for most uses. Most full-color
.GIF's and .BMP's are between 300 to 400 DPI at 640x480 anyway, so the added
resolution is lost when viewing denser images at a reduced size. 

...Adding to the surge in interest in desktop scanners has been the related
price drop in 300 DPI B&W scanners. While B&W .GIF's are already obsolete,
these low-cost sheet-fed scanners are perfect for starting a home business 
dealing in OCR and document scanning. Mail-order prices for a sheet-fed model
have been seen as low as $200, and Kyocera has reportedly dumped a load of
what used to be their "top-of-the-line" full-page scanners on the market as
well. Prices for the Kyoceras have been spotted in _Computer Shopper_ for as
low as $499, with prices expected to drop to about half that by the end of
the year.

...The demands placed on video performance by GUI's such as Windows and
OS/2 has hardware manufacturers scrambling to devise ways to boost video
performance at an economic price. While the future points towards placing
the video circuitry on the CPU bus itself, currently the best means available 
to improve high-res windows performance is to use video cards whose onboard 
processors are geared for direct windows support.

...However, local bus video is still a ways in the future, as most LBV 
designers are waiting for the 386/486 market to stabilize somewhat before
pushing for such a radical addition to the CPU. As a result, Chips & 
Technologies has developed an interim solution to the performance problem 
in the form of an additional on-board processor.

...Dubbed the "Wingine", the processor differs from other video performance
enhancements by utilizing inexpensive system RAM in place of more expensive
video RAM (VRAM), which in turn is managed by the existing system memory 
controller. The result is a compromise between placing the video controller 
directly on the CPU itself and improving performance with an expensive 
high-performance VRAM accelerator card.

...According to a C&T spokesman, several manufacturers had expressed interest
in the Wingine. However, as of press time only Epson had announced plans to 
produce systems based on the Wingine approach. 

...Back in 1988, the "Gang of Nine" banded together in an attempt to concoct
some form of advanced bus architecture that would provide a viable alternative
to IBM's proprietary (and expensive) Micro Channel Architecture, or MCA. The 
result was an enhanced version of the standard 8/16-Bit architecture, dubbed 
by that same "Gang of Nine" as "Extended Industry Standard Architecture" or 
EISA. 

...The creation of EISA retroactively gave 8/16-Bit bus structures the name of
"Industry Standard Architecture", or ISA, with the hopes of subliminally 
discrediting Micro-Channel systems as being "against the industry standard." 
EISA also promised backwards-compatibility with existing ISA peripherals, which
IBM refused to promise to apply to their MCA machines. IBM raised the battle
cry of "Total Upgrade...or DIE!", and relatively few people joined in the 
chorus.

...In light of benchmarks that showed virtually no difference in performance 
over even an ISA bus system with a fast clock speed, MCA naturally never took 
off as IBM hoped. A recent multi-page ad section in a recent issue of _PC 
Magazine_ actually gives some hint that even Big Blue is reconsidering its
own zealousness towards the Micro-Channel. With this in mind, EISA should have
taken off like a rocket, and we should all be reaping the rewards of a faster,
backwards-compatible bus, right?

...not hardly. Several factors have kept EISA from truly becoming the
"Extended Industry Standard". First of these was the waxing and waning
cooperation between the members of the "Gang of Nine", which slowed progress
on the EISA bus standards and delayed shipping of the first EISA bus PCs.
Secondly, the initial performance of the EISA machines wasn't better than
the ISA machines they were replacing. Since bus mastering hadn't come unto
acceptance at that time, the EISA controllers were designed around the
techniques used for ISA systems. 

...The lack of promised performance crippled EISA's reputation as much as those
unkept promises had done for the Micro-Channel. When combined with the $50 to
$1000 added cost-per-EISA-machine caused by the high premium Intel was charging
for the EISA bus controller chip set, the "Gang of Nine" were dealt as bad a
hand as that which IBM had drawn from their own deck.

...However, EISA is once again poised on the edge of an acceptance threshold.
Although recently developed bus-mastering disk controllers from Ultrastor and 
Adaptec have shown that the promises of EISA weren't as hollow as the 
benchmarks claimed, the major advancement for the new "Industry Standard" is
a new chip set from OPTI that promises to reduce the difference between EISA
and ISA to below $100.

...the key to the price difference appears to be the number of chips in the
set itself. Intel's set requires 20 VLSI's, which forces EISA system designers
to use motherboards that can only fit in well-ventilated (and more expensive)
tower cases. OPTi's chip set, however, requires only four VLSI's to perform
EISA tasks. The result is a reduction to about 1/4 of the cost to produce the 
chips themselves, while at the same time allowing retailers to sell EISA
systems in smaller footprint cases for an even lower cost.

...Oddly enough, EISA's "rebirth" comes at a time when the next evolutionary
step beyond EISA, the Local Bus Architecture, is about to come unto its own.
However, both have their comparative strengths and weaknesses, which will
definitely have an effect on future system designs. Where Local Bus is superior
for video performance, EISA excels when it comes to high-level disk file 
management. The logical compromise that will eventually take place is to
develop a hybrid EISA/Local Bus machine that combines the benefits of both
bus architectures on one board.

...Ok, so Apple's Newton PDA has been unveiled. Granted, it won't run WWIV
right off the bat, but that hasn't stopped IBM from trying to keep up with
the times. IBM has announced that a "technology demonstration" will be held
at November's COMDEX to unveil Big Blue's answer to the Newton. Insider
reports claim the two-pound device looks very similar to Apple's Newton, and
can be configured to use up to 40 Megs of flash memory. IBM officials have 
also gone on record to say that there is a "strong likelihood" that this, or
another IBM PDA design, will ship in the second half of 1993 at a price 
comparable to that of the Newton.

...Word from Cyrix sources claim that the "Intel Busters" are working on a new
i486 pin compatible processor that promises integer performance rivaling that 
of Intel's P5. Cyrix hopes to ship by the end of 2nd Quarter '93, but most
industry analysts remain skeptical as reports from inside Cyrix claim that the
new chip also suffers from the same overheating problems that have plagued 
Intel's faster processors. 

...According to Intel, the initial stock Intel P5's are expected to clock at
66 Mhz and deliver 100 MIPs. Performance on the order of four to ten times 
that of a 33 Mhz i486DX is also anticipated.

...Alright, confess: you didn't REALLY expect Windows NT to ship on schedule
as announced, did you? No, and with good reason, too. The end-user beta 
testing program for NT is only now getting underway and most industry 
observers are saying the product is unlikely to be ready before the second 
quarter of 1993 - probably closer to the 3rd, to be exact.  

...Though Windows NT is touted as offering hardware independence, the users of
systems using a processor other than an Intel x86-based CPU will discover that
existing Windows applications will only run - albeit slowly - in 8086 (XT)
emulation mode unless they obtain new versions recompiled for their specific 
hardware. 

...Speaking of expectation, IBM VP Richard Guarino has gone on record regarding
the promises of "Joint Apple/Mac/IBM/AIX/OS/2 Compatibility" that have been
cited as being part of the first edition of Taligent's "Pink" OS. Pink,
currently being developed jointly by IBM and Apple, "probably will not support
applications written for other operating systems, such as the Macintosh System
7, DOS, OS/2, and AIX." Guarino also pointed out that the first end-user 
version of Pink isn't expected until 1995, and expressed the opinion that it 
is too soon to know what will or won't be supported. 

...It should be noted, however, that Apple has reportedly been making good 
progress towards porting Macintosh Toolbox calls to native PowerPC code. This
could result in friction between the Taligent partners if one company's 
software engineers are ready with support for their existing applications far
in advance of the other. Based on the short track record of "partnership"
between Apple and IBM so far, you can probably safely bet the farm that there
will be problems between the two in this matter when "Pink" finally hits the
market.

...Word from the Boca Rats is that IBM is beta testing the next major upgrade 
for LAN Manager for OS/2, and is expected to ship it by the end of this year,
ahead of schedule by at least six months. Version 3.0 will include peer-to-peer
services, built in TCP/IP, and an enhanced High Performance OS/2 File System
(HPFS) for both client and server. 

...Meanwhile, word from the Microsoft beta-testers for DOS 6.0 report that
in addition to using XtraDrive/Disk Doubler/Magic Disk/Whatever it's called, 
the Gates boys also plan to include peer to peer networking services - this 
including serial port null-modem cable hookups - as part of the basic package!

...At the same time, however, the testers are also quick to point out that 
Microsoft's plan for DOS 6.0 appears to be geared towards taking care of two
major areas of DOS's shortcomings - On-The-Fly Compression and Network Support
- while at the same time trying to incorporate the "best" of the PD/Shareware 
DOS utils all in one package. Those they can't incorporate, say the testers,
will simply be shoved out of the way.

...The bad news from the testers appears to be that DOS 6.0 will be just a bit 
more memory-hungry than 5.0, and that accessibility to higher memory will be
required to keep LMA usage below 155k. Current beta reports also state that 
when DOS is loaded "high", the remaining lower memory "stub" is an acceptable
44K. As a result, Microsoft is reported to be seriously considering releasing
the new version so that it can't run on anything less than an AT with at least
1MB of RAM. This abandonment of the true 8086/88 processor class would, in all
likelihood, hammer the last nail in the coffin for the XT's by eliminating
one of THE major upgrade element paths.

...Exis, developers of Telix, has sold all rights to the program source code,
trademark name, and future sales of the program to former Exis Technical
Support Manager, Jeff Woods. The terms of sale were not disclosed, and no
reasons were given for the sale. However, Woods has gone on record that both
parties were in agreement "that this was the best course of action to ensure
the long-term growth and prosperity of the product."

...Woods has also stated that future releases of Telix would be available from
his new company, DeltaComm Development, and support/upgrade pricing will
continue to be offered to previous registered users. A minor upgrade to Telix
has been promised year's end, which Woods claims will "contain some of the
more popular feature requests." Some of these features should include a
sorely-needed script 'learning' capability, an easier learning curve for the
powerful SALT scripting language, and - tho many may argue against it - some
form of ANSI music capability.

...Woods noted that deltaComm is expected to be in full operation as of
October 5th, and that until then Exis would not be taking calls or orders for
Telix. At the same time, Woods also reported that Telix's chief programmer,
Colin Sampaleanu, will reportedly cease work on Telix and remain with Exis to
work on other projects.

....Warning! Warning! Danger, Will Robinson! Microsoft's latest plan for
Windows on ROM has a very dangerous tone to it. Some design engineers have
been looking at the idea of using WinROMs on - get this - household appliances.
Although WinROMs aren't available yet, some Microsoft engineers have reportedly
come up with base designs for telephones, microwave ovens, audio CD decks, 
VCRs, and even lawn sprinkler control systems that use a mouse and a Windowed
interface for operation.

...Now, the sprinkler idea isn't too bad when you think about it. Having a 
configurable timer manager for unattended watering of the grass according to 
city ordinances would be a boon to quite a number of amateur horticulturalists.
The same concept could be used for the VCRs and CD decks, while the phone 
concept would probably be an extension of WinTerminal and Notepad into Ma 
Bell's container. However, having a mouse in the kitchen...well, one wrong 
move with a carving knife, and you probably get the picture. 

...Besides, cleaning food out of a mouse is about as much a pain in the butt
as cleaning out a keyboard. Just ask the WWIVnews Editor about that!

...Intel has developed a new version of the Above Board that allows for mixing
and matching of SIMM's with different RAM configurations and speeds. The $299
0k ISA board holds up to 32MB of RAM, and provides for automatic remapping
of faulty memory in 128k blocks to provide access to the remaining memory.
An Intel insider also reports that development has commenced on another new 
version of the Above Board that will allow for mix and match of both SIMMs
and SIPPs, and is expected to see release by the 2nd Quarter of '93.

...Cray enthusiasts take note: Cray Research has finally ported C++ over to
their line of supercomputers, including the Cray X and Y-MP series. With
this advancement in the state of the art for supercomupting, can WWIV/Cray
be far behind?

...Talk about late-breaking news: Last July, Microsoft Corporation terminated 
its licensing agreement with Z-Nix Computer Inc., and filed suit against Z-Nix
and several of its distributors. The suit follows a Microsoft investigation 
that revealed distribution of thousands, of illegal copies of the complete 
Windows 3.1 package under the Z-Nix logo.

...According to a Microsoft spokesman, Microsoft filed suit against Z-Nix and
at least four of Z-Nix' distributors on June 22 of this year for copyright and
trademark infringements, as well as breach of licensing agreement. Microsoft
attorneys also requested and were granted a temporary restraining order against
any and all further reproduction and distribution of Microsoft software as 
manufactured by Z-Nix.

...Under the license agreement with Microsoft, Z-Nix was granted the right to
reproduce and distribute Windows 3.1 software as part of a package deal with 
the Z-Nix mouse, as well as the right to upgrade existing customers who had 
bought the same package with Windows 3.0 software included. According to 
Microsoft, Z-Nix engaged in widespread distribution of a stand-alone version, 
marked as an "Upgrade," to users other than existing customers. Under the terms
of the license agreement, distribution of such copies constitutes both a breach
of the agreement and a copyright/trademark infringement. This according to
the claim filed by Microsoft's attorneys.

...Since last July, an out-of-court settlement was reportedly reached between 
the two parties. In addition to the payment of an undisclosed sum, Z-Nix has 
lost all rights to distribute any version of Windows other than any existing 
stock of the 3.0 release. As this settlement prohibits Z-Nix from offering an
upgrade for Windows 3.1, Microsoft has agreed to accept ownership of Z-Nix
Windows copies as proof of eligibility for future Windows upgrade plans.

...This news might be a bit late, but seeing as how a lot of people bought
systems that included the Z-Nix mouse & Windows 3.0 package, it's better late
than never.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³  Squashing Those Gluttony .GIF's (Part 3)   ³
               ³            By Spackle (1@19955)             ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

This article is the last in a three-part series of articles discussing the
various GIF (Graphics Interchange Format) picture file compression methods,
their pros and cons, and a sample test with sample GIF files. The complete
article (12K archived) is available for download at The Rubicon in Raleigh,
North Carolina at 919-676-0738 under the filename of GIFCOMPR.LZH. Sysops
are auto-validated first call. This would make an excellent G-File, and is
good download information as well.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Conclusions on GIF Compression (based on personal experience and testing):
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

 1. Based on my own personal experience, GIF compression is usually a
    complete waste of time. The space gained vs. the loss in image quality
    is usually a lose-lose battle no matter how you look at it.

 2. Archiving GIFs using one of the popular archiving programs doesn't gain
    any space, it only allows multiple files to be "enveloped" into one file
    for download or disk transfer. The time spent compressing GIFs with an
    archiving program is ENORMOUS compared to the low overhead of starting a
    file transfer and doing it (even at 2400 baud).

 3. GIFLITE works well, and works consistently on all but a few GIFs. It
    doesn't always compress as well, but it ALSO doesn't degrade pictures
    NEAR as much. Too, there is not an opportunity to use and re-use GIFLITE
    and any one file... with JPEG you can compress and compress until the
    resulting picture hardly resembles the original image.

 4. JPEG was not intended for 8-bit machines. Period. Unless you have a
    24-bit TARGA board, or an XGA-equipped PS/2, don't bother with GIF2JPG.
    The results are unpredictable, and sometimes contrary to what it should
    be. The options are too many and too testy to be reliable. The relative
    difference between images compressed using a quality factor of 50 and
    one of 51 may be ten-fold -- or maybe it won't.

 5. In addition to being unreliable, I tested GIF2JPEG on the same file mult
    iple times to determine whether the SAME compression takes place each
    time. Guess what?  It doesn't!  You may compress file XX.GIF and YY.GIF
    (both are the same file), but the output from these files (XX.JPG and
    YY.JPG) MIGHT NOT BE THE SAME!!!  This suggests a HIGH probability of
    almost zero reliability and support for a "norm" in GIF2JPG. Once again,
    we're back to the fact that JPEG is a 24-bit compression technique, not
    an 8-bit technique.

 6. Let's explain Conclusion #1 a little more for those who find it flippant:

      Let's take 2 files - both are 100K. We'll call them A.GIF and B.GIF.
      We will follow 2 paths and add up the time spent and space gained for
      each path:

        PATH 1 - Compression of both files (using either GIFLITE or JPEG)
        takes 6 minutes. We gain 20K for each file - a total of 40K.
        Downloading both files takes approximately 12 minutes at 2400 baud.

        Path 1 Totals:  40 K saved        12 minutes to download
                                         + 6 minutes for compression
                                         ----
                                          18 minutes total time spent

        PATH 2 - No compression of files. Total file size is now 200K.
        Downloading both files takes about 20 minutes at 2400 baud.

        Path 2 Totals:  0 K saved         20 minutes to download
                                         + 0 minutes for compression
                                         ----
                                          20 minutes total time spent

        Is it worth two minutes of download time to:
          - Destroy a perfectly good GIF?
          - Render someone's artwork indistinguishable?
          - Have to exit the BBS, start the compression program,
            copy the new file over, update the file size info on
            the BBS, rename the file, and start the BBS back up...?
          - Possibly even infringe upon a copyright?

        It's the user that has to spend that extra 1 minute per file on
        download time, and I think it's worth it to nearly all of them
        to get a GIF that's not been tampered with or defiled or degraded
        using a compression program. And it seems to me it's a lot more
        hassle than it's worth.

 7. Making backups and testing quality factors and getting them right for
    each particular GIF is ridiculous. While it allows people in a 24-bit
    editing studio--who are LOOKING at the frame to be compressed and know
    what will be taken out--to define what they want, it only adds to the
    confusion and frustration of the PC user, Sysop, or BBS user. GIF
    compression shouldn't be a trial-and-error process. It takes too long
    for Joe Normal to sit patiently while FILE1.GIF gets compressed, only
    to find that he's compressed too much and lost too much image info.
    Whoops!  He also forgot to make a backup.... so much for that GIF...

 8. GIF compression is a personal issue. It's like abortion--well, maybe
    not, but it is controversial just the same. Do you take the file into
    your own hands and re-form it while it's still warm from the artist's
    hands?  Or do you let it settle--big as it may be--as it was intended
    by the artist?  Scanned images, of course, usually have a lot of room
    for compression. Hand-drawn and scanned or digitized hand-drawn images
    do not, and it is my opinion that tampering with these files is pretty
    much unethical. It's like re-writing someone's executable program and
    taking away all the nice little features and leaving just the menus.

 9. I must also bring up copyrighting. Some GIFs are copyrighted (actually,
    ALL the ones that are stolen from magazines are copyrighted!). To change
    the actual image and redistribute the new image is considered a copyright 
    infringement. It is highly unlikely that you will ever be arrested or 
    anything, but for the morally correct, compressing some GIFs is against 
    the law. But then so is speeding, and I'm not the only person to get a 
    speeding ticket at the age of 16 (years ago).

10. You may find that you need two separate directories for GIFs -- one for
    compressed files and one for uncompressed files. Then you must weigh
    the compression on each individual file against the gain in space that
    resulted from the compression. If you only compress the file by 500
    bytes, and lose a lot of the original image, it would be obvious that
    compression of that file would not be worth the effort (although to
    discover that, you have to have already compressed it!). Basically,
    it's your call as to what is an acceptable loss, and what's not.

My own personal feelings on this whole compression thing is this: If you
can't get back the ORIGINAL file, with its original information, don't
compress it, ESPECIALLY if you're distributing the compressed file(s) (such
as running a BBS). Leave the compression up to the individual, and make it
clear that uploaded files should not be compressed in any fashion unless the
original file(s) can be had (i.e. a lossless compression method such as
PKZIP, LHA, or ARJ). If Joe Downloader wants to compress his GIFs, that's
fine, but let HIM make that decision. "To each his own."

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Acknowledgements:
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Tests were run on a 13 Mhz IBM XT-Compatible machine, using Hercules Mono,
CGA, and VGA monitors and a 120-meg SCSI hard drive with 15ms access time.
Compression/decompression times will vary among the different CPU speeds,
obviously. The times in this article are for comparison to themselves only.

The author of GIFLITE is Tsung Ho, and may be contacted at the following
address:

     P.O.Box 938, Unit 105
     St. Catharines, Ontario
     L2R 6Z4  Canada

(Please note that current US-to-Canada postage is around 40 cents.)

GIF2JPG and JPG2GIF were written by the people at:

     Handmade Software, Inc.
     15951 Los Gatos Blvd., Suite 7
     Los Gatos, CA  95032

     +1 408 356 4143 (FAX)
     +1 408 358 1292

For more information on the JPEG format, write to:

     X3 Secretariat
     Computer and Business Equipment Manufacturers Institute
     311 First Street NW, Suite 500
     Washington, DC  20001-2178

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Addendum from the author:
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Shortly after this last segment was submitted to WWIVnews, someone submitted a 
copy of GIFBLAST, a new program first posted on the Internet to compress GIFs.
In my short trials with the program, it seems to compress the hell out of GIF 
files (albeit very slowly) with NO noticeable loss (that I can see). I plan to
do a follow-up review about this new program as soon as things calm down here
from my recent dive into married life and the subsequent trip to Disney World!

Send e-mail to Spackle #1 @19955 if you want information now on GIFBLAST, as 
I've created a small file outlining what it can do.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³          Filo's Mod of the Month            ³
               ³              by Filo (1@5252)               ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

[Editor's nOTE: the past three months on the Modnet have seen what most 
WWIV Sysops have come to consider the "pre-release drought" in the advance
of WWIV 4.22's release. Most mods that appear during this period usually 
take the form of bug fixes for previous releases, or cosmetic updates of
of mods designed for older releases of WWIV. The following Mod-of-The-Month 
selection by Filo is the best of the few mods that have appeared during this
period that could be considered "new and innovative" when compared to the
rest of the Modnet submissions.]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The Mod-of-The-Month Selection represents my choice of what appears to be a 
useful, practical mod to WWIV. It does not mean it is the best mod posted or 
even that it works as I may not have tested it. Given the limitations of this
media, uuencoded mods are NOT eligible for selection as mod-of-the-month. 
Further, I tend to reject mods that have had a number of fixes to them.

ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄFiloÄheaderÄ(c)ÄÄÄ¿
³ Mod Name:      WAF016.MOD               Author:  Wafwot #2 @2632           ³
³ Difficulty:    Easy/Medium              Date:    Oct 1, 1992               ³
³ WWIV Version:  4.21a Tested, should work with past/future versions.        ³
³ Description:   Sends E-Mail to a new user from the sysop. This sends the   ³
³                new user E-Mail, using a file in Gfiles. Nice feature!      ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

More Descriptive:
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
Ok, I have logged on to other BBS' in the country (not WWIV) and when I have
completed the newuser logon procedure, it tells me I have mail. I'm not sure, 
but I think (VBBS) has this feature. This mail tells me about the sysop, some 
features of the BBS, and/or other tidbits of useless <grin> information about 
the BBS. It makes some of the less experienced users jump for joy, because they
have mail on their first call... and you know how new users love to get mail!

Anyway, here it is. I have no idea if this has been done before, but I'd like 
to think it was my idea. I have over 900 mods, dating back to 1990, and I 
haven't seen ANYTHING like this. If it is someone else's idea, tough shit. I 
didn't steal it from you. <grin> Ok, Let go...


Step 1:
ÄÄÄÄÄÄÄ
Backup.


Step 2:
ÄÄÄÄÄÄÄ
Load up VARS.H and add the 'echo_off' variable to the int and extern int lists.
The examples below are from MY modded source, NOT an unmodded 'clean' source. 
So, if you see some variables that you don't have, don't add them. Just add the
'echo_off' variable. Sorry, I deleted the clean source... for no apparent 
reason. The 'echo_off' variable is used so that when you send the newuser 
E-Mail automatically, the user does not see all the lines associated with 
sending a load file via E-Mail. ie, File loaded into workspace, Saving...Mail 
sent to User #0, etc. It makes it seemless and invisible.

int...
    save_dos, screenbottom, screenlen, screenlinest, smwcheck,
    statusfile, sysop_alert, tempio, topdata, topline, two_color,
    userfile, usernum, useron, use_workspace, using_modem, wfc, x_only,
    chat_calls, lastrandom, force_chat, echo_off;
                            /* ^ ADD THIS */

...and again a little further down in the externs...

extern int...
    save_dos, screenbottom, screenlen, screenlinest, smwcheck,
    statusfile, sysop_alert, tempio, topdata, topline, two_color,
    userfile, usernum, useron, use_workspace, using_modem, wfc, x_only,
    chat_calls, lastrandom, force_chat, echo_off;
                            /* ^ ADD THIS */


Step 3:
ÄÄÄÄÄÄÄ
Save VARS.H and load up NEWUSER.C. This is the actual void that sends the 
E-Mail. Block copy the whole void to the end of your NEWUSER.C file.

void newuser_mail(void)
{
  char title[61],s[81],mail[81];
  messagerec msg;

  echo_off=0;                                      /* turns 'echo_off' */
  title[0]=0;                                      /* clears the title */
  strcpy(s,nam(&thisuser,usernum));                /* copy username to s */
  sprintf(mail,"%sNEWFORM.MSG",syscfg.gfilesdir);  /* finds the form ltr */
  load_workspace(mail,1);                          /* loads form ltr */
  msg.storage_type=2;                              /* set mail storage */
  inmsg(&msg,title,0,0,"E-Mail",0,s,0);             /* places ltr in mail */
  sendout_E-Mail(title,&msg,0,usernum,0,1,1,0,0);   /* sends E-Mail */
  ++thisuser.waiting;                              /* so newuser can read it */
  echo_off=1;                                      /* turns echo back on */
}


Step 4:
ÄÄÄÄÄÄÄ
This is where we will call the newuser_mail void. In NEWUSER.C, this is between
where the user pressed 'Q' to continue after he filled in all of his 
information, and before they have to re-enter their password. I liked it here 
because sending the mail will take a some (not much) time, and it DOES say 
'Please wait...' while the BBS assigns a user number. This was just the obvious
place.
    ok=0;
    newuser_mail();                             /* ADD ME */
    topscreen();
    do {
      nl();
      nl();
      npr("Your user number is: %d.\r\n",usernum);
      npr("Your password is: %s.\r\n",thisuser.pw); nl();


Step 5:
ÄÄÄÄÄÄÄ
Since we added a new void to NEWUSER.C, load up FCNS.H and add the new 
prototype to the newuser.c section.

void input_comptype(void);
void input_screensize(void);
void newuser_mail(void);                       /* ADD ME */
void input_pw(void);
void input_ansistat(void);


Step 6:
ÄÄÄÄÄÄÄ
Save FCNS.H (and NEWUSER.C if you didn't already), and load up MSGBASE.C.
Search for void load_workspace(blahblah) and make the following changes. Again,
this is making it so the newuser DOES NOT see the printed lines associated with
sending mail. Make the marked lines look like what is below. I indented my 
lines, because I like to be neat. <grin>

  else
    use_workspace=0;
  nl();
  if (echo_off) {                                             /* ADD */
    pl("File loaded into workspace.");                        /* INDENT */
    nl();                                                     /* INDENT */
    if (!use_workspace)                                       /* INDENT */
      pl("Editing will be allowed.");                         /* INDENT */
  }                                                           /* ADD */
}


Step 7:
ÄÄÄÄÄÄÄ
Now, still in MSGBASE.C, find void inmsg(blahblah) and make the following 
changes. Again, all we are doing is adding if statements to avoid printing
lines that we DON'T want printed with the newuser_mail. First, find the
section of code that deals with entering a title. You can just block copy
what I have here, or you can make the changes. Again, this came from my
modded source, so it may not be exactly what 4.21a should be.

  if (echo_off) {                                               /* ADD ME */
    nl();
    helpl=6;
    title[0]=0;
    if (okansi()) {
      prt(2,"Title: ");
      mpl(60);
      inputl(title,60);
    } else {
      pl("       (----------------------------------------------------------)");
      outstr("Title: ");
      inputl(title,60);
    }
  }                                                             /* ADD ME */

Then directly under this section of code, add this if statement. This is
making a personalized title. A nice touch, if I don't say so myself.

 if (!echo_off) {
    sprintf(title,"WELCOME %s!",thisuser.name);
  }


Step 8:
ÄÄÄÄÄÄÄ
Further down in void inmsg(blahblah) in MSGBASE.C, find this section of code 
and make the indicated changes/additions.

      save=exist(fnx);
      if (save) {
     if (echo_off) {                                         /* ADD ME */
       pl("Reading in file...");                             /* INDENT */
     }                                                       /* ADD ME */
      }
      use_workspace=0;


Step 9:
ÄÄÄÄÄÄÄ
Still further down, find this code, and make THESE changes.

      case anony_real_name:
     real_name=1;
     *anony=0;
     break;
    }
    if (echo_off) {                                             /* ADD ME */
      outstr("Saving...");                                      /* INDENT */
    }                                                           /* ADD ME */
    if (fsed) {
      i5=open(fnx,O_RDONLY | O_BINARY);
      l1=filelength(i5);
    } else {


Step 10:
ÄÄÄÄÄÄÄÄ
And again.... further down in void inmsg, find this code, and make the
indicated changes.

    farfree(b);
    farfree(b1);
  }
  s2[0]=0;
  if (echo_off) {                                               /* ADD ME */
    strcpy(s,"Mail sent to ");                                  /* INDENT */
  }                                                             /* ADD ME */
  if (sy==0) {
    read_user(un,&ur);
    ++ur.waiting;
    write_user(un,&ur);


Step 11:
ÄÄÄÄÄÄÄ
And now.... at the very bottom of void inmsg, make this indicated change.

  save_status();
  if (!wfc)
    topscreen();
  if (echo_off)                                                 /* ADD ME */
    pl(s);                                                      /* INDENT */
  if (s2[0])
    pl(s2);
}

I know I didn't need some of those brackets, but I may add some stuff later,
and they don't seem to effect anything.


Step 12:
ÄÄÄÄÄÄÄÄ
Ok, now just in case the newuser gets dumped off line, or they hangup on you in
the middle of getting sent E-Mail from the newuser_mail void, we will add the 
following line to LILO.C so that the echo_off variable equals 1. 'echo_off' 
must ALWAYS equal 1 except when send a newuser mail from this mod. If echo_off
equals 0, then your regular, registered user will not see the 'Saving...Mail 
sent to Jest #1' lines that they normally do. This will force echo_off to be 1
for EVERY caller. In void getuser(void), near the top, add this one line.

  ok=0;
  checkit=1;
  okmacro=0;
  echo_off=1;                                                   /* ADD ME */
  actsl=syscfg.newusersl;
  if ((!net_only) && (incom)) {
    sprintf(s,"%sWELCOME.ANS",syscfg.gfilesdir);
    if (exist(s)) {
      nl();
#ifdef OLD

Step 13:
ÄÄÄÄÄÄÄÄ
And again, just for safety, add this one line in XINIT.C. This will make 
echo_off equal 1 whenever the BBS is loaded up. In void init(void) in XINIT.C 
find this code and add the indicated line.

#ifdef EMS_XMS
  if (_OvrInitEms(0,0,16)!=0)
    _OvrInitExt(0L,0);
#endif

  userfile=-1;
  configfile=-1;
  statusfile=-1;
  dlf=-1;
  curlsub=-1;
  curldir=-1;
  echo_off=1;                                                   /* ADD ME */
  setvect(save_dos, getvect(INT_REAL_DOS));
  oldx=0;


Step 14:
ÄÄÄÄÄÄÄÄ
That should do it. Save all files and compile/link. You will compile the whole 
BBS, since we added a variable to VARS.H.

Step 15:
ÄÄÄÄÄÄÄÄ
You need to create a NEWFORM.MSG file. This is the file that is sent to the 
newuser. I have installed an MCI mod into our BBS, so mine is kinda full of MCI
commands that place the newuser's name, and other info into the mail. It really
looks nice when a newuser logs on, and they get mail that looks as though the 
sysop wrote it to them! I recommend a good MCI mod to go along with this mod. 
Below is my NEWFORM.MSG. You can use it, or create your own. (I removed the 
MCI codes from it, and changed it around for one sysop... The Evening Post has
two.)

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Welcome to The Evening Post!

You have successfully logged onto one of Whidbey Island's most exciting
bulletin boards. Thanks for calling!

As you can see, The Evening Post is setup to automatically send you 
E-Mail. You should respond to this mail, by pressing 'A' at the
E-Mail prompt (Mail {?}).

With most prompts, pressing a '?' will get you help. You will be 
presented with a menu of available commands for the prompt. It's
really quite simple. If you do have trouble, press and hold the 
control key (Ctrl) while pressing the letter 'O' key. (CTRL-O). 
This will give you context-sensitive help throughout the BBS, any-
where you may be. 

If you want to change any features of your new account, just press 'D' 
to go to D:efaults. Here, you can change just about anything 
pertaining to your account.

You now have full access to all of the BBS's message subs, file areas,
and external games. I am always adding new stuff to the BBS, so
call often!

If you have any questions, please press 'F' and send feedback to me.
I will be sure to answer it. I like hearing from all my users!

If you think I can improve the BBS, please let me know how, and I will
try to implement your suggestions.

Enjoy your visit, and call back often, you're always welcome!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Try to keep it short. Too long, and the user gets bored. If you use this mod, 
PLEASE, PLEASE, PLEASE send me E-Mail. I'd like to know what you think even if 
you hate it....

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³     WWIVnet-Compatible Network Listing      ³
               ³              Compiled 1/7/93                ³
               ³           By Red Dwarf (1@6264)             ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

[Editor's nOTE: This column will be a new feature of WWIVnews starting with
this issue. If you are part of a WWIV-compatible network that is not listed
below, have your Network Coordinator contact 1@6264 about having your
network listed]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
Network Name            Ident.  WWIVnet Node    IceNET Node     WWIVLink Node
Hosting BBS                     Hosting BBS Phone Number
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
CaffNet                         @3101
Star-Lit BBS                    301-229-2957
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
CHAOSnet                        @4954
The Elm Street BBS              419-422-9742
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
EliteNET                                        @2462
Alley Closed BBS                214-238-8121
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
ExpressNET                      @6754
Data Express                    617-247-3383
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
NorthStarNET            #&      @6259           @6259           @16259
AeroTech                        612-935-3505
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
NukeNet                                                         @14063

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
RATnet                  ^&                      @6255
Rat Land                        612-647-9530
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
SOLARnet                #$&^    @3484           @3454           @13495
Rap City [GSA]                  314-963-7960         
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
StarNet                         @3956                  
Diamond's BBS                   319-277-0166
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TeenNet                                         @4053           @14064
Central Station                 410-315-9854
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TerraNET                #^&     @8861           @8857
Blue Thunder                    818-848-4101
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TestNet                         @19960          @9994           
Test Site BBS                   919-760-4811
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TheLink                 L       @4718
Dislexia BBS                    407-851-9531
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
WWIVweb                 #       @5813           @5802
Sanctuary                       508-892-8529
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
*.Net                                           @2459
Reynard's Keep                  214-406-1264
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
KEY:
! Ä Registered Wayne Bell's NETUP software
# Ä Uses other automatic update software
$ Ä Long Distance assistance available
* Ä Restictions Apply to this network
& Ä Application available in master file (NmmddyyA.ZIP)(Net Applicatons)
^ Ä High Speed Connections (9600+)
% Ä PcPursuit
L Ä Local Network (within area code)

Please inform me of any errors in your network's listing.

Red Dwarf:
1@6264 WWIVnet
1@6256 IceNET

The File Pile BBS:
612-351-0144  2400 Baud [ISB]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³             Dateline: @#$*()#!              ³
               ³     Editor's Notes by Omega Man (1@5282)    ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

...Ok, ok, so it's been almost three months since the last issue of WWIVnews
was distributed across WWIVnews. Judging from the amount of mail I've gotten
regarding the status of the next issue, I suppose it's safe to say that a
LOT of you have been virtually going through withdrawals of some sort without
a WWIVnews fix. Most of you, naturally, want an explanation of some sort as
to what caused the delays, right?

...Well, without going into some really personal matters, I'll simply say that
WWIVnews was delayed for almost three months because yours truly got tied up
with matters that were job-related and somewhat unforseen. These delays were
further hampered by yet another episode of "OM vs. The Hard Drive from Hell",
and combined with a new job that took up 78% of my free time. Adding to this,
oddly enough, was the presence of a 5'11" stunning brunette who measured in at
36-25-38 who proceeded to occupy the remaining 22% of my spare time. The fact
that she's got a really cute little tyke of a son with a case of the "terrible
twos" didn't help - or hurt - matters either.

...Fine. So I violated rule #1 of the Computer Geek's Code of Honor. I let a
woman come between myself and my computer. So sue me, eh? I apologize for
the delays regarding work and the hard drive crash, but as far as that other
22% of wasted time goes I'd gladly waste it again given the chance to choose
my own ending. In fact, after I finish sending this to Wayne...heh, heh, heh!

...In any case, WWIVnews is back on track now. The next issue will definitely
be out February 25th as scheduled, and will probably be dedicated to all the
fallout that will surround the release of 4.22 - and probably 4.22a, depending
on how good the beta testers were this time around. The previously-scheduled
special issue on WWIV-compatible networking has been delayed for a couple of
issues to allow a couple of submissions to be rewritten to cover 4.22's
gatewaying features.

...If anyone would care to submit articles for WWIVnews regarding either of
these particular topics, or would like to contribute to WWIVnews in any way,
shape or form, feel free to contact me via E-Mail at WWIVnet 1@5282. The
WWIVnews Writer's Guide revision will be available shortly as well, and will
contain an updated suggested assignment listing. This was intended to be
included with the 4.22 basic package, but those pesky time constraints kept
the Guide from making Wayne's deadline.

...Finally, an aside nOTE to all the @1's of the various WWIV-based networks:
I'll be contacting each of you regarding a synopsis of what your respective
network is all about shortly. Please take the time to submit something about
your network, regardless of how private you wish your network to be. For 
everyone to get a better global picture of what's happening to WWIV networking,
your cooperation will be extremely beneficial for the entire WWIV community of
sysops and users.

ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³                             Closing Credits                               ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³ WWIVnews is an independent newsletter NORMALLY published monthly as a     ³
³ service to the WWIV community of sysops and users. The opinions & reviews ³
³ expressed herein are the expressed views of the respective writers, & do  ³
³ not necessarily reflect those of the WWIVnews staff. Reproduction in whole³
³ or in part is allowed provided credits are given. All rights reserved.    ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³ The source site for WWIVnews is the Klingon Empire BBS (512-459-1088),    ³
³ WWIVnet node @5282. Requests for information regarding articles and other ³
³ editorial submissions, as well as back issue requests and the WWIVnews    ³
³ Writer's Guide, can be sent in e-mail to the WWIVnews editor, c/o 1@5282. ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³            WWIV and WWIVnet, copyright 1986,1990 by Wayne Bell            ³
³  Any product or company mentioned or reviewed herein are copyrighted of   ³
³  their respective owners, creators, and other corporate pseudoentities.   ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

```
