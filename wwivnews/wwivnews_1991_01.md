```
                       WWIVNEWS Volume 1, Issue 1
                                 January 1991


                               Table of Contents
                               ~~~~~~~~~~~~~~~~~
    The Official History of WWIV.................................Random 1@1
    The Amazing 4.12 Disappearing G-Files...............East Bay Ray 1@9964
    Multi-line WWIV: Myth or Reality?...................East Bay Ray 1@9964
    Submitting to WWIVNEWS...................................WWIVNEWS Staff
    The DGROUP Saga......................................Lord Elric 1@18251
    The Pending File.........................................WWIVNEWS Staff
    The Editor's Corner.................................East Bay Ray 1@9964
    =======================================================================


                         The Official History of WWIV
                                 by Wayne Bell
                                  Random 1@1

          WWIV started around December 1984, when  I first put up a BBS. It
    was run on  an IBM-PC with a 10  meg hard disk and a  Hayes 1200. I was
    running  WWIV v1.0,  which was  in interpreted  BASIC. It crawled along
    quite slowly, and did not have a whole lot of features.
          About the only  other BBSs I was competing with  at the time were
    run on Apple II's, also running  in interpreted BASIC. Of course, there
    were RBBSs  and the like, but  I do not recall  ever having called one.
    Soon the 64k limitation of IBM interpreted BASIC became apparent. I did
    some pretty  strange stuff with  memory allocation and  string storage,
    but I had pretty much reached the  cutoff point. When you try typing in
    30 lines of a  message and the result is an "out  of memory" error, you
    know it is time to go on to something better.
          The better thing was Turbo Pascal 2.0. Turbo 2.0 did not have ANY
    support  directories (all  file I/O  was within  your current directory
    only).  I also  had quite  some trouble  getting comm routines working.
    With the release  of Turbo 3.0, I put  up WWIV v2.0. Soon after  that I
    got  REAL interrupt-driven  comm  routines,  and things  started moving
    along.
          I had  to go off  to UCLA, and  was forced to  take the BBS down.
    Around December  1985 on Christmas vacation,  I decided to put  the BBS
    back up for some reason. I did some major revamping at some time around
    then,  and called  it WWIV  v3.0. Still  in Turbo  Pascal 3.0,  though.
    Around this time (December), I got around to putting in a file section.
    It took  quite a bit  of work getting  xmodem working, and  I had to go
    back and re-format my data files  to allow for file descriptions. Since
    I had never actually  been on any other IBM-type BBS,  I had no clue as
    to  how the  file section  should  work,  so things  turned out  pretty
    randomly.
          On  January 1,  1986 I  finally released  WWIV v3.0.  It ended up
    going through  quite a few revisions,  especially in the first  week or
    two after being  released. And, to make things even  more fun, I had to
    resume classes at UCLA, so I  ended up pretty much writing WWIV without
    running a BBS. As you may guess,  this caused a few unfortunate bugs to
    slip by me, but that's life.
          Sometime around June 1986, I had decided to put in ANSI color and
    call it WWIV v3.2. This involved  re-formatting the user list (to store
    the user's color  selections), and a few other little  fun things, so I
    decided to put up  a BBS again. This was only for  a week because I had
    to move  back up to  UCLA after that  time for the  summer session. You
    might think  that not many  people would end  up calling a  BBS that is
    pretty much stated as  only being up for a week, but  it managed to get
    some pretty good  activity. To make this week even  more fun, for about
    half of it I was not there. I had a friend of mine, Stephen Davis, call
    up and remotely take care of  this experimental BBS. It even managed to
    make it without crashing.
          After releasing that,  it turned out that I had  a pretty bad bug
    in the Y-Modem routine. The BBS would read in a block of data, and THEN
    seek  to the  right place  in the  file instead  of FIRST  seeking then
    reading. So I came out with 3.20a rather quickly. Around January 1987 I
    put up the BBS again, running 3.21d.
          Then  around June  1987 I  started writing  WWIV v4.0. Naturally,
    since I  had a summer  job, things did  not go so  fast. Also, the fact
    that I had never written anything in  my life in C before did not help.
    I eventually got the hang of things. Finally,  on Dec 1, 1987, I put up
    4.0 as my  BBS for testing in real  life. Among my big promises  of how
    great it would be, I said  it would support networking among systems. I
    thought this sounded like  a good idea, only I had no  clue as to how I
    would  go about  implementing it  at the  time. So  I relegated that to
    "don't hold  your breath" status,  secretly thinking I  might never get
    around to it.
          Surprisingly,  I did  get around  to it  relatively soon. By that
    time, everyone had  already installed the BBS on  their computers, so I
    was stuck with the  format I had dreamed up a long  time ago when I had
    no clue how  it would work -- a number  1-65535 indicating which system
    was which. I ended up trying  to design a network around that, although
    it was not  quite the optimal solution (as  if is such a thing).  I was
    bored one day  and had been talking with someone  about a network, so I
    decided  to start  writing a  program to  send files between computers.
    There was no planning at all, I  just pretty much sat down and typed it
    in. That developed into the NETWORK.EXE program.
          Of course, there was more to  it than that. It was actually after
    I had the  NETWORK.EXE program mostly  working that I  started thinking
    about how the systems would connect together. I originally started with
    the idea of having it pretty much hierarchial, with a local-system list
    for all  systems to call  directly any systems  that were local.  After
    talking with Stephen Davis about this  for a while, I decided to pretty
    much  have it  grid-like, with  an amorphous  structure. That does not,
    however, prevent some  structure from being applied to  it. Without any
    software  changes,  it  can  be  easily  changed  over  to  a  straight
    hierarchial structure. All I would have  to do is set up the hierarchy,
    change one file, and send out an update of that.
          Well that  pretty much brings me  up to the present  time. Future
    expansion? Who  knows. One thing  that keeps appearing  is a multi-line
    WWIV.  That just  is not   practical. WWIV  depends upon  many external
    programs  (chains,   FSED,  archiving  programs)   and  you  can   NOT,
    practically, have the BBS run external programs without running under a
    multi-tasking  operating  system.  To  put  it  simply,  PC-DOS was not
    designed with multi-tasking in mind.
    =======================================================================


                     The Amazing 4.12 Disappearing G-Files
                                by Jeff Garzik
                              East Bay Ray 1@9964

          The  release of  WWIV v4.12  brought many  new features,  such as
    Zmodem  batch  downloads,  almost  100k  of  memory  savings  with TC++
    overlays, an upload event, and much  more. WWIV v4.12 also brought with
    it a hideous  bug. In v4.12 the G-Files section  had disappeared, and a
    new one could be not created. As you might have guessed, this created a
    stir almost immediately on both Amber  and WWIVnet. You see, Wayne made
    a small typographical error  in XINIT.C, where he told  the BBS to look
    for the G-File data in the GFILES directory This was a mistake, because
    the GFILE.DAT file goes into DATA, not GFILES.
          This problem  is very easy to  fix. When you first  run your BBS,
    copy  GFILE.DAT  from  your  DATA  directory  to your GFILES directory.
    Whenever you edit it with //GFILEEDIT (or 'G' from WFC screen), copy it
    over to the GFILES directory. If  you have registered to get the source
    code,  you  may  apply  this  small   mod  to  XINIT.C  to  remove  the
    disappearing  G-File  problem  altogether.  Search  for  this  line  in
    XINIT.C:

                   sprintf(s,"%sGFILE.DAT",syscfg.gfilesdir);

    and replace it with this:

                   sprintf(s,"%sGFILE.DAT",syscfg.datadir);

          That will stop your G-Files  from disappearing. If you still need
    help with this problem, you can contact 1@9964 for assistance.
    =======================================================================


                       Multi-line WWIV: Myth or Reality?
                                by Jeff Garzik
                              East Bay Ray 1@9964

          Current  technology has  opened up  new worlds  in BBSing. One of
    those is the capability for a single  BBS to have more than one user on
    the  BBS concurrently.  RBBS, PC-Board,  TBBS, and  many others already
    have this capability, but WWIV does not.
          There  are  many  solutions  to  the  problem of adding multinode
    support. One of them is using a LAN (Local Area Network), where several
    computers  are available,  one for  each phone  line. Another solution,
    sometimes used in  conjunction with a LAN, is the  user of a commercial
    multitasker such  as Desqview, DoubleDOS,  or MS Windows.  These multi-
    taskers allow  the use of  more than one  program concurrently, at  the
    price of  program speed. The final  solution is for a  BBS to multitask
    using its own routines.
          A  BBS multitasking  using its  own routines  is usually the most
    efficient solution, because it causes  the least program slowdown. This
    also removes  the author from dependence  on another company's product.
    Drawbacks  of this  include the  author not  having access  to all  the
    resources a large commercial has.
          The LAN method requires a lot of hardware (it involves a computer
    for  each node;  4 nodes  = 4  PCs), but  it is  generally the accepted
    method for large BBSs. LANs, however, are sometimes notoriously slow.
          The commercial  multitasker method is the  general choice for the
    hobbyist-sysop.  It  allows  multiple  nodes  on  a  single computer by
    running  2  or  more  programs  at  the  same  time. This does slow the
    individual programs  down, because a  single processor is  handling the
    load for  more than one  program at a  time. Processor slowdown  is not
    really a problem on fast machines, such as an 80386 at 33 Mhz.
          That is a little about multiple  node BBSs in general. Wayne Bell
    summarily declared a few years ago  (see the closing statements of "The
    Official History of WWIV") that WWIV is not going to be a multinode BBS
    system. He has, in my opinion, weakened in his position since then, but
    he has not  wavered visibly. I think there WILL  be a multinode version
    of WWIV,  but it is  still a long  way off, and  there is a possibility
    that it will not be written by  Wayne at all (the multinode portion). A
    multiple node WWIV, for now at least, is a myth and not reality.
    =======================================================================


                            Submitting to WWIVNEWS
                               by WWIVNEWS Staff

                    Submitting Tips/Letters to WWIVNEWS
                    -----------------------------------
          To  submit a  letter to  the  editor  (to be  published in  later
    editions) or a tip, simply send e-mail to 1@9964. Tell me in the letter
    that  it is  to be  published in  a later  edition of WWIVNEWS. Letters
    submitted  immediately  become  the  property  of  Jeff  Garzik, and he
    reserves the  right to edit any  tip or letter (letters  will be edited
    only for  size limitations and  clarity). Tips and  letters will be  no
    longer  than  1,000  bytes.  The  letter  or  tip  must include express
    permission  to  print  your  tip  or  letter.  If  not,  it will not be
    published. All unpublished or unacceptable submissions will be deleted,
    possibly without notification of the author or submitter.


                     Submitting an Article to WWIVNEWS
                     ---------------------------------

          Listed below are the requirements  for submissions (all this must
    be included in a single letter addressed to user 1@9964).

    1) The  title of the e-mail  you send to 1@9964  should be something to
    the effect of  "WWIVNEWS submission". It helps to  know your letter has
    something  to  do  with  WWIVNEWS,  because  that  will really speed up
    processing.

    2) Article title of no more than 40 characters.

    3) Real name,  such as "Jeff Garzik". If this  line is not included, or
    you use an alias, then the submission will be rejected.

    4) Your preferred alias, such as "Filo", "East Bay Ray", etc.

    5) Your main WWIVnet or WWIVlink node address.

    6) Double-space and then include a one or two line summary of your sub-
    mission. An example might be:

        This article is  about the problem of DGROUP, a  description
        of what it is, and recommendations on how to solve this problem.

    7) Double-space again. You will now enter your article. I would suggest
    that  you limit  your article  to between  3,000 and  5,000 bytes. This
    should  be  more  than  enough  for  a  decent  sized article. If space
    requirements become  more constraining in the  future, the maximum size
    (5,000 bytes) may be lowered.

    NOTE: All  submissions immediately become the  property of Jeff Garzik,
    and he reserves the right to print  and edit the submissions as he sees
    fit.  If substantial  changes need  to be  made, WWIVNEWS will probably
    contact you at the WWIVnet  address supplied. All WWIVNEWS issues are
    kept  for permanent  storage, and  all other  non-published submissions
    will be subsequently deleted.
    =======================================================================


                                The DGROUP Saga
                               by Wayne McDaniel
                              Lord Elric 1@18251

          One of the  most often asked questions by WWIV  modders is "I get
    this DGROUP error. What can I do?" This article should explain what the
    error is, what causes it, and how to prevent it.
          First, some background information is needed. The DGROUP error is
    a direct result of the architecture of the 8088 chip. The 8088 chip has
    a 16 bit word length. Using 16 bits, only 64K of memory is addressable.
    So, how can you have over 64K  in your computer? The chip uses 2 16-bit
    variables (known as "words") to store the address.
          The two words are called the segment and the offset. Each segment
    contains 64K. Segments start on even  16 byte boundaries. So, the first
    segment starts  at memory location  00h, the next  at 10h, the  next at
    20h, and so on. The offset is then added to the segment to generate the
    exact address.
          So, the  exact formula for a  memory address is (segment  * 16) +
    offset. In  hex, conveniently, this  involves shifting the  segment one
    position to  the left. Here  is a  sample  address in hex  and how they
    would go together.

    1111:2222 = 11110 <- shift the segment left, fill in a zero
              +  2222 <- add the offset
             --------
                13332 <- final memory address

          Anyway, what has all this got to do with DGROUP errors? Well, let
    me explain. DGROUP is the name Turbo  C gives for a particular group of
    segments. To be more specific, the _BSS and the _DATA segments are both
    lumped into DGROUP. Maybe this map will show you a bit more...

    Map of a C program, Large memory model

    Low    CS ->---------------------------------------
                : Code from one file                  :  Each chunk of code
                :        ---------                    :  is 1 segment, so
                : code from another file              :  you can have
                :       --------                      :  multiple chunks.
                : code from another file              :
           DS ->---------------------------------------
                : _DATA                               :  _DATA and _BSS
                :    initialized data                 :  are collectively
                :-------------------------------------:  known as DGROUP.
                : _BSS                                :  64K limit for
                :    uninitialized data               :  both combined.
           SS ->---------------------------------------
                :           free space                :  The stack can be
                :                                     :  up to 64K.
    Current SP->:-------------------------------------:
                : stack  (grows high to low)          :
    Start   SP->---------------------------------------
                :                                     :  Heap is all the
                : heap  (grows low to high)           :  remaining memory
                :                                     :  all the way up to
                :                                     :  the 640K boundary.
                ---------------------------------------
     High
     Address...

          As you can  see, the DGROUP segment consists  of the static data,
    both  the  initialized  (_DATA  segment)  and  the uninitialized (_BSS)
    segment. Since the _DATA segment and  the _BSS segment both have to fit
    in the DGROUP segment, this limits you to 64K total. Getting the DGROUP
    error simply means you have too  much data in the DGROUP segment. First
    lets take a look at what kind of data this is, so you know what to pull
    out.  The  _DATA  segment  consists   of  global  variables  which  are
    pre-initialized. This would be something like:

    int myvar ={25};

    which would  declare an integer myvar,  and initialize it to  25 at the
    start of the  program. The major part of the  _DATA section is not pre-
    initialized variables, but text. Plain and simple text.

    pl("Press a key to continue");
    strcpy(s,"Some more text examples");

          In these samples,  anything between the quotes is  going into the
    _DATA portion  of DGROUP. The other  section of DGROUP is  _BSS, or the
    uninitialized data.  And, thats what it  is, any global or  static data
    which does  not have a  constant or pre-defined  value has to  fit into
    _BSS. One way to check how much  DGROUP data you have is to consult the
    map file,  which will tell  you just exactly  how much DGROUP  data you
    havem and where it comes from. If you are compiling with the integrated
    environment,  turn detailed  maps on.   If you  are compiling  with the
    command line compiler, add "/s" to your call to tlink.

    The first section of the map file looks like this...


    Start  Stop   Length Name               Class

    00000H 00E2EH 00E2FH _TEXT              CODE
    00E2FH 03FDFH 031B1H BBS_TEXT           CODE

    . . .

    3863BH 38670H 00036H WHEREXY_TEXT       CODE
    38680H 40CADH 0862EH _DATA              DATA
    40CAEH 40CB1H 00004H _EMUSEG            DATA
    40CB2H 40CB3H 00002H _CRTSEG            DATA
    40CB4H 40CBBH 00008H _CVTSEG            DATA
    40CBCH 40CD3H 00018H _SCNSEG            DATA
    40CD4H 485B7H 078E4H _BSS               BSS
    485B8H 485B8H 00000H _BSSEND            STACK
    485C0H 486A5H 000E6H _STACK             STACK

          The addresses here have the  segment and offset already combined.
    The two most  important lines are near the bottom  of this section, the
    one for _DATA and the one for _BSSEND. Take the hex value for the start
    of _BSSEND  and subtract the  starting value of  _DATA to find  out how
    much DGROUP data  you have. So, I am using  485B8H-38680H = FF38. Since
    FFFF  is the  maximum allowed,  I have  FFFF-FF38, or  C7, or 199 bytes
    left. In other words, not much.

          The next part of the map breaks  down the segments a bit more, so
    you can see just exactly what makes up _DATA and _DGROUP.

    Detailed map of segments
     Address  Size Class    Segment          Group     Module name  ????
    0000:0367 0000 C=CODE   S=_TEXT          G=(none)  M=FLAGS87    ACBP=28
    0000:0367 0260 C=CODE   S=_TEXT          G=(none)  M=FPEXCEP    ACBP=28

    3868:0000 0093 C=DATA   S=_DATA          G=DGROUP  M=C0L        ACBP=68
    3868:0094 07F5 C=DATA   S=_DATA          G=DGROUP  M=bbs.c      ACBP=48
    3868:088A 1100 C=DATA   S=_DATA          G=DGROUP  M=bbsutl.c   ACBP=48

    3868:8654 0000 C=BSS    S=_BSS           G=DGROUP  M=C0L        ACBP=48
    3868:8654 7331 C=BSS    S=_BSS           G=DGROUP  M=bbs.c      ACBP=48
    3868:F986 00CD C=BSS    S=_BSS           G=DGROUP  M=bbsutl.c   ACBP=48

          So, you can  see that the initialized data  and text for BBSUTL.C
    takes up 1100H  bytes, or 4352 bytes in decimal,  or even better, 6% of
    the  space in  DGROUP. Add  them all   up, and  you wind  up with  text
    accounting for almost 50% of the DGROUP space.

          Now you know what the DGROUP error is and why it occurs. What can
    you do about it?  Well, the obvious thing to do is  to cut down on text
    in the source code. Instead of  "Oooh baby, tickle my keyboard" use the
    smaller "pause". That  may seem insignifigant, but that  is 24 bytes of
    DGROUP space  you just saved.  Find little used  text, comment it  out,
    copy it to a text file, and then use printfile to pull it off the disk.
    This  is only  recommended if  the text  is fairly  large. For example,
    change:

    pl("Please Re-enter your user number when prompted");
    pl("and write down your password");
    pl("Waste some more DGROUP");

    to

    /*
    pl("Please Re-enter your user number when prompted");
    pl("and write down your password");
    pl("Waste some more DGROUP");
    */
    printfile("newuser1");

          Now  all  the  text  is  stored  in  the  gfiles  directory under
    NEWUSER1.MSG, and not in DGROUP.
          One mod  to look for is  the External Strings Manager  by Caramon
    Majere. He has written a program to  read strings in from a file and an
    editor to  maintain the file. One  problem, however, is speed.  It will
    slow  the BBS  down (the  slowdown is  usually only  noticeable on slow
    computers  or hard  drives), so  I suggest  only using the infrequently
    accessed lines, and I would also suggest  a disk cache. Up to 500 lines
    of string data may be taken out  of your code using his program, and if
    you figure even 100 strings with an  average length of 40 bytes that is
    4K of extra  space. If you take out 500  strings with an average length
    of 4K, you just  saved 20K. A good method for doing  that is to comment
    out the line, but leave it in the source, so later when you are reading
    your  source code  you can  still search  for the  string to  find that
    section of code. Such as:

    /* pl("Please enter name or number"); */  /* now string 27 */
    get_string(27);

          I hope this  file has at least helped you  to understand what the
    DGROUP  error is,  and has  given you  some hints.  Mostly, remove  the
    string  text. String  text accounts   for 40%-50%  of your  DGROUP data
    usually. The  other option is to  remove some of the  static and global
    variables. However, since  you need almost every one  of them, it would
    be hard to do.  If you have any further questions, I  can be reached at
    812-877-3488, The Kingdom of Melnibone.
    =======================================================================


                               The Pending File
                    (WWIV & WWIVnet Tips, Tricks, and News)
                               by WWIVNEWS Staff

    If you find  a message in one of your  extended net logs (NETDAT0.LOG -
    NETDAT2.LOG in  your GFILES directory) informing  you that WWIVnet does
    not know what "8/0" is, and that  you don't have a "de2" program, don't
    worry  about it.  It is  a test  of an  upcoming WWIVnet feature, being
    conducted by  Black Dragon 1@2380  and Random 1@1.  It will not  affect
    your system in any way.

    For those of you who have Richard Ruffner's program SUBEDIT, do not use
    it. It is incompatible with  the new multiple-BBSLIST format introduced
    in NET20.  Both Filo 1@5252 and  East Bay Ray 1@9964  have released new
    sub  editors,  and  either  of  these  should  be  used in place of the
    original SUBEDIT.

    For those  who use NETEDIT, version  1.25 is out. It  is now separately
    compiled  for faster  execution if  you  have  an 80287  or 80387  math
    co-processor. The filename is usually  NETEDIT.ZIP, and it can be found
    on Amber and Black Dragon Enterprises (the author's BBS).

    As  many  are  aware,  a  program  called  NetZip  II was released into
    WWIVnet,  plagued with  dozens of  problems and  bugs. It  has now been
    fixed  and  has  been  working  for  several  weeks.  The  filename  is
    NETZIP26.ZIP.

    For those who are having problems with DSZ data overruns and are using
    US Robotics' HSTs, try putting "ha slow" on the command line.

    If anyone has  ever seen the message "corrupted,  not processing", then
    they  know that  particular feeling  of frustration.  After Wayne  Bell
    (almost) lost  a 2.3 meg packet,  he decided to implement  some sort of
    recovery  for  corrupted  packets.  LNET  and  NETWORK1  will now split
    corrupted  packets as  to isolate  the corrupted  part, and process the
    rest.

    Also, as  a result of  continued debate, Wayne  declared in a  piece of
    global mail  that all illegal activities,  such as pirating, phreaking,
    hacking, and other like undertakings which are carried over WWIVnet are
    outlawed and  forbidden. Further policy  and discretion is  left to the
    individual Group and Area Coordinators.
    =======================================================================


                              The Editor's Corner
                                by Jeff Garzik
                              East Bay Ray 1@9964

          This  section is  for any  notes, notices,  or changes  in policy
    regarding  any aspect  of WWIVNEWS.  It may  also contain  some sort of
    editorial, or information regarding  articles in upcoming issues. Since
    this is the  first issue of what I  hope to be a tradition  in WWIVnet,
    there isn't really any news (because the whole thing is new(s)!).
          I  also want  to clear  the  air  about a  couple things.  First,
    reviews ARE accepted, but they must  be objective AND they must cover a
    major utility,  such as NETEDIT. I  also prefer that the  author review
    the product,  but this is  not set  in  stone, per say.  As many people
    know, I  am fairly well  known as  both  a programmer (some  say of ill
    repute) and as  a modder. I will do the  utmost to keep advertisements,
    and any  other related material (excepting  announcements which I think
    benefit the  network as a whole)  away from WWIVNEWS. I  will also keep
    all "fights" between sysops or  factions away from this magazine unless
    it affects  a majority of the  net. An example of  an exception to this
    rule might be  the WWIVlink crisis. If people wish  to call my bulletin
    board,  my number  is listed  in the  BBSLIST (group  5) along  with my
    maximum baud rate. I also want to point  out that I try to keep my name
    out of  it as much  as possible. If  there is a  suitable place, I will
    exchange "East Bay Ray" for "WWIVNEWS" or "WWIVNEWS Staff".
          Some people  might be scared  away but such  things as the  tech-
    nicality of having to submit an article. I am very lenient, and as long
    as the article  comes with the basic information  I won't, for example,
    remove yours  outright simply because it  is missing a double  space in
    the  recommended place.  Far from  from it!  I want  to encourage,  not
    discourage,  submissions. Bug  reports (as  long as  they are supported
    with evidence, and are reproducible) are accepted and welcomed also.
          Finally, a  word about the accuracy  of this document. It  is not
    spell-checked at  all, only proofread by  myself. I am human,  and I do
    make errors. In the future, this will hopefully change, but until then,
    I will  stick with  the human  spell checker,  the Turbo  Pascal Editor
    Toolbox text editor, and RightWriter grammar checker.
    =======================================================================


                                    The End
```
