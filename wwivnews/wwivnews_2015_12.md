
    oooooo   oooooo     oooo oooooo   oooooo     oooo ooooo oooooo     oooo
     `888.    `888.     .8'   `888.    `888.     .8'  `888'  `888.     .8'
      `888.   .8888.   .8'     `888.   .8888.   .8'    888    `888.   .8'
       `888  .8'`888. .8'       `888  .8'`888. .8'     888     `888. .8'
        `888.8'  `888.8'         `888.8'  `888.8'      888      `888.8'
         `888'    `888'           `888'    `888'       888       `888'
          `8'      `8'             `8'      `8'       o888o       `8'

        ooooo      ooo oooooooooooo oooooo   oooooo     oooo  .oooooo..o
        `888b.     `8' `888'     `8  `888.    `888.     .8'  d8P'    `Y8
         8 `88b.    8   888           `888.   .8888.   .8'   Y88bo.
         8   `88b.  8   888oooo8       `888  .8'`888. .8'     `"Y8888o.
         8     `88b.8   888    "        `888.8'  `888.8'          `"Y88b
         8       `888   888       o      `888'    `888'      oo     .d8P
        o8o        `8  o888ooooood8       `8'      `8'       8""88888P'

                            http://www.wwivbbs.org/
        
                                Volume 8 Issue 1
                                  Winter 2015


                                Table of Contents
                                ~~~~~~~~~~~~~~~~~
    WWIV BBS 5.0 Release......................................WWIV Dev Team
    WWIV and WWIVNet Update From The New NC..................Weatherman 1@1
    WWIV 5.1 Release Goals....................................Rushfan 1@514
    WWIV Links and Information.............................................
    =======================================================================

                            WWIV BBS 5.0 Release
                            - WWIV Dev Team -

    We are happy to announce WWIV 5.0 is available as the stable release of 
    WWIV BBS. WWIV 5.0 was under development for many years and finishing 
    is a significant milestone. 

    Download WWIV 5.0: https://github.com/wwivbbs/wwiv/releases
    WWIV 5.0 Installation and Docs: http://wwivbbs.readthedocs.org/
    
    Here are some of the great new things in WWIV 5.0
    
    File Compatible with 4.30 & 4.31
        Drop the WWIV 5.0 binaries into your 4.30 or 4.31 setup and fire 
        up WWIV 5.0.
    WWIV 5.0 Telnet Server
        WWWIV 5.0 has a telnet server included to allow client access
        to WWIV 5.0.
    Internal Zmodem Support
    ZIP/UNZIP Support Included
    Networkb.exe - BINKP transport for WWIV networking is now part of 
        the WWIV builds.
    Netutil.exe - Network packet and config file utility now included.
    Network.exe - shim to proxy between network0, networkp (PPP project) 
        and networkb.
    New User Sign Up Notification (SSM) to SysOp.
    Source Code now hosted on GitHub https://github.com/wwivbbs/wwiv
    Compiled with MSVC 2015
    Compiles and runs on Linux
    Door32.sys Support
    Syncfoss Support - Thanks to Rob Swindell
        FOSSIL can now be specified in WWIV.INI as a valid flag for spawn
        options.
    BBS.EXE -k command line to pack all message bases
        -k # # # will pack the massage bases with those IDs.
    New WWIV.INI Parameters
        EXEC_LOGSYNCFOSS     = [ 1 | 0 ] - If non-zero then 
            wwivsync.log will  be generated.  The default setting is 
            1 and this is currently ignored.
        EXEC_CHILDWAITTIME   = (time to wait in milliseconds, this 
            parameter is only used on Win9X unless EXEC_USEWAITFORIDLE is 
            set to 0. The default value is 500 (1/2 second).
        NEW_SCAN_AT_LOGIN= [Y|N] - If Y when a user logs  in they will be 
            asked to scan all message areas for new messages.
        TEMP_DIRECTORY = temp%n  - The name of the Temp directory relative
            to the wwiv root directory. %n specifies the instance number.
        BATCH_DIRECTORY = batch%n  - The name of the Batch directory 
            relative to the wwiv root directory. %n specifies the instance 
            number.
        NUM_INSTANCES = 4  - The Number of Instances to allow.
        NOTE: Directories are created on demand by the bbs on startup and 
            config.ovr will be created by legacy tools when you run init.  
        NO_NEWUSER_FEEDBACK = [Y|N] - If set to Y no newuser messages will 
            be sent at all.
    2 new pipe color codes:
        |#<wwiv color code 0-9> as an alternative to the "heart" codes
        |@<macro character> as an alternative to ^O^O<macro char>
        Existing pipe codes are: |B<background char>, and |<2 digit code> 
            for foreground colors.
    WWIV Message Editor Commands
        '/A' - Abort Message
        '/H' & '/?' - Help
    !!! Many Bug fixes !!!
    
    What has been deprecated in WWIV 5.0?
        Windows XP No Longer supported
        Support for Modems has been removed
        SPAWNOPT[FSED] is now unused and no longer supported

    =======================================================================
                    WWIV and WWIVNet Update From The New NC
                               By Weatherman 1@1

    As many know, lots of things have been happening with WWIV BBS and 
    WWIVnet over the past few years.  When Weather Station BBS came back 
    online as a virtual machine around three years ago, the only networks 
    that were available were FTN based.  About 7-8 months later, I was 
    approached by Eli Sanford to join WWIVSN (the early beginnings of the
    resurrected WWIVnet).  Eli spent lots of time helping others and 
    leading the path so that we could have a functional WWIV network like 
    years ago.

    On a very sad day (October 26, 2015), our WWIVnet leader Eli Sanford 
    passed from leukemia.  We were in shock and upset from the news. A few 
    weeks went by as we were mourning the loss of Eli and then later, 
    figuring out plans to keep WWIVnet alive.

    We agreed to meet in the WWIV chat room on Monday evening to decide 
    how to move forward.  The first item of business was determining the 
    new @1 node for WWIVnet.  Rushfan suggested myself and the rest of 
    the group was on-board with that change.  I was very humbled by the 
    votes of support and encouragement.  It has been my passion to keep 
    WWIV and WWIVnet alive in the most resiliant way possible.  My hardware
    setup is robust for a home environment and offers a good deal 
    redundancy. I will always do my best to make sure WWIVnet is running 
    the best way possible.

    That same night, we decided to make a historic change for WWIVnet.  
    We switched the entire network from using WINS (PPP Project) to 
    NetworkB (BinkP) written by Rushfan.  Given the magnatude of changes 
    that we made that night, I think it went fantastic!  We have been 
    running completely using BinkP for WWIVnet ever since.  It has proved 
    to be a major step forward!  I can't thank Rushfan enough for writing 
    that program, as that was a HUGE step forward!

    In more recent news, we now have the ability to send out network 
    updates using NetUp just like the legacy WWIVnet.  WSS provided a 
    new version of NetUp for WWIVnet which has been working 
    perfectly sending out network updates, subs listings, and even this
    WWIVnet news.  This brings us back to the functionality that we had 
    with the legacy WWIVnet.  It has been well over a decade since this was
    possible.

    I am completely honored to be a part of such an excellent group of 
    people that have done so much for WWIV and WWIVnet in the past few 
    years. Highlighting the past few months as just nothing short of 
    incredible with the move to NetworkB (BinkP).  That was as huge of a 
    change for WWIVnet as when we started moving network packets using 
    Frank Reid's PPP Project (SMTP).

    This has been a very fun road for our hobby and I'm very excited for 
    what the future holds.  I'm sure as more people discover our 
    milestones, additional people will re-connect and join our fantastic 
    group.  We will also not forget Eli and all the hard work he did to 
    start the WWIVnet comeback.

    Here is a toast to the bright future of WWIV and WWIVnet!

        - Weatherman (Mark)  1@1.WWIVnet 
    =======================================================================
                            WWIV 5.1 Release Goals
                                By Rushfan 1@514

                                Main Themes
                                ~~~~~~~~~~~
    Messages and WWIVNet have always been at the heart of WWIV. For 5.1, I 
    plan on modernizing and improving the internal code quality of the 
    messaging code, making it easier to embed into new tools. Included in 
    this will be support for the JAM Message Base format to broaden the 
    range of tools available for exposing message bases.
    
    More on JAM: https://en.wikipedia.org/wiki/JAM_Message_Base_Format

    Net38 will be finalized [currently Beta 6] and released supporting any 
    new changes to get WWIVNet functioning in the Internet era. 
    
    See all of the work targeted to Milestone 5.1 on GitHub: 
    http://git.io/vRrOM
        
    =======================================================================
                          WWIV Links and Information
    WWIC 5.0 Team Site                               http://www.wwivbbs.org
    WWIV BBS List           http://wwivbbs.rtfd.org/en/latest/WWIV_BBS_list
    WWIV 5.0 Documentation                   http://wwivbbs.readthedocs.org
    WWIVNews Archive             http://wwivbbs.rtfd.org/en/latest/WWIVNews
    WWIV IRC                             irc://irc.ospreynet.info:6667/wwiv
    =======================================================================
	
