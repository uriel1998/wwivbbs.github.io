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

                               Volume 1, Issue 5
                                   May 1991


                               Table of Contents
                               ~~~~~~~~~~~~~~~~~
    WWIVNews Intro Contest Submissions II...........................Various
    NET24 Release Notes..........................................Random 1@1
    Why Register WWIV?.................................Shadow Master 1@9979
    Hack Scare MCXXVIII with Fix..........................Eight Ball 1@6909
    The Pending File.........................................WWIVNEWS Staff
    The Editor's Corner.................................East Bay Ray 1@9964
    Acknowledgements.........................................WWIVNEWS Staff
    =======================================================================


                     WWIVNews Intro Contest Submissions II


                                 Venom 2@7707
                                 ------------
    _______________________________________________________________________
     __         ____         __   __     __
     \\\       ///\\\       ///:[]\\\   ///              "title of issue:
      \\\  /\ ///  \\\  /\ /// :[] \\\ ///
       \\\//\\//    \\\//\\//  :[]  \\\//     VOLUME:
        \\/ \\/      \\/ \\/   :[]   \\/      DATE  :
                                              ISSUE :
              -*NEWS*-
    _______________________________________________________________________


                          Hard Rock 204@9964 (Winner)
                          ---------------------------
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
    =======================================================================


                       NET24 Release Notes (README.NET)
                                 by Random 1@1

          The most significant change to this release (NET24) of the
    network software is the option to compress (Zip) network packets.  If
    enabled, the network software will analyze the P0.NET and P1.NET
    (pending) files and compress the messages/mail for those nodes for
    which you have compression enabled.  When a compressed packet is
    received by your system (from another node), the network software will
    de-compress the packet prior to analyzing it.  All compressing and
    de-compressing is done by the network software.  PKzip or other
    compression programs are NOT called nor used.
          To enable network compression for an existing connection, simply
    add a semicolon (;) to the modifiers located in CALLOUT.NET.  For
    example, compression enabled for an existing connection with @1234
    (depending which modifiers are in use) could look like:

    @1234             &     ;                  "ABCDEFGHIJKLMNO"

    (The semicolon can be placed just about anywhere along with the other
    modifiers)

          BE SURE to ensure that the system you are compressing net packets
    for is also running at least NET24.  ONLY NET24 (and higher) supports
    net compression (not previous releases).  So in order for compression
    to be used for a connection, BOTH sides HAVE to be running at least
    NET24. MAKE SURE that the other connection is using at least NET24
    BEFORE enabling compression.
          Compressed files are stored in the Data directory starting with
    the letter 'Z' (ie: Z1234.NET would be a compressed packet for node
    1234).  Data for non-compressed connections is still stored starting
    with the letter 'S' (ie: S5678.NET).  After adding the semicolon for
    newly enabled 'compressed' connections, run NETWORK1.  Doing so will
    convert pending 'S' files to compressed 'Z' files.  To avoid having the
    network software re-analyze everything, 'touch' BBSDATA.NET prior to
    re-starting the BBS.  [Ed.- TOUCH is a utility included with most
    Borland programming languages which will update any file's timestamp to
    the current time and date.]
          The network1.exe program is the program which actually does the
    compression/decompression.  The compression technique used is the
    implode method used by PKzip.  The actual compression/decompression
    routines are from the PKware Data Compression Library.  The compressed
    net packets are NOT .ZIP files, and cannot be viewed or processed at
    all by PKzip or any other archive program.
          Do not blindly assume that compression should be used for all of
    your net connections.  Whether or not compression is actually useful
    depends upon many things, such as if the connection is local or long
    distance, and whether or not the modems already support compression.
    If you are using net compression, do NOT use MNP5 for the connection.
    V.42bis is fine, however. V.42bis's ability to compress network packets
    is about the same as net compression, so if you have a V.42bis
    connection, you may be just as well off to not use net compression (and
    thus avoid the delay involved in compressing the network data).  If you
    have a local HST/V.32 connection that uses V.42bis, I would not suggest
    using net compression.
          I do not know how this version will interface with other network
    packing programs not written by me, since I don't use them.

    NOTE: LNET does not currently allow you to look at compressed network
    packets.
    =======================================================================


                              Why Register WWIV?
                            by Shadow Master 1@9979
                  (post captured and printed with permission)

          A couple of weeks ago, I recieved in the mail a sample of
    TeleComputing Magazine.  In the magazine, there was an ad for The Major
    BBS.  Anyway, the major feature about this BBS, is supposed to be its
    multi-line capability and its real-time group chat conferences. Anyway,
    going back to the ad I read, I thought I would like to share the quoted
    prices...

          The Major BBS (2 node capability)             $  59.00
          Source Code for BBS                           $ 285.00
          For Every Doubling Of # Of Nodes              $ 300.00
          Transfer Section (Yes ability to Ul/DL files) $ 199.00
          Source Code For Transfer Section              $ 159.00
          (Recquired To Be Able To Install External Protocols)
          OnLine Entertainment Section                  $ 149.00
          Source Code For Entertainment Section         $ 129.00
          Program To Create Your Own Menus              $ 149.00
          Source Code For The Above Program             $ 129.00
          -------------------------------------------------------
          GRAND TOTAL                                   $1558.00

          WWIV Registration                             $  50.00

          Now I know I have never used The Major BBS before, but aren't
    those prices ridiculous no matter how many features the BBS software
    has?  So what are we missing out on by using WWIV?  MultiLine . . .
    What are Sysops Of The Major BBS suffering from?  A) They are broke. B)
    They have no NET.
          I just thought I would post those figures for WWIV Sysops who
    might have been looking for alternate BBS programs.  My advice: Think
    Again!
    =======================================================================


                         Hack Scare MCXXVIII with Fix
                             by Eight Ball 1@6909

          I don't know if this was brought up the first time the
    NETWORK.COM hack scare went around, so if it has, I apologize.
    Otherwise, we have a very SERIOUS problem because

      *** THERE IS NO "CLEAN" FIX IF YOU ARE NOT A REGISTERED SYSOP. ***

          I did however create a fix for registered sysops.

          While I was away on spring break, a user used the auto-validation
    to get into the system and uploaded a file called YEAH.ZIP which he
    called "A mod I wrote to send files over the net!"  Inside were
    HACK.BAT and NETWORK.COM and we all know what those are for, right?
    When he extracted these, he extracted out "-D.*" out.  The -d switch to
    PKUNZIP tells it to extract out any directories in the archive.  He
    archived them with the paths, so that a pkunzip -v looked like this:

    Searching ZIP: YEAH.ZIP

     Length  Method   Size  Ratio   Date    Time   Attr  Name
     ------  ------   ----- -----   ----    ----   ----  ----
         20  Stored      20   0%  11-22-90  20:37   --w  /WWIV/HACK.BAT
      14301  Stored   14301   0%  11-23-90  21:03   --w  /WWIV/NETWORK.COM
     ------          ------  ---                         -------
      14321           14321   0%                               2

          Thus, even though I use the full-pathname and all the other hack
    protection business, he was able to get around it with the -D
    parameter.
          For some reason he was unsuccessful; all he managed to do was
    hang the system for three days.  In fact, I ran the hack myself and it
    got as far as the CTTY in HACK.BAT before hanging the system as busy.
    I still haven't figured out what the would-be hacker did wrong but I
    am thankful it didn't work.
          If you are not a registered sysop, the only recourse I see is
    renaming your BBS directory to something that isn't easily guessed,
    because if the hacker can guess what your BBS directory is, he can put
    the directory into the ZIP file and you're screwed.

                       *** REGISTERED SYSOPS READ ON ***

          If you are using the autovalidation mod, you can use the U
    restriction which forces uploads to the sysop directory.  Use this:

                     thisuser.restrict |= restrict_upload

          However, validated users could still use the hack.  The fix for
    this, for 4.11 and 4.12 sysops (should work with earlier versions) is
    this.  Load up XFER.C and look for int okfn (char *s). (It's the first
    function in my XFER.C)

    Before the line that says

      return(ok)

    add this:

      if (s[0]=='-')
        ok=0;

          This prevents anyone from using a dash as the first letter of ANY
    filename that gets checked with okfn (for instance, an uploaded file).

    [Ed.- Wayne Bell's UNZIP program, detailed in a previous issue,
    prevents this sort of PKZip hacking.  Personally, I would not recommend
    modding your source code at all, but instead using Wayne Bell's
    program.]
    =======================================================================


                               The Pending File
                           (Tips, Tricks, and News)
                               by WWIVNEWS Staff

    As it has been annouced elsewhere as well, NET24 is out and available
    on all the major support boards.  There is one smaller feature in NET24
    that many have clamored for, which Wayne did not mention in his release
    notes:  preferred server routing.  Now that mail servers are becoming
    more and more popular, NET24's NETWORK3 now gives mail servers
    preferred routing over other non-server connections.
    =======================================================================


                              The Editor's Corner
                            by East Bay Ray 1@9964

          Hola senores y senoritas!  Yes, we have a winner!  A guy who
    actually called my system and //UPLOADed his art.  My gratitude and
    sincere appreciate goes out to all the people who participated in the
    "cover" contest, they were all great entries.  It was a tough choice!
          Just about everybody, including the people in Lizard Lick, NC,
    know that NET24 is out. With the release of this software dawns a new
    age: The age of network compression. It was first brought (somewhat)
    with NetZip, then with NetZip II and WWIVPACK, and now Wayne has made
    both obsolete. He uses the PKZIP technology directly in his software,
    eliminating the need for any sort of program that would compress
    packets. For more details on this, see the NET24 release notes included
    elsewhere in this issue.
          Another issue to note is that John Hardman 2@9954 (Group 5 GC) is
    stepping down May 21 as GC, and leaving WWIVnet (and BBSing altogether)
    as of June 1.  WWIVnet will truly be sorry when he leaves, and many
    sysops will miss him.  This also brings up an interesting topic:  How
    will the next one be appointed?  As far as I know, John is the first GC
    to be replaced.  Will Wayne appoint one?  Will John oversee an election
    within Group 5, or will John (or Wayne) simply appoint a new GC?  This
    is a new step in WWIVnet history, and it will be interesting to see how
    it turns out.
          Another interesting issue is that the 919 area code is about 4
    nodes shy of being full, which means that 919 will need some new node
    numbers.  Where to go?  Wayne says 5 digit node numbers!  That is the
    obvious solution, since the possible range of node numbers runs between
    1 and 65534.  The main topic this issue brings to mind is what the
    sysops will do about sub types.  Since the traditional numbering system
    consists of adding a 1, 2, 3, 4, and then 5 to your node number, some
    sub type conflicts will probably arise.  Please send any suggestions,
    comments, etc. to WWIVNews, c/o 1@9964.
    =======================================================================


                               Acknowledgements

    WWIV (c) 1988 by Wayne Bell.
    All other products mentioned are either registered trademarks or
      copyrighted by their respectives manufacturers.
    =======================================================================


                                    The End


```
