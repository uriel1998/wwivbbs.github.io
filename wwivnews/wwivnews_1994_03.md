```

                  Ú¿Ú¿Ú¿Ú¿Ú¿Ú¿   Ú¿  ÚÄ¿ Ú¿ÚÄÄÄÄ¿Ú¿Ú¿Ú¿ÚÄÄÄÄ¿
    ÉÍÍÍÍÍÍÍÍÍÍÍÍÍ³³³³³³³³³³³³  ÚÅ´  ³ À¿³³³ÚÄÄÄÙ³³³³³³³ÚÄÄÄÙÍÍÍÍÍÍÍÍÍÍÍÍÍ»
    º Volume 5    ³³³³³³³³³³³³ ÚÅÅ´  ³  ÀÙ³³ÀÄÄÄ¿³³³³³³³ÀÄÄÄ¿ March-June  º
    º  Issue 2    ³³³³³³³³³³³³ÚÅÅÅÅÂ¿³Ú¿  ³³ÚÄÄÄÙ³³³³³³ÀÄÄÄ¿³    1994     º
    ÈÍÍÍÍÍÍÍÑÍÍÍÍÍ³ÀÙÀÙ³³ÀÙÀÙ³ÀÁÁÅÅÁÙ³³À¿ ³³ÀÄÄÄ¿³ÀÙÀÙ³ÚÄÄÄÙ³ÍÍÍÍÍÍÑÍÍÍÍÍÍ¼
            ³     ÀÄÄÄÄÙÀÄÄÄÄÙ   ÀÙ  ÀÙ ÀÄÙÀÄÄÄÄÙÀÄÄÄÄÙÀÄÄÄÄÙ      ³
            ³ Serving WWIV Sysops & Users Across All WWIV Networks ³
            ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

                           ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
                           ³This Month's Features³
ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³ Random Factors.......................................Wayne Bell (1@1)       ³
³                                                                             ³
³ Soft Servings:  News from WWIV Software Services.....Filo (1@2050)          ³
³                                                                             ³
³ Listing of WWIV Utilities for V4.23..................Joe Barbara (1@6101)   ³
³                                                                             ³
³ The "Helms Hoax" Exposed!............................Polekat (1@7385)       ³
³                                                                             ³
³ Seeking Asylum! An Inside Look at The Asylum Group...Zu Digital (1@7321)    ³
³                                                      and Sam (1@2077)       ³
³                                                                             ³
³ Filling in Gates' Gaps: Undocumented DOS Commands....MicroSource Sysop      ³
³                                                      (1@15136)              ³
³                                                                             ³
³ Tips For Running WWIV Under OS/2 2.1.................Martin (1@6251) and    ³
³                                                      Lord Sigma2 (1@5498)   ³
³                                                                             ³
³ TechnOTES............................................WWIVnews Staff         ³
³                                                                             ³
³ The Power Mac: Panacea or Snake Oil?.................Omega Man (1@15117)    ³
³                                                                             ³
³ Type 0 Forum.........................................Edited by              ³
³                                                      Omega Man (1@5282)     ³
³                                                                             ³
³ A Net Sub Host's Best Friend - AutoSend..............JAFO (1@8861)          ³
³                                                                             ³
³ Posse Comitatus Activity On WWIVNet?.................Mr. Natural (1@8262)   ³
³                                                                             ³
³ Official WWIV Modification Services Listing..........Shadowspawn (1@3900)   ³
³                                                                             ³
³ Filo's Mod of the Month..............................Filo (1@2050)          ³
³                                                                             ³
³ Dateline: @#$*()#!...................................Omega Man (1@15117)    ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ


ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³               Random Factors                ³
               ³   Creative Commentary by Wayne Bell (1@1)   ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

WWIVCON
ÄÄÄÄÄÄÄ

Well, by the time you read this, WWIVcon has come and gone. I'll be there, and
next issue I'll have some comments on the event. Hope everyone who did attend
had a good time, though!


NET33 BUG REPORT
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Well, as you may know, there's a problem where if a system connects to the 
same node number in multiple networks, and neither has a password, the first
connect made will connect it to the wrong network, thus "crossing" the 
networks. While looking over the net code yet another time, I noticed that
I had a

        if (stricmp(net_networks[nn].name, name)) {

when I should have

        if (stricmp(net_networks[nn].name, name)==0) {

So, that is certainly what is causing the problem now (it will DEFINITELY pick
the wrong network). Until NET34 is released, therefore, don't add a new
CALLOUT.NET entry for the same node number in different networks at the same
time. Add one, get a PW, then add the other.


THE GREAT NETWORK SWITCHOVER
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

As most of you are aware, stage two of what's being called "The Great Network
Switchover" has taken place. This stage, the WWIVNet to WW4net system 
changeover, requires that everyone in WWIVNet run the CVTNODES program I sent
out UU'd in the related mail-to-all-sysops. This program will convert your
node assignments for subs and hosts from WWIVNet to WW4Net assignments, thus
saving you a bit of work.

In about two weeks, give or take a week, we'll look into moving onto the next
stage in the changeover, which will require that you delete the old WWIVNet
directory and rename the WW4Net directory to WWIVNet, and make the proper
changes in INIT. Don't do this yet, as the delay is to allow all E-Mail in
transit to reach its destination before we make the final change. I'll be
sending a mail-to-all-sysops when the time comes.


WWIV 4.24
ÄÄÄÄÄÄÄÄÄ

WWIV v4.24 is moving along smoothly in beta test, but isn't *quite* done yet.
The Fidonet support package appears to be working, but will probably be 
distributed in a separate distribution package. Should this occur, we'll 
probably see WWIV distributed in three separate packages - one for the basic
stock, stand-alone WWIV package, one for getting setup with WWIVNet, and a
third containing the Fidonet support executable. 

As it stands right now, this is what the v4.24 section of the README file for
the next release contains.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

  1) Swapping spawn implemented. (Code courtesy of TurboPower Software,
     distributed in .OBJ/.LIB format, with permission.)
  2) Sound Definition Files supported. (Uses local PC speaker to read/play
     alterable tunes.
  3) Various bug fixes as usual.
  4) Conferencing improved (confedit).
  5) N-Scanning dirs is now done automatically (if set in xfer defaults) only
     after the first n-scan - no more redundant file n-scans after msgbase
     n-scan.
  6) WWIV.INI file support added. See docs for available settings and details.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Short list, huh?

So far, there are really two new major features. The first is a 3rd-party 
"swapping spawn", which will allow the "shrink" functionality for any external
program (fsed, upload event, etc). Related to this, all the various spawn-type
functions (and people looking through the source know there are a bunch of 
hard-to-tell-apart functions for running external programs) have been 
consolidated into one function - extern_prog(), which will take a commandline,
and a series of flags OR'd together, which is much easier to code and 
decypher.

The second major feature is the support for a WWIV.INI file. This will allow
you to specify many parameters (some new, some from INIT, and some that used
to be OPT_ #defines) in a text file, and even to change the settings while 
the BBS is running (by modifying the WWIV.INI file, then saying //READINI). 
You'll be able to specify all the various flags (whether to shrink or not, 
intercept COMIO, etc) for each external run (fsed, upload event, etc), change
newuser colors, sysop-side colors, external programs (ul event, beginday 
event, newuser event, logon event, terminal prog, etc), simple ASV settings, 
and many flags (enable simple ASV, new chatsound, enable /s & /z, use fsed 
for ext desc, local sysop, 2way chat, close xfer, new extract, fast search, 
etc). These can even be set differently for different instances of the BBS, 
if you are running in a multi-instance environment.


INTERNAL QWK SUPPORT
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Of late there's been some debate on the various Sysops' subs over whether or
not an Internal QWK manager should be included in WWIV. As it stands right now,
I doubt there will be any QWK support built-in to v4.24, due to the timing. 
However, I'm not ruling this out for future versions.


WWIV.INI
ÄÄÄÄÄÄÄÄ

As most of you read last issue, WWIV v4.24 will have most of the OPT_ #defines
configurable through a .INI file. This file can be changed and reloaded while
the BBS is running, which will help those who rely on remote maintenance., 
The current settings file - called WWIV.INI - currently looks like this:

; -----------------------------------------------------------------------------
;
;                               WWIV Version 4
;                    Copyright (C) 1988-1994 by Wayne Bell
;
; -----------------------------------------------------------------------------
; Colors are selected numerically. To determine the value for a color, use the
; following chart:
;
;    0 = Black             8  = Dark Gray
;    1 = Blue              9  = Light Blue
;    2 = Green             10 = Light Green
;    3 = Cyan              11 = Light Cyan
;    4 = Red               12 = Light Red
;    5 = Magenta           13 = Light Magenta
;    6 = Brown             14 = Yellow
;    7 = Light Gray        15 = White
;
; Now, to calculate a color, you take the value for the background color and
; multiply by 16, then add it to the foreground color you wish. This will
; provide the value you should use for that color combination. Note that
: color values greater than 127 will result in blinking. In other words,
; you should probably restrict background colors to colors 0-7 above.
;
; An example: if you want to find the value for, say, bright yellow on magenta,
; it would be (5*16) + 15. This equates to (magenta * 16) + white.
;
; -----------------------------------------------------------------------------
;
; The various spawn options that may be used are:
;
; ABORT        Allows ^C to break the spawned program.
; INTERNAL     Makes extern appear as part of BBS
; NOHANGUP     Doesn't check for hangup
; COMIO        Use RETURN.EXE for WWIV's DOS intercept (takes about 50k more 
;              mem)
; SHRINK       Swaps out to XMS, EMS, or disk, to free more memory.
; FILES        Creates STAT.WWV and RETURN.WWV files.
; NOPAUSE      Turns off user's pause-on-screen.
; NETPROG      Tries to run program in network data dir first.
; TOPSCREEN    Redraws topscreen after execution.
;
; These options may be combined like:
;
; SPAWNOPTS[FSED]=SHRINK,COMIO,NOHANGUP
;
; Valid locations that can have spawn options specified are:
;
; TIMED, NEWUSER, BEGINDAY, LOGON, ULCHK, FSED, PROT_SINGLE, PROT_BATCH
;
; -----------------------------------------------------------------------------

[WWIV]
;
; Default spawn options
;
;SPAWNOPT[TIMED]        =SHRINK, FILES
;SPAWNOPT[NEWUSER]      =NONE
;SPAWNOPT[BEGINDAY]     =SHRINK
;SPAWNOPT[LOGON]        =COMIO
;SPAWNOPT[ULCHK]        =NOHUP, SHRINK
;SPAWNOPT[FSED]         =COMIO
;SPAWNOPT[PROT_SINGLE]  =NONE
;SPAWNOPT[PROT_BATCH]   =SHRINK, TOPSCREEN

;
; Newuser colors
;
;NUCOLOR[0]     = 7
;NUCOLOR[1]     = 11
;NUCOLOR[2]     = 14
;NUCOLOR[3]     = 5
;NUCOLOR[4]     = 31
;NUCOLOR[5]     = 2
;NUCOLOR[6]     = 12
;NUCOLOR[7]     = 9
;NUCOLOR[8]     = 6
;NUCOLOR[9]     = 3
;NUCOLORBW[0]   = 7
;NUCOLORBW[1]   = 15
;NUCOLORBW[2]   = 15
;NUCOLORBW[3]   = 15
;NUCOLORBW[4]   = 112
;NUCOLORBW[5]   = 15
;NUCOLORBW[6]   = 15
;NUCOLORBW[7]   = 7
;NUCOLORBW[8]   = 7
;NUCOLORBW[9]   = 7

;
; Sysop-side colors
;
;TOPCOLOR       = 31
;F1COLOR        = 31
;EDITLINECOLOR  = 112
;CHATSELCOLOR   = 95

;
; External program commandlines
;
;TERMINAL_CMD   =
;EXECUTE_CMD    =
;UPLOAD_CMD     =
;BEGINDAY_CMD   =
;NEWUSER_CMD    =
;LOGON_CMD      =

;
; System specification
;
;SYSTEMNAME     =
;SYSTEMPHONE    =
;SYSOPNAME      =

;
; System flags
;
;FORCE_FBACK            =
;CHECK_DUP_PHONES       =
;HANGUP_DUP_PHONES      =
;POSTTIME_COMPENS       =
;USE_SIMPLE_ASV         =
;SHOW_HIER              =
;IDZ_DESC               =
;SETLDATE               =
;NEW_CHATSOUND          =
;SLASH_SZ               =
;READ_CD_IDZ            =
;FSED_EXT_DESC          =
;FAST_TAG_RELIST        =
;MAIL_PROMPT            =
;SHOW_CITY_ST           =
;LOCAL_SYSOP            =
;2WAY_CHAT              =
;OFF_HOOK               =
;PRINTER                =
;LOG_DOWNLOADS          =
;CLOSE_XFER             =
;ALL_UL_TO_SYSOP        =
;NO_EASY_DL             =
;NEW_EXTRACT            =
;FAST_SEARCH            =

;
; ASV values
;
;SIMPLE_ASV[SL]         =
;SIMPLE_ASV[DSL]        =
;SIMPLE_ASV[EXEMPT]     =
;SIMPLE_ASV[AR]         =
;SIMPLE_ASV[DAR]        =
;SIMPLE_ASV[RESTRICT]   =

The only remaining OPT_ #defines are for chain_reg, msg_tag_ability, 
packscan_freq, registration, can_save_ssm, and extra_color.

As with .INI files for other programs, such as Windows, I expect that we'll
see third-party WWIV utils and mods start taking advantage of WWIV.INI to
provide a common file for user-configurable settings.


NET34
ÄÄÄÄÄ

NET34 should be released soon. Well, as many of you may know, NET34 has been
in beta-test for a while now. The two main new features are the new routing 
info lines, and support for net calls on multiple instances simultaneously 
- even on the same net!

Beta testing continues in earnest as of this writing. Hopefully, the last few
bugs have been caught by the beta testers - the last one being a problem with 
the DSZLOG with HSLink in multi-instance support, which was caught about in 
mid-June. This shows that keeping it in test for a while DOES help in the 
long run. Again, you will receive mail-to-all-sysops from me prior to its 
release.

As I said, routing information has been changed. The ^D0 lines, of course, 
have been edited for viewing:

0R: net33: @5282 (via @1041) [01:54 04/26/94]
0R 34 04/25 23:16 WWIVnet ->1041
0R 34 04/25 15:32 WWIVnet ->1021
0R: net33: @1040 (via @2050) [15:45 04/24/94]
0R 34 04/24 13:42 WWIVnet ->2050
0R 34 04/24 13:41 WWIVnet 1040->2050
0R: net33: @1040 (via @1) [13:21 04/24/94]
0R 34 04/24 20:03 WWIVnet ->1


You'll notice that, in addition to fields being moved around, the two main 
changes are that it's shorter, and that the network name is listed. In 
addition, the fields are in an order such that most fields will line up nicely
 - when everyone is using NET34+, of course -  rather than the current format
with staggered lines. This will make it easier to visually see the route 
taken by a post, and will assist in debugging any network routing problems.

With NET34, net calls can be initiated and received on multiple instances at
the same time. While it wouldn't be very useful, it will even handle two nodes
calling each other on the same net at the same time, without screwing anything
up. This involves some increasingly-funny-looking names - you end up sending
files like p1-0-2.001 - and NETWORK1 runs even if you don't receive any data
so as to update the logs correctly. But it all seems to work out in the end. 

Additionally, due to a request by Jim Nunn of IceNET, NET34 supports receiving
files sent by the NC, into the network data dir. I have been very careful in
the NETWORK2 code support for this, so that it will only accept certain files
for receipt. Only .NET or .ZIP files will be allowed for receipt, which means
that no network files or standard DOS devices can be overwritten. Upon receipt,
a NETDAT0.LOG entry is written, and an SSM to the #1 account is sent.

Additionally, I've updated NETUP to send out files, splitting it up into 
multiple 32k packets as necessary.

If anyone has any concerns about potential security problems with the file
transmission, I'd like to hear about them. I am pretty sure I've caught all 
the potential problems, but due to the importance of this feature I'd like
to make sure that all bases are covered.


BACKWARDS COMPATIBILITY
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

I'd also like to make a comment about net software compatibility: As I'm VERY
paranoid about backward compatibility, I am almost certain that NET34 today 
is compatible with the very first WWIV version that supported WWIVnet. This,
of course, is assuming that you're using a <64k bbsdata.net file. Additionally,
WWIV v4.24 will almost certainly work with almost all previous net versions 
after NET10, assuming again, that you're using a <64k bbsdata.net file, and 
aren't using groups for net versions that don't support that file size.


NOTES ON NETUP
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

For those using NETUP, I've written new versions of EN1 and DE1. These new 
EN/DE files support compression, but only when it actually compresses, as 
opposed to the existing WWIVNet DE1.EXE, which always uses compression. Other
than the compression, however, the data is not encrypted in any way at all. 
Instead, the verification involves RSA signatures using MD5 digests. Yes, 
I am paying a royalty for use of this code, and yes, it has been approved for 
export from the US. Since it involves only digital signatures, and not any 
encryption at all, this does not constitute a violation of any sort of legal
restrictions on the export of encryption technology.

According to an analysis by Dr. Ron Rivest (the "R" of RSA), the security
involved in the source verification should be sufficient to withstand attack 
by a major corporation for at least 25 years. In any case, I can easily 
generate new EN1/DE1 programs - I wrote a program specifically to do so - 
and so expect to implement new ones every few years anyway. 


WWIV 5.0?
ÄÄÄÄÄÄÄÄÄ

I hear some people are talking about WWIV v5.0. Well, don't bother, one is 
not being worked on. If there ever does happen to be one (don't hold your 
breath), it will probably have a higher registration fee, but currently 
registered WWIV v4 sysops will be credited the $50 or $80 toward the v5.0, 
if they wanted to upgrade. But, again, as I said, I am currently not even 
planning on writing a v5.0, much less started doing anything on one.


WHAT'S IN A NAME?
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

There have been some people recently trying to claim some kind of legal
protection for sub names. In the past, someone has even tried to
require another BBS to change a BBS name that they felt was too close to
theirs. Remember: WWIVnet does not have any rules on sub or BBS names,
other than that they not be clearly obscene. So, if you or someone else
want to try to claim legal ownership of something like that, do not
expect me or anyone else to force someone to change their BBS/sub name.


RANDOM WAYNE TRIVIA
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

On a lighter note, some of you have been wondering what sort of processor ol'
Wayne does his WWIV R&D work on. Currently, this is done on a 386/20. Using 
the new EN1.EXE for WW4Net, it takes about 15 minutes to do a full network 
routing update. Naturally, I expect to replace the computer in the next 4 to 
6 months to a 586/66 or so. 

That's it for this month. In the meantime, if anyone knows of some good, 
reliable deals on a system...:-)

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³                Soft Servings                ³
               ³       News from WWIV Software Services      ³
               ³           By Filo (WWIVnet 1@2050)          ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

WWIVCON
ÄÄÄÄÄÄÄ

WWIVcon '94 opens in New Orleans on July 1, 1994. The three-day convention 
features panel discussions which should be of interest to those in attendance,
software "door prizes" including the pre-release of a new WSS utility to be 
distributed with v4.24 when it is released, and lots of "free" time for those 
who want to explore the New Orleans area. Representatives from most of the 
major WWIV-Based networks will be in attendance along with many members of 
the 4.24 Beta Test Team.

Topics that will be discussed by panels (with audience participation invited
in the question and answer sessions) include: 

 - "BBSes and the Law" 
 - "Networking with WWIV"
 - "v4.24--New Features and Bug Fixes"
 - "WWIV -- Past, Present and Future."  
 
During the Sunday morning session there will be discussion of topics including
suggestions regarding future developments in WWIV and possible sites for 
WWIVcon '95.

Wayne Bell plans to attend and upon request is bringing "the gold pen" and a 
version of WWIV to autograph. The "gold pen" writes in a gold color and is 
suitable for autographing both 3.5 inch diskettes as well as 5.25 inch
diskettes. Those who attended the WWIV Bash in St. Louis in 1992 may remember
it. Let's hope it has not dried out since then :-)

Other attending dignitaries include Linwood Davis, the WWIVLink Ombudsman, Jim
Nunn, IceNET's 1@1, and JAFO, well-known modder and utility author. The
WWIVNews Editor, Omega Man, was scheduled to attend, but could not do so due
to some last-minute personal obligations involving several 66Mhz Pentium
systems. As he'll no doubt remind us, all those who attend WWIVCon are urged
to contribute eyewitness reports of the event for publication in WWIVNews.


WWIV v4.24
ÄÄÄÄÄÄÄÄÄÄ

Beta testing of v4.24 is coming along quite nicely in both DOS and OS/2 
versions. The most troublesome bug that we are trying to squash is one that 
shows up occasionally and not on all systems and that locks the board up. 
Once that is solved and once the FidoNet interface has been tested by more 
people on the Beta team, then we should have a release.

From a purely strategic point of view, it would be good to have completed the 
network change over (being done to accommodate those area codes without zeros 
or ones as middle digits) prior to having people work with a new version of
WWIV.


WWIVNET - WW4NET SUB CONVERSION
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

As most of you on WWIVnet are aware, the Sub conversion will take place on the
25th of June. At this time most traffic flow should move from WWIVnet to 
WW4net. Anyone on WWIVnet who has not obtained a WW4net node number and the
software to utilize that network must contact their GC ASAP in order to get 
on the "new" network.

The renumbering has raised quite a few questions among many of you, and 
considering the scope of this effort this isn't a surprise at all. For those
still unsure as to why we went through this process, and why we did so in the
way we did, here's the official explanation:

We renumbered the nodes in WWIVNet because the telephone system in this great
country of ours has finally outgrown the number of area codes available under
its old numbering plans. The old numbering plans called for each area code to
have a zero or a one as a middle digit. WWIVnet had capitalized upon this and
created a logical system of node numbering that allowed a person to tell which
area code a board was in, and which allowed for 250-300 nodes per area code,
depending upon the 1st and third digit of that area code.

Our old numbering system would simply not work with the new one proposed by
the telephone companies. For example, if 626 were to be a new area code, we
could not incorporate it easily. Thus, almost -two- years ago, we began 
discussions regarding how to change the node numbering. Wayne requested that
any plan continue to use unsigned integers in order to:

    (a) maintain as much backwards compatibility as possible.
    (b) avoid having to rewrite massive parts of the network and bbs software
        programs.

So, now we knew what we -had- to do, the question then put forth was -how- to
get the job done. Many excellent proposals were put forth by network sysops,
and each proposal was considered carefully. The proposal which was finally 
decided upon, and put into effect, went basically like this:

    (1) Node numbers will be either 4 digits or 5 digits in length depending
        upon whether the group number is 1 or 2 digits. Each group will start
        with the group number and be followed by node designations ranging
        from 000-999. Thus each group can have 999 nodes in it. If a group
        expands beyond that size, the group will be split into two or more
        groups.

    (2) GC's were responsible for renumbering their groups. They were allowed
        to either do it all themselves or enlist the aid of ACs. In the 
        renumbering, the GCs were encouraged to reserve "blocks" of numbers
        for various area codes and the block should allow the area code some
        room for growth (see related Q & A section later in this article). 
        Wayne also asked that numbers 001-019 be reserved for Net Servers
        within each group. 
        
        So, for example, these procedures would result in:

           GROUP 4
             4000 ................Reserved for GC
             4001-4019............Reserved for Servers
             4020-4049............Reserved for Area Code xxx
             4050-4149............Reserved for Area Code yyy
             etc

           GROUP 15
             15000................Reserved for GC
             15001-15019..........Reserved for Servers
             15020-15099..........Reserved for Area Code zzz
             etc

         Note the treatment of 4 digit groups as in Group 4 and the treatment
         of 5 digit groups as within Group 15.

    (3) As WWIV spreads throughout the world, the outline is to have node
        numbers reserved for certain areas of the world. Currently there are
        not enough boards in most of them to justify creating a different 
        group, but when the number of boards increase in those areas then
        such groups will be created. The basic plan (unless Wayne decides to
        change it) will look like this:

           Nodes           Area
           1000-19999      USA
           20000-29999     Rest of North & South American
           30000-39999     Europe
           40000-49999     Asia and Africa
           50000-64999     Held in reserve

    (4) Charter net members (1-25) will maintain the chartered status and 
        their node numbers will not reflect their group assignment.

Now that we had a renumbering formula, the method for implementation had to 
be developed. What resulted was what we're now using, which was a parallel 
network called WW4NET. This temporary network will work on the reassigned 
numbers, and will connect in the same manner as our current network. Thus, 
everyone would run two networks for a short period of time, and once the
connections are successfully established, the process of resubscribing to subs
will take place. Once a sub has been converted over to the new network, it can
be killed on the old network. After a point, the old network can be deleted 
and the new network renamed to the old network name of WWIVnet.

Of course, to facilitate the conversion process, the CVTNODES program was
developed, which went through your *.NET files and changed all the nodes
in your distribution lists for you.

A word of advice on naming subs during and after the renumbering. Once the 
network renumbering starts, people will be asked not to do the following:
 
    (a) Create new subs until it is finished.
    (b) Create new subs using numbers as SubTypes. 
    
If a person has subtypes that are using numbers, it is NOT necessary that they
be changed. Persons using numbers as subtypes may continue to do so but they 
must not change the number. If the subtype number is changed, it MUST be 
changed to an alpha non-numeric type.

With alpha type subs, it is recommended that subtype names not be more than 6
characters in length. The reason for this is that when SAsubnam is used, the 
network software will only look at the first 6 letters; thus each sub must be
unique in the first 6 letters or the network software will send auto-responses
to subscribers as the first SA file encountered where the six letters are the 
same. For example, if subtypes MODNETA and MODNETB were created, when the SA 
response was sent it would sent the first SAMODNET file it found. 

If people want to use ALPHA types and combine numbers, that is permissible.
For example, Node 15999 might have 15999A, 15999B, ..., 15999Z which would 
allow hosting of 26 subs and make them identifiable with that particular 
board. Alternatively, A15999, B15999, ...,Z15999 would also be acceptable.

Another safety tip, of course, is that if a person is using a name subtype
such as MODNET, the person should first search the SUBS.* files to be sure
that the name is not in use.

Finally, on the issue of compatibility with older versions of WWIV and 
WWIVNet, if anyone is using a version of WWIV that is 4.21A or earlier, they
will be limited to taking only numeric type subs unless they upgrade to a 
newer version or significantly modify their earlier version of WWIV. As
you know, the older versions of WWIV will not handle Alpha subtypes.

NEW PRODUCTS FOR WSS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Along with v4.24, a new products list for WWIV Software Services will be 
released. This list will include software utilities and games that have been
obtained by WSS for distribution. All of the Middle Earth product line will 
be included along with WSSFDI (which is my FrontDoor installer program 
rewritten to work with v4.24 of WWIV and with the version of WWIVgate which 
WSS bought from Kevin Carpenter).


PLANET CONNECT
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Negotiations are still taking place to have WWIVnet put on Planet Connect,
the satellite computer network transmission service. The last word from Boyd
Goodin was that it looked quite favorable. The advantage to WWIV is two-fold,
as Planet Connect will provide the following:

    (a) A reduction in the cost of networking significantly for those boards
        who want to set up to receive the transmissions from the satellite.
    
    (b) An increase in the awareness of WWIVnet, permitting those who choose
        to run WWIV to setup to receive our network in addition to the others
        that they receive.

As this is a major step forward for WWIV networking, we'll keep you posted
on developments as they happen.


FIDONET COMPATIBILITY STATUS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Finally, quite a few of you are wondering what's up with the work on making
WWIV more compatible with Fidonet. To be totally honest, at the moment, no 
one knows whether or not v4.24 will have Fido support integrated into it.

Let me summarize the current status:

    (1) WWIV Software Services purchased the code to the WWIVgate program
        (translator program that translates FidoNet headers into WWIVNet
        compatible headers and vice versa). This code has been updated to 
        allow for more subs than the 2.0 beta release of WWIVgate, and to 
        operate without requiring a registration number. The "register" nag
        has been removed.
        
    (2) The 4.24 software has various "Fido Hooks".

    (3) The INIT has a Fido Option.

    (4) The installation program to modify the WWIV.INI file for use with the
        FidoNet/WWIV software has been written.
        
    (5) Ken Carpenter and myself have been testing the new executable -
        WFIDOIN and WFIDOOUT - for some time with reasonable success.

The next step, I think is to release the FINST (Fido Install in WWIV.INI) and
the WFIDOIN / WFIDOOUT programs to the BETA team (or those who want to try it)
to see how it works.

Before the official release, we should have a utility based on my FrontDoor
Installer program that will be available for those sysops who do not have the
time or inclination to mess with all the support files required for a FidoNet
board but who still want to be on FidoNet.

So, I am hopeful that Fido Support will be part of the 4.24 release, but some
additional testing is necessary first before it can be a part.

That's it for this issue. See you all at WWIVCon!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³     Listing of WWIV Utilities for V4.23     ³
               ³            Joe Barbara (1@6101)             ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

How to Read the list:
 
 FILENAME.EXT  ID  MM/YR  Description of file goes here.
   by: Author Name        More description. Registration fee if any.

  ID = PD, SW, CM for Public Domain, Shareware, Commercial respectively.
  MM/YR is Month/Year added or updated

  Most all these programs should be available at any support BBS. Refer to 
  the support BBS list for one closest to you.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

 DFRAG2xx.ZIP  SW   1/94  Message base/EMAIL.DAT defragging program. Also 
   by: Spackle            repairs files/messages. $15 registration.

 PAGEME2A.ZIP  PD   1/94  Small but GOOD Super Chat Pager for WWIV. Can set 
   by: Jason Johnson      high and low times, custom registration available.

 WCHT3xxx.ZIP  SW   5/94  Replacement Chatroom for inter-instance chat. 
   by: Joe Barbara        Lots of new features. TRY IT! $20 registration.

 FSPFDI  .ZIP  CM   1/94  Front Door Installer program. Everything
   by: Filo               needed for FidoNet/WWIV. $25

 NETL285 .ZIP  SW   1/94  WWIV Network Analysis Program (single/multinet)
   by: Aldur              Unknown Fee.

 ALIASxxx.ZIP  PD   1/94  Alias - Converts the real name to handle in
   by: Cris McRae         CHAIN.TXT.

 AUTOSxxx.ZIP  SW   3/94  AutoSend - A Full-Featured Network Sub Host Utility.
   by: Cris McRae         Too many features to list. $15 reg.

 BDAYxxx .ZIP  SW   2/94  Birthday - A Birthday List Generator and Logon Event
   by: Cris McRae         Viewer. $5 reg.

 ECLWxxxx.ZIP  SW   2/94  Eclipse is a full featured offline mail reader
   by: Will Hobday        designed specfically for WWIV/WOMR. $20 reg.

 WLxx    .ZIP  SW   2/94  WWIVList is a viewer for text files with embedded
   by: Will Hobday        WWIV color codes. Free!

 WOMRxxxx.ZIP  SW   2/94  WOMR is an easy to install, easy to use mail door 
   by: Will Hobday        for WWIV. $30 for WOMR and WOMR-QWK!

 WQWKxxxx.ZIP  SW   2/94  WOMR-QWK is an easy to install, easy to use QWK mail
   By: Will Hobday        door for WWIV. $30 for WOMR-QWK and WOMR!

 WWIVESEx.ZIP  SW   1/94  External String Editor For WWIV v4.22 and Higher.
   by: Martin Bourdages   Very easy to use, import/export. Unknown Fee.

 NETCOM21.ZIP  PD   1/94  Network Utility - Updating over networks. 
   by: Perry Navarro      Current version v2.1
 
 ELN2x.ZIP     SW   4/94  Network packet editor - like LNET with GUI+mouse,
   by: Starship Trooper   header edit, extract, reroute, delete... $15 reg.

 PMELLNET.ZIP  SW   4/94  ELLNET net packet editor for OS/2 Pres. Manager
   by: Starship Trooper   Slick GUI, internal multitasking.  $15 reg.

 NSTATxx.ZIP   SW   4/94  Automatically log all net traffic thru your system.
   by: Starship Trooper   Create reports of how much systems send/recv. $10

 STRIPIT2.ZIP  SW   4/94  Net preprocessor to remove ansi & taglines, and
   by: Starship Trooper   delete incoming msgs from "fools". $5 reg.

 STRCOM11.ZIP  PD   4/94  Small and fast WWIV stringfile compiler/decompiler.
   by: Starship Trooper   Edit string files as text with any ASCII editor.

 WNETD.ZIP     PD   4/94  Front end for network mail handling programs.
   by: Starship Trooper   Free.

 KLINTxx.ZIP   PD   4/94  Klintonov, displays random Clinton bashing tags,
   by: Bull Ship          supports WWIV color, used normally as a logon event

 LINKUPVx.ZIP  SW   4/94  LinkUp - Network Update Software, nice interface, 
   by:  Jason Whelan      with mouse support. registration fee of ONLY 15!

 NETPROVx.ZIP  SW   4/94  NetPro - NETWORK2 preproc. Has many NICE features,
   by:  Jason Whelan      E-mail 1@5213(4205)WWIVnet! Only $10!

 WHELNETx.ZIP  SW   4/94  WhelNet - LNET replacement, NICE interface, new
   by:  Jason Whelan      LNET options E-Mail 1@5213(4205)!

 WWIVVGAx.ZIP  SW   4/94  WWIVVGA - Allows VGA Planets games to be played
   by: Jason Whelan       in WWIV networks, E-Mail 1@5213(4205)WWIVnet!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Attention Writers of WWIV Utilities

Please send any submissions in the above format to 1@6101 to be added to the
list. When a new version of WWIV is released all info must be updated as
this list will only contain utilities that are compatible with the 
current version.


 FILENAME.EXT  ID         Description
   by: Author             Description line 2
 ^     ^       ^          ^
 :     :       :          :.. Description MUST not be longer than
 :     :       :               102 characters including spaces.
 :     :       :               If it is available at a fee then the
 :     :       :               fee must be included in the
 :     :       :               description.
 :     :       :
 :     :       :............. Use PD, SW, or CM as ID to
 :     :                       indicate Public Domain, ShareWare
 :     :                       or Commercial.
 :     :
 :     :..................... Self Explanatory
 :
 :........................... Filename and Ext


Please send this information to 1@6101 WWIVnet (or 4230 WW4net).

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³          The "Helms Hoax" Exposed!          ³
               ³             by Polekat (1@7385)             ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

[Editor's NOTE: Some weeks back, someone posted a "press release" on the
Internet - including several dozen Usenet newsgroups - that claimed to have
been issued by the Electronic Frontier Foundation. While this isn't the first
time some clown has posted falsified press releases on what's being called
the "Information Superhighway", this particular one has caused quite a stir
among BBS sysops and users alike for obvious reasons. 

Polekat, the EFF's loudest voice on the WWIV networks - even louder than
Blade X, I'm told - as passed this official disclaimer on to WWIVNews in hopes
of helping suppress the panic and agitation that this hoaxer has caused not 
only among the national BBS community, but within the offices of one rather
renowned Senator by the name of Jesse Helms. 

The original author of this disclaimer was Mike "Johnny Mnemonic" Godwin, 
who in addition to being one of the EFF's chief legal wizards, was once one
of Central Texas' more renown BBSers, the last effective editor the infamous
college newspaper _The Daily Texan_ will ever have, and a difficult man to 
debate against when drunk!

Those wishing to reach Mike for more information on this hoax, as well as
the EFF, can do so through the internet at mnemonic@eff.org.]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

At EFF, we have been receiving a number of queries about an alleged EFF
"press release" or "statement" announcing the following:

"Senator Jess Helms (R-NC) requested that the FBI become more involved in
the fight to stop adult images from being distributed on electronic
bulletin boards and the Internet."

Typically, the "press release" has included the following:

: "The EFF has issued a warning to sysops that the following files
: which depict any of the following acts are illegal in all 50
: states, and can subject the sysop to prosecution regardless of
: whether the sysop knows about the files or not.
:
: "--Depiction of actual sex acts in progress"
:
: "--Depiction of an erect penis"


                      *There is no such press release.*

                        *The press release is a hoax.*


Several people seem to have been fooled by the false press release, including 
the new publication SYSOP NEWS, which reprinted it uncritically in its first 
issue.

I urge you to spread this announcement to every BBS of which you a member.

Thank you for helping us stop the unethical people who spread this
misinformation.

--Mike

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³              Seeking Asylum!                ³
               ³     An Inside Look at The Asylum Group      ³
               ³   by Zu Digital (1@7321) and Sam (1@2077)   ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ
         
[Editor's NOTE: Since all the hoopla over the release of the Asylum/QWK, and
the subsequent flame debate over whether it should be included in stock WWIV
or not, quite a few of you readers have been asking just *who* the Asylum
Group. There's been a lot of talk and speculation over their identities, and
some have been calling the Asylum Group just another of those 'vapor-groups'
that have sprung up on the WWIV networks from time to time.
To hopefully shed some light on the truths about the Asylum group, the two
founders - Zu Digital and Sam - AKA the infamous "Super American Man" - 
have submitted the following dossier on just who this group is, how they
came to be, and where they're going if the anti-QWK modders don't send
them someplace worse first!

The one doing most of the first person descriptions is Zu Digital. Sam's
the one proving he can take dictation just as well as any secretary!]


"COMMON" ORIGINS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

I suppose it all really began with the COMMON mod. COMMON was conceived to be 
a set of functions to make WWIV just a little more visually pleasing. My idea
of the COMMON series started before COMMON was even thought of being created.
I just didn't realize it yet. With the creation of the Pulldown Menus, about 
1 year before COMMON ever came out, I had sure plans of making an interface 
that, number one, used the arrow keys to navigate, and two, just looked better
than the old 'tty' interface you've grown to learn and love.

In all actuality, COMMON was not my 2nd generation of arrow-key modifications.
After the Pulldown Menus were first built - for internal use only - I went to 
the NTC (for the Army) in California for 30 days. While on guard duty, I 
planned what would be built, and dubbed it "EMS", which was short for the 
"Evolution Menu System'. The EMS was not to be judged by today's current menu
interfaces for regular DOS applications, but against BBS programs. It evolved
from the tty interface, to my Pulldown Menus, to the EMS library which was
written in C++.

After this, I decided to start releasing my modifications. But I knew that 
another set of functions would be required to do such, written in standard C,
as WWIV will not compile in C++ mode.

Needless to say, COMMON now exists because of that reason.


PULLDOWN MENUS - THE ACTUAL BIRTH OF ASYLUM
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

With my first major mod, the Pulldown menus, I saw what happens to a fairly
good mod when I don't play by a certain set of rules.

I had a completed mod, one that I knew was good, but where do I go from here?
How is someone supposed to know what your mod will do for them, and how do 
they know that they 'need' to install your mod.

To compound matters, while my mod was completed for my own use, I made the 
menus all hard coded, didn't do proper bug testing, and ended up posting it, 
completely, about 4 times on Modnet in hopes of getting some additional beta
testing done. I knew this was not the best way to go about things, but I 
wasn't really sure about exactly *what* it was that I needed to do.

Then, through a twist of fate, I found Sam. He posted something about the
pulldown menus, and I called his board to see them somewhere besides my board.
Shortly after that, Asylum was born.

My original plan for Asylum was to have a number of fictitious members, along
with myself and Sam, to make us look like an good-sized, organized group.
I felt that people would take a "group's" word, over a single person saying
"Use this mod! It's cool, and you need it". And with the size of the mods I
planned on releasing, I figured I could pass it off.

Well, the group name stuck, but we never did get around to adding all the
fictitious members, instead we added quite a number of real people that wanted
to be apart of something real. Theses are very brave sysops, our Beta Testers,
have helped us to release a stable product, one that won't get killed right
after it is released from massive BBS breakdown/crashes etc...

Sam helped me with everything from getting into the network, (that experience
will be in another article), to registering WWIV, to getting my mod introduced.
We re-wrote the pulldown menus and tried again, learning as we went, but using
a little more common sense in the process. Sam was an up-and-coming C
programmer himself at the time, and was learning, literally, by the seat of
his pants.

We then saw a little more success with the second version, especially after I
made the menus more easily-configurable with the PullDown Menu Compiler, eased
up on the STACK, removed quite a bit of D-group hogging, and a LOT of bug
fixes.

Even though I found that PullDown menus maybe aren't the best menu interface
for a bulletin board, I did not give up with my ideas of making the interface
of other aspects of a WWIV BBS a little more fun, and a LOT easier.

We found the main problem with our Pulldown Menu System was that sysops know
how to use WWIV, and do not need to use menus (myself and Sam included). Of
those that *did* put it in, they reported their new callers simply loved it,
and loved the ease at which they were able to navigate through the menus. Of
course, callers using Expert status would never know they were there.


COMMON POINTS OF REFERENCE
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Current COMMON mods that exist are the User Pulldown Menus, ListPlus, Super
Config and QWK. There are a few other mods that require functions in COMMON,
but they are nowhere as complex as what we like to bill as "Asylum", rather,
modifications that grew out of necessity. TRYTOUL (Try To Upload) for example,
which allows you to upload files without entering a filename or description in
advance.


THE MAKING OF COMMON
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The first stage of a COMMON mod, if it is to become good enough to be called
Asylum, is to come up with an idea that needs to be implemented, followed by
an extensive design process. Believe it or not, the design phase is the most
tedious and time-consuming portion of writing an Asylum Modification. I rarely
jump right into a huge mod and just start coding. It may be in my mind for a
month before I do anything, while I ponder over various ways to start to write
this in text mode, followed by pseudo-code, then finally, C code. This is true
of the Pulldown Menus, ListPlus (which had a design life of something like 2
months) and QWK.

Inspiration comes at weird times. Sometimes at work when I have a few minutes,
I will jot down on paper some design criterion and places I would like to go
with the mod, and decide what areas I am going to ignore for the time being.
Believe it or not, a lot of ideas come to me in the last place you would think
they would...the shower, in a chat with one of my callers, at work, and of
course, in conversation with Sam on the phone.

Eventually, I manage to come up with a pretty rough idea how it will work.

Once the program has enough features added that I think others would like to
try it out, I go ahead and have Sam try it out. If it can make it through HIS
complex set up, it can make it through about anything.

Inevitably, Sam sends in some bug reports, along with a HUGE amount of added-
feature requests.

Sam and I finally work out things and decide it is time to let our collection
of BRAVE beta testers give it a try. Again, in come a few bug reports and
more added-feature requests.

The months pass on, the mod we are working on grows into crazy proportions,
and finally Sam and I decide, what the heck, let's release it on the net.

Need I say what happens?  MORE bug reports, even after 6+ months of extensive
beta-testing by the greatest team of beta testers ever assembled, save that of
Wayne's beta-testing team. QWK recently had a dandy of a bug that went 
completely undetected in the initial six months of testing, only to be found 
the very next day after it was released on Modnet by a -very- observant Dave 
Wallace and Emerald Lady. Needless to say, they are now members of our beta
testing team.

Within days, we actually have a working error-free version.


LISTPLUS
ÄÄÄÄÄÄÄÄ

I was resting on the laurels of my Pulldown Menus and we were feeling rather
proud of ourselves. Then one day, I called a local Vision/2 bbs. It was
simply awesome, and put what I felt was my greatest (at the time) achievement,
my Pulldown Menus, to complete shame.

I decided I HAD to write something of that quality for myself... and for WWIV.

So in a 6 hour long-distance phonecall between me and Sam, a new concept was
born that was destined to revolutionize WWIV's transfer section-  Listplus.
Public Relations was going to be critical if this was going to work. At the
time, there were a number of file-tagging mods available. Frank Reid's was
(possibly) the most popular. By this time, most all sysops that wanted file
tagging had already installed one of the existing taggers, and didn't feel
like digging it out just to install a new one that 'claimed' to be
better...especially buy a couple of guys that called themselves "Asylum"...

Sam posted numerous plugs about my new file-tagging mod. He showed it to
every sysop that called his board. That met with a lukewarm reception.
Something more was needed.

I remember a post about a sysop who lost his back up and started over, he
looked for the same file tagger he had before, but couldn't find it... luckily
our tagger was still on his sub and he put it in. The sysop posted a very
nice comment, something along the lines of not being able to stay in his chair
when he ran it, not believing what he saw (Gee, the same feeling I got when
I saw the Vision/2 file listing).

That, combined with a few other posts from people who took a chance and tried
it, (and more plugs by Sam), Listplus went from being "just another file
tagger" to a network-wide craze. EVERYONE, it seemed, was going ga-ga over
Listplus. People were calling and e-mailing from everywhere wanting it, and
anything and everything else from Asylum.

Asylum-mania had begun.

As time went on, Listplus went from a fairly 'rigid' mod, without any
configurations or extras, other than the arrow key tagging, to a mod that
supported extended descriptions, the most complete search/finding routines I
have seen on ANY BBS, user configurable file listing, and finally, plenty of
sysop configuration options, being able to set the color while in the BBS for
most any item, as well as being able to toggle most features on and off.

I also had the good luck of 4.23 coming out. Good luck because I was able to
test it on all 4.22 users, and had a *legitimate* reason of posting all the
fixes that had been done to it... labeled the '4.23 version of List Files
Plus' in it's entirety on Modnet.

By this time, I came up with my own ideas of making my mods a little more
popular as well as having my own confidence in my mods grow.


ASYLUM/QWK
ÄÄÄÄÄÄÄÄÄÄ

With the popularity of ListPlus, I felt we were about as high as we would get
in WWIV modding. Then, Sam went multi-line and found (as did many others) that
most (all we tried) QWK mail packet generators would not work (at that time)
with non-standard IRQ's.

Asylum to the rescue!

I started writing Asylum QWK around September of 1993, but lost interest. But
with Sam going multi-line/multi-node, I now had a legitimate reason to put a
concentrated effort into it's development. Armed with possibly the greatest
beta-testing team ever assembled, save Wayne's, we put Asylum QWK through a
vigorous six month test period. Finally, in May 94 it was released on Modnet.
As it turns out, the beta team caught all but two minor bugs and one major bug.
Not to bad for a mod of this proportion. Those bugs were all killed, and now
Asylum QWK is the fastest QWK packet generator (that we have found) for WWIV
on the market. It has many features not found in other similar products, such
as the ability to configure your Q-Scan from within QWK, your ability to set
how many (in numbers, not bytes) messages you would like to be able to down-
load from each sub, as well as the total packet, an option to allow you to take
a percentage of posts from each sub, and it is internal, so the same functions
that limits a users time for the BBS, are used in Asylum QWK.

But the best option of all... it is free. Please note, however, that we will
not refuse any donations sent our way :-)

The public response to Asylum QWK has gone off the meter. Those who have tried
it have absolutely fallen in love with it's speed, flexibility, versatility,
and reliability. And if I must say so myself, our product support has been
second to none. Sam and I both have gone so far as to call people voice at our
own expense to help them get things set up and running right. So far, no one
(to our knowledge) has been disappointed.

We have offered the code to Wayne and WWIV Software Services free of charge to
include in WWIV. There has been a lot of debate on this topic on the #1 Sysops
Sub, with the vast majority of sysops opting for it to be included as either a
#define option or as a WWIV.INI option. With the onset of v4.24 of WWIV and
it's virtually unlimited message-base capability (in numbers of posts you can
keep in each sub), some sort of QWK is going to be nearly mandatory. By in-
cluding a QWK package in WWIV, it offers a very useful option, and makes WWIV
more attractive to new sysops. By making a way to turn it off (by #define or
INI), you appease those few sysops who would rather not have it. And by mak-
ing it free, everyone can use and enjoy it without having to worry about send-
ing money to someone to stop shareware delays or gain added features.

We understand that other mail generators are available, but it is our opinion
that the generator should be apart of the package of WWIV, included in the
same $80 as WWIV itself.


SUPER CONFIG
ÄÄÄÄÄÄÄÄÄÄÄÄ

Super Config was released between Listplus and Asylum QWK. While it is a true
Asylum Mod, it doesn't have all the bells and whistles of the Pulldown Menus,
Listplus, or Asylum QWK. Still, no WWIV board should be without it. It is
a great addition to Asylum QWK. Basically, it allows you to set up your New-
Scan and File-Scan in true Asylum fashion, using your arrow keys and space-bar
to toggle on or off the subs you want to read, a page at a time. Super Config
is smart. It auto-detects if you are using conferencing, and adjusts itself
accordingly. Once you see it, you will not know how you ever lived without it
and your users will love you for using it.


MARKETING THE PRESENT
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Marketing opportunities have come in the strangest ways. After seeing all
that Sam had done to promote Asylum, I though he had covered just about 
every avenue available.

But as I saw, with a little luck, creativity, and a little opposition, Sam
could still make people not only stand up and take notice of Asylum, but he
was actually able to get them discussing it!  Sam unintentionally started a
product war on the #1 Sysops Sub, and because of that, the Asylum Group is 
now getting more attention than ever. I had sysops calling my board to find 
QWK who didn't even know anything about ListPlus, let alone COMMON. Through 
careful planning, inadvertent help from JAFO, a little luck, and the many 
people posting their opinions supportive of Asylum, I now find people not 
knowing about Asylum very few and far between.

With the popularity of Asylum QWK (it has already been downloaded over 150
times from Sam's BBS in just one week), and the fact that COMMON must be
installed to have QWK run, I find my previous mods now riding on the coat
tails of my newest mod. New users on my board (sysops in their own rite) that
didn't even know ListPlus, COMMON, Super Config, Pulldown Menus, and my few
non-COMMON mods existed are becoming institutionalized in Asylum themselves.


CHARTING THE FUTURE
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The future for Asylum (and WWIV) is very bright. Ideas we are kicking around
include modifications to the sublist and dirlist functions, G-Files, and
Defaults. Maybe something that will pop up, possibly a network optimizer that
will take huge packets from servers and optimize them into message data file,
taking out redundant posts, leaving text files for each system, so that the
distant node can rebuild these packets into the correct form that the network
software wants to see it in. Sam is currently writing a new voting section
done in Asylum fashion. We have gone about as far as we can go with Listplus;
QWK may have a little un-tapped potential in it, but it is time to move on. 
Any ideas people have are always considered, so if you are using one of these
and have an idea for a feature, be sure to let us know.

The motto we live by at Asylum is "Make 'em say "Wow!". Not only through the
flash and pizazz we put into every effort, but through product support as
well.

We strive in every modification we release to do just that.

Asylum! Say it like Sega!

Be sure to subscribe to the Asylum Support Sub. This sub seems to be more
active than Modnet and Mod Talk and Requests at times (at least it did after
Filo's HD crash :-)

  Subtype  @     Net
  ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
  ASYLUM   2077  WWIVNet
  ASYLUM   5497  ICENet
  ASYLUM   5497  WWIVLink
  ASYLUM   5497  TerraNet

To get the ABSOLUTE latest version of my Asylum's Current mods, call the
Asylum HQ, but be forewarned, alphas and betas are usually what the latest
mod is.

My BBS is single node, but I keep it free, not keeping alot of files online
that local users would want to download.

Sam's board is a very active board, but it has three nodes, so you should be
able to get on without to many problems.

Sam's BBS will have mods that are tested and complete.

                     Asylum HQ               Sam's BBS
                     @7321 WWIVNet           @2077 WWIVNet
                     703-427-1214            210-659-7267
                     210-659-3541
                     210-659-9157


"THE FOLLOWING MEN ARE ARMED AND CONSIDERED DANGEROUS:"
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Zu Digital aka Michael Deweese is a 24 year old Heating and Air Tech. Mike
lives in Virginia and has been active in WWIVNet in one shape or another for
well over a year. Hopes to move on to become a full-fledged programmer before
to long. (Anyone got any openings?)  Also, in case Wayne is wondering, Enigma,
(Michael Dorsey) is the one you need to give a commission to for getting me
into WWIV and eventually registering.

Sam aka Sam Morris is 31 years old, lives in San Antonio Texas, and is
the Logistics Coordinator for the US Air Force's "Tops In Blue" touring
entertainment extravaganza. Sam has been heavily involved in WWIV and WWIVNet
for nearly 3« years. He is a former Area Coordinator for North Dakota, and is
currently Filo's alternate Group Coordinator for Group 4.

Stephen Leprell, former member and name creator, now serving time... er,
serving our country. (I tried to talk him out of it, I feel me and Sam did
enough time for our country (Sam is still doing it). Probably over two decades
of military experience and service in our group between the three of us.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³           Filling in Gates' Gaps            ³
               ³  A Collection of Undocumented DOS Commands  ³
               ³       by MicroSource Sysop (1@15136)        ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

"DOS is great
 DOS is good
 Let us thank Bill
 For our...uh, wait, is that in the manual?"
 
Don't laugh too hard, because this is a sad but true fact. DOS may be one 
of the best operating systems on the market today, and it's arguably the
most widely used, but there are several undocumented commands and switches
that would be very useful if we only knew what they were!

Yep, it's true. There are "secret" commands in almost all versions of DOS. 
Unlike those found in quite a few Windows programs, these are -useful- 
commands, and it a sure sign of some serious incompetence on the part of
the technical writers for no less than -three- different DOS suppliers that 
the last few releases of DOS have several of these undocumented commands.

Over the years I've taken notes on these "secret" commands, and while it's
possible I missed a few, here's the most complete list I've got to date:

- Using ATTRIB to hide directories
- COMMAND /F
- COMMAND /P
- COMMAND /D
- COPY. A:
- DIR,
- DOS?=HIGH
- ECHO OFF and ECHO ON
- FDISK /MBR
- FDISK /STATUS
- FOR %%V IN (/SOMETHING)
- FORMAT /AUTOTEST
- FORMAT /BACKUP
- FORMAT /SELECT
- FORMAT /SELECT /U
- FORMAT /H
- IF EXIST <dirname>\NUL <command> and IF EXIST EMMXXXX0 <command>
- INSTALLHIGH
- REM in lines with pipes or redirection
- SHELL=C:\COMMAND.COM /P /F
- SWITCHES=/W
- TRUENAME
- VER /R
- Using : for comments in DOS batch file
- Delimiter characters

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Using ATTRIB to hide directories
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The DOS 5.0 and 6.0 ATTRIB command can do the same thing for directories as it
can for files:  ATTRIB +H <dirname>  will hide the named directory.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

SHELL=C:\COMMAND.COM /P /F
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
The /F in the CONFIG.SYS SHELL= statement forces a "Fail" response to all
"Abort, Retry, Fail" prompts issued by the DOS critical error handler.


COMMAND /F
ÄÄÄÄÄÄÄÄÄÄ

Entered on the command line, COMMAND /F makes all those annoying "Abort,
Retry, Ignore, Fail" disk error messages default to "Fail" from then on until
rebooting.


COMMAND /P
ÄÄÄÄÄÄÄÄÄÄ

For DOS 3.30 (not checked with other versions):  Docs say that this doesn't
allow you to exit back to the previous shell, but /P also forces AUTOEXEC.BAT
to be run on secondary shells.


COMMAND /D
ÄÄÄÄÄÄÄÄÄÄ

When used with a primary shell, or secondary with /P, prevents execution of
AUTOEXEC.BAT.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

COPY. A:
ÄÄÄÄÄÄÄÄ

The use of a period IMMEDIATELY after some DOS statements will work just like
*.*

     Examples:  DEL.     (erase all files in current directory)
                COPY. A:  (copy all files in current directory to A:)

There may be more statements with which it works.

This is actually a documented although obscure feature, though the ability to
use the period with COPY is not documented. What is documented is the fact
that "." and ".." can be used to represent the current and parent directories
respectively, and these will work with many applications which can handle
directory names as arguments. In this case the "." could also be viewed as a
replacement for "*.*"

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

DIR,
ÄÄÄÄ

Using a comma immediately after DIR shows ALL files, including the HIDDEN
ones.

This appears only to work with DOS 5.0 and 6.0. With 3.30, it doesn't display
either IO.SYS, MSDOS.SYS (both with S, H and R attribs) or a test file with A
and H attribs.

With DOS 5.0, it displayed a test file with H and A, but would not display
IO.SYS or MSDOS.SYS with S, H and R. This isn't surprising actually, since S
alone (without H) will prevent inclusion of a file in a normal DIR.

Not tested with DOS 4.x. Not supported by JP Software's 4DOS.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

DOS?=HIGH
ÄÄÄÄÄÄÄÄÄ

DOS?=HIGH in CONFIG.SYS with DOS 6.0 will prompt you whether to load the DOS
kernel high (into the HMA) or not.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

ECHO OFF and ECHO ON
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Entering ECHO OFF from the command line erases the prompt and leaves just a
cursor on the screen. ECHO ON from the command line restores the prompt. 
This works with all version of DOS.

One of the most frequently asked questions is "How do I ECHO a blank line in
a batch file?"  The most common answer is to use ECHO directly followed by a
period:  ECHO. like so. However, just about any "white space" character will
work, as well as any "delimiter". The following alternatives can be used: 
ECHO. ECHO"  ECHO,  ECHO:  ECHO;  ECHO[  ECHO]  etc. Apparently it's just
the way that the command handles the delimiter and has been available from way
back!  Microsoft just began mentioning it in the documentation recently,
though, and their examples use a period.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

FDISK /STATUS
ÄÄÄÄÄÄÄÄÄÄÄÄÄ

Prints a screen just like using option 4 of FDISK, "Partition information",
but includes extended partition information. Nice if you want to get an
overview without fear of pressing the wrong keys.

Doesn't work in DOS 3.30.


FDISK /MBR
ÄÄÄÄÄÄÄÄÄÄ

MS-DOS 5.0 FDISK has an undocumented parameter, /MBR, that causes it to write
the master boot record to the hard disk without altering the partition table
information. While this feature is not documented, it can be told to
customers on a need-to-know basis.

Warning:  Writing the master boot record to the hard disk in this manner can
make certain hard disks partitioned with SpeedStor unusable. It can also
cause problems for some dual-boot programs, or for disks with more than 4
partitions. Specific information is below.


What is the MBR, anyway?

At the end of the ROM BIOS bootstrap routine, the BIOS will read and execute
the first physical sector of the first floppy or hard drive on the system.
This first sector of the hard disk is called the master boot record, or
sometimes the partition table or master boot block. At the beginning of this
sector of the hard disk is a small program. At the end of this sector is where
the partition information, or partition table, is stored. This program uses
the partition information to determine which partition is bootable (usually
the first primary DOS partition) and attempts to boot from it.

This program is what is written to the disk by FDISK /MBR and is usually
called the master boot record. During normal operation, FDISK only writes
this program to the disk if there is no master boot record.


Why is the MBR changed during Setup?

During installation of Microsoft MS-DOS 5 Upgrade, Setup will replace the
master boot record on the hard disk with code to display the message:

        The MS-DOS 5.0 Setup was not completed.
        Insert the UNINSTALL #1 diskette in drive A.
        Press the ENTER key to continue.

This message should be erased and the master boot code rewritten before Setup
is completed. If a problem occurs during Setup and you return to the previous
MS-DOS, UNINSTAL should also remove this message. However, should Setup or
UNINSTAL fail to remove this message, or should the master boot record become
corrupted, a new master boot record can be written to the disk using the
following command:

         C:\>FDISK /MBR

     WARNINGS:

     This option should not be used if:

        - the disk was partitioned using Storage Dimensions'
          SpeedStor utility with its /Bootall option
        - more than 4 partitions exist
        - certain dual-boot programs are in use

Storage Dimensions' SpeedStor utility using the /Bootall option redefines the
drive's physical parameters (cylinder, head, sector). /BOOTALL stores
information on how the drive has been changed in an area of the master boot
record that MS-DOS does not use. FDISK /MBR will erase that information,
making the disk unusable.

Some older OEM versions of MS-DOS and some third-party partitioning utilities
can create more than 4 partitions. Additional partition information is
commonly stored information on partitions in an area that FDISK /MBR will
overwrite.

Some dual-boot programs have a special MBR that asks the user which operating
system they want on bootup. FDISK /MBR erases this program. Dual-boot
systems that boot whichever partition is marked Active are not affected by
FDISK /MBR.

If you have a Boot Sector Virus, just boot from a known "clean" floppy disk
that's write protected and which has FDISK on it, and run FDISK /MBR.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

FOR %%V IN (/SOMETHING)
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

How can a batch file (without 4DOS) determine from which drive it has been
started?

      Example:  C:\>A:TEST.BAT

Now my batch should be able to find out that it is located on drive A: (not
the path, only the drive!).

In a batch file, the variable %0 contains the name of the batch file as it was
typed at the command line. If you run the batch file as A:TEST.BAT, %0 will
be "A:TEST.BAT". If you have the directory on your path, and simply type
TEST, then %0 will be "TEST". The drive, path, and extension will only appear
in %0 if you enter them in the command used to call the batch file (either
typed at the command line, or called from another batch file). So, you must
specify the drive as part of the batch filename for this to work.

To extract the drive only from %0, use the undocumented FOR %%V in /SOMETHING
command:

     set drive=
     for %%v in (/%0) do call test2 %%v
     echo Calling drive is %drive%

...where TEST2.BAT is:

     if not '%drive%'=='' set drive=%1:

FOR %%V IN (/SOMETHING) DO WHATEVER will do WHATEVER twice -- the first time
with %%V set to the first character in SOMETHING ("S"), the second time with
all the remaining characters in SOMETHING ("OMETHING"). If SOMETHING is only
a single character, WHATEVER will only be called once, with that character in
%%V. If the single character is a wildcard (? or *) that wild card will not
be expanded to a set of filenames. (The main purpose of this feature is
apparently to allow inclusion of the literal characters "?" and "*" without
them being expanded.)

This works in DOS 3.30 and later.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

FORMAT /AUTOTEST
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The autotest parameter will allow FORMAT to proceed, checking the existing
format of the disk (unless the /U parameter with DOS 5 or 6 is also present),
and proceeding with the format.

All this will take place with no delay and no waiting for user input. It will
also end without pausing. It will not ask for a volume label or whether to
format another diskette.

WARNING!  This procedure will also work on hard drives!  Be very cautious if
you plan to use this feature!


FORMAT /BACKUP
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

This works exactly like /AUTOTEST, but it does ask for a volume label.


FORMAT /SELECT
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

This is like the DOS MIRROR command... For safety-fanatics only.


FORMAT /SELECT /U
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Just makes a disk unreadable. Guess it could be handy?


FORMAT /H
ÄÄÄÄÄÄÄÄÄ

In DOS 3.30 (not tested with other versions), FORMAT /H will cause the format
to begin immediately after pressing Y in response to "Format another", rather
than displaying "Place disk to be formatted in drive x: and press Enter" on a
second and subsequent disks.

In DOS 5.0, FORMAT reports "invalid switch".

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

IF EXIST <dirname>\NUL <command> and IF EXIST EMMXXXX0 <command>
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
This is a handy quirk of DOS. Installable drivers are seen as files in all
directories. You can use the if exist test to either test for the existence
of a directory, with "if exist <dirname>\nul", which fails if the directory
does not exist because the nul device is not found; or to test whether any
driver is loaded, such as the DOS 5 or 6 EMM386 memory manager.

Caveats:  For testing NUL, you need to know the name of the directory or the
driver whose existence you are testing, and this is MS-DOS specific -- it
doesn't work on network drives, and may not work under DR-DOS.

Where did you learn the "EMMXXXX0" name from?  Instead of typing MEM /C, type
MEM /D for the "debug" listing.

The only trouble is EXISTS returns true for COM3/4 and LPT2/3 even if the
hardware does not exist.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

INSTALLHIGH
ÄÄÄÄÄÄÄÄÄÄÄ

In DOS 6.0, there is an undocumented CONFIG.SYS command called INSTALLHIGH=
which works just like INSTALL= but loads the TSR high (into upper memory).

The only drawback to this is that MemMaker will not touch INSTALLHIGH lines
during the optimizing process. It just takes it as it is currently. But then
again, INSTALL= is ignored too. All in all, INSTALL and INSTALLHIGH really
are commands to set up manually by the user, and are not really recommended
for normal use. Load TSRs at the beginning of AUTOEXEC.BAT (and using
LOADHIGH if desired).

       Example:

       DOS=HIGH,UMB
       DEVICE=C:\DOS\HIMEM.SYS
       DEVICE=C:\DOS\EMM386.EXE NOEMS
       INSTALLHIGH=C:\DOS\SHARE.EXE

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

SWITCHES=/W
ÄÄÄÄÄÄÄÄÄÄÄ

Enables you to have the Windows 3.0 WINA20.386 file anywhere on your boot
drive. Without this you have to have it in the root directory.

This should not be used with Windows 3.1, since it appears to waste around
120 to 130K of UMBs, depending on your system configuration.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

TRUENAME
ÄÄÄÄÄÄÄÄ

Internal DOS 5.0 command. Canonicalize a filename or path (using DOS
interrupt 21h, function 60) prints the actual directory.

     Syntax:

     TRUENAME filename   - Prints the complete path to file.
     TRUENAME directory  - Prints the complete path to directory.

Note:  If the path is in a network, it starts with a \\machine-name.

TRUENAME is analogous to the UNIX "whence" command. It returns the real
fully-qualified path name for a command.

TRUENAME is useful in networks, where a physical drive may be mapped to a
logical volume, and the user needs to know the physical location of the file. 
It ignores the DOS SUBST and JOIN commands, or network MAPped drives.

TRUENAME is an undocumented MS-DOS feature, but it is documented in JP
Software's 4DOS software (COMMAND.COM replacement) as follows:
     Syntax:

     TRUENAME [d:][path]filename

     Purpose:

     Returns a fully qualified filename.

     Comments:

     TRUENAME will see "through" JOIN and SUBST commands, and
     requires MS-DOS 3.0 or above.

     Example:

     The following command uses TRUENAME to get the true pathname
     for a file:

     c:\>subst d: c:\util\test
     c:\>truename d:\test.exe

     c:\util\test\test.exe

TRUENAME : will reveal the full name drive and path of the filename. If you
specify a wildcard (*) in the filename, it will expand the filename to use
question marks instead. If the path includes the ..\ sequence, TRUENAME will
examine the directory structure and calculate the path.

Stranger still, the line:

     TRUENAME \CRONK\FLIBBET\..\ART

produces the response:

     C:\CRONK\ART
even if the directories \CRONK\FLIBBET and the file ART don't exist! Don't
expect this command to work well across networks. After all, this is still
undocumented in MS-DOS for a reason!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

VER /R
ÄÄÄÄÄÄ

Yields extended information about the DOS version:

     MS-DOS Version 5.00
     Revision A
     DOS is in HMA

Doesn't work with DOS 3.30. VER /R is a documented feature of JP Software's
4DOS.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Using : for batch file comments
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

DOS uses a leading : to indicate a label in a batch file. If the next
character following the : is a space or other non-alphanumeric character, then
DOS will decide it's an invalid label and skip to the next line, performing no
further action. Faster batch file processing is achieved using this method
for comments instead of REM commands.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

REM in lines with pipes or redirection
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

For example:  REM echo y | del *.*

Problems are encountered when trying to REM out an "echo y | del *.*" line in
a batch file. The problem appears to only occur if there is a pipe or
redirection in the REMed out line, which shows that DOS first reads the entire
line and processes pipes and redirections first, and then goes back to find
out what to do with them in the line. It's actually doing what it thinks
you've told it:  Piping the output of REM to DEL. Since REM has no output,
DEL hangs, waiting for the answer to its question.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Delimiter character
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Prior to DOS 5.0, there was an undocumented DOS function that would allow you
to set the DOS option delimiter character to something else, like a dash (-). 
Once you did this, you could use either \ or / in PATH specifications.

DOS 5.0 removed the function to set the option delimiter, but retained the
function to query what it currently is.

(Unfortunately, no further details were provided in this file, so not sure if
the delimiter character can still be changed somehow.)

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Once again, there's probably a few commands I've missed. If you've got any
to add, please pass them on to me, and I'll reprint the additions in an
future issue of WWIVNews!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³    Tips For Running WWIV Under OS/2 2.1     ³
               ³             By Martin (1@6251)              ³
               ³                     And                     ³
               ³            Lord Sigma2 (1@5498)             ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

[Editor's note: In response to repeated requests by sysops in configuring
OS/2 2.1 to properly run WWIV, both Martin and Lord Sigma2 contributed to
several discussions regarding this topic. The end result is this article, 
which is a compilation of the tips revealed in those discussions, and also
includes the contents of an article on the topic that appeared in _IceNEWS_,
our sister publication on IceNET.]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

MARTIN: FIRST THINGS FIRST
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Getting WWIV 4.23 was something that I, like everyone else it seems, had been
looking forward to for a long time. I was lucky enough to have been able to
get it from Amber the night it was released so I was able to take a look at it
right away. I had planned to wait to install 4.23 on my BBS for at least a
week so I'd have time to really look it over but when I saw what it had to
offer I decided not to wait.

I had been running OS/2 on my second computer for almost 4 months. When I
first installed it I realized that I was faced with almost the same magnitude
of confusion as I had worked through each time I had bought a new, unfamiliar,
computer system. I say this only to say that when I set up WWIV 4.23 under
OS/2 I was far from being an expert (and still am not) on the operating system.
I was a beginner as far as the use and understanding of OS/2 was concerned, and
I was also using a new version of the BBS software. I had a lot of confusion
to overcome!

Regardless, to the best of my memory, and for whatever help this is worth, 
here is the breath-taking saga of Amiga Blues' encounter with running multi-
instance under OS/2.


HPFS or FAT?
ÄÄÄÄÄÄÄÄÄÄÄÄ

I had set up OS/2 on my "personal" (as opposed to the BBS) computer with the
HPFS and dual boot. I didn't realize at that time that a person could switch
back and forth booting either OS/2 or DOS without installing the dual boot
feature under the HPFS. It is possible, though, to install OS/2 on an existing
partition by installing it in a subdirectory using the FAT system. You can
still reboot into DOS by using the "boot /dos" command, and back to OS/2 by
typing "c:\os2\boot /os2" (assuming you have used the default directories).
When it came time to install OS/2 on my BBS computer I decided to use the FAT
system and give it a try. I didn't want to have to repartition my hard drive
to use HPFS. You will have to weigh the advantages and disadvantages of the
FAT vs the HPFS and decide which way seems best for you.

Once I had installed the operating system, I booted it up, made an icon (see
below) for instance number one and ran it. It worked!

Well, it worked to the extent that the board came up and ran. There was still
a lot of work to do before I was ready to actually open the board back up to
callers while running under OS/2.


ICONS AND .BAT FILES
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

In order to get icons for my "instances" of WWIV, I had to go into the System
Setup folder and select "Migrate Applications". Your OS/2 manual will explain
the process involved with doing this. After running Migrate Applications, you
will need to select the "Add Programs" option and "Add" your BBS.COM to the
Selected Programs list. You will do this so that you'll have an icon, but you
will only do this as a first step; you won't actually run the board off it.
You should make a copy of this icon for each instance you will want to run so
that you have one icon for each instance.


ICON SETTINGS
ÄÄÄÄÄÄÄÄÄÄÄÄÄ

Once you have created your icons, go into the Settings for each one and under
"Path and file name:" have them call a .BAT file for each instance rather than
calling BBS.COM. Under "Path and file name:" you will want C:\WWIV\WWIV1.BAT,
C:\WWIV\WWIV2.BAT, and so on rather than C:\WWIV\BBS.COM. This will allow you
to set the instance correctly. See my example .BAT files (following) if you
don't know what I mean by this.

One of the other very important things to do is replace the standard COM
drivers that come with OS/2 with Ray Gwinn's SIO drivers. I won't go into the
way to do this; it's well covered in the documentation files that come with the
drivers. But one thing that's not immediately clear is that you should go into
the BBS's icons and make some changes under the new options the SIO drivers
give you. For one thing, you'll need to disable access to every COM port but
the one used by that instance. For example, let's assume you're running your
setup as follows:

2 remote and one local instance (3 icons total).
Instance 1 (WWIV1.BAT) uses COM2
Instance 2 (WWIV2.BAT) uses COM3
Instance 3 (WWIV3.BAT) is local.

You would want to go into your BBS icons and change your DOS settings so that
the icon for instance 1 (WWIV1.BAT) has access to COM2 only, the icon for
instance 2 (WWIV2.BAT) has access to COM3 only, and the icon for instance 3
(WWIV3.BAT) does not access any of the COM ports. Once you've installed the
SIO drivers, you'll see that the icons will allow for the new options the SIO
drivers provide. Restricting each instance's access to only the COM port it
needs will prevent problems such as online programs causing a System Error
message telling you that your application tried to access a communications port
which is in use by another application.

I don't have any experience with running WWIV under OS/2's drivers and I would
highly recommend getting Mr. Gwinn's drivers. I ran the OS/2 drivers for a
while under Procomm Plus, and the difference between the SIO drivers and the
standard OS/2 drivers was amazing. I went from approximately 600 CPS and many
crashes during transfers to 1600-1700 CPS and no more crashes.

Anyway, back to the issue of setting up your icons... You will also want to
set the IDLE_SECONDS and IDLE_SENSITIVITY to provide the best performance on
your particular system. As I've said, I'm no OS/2 expert, but I do believe
that these settings will work differently from one system to another. Your
settings will probably be different from mine. What I did to get them tweaked
the best I could was to set the IDLE_SECONDS just high enough so I didn't get
the famous "pause after message header" problem, and set the IDLE_SENSITIVITY
so that the processing time would be divided up between instances as evenly as
possible.

What I believe causes the problem with messages pausing right after the header
is displayed is OS/2 mistakenly thinking that the session is inactive and
pausing it until it thinks it's active again. Apparently this is a problem
with OS/2 and communication software. The software (in this case your BBS) is
processing data but there is no mouse movement or keyboard action while you are
reading the message. OS/2 doesn't think anything is happening and idles the
session until you do something. On my system I experienced the problem with
the session pausing after the message header until I set the IDLE_SECONDS up to
4. Setting the IDLE_SECONDS to 4 took care of the problem.

In order to get IDLE_SENSITIVITY set so that it seems to work the best, I tried
setting it as low as possible, and then ran the session. I checked the setting
by doing a new message scan and watching to see if the text was "jerky". If it
was jerky at the IDLE_SENSITIVITY I had, I exited the BBS, quit the session,
opened the icon's DOS settings and bumped the setting up by 10 at a time until
the text displayed smoothly. I then adjusted it by an increment of 5. What I
mean is this:

With IDLE_SENSITIVITY set at 30 if the text scrolled jerkily, I went out and
set the sensitivity to 40. If it was still jerky I set it to 50. If it was
then okay, I set it to 45. If it was okay, I left it alone, and if it was
jerky again I set it back to 50.

I have left INT_DURING_IO off. I have heard that having it on can mess up
network packet handling, and I don't want to risk that.
Another thing I did was to aim the DOS_DEVICE to C:\OS2\MDOS\ANSI.SYS so that
my system would be able to handle ANSI displays.

One last thing that I have just tried is setting the HW_TIMER to on. This is
due to a recommendation in "Your OS/2 Consultant" written by Herb Tyson and
published by Sams Publishing. Having the HW_TIMER on allows WWIV to have
direct access to the timer ports and stops OS/2 from emulating a timer.
Apparently, it's been documented that some fax programs and high speed data
transfer utilities don't run well unless HW_TIMER is set to on.


.BAT FILES
ÄÄÄÄÄÄÄÄÄÄ

The .BAT files are fairly simple. Here are mine:

(WWIV1.BAT)

set WWIV_INSTANCE=1
c:
cd \wwiv
bbs.com /i1

(WWIV2.BAT)

set WWIV_INSTANCE=2
c:
cd \wwiv
bbs.com /i2

(WWIV3.BAT)

set WWIV_INSTANCE=3
c:
cd \wwiv
bbs.com /m /i3

You can see that I've got instance 3 set up for local only use and have used
the /m parameter to disable the BBS from trying to find a modem.


CD-ROM DRIVES
ÄÄÄÄÄÄÄÄÄÄÄÄÄ

I had a little difficulty setting up my CD-ROM drives to work under OS/2 in the
same way they had been working under DOS. The problem was not the fault of
OS/2; it runs CD-ROM drives just as well as it runs anything else. It was just
a matter of finding drivers that worked with my drives (I have Mitsumis). If
you have a Mitsumi CD-ROM drive and haven't been able to find a driver for it,
you can call the OS/2 BBS at 919-517-0001 and get the driver there. The file
name is MITFIX.ZIP and the driver name is MITFIX001.ADD. This driver supports
the new FX series of Mitsumi drives as well as the CRMC-FX001, the CRMC-FX001D
and the older CRMC-LU005 drives. Once I found and installed the drivers (see
your OS/2 manual for more information on this; it's covered very well), I set
up a small RAM drive so that the CD-ROM drive letters would be the same as they
had been under DOS. I did this because I had used a RAM drive under DOS. This
may or may not be important to you; I originally did this so I could run the
board under DOS or OS/2 without having to change anything. I've never gone
back to DOS though.


ADDITIONAL CONSIDERATIONS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

OS/2 AWARE
ÄÄÄÄÄÄÄÄÄÄÄ

The source code I got when I first downloaded WWIV 4.23 from Amber somehow did
not have the code enabled to allow WWIV to work as well under OS/2 as possible.
If you are registered and have access to your source code, check UTILITY.C and
be sure the following code is in void giveup_timeslice(void):

      case 4 :/* outs("OS/2"); */
        win_pause();                  /* add for OS/2 timeslices*/
        /* delay(17); */
      break;

Many thinks to the person responsible for this "fix". My board ran a lot
better after I put this code in, and I checked with Wayne, who confirmed that
it should be in there. People had been complaining about the system being very
slow and jerky at times until I put this code in. I had even upgraded from a
386DX-40 to a 486DX2-50 in order to help the BBS run more smoothly, but things
didn't really improve until I added this code. The only time the board seems
to slow noticeably now is when someone is doing a file transfer.


INIT
ÄÄÄÄ

I've corresponded with Filo regarding the way INIT handles things with more
than one instance and he's indicated that there may be some changes under 4.24
to make the data it writes more "instance specific" (my word, for lack of
being able to think up anything better). As things are now, the only thing I
feel I can count on being kept separate from instance to instance is the modem
and COM port configuration information. I do know from first-hand experience
that your net low and high times are not kept separate; if you change the net
times under one instance it will be changed for all.


MEMORY
ÄÄÄÄÄÄ

OS/2 is VERY memory hungry and you will not be satisfied with its speed or
performance unless your system is configured with enough memory. I know of
people who are running WWIV under OS/2 with only 4 megabytes of memory, but I
understand the Presentation Manager (the graphic interface) takes up almost 4
MB, so I believe 8 MB is really the minimum for satisfactory performance and
more is, of course, even better. Another consideration is that if you are used
to using a RAM drive you should be aware that using one under OS/2 will take
the memory right off the top and may have a significant impact on the
performance of your system.

Rocker (1@6450) is running his system without using the Presentation Manager
and he reports that this frees up his system significantly.


EXTERNAL TRANSFER PROTOCOLS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

JAFO (1@8857) had indicated in one of the networked subs that the newest
version of DSZ is much more better behaved under a multitasking environment
than its predecessors have been and I believe he is right. I just downloaded
the DSZ.ZIP file from Telegodzilla with the DSZ.COM dated 02-02-94 and the
GSZ.ZIP file with the GSZ.EXE file dated 02-03-94 and have installed them. The
system used to bog down significantly during file transfers and I believe that
it is a lot better now that I've installed these newest versions of DSZ and
GSZ. If you can't find them anywhere else they are available on Telegodzilla
at 503-621-3746.


MY OWN SETUP
ÄÄÄÄÄÄÄÄÄÄÄÄ

If you are interested, my system currently looks like this:

I have a 486DX2-50 MHz computer with 8 megabytes of RAM, 550 megabytes of hard
drive storage space, two Mitsumi CD-ROM drives, a US Robotics 14.4 Courier HST
dual standard modem on the first line (612-591-1781) and a US Robotics 14.4
Sportster on the second line (612-591-0173).


CONCLUSIONS
ÄÄÄÄÄÄÄÄÄÄÄ

In case you haven't been able to tell, I am very happy with the way WWIV runs
multiple instances under OS/2. While there are definitely some challenges, the
end result is, in my opinion, well worth it. If you've got the resources to be
able to run OS/2 and if you want to run more than one instance, I heartily
recommend going with OS/2.

-Martin


REFERENCES
ÄÄÄÄÄÄÄÄÄÄ

DSZ and GSZ can be ordered from Omen Technology Inc.
                                17505-V Northwest Sauvie Island Road
                                Portland, Oregon  97231
                                Modem: 503-621-3746
                                Fax:   503-621-3735

The Mitsumi device drivers can be downloaded from IBM's BBS, located at
                                                  Research Triangle Park, NC
                                                  Modem: 919-517-0001
                                                  Fax:   800-IBM-3395

SIO can be ordered from The Software Division
                        Attn: Raymond L. Gwinn
                        12469 Cavalier Dr.
                       Woodbridge, VA  22192
                        Voice orders: 703-494-4673
                        Fax:          703-494-0595


Reference Books I've found helpful
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Dvorak, John C. "Dvorak's Guide to OS/2 version 2.1",
        Random House, Inc., New York, 1993.


Moskowitz, David and Kerr, David,  et al. "OS/2 2.1 Unleashed",
        Sams Publishing, Carmel, IN, 1993.


Tyson, Herb. "Your OS/2 2.1 Consultant",
        Sams Publishing, Carmel, IN, 1993.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

LORD SIGMA2 ON DOS SETTINGS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

I have been running with WWIV 4.23 and OS/2 2.1 and found these setting to
be acceptable. True, I run nothing big except the local node, Norton, and a
few other things here and there, but it works a HELL of a lot better than it 
did with Windows. In fact, my users get 1650+ cps UL or DL (at 14.4k) with me
there in the background! 

A word of advice: A few of these settings are particular to my system, such
as those for the COM ports, so I expect you to make the changes necessary for
it to work 100% for you. It may take a little tweaking, but these settings
should get you in the right direction.

Oh, and for those wondering, I do -NOT- run HPFS. Also, you need to have both
Ray Gwinn's SIO and VSIO COM drivers installed. At the present, I use v1.26c,
but by the time this article sees print I expect Ray to have released at least
one new release.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

AUDIO_ADAPTER_SHARING = ON
DOS_AUTOEXEC = C:\AUTOEXEC.BAT
DOS_BACKGROUND_EXECUTION = ON
DOS_BREAK = OFF
DOS_DEVICE = c:\os2\mdos\ansi.sys
DOS_FCBS = 16
DOS_FCBS_KEEP = 8
DOS_FILES = 30
DOS_HIGH = ON
DOS_LASTDRIVE = (f)
DOS_RMSIZE = 640 
DOS_SHELL = <DEFAULT>
DOS_STARTUP_DRIVE = <BLANK>
DOS_UMB = ON
DOS_VERSION = <DEFAULT>
DPMI_DOS_API = AUTO
DPMI_MEMORY_LIMIT = 2
DPMI_NETWORK_BUFF_SIZE = 8
EMS_FRAME_LOCATION = AUTO
EMS_HIGH_OS_MAP_REGION = 0
EMS_LOW_OS_MAP_REGION = 384
EMS_MEMORY_LIMIT = 1024
HW_NOSOUND = ON
HW_ROM_TO_RAM = ON
HW_TIMER = ON
IDLE_SECONDS = 4
IDLE_SENSITIVITY = 90
INT_DURING_IO = OFF
KBD_ALTHOME_BYPASS = OFF
KBD_BUFFER_EXTEND = ON
KBD_CTRL_BYPASS = NONE
KBD_RATE_LOCK = OFF
MEM_EXCLUDE_REGIONS = <BLANK>
MEM_INCLUDE_REGIONS = <BLANK>
MOUSE_EXCLUSIVE_ACCESS = OFF
PRINT_SEPARATE_OUTPUT = ON
PRINT_TIMEOUT = 15
SIO Allow Access COM1 = ON
SIO Allow Access COM2 = OFF
SIO Allow Access COM3 = OFF
SIO Allow Access COM4 = OFF
SIO_Idle_Sensitivity = 100
SIO_Mode_DTR = Turn ON at OPEN, OFF at CLOSE
SIO_Mode_FIFO_Load_Count = 16
SIO_Mode_IDSR = Ignore DSR During Receive
SIO_Mode_OCTS = HandShake Signal, as in RTS/CTS
SIO_Mode_ODSR = Ignore DSR During Transmit
SIO_Mode_RTS = HandShake Signal, as in RTS/CTS
SIO_Mode_XON/XOFF = No XON/OXFF flow control by SIO
SIO_Screen_Sync_Kludge = ON
SIO_Share_Access_With_OS/2 = ON
SIO_Virtualize_16550A = ON
SIO_Virtualize_COM_Ports = ON
VIDEO_8514A_XGA_IOTRAP = ON
VIDEO_FASTPACE = ON
VIDEO_MODE_RESTRICTION = CGA
VIDEO_ONDEMAND_MEMORY = OF
VIDEO_RETRACE_EMULATION = ON
VIDEO_ROM_EMULATION = ON
VIDEO_SWITCH_NOTIFICATION = OFF
VIDEO_WINDOW_REFRESH = 5
XMS_HANDLES = 32
XMS_MEMORY_LIMIT = 1024
XMS_MINIMUM_HMA = 0

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Also, there are a couple of changes to CONFIG.SYS that I suggest:

PRIORITY_DISK_IO=NO
TIMESLICE=32,32
MAXWAIT=1

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Hope these help! If you have any questions or suggestions, please feel free
to drop them my way!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³                 TechnOTES                   ³
               ³        Compiled by the WWIVnews Staff       ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

...From the "Sleeping With The Enemy of My Enemy" department: Remember when
Stac decided to go with Microsoft's offer of bundling Stacker with DOS instead
of IBM's offer? Well, IBM wasn't pleased at all, and went with Addstor's
competitive product, SuperStor, in a rather unsuccessful coupon mail-in
gimmick. Less than 30% of the coupons included with IBM DOS 6.1 were mailed
in, with most IBM DOS users preferring to stick with Stacker.

...As WWIVNews readers found out last issue, Addstor is no longer in business, 
and SuperStor is history. Add to this Stac's recent defeat of Microsoft over
infringement of copyrights concerning DoubleSpace technology, and you now
have a clear understanding of why IBM went knocking on Stac's door the day
after the verdict with a serious offer to include Stacker 4.0 with IBM DOS
6.3. This time, however, Stac officials decided that the coupon gimmick was
just as bogus as consumers showed it was, and insisted that Stacker be 
packaged *with* IBM DOS 6.3. IBM agreed to these terms gladly, and IBM's
"OS/1" will be released as such around mid-May at last report.

...Microsoft, however, was rumored to be courting the now-unemployed software
engineers from Addstor, in hopes of being able to produce a legal successor
to DoubleSpace, and one that will work with NTFS as well. NTFS is scheduled
to be included as part of Windows 4.0 - "Chicago" for those uninformed - and
at last word was still an option and not a forced feature. Word from inside
Microsoft, however, is that were a version of NTFS shows up with working
file compression, the plan was to make this a required feature for at least
one partition, and quite possibly for all others. The general impression 
appears to be "Ok, fine. You geeks supported Stac when they challenged our
might. Sure, we lost, and we'll give you file compression that's legal.
However, if it doesn't work with your system or your software, that's just
too bad, chump!" 
...Now, if that's all there was to it, you could simply chalk it up to more 
sour grapes on the part of Microsoft. However, in late, late June, Microsoft,
on orders from Bill Gates himself, threw in the towel on this fight, and
gave up all court manouvers to reverse any of the decisions made against them
in Stac v. Microsoft. In an agreement that reportedly "took two minutes to
draft, and less time than that to sign", Microsoft agreed to pay $83 million
to Stack, in addition to purchasing a non-voting 15% of Stac corporate stock.
Stac, in turn, granted a cross-platform technology licensing agreement to
Microsoft, which allows the Gates boys to use Stacker code if they wish in a
future replacement for Doublespace.

...The agreement, thankfully, does not prevent Stac from selling similar or 
competetive rights to their products to other companies. This, in turn,
protects the recent deal with IBM to include complete versions of Stacker
4.0 in future versions of IBM DOS. In short, folks, Bill Gates finally had
to eat crow, and admit he likes the taste!

...From the "How Green is my PC" department: Ever wondered where those cheap,
bulk diskettes come from? One of the major suppliers is a company called Eco
Tech. This company buys floppies of obsolete, unsold packages in bulk from 
major software manufacturers, and reformats them into blank, high quality 
diskettes. Manufacturers such as WordPerfect, Lotus, and even Microsoft have
sold their old back stock diskettes to Eco Tech, who in turn sells them
for a reasonable discount. 

...These disks are a little higher than the cheap disks you see in _Computer
Shopper_, but the difference in cost is about what Eco Tech donates to the 
Wilderness Society for each disk sold. If you want to help save some trees
or some extinct mutant species of albino salamander, and save some cash on
floppies, call Eco Tech at (713) 444-6074.

...From the Alpha Control department: Amidst all the hoopla about the Pentium,
the PowerPC, and the DX4, Digital Equipment Corporation unveiled a new Alpha-
based workstation as powerful as the one announced by IBM in January, but at 
half the price. Running at just under 150MHz, this particular unit is 
considered by DEC to be a "scaled-down" version of their 250MHz Alpha 
Workstation.

...Those thinking to use one of these systems for netsurfing had better
start saving now; Digital's model costs $36k, compared to $70k for the IBM's 
PowerPC workstation. A DEC spokesman attributed the "low" cost to the tight
integration of the Alpha chip with the interfacing chipset used by this 
machine, while IBM's machine uses 8 chips to do what the Alpha chip can
accomplish with a single chip. Still, it's a bit pricey for most of us,
but think of the multitasking capabilities!

...Speaking of downsizing, Seymour Cray is at it again. This time, though,
Cray Research is moving into the commercial computing market with a downsized 
version of the YMP Interface series. The Cray Superserver 6400 is said to be
based on Sun Microsystem's Sparc chip, and runs software based on Sun's 
Solaris operating system.

...The first machines are already being offered for sale, and Cray spokepersons
have reported that the $1 million, unoptimized prototype model handled 700
users as fast as a comparable $5 million midsize mainframe computer, which 
also happened to be manufactured by Cray. Talk about shooting yourself in
the foot for a good cause!

...For those looking to push WWIV to its limits, tho, the Alpha looks a bit
closer to reality. System base prices for this new series of Crays will 
range from $400,000 to $2.5 million. Wonder if that includes the hard drive?

...From the Shaking the Apple Tree department: While everyone is either
praising or condemning Apple's entry into the PowerPC market, or flipping
out over the overrated 640AV, another Apple entry into the niche market has
been virtually ignored - the MacTV.

...This new Mac incorporates the equivalent of a Macintosh Centris 610, a 14"
color television and a stereo CD/CD-ROM player all in one unit. In a break from
typical Apple archetecture, this unit can be connected to VCRs, camcorders, 
video disk or video game players of almost any manufacture, and comes with a
suite of word processing, spreadsheet and database software. 

...Priced at $2,079, the MacTV will be aimed at the home and educational 
market, and will be available later this year at selected retail stores, 
college campuses and through the Apple Catalog.

...From the Legal Buzzards department: A brief nOTE for those who've been
keeping up with former Apple CEO John Sculley. At last report, Sculley had
taken a similar position with Spectrum, a small East Coast company that 
controls a series of patents related to the wireless transmission of computer
data. In recent weeks, Sculley has left this position, and filed suit against
Spectrum's owners for breach of contract and false presentation of the
company's financial status at the time of Sculley's hiring. Seems that Spectrum
was nowhere near as stable as they presented themselves to Sculley, nor were
their patents as base solid as they claimed.

...Sculley, who took control of Apple after the ousting of Steve Jobs, left
Apple after sales flagged in response to a more PC-demanding consumer market.
He was replaced as Apple CEO by A.C. Markkula Jr, one of the three co-founders
of Apple, and had relinquished his position as CEO to the president, Michael 
Spindler, in June of 1993. A few days later, in a move that surprised most
industry analyists, Sculley accepted the position of chairman and CEO of 
Spectrum, who at that point and time hadn't even broken into the NYSE!

...From the Francisco Franco is *Still* Dead department: A nOTE from a
WWIVNetter in Barcelona, Spain, reports that some 100 Spanish Olive growers 
have filed a complaint with the proper authorities about how they had not
received their European Community subsidies, even though they'd filled
out the required paperwork. Authorities in Andalucia were more than redfaced
when they discovered their computer wasn't programmed to recognize the letter
"n" with a tilde.

...And yes, all the farmers affected had names with tildes. Go figure.

...With tax time past for a while, here's a bit of trivia that might interest
you: In the first 8 months of 1993, the IRS identified more than 23,000 
fraudulent electronic returns. While this might seem a drop in the bucket 
compared to the total number of returns, this figure was *double* that of 
1992! And this occurred even though the total number of returns filed 
electronically had increased by only 13%. Wonder how many of those were 
submitted with those goofy incomplete copies of Andrew Tobias' MYM!

...From the I WANT MY MTV.COM! department. Yep, its true. MTV is officially 
on the Internet. VJ Adam Curry is now running an ftp and gopher site through
a T1 connection supplied by Digital Express. Since the folks at MTV are not
yet ready to commit financially to the project, Adam is paying for the
connection himself. 

...Those wishing to access files such as charts, audio files, schedules,
.GIF's and .AVI files can use the anonymous ftp connection of ftp.mtv.com 
and cd /pub/. The pub directory contains a README file explaining the
setup and what's available. Adam hopes to get the other MTV VJs online for
Q&A participation, and plans to have a weekly newsletter out as well. Until
then, those of you wishing to tell those at Empty-Vee to wisen up and drop
all the technoboogiepoprapcrap and Seattle Garage Garbage should pass all
such correspondence to Adam c/o root@mtv.com.

...From the ZPG (Zero Population Growth) department: At best estimates, The 
Internet is growing at 10% increase in users per month Various sources are,
naturally, starting to report serious electronic traffic jams. Those doing the 
estimates, the National Center for Supercomputer Applications, report that an 
increase in connections increased from roughly 100,000 in June of 1992 to 
almost 400,000 in October of 1993, and that this number is expected to 
double by the end of 1994.

...Center officials suggest that the only solution to the traffic snarls may 
be to take a $15 million supercomputer and use it as both an electronic 
switchboard and an an electronic librarian. With Seymour Cray trying to make 
his own X and Y-MP's obsolete, at least one should be available as surplus for 
this purpose within a year or two, if not sooner!

...Shades of ARPAnet: In a possibly related story, the DOD has announced 
that Defense Technical Information Center will separate the Internet early 
in 1994. This separation will be accomplished by the installation of a mail
-relay between the DTIC and the Internet. Although esxchange of electronic 
mail between the DOD and Internet users will be allowed, the intent is to 
add another level of security to prevent any sort of security breach problems
along the lines of those that resulted in the destruction of ARPAnet.

...Although some getting used to will be required by users attempting to
communicate through the new mail-relay, Internet users will not be allowed 
to make direct network connections to DoD host computers. This move by the
DOD should probably not be interpreted as an isolated incedent, and 
netsurfers should expect other government agencies to start distancing 
themselves from the Internet as its size continues to grow exponentially.

...From the Try Before You Buy department: Jumping on the Demo CD bandwagon,
Apple is marketing an Instant Access CD-Rom for the Macintosh, with over 650 
MB of commercial software on it. As with the PC versions, demo and test
versions on the disk can be upgraded to full working versions by calling a 
phone number and paying by plastic. You'll be given a password for each 
program you register to unlock it and install it as if it were a regular, 
store-bought version. No word on whether a crack exists for this disk yet 
or not.

...From the Disclaimer of the Month department: This disclaimer from Haventree
Software's EasyFlow program was passed onto us by a reader from ICEnet: 

"If EasyFlow doesn't work: tough. If you lose millions because EasyFlow messes
up, it's you that's out the millions, not us. If you don't like this 
disclaimer: tough. We reserve the right to do the absolute minimum provided by
law, up to and including nothing. This is basically the same disclaimer that 
comes with all software packages, but ours is in plain english and theirs is
in legalese. We didn't want to include any disclaimer at all, but our
laywers insisted."

...Hmm, wonder if we should let Wayne and Filo read this section of WWIVNews.
They might get some really nasty ideas!

...From the Pyrhhic Victory department: In Hempstead, NY. a fired computer 
contractor was found guilty of using a virus to attempt to collect an unpaid 
bill from a customer. He reportedly infected the client's system with the 
virus, threatening loss of data if they did not pay for services rendered.
The customers claim his work was substandard and were withholding payment.
While the contractor was both fined and jailed, the customer still lost all
data, and had to reformat several systems on-site in order to regain the
use of their systems.

...From the Let's Copy AOL department: Microsoft is reportedly developing a
an online service along the lines of America Online in structure, but akin
to Compuserve in size and features. This service, code-named "Marvel", will
offer all the usual services and gimmics associated with online services,
but Microsoft spokespersons have gone on record as saying "this *might* be
the only way that users will be able to get bug fixes and quick upgrades
for Microsoft products in the future." 

...Plans are to have the graphic front end installed on all machines as part 
of the upcoming Windows 4.0. Rumors have it, thought, that delays in the
development of "Marvel" has added additional delays in the release date of 
Windows 4.0, which has been pushed back to as late as 4th Q'94!

...Don't let our Editor see this one: With all the hoopla over how many DSP
products don't work with OS/2, it seems Best Data is set to release an 
incredible add-on card for IBM PCs. Developed by IBM, the ACE (Advanced 
Communications Enhancement) system uses DSP (Digital Signal Processing) 
technology to create a single card that is a 14.4 V.32bis modem with 9600 
Fax send and receive, a 16-bit CD quality stereo sound card, an answering
machine, a voice mail system, a fax server, and a full duplex speaker
phone! In addition, later releases of the new DSP card will do OCR and then
read your faxes to you! 

...This is some card, folks. Should IBM decide to sell these separate from
their systems, the ACE is expected to cost around $399. Standard equipment
includes a microphone input jack, audio I/O jacks, and standard RJ-11 
telephone jacks. The ACE also supports basic voice recognition, text <-> 
speech, and phonic speech synthesis. Future versions of the ACE will have 
plans for the card to support colorfax, full motion video, NTSC output, 
JPEG/MPEG, etc, etc. All this card needs is a Swiss Army seal of approval!

...From the "Smells Like Windows Spirit" department: Word from insiders at
Sun Microsystems tell of a new version of WABI that has been reportedly 
reverse-engineered to allow proper emulation of Windows 3.11 for Workgroups 
routines. No release date has been set for this still unannounced product,
as Sun's lawyers are reportedly burning the midnight oil to cover all bases
and keep Microsoft from finding any reasons to sue over the Unix world's
attempt to stay afloat in the mainstream computer market.

...As readers of WWIVNews are aware, Sun released the final version of its 
Windows Application Binary Interface late last year. WABI will allow Unix
systems from IBM, Hewlett-Packard, Novell and Sun to run Windows
applications on their systems seamlessly, so long as they don't do any
serious object imbedding above release 1.0.

...From the "Simon Legree" department: American Express reports that home-
based workers handle an average of 26 percent more calls than office-based
workers, resulting in a 46 percent average increase in revenue from travel
bookings. AmEx, which began looking into telecommuting for employees over
two years ago, expects to have 10 to 20 percent of its telephone order-entry
employees working from home.

...On a related note, however, it was revealed that at least 10 of that 46
percent increase in revenue was attributed to the fact that the AmEx order
takers were paying for their own phone bills! However, for working parents
with seriously dependent children, this move in telecommuting was rather
well recepted. AmEx's personel department was forced to establish a waiting
list because the demand for this program was so high!

...From the "I Got Da Power" department: IBM spokespersons are talking now
about yet another version of the PowerPC microprocessor. This processor, which
some are calling the PowerPC 630 chip and which IBM has referred to as the 
Power3 architecture in the past, is reportedly under development *without*
any assistance from either Apple or Motorola!

...According to IBM insiders, the new PowerPC chip will be used in IBM's RISC
System/6000 workstations and servers, and quite possibly in a proposed new
version of the AS/400 line of midrange computers, rumored to be internally
called "The Borg". Other plans call for its use in a future line of parallel
processing systems. However, IBM has publicly stated that PowerPC chips,
though not necessarily the 630 itself, will be incorporated in the AS/400 
line, which currently uses some rather archaic, proprietary processors. 

...For those keeping score, there are three existing versions of the PowerPC 
chip, and another two due to begin production this year. The first, and 
most widely used PowerPC chip today is the 601. The 601 is used in the PowerPC
computers currently available from IBM and Apple, and is currently the only
version readily available on the market. The second version, the PowerPC 603,
is a power-saving version of the 601, while the more powerful 604 version is
due for volume production by the end of this year. On the way is the PowerPC 
620, which is due to begin limited production late this year and will be
designed for high-performance workstations and servers, and the 615, which
will feature the 80486 instruction set on the chip as well as the native
PowerPC code. 

...By comparison, the 630 chip is expected to offer roughly double the 
performance of the 620, and might become available around 1996, according 
to some industry analysts. 

...Speaking of IBM-produced chips, IBM has also announced that it has placed
a complete digital signal processor (DSP) subsystem on a single microprocessor.
The new chip is part of IBM's Mwave line of products, and includes 32-voice 
wave table synthesis and Sound Blaster hardware registers. 

...Known as the MDSP2780, the new processor has a 16-bit central processing 
unit (CPU) that IBM said can process signals at 33 MIPS. It also has high-speed
fax and data communications capabilities, including support for the new 28.8 
V.34 modem "standard". Power management features, including a sleep
mode and the ability to control attached peripherals, are also built in. 

...By effectively combining a sound card and fax/modem on a single chip, which
IBM claims is an industry first, costs are cut and board space is saved. This
in turn will give OEMs more flexibility in designing the IBM chip into their 
products, which in turn will allow VARs to cut their own costs while adding
versatility to their basic systems. 

...Lessee, they combined the sound card and the modem. All they need to do
now is to throw in the Multi I/O, IDE and SCSI interfaces, and a 2MB SVGA
adaptor. And we thought the long card format was dead!

...From the "What? Me Worry?" department: As expected, Microsoft has released
a version of DOS that includes a new disk compression technology. Version 6.22
includes Drivespace, a technology that replaces the company's biggest gaffe
to date, Doublespace. Microsoft, as we all know, was forced by a court verdict
to remove Doublespace after it had determined that Microsoft had violated the 
data compression patent of Stac Electronics, the publisher of Stacker, which
is now the defacto standard data compression program. 

...MS-DOS 6.22 is essentially the last gasp of the mortally wounded following
a 16-month battle between Microsoft and Stac. In January 1993, Stac sued 
Microsoft, alleging violation of its patents following a failed partnership -
viewed by most as a botched attempt by Microsoft as a merger-takeover of
Stac - and a month later Microsoft countersued, charging patent infringement
by Stac because of Stacker's compatibility with Doublespace. Stac won their
end of the suit, and the court awarded them $120 million in damages. However,
the same court gave Microsoft $13.7 million based on Stacker's illegal
compatibility with Doublespace.

...Almost immediately, Microsoft started shipping MS-DOS 6.21 without any
form of data compression. To add salt to the wound, a federal judge denied
Microsoft's attempt to have Stacker pulled from retail shelves over the 
Doublespace compatibility issue, and ordered Microsoft to withdraw or destroy
any versions of MS-DOS 6.0 or 6.2 that hadn't already been sold. 

...Now, as for just exactly *what* replaced Doublespace, Microsoft is calling
this new form of data compression "Drivespace". Those who've worked with the
beta testing have informed TechNOTEs that "the technology included in the 
latest release offers similar features to those in Doublespace, and also
includes a revised ScanDisk, the utility that detects, diagnoses, and repairs
disk errors on uncompressed drives, that supports Drivespace." A feature 
called Doubleguard has been added that provides an extra layer of protection
for data by checking data integrity on the fly. 

...However, the hot inside tip is that Drivespace is reportedly nothing more
than XtraDrive in Bill Gates' old clothes! While this hasn't been confirmed 
- and in fact, has been vehemently denied by Microsoft spokespersons - beta
testers have been reporting on several computer networks about how the
volume format of Drivespace is almost identical to that used by XtraDrive.
Those following the history of this mess will remember that Microsoft *and*
IBM both courted XtraDrive's creators prior to setting their sights on
Stac and Stacker, and probabl are the least surprised at the surfacing of
this particular rumor.

...DOS 6.22 is starting to ship to OEMs, and is expected to be available to 
end users later in July. Microsoft will make available an upgrade for users 
of MS-DOS 2.11 - as if there's really any of them left! - or higher, and a 
Step-Up that allows licensed users of MS-DOS 6.0 and 6.2 to upgrade to this
legal, Stac-free version. The complete MS-DOS 6.22 has an MSRP of $77.95,
while the upgrade and Step-up versions are expected to ship for $49.95 and
$9.95, respectively. 

...From the "Michael Crichton" department: Another new super-virus has reared
its ugly head, in all places good old Ann Arbor, Michigan. This virus, called
"Junkie," was discovered accidentally while a sales representative for Reflex
was demonstrating an anti-virus program for a customer. Ironically, the rep 
was in the process of demonstrating the merits of that company's Disknet 
anti-virus software. 

..."Junkie", according to McAffe & Associates, reportedly has most software 
engineers concerned for several reasons: It is encrypted, making it difficult
to be spotted; it is polymorphic, meaning it changes each time it replicates;
and it infects both the drive's boot sector and executable files on the disk.
The latter characteristic is called multi-partite by engineers. 

...Reflex engineers, concerned because the virus was first discovered on their
own home turf, are studying the characteristics of "Junkie" in an effort to
see what other effects it may have on a computer. The source of the virus is
still uncertain, but it was discovered on pre-installed, shrink-wrapped
software. 

...Those same Reflex engineers say 'From what we've observed, "Junkie" is 
spread by infecting the boot sector, the portion of the hard disk that 
contains the startup instructions for a computer. It can reportedly also 
infect the boot sector of a floppy drive and even make an anti-virus program 
a carrier, and in turn spread the very viruses its supposed to detect and
eradicate. Scanners open files to search for viruses, in turn opening the door
for Junkie to use the scanner itself as a means of spreading the virus!" 

...As of press time, the so-called "Ann Arbor incident" is the only time so 
far "Junkie" is known to have surfaced. Both McAffe and Reflex engineers
warn that there are no visible warnings of the virus, and stress the need for
having a current backup of your computer data. "The only known cure for this
virus is re-formatting the hard disk," said one Reflex spokesperson. "That 
gets rid of "Junkie" better than anything else!" Users are cautioned not to 
make a backup copy of a drive that is suspect, since the backup will also be 
contaminated. 

...From the "Obscure Blondie Album Title Reference" department: Parallel
computing is no longer the private playtoy of the Cray Busters. Adaptive 
Solutions has announced it will ship a parallel coprocessor board for
the PC in July. The company says the board - called the CNAPS/PC - can
speed up performance of a Pentium-based system by as much as 1,000 times. 
According to ASI spokespersons, the board also works with 386 and 486-based
systems. 

...The board complements the PC's microprocessor by accelerating high-volume
pattern recognition applications such as real-time optical character 
recognition (OCR), forms processing, image processing, signal processing and 
neural networks. This allows the PC to perform those tasks which humans 
traditionally perform but which have been difficult for even the most powerful
computers, such as reading handwritten text, recognizing an individual's face,
or quickly understanding patterns within complex data such as a manufacturing 
process.

...This step towards HAl doesn't come cheap, either. CNAPS/PC is priced at 
$2,995 to $6,695 in OEM quantities and is scheduled to ship in July. Also,
as with most parallel systems, the board requires some application software
and some code optimization to fully utilize the capabilities provided by
parallel processing. The company is working on plans, yet unannounced, to 
release the board and an operating system enhancer as an after-market item. 

...From the "IDE Didn't Know That!" department: IBM's Storage Systems
Division - don't you just *love* those official sounding department names? -
is now offering a 3.5-inch, one gigabyte (GB) AT Hard Disk Drive for sale to 
individual users as well as OEMs. This drive is another version of the same
1GB drive that IBM has been selling for some time with a SCSI interface. 

...A key feature of the drive is that it can work in duplex mode, making it
compatible with existing AT basic input-output systems (BIOS) by having the
drive appear as two logical 500 megabyte (MB) drives. Thus the drive would
appear as volumes C and D, each of 500MB, getting around the inability of
older AT BIOS systems to deal with drives of more than 528MB. No additional
device drivers are needed, IBM said. 

...The 1GB AT Hard Disk Drive is one inch high, runs at 5,400 rpm, and has an
8.5ms access time, according to IBM. The company promises a mean-time-between-
failures of 800,000 hours, and sells the drive with a five-year warranty. 
Available now, the 1GB AT Hard Disk Drive has a list price of $785. 

...On a related note, According to market research group Frost & Sullivan,
the average size of your hard disk will rise to 1GB by 1996! Surveys have
indicated that increased demand for storage space will push computer users 
to seek five to 15 times more hard disk space within the next two years, 
pushing the average hard disk on a stand-alone desktop PC to a Gigabyte in 
size, the market research group said. 

...From the "All Eggs in One Basket" department: On May 10, Novell secured
federal regulatory antitrust clearance for its $1.4 billion acquisition of 
WordPerfect and its $145 million buyout of all rights to Borland's Quattro 
Pro spreadsheet program. 

...By setting in motion the processes necessary to buy both WordPerfect and 
Borland's spreadsheet business, as well as the release of Novell DOS v7.0,
Novell has in effect declared war on market dominator Microsoft. In fact, the
two deals should enable Novell to become a potent challenger to Microsoft on 
virtually all fronts.

...Novell's head honchos haven't skipped over this fact, obviously. The 
company has has already announced several plans to use the new product lines
to develop an integrated suite of products. This suite will be aimed at both 
office and stand-alone environments, and will include the normal features of 
word processing, spreadsheet operations and communications. All products will
also be cross-platform compatible, and will take complete advantage of both
Novell's Netware and Unixware software. 

...However, as with any war, casualties tend to accumulate. Novell's stock 
lost more than a quarter of its value over concerns by Wall Street that
Novell has paid too much for the assets. Shares of Novell were down from
$62.5, to as low as $17.625 a share in mid-May on the NASDAQ. Numerous
financial analysts, such as Dean Witter Reynolds, Alex. Brown & Sons and 
Merrill Lynch have all dowgraded the stock since the deal was announced. 

...Novell, of course, has been on a merger trail for several years, with
eyes on WordPerfect, Lotus and Borland. The trail got hotter late last year 
when Ray Noorda, Novell's 69-year-old CEO, announced that a search was 
underway for his successor - one who reportedly would be more experienced
in corporate takeovers.

...Novell, of Provo, Utah, reported annual revenues of $1.1 billion, and is 
considered the leading manufacturer of computer networking software.
WordPerfect, of Orem, Utah, still managed to garner 1993 sales of $700 million
despite severe competition from Microsoft Word, and is arguably the leading 
producer of word processing programs PCs.

...While we're still looking in the egg basket, Adobe announced in March plans
to buy Aldus for $525 million, although in mid-June the FTC had issued a
preliminary denial of approval, and had requested that some undisclosed 
documents be released to stockholders before said approval could be considered.
Meanwhile, entertainment software leader Electronic Arts announced it would 
buy rival Broderbund for $400 million. However, Broderbund axed that deal in
late May, citing "irreconcileable differences".

...From the "Motel 666" department: IBM has announced that its UK operation 
has teamed up with Rob Payton, a US hotelier to create an IBM-themed bedroom 
at Stapleford Park, his luxury country hotel in Leicestershire. The IBM 
bedroom - rumored to be called "The Blue Suite" - will be part of a new 
venture involving the redesign of a 16th century cottage next to the hotel 
and its 500 acres of parkland.

...Guests in the IBM bedroom will be able to stay in what's being described 
as "a stylish, cosmopolitan room, which not only comes complete with a
fully-equipped home office and a 24 hour hotline to IBM helpware, but also
offers tutorials to those who want to learn the basics of computing." The
decor is, as one would expect, somewhat blue in nature, and subtle 
interpretations of the IBM corporate logo can be found on everything from
the carpet to the bathtowels to - you guessed it - the toilet lid. 

...Now, before all you Mac geeks go rushing off for the opportunity to take
a tinkle on Big Blue, you'd better start asking how much a night in the IBM 
room costs. Right now, nobody's willing to make an official statement, but
one IBM spokesperson who asked to remain nameless *and* genderless said that
the internal word was $295 a night, with group rates available! The actual
price will reportedly be decided nearer to opening day in August.

...From the "HAl meets Jurassic Park" department: In a move that surprised
most industry experts, IBM has completely revamped, renovated, recycled, 
replaced and regurgitated its AS/400 line of midrange computers. Major changes
were brought on the aging line of minicomputers, starting with reducing the 
number of models from 19 to four, updating the OS/400 operating system, and 
even changing the color and shape of the boxes.

...IBM intends for the new designs to help IBM sell AS/400s to buyers who are
interested in client/server computing, and to "blow away the concept of the
AS/400 not being an open system," said David Thomas, general manager of IBM's
AS/400 division, in a New York press conference. This blowing is reportedly
accomplished by an updated OS/400 operating system, whose POSIX environment
now incorporates about 80 percent of the APIs used by the top 60 Unix 
applications. At the same time, tighter support for client integration was
added with Client Access/400, which now allows any client computer - including
IBM and compatible machines running DOS, OS/2, or Microsoft Windows, as well 
as Apple Macintoshes - to be able to 100% with the new AS/400 line.

...The idea is to remold the aging AS/400 line into the super-servers for
the remainder of the decade. Old AS/400 models can be upgraded to the new 
models, with upgrades ranging from a simple performance upgrade using a 
processor and network accellerator combo, to a complete motherboard swapout.
Other hardware changes also include the introduction of a new File Server 
Input Output Processor (FSIOP) that uses a 66 megahertz (MHz) Intel 486 
processor that IBM said results in an eight-fold boost in performance when 
using the AS/400 as a file server to personal computers.

...Still to come is a change in the processor chips at the heart of the 
AS/400 itself. IBM plans to replace the current chips with a variant of the 
64-bit PowerPC 620 chip, and a possible "low-budget" version using the 615
chip is also reportedly in the works. IBM spokespersons have stressed 
repeatedly, however, that the change in processors will not require any 
changes in applications currently written for the AS/400, and that the
AS/400 version of the PowerPC 620 may actually contain true AS/400 code
imbedded in the chip in the same fashion as 80486 microcode will be added
to the 615 version.

...The new AS/400's are expected to ship in early July, except for the new
input/output processor and a wireless local area network (LAN) adapter which
are due in September. Initial shipments of OS/400 Version 3 release 1 and
most software is planned for mid-August, with general availability midway
through the fourth quarter, according to IBM spokespersons. Client Access/400 
will be available for OS/2 1.3 and for DOS with extended memory in June, for 
Windows 3.1 in the fourth quarter, and for OS/2 2.1 in March of 1995.

...From the "Billie Gatesenfurghen Bork Bork Bork!" department: After
years of ignoring the critics over flaws in usability, Microsoft has signed 
an agreement with a Swedish company to provide testing of Windows-compatible
applications. Microsoft spokespersons say the testing, which will be based on
an established usability standard, will be done by Nomos Management AB, a
Stockholm company. Nomos will evaluate the usability of Windows-based
applications from independent software developers, consultants, and other
sources, as well as those produced in-house by Microsoft itself. 

...Microsoft already operates its own usability lab on its Redmond, Washington
campus. That lab was established in 1988, and puts Microsoft products through
usability testing throughout the entire development phase. However, most 
critics of this process cite the reluctance of Microsoft to drop the 
cumbersome Program Manager/File Manager separatism - which is further 
compounded by the vehement support of Bill Gates himself - as the prime
example of just how ineffective this lab is perceived to be. Other sources
claim that this lab was established not to test for compatibility, but to
test *intentional incompatibilities* between Microsoft Windows and certain
third-party programs. These same sources also claim that these accusations
do appear in certain documents filed by IBM, Lotus and WordPerfect with
the FTC during the investigations against Microsoft on violation of
Federal Anti-Trust regulations.

...Of course, there's other Microsoft shenannigans for the FTC to take note of.
For example, insiders report that when you install the latest beta version of 
Windows 4.0 on a machine that has OS/2 installed, you'll get the following
warning message: "Setup has detected OS/2 files on your system. Although you 
can install this version of Windows, these OS/2 files use considerable disk 
space. Exit Setup or Continue?' Many of you may recall that a similar message
in a beta version of Windows 3.1 complained if you were running DR DOS instead
of MS-DOS, and that one *was* cited by FTC insiders as one of the primary 
triggers of that agency's antitrust probe of Microsoft! 

...From both the "May the Pakistani Brothers Rot In Hell!" and the "Look
at My Thumb <POW!> Gee, You're Dumb..." departments: A new "Trojan Horse" 
computer virus has gotten loose on the Internet, and is considered one of
the most devious viruses identified to date.

...Disguised as a - are you sitting down? - "utility to turn certain Chinon
CD-ROM drives in to *writeable* CD-ROM burners", the trojan called CD-IT is 
in fact causes the computer to lock up, forcing a reboot. Thanks to some 
boot-sector tricks, the trojan then reloads itself into memory after the 
reboot, and then corrupts critical system files on the hard disk. After this,
nothing but a high-level reformat of the hard disk drive will eradicate the 
virus at this point, and we all know just what *that* means.

...Network admins are reportedly scared turdless over this trojan, as it 
will also corrupt any network volumes available. As of this writing, -none-
of the current releases of any antiviral software are equipped to detect,
eradicate, and/or repair damage caused by this trojan. Some are even calling
this "the Computer AIDS they warned us about!".

...Chinon, whose name has been associated with this mess simply because the 
trojan designer(s) decided to pick *them* as the victim, is encouraging anyone
who might have information that could lead to the arrest and prosecution of 
the parties responsible for CD-IT to call the company at 310-533-0274. No
word of a reward was mentioned, but if someone *does* read this and happens
to finger those responsible, be sure to suggest that they send the WWIVNews
editor a 6-drive CD-ROM array as a show of thanks :-)

...From the "Wayne Bell Memorial Award" department: After much talk, promises,
threats, begging, cajoling, and prayers to Roddenberry, Telix, the popular DOS 
PC communications package, is about to be released in a Windows version.
According to the company, Telix For Windows has several features which are 
unique to the world of Windows communications products. The package includes 
the RIPscrip graphics terminal emulation which allows users of many online 
systems to interact graphically, using icons, images, and graphics-based text.
Also included in the package's feature list are a graphics file (GIF) viewer, 
a phone book manager, support for network communications, upgraded versions of
SALT and SIMPLE, the two Telix script languages, as well as an integrated 
sound capacity to link Windows .WAV files with system events. 

...Existing users of Telix are being invited to order their Windows version 
now, although shipment won't be until June 15. In return they will be provided
with a beta version of the software immediately, making them part of a very 
widespread evaluation team for the package.

...From the "Looks like SCSI. Smells like SCSI. Must be SCSI. Burn it!"
department:  A new intelligent IDE controller for IBM-compatible PCs has been
announced by GSI. According to the company, the new controller will support
up to eight devices and has its own onboard BIOS to support not only the
additional drives, but the new IDE-2 (also called "Enhanced IDE") standard
as well.

...GSI claims that the Model 4C-V controller is designed as a direct 
competitor with SCSI market, and has four channels, adding "multi-channeling" 
capability with each channel supporting one pair of devices (one master, 
one slave). This multi-channel operation, GSI says, will allow network users 
under Novell Netware 4.01 to increase concurrent operations, making for faster
performance on both file servers and on desktop systems. Drive setup during 
installation is also automated, so users no longer need to know the number of 
heads, cylinders, and tracks a drive has in order to install it. Also, since 
the Model 4C-V has its own Flash BIOS it can support partitions larger than
the 528MB limit imposed by the BIOS built into some computers.

...The Model 4C-V comes with four IDE cables and a power supply cable for 
additional drive-power outlets. Retail price has been set at $179, but street 
prices from mail order companies have been closer to $139.

...From the "Up the Intelligencia!" department: Cyrix has signed a deal that 
gives IBM the right to manufacture Cyrix chips for its own use and to sell to 
other personal computer makers, as well as supplying them to Cyrix. IBM has 
been building 486 chips for Cyrix, of Richardson, Texas, since last September,
and the new deal covers not only Cyrix's 486-class processors but its upcoming 
M1 Pentium-class processor, a competitor to Intel's P-5...er.. Pentium that 
is expected to be released at Comdex/Fall '94.

...The inclusion of the M1 is especially significant in light of the fact that
IBM recently announced it would not exercise its option to extend an existing 
chip-making agreement with Intel to include the Pentium. Under the existing 
deal with Intel, IBM has the right to make Intel's chip designs for use in its
own hardware, and to create its own variations on Intel chip designs both for
its own use and for sale as part of board level products. However, they may
not sell individual chips, which is believed to be a key lynchpin behind
just exactly why IBM chose to sign a deal to manufacture Cyrix's M1 instead 
of Intel's Pentium.

...There has also been quite a bit of speculation in the industry that the 
decision not to extend the agreement with Intel was really centered on IBM's 
promotion of the PowerPC processor that it has co-developed with Motorola and
Apple as a competitor to the Pentium. However, IBM insiders say there were 
technical concerns involved. Besides the desire to secure the right to sell 
individual chips on the open market, the Pentium uses a bipolar complementary 
metal oxide semiconductor (BiCMOS) design that can't be manufactured with ease 
or in quantity under IBM's current manufacturing facilities. In addition, 
Cyrix had chosen IBM's half-micron CMOS technology for use in the M1, and 
one that was decided upon the agreement seemed to be the logical next step.

...Whatever the reason, in late June Intel filed a breach of contract suit
against IBM over their decision to use the Cyrix chips instead of the 
Pentiums. Intel claims that not only did the agreement that allows IBM to
use Intel's 486 design prevent them from selling individual chips, it also
prevents them from going anywhere else for compatible designs! IBM, naturally,
says this is a) a load of crap, and b) probably illegal infringment of free
trade. Industry insiders say that if Intel loses this one, it could possibly
put the final nail in the coffin for the company that was responsible for
the x86 architecture.

...From the "Plesalio" department: Meanwhile, IBM Japan is preparing to 
release a hybrid personal computer which has the proverbial "kitchen sink" 
array of functions and combines a personal computer and various multimedia 
devices. An IBM Japan spokesman claimed that this "computer appliance" will 
be officially announced in July, and will be marketed in the US prior to
Comdex/Fall '95. 

...IBM Japan's hybrid personal computer will be based around its multimedia 
personal computer, the PS/V Vision. It is expected to include a regular TV 
tuner, a CD player, a telephone, a fax machine, and a game machine. The
unit price of this new PC is the source of speculation but it is likely that 
it will be about the same as the PS/V Vision, which is 300,000 yen, or
$3,000, depending on how far the dollar drops by the time Wayne sends this 
issue over the network!

...From the "Cheap-Deal ROM" department: TEAC America is shipping a quadruple
speed (4X) CD-ROM drive for only $399 in July. NEC, one of the few vendors 
that has offered a 4X drive, has followed suit by dropping their prices to
$399 as well. Previously, NEC had charged a whopping $995 for its product. 
The TEAC drive will have the same 600-kilobytes-per-second (K/sec) 4X
transfer rate as the NEC drives, plus a faster access time of 195ms. Industry
experts now expect the 3X standard to die a quick death, and that consumers 
will see a wave of 4X products in the fall. Plextor has already announced 
plans offer a 4X product in late July, although pricing was not mentioned.

...From the "Final Frontier" department: Spectrum HoloByte has signed an 
agreement with Paramount Pictures to produce a new line of interactive 
software products based "Star Trek", including the upcoming release of the 
movie "Star Trek - Generations." 

...This agreement is in addition to Spectrum's original licensing contract to
develop titles on certain platforms for all the "Star Trek" television series
and is applicable through 1998. The agreement outlines a multiplatform deal 
which will authorize Spectrum HoloByte to develop games for all significant 
16- and 32-bit platforms, to include 16-bit video game platforms, 32- and 
64-bit game consoles, 3DO, IBM and Macintosh CD-ROM and disk-based products. 

...Insiders at SHB report that in addition to the "Generations" games, a
"Deep Space Nine" game, as well as a "real-time warp flight simulator" game 
are in development for release in 1995. Pricing was not available at press
time, but is expected to be the same as that for SHB's previous "Trek"
games.

...From the "More Eggs, Different Basket" department: At Systems Support Expo
in Boston, Microsoft unveiled a CD-ROM disk that includes drivers for the 
entire line of Microsoft software products, code samples, articles, and 
utilities, along with the latest patches for Windows NT. The new "Microsoft 
TechNet Supplemental (Drivers & Patches) CD", which contains a total of some
1000 drivers, is scheduled to be bundled with the latest edition of the 
TechNet CD that is supplied to Microsoft TechNet subscribers.

...Both discs are the first CD-ROMs from Microsoft to be offered with
unlimited user licenses, and also provide the first generally-complete 
collection of official patches for Windows NT to be available on CD-ROM. 
The disc is the first of a series of supplemental monthly CDs that will be 
sent to Microsoft Technet subscribers, and future supplemental discs in the 
series will include patches for LAN Manager and Windows for Workgroups.

...The blood money Microsoft is asking isn't pint-sized for most of us. For
12 monthly issues of "TechNet" and "TechNet Supplemental (Drivers and Patches)
CDs", $295 gets you a single user license, while $695 set you up for a single 
server, unlimited users license. Nope, no word on whether Microsoft considers
distribution of the contents on the Drivers and Patches disk a breach of 
copyright.

...From the "We *Told* You So!" department: Dell's having a fire sale these
days, what with the US Consumer Product Safety Commission forcing them to
"voluntarily" recall over 63,000 Royal-made OEM color monitors due to the 
high possibility of them catching fire with extensive use. 

...The reason the monitors were recalled went like this: Following complaints
filed with the CPSC, that august body determined that faulty and below-
tolerance internal components in the Royal monitors can overheat and cause 
a fire. Prior to the CPSC ruling, 132 users reported overheating and in 47 
of those instances the monitors have caught fire. After the recall was started,
these figures were lated found to have been roughly three times higher in
actuality due to unreported cases. 

...Dell, still stinging from their notebook and stock value fiascos, has
attempted to make rather light of the issue. A Dell spokesperson says that
no injuries resulted from any of the monitors that overheated, and the fires
did not spread beyond the monitor. Other spokespersons assured TechNOTEs that
the use of the word "fire" was a gross exaggeration on the part of the CPSC,
and that the situation as more of a "pungent meltdown".

...For those who got suckered into buying proprietary Dell systems, you only
need to be concerned if you happen to own one of the Model DL-1460NI 14-inch 
Super VGA color monitors. These units were sold direct by Dell and through 
Sam's Club, Costco, Price Club, and CompUSA. Users can determine the model 
of the monitor by checking the identification plate located on the rear of 
the unit. The model number is found in the upper left corner of the ID plate. 

...If you happen to have this monitor in use, unless you've got a 
fully-charged, ABC-rated fire extinguisher handy beside the PC, Dell stresses
that you should immediately unplug the monitor and contact them at 800-913-3355
between the hours of 9AM and 9PM ET, Monday through Friday (11AM to 3PM ET on
Saturday) for an RMA number. The company will send packing materials via 
overnight service, and Airborne Express will pick up the monitors for return 
to Dell. Dell tech support claims that the turnaround time for the repair is
expected to be 3-5 working days, but reports claim this is in actuality as 
long as two weeks. Also, the monitors can only be repaired - Dell will not
exchange the monitors for new and/or already repaired ones, much to the 
chagrin of many an angry customer.

...Speaking of Dell, this side nOTE comes from one Austin, Tx computer 
dealer: "Seems the other day we got a request for a system quote from the
American Atheist Center. Our boss is a really devout Christian, and is 
probably one of the nicest, politest people I've ever worked for. However,
when I told him about the quote and who was asking for it, his response
was 'tell them I said they can go to Dell!' Needless to say, this floored
the entire office for hours!"

...From the "Great White North" department: Word from WWIVNetters in Canada
tell of the demise of Canada's principal computer show. The Canadian Computer
Show would have celebrated its 25th anniversary this fall, and according to
those who've talked to Ross Horton, manager of computer shows for Industrial 
Trade and Consumer Shows (ITCS) in Toronto, "the computer industry just was 
not showing enough interest in the Toronto-based show this year, and ITCS 
decided it would be better to make the decision [to cancel the show] now." 

...ITCS runs seven regional computer shows in cities across Canada, and 
according to Horton, plans to continue doing so. He also added that the 
company hopes "...to return to the Toronto market sometime in 1995 with a 
new show, but we've got no detailed plans to discuss at this time." 
...While orton also blamed a weak economy and increased competition for the 
show's demise, a major factor was undoubtedly the launch last year of 
Comdex/Canada, a spinoff of that debaucherous event held each fall in Las 
Vegas and repentantly each spring in Atlanta, and may be spinning off to a 
summer event in Dallas starting in 1996. Last fall's edition of the Canadian 
Computer Show was smaller than it had been in some years, with booths for 
about 200 exhibitors filled out of the 500 alotted. Many industry experts 
speculated at the time that the new competition posed by Comdex/Canada might
actually kill any chances of future shows based on the apparent lack of
local interest.

...Two VAR's on WWIVNet - MicroSource in Austin, Tx, and Dale's Dataexperts 
in Los Angeles, had the same thing to say insofar as to why those who sell 
computers prefer Media Vision over Creative Labs. "The only reason that 
everyone wants Sound Blasters has nothing to do with how good they are, its 
because on every game box the words 'Sound Blaster support included' are 
printed in big bold letters. Media Vision's ProAudio line has far better 
versatility than CL's overhyped junk, cause less problems with regards to
incompatibilities, and actually cost less when you get down to it. Hell, they
even work right with OS/2!"

...From the "Andy Warhol Memorial 15 Minutes of Fame" department: Ziff-Davis,
publisher of ad-rags such as _PC Magazine_, _PC Week_, and _Computer Shopper_,
has announced plans to produce two half-hour weekly shows for Technology 
Information Network (TechTV). In what most are calling a totally expected
move, considering who's producing the weekly shows, Tech TV plans to pair the 
two Ziff shows with several half-hour and hour-long computer-related 
infomercials. 

...Starting in August, two one-hour packages will be broadcast on weekend 
afternoons as paid programming on CNBC. The half-hour infomercial segments 
will follow the Ziff-produced shows, and will contain material provided by 
manufacturers and designed to sell their products. While TechTV will be paying
for the time on CNBC, the two Ziff-Davis segments will reportedly not be 
infomercials, which will be interrupted by commercial breaks as in normal
television. Ziff-Davis said its productions, "PC Update" and "The Personal
Computing Show", will reportedly feature segments hosted by computer industry
experts, including editors and columnists from Ziff publications and personnel
from its product testing laboratories. "The Personal Computing Show", on 
Saturdays, will demonstrate the use of personal computer products, while
"PC Update", on Sundays, will be a newsmagazine focusing on trends and on 
new technologies and products. The infomercials, which will follow the
Ziff-Davis productions, will follow time-honored traditions of hype and
tackyness, and will of course allow viewers to order products through a 
toll-free telephone number. 

...The laugher of all this is the report that Ziff will retain control of 
editorial content for their programs, and has reportedly even reserved the 
right to lambast the accompanying infomercials if they see fit! Ziff-Davis
condemning an advertiser in front of millions of couch potatoes? Yeah, right
pal, pull the *other* leg next time.

...From the "Frisbees Don't Fly High Forever" department: TEAC America has
thrown down the first gauntlet in what's expected to be the start of a major
price war in the CD ROM market. In June, TEAC began shipping a quadruple-speed
(4X) CD-ROM drive for $399, which is $600 below comparable drives offered by
NEC, Sony and Plextor. The TEAC drive will have the 600-kilobytes-per-second
quadruple-speed transfer rate, plus a zippy access time of 195 milliseconds.

...As a result, NEC immediately dropped the price of their 4X internal drive
to the same price as the TEAC 4X, and Plextor is reportedly following suit
in July with the official release of their own 4X drive. Industry experts
cite this as being only the first battle in a major price war over the 
CD-ROM market, and will most likely result in a price drop for 2X drives
to under $100, and a probable extinction of the 3X drives which failed to
offer sufficient enough of a performance boost over 2X drives to justify
the almost double cost.

...Meanwhile, over in those Creative Labs, the Sound Blaster people have 
reached a settlement with Prometheus Products and Computer Peripherals in 
the false advertising suit brought against the companies. In the announced 
settlement, Prometheus, producer of Aria audio cards, agreed to change its 
packaging and will no longer advertise its products as "Sound Blaster 
Compatible." Computer Peripherals, also sued for false advertising, will 
"black out" all claims of compatibility with the established "standard". 
Both companies, however, have stated that they will instead refer to their
products as having "Sound Blaster emulation" capabilities.

...Creative Labs also announced the continuation of the same false advertising
claim against Cardinal Technologies, as a Federal District Court in San 
Francisco granted a preliminary injunction against Cardinal. The judge ruled 
that Cardinal must either "block out" the reference  to "Sound Blaster 
Compatibility" on its packages, reprint its boxes to delete the claim, or 
upgrade the packaged units. 

...The curious point of order in this case is that according to Creative Labs,
Cardinal achieved the standards of compatibility in March of 1994, and any 
cards issued after that date are not affected by the suit. In the suit, 
Creative is asking that Cardinal effect changes to those cards produced prior
to the compliance, and that it is seeking this and other court injunctions 
"preserve the standards that have been established as 'Sound Blaster 
Compatible." Currently, both IBM and Media Vision have been licensed by 
Creative as having this capability and the right to advertise as such. 

...In other words, folks, Creative Labs wants the cows to go through USDA
approval after they've been branded, slaughtered, cooked, served and eaten.
Real swift thinking there, eh?

...Comdex/Spring '94 has come and gone, and WWIVNews had a few informants
taking notes of what was hot. This time, Personal OS/2 from IBM was the show
stealer, and managed to get named 'Best of Show' in both BYTE magazine and
The Interface Group's "Best of COMDEX/Spring and Windows World '94" awards 
ceremony. Needless to say, it was also the choice of those WWIVNews 
representatives as *the* package to watch for with regards to putting Chicago
in its place. Still six months away from official release, Personal OS/2 will 
be a tighter, 4 MB version of OS/2 for Windows, will include some badly-needed
complete support for Windows for Workgroups 3.11, and offer an easier 
installation while offering better stability than Windows 3.1. 
...The Most Significant Technology award was given to OLE Custom Controls 
from the Gates Boys at Microsoft. OCC merges the benefits of Visual Basic
Exchange with OLE 2.0, giving Windows programmers easier and more versatile
access to both VBX and OLE facilities. Other finalists in this category
included DEC's 150MHz Alpha at 33 Mhz, and Kurzweil Voice for Windows, a 
voice recognition system from Kurzweil Applied Intelligence Inc., the same
folks who first brought you somewhat reliable OCR. WWIVNews reporters chose
this program over the others as being of "more significance than a set of
custom controls for a GUI that shouldn't be so damn hard to program for in
the first place!"

...The "Best Rookie" award was presented to the top first-time exhibitor 
with a product that shows outstanding potential. This time, the award went to
Medio Multimedia for "Medio Magazine", a magazine on CD-ROM which integrates 
full-motion video, audio, text and graphics with current news stories, 
entertainment, reviews, sports and childrens' materials. Those viewing the
demos of this product reportedly support the awarding in this case, and 
claim that "this disk is sort of like a family version of 'Entertainment
Tonight', without having to put up with the ignorance of Mary Hart!'

...In the Multimedia Software Category, "Elastic Realty" by Elastic
Realty Inc. took this show's award. The program, a morphing and special 
effects software for Windows, features warping, layering and matting 
capabilities. Other finalists in the category were MediaShop for Windows, a
multimedia production, integration and authoring package from Motion Works,
and Razor, a professional digital video editing package for Windows from 
in:sync corporation.

...The award for best in Multimedia Hardware went to "Video Machine Lite", a 
video editing system which allows users to add complex digital video
effects in real time video. MediaPlayback PC and Macintosh, computer 
expansion boards and software from International Interactive Media, and the
WWIVNews-preferred MGA Impression Plus 64-bit graphics accelerator from 
Matrox Electronic Systems Ltd. were named finalists.

...Over in the Best New Portable category, Apple Computers' new line of
PowerBooks, the 500 Series were named winners based on their perceived high
performance and supposed low cost. However, most WWIVNews reps at the show
felt that this was probably more "under the table paid lip service", as
several of the demo units reportedly could not stand up to the amount of
use and abuse they received at the hands of show attendees. Runners-up in 
this category were Z-Noteflex, a modular notebook computer system from 
Zenith Data Systems, and the WWIVNews-preferred IBM ThinkPad 755 family of 
notebooks, also with interchangeable modules and the "nipple".

...The Best System Category award went to TD-4 Personal Workstations from 
Intergraph Corporation, which feature dual 90 Mhz Pentium processors and G91
graphics acceleration with an optional 3D GLZ graphics engine. Finalists in 
the category were the WWIVNews reps' choice and the WWIVNews Editor's wetdream
machine, the Revolution Q-SMP Symmetrical Multiprocessor system from Advanced 
Logic Research Inc., and the MACH 1-166, an entry-level Alpha system from 
NEKOTech, a division of Inventory Conversion Inc.

...In the Best Peripherals Category, Imagine-128, a 128-bit graphics and
multimedia processor from Number Nine Computer Corporation was named winner. 
Finalists in the category were ViewSonic 17 Monitor OnView from ViewSonic and 
SmartRAID, a full 'RAID-ready' storage solution from DPT. The WWIVNews reps'
award went to ADI's 4GLR, a 15" NI SVGA monitor whose flat screen actually
puts NEC's 4FGX to shame.

...Over in the Best Printer arena, for reasons unfathomable Epson's Stylus 
Color ink-jet printer was named the winner. Finalists in the category were the
LaserJet 4 Plus and 4M Plus from Hewlett-Packard, which also won the WWIVNews
reps' choice award, and Fargo Electronics Inc.'s PrimeraPro Color Printer, 
which the WWIVNews Editor is attempting to purchase for $795 as part of the
dealer incentive program. 

...In the Best Software Category, Lotus Forms Version 1.0 electronic-forms 
software for designing, routing and tracking forms took the award despite
the fact that integration with Lotus Notes was flawed and incomplete as
demonstrated at the show. The finalists in the category were XRES, a
painting/editing system for large, high-resolution images, from Fauve Software
and Ca$HGRAF, a financial management package designed for small to mid size 
businesses, from Target Software Group Inc.

...In the System/Development Software Category, Personal OS/2, winner of
Best In Show, took this award as well. Other finalists were Microsoft's 
Windows NT Workstation, which was another example of "under the table paid
lip service", and WinG, which actually deserved recognition due to its
ability to render fast, smooth game graphic animation in Windows 3.1, Chicago,
and Windows NT, despite the fact that it was also from Microsoft.

...The Best in New Communications award went to Scanfix, a multipurpose 
desktop scanner that brings low-cost color faxing to the desktop, which 
ironically came from from Plustek USA Inc., notorious for producing the 
shoddiest scanners this side of the shoddier *and* overpriced scanners from 
Umax. Finalists in this category were the CommCard, a high-speed, wireless 
fax/modem with data and voice capabilities from Open Sky, and Connection Pro,
a DSP-based fax/voice modem with business audio and digital voice messaging, 
from Digicom Systems

...In the normally Novell-dominated Networking category, CorStream server, a 
dedicated server for the LANtastic network operating system from Artisoft 
Inc., was named this show's winner. Other finalists in the category were 
SkyLAN local talk wireless LAN from S&T Co. Ltd and Ben IIO, a 16-bit ISA
Ethernet bus adapter, from Boca Research Inc. 

...While Personal OS/2 reportedly stole the show at Comdex/Spring '94, the
program that everyone was *really* talking about was 7th Level's Monty Python 
CD-ROM, titled "The Secret to Intergalactic Success." In true Python fashion,
the debut of the program was riddled with all sorts of comical difficulties.

...The reported technical difficulties, it should be noted, had nothing to do
with the title. The microphones in the hotel room 7th Level had rented simply 
did not work. This 16-ton weight was dodged by some last-minute adlibbing by
Charles Fleischer, better known as the voice of "Roger Rabbit", who'll be
the target of 7th Level's upcoming "Virgil Reality" title. This, in turn, let
to Fleischer, who will soon have a column in "PC Computing" magazine, being
dubbed "the seventh Python."

...According to those attending the demonstration, the game is not just a 
group of clips thrown together to enhance a simple arcade game, but a diverse
collection of classic and original clips combined in a complex puzzle. 7th
Level will also be sponsoring a contest, with the first person to figure out
the "secret to intergalactic success" winnig themselves $5,000 or a high-end 
computer. 

...In true Python fashion - or Catch 22, depending on how Amerocentric you
choose to be - it will take a high-end computer to run this title in order
to attempt to beat the game and possibly win a high-level computer. 7th Level
recommends a 486-based machine with Windows 3.1, MPC II accessories, and a 
double-speed CD-ROM drive are recommended. 

...From the "Different Eggs, Basket Full of Holes" department: April saw yet
another strange twist in the software industry when Symantec announced an 
agreeement to merge with Central Point Software. Executives at the two 
companies say the merger is intended to promote the development and marketing 
of "enterprise'' software for networked environments. Symantec, which markets 
several enterprise software products, including Norton Administrator for 
Networks, Norton AntiVirus for NetWare and Norton Utilities Administrator, 
and Central Point, which markets enterprise software products including 
Central Point Anti-Virus for NetWare, XTree Tools for Networks and LANlord, 
made a joint announcement of the merger on April 4. 

...When asked, spokespersons for both companies replied through April that
the companies had merged. However, when May rolled around, Symantec reps
were saying off-the-record - yeah, *right* - that they had bought Central
Point outright, while CP reps were still talking merger. By the first of
June, both sides were beginning to make off-the-record comments to the
effect that the merger *might* not take place as announced. At press time
no official changes to the status of the merger had been announced, and
both sides are now mum on the matter.

...From the "Same Basket, Rotten Eggs" department: As if there weren't enough 
flavors of CPU to keep track of, Intel released the SX2 in June. The SX2, a 
speed-doubled SX processor, promises to turn your 25MHz 486SX system into a 
486SX2/50 system. According to Intel spokepersons, the SX2 offers end users 
30 percent more performance than the standard Intel 486SX, but is *not* the
long-awaited "Overdrive" chip. The processor is priced at $189 in the U.S. 
in quantities of 1,000 and is compatible with standard DX2 processor pinouts.

...So, where *is* that "Overdrive" chip we've been promised since day one?
Well, you might not have recognized it, but it's the IntelDX4. The IntelDX4
was, according to several Intel insiders, originally planned to be released
as the "Overdrive" chip for the 486DX series of Intel processors. However,
with Intel's losses to Cyrix and AMD of late, the plan now is to attempt to
hold onto the 486 market long enough to get the 32-bit Pentium Overdrive
chip perfected enough to sell to those of us who bought systems with P24T
ZIF sockets before Cyrix and AMD can gain any further toeholds into the
market.

...Granted, Pentium is the way Intel is heading, but even they realize that
the "upstarts" got their leverage by capitalizing on the user base that could
not afford to upgrade to the latest and the greatest in CPU power, and milked
them for all this rather potent cash cow could supply! Now, Intel has to
attempt to maintain the path to the future, but recapture the past as well
if they're going to survive. In light of the Cyrix and AMD deals with IBM,
the failure of Intel's agreement with IBM, and the even slight threat of
the dual chipset Nx586 from NextGen, Intel has no choice but to keep the 
support promises they thought the Pentium would have bailed them out of.

...From the "Bust the Trust" department: Fujitsu has joined the movement to
establish the Microsoft Windows Application Programming Interface (MAPI) as 
an open, published standard. Microsoft, naturally, opposes this move as it -
by their lawyers' reckoning - would take Bill Gates' #2 cash cow and set
it loose on the public domain pasture, resulting in dozens of shareware 
and commercial clones of Windows, and turning the DOS/Windows world into the
same sort of chaos that the Unix geeks seem to thrive on as much as they do
on the cold pizza they sleep with. 

...This Public Windows Interface movement includes numerous movers and shakers
in the industry, including Amdahl, Borland, Corel, Hewlett-Packard, IBM, 
Oracle, The Santa Cruz Operation, Sun Microsystems, WordPerfect and - oddly
enough - Novell's UNIX Systems Group, which recently announced plans to 
support the move to make Unix itself part of the public domain.

...From the "Better late than never" department: IBM took its sweet time 
getting its PS/2 Premium 56 and 57 systems out the door. Now, after an
expectedly lengthy wait, Big Blue has finally started shipping updated 
versions of these systems, featuring increased processor performance and 
better graphics. 
 
...Both models use the 25/75 486SLC3 ship, better known as the "Blue 
Lightning", IBM's internally developed 32-bit processor. The chip features
16KB of on-chip cache and improves processor-intensive, non-floating-point 
application performance anywhere from 40 percent to 424 percent, depending 
on which of the older models it's replacing and which hype you choose
to believe. Graphics, on the other hand, are based on XGA2, a faster, less 
expensive version of XGA. This makes this "new" standard - if you can believe 
it - a cheaper form of 8514 which ironically isn't supported yet by OS/2!

...Those who already own the original release of the 56 or the 57 can upgrade
to the new processors with a Processor Upgrade Card for the cheap-by-IBM-
standards price of $535. This upgrade works in the older PS/2 56 and 57 SX, 
SLC and SLC2 models. 
 
...From the "GraspRT Wetdream" department: Fast Forward Video, manufacturers 
of the Digital Video Recorder "Bandit", are offering their flagship product 
($5995 plus storage - best take out those loans *now* while interest rates
are a little lower...) with several significant newly implemented features. 
Bandit, a peripheral device which originally transferred and recorded images 
to a 32mb RAM module allowing 20 seconds of video to be played back in real 
time, is now capable of recording direct to a SCSI hard disk.
 
...The new version uses fast SCSI-2 storage for the simple fact that you can
daisy-chain up to six drives - or so the theory goes -  to achieve over 2 
hours of recording time. In addition, since the recording drive subsystem is 
dedicated to an onboard JPEG compression card, the data never has to pass over
the bottlenected computer bus, allowing full screen video at 60 fields per 
second with as little as 5:1 compression. 
 
...Prior versions of the Bandit also had another limitation that no longer
exists. Until now, the unit has only been available with composite ins and 
outs, which is not acceptable to the broadcast and professional users. To
meet the demand, YUV and S-Video jacks have been added to the options that
are available. This allows producers and editors to maximizing their image 
quality and record broadcast images directly to VTRs they are using, such
as Betacam SP, BPI-31XX, and U-Matic. 

...WWIVNews readers are encouraged to let us know when Rusty & Edie manage
to purchase one of these. If this happens, don't be surprised to see Rusty
suddenly showing up as having been the star of "Devil in Miss Jones"!
 
...From the "Slot Machine" department: Ok, we've all run out of slots in
our machines on occasion, especially when we throw in a video card, a TV
board, a sound card, a multi I/O IDE controller, a SCSI controller, a
modem or two, and a network card, and we've thrown it in a case whose
hard drive bay gets right in the way of the long cards! It's enough to
make you want to scream, right?
 
...Well, there's a bit of hope for people like us. Ultralink offers a simple 
but sophisticated ISA bus expansion system is now available for users of 
laptops, Microchannel and other non-ISA personal computer platforms to use the
wide range of data acquisition, control and peripheral I/O cards available for
the ISA bus. PC users who are out of motherboard expansion slots now have the 
ability to expand economically and without disturbing existing system 
configurations. 
 
...The Ultralink Model 120 consists of a single PC card and cable which 
connect a passive ISA backplane to a host PC's parallel printer port. Up to 
16 ISA I/O cards can be installed in the passive backplane. The unit operates
with Centronics compatible and enhanced parallel printer adapters at data 
rates up to 100K bytes per second, and both 8 and 16 bit ISA I/O data 
transfers are supported. The 'Link also incorporates logic which expands 
address space and interrupt levels available on the expansion backplane. 
 
...Another feature offered by the 'Link is a concept that's foreign to most
PC users - hotswapping. This feature allows insertion or removal of cards 
from the expansion backplane without shutdown or opening of the PC. In 
addition, the expansion backplane is only active during data transfers with 
resident I/O cards, reducing backplane electrical noise for sensitive data 
acquisition applications. 
 
...Now, if all this sounds familiar, keep in mind that IBM once had an
"expansion chassis" for the original XT's that used another XT chassis
as a semipassive backplane. That unit, however, didn't support even 1/4th
of the peripheral cards on the market at that time, and you couldn't put
any hard drives in it either! Those interested in the Link should be prepared
to shell out an MSRP of $159, not to mention a case of some sort to hold
the unit. 
...From the "Jocko Homo" department: Sick of Flying Toasters? Want something
a bit more <snicker> "sensual"? Well, romance-novel cover boy Fabio has a 
screen saver of his own now, and it can be yours for a mere $29.95! That's
right, you too can have 17 images of the fab Fabio plastered all over your 
computer screen for all your secretaries to gawk at. For those who need 
something with more "meat" on their screens, the Fabio Screen Saver and 
Wallpaper for Windows from GT Interactive is expected to appeal to millions 
of female and not-so-female PC users nationwide. 

...According to the company's vice president of marketing, Allan Blum, "Fabio
is one of the most recognized romance figures in the world." Guess that 
depends on who's looking. Of course, if they *really* wanted to do a screen 
saver of someone gracing the cover of a paperback, Doc Savage would have 
probably been a better choice. If anything, he'd have been far more real!

...Ten years after the first PC hit the market, we're now finally coming to
realize just how important it is to keep your system internals as cool as
possible. While some systems can get by on just having a cooling fan on the
CPU and the power supply, others have found that using a fan card is a far
better solution to the heat problem.

...However, there's one problem - the damn things take up a slot and all
they do is move air! T. S. MicroTech, maker of what's still the only patented
internal cooling fan for PCs, has realized this fact, and has released a new 
version of its FanCard that pulls double-duty by supplying I/O for both air
*and* data. The FanCard/Combo uses the same two bidirectional fans as the 
original versions, but this time they've placed on a multi-I/O card. The 
new Combo allows for maximum cooling for your machine while providing a full
complement of I/O ports.

..."But wait! There's more!" Ronco aside, the FanCard/Combo also has an 
optional 6v connector, which will power most multimedia speakers, as well
as two serial ports, one parallel port, and one game port. All ports can be 
enabled or disabled individually, and the controller supports up to two IDE
hard disks and two floppy drives, all of which are also disableable. 

...There's two drawbacks to this card, however: There isn't a Local Bus 
version yet - the Combo is an ISA bus card only - and with this in mind the
MSRP of $95 seems quite a bit steep for those of us who need a VLB version.
TSM is reportedly working on a such a card, but had no release date at
press time.

...From the "Open Sesame" department: Last May, Texas Instruments announced
its participation in the development of an industry standard model for printer
management, for implementation in desktop, local area, and wide area network 
printers. The idea is to establish a standard database to describe and manage
printer functions that will allow application and systems developers to 
actually develop standard printer management and control software. Such a 
standard, TI reps claim, "will ultimately free the user from dealing with 
the myriad technical details associated with setting up and controlling 
printers." Now, if only they could get their damn MicroWriters to quit 
hanging systems sporadically after a reboot!

...Speaking of Parallel Processing, Motorola spokespersons are hyping a lot
about a line of parallel processing, supercomputing-class hardware 
accelerators being developed by a Canadian company will utilize Motorola's 
PowerPC 601 microprocessor. ISG Technologies, based in Toronto, Canada will 
reportedly produce a line of symmetrical multi-processing (SMP) hardware 
accelerators scheduled to ship in the fourth quarter. The accellerators
will be marketed under the "Pulsus" line.

...ISG Technologies specializes in the development and manufacture of visual
data processing applications and imaging systems. A company spokesperson says
"Pulsus is designed and optimized for visual data processing and is best 
suited for systems where there are computation and visualization intensive
requirements such as medical imaging. The ability to do both the computing 
and the visualization on a single platform results in lower development and
maintenance cost, faster system response and less resource management at the 
system level. This technology is therefore well suited for applications such 
as three-dimensional (3-D) seismology as well as medical imaging". 

...The entry-level Pulsus, with eight processors, delivers about five times 
the performance of the typical midrange RISC workstation, according to the 
company's latest hype sheets. Pulsus uses Posix Parallel Threads, allowing 
compiled applications to be run on Pulsus or other workstations using a single
CPU (central processing unit) or an SMP architecture. 

...For those still in the dark about the stats on the PowerPC 601, this new
RISC-based superchip uses 2.8 million transistors and is manufactured using a 
.6 micro CMOS process. The chip includes an advanced bus interface that can
support a range of computer systems from handheld, portable and desktop 
computers to midrange workstations and servers. 

...From the "Bonsai Floppy" department: Hitachi has developed a powerful
Mini-Disk that stores a whopping 100 times more data than regular Mini-Disks.
Hitachi also reports that the new medium is targeted towards storing motion 
picture data, including entire TV programs. 

...The Mini-Disk technology was originally developed by Sony, and many
electronics firms including Matsushita and Sanyo have been selling Mini-Disk
-based products for several years. Hitachi's latest twist on Mini-Disk 
technology was developed by improving the method with which data is written to
the disk. Optical fiber material is used instead of a lens. The optical fiber 
enables data to be written by an extremely narrow laser with a wavelength of 
0.07 micron, or about a 10th the size of the laser applied on a regular 
Mini-Disk. Hitachi has applied what it calls "the tunnel effect" of lights in
combination with this optical fiber material, and claims it is possible to 
further increase the amount of data stored to about 1,000 times higher by 
applying even narrower optical fiber material. 

...Hitachi spokespersons have not specified how long it will take for this
technology to reach the market, nor did they have any clues as to what the 
initial consumer costs would be like. 

...From the "Daddy Was a Philanthropic Cheapskate!" department: Microsoft 
Chairman Bill Gates says eventually he will give away most of his wealth, 
leaving about $10 million to any children he might have. 

...Gates, 38 and nowhere near death barring another Doublespace fiasco, is
considered the second wealthiest American, with a net worth of about $6 
billion. Gates, however, is quick to point out that his fortune is mostly 
on paper. "Outside of what's in my wallet, I really don't *own* any dollars.
I just own Microsoft stock, so it's only through multiplication that you 
convert what I own into some scary number!" 

...Since late April, Gates and other Microsoft officers have sold millions of
shares of Microsoft stock. That includes 1.12 million shares that brought 
Gates over $93 million. As one would expect, Microsoft officials frequently
decline all requests for information about the sale of stock by its officers,
which has helped share prices to fluctuate from a low of 41-1/2 in mid-April 
to 57-3/4 in mid-June. 

...As for what someone does when you have everything and you can't take it
with you because you havn't bought the technology to do so, Gates said when 
he divests himself of much of his wealth it will go to charities and 
scientific groups. Proof of this plan was first seen in November 1991, when
Gates personally donated $12 million to the University of Washington School
of Medicine to create a Department of Molecular Biotechnology. Old timers
will recall that this move caused speculation that Gates was really attempting
to buy in early on nanotechnology! In August of 1991, Wild Bill donated $1 
million to the Seattle-based Fred Hutchinson Cancer Research Center, and a 
year later gave $6 million to Stanford University to help the school complete
its new Information Sciences building. Neither of these donations, however,
sparked any wild rumors about Gates having the Big C and/or starting up his 
own online information service.

...As for the future, Gates says he will continue to run Microsoft for another
decade, then step aside to let a younger person run the day-to-day activities 
of the giant software company. Gates also says he tries to make his life as 
normal as possible, flying coach class when he travels, and eating at 
McDonald's more than most people. 

...Well, there you have it, folks. Proof positive that Doublespace was the
result of the hallucinogenic effects of those damn McRibs!

...From the "Orkin Man" department: Tests conducted at Lone Star Evaluation 
Labs (LSEL) in Georgetown, Texas have discovered a potentially serious bug in
the Cx486DX, Cyrix Corp.'s 486DX-compatible chip. The bug affects the chip's 
built-in floating point unit, and can cause unpredictable results in 32-bit 
applications created for OS/2 or Windows NT. It is less likely - but still
possible - for these results to occur in certain math-intensive DOS and 
Windows applications.

...LSEL's tests were designed to check the compatibility of the Cyrix and AMD
parts with the Intel 486. Cyrix's 486DX chip gave erroneous results in quite
a few tests of 32-bit floating-point code, but found none in the AMD versions. 

...Following the initial report - which was plastered all over the wire
services in big bold letters - Cyrix initiated fixes to the chip design to 
correct the problems, and reported that all chips manufactured after late 
March would incorporate the fix. The company has been shipping the Cx486DX 
since October 1993, and all units shipped since then have the bug. However,
Cyrix has reportedly shipped less than 10,000 of the buggy chips, and 
vendors have been notified of the problem so they can adjust their stocks
accordingly. The bug does not occur, it should be noted, with Cyrix's other
CPU and FPU products, such as the Cx486SLC/DLC, Cx486SRx2/DRx2, or FasMath 
83D87 chips.

...Owners of PCs that use the Cx486DX can call Cyrix at 800-462-9749 to see 
if their chips are affected. Cyrix can identify the faulty chips based on 
the date code marked on the top of the chip, but you will need to open up 
the PC and copy these numbers down before making the call.

...Cyrix engineers determined the bug is caused by an improperly-executing 
two-instruction sequence that can cause many types of program failures when 
it occurs. It is also believed that the bug would not occur with DOS or 
standard Windows applications because most 16-bit compilers (used to build 
the DOS and Windows applications) do not generate this code sequence. 

...This means that although the error can occur in DOS and Windows, the
users at highest risk are indeed those who use the Cx486DX with native 32-bit
apps in Windows NT or OS/2. Compilers used to build 32-bit applications for 
these environments are more likely to use the improperly executing instruction
sequence.

...Sound familiar? It should, because the original 386-12's had an almost
identical problem with their math segments. While not confirmed at press time,
an insider close to LSEL says that one of the tests failed was, in fact,
the computational accuracy of Pi. On the old 386-12's, after a specified
number of iterations, Pi *repeated* itself, which mathematicians all claim
is impossible! If this is actually one of the tests that the Cyrix chips
failed, then one must wonder just what revision of the 386 instruction set
was used to make these hybrid chips in the first place!

...From the "Old Dog, New Tricks" department: In 1992, Borland first 
demonstrated dBASE for Windows. Shortly afterwards, the product was put on
an indefinate hold while the product was retooled around its then-new
Interbase engine technology.

...The delay, however, stretched longer than anyone expected. In fact, the
release date of dBASE for Windows became almost as much the brunt of jokes
as Microsoft's "Chicago". Borland has even abandoned trying to guess as to 
a shiping date, much less a "final" beta. "No more promises. We'll ship when 
the product is damn good and ready!" claimed a Borland official who spoke
over the phone to a WWIVNews inquiry.

...Despite refusals to discuss possible ship dates, Borland has demonstrated
a pre-beta version of dBASE for Windows to selected customers and the press.
The dBASE it has shown isn't the same product Borland demonstrated over two 
years ago, though. That product, it turns out, was scrapped and replaced with
a totally redesigned version that like a cross between Quattro Pro - now 
owned by WordPerfect, by the way -  and Paradox. Most of this is due to the
fact that dBASE for Windows shares their query-by-example engines and table 
manipulation dialogs. Adding to the mix are several features from WordTech 
System's Arago, which Borland bought back in December 1992, And some strange
attempt at backwards compatibility with the DOS versions of dBASE, right down
to the good old idiot-confusing dot prompt.

...Of course, that good old idiot-confusing dot prompt is in a Window box,
which takes a little getting used to. However, this does allow all your old
dBASE code to be 100% compatible with the new version - or so Borland claims.
On the other hand, commands executed in the Windows environment - those using
GUI buttons and menus, as well as query by example or table manipulation - are
reflected at the dot prompt as dBASE commands that can be cut and pasted into
programs. The combination of both forms of support promises complete 
compatibility with DOS dBASE programs, and programs generated by the older 
DOS version run, unchanged, as Windows applications, with the added benefit 
of full mouse support and cut-and-paste capability.

...Out of all this, there was one standout feature that's *not* supported by
any other competing database product. Any Windows DLL can be called directly 
from dBASE for Windows. This means that for those who know how to handle
API calls, dBASE can be used to invoke Windows routines just like a higher-
level programming language.

...At press time, Borland wasn't even talking about introductory pricing. 
However, surveys reportedly taken at Comdex/Spring showed that users were
expecting something akin to the price Microsoft was asking for Access 1.0,
which dropped as low as $79.

...From the "Copper Top" department: Duracell has proposed four standard 
battery sizes for the NiMH cells that power notebooks. Optimistic that 
standardization is possible - citing the 35mm camera battery market as the
prime example, and which started out with literally dozens of battery designs
for dozens of cameras, and now has five standard sizes. The end result hoped
for is that both disposable *and* rechargable batteries for notebooks can
be purchased over the counter just like a pack of AA cells.

...As with any sort of unification in this business, cooperation from computer
manufacturers has been less than encouraging. Although Duracell has approached
over 90 manufacturers and OEMs in the US, Europe and Japan, only Compaq has 
agreed to design in the standard-sized batteries. This isn't too surprising,
considering that Compaq ships Duracell's model DR19, which costs $99, in the 
monochrome Contura Aero subnotebook. The model DR31, a longer lasting cell, 
will be sold as an optional accessory.

...Most industry observers are skeptical, citing computer manufacturers'
desire to buy customized batteries to optimize their designs and force their
customers to buy batteries from them and them alone. They also predict 
customer resistance to the price point, observing that a $100 price tag for
a laptop battery is well out of the kind of "impulse buying" market that
9-volts and AA's belong to.

...From the "Room at the Top" department: Logitech will incorporate Helix 
Software's Cloaking technology in the next release of Logitech's MouseWare.
Cloaking technology, such as that marketed by Helix, lets mouse drivers and 
TSRs use little or no conventional memory when operating under DOS by moving
the driver to extended memory or protected memory, in most cases leaving
no more than a 1k footprint in conventional memory. Logitech reps expect
the new drivers to be released in late Summer, although it had not been
decided whether the drivers would be available through standard upgrade
paths, or whether full retail would be charged to offset the licensing
cossts for the Cloaking technology.

...From the "Scarcity Begats Demand" department: Windows for Workgroups 3.11
is finally outselling Windows 3.1, according to Microsoft's chief sales
reps. According to those same reps, "at the end of the first quarter Windows
for Workgroups 3.11 (WFWG) was outselling Windows 3.1, and has become the
'mainstream' Windows operating system."

...Retail sales of WFWG 3.11 reached 300,000 copies worldwide at the beginning
of this year, according to Microsoft, and the company predicted that 6 to 8 
million copies of WFWG will have been sold by this fall - 12 months after its 
launch last October.

...Microsoft touts WFWG's improved performance over Windows 3.1 as being its
selling point. In fact, Microsoft's emphasis on WFWG instead of Win 3.1 is
considered by most industry experts as an attempt to pave the migration path 
to Chicago, at the expense of short-term profit. Industry analysts do not see
a huge profit for Microsoft now but predict a return after the release of 
Windows 4.0.

...However, Microsoft officials declined to comment on several comments
raised at Comdex/Spring regarding the lack of availability of Windows 3.1
around the time of the release of WFWG. One Dallas distributor was cited
as accusing Microsoft of "deliberately forcing us to sell WFWG in place
of regular 3.1, just to inflate the 'worth' of a product they couldn't
have sold otherwise!"

...The problem with that sort of thinking, though, is that WFGW - or
WinGroups, as it's also been referred to - *is* a faster version of Windows
and runs quite a bit more reliably not only moreso than its standalone 
predecessor, but even more than the version from which the improvements
were first developed, Windows NT! Outside of the lack of compatibility with 
OS/2, upgrading to WFWG is *not* an unsound idea.

...From the "Jurassic Park is Melting In the Dark" department: Pixar is about
to bring a version of its rendering technology software - yeah, that's what
Spielberg used to create those dinosaurs with in "Jurassic Park" - to end-user
desktops. Aimed at the power executive, Cool Charts will use rendering and
morphing technology to control the movement and adjustment of light sources,
creating the illusion that graphics used for presentation displays are 
actually photographic, or rendered, images. 

...While Pixar claims the package will run on 486SXs, as with any high-end
graphics package, performance will improve on a DX4 or Pentium-based system.
Pixar suggests that the package will run best on a Pentium-60, although
a DX4-100 is acceptable. As one would expect, if something needs expensive
hardware to run it, rest assured the cost of the software is going to be
expensive as well. Pixar plans to MSRP Cool Charts at $995, although Pixar
spokespersons did hint that a somewhat scaled-down version for hobbyist
and small commercial use would probably be developed depending on the 
demand.

...From the "Wanna Buy a Bridge?" department: Worldwide losses to business 
software piracy totaled $7.45 billion in 1993, according to figures recently
published by the industry's most notable paranoid watchdog, the Software 
Publishers Association. The United States suffered the greatest loss with 
$1.57 billion, followed by Japan with a loss of $650 million. 

...Although the Western nations led in terms of overall monetary losses, the 
SPA reported that piracy rates in economically emerging nations exceeded those
seen in the industrialized world. Of course, considering that the primary
excuse for piracy is the fact that most software is overpriced to begin
with, this observation should really come as no surprise.

...From the "Throw in the Towel!" department: Remember Microsoft Profit? Of
course not! Everyone was too busy dumping on Doublespace to dump on this
particular gaffe from the Gates Boys. Well, Microsoft has come to their
senses about this worthless package, and has left the business accounting 
arena to remain dominated by the likes of Quicken. Anyone who has ever
tried to use Profit has come to believe that the package itself, and not 
Quicken's usability, was a major factor in why Quicken's sales were so
high.

...In late May, Microsoft handed over Microsoft Profit for Windows, to 
Great Plains Software, for what's been rumored to have been a really *low*
sum of money. Great Plains, as you'll recall, originally developed the DOS
version of Profit - which wasn't too bad a program -  and the North Dakota
-based company joined Microsoft in developing and distributing the Windows 
version in 1992. Great Plains will continue to market and develop future 
versions of Profit, but intends to make some major changes in the design
and efficiency of the product prior to its next release.

...On a nasty note, word has it that Compu$erve is moving from its mainframe
core system to a series of RISC boxes, all running Windows NT on top of
Unix. Expect rates to go up and accessability to go down when someone 
discovers that CI$ bought I/O controllers that can't support 32-bit disk
access!

...From the "Crimestoppers Textbook" department: CD-ROM publishers may soon 
take a hint from the record industry and distribute the shiny discs in 
plastic "jewel cases'' with no additional cardboard packaging. The jewel cases
can hold a 16-page manual, a registration card, and the disc itself, but
several multimedia publishers have warned that larger cardboard packaging has
advantages that aren't needed with audio CD's. According to a Software 
Toolworks spokesperson, "the larger box lets a company display the features
and explain an application to customers. An illustrated box is very
informative, and is a lot more difficult to shoplift than one might think!"

...All hell is breaking loose in San Francisco, and it's not because of
Earthquakes, either! Media Vision, manufacturers of is considered by most
OEM's and computer resellers the more reliable line of sound cards on the
market today, is under fire from nearly every quarter. The #2 multimedia 
hardware and software company - second only to Sound Blaster thanks to an 
unfair advantage in on-the-game-box advertising - is under investigation from
both the Federal Bureau of Investigation (FBI)and the Securities and Exchange 
Commission (SEC) concerning securities issues. Several class action lawsuits 
have been filed against the company in March in addition to lawsuits alleging 
violation of Section 10(b), 20 of Securities Exchange Act of 1934, and several
chief executives have bailed out of the company in the wake.

...As of May 20th, Paul Jain is out as chief executive officer, and is being
joined in his resignation by the company's chief financial officer, Steven 
Allan, chief operating officer Russell Faust, and senior vice president of 
worldwide sales Michael Humphress. These resignations come following reports
in _The San Francisco Chronicle_, which detailed how the company's financial
reports for the last two years had been doctored to look better than they
really were, and that former employees and executives of the firm have been
talking about illegal activities that took place at Media Vision, such as the
altering of sales records, a hidden warehouse with returned products, and 
recording sales of products that had not shipped. 

...The personal conduct of Jain himself was also the subject of the newspaper's
reports, centering around Jain's trips to Paris with women allegedly financed 
by company funds. Following his resignation, Jain issued a statement for 
himself through a public relations firm blaming these scandalous reports in 
the _Chronicle_ concerning his acts, as well as the company's, for his 
resignation. In his own statement, Jain said concerning his resignation: 
"I believe it to be in the best interests of the company and an important 
step in restoring confidence in Media Vision and its products among customers,
suppliers and shareholders." Jain also said he plans to spend his time in
making an attempt to clear his name and reputation, and will make himself 
"available as a consultant" to Media Vision.

...In addition to these departures, five other Media Vision board members and
vice presidents have left the company entirely since May 9th: Executive Vice 
President Min Yee, Vice President of Strategic Marketing Satish Gupta, and 
Vice President of Set Top Engineering Shiraz Shivji, outside board member 
Bernard Vonderschmitt who is president of Xilinx, and outside board member 
Curtis Wozniak who serves as vice president of worldwide marketing at Sun 
Microsystems. All have declined comment to the media on the situation on the
advice of their attorneys. Shortly after these departures, the company also 
gave fifty employees pink slips, reducing the work force to 300. 

...Meanwhile, Media Vision's stock value continues to take a nose dive. In
December of 1993, the stock was at a high of 46, but has since dropped to the
2 level as of press time! This comes on the heels of two delays by the board 
of directors in reporting its earnings for its fourth quarter and fiscal year 
ending March 31, 1994. Company officials now say that it would be several 
weeks until the results are ready, and cites the delay to the turmoil 
surrounding the departures of the high-level executives. 

...Adding final insult to injury, reports flew over several computer networks
prior to Memorial Day weekend of calls to Media Vision's tech support lines
which were answered by technicians who told of a "company-wide panic" 
following a rumor circulated over the company's in-house network, warning
that "everyone should *not* be surprised when they show up back to work on
Tuesday to find the doors have been padlocked!" Workers were also reportedly
urged by department heads to "take home anything of value" from their 
offices, just in case the rumor turned out to be true. Luckily for Media
Vision employees, the rumor turned out to be just that - at least, for the
time being.

...Finally, industry experts, OEM's, and VAR's are watching the developments
with Media Vision closely. Should the company's financial troubles result in
cessation of operations, this would give Creative Arts a virtually unchallenged
dominance of the computer multimedia market. Many OEM's and VAR's view this
as something they'd rather not see happen; polls conducted by publications
such as _Computer Reseller News_ and _PC World_ show that Media Vision products
were preferred over Creative Arts line of Sound Blasters by a 2 to 1 margin.
Most cited the ease of compatibility with non-Media Vision OEM products,
and the ease of configurability when compared to that of the Sound Blasters.

...WWIVNews will obviously keep a ear open for further developments.

...From the "ALIAS is *Dead*" department: If you've never uttered the words 
English and DOS in the same sentence, this product is for you. Natural 
Language Solutions has developed EasyEnglish DOS, which is an alternative to 
DOS commands and syntax that non-geeks - that is, people who aren't normal
like the rest of us - cannot comprehend. The program allows you to freely 
form DOSlike requests using everyday English words and phrases, such as 
"Add the current directory to my path" and "Does this directory fit on drive
A: or B:?" 

...Powered by NLS's proprietary SmartLogic artificial intelligence technology,
EasyEnglish DOS is an advanced natural-language processor that analyzes and 
understands your ordinary English so you don't have to memorize cryptic or
complex keywords and syntax. You can simply phrase your request as if you were
speaking to a person. The program even expands the usual set of DOS commands. 
For example, you can find and manipulate files or groups of files ("...all 
files that end in DOC or WAV except FART.WAV"), get information ("Which drive
has the most free space?"), and much more. 

...As for performance, those who've used EasyEnglish DOS claim that it can
slow down your system depending on how much difficulty the program has in
parsing out your command. NLS suggests that while the processor will work on
anything above and including an XT, a 386DX-40 is the minimum recommended
system configuration for at least acceptable performance. EasyEnglish DOS 
has an MSRP of $49.95, and is available directly from Natural Language 
Solutions or through most suppliers and VARs.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³    The Power Mac: Panacea or Snake Oil?     ³
               ³            by Omega Man (1@5282)            ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

Ok, we've all heard the rhetoric. We've seen the ads, tolerated the hype, and
politely nodded our heads when the Mac geeks were all jumping up and down 
about Apple's line of Macintoshes equipped with PowerPC processors. Specially,
we've had to endure the blatherings over Insignia Solutions' SoftWindows, 
which is the special version of Windows 3.1 which in turn is executes under 
a software-emulated version of DOS. The end result is a machine that's supposed
to unify the two sides of the Great Computer War into one common machine
that'll put Apple on top of the computer industry.

Now, Apple has had some really high hopes that they can sucker all the DOS 
geeks away from their DOS boxes and have them buying the new Power Macs 
because they can run both Windows and the Macintosh operating system. But the
question here isn't compatibility, it's speed. Do Apple's latest foray into 
the world of Windows deliver a level of performance high enough to interest 
mainstream Windows users? Let's find out.


"THE STORY YOU ARE ABOUT TO SEE IS TRUE..."
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

First off, let's look at what we're dealing with. The three new machines, 
which will have Windows preloaded, are specially configured versions of the 
Power Macintosh 6100/60, 7100/66 and the 8100/80. This adds between $300 and
$700 to the price tag. The added cost comes not only from the licensing fee
for SoftWindows, but because SoftWindows requires a substantial chunk of RAM.
In fact, Power Macs equipped with Windows will ship, at minimum, with a
whopping 16MB of 4MB SIMMs, which as we all know usually runs about 40% more
for Mac systems than for PC's simply due to dealer price gouging.

Next, there's the processor. The new Macs are based on the PowerPC 601 chip,
which is a reduced instruction set (RISC) CPU. This chip offers some really
choice performance results when used with apps that were written in native 
PowerPC code. In benchmark tests performed by Apple and IBM, some apps run
four times as fast on a PowerPC system as they do when compared to their 
counterparts running on Pentium and 68040 processors.


"THE NAMES WERE CHANGED TO PROTECT THE INNOCENT..."
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

When the power Macs were released, Apple's CEO, Michael Spindler, claimed that
the architecture of the Power Macs would "deliver Windows 3.1 performance 
equivalent to that offered by 486-based computers!" However, benchmark 
tests performed by several different magazines and testing centers, including
the normally tainted-by-brownnosing Z-D Labs, have shows that the pairing 
between the Power Macs and the Insignia Solutions have been far less than 
completely successful. In fact, the word "lame" probably best describes the
situation.

Now, this situation could have been avoided had the PowerPC been designed
along a specification suggested by IBM when the consortium between Big Blue,
Apple, and Motorola started designing the 6xx series of PowerPC chips. IBM's
idea - which will be implemented, incedentally, in the PowerPC 615 - called
for including CISC code for both the 80486 and the 68040 along with the
PowerPC RISC microcode on the same 601 wafer. There was plenty of room, and
the design would have ensured total compatibility between DOS apps, Mac apps,
and whatever PowerPC environment the user chose to operate under. 

However, both Apple and Motorola engineers pressured the decision to make the
initial 601 and 603 chips as RISC-specific as possible. RISC technology places
the burden for performance on having the software as optimized as possible
using a reduced instruction set. The belief on the part of Apple and Motorola
was that by forcing those wishing to use CISC-based apps to take a performance
hit when compared to RISC-based apps, pressure would be applied to both users
and software developers to switch to the RISC-based - read: PowerPC-based - 
apps in order to gain back the lost performance.

In other words, if you wanted to use that "now-antiquated" Word for Windows 
or MacExcel on a PowerPC, you had to pay a penalty and use an inefficient
emulator package. As we're finding out - at least, as far as the SoftWindows
emulation is concerned - that such a method just might not cut it when it
comes to performance needs.


"JUST THE FACTS, MA'AM..."
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The tests show that on the average, a Windows-equipped Power Mac 7100/66
with a $4200 price tag, delivered an amazingly s-l-o-w 10.21 MIPS, 4.36 MFLOPS,
and 0.723 MPixels. For those not up on MIPS, MFLOPS and MPixels, this level 
of performance is typical of 386SX CPU's in the 10-12MHz range, and 286 CPUs
in the overdriven 20MHz range. Adding more insult to injury is the fact that
the Windows emulator supplied by Insignia not support any accellerated or
enhanced video for Windows, has no support for sound or multimedia, and lacks
the ability to utilize any other drivers not included with the emulator. Oh,
and the whole mess runs in Standard mode. No Enhanced mode, nor any Real
mode, either. 16-bit compatibility is all you get, which throws Windows
for Workgroups right in the toilet, and gives you performance that's closer
to Windows/386 than Windows 3.1.

Of course, Insignia Solutions claims that a new version of Windows for
Power Mac is in the works that will overcome these difficulties, but insiders
at Insignia say not to expect this to ship before the end of this Fall. The 
revision, those insiders also warn, will only address complaints about the 
existing version's lack of speed, and to offer 486 performance. Absolutely
no plans are in the works at the present to address compatibility with 32-bit
Windows apps, although the Multimedia issue "is being looked into, but will
probably require the use of the Power Mac's own sound capabilities.

Now, in all fairness, it should be noted that the Power Macs run Mac wares
at anywhere from 90% to 400% faster than on your normal 68040. Your performance
varies depending on the app in question. However, at the same time it needs
to be pointed out that quite a number of FPU-intensive Mac apps have shown
poorer performance thanks to an incompatibility between the 040-native apps
and the PowerPC's 040 FPU emulation. These apps - most specifically, Excel
for the Mac - fail to recognize the emulated FPU, and start their own
software emulation process. The end result is that these apps run anywhere
from 10% to as much as 60% *slower* than when run on a 33MHz 68040! 


"AND NOW, THE RESULTS OF THAT TRIAL..."
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

So, when you get down to brass tacks, what you're looking at is, at best, 
386SX-16 performance which carries a Pentium price tag. Take your basic Power
Mac, throw in 24MB of RAM - 16MB for the SoftWindows appetite, 8MB for the 
Mac OS requirements, a typically overpriced Apple multisynch monitor, the 
equally overpriced Mac keyboard, and SoftWindows, your complete PowerMac 
7100/66 system will run $4,200. Those wishing to sacrifice maximum performance
for savings can look at the so-called entry-level Windows-capable Power Mac 
6100/60, which comes only with 16MB of RAM and a price tag of around $2,600. 

With that kind of pricing and performance, it should be rather obvious whether
or not a Windows-capable Power Mac is worth buying or not. In the opinion of 
this writer, the Power Mac isn't worth the cost. Granted, there will be those
die-hard Mac geeks who happen to think that these Power Macs are a really good
deal. Those people will be those who primarily use Mac apps - and eventually
PowerPC-native Mac apps, and only use one or two Windows apps for those
"rare" compatibility matters that MacinDos or an Appletalk connection used
to solve. 

For the rest of us, whether we be IBM geeks or Mac geeks, the issue is whether
or not the combination is efficient enough to justify the added cost. Those
of us in the IBM world would be best suited in plunking down their cash for
a 486DX-100 or a Pentium-66, and taking what's left over and finding a used
Mac if a Mac app or two needs to be run. Apple dogmatists should purchase
a Power Mac, but avoid the added costs of Windows compatibility and spend
what's left over on a down payment on a used 486SX-25 machine for those few
DOS apps they need to run. 

Bottom line is this: If Apple expects these Macs to start setting the world
on fire, then they'd better start dropping the prices and improving the
performance issues. The former insures that the normally-frugal IBM crowd
will give it more than just a curious glance, while the latter will keep
everybody happy.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³                Type 0 Forum                 ³
               ³         Edited by Omega Man (1@5282)        ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

[Editor's nOTE: As Wayne has mentioned in his column, lately there's been 
quite a bit of debate on the various sysop subs as to the merits of adding
a QWK packet manager to stock WWIV code. During the debate, opinions for
inclusion in WWIVNews were solicited, and the following responses were 
received prior to press time. Also, a net-wide poll was being taken with
regards to this question, and the results will be reprinted in the next
issue of WWIVNews, along with any other commentaries received.]

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

What ever happened to the old spirit of WWIV sysops? 

You know, the ones who used to fight about who had the silliest mod?

Who spent hours tweaking their boards to have something different?  

Who went out of their way to find externals to install on their machines?  

Now we want *everything* built into WWIV? 

Somehow I don't think so If you want everything built in, and if you want to
be a lazy shit (pardon my french), go spend $200 on wildcat! This is the IDEA
of WWIV: You have an excellent basic BBS program with which to do whatever 
your personal tastes dictate.

                                                                Me (1@5439)


I do believe an internal QWK mailer would be beneficial to WWIV. I have had 
problems with WWIVMail/QWK, even set up correctly, odd problems that cannot be
nailed down to any specific event or happening. There is also too much fluff
in the other external QWK mailers, gee, my users download, and upload posts, 
they don't need the other four screens of options that they have no idea as to
what they are for, a simple menu and a simpler setup is what is needed. It 
should pack messages and send them to the user, and recieve from the user
and unpack, and use the user's default protocols and qscan setups.

                                                          Wildfire (1@5891)


[..] I'm gonna keep using WOMR and WOMR-QWK, unless Wayne comes out with an
absolute *killer* QWK. So, for that reason, I'd obviously like to see one
added to stock WWIV, but it needs to be "#define-able". It's not really 
that big a deal, tho, 'cuz I can rip the offending code out, easily enough!

                                                               Wiz (1@3325)


Considering that there are problems with running some external programs with
WWIV under OS/2, it only makes sense to have an important feature such as
a QWK packet manager built into WWIV itself. The majority of system lockups
under OS/2 that occur on our company's BBS have been attributable to the
external QWK manager that we use -- specifically, WWIVMail/QWK. Since WWIV
itself has no real problems under OS/2, and in light of the upcoming WWIV for
OS/2, adding an *internal* QWK mailer to your basic WWIV source makes a whole
lot of sense, IMHO.

                              MicroSource Sysop (1@15136)

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Dear Editor:

With the release of NET33, WWIV network software gained the ability to gate
e-mail and posts between the different networks without much (if any) effort. 
While this ability has made it much easier to interconnect the other networks
with WWIVNet, I think a side effect of this gating ability has probably
resulted in reduced registrations for the WWIV bbs software and has without
question slowed the growth of WWIVNet.

The proliferation of mini-networks has in some areas made communication between
local boards easier by allowing local connections to pass e-mail etc.. between
boards which connect to different long distance servers. These types of
connections are beneficial in that they remove some of the burden of
unnecessary traffic from the network servers.

Now for the down side of all of this: The operators of these new mini-nets 
often accept any and all applicants in an effort to grow. While that growth 
is good for the mini-net, it tends to be detrimental to WWIVNet in the long 
run. Since new SysOps tend to join local networks before joining the national
ones, they are usually under no pressure from the NCs of the mini-nets to 
register their boards or network software. In fact many of them tend to shy 
away from the main networks when it becomes known that they will be required 
to register in order to retain a node number.

Another catch: Due to the ease with which gating subs can be accomplished, 
the new "1@1s" can and often do subscribe to the major networks then gate 
anything they please into the mini-net. This makes it easier still for a 
nonregistered board to receive "main network" traffic and at the same time 
further reduces their incentive to register or join the larger networks.

Where is all this leading? I not sure what can be done, but based on these 
observations I think all of the new "1@1s" should abide by and attempt to 
uphold Wayne Bell's policy of the trial period for WWIV and WWIVNet usage. 

                                                          Maintech (1@5211)


Editor's Reply:

The local "mini-nets" do in fact provide a "proving ground" for new sysops
to get their feet wet with regards to running a BBS with network access, and
managing its users as well. Once they've become confident with how everything
works, and have their users understanding how to properly use the resources
of a network, -then- the sysop should start looking into a larger, more
nationally-based network, such as WWIVNet or IceNET.

However, your last comment does need to be made clear to -everyone-, and not
just the 1@1's for these "mini-nets". If a sysop intends to stay in a WWIV 
network past the trial period, Wayne requires that the program be registered.
Based on what has been brought up over some of the sysop subs of late, there
are quite a few "mini-nets" whose 1@1's are reportedly not enforcing Wayne's
requirement. While some 1@1's elect to "extend" the deadline for certain 
systems depending on individual circumstances, wantonly exempting systems
from being required to register WWIV with Wayne is not an acceptable practice,
and should be refrained from in the future. 

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

"Nyah! My modem is faster than yours!"

We all do it, we all get a little lift by telling people how great we think 
our new stuff is. This very human characteristic spilled into the networks 
probably within hours of the first BBS systems and has never ended. My 
particular concern is the usefulness of this practice when it spills into the
very data files that are used by the network to determine connection rates,
the BBSLIST.x files.

Let me just pull an example (this is a random selection, so don't get mad at 
me for picking on particular systems)

@3250      *312-334-9092 #2400              [40841]  "The Talamasca"
@3350      *313-655-8030 #14400   >!$       [30765]  "Dragon's Lair"
@3351      *313-234-9242 #2400              [40732]  "The Space bbs"
@3352      *313-736-5730 #9600    >!$       [40413]  "Black Celebration"
@3354      *313-733-6057 #38400   >!$       [30168]  "The Dojo"
@3355    ^ *313-694-9957 #57600 <  !$       [11017]  "The Cat's Meow"

In the above section from one of the WWIVnet BBSLIST files we see systems 
listing modem speeds from 2400 to 57600. Last I checked the VFAST modems are
only recently available (though not yet standard) and have a rate of 28800. 
What are these listings of 38400 and 57600 showing up for?  Even 19200 is
suspicious.

Now before someone sends me email to explain that compression provides
throughput at these higher speeds, my question is this:  What makes these
systems different from the systems listing 14400 or 9600?  Those people 
probably have very similar or even the same modem. Looking at the lists to
see who might be a potential connect or a good place to call looking for
files, etc. it gets rather confusing. The identifiers are some help, but 
not a complete solution Furthermore, with the new 28800 modems on the way it
becomes more complicated and no end is in sight.

Perhaps the network software is using these inflated values in some useful way,
or perhaps some sysops feel better about themselves if they list a higher
modem rate. But the fact is, some type of standards are needed to clear things
up. If we agree that 57600 is the value we should use for a 14400 with all 
it's compression, etc. great, lets get them all listed that way. If we are
going to use real rates lets do that.

As things are now, there is no rhyme or reason to any of it and as the nets 
continue to grow and WWIVnet begins to interface with FIDO and perhaps other
"outside" networks these standards may become even more relevant. It seems a
simple matter to fix, we have the people in place to do it: AC's, and GC's 
already handle updates of the BBSLIST files now. Simple search and replace 
commands would make short work of standardizing the lists, and really who are 
we trying to impress anyway?  These are data files used by sysops. If people 
want to advertise these high modem rates use the A)dd command on the BBS list
file on every system you log onto...that's the one users are going to look at!

                                                         Mr. Jones (1@3359)

Editor's Reply:

Personally, I've been prodding Wayne for years to add standard Warp Speed
codes to the BBSLIST files, with Impulse Power being anything below 9600,
and a -true- 115k connection being that unattainable infinite speed of Warp
10 :-)

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Dear Editor:
I have read numerous posts from sysops complaining about the order of their
subs and directories. They try to insert a new sub or directory into a
position they want them in, only to have them pop up at the end of the
conference.

It is my understanding this is being changed in 4.24, but for now, here is an
FAQ I typed up everyone using 4.23:

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The "legal" way currently (as of 4.23) is to (C)lear the entire conference
(not really a lot of fun if you have a lot of conferences, or subs or
directories in a conference).

Or, there is another way (and the way I prefer to do it). Use an editor and
edit the appropriate file (SUBS.CNF or DIRS.CNF)  They are located in your 
DATA directory.

When you do this, you have GOT to be careful though. I strongly urge you to
make a backup copy of them before you do it in case you mess up. It is
IMPERATIVE you use an editor that does not 'word-wrap', or put those little
smiley faces in the file for you. I use the one that comes with Borland C++.
It works very nicely. 

When you open the file, you'll see a note to not edit this file, rather to use
//CONFEDIT. Ignore that part, since that is exactly what we are getting to
do. (Did I mention to back up these files before you do this?)  

Next you will see something that looks like this. Of course the sub names will
be different, as will the numbers:

~A Politically-Oriented
!0 0 255 0 255 0 255 0 2 - -
@0 12 13 14 16 

~B Of Interest to Sysops
!0 0 255 0 255 0 255 0 2 - -
@1 2 65 66 67 68 69 70 71 72 73 75 76 77 78 0 3 79 80 81 4 74 64 

~C General
!0 0 255 0 255 0 255 0 2 - -
@0 5 6 7 8 9 10 11 14 16 17 18 26 63 82 78 19 


Now, say I want to add a new sub in the General (~C) area, and I want it to be
listed second. Assume it is sub number 333. When you use //CONFEDIT to add it
in, this section will now look like this:

~C General
!0 0 255 0 255 0 255 0 2 - -
@0 5 6 7 8 9 10 11 14 16 17 18 26 63 82 78 19 333
                                              ^^^
(Did I mention to back up these files before you mess with them?)  

All you need to do with your editor is take it and put it second, like this:

~C General
!0 0 255 0 255 0 255 0 2 - -
@0 5 333 6 7 8 9 10 11 14 16 17 18 26 63 82 78 19
     ^^^

Save the file, and wala, it is in the correct place!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Make sure it came out like you wanted it,, then delete your backup copies of
the file(s) so that when you back them up the next time, you will not get
confused. In case I forgot to tell you, make sure you back these files up
before you go to edit them, and do NOT use an editor that will automatically
word-wrap the line when it goes beyond 80 columns, or you will not be happy!
 
                                                              Sam (1@2077)


Editor's Reply:

This has been tested on Klingon Empire (1@15117), and despite the fact that
it came from Sam, it worked :-) While it's not that "Official Wayne Bell
Fix" that everyone's been waiting for since //JE was added to WWIV, it'll
do just fine for now.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³   A Net Sub Host's Best Friend - AutoSend   ³
               ³              by JAFO (1@8861)               ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

Have you ever subscribed to a sub and two weeks later you still have not
seen any posts on the sub?  Wouldn't you rather see posts right away so you
can join in the conversation?

I've written a program called AutoSend which solves this problem. When an
auto-request comes in for one of your subs, AutoSend sends old posts to the
new subscriber so they can immediately receive posts.

AutoSend was originally meant to only send old posts, but it has grown into
a full-featured sub host utility. Here are some of its features:

  - Graphical packet scanner, which allows you to view packets as they
    arrive on your system. The display rate for the viewer is configurable
    and you can turn it off if you want.

  - Sends old posts to new subscribers. This is the main and original
    purpose of AutoSend.

  - Keeps log of amount of posts sent. This lets you see who is requesting
    your subs and shows you the number/size of posts sent out.

  - Posts sub rules on new subscriber's system.
  - Posts subscription lists. The colors for the subscription lists are
    completely configurable. AutoSend lets you set up a date to post
    subscription lists, so you never have to worry about doing it.

  - Posts new subscriber lists. AutoSend will track new subscribers for subs
    you host. You can track new subscribers for each sub by month or by the
    week. AutoSend will automatically post these new subscriber listings on
    the first day of each week or month. This feature is in v1.14, which
    will be released when WWIV v4.24 comes out.

  - Posts sub ads, rules, etc. on any sub. This feature lets you post >any<
    text file on >any< sub you have. Do you have sub ads?  Post them on all
    of the Yellow Pages subs you carry!  You can also post your sub rules
    too!  AutoSend lets you assign certain dates to post certain text files,
    and posts them on those days automatically. You can even set up AutoSend
    to post a message every day if you would like.

  - Removes unknown systems from N*.NET files and keeps a log. This keeps
    your host data files clean. This feature also sorts your N*.NET files.

  - Returns dead network e-mail to sender. If e-mail to unknown systems are
    found in your DEAD.NET, AutoSend will return the e-mail to the sender so
    they know that they're mail was undeliverable.

  - Sends e-mail to sub host if dead posts are found. If dead posts are
    found in your DEAD.NET, the sub host for the various subs are notified
    that they have unknown systems in their host data files. Of course, if
    you're using AutoSend you will rarely get these messages, since it
    removes unknown systems from your data files automatically.

  - Keeps detailed error log if any errors occur. The error log tells you
    specifically what the error was and where it occured.

  - Configuration program for ease of use. This program is completely
    graphical and lets you edit most of AutoSend's features. One of the
    best features is the ability to configure the subscription list colors
    on screen.

  - WWIV v4.23+ multi-instance compatible. As of this writing, AutoSend has
    also been updated to work with WWIV v4.24 and its new messaging stuff.
    This new version is v1.14 and will be released when WWIV v4.24 comes out.

Of course, everything in AutoSend is completely configurable. If you don't
want to use certain features, you don't have to.

Most people who are using AutoSend agree that it is one of the most useful
network utilities around. I have only heard positive things about AutoSend
from day one.

Here are some things AutoSend users have said:

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

"I think AUTOSEND is the best WWIV utility program that was ever written!
It saves me COUNTLESS hours of work, and it's TOTALLY automated!  It scans my
packets, sends out messages, gives me subscriber lists of all of the subs that
I host once a month, and now even automatically posts ads for subs that I host
in the WWIVnet Yellow Pages!"

"It is only something like $15 to register the program, and it's worth ten
times that amount!  If you host a sub (or LOTS of subs) and haven't checked
out this program, give it a shot!  If you don't like it `I'll eat a bug'!"

                                                    Robert Griffith #1 @7729


"I agree!  AutoSend would be perfect to include with WWIV and/or NETxx
releases. It's the perfect sub-host utility. It could also be used to post
FAQ's in some of the subs, eliminating some of the useless repeat-questions
that pop up once in a while. :)"

                                                             Chris #1 @2914


"And thanks for replying to my posts and trying to explain it to me. Also
thanks for working on it for us. I am still telling others how great AutoSend
works. I think anyone hosting a sub should be using it."

                                                          Chat Cat #2 @5211

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

AutoSend is currently being used by over 300 sysops. If you haven't seen it
being used to post sub ads and subscription lists, you probably will soon.
Perhaps you should pick up a copy and try it yourself!

AutoSend is shareware and costs $15 to register. Registration does not really
give you any extra features because AutoSend is not crippleware, but you do
get a lot for your money.

If you want more information about AutoSend, feel free to e-mail me. The
current version is v1.13. There is a sub set up for support of AutoSend and
my other programs. The sub type is JAFOSUP on every network that my BBS (Blue
Thunder) is on. You can find AutoSend on most WWIV Support BBSs and on my BBS
as well. You can reach my BBS by calling (818) 848-4101 or my second line at
(818) 848-4350.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³    POSSE COMITATUS ACTIVITY ON WWIVNET?     ³
               ³             Mr. Natural (1@8262)            ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

[Editor's nOTE: This guest editorial by Mr. Natural asks more than just
the question of whether or not racist, seditionist, or anarchial activity
should be allowed over the WWIV networks, but whether or not they should
be used for any sort of questionable sales practices. As this is a very
sticky topic, considering the recent "Green Card Lottery" fiasco on the
Internet, and the White Supremacy debates on Prodigy, your responses to 
the questions raised by this editorial are hereby solicited.]
                 
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

There has been some activity being promoted on a WWIVnet subboard that strikes
me as illegal, and I thought I ought to call someone's attention to it.

There has been a fair amount of activity on a political netted subboard by 
white supremacists. One of these white supremacists is a member of a tax-
protest and survivalist group that has historically been associated with 
crimes including the unlicensed practice of law - the specific violation I 
think I observed - and far worse, including homicide.

This group calls itself "Posse Comitatus." It takes its inspiration from the
old Sheriff's posses familiar from Wild West movies, and from a Federal law 
forbidding military intervention in civilian law enforcement.

They espouse a belief system that, however unlikely it seems, can only be 
described as white-supremacist, Christian fundamentalist anarchism. They are 
a loose-knit bunch, so it's hard to make universally true generalizations 
about them; but many members are also involved in the white-supremacist 
fundamentalist religious cult of "Identity" Christianity, which teaches that
white Anglo-Saxons are the true descendants of the Lost Tribes of Israel, and
that contemporary Jews are diabolical impostors. I understand that they are 
an offshoot of an earlier terrorist group called the "Minutemen," which 
operated more publicly and was scotched in the late '60s or early '70s for 
weapons violations.

They also have some bizarre legal and Constitutional beliefs: some of these
are familiar crackpot theories like the gold standard; but they also claim 
that just about every Constitutional amendment after the Civil War is somehow
illegal and the work of Zionist bankers. The "true" Constitution is founded 
on something they call "Christian common law," and laws they disagree with 
are the work of a conspiracy.

They use these claims to recruit white people who have legal or financial 
problems, claiming that they have discovered secret legal theories that, when
revealed, will convince the courts that the income tax is illegal; or that 
their mortgages are invalid; or that they don't need a driver's licence to 
drive, etc., etc. They sell briefs and pleadings that allegedly will compel 
the courts to recognize these claims. Since self-interest clouds peoples' 
judgment so easily, some are persuaded that these opinions represent the 
"true" meaning of the law and Constitution. They were active throughout the 
Midwest during the farm credit problems in the mid 1980's; they also form 
one of the cores of the tax-protest movement.

They also encourage their followers to file meritless pro-se lawsuits against
banks, IRS officials, and anybody else who opposes them; and to record 
eccentric screeds in the land title offices, declaring "Christian common-law"
liens against their opponents' property, or "Allodial land patents", 
proclaiming their own land to be an independent county beyond the jurisdiction
of the United States government. Of course, all their claims lose sooner or 
later. The Courts, especially the Federal courts, have learned to recognize 
this material and dispose of it quickly, often enjoining the perpetual 
plaintiffs from filing more without leave of court.

But the next step is to convince people that the reason the courts have turned
a blind eye to the "true" meaning of the Constitution, &c., is because they 
are controlled by the Jewish/Illuminati Conspiracy. They call the U.S. 
government "ZOG," meaning the "Zionist Occupational Government." From here we
move into the relatively familiar territory of white-supremacist conspiracy 
theories, the Protocols of the Elders of Zion, and the Illuminati.

Were this the extent of their activity, they would be merely harmless 
nuisances. But they also buy into long-exploded theories about the "true" 
meaning of the Second Amendment, and form armed survivalist cells willing to 
violently resist enforcement of ZOG's laws. Their great martyr, Gordon Kahl, 
killed a sheriff and died in a firefight with law enforcement officers; they 
have killed or claimed to have killed a number of other law enforcement 
officers and IRS agents, and people moved by this belief system have died 
violently in shootouts with the police. In 1982 eight Posse members were 
jailed for plotting to kill a Federal judge and bomb the IRS office in Denver,
Colorado.

They have also been caught up in litigation involving "barter banks" they have
set up, in order to pay members' bills without leaving a paper trail for the 
IRS; Federal agents have seized stockpiles of gold and silver they have 
hoarded as parts of these schemes; I understand that these may still be in 
litigation.

Now, as it relates to WWIVnet specifically:

One of the believers in this stuff, who has posted messages that display a 
disconcerting familiarity with Posse ideology and beliefs, has gone past 
merely advocating these beliefs on the network. I have enough respect for 
freedom of speech that I would not recommend any action against a BBS because
a user, or even its sysop, believed in this trash. But I think that this 
particular user and system have crossed the line. He has started posting 
advertisements on the sub-board, advertising for sale (for $20.00 apiece) a 
"Traffic Motion for Dismissal" that allegedly will make you exempt from having
to get a license to drive.

I believe that this constitutes the unlicensed practice of law, and represents
the use of WWIVnet to advertise and promote illegal activity.

I also believe the sysop of the system he is using for this supports him; I 
know he has turned over an entire message base on his system to the individual
who is selling this material; and he claims to have some similar files 
available for download.

Do I have general agreement that this sort of thing is an inappropriate use of
the network?  I'd like to have other people's feel for this before I take it 
up with the system's AC and GC. I make no secret about the fact that I have 
tangled with these fellows and had flaming responses to and from them in the 
past on the subboard in question. I also admit that I personally consider 
neo-Nazis, anti-Semites and Holocaust revisionists to be among the most 
loathsome examples of human vermin I can imagine. So I admit my own personal 
judgment may be clouded here.
But I submit that advocacy and instruction in the illegal activities of Posse
Comitatus, and the offer of bogus legal pleadings for sale over the network, 
is something that does not belong here.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

For more information about Posse Comitatus, their belief system, and
their violent activities, consult:

"The Ku Klux Klan Encyclopedia", pp. 466-467

"Armed And Dangerous: The Rise of the Survivalist Right", pp. 104-122

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³ Official WWIV Modification Services Listing ³
               ³             Shadowspawn (1@3900)            ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

  Please submit any changes to this list to the author c/o @13900.WWIVLink, 
                     @3900.WWIVnet, and/or @3900.IceNET.

DISCLAIMER:

  ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
  ³ WWIV Software Services, Wayne Bell and the author of this list do not  ³
  ³ warranty the work performed by the sysops listed in this document. This³
  ³ document is published solely as an aid to those sysops wishing to have ³
  ³ their World War IV Bulletin Board Systems modified, but lack the       ³
  ³ resources to do so themselves. Sysops are only guaranteed to have      ³
  ³ registered their WWIV software with WWIV Software Services, and are    ³
  ³ thus able to modify source code for other sysops as specified within   ³
  ³ the WWIV License Agreement. All other information in this document is  ³
  ³ believed accurate at the time of publication, but is not guaranteed.  ³
  ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

Modification Code Definitions
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ


CODE "D" - TOGGLE DEFINES ONLY
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The following system operators are authorized to compile the source code for
REGISTERED sysops, toggling the custom #defines located in VARS.H. There is a
fixed $5 fee for this service.


CODE "M" - PRE-WRITTEN MODIFICATIONS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

System Operators with a MOD: code of "M" have specified that they would
be willing to add modifications requested by the sysop which have been posted
on the WWIV Mod Sub. The fee for this service is variable, depending upon the
relative difficulty of the pre-written mod, and should be decided upon by the
sysops involved before the work is started.


CODE "C" - CUSTOM MODIFICATIONS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

System Operators with a MOD: code of "C" have also specified that they would
be willing to add any modifications requested by the sysop, including custom
written modifications based upon the specifications of the sysop. The fee for
this service is variable, and should be decided upon by the sysops involved
before the work is started.


MODIFICATION BBS LISTINGS
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

210-631-5841  The Dragon's Den                  [81006] Filo
        BPS: 14400 !$  (2)     MOD: D                   Wig De Moville
        SDS, ASV               MT:                      McAllen, TX
        WWIVnet: 2050 (GC4)    WWIVLink: 2050           IceNET: 2050
        Compiler:  BC++ v3.0  TC++ v2.0
        Machine Type: 486

602-942-9228  Moon Valley Triangle              [11024] Lance Halle
        BPS: 14400 <!$ (1)     MOD: D                   Lance Halle
        SDS, ASV,              MT: DV                   Phoenix, AZ
        WWIVnet: 6211          WWIVLink: Pending        IceNET: 6211
        Compiler: Borland TC++ v3.0
        Machine Type: 486, but can compile w/o '286 / '87 options

209-491-0782  Anything Goes                     [20791] Chris
        BPS: 12000 !$  (1)     MOD: DM                  Chris Yarnell
        SDS, ASV               MT: OS/2                 Modesto, CA
        WWIVnet: 2914          WWIVlink: 22914          IceNET: 2914
        TARDISNet: 2           TerraNET: 2914           CHAOSNet: 2914
        Compiler: Borland C++ v3.1
        Machine Type: 386DX/33

301-863-8706  Off The Wall                      [41022] TooSlow
        BPS: 14400 <!$  (1)    MOD: DM                  Mike Toloso
                               MT: None                 Lexington Park, MD
        WWIVnet:               WWIVLink: 13100          IceNET:
        Compiler: Turbo C++
        Machine Type: 386DX/33

309-452-2838  Adventurer's Corner               [10419] ShadowSpawn
        BPS: 28800 <!$ (1)     MOD: DM                  Scott Kuntzelman
        ASV                    MT: OS/2 v2.1            Normal, IL
        WWIVnet: 3900          WWIVLink: 13900 (ZC3)    IceNET: 3900
        Compiler:  Borland C++ v3.0, Borland C++ for OS/2 v1.0
        Machine Type:  IBM 486SLC2/66

310-518-9701  T.U.M.S.                         [30582] OCC
        BPS: 14400 <!? (2)     MOD: DM                  Larry Saunders
                               MT: Windows v3.1         Torrance, CA
        WWIVnet: 3052          WWIVLink:                IceNET: 3062
        Compiler: Turbo C++ v3.0
        Machine Type: 80386SX/25

310-973-4949  Entity BBS                        [31050] Bogie
        BPS: 19200     (1)     MOD: DM                  William Bogart
        ASV, GSA               MT: OS/2 v2.1            Lawndale, CA
        WWIVnet: 3081          WWIVLink:                IceNET: 3081
        TERRAnet: 3052         Infinet: 8               Filenet: 600
        Compiler: Borland C++ v3.0
        Machine Type: 80286, 80386SX, 80486DLC

405-677-6159  Alkar's Keep                      [32413] Alkar Zephyr
        BPS: 14400 !$  (1)     MOD: DM                  T. Karl Rollans
                               MT:                      Oklahoma City, OK
        WWIVnet: 4506          WWIVLink:                IceNET: 4506
        Compiler: Turbo C++ v3.0
        Machine Type: 80486

512-836-8071  The Water Closet BBS              [20825] H2O DOC
        BPS: 14400 !$  (1)     MOD: DM                  Dwane Newby
        ASV, SDS               MT: Desqview v2.62       Austin, TX
        WWIVnet: 5284          WWIVLink: 25284          IceNET: 5284
        TARDISnet: 5284        GAYnet: 5284
        Compiler: Turbo C++ v3.0
        Machine Type:  386DX/40

514-487-7467  Permanent Vacation                [21264] Your Mother
        BPS: 14400 !$  (1)     MOD: DM
        SDS                    MT:
        WWIVnet: 5458          WWIVLink: 15458          IceNET: 5458
        Compiler: Borland C++ v3.0
        Machine Type: 486DX/33(VLB)

514-664-4503  Alternative Worlds                [10556] Spotnick
        BPS: 14400 !$  (1)     MOD: DM                  Nicolas LeBlanc
        ASV                    MT: Desqview             Laval, Qu‚bec Canada
        WWIVnet: 5497          WWIVLink:                IceNET:
        TERRAnet: 5497         ROCKnet: 5497
        Compiler: Borland C++ v3.1 w/AF
        Machine Type: 386DX/40

514-748-7383  The Hornet's Nest                 [31249] The Master
        BPS: 14400             MOD: DM                  Ian Strulovitch
        ASV                    MT: Desqview             Montreal, Qu‚bec Canada
        WWIVnet: 15498         WWIVLink: 15498          IceNET: 5498
        ROCKnet: 5453          APEX: 5498               TERRAnet: 5498
        TARDISnet: 5498        SOLARnet: 5454
        Compiler: Borland C++ v3.0
        Machine Type: 486DX/33

604-578-7634  The BS BBS                        [81101] Computer King
        BPS:       >!  (1)     MOD: DM
        ASV, GSA               MT: Desqview v2.42
        WWIVnet: 6401          WWIVLink:                IceNET: 6401
        Compiler: Turbo C++ v1.0
        Machine Type: 286/12

704-525-1491  The Funny Farm (East)             [90627] Benny Hill
        BPS: 14400 <!$ (1)     MOD: DM                  Joseph Rybaczek
        SDS, ASV               MT: None                 Charlotte, NC
        WWIVnet: 7400 (GC6)    WWIVLink: 17400          IceNET: 7400
        Compiler: Borland C++ v3.1
        Machine Type: 386SX

716-592-5652  The Great White North             [11258] Jim
        BPS: 16800 <!$ (1)     MOD: DM                  Jim Nunn
        IPSS, ASV              MT:                      Springville, NY
        WWIVnet:               WWIVLink: 17662          IceNET: 1 (NC)
        Compiler: Borland C++ v3.0, TurboC++ v2.0
        Machine Type: 80486

716-592-5910  Paragon                           [11258] Jim
        BPS: 16800 <!$ (1)     MOD: DM                  Jim Nunn
        SDS, ASV               MT:                      Springville, NY
        WWIVnet: 7663          WWIVLink: 17652          IceNET: 7654
        Compiler:  Borland C++ v3.0, TurboC++ v2.0
        Machine Type: 80486

803-731-0690  The Trading Post [SOUTH]          [30646] Morgul
        BPS: 16800 <!$ (1)     MOD: DM                  Craig Dooley
        ASV                    MT: Desqview             Columbia, SC
        WWIVnet: 8315          WWIVLink: 18315          IceNET: 8315
        Solarnet: 8315         FILENet: 350 (GC2)
        Compiler: Borland C++ v3.1
        Machine Type: 386DX/40

812-877-4342  The Resource Center               [11030] Parapuke
        BSP: 14400 <!$ (1)     MOD: DM                  John Wheeler
        ASV GSA SDS            MT: Desqview             Terre Haute, IN
        WWIVnet: 8251          WWIVLink: 18251          IceNET: 8251
        Solarnet: 8251         TardisNet:8251           Apex:  8251
        Compiler: Turbo C++
        Machine Type: Packard Bell 386SX/16

818-848-4101  Blue Thunder BBS                  [21232] JAFO
        BPS: 16800 <!$ (1)     MOD: DM                  Cris McRae
        ASV                    MT: DESQview             Burbank, CA
        WWIVnet: 8861          WWIVLink: 18857          IceNET: 8857
        Compiler: Borland C++ v3.1
        Machine Type: 486DX/33

812-299-8621  God Only Knows                    [40412] Kilroy
        BPS: 14400     (1)     MOD: M                   Bill Altvater
                               MT:
        WWIVnet: 8253          WWIVLink:                IceNET:
        KILnet: 1 (NC)         ASSnet: 2005             SENnet: 8253
        ALTERnetIVE: 8253      APEX: 8253               SPEEDnet: 8253
        Compiler: Turbo C++ v3.0
        Machine Type: 386/20

916-222-8911  Maestro BBS                       [30305] Music Man
        BPS: 14400 !$  (2)     MOD: DM                  Chris Nicholson
        ASV                    MT: Windows v3.1         Redding, CA
        WWIVnet: 9680          WWIVLink:                IceNET: 9680
        USAnet: 1 (NC)
        Compiler: Borland C++ v3.1
        Machine Type: 80486 33

210-659-7267  Sam's BBS                         [21121] Sam
        BPS: 14400 <!$ ( )     MOD: DMC                 Sam Morris
        ASV                    MT: Desqview 2.61        San Antonio, TX
        WWIVnet: 2077          WWIVLink:                IceNET:
        Compiler: Borland C++ v2.0
        Machine Type: 486DX2/66

312-413-3914  ..Something Completely Different  [30658] Starship Trooper
        BPS: 14400 !$  (1)     MOD: DMC                 Matt Hucke
        ASV, GSA               MT: OS/2                 Chicago, IL
        WWIVnet: 3251          WWIVLink:                IceNET:
        Compiler: Borland C++ v3.1 w/AF, Borland C++ for OS/2 v1.0
        Machine Type: 486SX

314-821-7985  The Land of the Little People     [40266] Little Jon
        BPS: 14400     (1)     MOD: DMC                 Jon Feldmann
        ASV, GSA               MT: DESQview             St. Louis, MO
        WWIVnet: 3495          WWIVLink:                IceNET:
        SOLARnet: 3494         BREWnet: 11
        Compiler: Turbo C++ v3.0
        Machine Type: 386/25

319-296-1529  HIT BBS                           [10914] Jim
        BPS: 16800 <!$ (1)     MOD: DMC                 Jim Wire
        ASV, GSA               MT: DV, WIN, OS/2        Waterloo, IA
        WWIVnet: 3950          WWIVLink: 13950          IceNET: 3950
        Compiler: Borland C++ v3.1 (Borland C++ v4.0 on order)
        Machine Type: 8086, 8088, 80286, 80386SX, 80386DX, 80486DX
        * Prices may vary with experience and knowledge level of the
          recipient sysop

410-850-0871  The White House BBS               [40203] The President
        BPS: 14400 !$  (1)     MOD: DMC                 Michael Jewell
        ASV, GSA               MT: DesqView v2.60       Linthicum, MD
        WWIVnet: 4071          WWIVLink: 14063          IceNET:
        Compiler: Turbo C++ v1.01
        Machine Type: 80486DX/40

502-358-3087  THE OUTLAW BBS                    [30134] Maintech
        BPS: 14400 !$  (1)     MOD: DMC                 Dennis Thompson
        ASV                    MT: Desqview             Hodgenville, KY
        WWIVnet: 5211          WWIVLink:                IceNET:
        Compiler: Turbo C++ v1.0, v3.0
        Machine type: 386DX

801-774-5574  The Sandbox ][                    [11107] Sandman
        BPS: 14400 <!$ (1)     MOD: DMC                 Warren Reed
        ASV, SDS               MT: Windows 3.1          Ogden, UT
        WWIVnet: 8135          WWIVLink:                IceNET: 8135
        Ogdennet: 1
        Compiler: Borland C++ v3.1
        Machine Type: IBM 386DX/40

804-766-3192  Collage                           [20916] Dr Diversity
        BPS: 14400 !$  (1)     MOD: DMC                 Don Smith
        ASV                    MT: Desqview             Hampton, VA
        WWIVnet: 8433          WWIVLink: 18433          IceNET: 8400 (GC1)
        Compiler: Borland C++ v3.1, Turbo C++ v3.0
        Machine Type: 386/33 w/387

812-232-1821  SpellSinger ][                    [30675] Strange Brew
        BPS: 2400      (1)     MOD: DMC
                               MT: DV                   Terre Haute, IN
        WWIVnet:               WWIVLink: 18250          IceNET:
        RadsNet: 8250          ASSnet: 2010
        Compiler: Borland C++ v3.1
        Machine Type: 386SX/25

910-924-2373  InFiNiTe rEaLiTy BBS              [40551] Metal Maniac
        BPS: 14400 <!$  (1)    MOD: DMC                 Justin Jackson
        GSA, ASV               MT: OS/2 v2.1            Pfafftown, NC
        WWIVnet: 29971         WWIVLink: Pending        IceNET: 9958
        RealityNet: 1 (NC)     TERRAnet: 9958
        Compiler: Turbo C++ v1.0, Borland C++ v3.1
        Machine Type: 486

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Legend:

BBS Phone Number  BBS Name                      [REG #] SysOp Handle
        BBS Rate    (Nodes)    Service Offered          SysOp Real Name
        Special Features       Multitasker              Location of BBS
        WWIVnet Info           WWIVLink Info            IceNET Info
        OTHERnet Info
        Compiler / Machine Info

Special Features:  ASV - Auto Sysop Validation         Star - Starlinkable
                   SDS - Source Distribution Site
                  IPSS - IceNET Primary Support Site
                   GSA - Guest Sysop Account (Email #1 @node for details)

Modem INFO Codes:  / CompuCom CSP       ! V32              $ V32bis
                   < USRobotics HST     > Hayes V Series
Note:  BBS Rate listed is actual top DTE speed

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³          Filo's Mod of the Month            ³
               ³              by Filo (1@2050)               ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

The Mod of the Month is selected by Filo and represents his choice of what
appears to be the most promising mod posted during the past month on the Modnet
(subtype 2370). UUencoded mods are not considered for selection as part of the
mod of the month due to the difficulty of including them in the WWIVnews. Mods
which involve the use of related files such as ENHANCE.C, or any of the 
various COMMON type files are also not considered due to the amount of space 
required to include them here. Many of these mods have NOT been tested by Filo
and are selected based on their description as a promising, practical mod.

The mod for March-April was submitted by Dave Wallace:

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Dave Wallace #1 @5806
Mon Feb 28 19:37:05 1994

Identifier:     DAW2318A
Name:           QRZ.MOD
By:             Dave Wallace (1@5806)
Purpose:        This mod will display the list of all users with amateur
                radio callsigns. (What's the point of asking for the data
                otherwise?)
Version:        Revision A
Issue Date:     02-28-94
Target:         WWIV Version 4.23
Status:         Initial release
Difficulty:     Relatively simple
Description:    When a user types //QRZ (QRZ is the ham abbreviation for "who
                is calling?" or "who is on this frequency?"), the userlist is
                scanned and all currently-active accounts whose callsign field
                is not empty are listed.

Revision A:     The original release restricted the use of //QRZ to co-sysop
                and above users. This version, by moving the command-invoking
                code to a bit further down in the mainmenu function, allows 
                any user to view the list of hams.

Key:

    /* =QRZ */      find this line
    // -QRZ         delete this line
    /* +QRZ */      add this line


Installation:

1. In BBS.C, add the following new function at the top, just before
    int checkpw(void):

/* +QRZ */  void list_hams(void)
/* +QRZ */  {
/* +QRZ */    int i, abort;
/* +QRZ */    userrec u;
/* +QRZ */    char s1[51];
/* +QRZ */  
/* +QRZ */    abort=0;
/* +QRZ */    nl();
/* +QRZ */    pla("               \003"
/* +QRZ */        "4        Users with Ham Radio Callsigns       ", &abort);
/* +QRZ */    pla("               \003"
/* +QRZ */        "4          User's Handle            Callsign  ", &abort);
/* +QRZ */    if (okansi()) {
/* +QRZ */        pla("               \003"
/* +QRZ */         "4ÉÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍËÍÍÍÍÍÍÍÍÍÍ»", &abort);
/* +QRZ */    } else {
/* +QRZ */        pla("               \003"
/* +QRZ */          "4+--------------------------------+----------+", &abort);
/* +QRZ */    }
/* +QRZ */    read_status();
/* +QRZ */    for (i=0; (i<status.users) && (!abort) && (!hangup); i++) {
/* +QRZ */      read_user(i,&u);
/* +QRZ */      if ((u.inact != inact_deleted) && (u.callsign[0])) {
/* +QRZ */        sprintf(s1,"               \003"
/* +QRZ */             "4%c %-30s %c  %-7s %c", (okansi() ? 'º' : '|'), u.name,
/* +QRZ */        (okansi() ? 'º' : '|'), u.callsign, (okansi() ? 'º' : '|'));
/* +QRZ */        pla(s1,&abort);
/* +QRZ */      }
/* +QRZ */    }
/* +QRZ */    if (okansi()) {
/* +QRZ */        pla("               \003"
/* +QRZ */          "4ÈÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÊÍÍÍÍÍÍÍÍÍÍ¼", &abort);
/* +QRZ */    } else {
/* +QRZ */        pla("               \003"
/* +QRZ */          "4+--------------------------------+----------+", &abort);
/* +QRZ */    }
/* +QRZ */    nl();
/* +QRZ */  }


2. Later in BBS.C, make this change to void mainmenu(void):

/* =QRZ */    if ((strcmp(s,"NET")==0) || (strncmp(s,"NET=",4)==0))
/* =QRZ */      print_net_listing(0);
/* +QRZ */    if (strcmp(s, "QRZ") == 0) {
/* +QRZ */      list_hams();
/* +QRZ */    }
/* =QRZ */    if (strcmp(s,"QSCAN")==0) {
/* =QRZ */      nl();


3. Recompile. Should be quick -- you only changed one file.


4. Add //QRZ to the slash-commands menu (menu #15).

5. If you have my MODLIST mod installed, the CHANGES.MSG description line
    for this mod is:

QRZ         02-23-94    1@5806     Display all users with amateur radio calls.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ


The Mod of the Month for May-June was written by Spotnick, who incidentally 
is one of those most instrumental in providing the French menus and string 
files for WWIV.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

   ÚÂÄÄÄ ÄÄ  Ä   Ä  ÄÄ ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄ ùù
   ³³                    Alternative Worlds Presents                      ³
   ÀÅÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
   ³³ Mod Name       ¯ ALTW-13.MOD                                        ³ù
   ³³ Difficulty     ¯ Û±±±±±±±±±± (1/10)                                 ³:
   ³³ WWIV Version   ¯ 4.23 and higher                                    ³³
   ³³ Date Affected  ¯ 06/04/94                                           ³³
   :³ Files Affected ¯ COM.C                                              ³³
   ù³ Description    ¯ Multilingual Yes/No Prompts Toggable With Space    ³³
    ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÅ¿
    ³     A French Mod Division Release - (C) 1994 Logicom Softwares      ³³
ùù ÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ ÄÄ  Ä   Ä  ÄÄ ÄÄÄÀÙ

 ÚÂÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¿
 ³³ Long Description ³³
  ÀÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÁÙ

    This is an update to SPOT015.MOD. Actually all it does is to display
a yes/no prompts in the language of the user, and this prompt is toggable by
hitting the space key. It's easy to install and it is very useful.

ÄÄÄ[Step 1]ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Load COM.C and add this function before int yn(..) :

void rprompt(int pos, int redo)
{
 int i,i2;

 if (!wfc) {
 i2=(strlen(str_yes)+strlen(str_no)+5);
 if (redo)
   for (i=0;i<i2;i++)
     npr("\b");
   if (pos==0)
    npr("7[3%s/4%s7]9: ",str_yes,str_no);0
   else
   if (pos==1)
      npr("7[4%s3/%s7]9: ",str_yes,str_no);0
    }

}


ÄÄÄ[Step 2]ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Remplace the following 2 functions:


int yn(void)
/* The keyboard is checked for either a Y, N, or C/R to be hit. C/R is
 * assumed to be the same as a N. Yes or No is output, and yn is set to
 * zero if No was returned, and yn() is non-zero if Y was hit.
 */
{
  char ch=0,pos=0,done=0;

  rprompt(pos,0);
  do {
  ch=upcase(getkey());
  if (ch==*str_yes)
    done=1;
  if (ch==13) {
    if (pos==0)
      ch=*str_no;
    else
      ch=*str_yes;
    done=1;
  }
  if (ch==*str_no) {
      done=1;
    }
  if ((ch==32) || (ch=='')) {
     if (pos==0)
       pos=1;
     else
       pos=0;
     rprompt(pos,1);
     done=0;
    }

  } while((!done) && (!hangup));
    if (ch==*str_yes)
      print_yn(2);
    else
      print_yn(3);
    return(ch == *str_yes);
}



int ny(void)
/* This is the same as yn(), except C/R is assumed to be "Y" */
{
  char ch=0,pos=1,done=0;

  rprompt(pos,0);
  do {
  ch=upcase(getkey());
  if (ch==*str_yes)
    done=1;
  if (ch==13) {
    if (pos==0)
      ch=*str_no;
    else
      ch=*str_yes;
    done=1;
  }
  if (ch==*str_no) {
      done=1;
    }
  if (ch==32) {
     if (pos==0)
       pos=1;
     else
       pos=0;
     rprompt(pos,1);
     done=0;
    }
  } while((!done) && (!hangup));
  if (ch==*str_no)
    print_yn(3);
  else
    print_yn(2);
  return((ch == *str_yes) || (ch==13));
}

ÄÄÄ[Step 3]ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Compile back the BBS and you're done.


French Proverb: Un tien vaut mieux que deux tu l'auras.

For comments, bug report and suggestion, e-mail at the following address:

Spotnick    1 @5497 (soon to be @20397)
Dark Shadow 3 @5497


French Division Support Sub: Sub Type "ESE", Host 5497. A Must!

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³             Dateline: @#$*()#!              ³
               ³    Editor's Notes by Omega Man (1@15117)    ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ
Is it my turn on the soapbox yet? It is? Good, because I've got quite a few
things to cover this issue...


THE GRAND NETWORK RENUMBERING
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

By the time you read this, Wayne should have implemented Stage 2 of the 
WWIVNet renumbering scheme. As this went to press, this had not taken place,
and as a result most of the network addresses listed for the authors of the
articles you see here in this issue are probably not going to be accurate
by the time you read this. This was an editorial decision, and one that I
suspected would happen based on the timing of both this issue's release and
Wayne's desire to implement Stage 2 prior to WWIVCon.

So, if you wish to correspond to one of the authors whose words of wit appear
in this issue, you might want to doublecheck those network addresses before
you send that E-Mail off to never-never-neverland.


WW4NEWS?
ÄÄÄÄÄÄÄÄ

Ok, ok, ye editor decided to get a little humorous with the title of this
issue. This isn't a permanent change, obviously :-)


WWIVCON
ÄÄÄÄÄÄÄ

As most of you know, I will be unable to attend this year's WWIVCon for 
several reasons, most of which were job-related. I sincerely hope everyone
that does show up has an enjoyable time, and doesn't let H2O Doc and Filo
tear up the hotel too much during the post-seminar debaucheries I'm told will
occur.

I would, however, like to make an aside note of commentary to the organizers
of WWIVCon itself, one that echos some of the sentiments surrounding the
organization and promotion prior to the event.

Folks, WWIVCon needed to be promoted -quite- a bit more than it was this 
time around. There were a lot of people complaining on the WWIVCon'94 sub
as well as directly to myself through E-Mails to WWIVNews about "how little
[they're] plugging the event, and how repeated requests to [the organizers]
for event schedules are being ignored!"

Now, while Filo posted a rough event schedule just after the last round of
"what the -hell- is going on?" postings on the WWIVCon'94 sub, quite a few
people had already reversed their decisions on attending the convention.
For many, a trip to New Orleans - especially during the July 4th Weekend - 
is somewhat of a financial burden. Those who cancelled their plans did so
citing the lack of accessability to con information prior to attending,
which is something that simply shouldn't have happened in the first place.

Despite this, I suspect that WWIVCon will be considered enough of a success to
merit a repeat in '95. However, I strongly suggest that the organizers for
next year's convention should concentrate on getting the word out quite a
bit wider than it was this time around. The more people who know about an
event, the more people are likely to attend.

Finally, a suggestion for a location for WWIVCon'95: San Antonio, Tx would
be a perfect place to hold this event. There's numerous historical and
family-oriented landmarks and attractions in this city, and hotel rates
are actually a little bit cheaper than in N'Orleans. Oh, and the Riverwalk
is a great place to get blasted after the con, too!


ALT.BBS.RENEGADE?
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Word from the Internet/Usenet side of the fence tells of a proposal to create
an alt.bbs newsgroup dedicated to the Renegade BBS program. Renegade, as
most WWIV sysops are aware, is an acknowledged derivative of Telegard, which
in turn was derived from the unauthorized use of the source code for WWIV
3.21d. While the formal Request for Discussion (RFD) will no doubt garner
quite a few flame wars, considering the heated nature of this particular
topic, one can't help but wonder that if the Call for Votes (CFV) for this
newsgroup manages to pass, will comp.piracy.for.fun.and.profit be far behind?

Regardless of how this turns out, it might be wise to look into at least an
RFD for comp.bbs.wwiv, seeing as how WWIVnet-Usenet gateways are beginning
to proliferate these days...


INTERNAL QWK FOR WWIV
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

This seems to be one of -the- hot topics on the sysop subs these days, with
the dividing lines being set three ways: those who want a -free-, built-in
internal .QWK manager - whether it be by Wayne or by someone else's mod -  
those who are external .QWK developers, and those who don't want -either- on 
their systems. Needless to say, there have been a few heated commentaries, and
as you've seen already some of the more "sedate" ones were reprinted in the 
Type 0 Forum for this issue of WWIVNews.

My own opinion tends to side with those who want a basic-featured 100% Wayne 
Bell-written or installed internal .QWK manager. However, I also side somewhat
with the designers of the external managers in the fact that were such a 
feature added internally to WWIV, it should be toggleable only through a 
#define, which of course requires that you be a registered WWIV sysop with
an equally registered copy of the source code. This fence straddling approach
addresses the two major concerns surrounding this particular improvement:

In case you haven't noticed it yet, those siding against inclusion of an 
internal .QWK manager into WWIV come from two different camps - those who 
don't want to waste memory on a feature they don't use or need, and those who
actually -write- external .QWK managers. The former is comprised of sysops 
whose systems are a bit short on memory for any number of reasons, and need 
WWIV to remain as small as possible while within conventional memory. Those 
in the latter category, of course, are looking out not only for their own 
finanical interests, but for the interests of those in the first category as 
well.

On the other side of that fence, those supporting an internal .QWK manager do
so for several reasons. Most agree that making .QWK management an internal 
part of WWIV would solve three major problems cited with external managers: 
special configuration problems, external shrinking lockups, and difficulties 
regarding customer support. All three of these problems, most proponents claim,
would be eliminated if Wayne were to incorporate a basic-featured QWK manager 
in WWIV; after all, if a bug can't be fixed by Wayne in a timely fashion, the 
source code would at least be available for -someone- to devise a fix. At the
same time, those writing external managers can continue to do so without fear
of losing too much business. As the internal QWK manager would only have the
very basis features, external QWK authors would be free to continue development
of their utilities, and use whatever extra features their programs provide as 
their selling point.

Such a modification already exists, as the autobiographical article by the
Asylum Group in this issue explains. 

While I have not personally installed or used a WWIV BBS that has such an 
internal manager, all the reports I've received regarding the Asylum/QWK mod
have been either on the borderline of "flawless performance!" or "It crashed
my system, but that's because I goofed up with some cut & paste in Borland's
crappy editor!" It's these latter types of reports that has me convinced that
a pre-installed, but #defineable internal QWK manager is preferable to 
expecting everyone to install such a complex mod from scratch.

Wayne has stated that no internal QWK manager is planned for 4.24. However,
he did not rule out one for a later release of WWIV. Currently, a poll on
this topic is being conducted on several of the Sysop subs, and the results
will be posted in the next issue of WWIVNews. In the meantime, express your
opinions on this matter by participating in this poll, and by submitting 
your comments to the Type 0 Forum.


WWIV NETWORKS LISTING
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Some of you may have noticed a lack of this feature in this issue. This was
due to a loss of contact with Red Adept prior to press time. We should have
this problem rectified by next issue, and WWIVNews apologizes for any 
inconvenience this omission has caused.


COMING UP NEXT ISSUE
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

By next issue, 4.24 should either be out, or just seconds away from being
released. We'll have the latest news on this new release, as well as Filo's
first "mods of the month" specific to 4.24. The first reports from WWIVCon
will be out, and WWIVNews will have those, as well as the first site proposals
for WWIVCon'95. We'll also have more commentary on the "internal QWK" debate, 
an update on "comp.bbs.renegade?", as well as the usual plethora of news and 
information. 

Until then, folks, don't give, back WWIV!


ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³                             Closing Credits                               ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³ WWIVnews is an independent newsletter NORMALLY published every 6 weeks as ³
³ a service to the WWIV community of sysops & users. The opinions & reviews ³
³ expressed herein are the expressed views of the respective writers, & do  ³
³ not necessarily reflect those of the WWIVnews staff. Reproduction in whole³
³ or in part is allowed provided credits are given. All rights reserved by  ³
³ WWIVnews, and all articles are copyright of their respective authors.     ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³ The source site for WWIVnews is the Klingon Empire BBS (512-459-1088),    ³
³ WWIVnet node @15117. Requests for information regarding articles & other  ³
³ editorial submissions, as well as back issue requests and the WWIVnews    ³
³ Writer's Guide, can be sent E-Mail to the WWIVnews editor, c/o 1@15117    ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³            WWIV and WWIVnet, copyright 1986,1990 by Wayne Bell            ³
³  Any product or company mentioned or reviewed herein are copyrighted of   ³
³  their respective owners, creators, and other corporate pseudoentities.   ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

```
