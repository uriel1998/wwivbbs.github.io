```

                Ú¿Ú¿Ú¿Ú¿Ú¿Ú¿ÚÄÄÄÄ¿Ú¿  Ú¿ÚÄ¿ Ú¿ÚÄÄÄÄ¿Ú¿Ú¿Ú¿ÚÄÄÄÄ¿
  ÉÍÍÍÍÍÍÍÍÍÍÍÍÍ³³³³³³³³³³³³ÀÄ¿ÚÄÙ³³  ³³³ À¿³³³ÚÄÄÄÙ³³³³³³³ÚÄÄÄÙÍÍÍÍÍÍÍÍÍÍÍÍÍ»
  º  Volume 3   ³³³³³³³³³³³³  ³³  ÀÅ¿ÚÅÙ³  ÀÙ³³ÀÄÄÄ¿³³³³³³³ÀÄÄÄ¿ September 28º
  º   Issue 5   ³³³³³³³³³³³³  ³³   ³³³³ ³Ú¿  ³³ÚÄÄÄÙ³³³³³³ÀÄÄÄ¿³    1992     º
  ÈÍÍÍÍÍÍÍÍÍÑÍÍÍ³ÀÙÀÙ³³ÀÙÀÙ³ÚÄÙÀÄ¿ ÀÅÅÙ ³³À¿ ³³ÀÄÄÄ¿³ÀÙÀÙ³ÚÄÄÄÙ³ÍÍÍÑÍÍÍÍÍÍÍÍÍ¼
            ³   ÀÄÄÄÄÙÀÄÄÄÄÙÀÄÄÄÄÙ  ÀÙ  ÀÙ ÀÄÙÀÄÄÄÄÙÀÄÄÄÄÙÀÄÄÄÄÙ   ³
            ³ Serving WWIV Sysops & Users Across All WWIV Networks ³
            ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ
                           ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
                           ³This Month's Features³
ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³ Random Factors.......................................Wayne Bell (1@1)       ³
³                                                                             ³
³ TechnOTES............................................WWIVnews Staff         ³
³                                                                             ³
³ Squashing Those Gluttony .GIF's (Part 1).............Spackle (1@1995)       ³
³                                                                             ³
³ Tackling DGROUP with External String Management......Elrond (8@4)           ³
³                                                                             ³
³ Filo's Mod of the Month..............................Filo (1@5252)          ³
³                                                                             ³
³ Dateline: @#$*()#!...................................Omega Man (1@5282)     ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³               Random Factors                ³
               ³   Creative Commentary by Wayne Bell (1@1)   ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

A few comments on the future directions of WWIV and WWIVnet:

The next version of WWIV will be v4.22, out probably around the beginning of
the year. It will support gating subs among networks, and subboards by name
(up to 7 chars, not starting with a digit), in addition to subs by numeric 
type. (That part is already done and seems to be working - and requires net32)

I also plan on redoing the userlist, to have, in the standard structure, most
of the things that people have been adding (address, that kind of thing).
Quickscan pointers will, however, be stored in a different file. This will
allow up to 999 subs and 999 dirs in the BBS. There will be an option in INIT
to allow you to specify the max # subs/dirs, and will reformat the quickscan
file for that new number. Note that specifying more subs uses up more memory.

Net32 should be out in a month or so. It will have the new support for subs by
name, and sub gating (but requires v4.22 for that to work). There have also 
been a bunch of fixes and requested enhancements (the network name is now in
the net.log file, for one).  It should also run somewhat faster unpacking 
local mail, should work with multi-line systems better, will gate email, and
filter out duplicate posts.

Also, to restate a previous position of mine, please do not start up your own
network unless A) you know what you're doing and how to run it, >AND< B) it 
will really be different than a currently-existing network in some way.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³                 TechnOTES                   ³
               ³        Compiled by the WWIVnews Staff       ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

...While McAfee and Norton continue to wage war against computer viruses
through software protection methods, until now the only way to prevent
infection through hardware means was to use write-protect tabs for their
only known use. Multix of Dallas, Tx has developed the ViruStop, a bus card 
that offers antiviral protection by monitoring data crossing the system bus 
for signs of viral activity. 

...The ViruStop is an 8-bit short card that plugs into any free slot, and is 
automatically invoked after the system BIOS is uploaded. Acting as a filter
of sorts, the ViruStop inspects all data prior to being processed, regardless
of whether it's operating systems, programs, or system data. Since all viruses
possess certain common characteristics, ViruStop is designed to take note of
these danger signs and other peculiar behavior patterns and suspend operations
and notifies the user of a probable viral presence. 

...Since ViruStop is not a memory-resident program, and requires no TSR's or
software interface, there is no loss of RAM occurred when installed. Also,
since the bus itself is monitored directly as opposed to scanning the RAM and
peripheral memory devices (as most software-based scanning utilities do),
there is no perceivable loss of system performance caused by ViruStop.

...a side nOTE about ViruStop: word down the pipeline hints that certain
manufacturers may be offering the card as a standard feature on their new
systems. Multix reportedly has also been approached by Gateway regarding an
local bus version of the ViruStop for a new line of local bus motherboards.
As viruses can only infect through certain methods inherent to DOS that will
probably not change anytime in the near future, no upgrade to the ViruStop
will be necessary.

...ok, admit it. You've gone "ooh!" and "aaah!" and "c00l, d00d!" when you
saw those "Intel Inside" ads on TV. You have, we have, everyone has. And
with good reason, too. They're visually striking any way you look at them.
But answer this one honestly: Have these ads actually influenced your new
system purchases? According to several industry sources, the answer is 
"probably not."

...Despite all the ads and hype about the satisfaction and peace of mind
one can have by using only Intel chips, most system retailers are reporting
very few specific inquiries regarding whether the processors are Intol or
not. One Computerland employee, who asked to remain nameless, commented that
"those few who do inquire in most cases turn out to be novice computer users 
who obviously don't raid the fridge during the commercial breaks!"

...While the ads havn't exactly increased Intel's sales as dramatically as
Intel had hoped, computer retailers are reporting that while users aren't
turning a deaf ear and a blind eye to alternative processors, they are 
showing an increasing interest in the capabilites of Intel's DX2 series of
chips. The added cost of purchasing a system with an processor manufactured
by Intel becomes a moot point only when the performance exceeds that of
the competition. Thus, the bottom line appears to be that consumers are more
interested in purchasing systems with processors with the highest performance 
and the lowest cost, regardless of who manufactured them. 

...One of the benefits of an internal modem is that you don't have to worry
about spilling your coffee on it in the morning. However, in exchange for
that peace of mind, you usually have to sacrifice those fancy external
readouts that not only tell you how fast your modem is leeching wares from 
every BBS on your dialing directory, but impress your computer-illiterate 
as well.

...Image Communications, creators of the Twincom line of modems, has provided
a solution for this dilimma. The "Twincom Dashboard" is a modem add-on that 
provides the company's 14.4DFI (v32bis 14.4k internal fax/modem) with an 
external status readout. This readout consists of 20 LED's. 8 of which display
the status of the basic modem functions, while the remaining 12 are used as
a "speed indicator" for data transfer rates. The Dashboard connects to the DFI
via a cable, and is available for mounting in two versions: attachment with a 
Velcro strip, or molded to a face plate for mounting in a spare drive bay. 

...At press time, the Dashboard works only with the Twincom DFI, but the
company is looking into adapting it to the other modems in the Twincom line
depending on consumer demand. Price was also not set at press time, but
is expected to be $79 direct from the company.

...Interested in a CD-ROM drive for your board? Then take nOTE of this: DAK
has lowered the price of the BSR 6800MX to $199. No, that's not a misprint,
either. This is reputed to be the lowest price yet for a CD-ROM drive, and
reports from DAK are that the drives are selling like hotcakes. Oddly enough,
this shouldn't come as too much of a surprise, as DAK's founder Drew Kaplan
has been both a data and audio CD-ROM advocate for quite some time.

...There's a good and a bad side to these drives, however. While they will
play regular audio CD's, the access time for data CD's is a somewhat limping
800 milliseconds - just 200ms under the Multimedia Council's specifications.
Considering the rest of the industry is gearing up for a standard access time 
roughly half that of the 6800MX, this may seem a bit slow for those needing 
faster access times. In fact, those who need real-time motion video playback
probably would be better off with a faster (and more expensive) drive.

...Still, for BBS usage, 800ms isn't too slow at all. To be honest, DAK's BSR 
deal might be a godsend to those wishing to provide their users with as much 
data as possible. With several shareware collections and periodical collectons
available on CD-ROM, each respectively containing several hundred of the latest
public domain programs and several years worth of hundreds of periodical runs,
keeping the ware leeches and info addicts happy might have become a bit easier
for sysops everywhere.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³  Squashing Those Gluttony .GIF's (Part 1)   ³
               ³             By Spackle (1@1995)             ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

This article begins a three-part series of articles discussing the various
GIF (Graphics Interchange Format) picture file compression methods, their
pros and cons, and a sample test with sample GIF files. The complete
article (12K archived) is available for download at The Rubicon in Raleigh,
North Carolina at 919-676-0738 under the filename of GIFCOMPR.LZH. Sysops
are auto-validated first call. This would make an excellent G-File, and is
good download information as well.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

GIF Compression: The Basic Archiving Methods
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

So you've got a kajillion of those great-looking GIF files lying around taking 
up disk space. Sure, they're always there to look at, and anyone can download
them, but what if you need to install the new Borland C++ 3.0?  I have heard 
rumor to the effect that this compiling masterpiece takes up a robust 30-or-so 
megs of disk space... That's a lot of space, even with today's standard 100- 
and 200-meg drives. So what do you do if you want still more out of your hard 
disk?  We'll explore the options here, as well as the good and bad points of 
each method.

There are three basic roads you can travel... Here are a few ideas that we'll 
be looking at:
     
  1. You can archive them using one of the many popular archiving programs
     such as PKZIP, LHA (formerly called LHARC), or ARJ.

  2. You can use GIFLITE to compress the GIF by removing the non-essential
     video information. This option allows the GIF to remain a GIF (an
     8-bit format), thereby making viewing easy.

  3. You can also use GIF2JPEG to remove non-essential information, as
     defined by the Joint Photographic Experts Group. (For more information
     regarding the JPEG standard, write to the address at the end of this
     article.)  However, JPEG is a 24-bit format and is therefore unviewable
     on practically anything but a TARGA card or a PS/2 with an XGA card.

Let's explore each of those at length...

The Archiving Method:
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The idea behind archiving is simple: you put files you don't necessarily need 
right away into another file, which is a compressed version of the originals. 
That having been said, here's a tiny comparison of the three most popular 
archiving programs, PKZip, LHA (LHARC), and ARJ:

This is a directory listing of the GIF files being archived, as well as their 
respective resolutions (given as Height X Width X Number of Colors):

  Filename.EXT    Size    Date     Time    Resolution
  ÄÄÄÄÄÄÄÄÄÄÄÄ   ÄÄÄÄÄÄ  ÄÄÄÄÄÄÄÄ ÄÄÄÄÄÄ   ÄÄÄÄÄÄÄÄÄÄÄÄÄ
  3babes.gif     260608   6-06-90  3:52p   (640x480x256)
  calvin2.gif      8192  11-27-90 11:45a   (320x200x16)
  claudia.gif    107520   3-08-92 11:15p   (607x774x16)
  waterfal.gif    22144  10-04-89 12:47p   (576x360x4)  (interlaced)

  (Total size: 398464 bytes)

These four files were chosen as representative because there are two "standard"
GIFs (one VGA and one Super-VGA) and two odd-sized/colored ones (last two), as 
well as the disk size of the GIFs (one huge, one large, one average, and one 
tiny one).

For reference (i.e. where the GIFs originated), I will give short descriptions 
of the files:

  3BABES  .GIF - Three bikini-clad women - digitized video or photograph
  CALVIN2 .GIF - Calvin from Calvin & Hobbes cartoon - scanned or drawn
  CLAUDIA .GIF - Claudia Shiffer - scanned image (probably retouched)
  WATERFAL.GIF - Scanned image of Escher's waterfall - INTERLACED image

Now here's a comparison of the various archives (ZIP, LZH, and ARJ) when each 
of these files was added to its own archive:

  Filename.EXT    Size     Date    Time   Time to archive
  ÄÄÄÄÄÄÄÄÄÄÄÄ   ÄÄÄÄÄÄ   ÄÄÄÄÄÄÄ  ÄÄÄÄÄ  ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
  testgifs.arj   393634   6-11-92  6:38p      2:21.86
  testgifs.lzh   393252   6-11-92  6:34p      2:01.00
  testgifs.zip   398878   6-11-92  6:36p      0:59.21

As you can see, LHA does the tightest compression, with ARJ close behind. 
PKZIP doesn't quite compare, but makes up for this with much faster 
compression. In fact, PKZIP _ADDS_ to the size of the GIFs. That being the 
case, if you're simply archiving and looking for more drive space, LHA is a 
clear winner; if you're looking to save time and don't care about space, PKZIP 
wins hands-down. ARJ fits somewhere in between those two. I use LHA myself for 
everything but files needing PKZIP's -AV codes (such as McAfee's Viruscan, 
Clean, etc.).

However, archiving has the downside that you can't load up CompuShow and view
the GIFs... you have to unarchive them first. Unarchiving with LHA and ZIP 
takes essentially the same amount of time, with ARJ falling slightly behind.
Still, that's an added inconvenience. Let's look at another method of GIF 
compression: GIFLITE.


The GIFLITE Method:
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

GIFLITE is a GIF compression program that basically filters out unnecessary
(or non-visible) image information. The documentation for GIFLITE does not
mention any special compression algorithms; therefore, it is my understanding
that it only removes non-vital information from the image. The difference
in GIFLITE-compressed and non-compressed images is usually not detectable by
the human eye. Therefore, GIFLITE may be considered "safe" to use, in that
the before- and after-compression images look virtually alike. There are
exceptions to this rule, however. Large, complex GIFs (1024x768x256 SVGA,
for example) tend to not only take forever to compress, they lose some of
their information. Still, at 35-50% compression, few people will harp over
a slight image quality loss.

GIFLITE also offers three different methods of compression. You can specify
these with the -mX parameter, where X is 1, 2, or 3. Method 1 (the default
if none is specified) produces an output file with maximum compression. Method 
2 produces a less-compressed file, and Method 3 produces a least-compressed 
file. For most GIFs, the output images are almost identical to the source 
images. For some images, however, such as hand-drawn images, or images with 
detailed texture, Method 2 and Method 3 will preserve more of the quality of 
the original images.

GIFLITE is easy to use and useful, but if you want a backup of the original
GIF, you will either need to make a COPY, or GIFLITE can make one for you if 
you use the -b parameter. If this copy is lost, however, there is no recourse 
for getting it back. GIFLITE compression is irreversible, which means that you
cannot compress and then uncompress a GIF to its original state.

The upside to all this is that the image quality is almost always intact. You 
can readily view the compressed image as if it was any other GIF, and there's 
also the fact that you've saved yourself some precious disk space.

That having been said, let's take a look at our sample files. We'll make a 
chart to show their original sizes, the post-compression size, the percent size
reduction, the time for compression, and a small comment on any post-
compression image degradation, if I can detect any (I have 20/20 or better
vision in both eyes... <grin>).

  ÚÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
  ³GIF File ³  3BABES.GIF   ³ CALVIN2.GIF   ³ CLAUDIA.GIF  ³ WATERFAL.GIF ³
  ³Resolut. ³ (640x480x256) ³ (320x200x16)  ³ (607x774x16) ³ (576x360x4)  ³
  ÃÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
  ³Method 1 ³WAS  260.61 Kb ³WAS  8.19 Kb   ³UNREGISTERED  ³WAS  22.14 Kb ³
  ³         ³NOW  165.59 Kb ³NOW  7.61 Kb   ³VERSION WILL  ³NOW  21.76 Kb ³
  ³ Redux   ³36.4% reduction³7.0% reduction ³NOT COMPRESS  ³1.7% reduction³
  ³ Time    ³Time: 11:59.09 ³Time:  2:02.05 ³IMAGES BIGGER ³Time: 22:40.29³
  ³ Loss?   ³Minimal loss   ³No visible loss³THAN 640x480  ³No loss at all³
  ÃÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
  ³Method 2 ³WAS  260.61 Kb ³WAS  8.19 Kb   ³UNREGISTERED  ³WAS  22.14 Kb ³
  ³         ³NOW  192.10 Kb ³NOW  7.61 Kb   ³VERSION WILL  ³NOW  21.76 Kb ³
  ³ Redux   ³26.2% reduction³7.0% reduction ³NOT COMPRESS  ³1.7% reduction³
  ³ Time    ³Time:  9:41.88 ³Time:  2:00.78 ³IMAGES BIGGER ³Time: 22:39.40³
  ³ Loss?   ³Minimal loss   ³None visible   ³THAN 640X480  ³No loss at all³
  ÃÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
  ³Method 3 ³WAS  260.61 Kb ³WAS  8.19 Kb   ³UNREGISTERED  ³WAS  22.14 Kb ³
  ³         ³NOW  204.54 Kb ³NOW  7.61 Kb   ³VERSION WILL  ³NOW  21.76 Kb ³
  ³ Redux   ³21.5% reduction³7.0% reduction ³NOT COMPRESS  ³1.7% reduction³
  ³ Time    ³Time:  8:00.26 ³Time:  2:00.67 ³IMAGES BIGGER ³Time: 22:39.68³
  ³ Loss?   ³None detectable³None visible   ³THAN 640X480  ³No loss at all³
  ÀÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

As you can see from the chart, the three compression Methods are really quite 
similar for animated or digitized images, just as the documentation says. 
Scanned and retouched or hand-drawn images receive quite a bit of attention, 
and "suffer" a might bit of compression as well. Unfortunately, unregistered 
versions of GIFLITE will not compress images greater than 640x480, so no 
information is given for CLAUDIA.GIF. (Had I known that when I started this 
project, I would have chosen another file.)  However, it goes to illustrate 
the idea behind Shareware, which is that you should register and pay for those 
programs that you use, and the fact that not all GIFs are created equal, and 
none have inalienable rights to your disk space.

I can also mention that these results are quite different from the AVERAGE I 
have gotten from all the compressions I've done on my board. Most of my GIFs 
are like 3BABES - scanned and digitized. Those result in the biggest gains. And
when you consider a board like mine, with over 80 megs and 500 files of just 
GIFs, even a small gain of 10Kb per file compressed gives an extra half a meg
of disk space. Consider also that the average percent reduction is 35-50% on 
most GIFs; Think about gaining an extra 35% of your disk space back!

[To be continued in next month's issue of WWIVnews]


ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³            Tackling DGROUP with             ³
               ³         External String Management          ³
               ³              by Elrond (8@4)                ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

DGROUP: 

The word alone is enough to send shivers down the spines of even the most
experienced WWIV modders. To them, DGROUP conjures up living nightmares of 
installing complex modifications, only to wind up having to pull out their 
favorite (and largest) mods because they took up too much DGROUP space. For 
others, the less initiated, it brings up a several questions: For instance,
what the heck is it, and how come everyone is always so caught up in it? 
And above all, how can I get rid of the problems it causes?

Let's start from the beginning. Assuming that the vast majority of people
out there really do not have even the slightest knowledge of Pascal, C, or
Assembly, I will try and keep things simple. A program has several different
segments of memory that are assigned to it. One of these segments is called
the DGROUP, which is a group encompassing several memory segments that can be
referred to as a single group. DGROUP is short for the (D)ATA GROUP, and it
is where certain parts of the current (EXEC'ing) program are stored. I will
not get into the sub-segments within the DGROUP, because it is enough to say
that it holds parts of the program, which of course for us is WWIV.

One of the major parts of any program's data is text. When a program is
compiled, it is translated into the binary language (machine language) that
your CPU can understand. Most of what goes into a program is actually ignored 
or simplified when a program is compiled, for the CPU has no use for this extra
information. We only include it in our programs in order to increase the
readability of the code. Addition, subtraction, variables, and the other common
parts of your program are translated into their simple equivalent instructions
that your CPU can understand. However, the text, or strings in your program
cannot be translated to some simpler equivalent. If they were, then you 
obviously would not be able to read them. So, when a program is compiled, any
text that gets sent to any device (be it the CRT, COM port, LPT port, whatever)
is kept in its original state.

If you have lots of text in your program (and BBS systems have a lot just by
their very nature) then the DGROUP segment starts to get filled up rather
quickly. Each character in a string takes up at least one byte of memory, so
one thousand characters will take up about a kilobyte. Wayne was smart(?)
enough to compile his program in a memory model that only allocates 64
kilobytes for the DGROUP segment. So, when you fill that up, your finished. 
No more modding. You get a compiler error, and so you are up against a brick
wall. Right?

To many sysops, this is exactly what they thought. If they did understand
DGROUP, at least slightly, they would go rip out a big mod, like a time bank
or a fancy file listing system. Then they could compile again, but they would 
be stuck without being able to install any more of the neat mods that come out 
every day. I can remember myself running around all the different support 
boards at the beginning of last summer looking for *SOMETHING* that would 
save me from that infernal compile message. I installed lots of little, very 
inefficient fixes - the DGROUP error went away for a mod or two, but then it 
was back to plague me again. 

Then one day Tolkien released ESM, and thus changed the way that people thought
about DGROUP altogether.

ESM, or External Strings Manager, is a program to help you cut down on the
amount of DGROUP that WWIV takes up. The logic behind this is that if you can 
get the strings out of the program, and into an external file, then they will 
not have to be loaded every time the program is run. Whoever first came up with
this idea (it was not an original) is someone we owe a lot to. With the strings
out of the main program and in an external file, we virtually eliminate as much
DGROUP space as we choose to - it all depends on how many strings we remove.

ESM is very efficient (and FAST!!) at retrieving strings from the external 
file. Even on an 8 mhz. 286, there is hardly a noticeable delay while the call
to get a string from the external file is executed. Plus, the ESM editor (for
editing strings in your external strings file) makes it easy to change what a
string says, and you don't even have to re-compile your BBS when you do it.

There is only one major drawback with ESM, and that is it takes a long time to
manually remove the strings from your source code and paste them into a strings
file. This can take literally hours, if not DAYS, and it is a very slow and 
painstaking process. You cannot afford to screw up a string, or you'll wind up
printing out the wrong one. That can look very funny, but is still a bit
embarrassing. With the recent upgrades to ESM, however, this task can be done 
automatically with a special utility program (available only to registered ESM
users). Using this utility, you can generate a strings file by letting the 
program go through and pull out the strings for you. Therefore, it is a very
fast and effortless process. 

If you do not plan on registering ESM, there is an alternative. I have written
a program which I call ASR, or Automatic Strings Remover, which does virtually
the same thing. Best of all, it is free, like all the software that I write
(and it looks neater, too, but that's just an opinion). 

A note on the side: There was a mod released some months ago onto the modnet
which will allow WWIV to compile in a much larger memory model, and thus allow
1024 k of DGROUP. This will obviously be much more than you will probably ever
use. But if you want my advice, I wouldn't install it. Here's why: It is way 
too unstandard. Installing this mod not only stops you from using the wonderful
MAKE interface, but it also forces you to rewrite most of the routines in some
of the major C files. Sure, the replacements are included, but they are very 
confusing, probably (no guarantees) not very well coded, and that much more 
difficult to deal with than the ESM/ASR combination. There also is the chance
that other mods will conflict or not work at all with this one installed. All 
told, I suggest that you steer clear of it. If Wayne himself ever takes it upon
himself to rewrite WWIV to support this memory model, then you we can all stop 
worrying about DGROUP, but that's just it - he hasn't.

With ESM and its support programs, or with ESM and ASR, you can very easily 
eliminate those horrible DGROUP errors and get back to the business at hand,
which is adding more mods, of course. Regardless of how good a modder you may
be, sooner or later you will reach the limit of the DGROUP segment. Go grab ESM
and ASR, install them, and then basically forget them. Then, go treat yourself
by installing the biggest, most DGROUP consuming mod that you can find on the
Modnet which you couldn't dare install before. Good luck with your modding!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Where to obtain ESM and ASR:

ESM, External Strings Manager
Current version     : 1.04 (shareware), 2.00 (registered)
Author              : Tolkien
BBS name            : The Fellowship
WWIVnet             : @3456
Phone number        : (314) 664-5777
Auto Validation     : YES
WWIV support board  : YES
High speed modem    : v32, v32bis, HST (14,400 and lower)

ASR, Automatic Strings Remover
Current version     : 1.50 (freeware)
Author              : Ellrond
BBS name            : Silicon Valley
WWIVnet             : @9987
Phone number        : (919) 765-8640
WWIV support board  : NO
Auto Validation     : YES
High speed modem    : v32, v32bis, HST (14,400 and lower)

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³          Filo's Mod of the Month            ³
               ³              by Filo (1@5252)               ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

The Mod-of-The-Month Selection represents my choice of what appears to be a 
useful, practical mod to WWIV. It does not mean it is the best mod posted or
even that it works as I may not have tested it. Given the limitations of this
media, uuencoded mods are NOT eligible for selection as mod-of-the-month.

This month's offerings contained three mods that really appealed to me. All
three involved features that are already in NET32 but which are definitely
needed in NET31 and v4.21 usage: a NETNAME in the name of the Sub, a NETNAME
in E-mail response to user, and a force specific network callouts. The latter
is the one that I have chosen to put here.

This is another of Darrel Mobley's fine mods:

ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³ Mod Name:    :  DDM-0002.MOD          Author :  The Primerican #1    ³
³ Difficulty   :  Moderate              Network:  WWIVnet @9402        ³
³ WWIV Version :  4.21a                 Files  :  NETSUP.C             ³
³                                                                      ³
³ Description  :  This mod allows you to force a callout to other      ³
³                 network node numbers than your main network.  4.21a  ³
³  (9/12/92)      does not check to see if you use the same node #     ³
³ CALLOUT4.21B    in more than one network during Forced Callout "/".  ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ
                                                                      
What this does:

I noticed from my WFC screen in the net pending list that if I had two nodes
sharing the same number but were in different networks, the "/" Force Callout
command would always force the callout to the node in the primary network.

This is the second version of the mod. This will ONLY prompt you IF there are
two nodes sharing the same node number within multiple networks on your system.
The first mod asked the network to force from on each callout attempt, this one
only asks for the network if it finds more than one network sharing the same
node number.

On with the mod.

Disclaimer: Why bother? You KNOW to back up your source! Grin.

Replace the entire void "force_callout(void)" with this void:

void force_callout(void)
{
  int i,i1,i2,i3,index,ok,sn,nn;
  int nv,onxi,odci,abort;                                                   
  float fl,fl1,fl2,ffl;
  long l,l1;
  char ch,s[81],s1[81];
  char *ss,onx[20],*mmk;                                                    
  struct time ti;
  net_system_list_rec *csne;                                                

  time(&l);
  nl();
  prt(2,"Which system? ");
  input(s,5);
  sn=atoi(s);
  abort=0;                                                                  
  if (sn && (net_num_max>1)) {                                              
    odc[0]=0;                                                               
    odci=0;                                                                 
    onx[0]='Q';                                                             
    onx[1]=0;                                                               
    onxi=1;                                                                 
    nv=0;                                                                   
    ss=malloc(net_num_max);                                                 
    for (nn=0; nn<net_num_max; nn++) {
      set_net_num(nn);
      if (next_system(sn))                                                  
        ss[nv++]=nn;                                                        
    }
    if (nv==1) {
      set_net_num(ss[0]);
    } else {
      nl();
      for (i=0; i<nv; i++) {
        set_net_num(ss[i]);
        csne=next_system(sn);
        if (csne) {
          if (i<9) {
            onx[onxi++]=i+'1';
            onx[onxi]=0;
          } else {
            odci=(i+1)/10;
            odc[odci-1]=odci+'0';
            odc[odci]=0;
          }
          npr("%d. %s (%s)\r\n",i+1,net_name,csne->name);
        }
      }
      pl("Q. Quit");
      nl();
      prt(2,"Which network (number)? ");
      if (nv<9) {
        ch=onek(onx);
        if (ch=='Q')
          i=-1;
        else
          i=ch-'1';
      } else {
        mmk=mmkey(2);
        if (*mmk=='Q')
          i=-1;
        else
          i=atoi(mmk)-1;
      }
      if ((i>=0) && (i<nv)) {
        set_net_num(ss[i]);
      } else {
        nl();
        pl("Aborted.");
        nl();
        abort=1;
      }
    }
  }

  if (!abort) {
    if (!net_networks[net_num].con)
      read_call_out_list();
  
  
    i=-1;
    for (i1=0; i1<net_networks[net_num].num_con; i1++) {
      if (net_networks[net_num].con[i1].sysnum == sn) {
        i=i1;
        break;
      }
    }
  
    if (i!=-1) {
      if (!net_networks[net_num].ncn)
        read_contacts();
       ok=ok_to_call(i);
      i2=-1;
      for (i1=0; i1<net_networks[net_num].num_ncn; i1++) {
        if (net_networks[net_num].ncn[i1].systemnumber==sn) {
          i2=i1;
          break;
        }
      }
      if (i2==-1)
        ok=0;
      else
        if (!ok) {
          nl();
          prt(5,"Are you sure? ");
          if (yn())
            ok=1;
        }
      if (ok) {
        if (net_networks[net_num].ncn[i2].bytes_waiting==0L)
          if (!(net_networks[net_num].con[i].options & options_sendback))
            ok=0;
        if (ok) {
          nl();
          do_callout(sn);
        }
      }
    }
  } 
}

Recompile and enjoy!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³             Dateline: @#$*()#!              ³
               ³     Editor's Notes by Omega Man (1@5282)    ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

Editor's nOTE: The past four months worth of weekends have been spent by yours
truly on the monumental task of first upgrading @5282 to WWIV 4.21, and then
scrapping everything when Wayne released 4.21a and starting over. This task
included the monumental effort of evaluating over 750 WWIV mods with widely
varying levels of "assured compatibilty." 

As one could expect, it damned near caused this issue of WWIVnews to be 
replaced with a "Best Of" special issue I've got stashed away for such
emergencies...

As of this writing I'm almost finished with the upgrading. Despite several 
setbacks and several trips to my favorite place to kick back and think (which 
also happens to be my favorite topless bar, incedentally), the following 
commentary keeps burning in my thoughts every time I fire up MAKE.EXE.

Sympathize, identify, or villify. In any case, keep the above facts in your 
mind as you read some of what's been running through mine...

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Evolution and Change.

These are integral parts of the whole that we refer to as the "Computer 
Revolution." In the history of Mankind no previous form of socio-technological 
advancement has possessed such a propensity for consistent alteration and 
improvement and seen it utilized to an equal degree. Unlike any other type of
industrial or technological base, that which is produced and deemed "state of 
the art" when first designed is usually well on its way to becoming outdated by
the time it hits the open market. The degree of Evolution and Change in this
area is indeed that great.

As a result, survivability within the computer industry now requires that each 
new advancement be able to adapt readily to consistently evolving standards, 
and those who design said advancements must in turn be able to not only meet 
and even exceed these demands, but in essence predict future demands in well in
advance of their actual implementation. 

To accomplish this, designers must not only be users of the products themselves
but they must also be trailblazers as well. No longer is it simply enough to 
blaze the trail and hope the users will follow; designers must be willing to 
travel those trails already taken and determine the next best path to take
without choosing one that will force users to halt in their tracks.

WWIV and all its various facets are no exception to these forces of Evolution 
and Change. Witness the fact that the Turbo C version of WWIV has been upgraded
14 times in the near 5 years since Wayne's decision to abandon Turbo Pascal, 
and that the WWIVnet executables themselves have been upgraded more than twice
that number as well. This number of upgrades, while arguably far above current
industry averages, reflect not only improved software flexibility and 
functionality (not to mention bug fixes), but to accommodate the evolution of 
Turbo C as well. 

With WWIV and WWIVnet evolving and changing at these rates, those who design 
and test the literally thousands of modifications to the basic WWIV source code
are pressed harder than ever to not only accommodate users by debugging their 
mods thoroughly and providing instructions for seamless, efficient 
installation, but to provide improvements and additions to stock WWIV features
that may provide a permanent increase in versatility and user-friendliness.

This, in essence, is what truly motivates the WWIV modder in today's continuing
Computer Revolution. The desire to produce something that not only improves 
existing features of WWIV, but offers a new approach to a particular WWIV facet
that isn't so radical that it scares people away from implementing it. This
also, in essence, is the "catch" that any modder has to face. How modders
should handle this catch is the focus of this editorial.

Innovation and creativity is fine and dandy, but make damn sure that you've 
made it clear exactly what you're trying to accomplish. Without a proper 
approach to design and implementation, a mod that might be the best thing to 
hit WWIV since Wayne added color to the TP3 version could very well be ignored 
due to improper design, presentation, and implementation

In other words, modders, document your mods *properly*. Explain not only what 
they do, but *why* they are in fact an improvement over stock code. If your mod
is a radically different approach, go into details as to *what* is so different
about your mod, and *why* your way of doing things is that much better. If 
there are any "catches" to installing your mod, then make doubly certain that 
you explain them in detail, and what should be done to prevent getting stung by
them.

Carry on, modders! Blaze those trails to the future and blaze them well! We're
right behind you, so make sure you don't set ablaze the collective rear ends of
those who follow your path.

Including, of course, your own.

ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³                             Closing Credits                               ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³ WWIVnews is an independent newsletter published monthly as a service to   ³
³ the WWIV community of sysops and users. The opinions and reviews expressed³
³ herein are the expressed views of the respective writers, and do not      ³
³ necessarily reflect those of the WWIVnews staff. Reproduction in whole or ³
³ in part is allowed provided proper credit is given. All rights reserved.  ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³ The distribution sites for WWIVnews are the Klingon Empire BBS (512-459-  ³
³ 1088), WWIVnet node @5282, and the WWIVnews Editorial Desk networked      ³
³ subboard, subtype 15282 host 5282. Information regarding article and      ³
³ editorial submissions, back issue requests, and the WWIVnews Writer's     ³
³ Guide, can be requested in e-mail from the WWIVnews editor, 1@5282.       ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³            WWIV and WWIVnet, copyright 1986,1990 by Wayne Bell            ³
³  Any product or company mentioned or reviewed herein are copyrighted of   ³
³  their respective owners, creators, and other corporate pseudoentities.   ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

```
