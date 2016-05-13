```

                          WWIVNEWS Volume 1, Issue 4
                                  April 1991


                               Table of Contents
                               ~~~~~~~~~~~~~~~~~
    WWIVNews Intro Contest Submissions..............................Various
    Stop the Hack Attack...........................Bethnal the Black 2@5465
    FidoNet from a WWIVnet Perspective..................East Bay Ray 1@9964
    The Pending File.........................................WWIVNEWS Staff
    The Editor's Corner.................................East Bay Ray 1@9964
    Acknowledgements.........................................WWIVNEWS Staff
    =======================================================================


                      WWIVNews Intro Contest Submissions


                                 Xavier 1@9409
                                 -------------

       /\          /\
       \W\  /\    /W/
        \W\/W/\  /W/
         \W /  \/W/
          \/    \/     /\          /\
                       \W\  /\    /W/
                        \W\/W/\  /W/
                         \W /  \/W/      ___________
                          \/    \/      [IIIIIIIIII]
                                             /I/
                                             /I/
                                             /I/        /\      /\
                                         ___ /I/____    \V\    /V/
                                        [IIIIIIIIII]     \V\  /V/
                                                          \V\/V/
                                                           \V /
                                                            \/       NEWS!


                              Agent Steel 1@6556
                              ------------------
    _________          __          __
   _____  / / __  __  / / __  __  __  __ __    ____    ______________________
  _____  / / / / / / / / / / / / / / / // /   ____    ______________________
 _____  / /_/ /_/ / / /_/ /_/ / / / / // /   ____    ______________________
       /_________/ /_________/ /_/  \___/   ____    ______________________
      ___________________________________________________________________
     ___________________________________    __________          _____________
    ___________________    ____    / __ \  ______    / __  __  ______
   ___________________    ____    / / / / / ____/ / / / / / / /___  / _____
  ___________________    ____    / / / / / /___  / /_/ /_/ /_____/ / _____
 ___________________    ____    /_/ /_/ /_____/ /_________/_______/ _____



                                Bro John 1@4701
                                ---------------

             ------===*   \    / \    /   :   \  /   *===---------
           ------=====:    \/\/   \/\/   _:_   \/    :=====---------
         ------=======:           __           __    :=======---------
      -------=========:    :\ :  :__  \    /  :_     :=========---------
    -------===========:    : \:  :__   \/\/   __:    :===========---------
      -------=========:                              :=========---------
         ------=======:   Volume:     Issue:         :=======---------
           ------=====*_          (Date)            _*=====---------
    =======================================================================


                             Stop the Hack Attack
                          by Bethnal the Black 2@5465


          A recent rash of WWIV Hacking in the Montreal area has shown me
    that there are too many SysOps who are not taking the right precautions
    to make their systems safe and secure.
          Simple things, like backups, seem foreign to most SysOps, but
    this is the first line of defense against a crash, hacked or otherwise.
    Regular backups need not be a time consuming activity.  Once the
    initial system backup has been done, incremental backups of the disk
    may take as little as 10 minutes.  Backing up to disk may not be the
    most enjoyable task, but it isn't life threatening either.  It may save
    you quite a bit of time and trouble later.
          Once you have the backup situation covered, you can start doing
    things that will ensure that you will never have to use those disks.
          The first step is to protect yourself from yourself!  Ever
    accidentally erase a file?  Not too difficult to do, really, but quite
    easy to prevent. DOS has provided a command called ATTRIB that allows
    you to set the Read-Only flag on any DOS file.  Start with COMMAND.COM,
    AUTOEXEC.BAT, CONFIG.SYS, BBS.COM, BBS.EXE and anything else that you
    can think of.  If these files are set as Read-Only they cannot be
    deleted accidentally or clobbered by some vicious hacker. Protecting
    COMMAND.COM also has the added benefit of stopping a large number of
    virii from infecting your system.
          If we look specifically at the most recent Hack making the rounds
    (the PKUNZIP extraction hack), we can use a feature of the INIT.EXE
    program.  Simply restrict all Uploads to SysOp and check everything
    that comes into your board before making it available for download
    (and, therefore, Extractable-to-TEMP).  This is not always easy,
    especially if you get a lot of uploads, but it is the best way to
    insure safety from this particular hack.  Another good stopper for this
    one is Wayne Bell's UNZIP program.  Better yet, just remove the extract
    option all together, has anyone ever used it?
          I think it is also important to remember one of the basic rules
    of computer security: change your passwords (your's and the System's)
    regularly.  This practice applies to all your users and should be
    enforced for your high access accounts.  Also, don't give your system
    password to anybody that you don't know (or can't kill), and, even
    then, only if ABSOLUTELY necessary.  If you never log onto your BBS
    remotely, make your password totally random, so that even you wouldn't
    know it.
          Voice validation is another way of ensuring that your users act
    responsibly (you have their phone number and they know it).  It doesn't
    have to be a 20 minute conversation, either.  Just a quick chat to let
    him know what the BBS is all about and what you expect from him, as a
    user.  It gives the user the feeling of being wanted, and it gives you
    the chance to size him up and decide if he is someone who needs to be
    watched, or maybe even restricted.
          I realize that you have probably heard most of this stuff before,
    and some of you probably know more ways to protect your BBS from
    damage, but for the rest of you, I hope this has given you some insight
    into how you can protect that investment of time and effort that we all
    call "The Board".
          I invite, and appreciate, your comments.
    =======================================================================


                      FidoNet from a WWIVnet Perspective
                              East Bay Ray 1@9964

          The popularity of being a FidoNet gate to WWIVnet is growing
    rapidly these days.  Just check out a //NET listing and see how many
    node numbers are in the @600-@699 range.  However, many sysops are
    confused when they first plunge into FidoNet, because the two networks
    are indeed vastly different.  In this article I will address some of
    the major differences between FidoNet and WWIVnet, from a fundamental
    point of view.  It would take at least a book to do the same from a
    software point of view.
          First of all, you are not dealing with a single type of BBS
    software.  You are not even dealing with a single type of operating
    system, or computer.  There are FidoNet systems being run on DEC
    Rainbows, Ataris, Apples, as well as PCs running (other than MS-DOS)
    OS/2, UNIX, and PC-MOS.  You must realize this, because unlike WWIVnet,
    everybody doesn't run the same software, and most people will have
    different problems than you will.  Some FidoNet software is even
    commercial!
          Second, there are several different pieces of networking software
    available.  You don't just have one author and one set of programs to
    use, you have a diverse number of choices.  The software is mainly
    divided up into two categories:  mailers and messaging software.
          A mailer, also called a front-end, is a program that you run that
    connects you with other FidoNet systems.  With this mailer you can dial
    out and send FidoNet packets and files to other FidoNet systems, and
    receive them as well.  These mailers are also the driving force behind
    FREQing, or "File REQuesting".  Sysops that have heard of Snarf have an
    idea of what this is.  A mailer can call another mailer, and request a
    file.  It can also call that system and request a file.  All this is
    done in the same program.
          The second major portion of FidoNet software is the messaging
    software.  These programs are the ones that unARC or unZIP the packets
    received from the mailers, and put them into message directories.
    Surprised?  Yes, FidoNet got wise a long time ago and started sending
    compressed mail between systems.  Most FidoNet-compatible BBS systems
    can directly read the messages output by the messaging software.  WWIV
    sysop, however, must take an extra step to get the FidoNet mail to
    their boards.  This program is called NetSEX, and it will be explained
    in detail a little bit later in this article.
          The third major difference between FidoNet and WWIVnet is that
    mail is not as structured in FidoNet.  If you want to, and the other
    guy is not too excessively annoyed, you can connect to anyone you want
    to pretty much.  This practice isn't very smart, but it is a
    possibility.  Another, more realistic example is if you really want to
    get a piece of mail to someone across the country, then you can simply
    "Crash Mail" him.  This is a practice where, after you write the
    letter, you call his system directly and send him your letter.  It
    really speeds things up sometimes.
          Before I go any further, I wish to introduce some new terms.
    These are basically synonyms, but FidoNet terms nevertheless.
          The first is netmail, which e-mail, or net e-mail in WWIVnet.  In
    FidoNet, some regions have routed netmail, where you can send a piece
    of netmail to any place in the country, and it will go the longer, but
    cheaper route (much like WWIVnet).  In other regions, netmail must go
    directly to the destination system, or it goes not at all.
          The second term is echomail.  Echomail is synonymous with a
    WWIVnet post.  However, echomail "conferences" (net subs) are vastly
    different than WWIVnet ones.  FidoNet echomail conferences are, by
    WWIVnet standards, free-for-alls.  Although there are appointed
    moderators, these moderators have little knowledge of who is picking up
    their conference, and have little control over who it goes to.
          Another FidoNet concept that cannot be used currently in WWIVnet
    is message threading, or reply-chaining.  This technique employed by
    most BBS systems to some degree allows all the posts relating to the
    same topic to be read at the same time, regardless of when they were
    posted.  This makes reading messages infinitely easier on the reader.
          NODELIST.  This file is a huge file that contains a listing of
    all the FidoNet systems currently in the network, yet it IS NOT
    distributed on any basis, regular or irregular.  Since it is close to a
    megabyte (around 9500 systems in FidoNet so far), it would be highly
    impractical to send this file out.  Those poor 300 (yes, there are a
    couple) and 1200 baud systems would spent their entire weeks just
    downloading the NODELIST.  Instead, weekly NODEDIFFs are distributed in
    compressed format (ARC, ZIP, LZH, etc.).  A NODEDIFF file contains the
    difference between last weeks NODELIST and this week's.
          That is about all I can think of at the present time.  Besides
    NetSEX (the utility required to interface WWIV and FidoNet, available
    as NETS100.ZIP), I have pretty much left FidoNet software untouched.
    Hopefully in some future issues some of the people in WWIVnet who know
    more about FidoNet software will write some reviews.  Heavy 7, Benny
    Hill, Pierre Tremblay, Darkster, Otto (grin)...
    =======================================================================


                               The Pending File
                           (Tips, Tricks, and News)
                               by WWIVNEWS Staff

    Wayne Bell, due to the recent upsurge of hack paranoia, has released a
    PKUNZIP front end called UNZIP.  This program scans all the files in a
    ZIP before extraction, and if there is a suspicious file present, it
    will bar extraction from that ZIP completely.  It looks for directory
    denotations ("\" and "/"), PKZIP and PKUNZIP, UNZIP, and a couple other
    strings.

    Black Dragon 1@2380 has released a new version of his Network Editor
    (NETEDIT).  Here are the release notes from the v1.28 READ.ME file:
              The search command now allows more than just a BBS name
         match.  This command has been expanded to search similiarly
         to WWIV v4.07's //UEDIT search command.  In addition, for the
         registered version, the network may now analyze around any
         temporarily disabled node.  The analyze routine was fixed
         with respect to CALLOUT.NET entries which were listed as
         receive only. Lastly, some menus were redone.

    -I- have released a Windows 3.0 PIF and icon (along with a short doc
    file detailing running WWIV and Windows) as WW4WNDWS.ZIP.  I am sorry
    to say, however, that Wayne -hates- Windows with a passion, so I doubt
    there is much hope of a Windows-aware WWIV anytime.
    =======================================================================


                              The Editor's Corner
                            by East Bay Ray 1@9964


          Hello again, cowboys, cowgirls, and cowneuters.  This is another
    fun-filled issue of WWIVNews.  This month's editor's corner is devoted
    to begging.  I am begging for some submissions.  Even human interest
    stories are OK, as long as the relate to WWIV or the BBS industry
    somehow.  For example, if you consider your dog or cat as a co-sysop,
    write it up!  If you have an opinion on the "I've fallen and I can't
    get up!" commercial, and it relates to WWIV, write it up!  We need some
    submissions!
    =======================================================================


                               Acknowledgements

    WWIV (c) 1988 by Wayne Bell.
    All other products mentioned are either registered trademarks or
      copyrighted by their respectives manufacturers.
    =======================================================================


                                    The End

```
