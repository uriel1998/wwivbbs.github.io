```

                Ú¿Ú¿Ú¿Ú¿Ú¿Ú¿ÚÄÄÄÄ¿Ú¿  Ú¿ÚÄ¿ Ú¿ÚÄÄÄÄ¿Ú¿Ú¿Ú¿ÚÄÄÄÄ¿
  ÉÍÍÍÍÍÍÍÍÍÍÍÍÍ³³³³³³³³³³³³ÀÄ¿ÚÄÙ³³  ³³³ À¿³³³ÚÄÄÄÙ³³³³³³³ÚÄÄÄÙÍÍÍÍÍÍÍÍÍÍÍÍÍ»
  º  Volume 3   ³³³³³³³³³³³³  ³³  ÀÅ¿ÚÅÙ³  ÀÙ³³ÀÄÄÄ¿³³³³³³³ÀÄÄÄ¿   Feb/Mar   º
  º Issue 10/11 ³³³³³³³³³³³³  ³³   ³³³³ ³Ú¿  ³³ÚÄÄÄÙ³³³³³³ÀÄÄÄ¿³    1993     º
  ÈÍÍÍÍÍÍÍÍÍÍÍÍÍ³ÀÙÀÙ³³ÀÙÀÙ³ÚÄÙÀÄ¿ ÀÅÅÙ ³³À¿ ³³ÀÄÄÄ¿³ÀÙÀÙ³ÚÄÄÄÙ³ÍÍÍÍÍÍÍÍÍÍÍÍÍ¼
            ³   ÀÄÄÄÄÙÀÄÄÄÄÙÀÄÄÄÄÙ  ÀÙ  ÀÙ ÀÄÙÀÄÄÄÄÙÀÄÄÄÄÙÀÄÄÄÄÙ   ³
            ³ Serving WWIV Sysops & Users Across All WWIV Networks ³
            ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ
                           ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
                           ³This Month's Features³
ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÁÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³ Random Factors.......................................Wayne Bell (1@1)      ³
³                                                                            ³
³ Type 0 Forum.........................................Omega Man (1@1)       ³
³                                                                            ³
³ "Box Mods" - Threat or Menace?.......................Starship Trooper      ³
³                                                       (1@2750/12754)       ³
³                                                                            ³
³ Filo's Mods of the Month for February & March........Filo (1@5252)         ³
³                                                                            ³
³ TechnOTES............................................WWIVnews Staff        ³
³                                                                            ³
³ WWIVNet-Compatible Network Listing (4/1/93)..........Red Dwarf (1@6264)    ³
³                                                                            ³
³ Dateline: @#$*()#!...................................Omega Man (1@5282)    ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³               Random Factors                ³
               ³   Creative Commentary by Wayne Bell (1@1)   ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

As most people certainly know, WWIV v4.22 is out now, and yes, there are a few
bugs here and there, as well as a couple of problems regarding the use of WWIV
and WWIVNet. I'll address these problems a bit, and then comment on some of
what's in store for v4.23.


FIX.EXE:

There is a bug in the version of FIX.EXE that was released with 4.22, and this 
has been addressed. The version of FIX released with v4.22 did have a bug in it
in that it would not work correctly if you have more than 64 subs. An updated 
version, FIXV6.zip, is available on my system which supports however many subs
you have.


PKZIP 2.04xxxxx:

If you have any flavor of PKUNZIP 2.04 online on your BBS, and you have it set
up to allow people to extract files, make sure you have the "-o" option on the
command line. This should be there for PKUNZIP 1.10 also, but it is not as 
critical. 

Just to remind people, for WWIV the recommended command lines (for any version)
are as follows:

add:      pkzip -a %1 %2
extract:  pkunzip -o %1 %2
list:     pkunzip -v %1

Those interested in direct-screen-write overrides should check your release
docs from PKWare for the necessary information. 

[Editor's NOTE: For added security, some sysops prefer to add the direct path
to these files in INIT, and remove said path from the PATH= command in their
AUTOEXEC.BAT files.]


GATING NETWORKED SUBS:

A short note needs to be made to update people on the WWIVNet rules regarding 
the gating of subs:

With regards towards gating subs, gating - such as with WWIV v4.22 and net32 -
should ONLY be done BY THE HOST, or WITH THE HOST'S PERMISSION. If you do not 
host a specific sub, then do >NOT< gate it to another network, *UNLESS* you 
*FIRST* get the host's permission. If you do not first get permission, you 
will almost certainly be dropped from the sub, and nobody will like you.


UNSOLICITED E-MAIL:

As for sending unsolicited E-Mail, if you are starting up your own network (or 
drumming up business for one), do NOT send applications or "Please join my 
network" E-Mail to sysops in WWIVNet or any other net, for that matter. You 
should only send an application to someone if they have explicitly expressed 
interest in your sub (eg, they E-Mail you asking, "Please send me an 
application"), or if you have very good reason to suspect they would be 
interested (eg, you see a post from them saying, "I wish there were a network
that...", and describes your network, or you are starting up a network 
specifically for blue-haired people, and you see a system named "Blue haired 
person's BBS").

Almost all sysops detest unsolicited net applications (or any unsolicited 
junk E-Mail), and blindly sending net applications to everyone will only make 
them LESS likely to want to join your network. If you want to get people to 
join your network, look for a generic netted sysop sub, or something similar, 
and POST something advertising your net. But do *not* E-Mail it!


//CHUSER BUG FIX:

There is a bug in void chuser(void) that can cause the qscan pointers of those
accounts being accessed via //CHUSER to become a bit confused. Registered
sysops can correct this bug by replacing this void with the one below:


void chuser(void)
{
  char s[81];
  int i;

  if (!checkpw())
    return;
  if (!so())
    return;
  prt(2,get_string(328));
  input(s,30);
  i=finduser1(s);
  if (i>0) {
    write_user(usernum,&thisuser);
    write_qscn(usernum,qsc,0);
    read_user(i,&thisuser);
    read_qscn(i,qsc,0);
    usernum=i;
    close_user();
    actsl=255;
    sprintf(s,get_stringx(1,17),nam(&thisuser,usernum));
    sysoplog(s);
    changedsl();
    topscreen();
  } else
    pl(get_string(8));
}


SUBS.LST:

As many people have seen, I'm currently involved in fixing the SUBS.LST 
updating. So far, 27 people have E-Mailed me saying that they are willing to
take it over. However, I think most likely I'll end up handling it myself,
since it is almost completely automated now. I am in the process of setting up
some categories for the SUBS.LST file, and once that is sent out, anyone using
v4.22/NET32 will be able to select the category for each sub in //BOARDEDIT.
I'll then hack up a program to sort out by category, and sort subs within
categories, and everything should be working fairly easily, and automatically.

Note that sub descriptions are (incorrectly) cut off at 40 chars currently.
That is a bug in NETWORK2.exe that will be fixed in NET33.


NODE RENUMBERING:

We're currently working out a node renumbering scheme for WWIVNet, since the
current numbering scheme is being pushed beyond where it was intended to go,
and when the phone company runs out of x0y and x1y area codes, we'll have to do
something new anyway. Something will probably happen with this in a few months.


WWIV V4.23: 

I believe I have multiple-language support installed now, but I am waiting for 
some non-English .STR files before I try it out "for real". I have a long list 
of things to be added into v4.23, but am not sure how many of them will be 
fully implemented in v4.23 (I want to avoid putting TOO much in each release)

So far, I have NETWORK.EXE modified to swap itself to EMS or disk (if
necessary) when running DSZ or HSLINK, so if you are short on memory for net
callouts, this will give you about 90k more free for running protocols for net
transfers. I've also implemented a new external method, whereby external net
messages are processed by the external program when the message is received,
instead of sometime later when the external program happens to run. Hopefully,
external programs will start supporting this sometime after NET33 is released.
I also hope to have NET33 support transfers for multiple networks in one net
call, but have not started implementing that yet.

No, I don't have any release date yet for either v4.23 or NET33, but NET33 will
be out before v4.23.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³                 Type 0 Forum                ³
               ³         Edited by Omega Man (1@5282)        ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

The Type 0 Forum is WWIVnews' "Letters To The Editor" section. Comments,
criticisms, questions, and suggestions can be sent to WWIVnews c/o 1@5282.
WWIVnews reserves the right to edit any submissions for either clarity,
punctuation, or spelling, but will endeavor to maintain the content integrity
as close to that originally submitted as possible.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Dear Editor:

I have registered a file called NetRunner 1.02. It is distributed as 
NETRN102.ZIP on MegaRom ][ - Shareware Spectacular, as well as through normal 
shareware channels (i.e. bbs systems).

This game is a "Cyberpunk" styled game. The mission: Hack into systems and
steal credits while avoiding ICE (Intrusion-Counter Electronics). It is a fun 
game and many of the users at The Theatre Of Vampires (WWIVNet/ICEnet 3325) 
enjoyed the game immensely. 

Unregistered the game is fully functional. However, SYSBUILD.EXE (a utility to
build systems) does not work until the game is registered. Also, all NetRunners
are retired at 5000 experience points.

The game was authored by Rob Jacob, of Federal Way, WA and distributed by 
Seattle Cybertechnologies. 

I sent in the registration form and a check for $25.00 on the 9th of January, 
1993. I waited for four weeks and had not received a registration number when 
I received a new bank statement for my checking account. The check I wrote to 
Seattle Cybertechnologies had cleared the 12th of January 1993, only three days
after I wrote and mailed it.

I tried to contact Rob Jacob or Seattle Cybertechnologies by telephone, to find
that the numbers were unlisted or disconnected. I attempted to call the two 
telephone numbers listed for CyberSpace BBS, both of which had been 
disconnected. I contacted the second SDS for NetRunner 1.02, HCS BBS, and left
mail with the sysop of that board, explaining to him my dilemma.
 
On 9 Feb 93, I sent a letter to Rob Jacob requesting the registration number.
I gave him the benefit of the doubt (lost in mail, oversight, etc) and 
requested a registration number be sent for this game.

On 23 Feb 93, I called back to HCS BBS, and had received mail back from the 
sysop. He informed me that this lack of support from Rob Jacob had begun in 
July of 1992. Several registrants, who had downloaded the game from HCS, had 
contacted the sysop of HCS concerning the registration numbers not being 
received. HCS BBS' sysop spent a relatively large sum of money attempting to 
contact Rob Jacob concerning NetRunner and the failure to support the product. 
Rob Jacob did not return his calls. After that, HCS BBS dropped the game from 
his download area and posted several warnings on nationwide networks such as 
FidoNet.

At that time I sent Rob Jacob the second follow-up letter. In this letter I 
informed him of my correspondence with HCS BBS and of my intentions should a 
registration number not be received. 

I am now (28 March 93) waiting for further correspondence and a reply from 
Seattle CyberTechnologies and Mr. Rob Jacob. In the meantime, is there any
other recourse I can take to expedite matters?

                              Lestat The Immortal (1@3325)


Editor's Reply:

Lestat's problem isn't unheard of. At least once a month, reports surface on 
the major computer networks about a particular shareware author who appears to
have suddenly disappeared off the face of the Earth, leaving all registered 
users and pending registrations in limbo. In the majority of cases this is
usually revealed to be a misunderstanding or miscommunication between the
author and his customer(s), and matters are usually settled between both
parties in a satisfactory manner.

However, in Lestat's case, the problem may be a bit different. Inquiries have
also surfaced in recent weeks on Usenet and Fidonet regarding the whereabouts 
of both Seattle CyberTechnologies and Ron Jacob. As of this writing, neither
company nor shareware author have been located, and Lestat's grievance has
not been settled.

Lestat is not without recourse, however. When purchasing *anything* using
the United States Postal Service, there are several steps that should be taken
so as to protect yourself from any possibilities of fraud or misconduct on the
part of the vendor:

1) Prior to purchase, ask around to see if anyone's heard anything negative
about the vendor. Ask about post-sale support, positive customer relations,
and integrity of financial dealings. If you cannot find anyone locally who has
dealt with the vendor, contact the chapter of the Better Business Bureau that
is local to the vendor, and inquire about any complaints pending with the
agency. Another option is to try using one of the computer networks to inquire 
as to the integrity of the vendor. If all else fails, try asking the vendor 
for a brief list of other consumers with whom you can correspond about their 
products. If the vendor refuses to grant such a list, this is generally 
considered to be a warning sign against that vendor.

2) If you decide to purchase from the vendor, unless it is totally impossible
to do so, pay by a credit card. If you fail to receive what you've ordered, 
the credit agency behind the card can stop payment on the item until the 
matter is settled.

3) If you cannot pay by a credit card, pay by cashier's check from your bank,
S&L, or credit union. Prior to purchasing, ask your financial institution
whether they can offer the same sort of protection for the check as they can
with a credit card purchase. If they cannot, ask them to suggest an alternative
method of purchase.

4) While it's not feasible for some consumers, the best way to ensure that
the product you order is delivered into your hot little hands is to order via
COD. If the vendor refuses to ship COD, refuse to do business with them.

5) Under *no* circumstances should you ever pay by cash over the mail. COD is
only slightly more permissible, and a check should be used when possible. This
is especially true in the case of large purchases.

If you think you're the possible victim of mail fraud, and you've taken these
steps, you stand a better chance of getting the matter settled with a positive
result. If you think something's amiss behind your purchase, take the following
steps:

1) A good faith attempt to contact the vendor is in order. This does NOT mean
that one disconnected phone call constitutes a good faith attempt. Follow-up
the call with a second call the following day to ensure that the disconnection
was not a screwup on the part of either the vendor or the local phone company.
One report on Usenet years ago about one of Microsoft's support lines being
disconnected started a brief world-wide flurry of rumors regarding the 
impending demise of Gates' then-minor empire.

If you paid by credit card, you can call the agency and request a stop payment
on the purchase. This usually will get a quick response from the vendor.

If you paid by anything other than a credit card, read on.

2) Send a letter of inquiry to the vendor. Have this letter sent registered
with the USPS. This usually costs an extra $1, and requires that the recipient
of the letter sign a green card of acceptance before being the letter is 
officially delivered. This is a sign to a vendor that you mean business right
off the bat, and usually expedites matters about two steps down the chain
quicker than a normal letter.

3) If the letter is returned as undeliverable because the vendor could not
be located, attempt to locate through the USPS any sort of forwarding or
alternative addresses for the vendor. Some vendors use Post Office Boxes
which some local USPS sites have been known to change without notice, and
these changes take weeks to be reflected throughout the entire USPS system.

4) If the letter is returned as refused by sender, then a complaint can be
filed with the USPS for possible mail fraud. This will require forms being
filled out, and copies made of any correspondence with the vendor prior
to filing the complaint. Call in advance and ask for details so that you
bring everything the local Postmaster will need to pursue the matter further.

5) If the Postmaster determines that fraud may have occurred, the matter
becomes a Federal case, and is pursued accordingly. If the purchase was of 
a significant amount, it may be wise to pursue the advice of a local attorney
with regards to your next steps.

A word to the wise: if the matter gets this far, don't expect to get your 
money back any time soon, and don't expect to get it all back. In many cases,
such as the recent computer mail fraud situation in Southern California, the 
consumer who failed to pay by credit card is usually the consumer whose only 
satisfaction is knowing they helped prevent other consumers from being 
defrauded as well.

It should be noted that the majority of shareware authors are persons of honor
and integrity, and as with any business there are times when accidents happen
and orders fall through the cracks. Before going half-cocked and filing a
formal grievance at the first sign of trouble, attempt to contact the vendor
and try to solve the problem in a friendly, professional manner.


Dear Editor:

I just saw someone locally that pulled the neatest "trick" I've ever seen...
also one that unfortunately removes much of the control over a subboard from
it's Host. I do not fault the person that showed me this: he only did this to
show me "Hey, look at what a neat thing I can do with your sub if I wanted to."

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
This is the normal, typical setup in 4.22 to SUBSCRIBE to a sub
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
A. Name       : Drawing Down The Moon / Ritual Magick
B. Filename   : DRAWING
C. Key        : None
D. Read SL    : 28
E. Post SL    : 28
F. Anony      : No
G. Min. Age   : 0
H. Max Msgs   : 75
I. AR         : None.
J. Net info   :
      Network      Type    Host     Flags
   a) WWIVNet      5413    5413
K. Storage typ: 2
L. Val network: No
M. Req ANSI   : No
N. Disable tag: No
O. Description: Pagan/Wiccan/Ceremonialist discussions, some chatter.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
Here's a perfect example of how a SUBSCRIBER can GATE WITHOUT PERMISSION!
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
A. Name       : Drawing Down The Moon / Ritual Magick
B. Filename   : DRAWING
C. Key        : None
D. Read SL    : 28
E. Post SL    : 28
F. Anony      : No
G. Min. Age   : 0
H. Max Msgs   : 75
I. AR         : None.
J. Net info   :
      Network      Type    Host     Flags
   a) WWIVNet      5413    5413
   b) WWIVLink     5413    <HERE>   Auto-Req Auto-Info
K. Storage typ: 2
L. Val network: No
M. Req ANSI   : No
N. Disable tag: No
O. Description: Pagan/Wiccan/Ceremonialist discussions, some chatter.

My concerns are of *security* and *control*, by a Host, for their subs.

I did not create my subs merely to allow other Sysops unrestricted reign. The
above two screen capture sets show that *apparently* anyone can gate a sub, at
least to another network, without any form of permission from the original
host. At the minimum this offers several problems.

Say I wanted to prevent someone from subscribing to a sub. I can either put
the sub on manual updating, or I can opt to use auto"R"equest features and put
that node in DISALLOW.NET.

PROBLEM #1: Someone decides to gate my subs to perhaps a second network. A 
banned system I'm disallowing to my sub has access to the second network. The 
banned system effectively subscribes to my sub ANYHOW because they are picking
it up on the second network's gating of my sub.

PROBLEM #2: (more convoluted) A member of second network picks up my sub on
WWIVNet and gates it to perhaps IceNet. An IceNet member gates my sub over
to WWIVLink. A Link subscriber gates it to TeensieNet. A TeensieNet member
gates it to StupidNet. StupidNet member gates it to PubertyNet. etc, etc.

PROBLEM #3: In either of the above cases, who sends what to whom? Do I suddenly
lose total control over the subscription process? Do people now send request
notices to boards other than the original Host?!

PROBLEM #4: I have one of the two largest subs in WWIVNet, totalling 487 
subscribers. Am I now being told that any one of those people can now each gate
my sub to have a dozen or more different networks?!

PROBLEM #5: And what about massive, I mean MASSIVE traffic flow problems? What
will happen when these gated and re-gated packets bounce several times across
the nation, possibly looping several times, before winding back at *MY* system?
(remember me, the HOST?!)

PROBLEM #6: Since other systems, other SUBSCRIBER systems, are now acting as 
Co-Hosts to *MY* subs, could THEIR having NetVal or other flags override or 
complicate any setting arrangements that are present on *MY* board? Could
THEIR having things like NetVal turned on for *MY* sub that they "poached"
cause outbound message from *ME* to have to be subjected to NetVal before THEY
allow *MY* Hosted message to pass THEIR gateway?! (remember me, the HOST?!)

Now these are all REASONABLE concerns in my view, and other people are going to
start asking the same questions once they read this message. If they haven't
already seen other similar pieces of seeming evidence. Frankly this scares me,
and drastically lowers my confidence in the way the network is changing if all
of this turns out to be true.

                                   Furry Lover (1@5413)


Editor's Response:

This incident wasn't exactly unforseen, but at the same time there's not really
that much that can be done about the problem software-wise with regards to the
network executables. There's been a few ideas battered about on the various 
sysop subs, but nothing comprehensive has been proposed so far.

Although no preventive fix currently exists for this potential abuse of gating,
this does not mean that the problem has simply been ignored by Wayne Bell. As 
this month's column from the creator of WWIV and WWIVNet explains in clear
details, unauthorized gating of this sort is against WWIVNet rules, and should
be expected to be just as illegal on any of the other WWIVNet-based networks.


Dear Editor:

I have been getting a lot of E-mail about stopping WWIV from being hacked. I
made a standing offer on one of the subs about hacking that I would pay $100.00
to anyone that could hack my board, and that I would even give them 255 SL and
the system PW. No one took me up on it.

Anyway, I have written this short file on what I have done on my board to 
protect it, and thought that you might want to consider putting it in the next
issue of WWIVNews. If not, or if you like the idea but need more meat, let me
know and I will add more to it, however I don't think that there is a lot more
to add that could make it any better.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

Here is what you should do if you want to make your WWIV hack-proof. I cannot
GUARANTEE it will stop hackers, but it should. I have offered hackers $100.00
if they could hack my board, and even offered to give them the system password
and 255 SL to help them out, but none has been able to do it successfully.

If you have the source, it will be VERY helpful. What you will need to do is
go into BBS.C and change all the // commands, especially //DOS, //EDIT, //LOAD,
//UEDIT, //CHAINEDIT, //REN, //MOVE, //DIREDIT, //LOG, and //CHUSER. You might
as well change them all. What you change them to doesn't matter, but make it
something completely unrelated to BBSing, for instance, change //DOS to
//TURTLE or something that they could never guess. This way, even if they get
255 SL AND your system PW, they will not be able to do anything.

DON'T have a C:\WWIV\DLOADS dir. Call it something else. Make sure that you
identify it in INIT. Call your C:\WWIV\TEMP dir something else, again making
sure that you let INIT know about it.

Change your system PW often, and DON'T GIVE IT TO ANYONE!!!!  I cannot stress
this enough. Your BBS is only as secure as what you want to make it. If you
go giving out 255 SL's to people, you are asking for trouble. Even IF they
never do anything to you, someone could see them logging on sometime and get
their logon info, or they could copy all their script files from their term
program without your friend knowing it...all sorts of things can happen. I
cannot think of any reason to give someone 255 SL, and if you set up your //
commands like I have outlined above, even if they did log in as your friend,
they would not be able to do anything, unless of course your friend had all of
them written down by his computer or in a file somewhere.

Of course, there is not really a lot that you can do about stopping trojans and
viruses from being uploaded... a good upload event would help, although I'm
told that there is a viruses that is executed when Scan runs on it, so it
might be a good idea to write-protect your hard drive, and copy the file to
floppy and scan it. Most hackers are not out to upload viruses though. Most
of them want to get into your DOS somehow.

Common sense plays a HUGE role in BBS security. Use it.


                                        Sam (1@2077)

Editor's Response:


Sam's suggestions are very good ones. In fact, many of them date back to the
old 3.21d days of WWIV, where renaming // commands was the easiest way to
make Wayne's solid spaghetti code a bit more bulletproof. This solution was
usually combined with the "Sysop Menu" mods that still find their way onto
the MODNET to this very day.

The same basic philosophy applied to changing directory names to something
nonstandard so as to confuse anyone who'd managed to hack into the system
remotely. If your BBS was in C:\123R3\SMARTPIC instead of C:\WWIV, then
odds are very unlikely that a hacker would take what little time he had to
snoop around every directory to find where WWIV really resided. When combined
with a mod or two to the source to make sure the shell to DOS placed the
hacker in the root directory, this became a very effective means of reducing
a hacker's time frame from which to work with.

Finally, the best way period to dramatically increase your system security is
to frequently change your system passwords - especially at the first sign of
any suspected attempt upon your system's security. Again, when selecting a 
password, choose something that you can easily remember, but doesn't have
anything directly relating to you on a surface level. Some sysops use the 
method by which the password is determined by a serial number of a part inside
the system itself. A BIOS revision number, SIMM OEM number, or even the slot
number in which their modem resides is not easily hackable by someone who has
no sysop-side access to the system itself.

Again, a little common sense can deter even the most experienced hacker.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³       "Box Mods" - Threat or Menace?        ³
               ³     By Starship Trooper (1@2750/12754)      ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

Many people ask for or write mods to colorize and draw boxes around
the "Last few callers" listing, sub lists, and similar items. This is
actually a very simple procedure, which can be done by anyone without
working from a published mod file. In this article, I will demonstrate
how this should be done.

As an example, consider the function to list the chains available.
Unmodified, it appears in BBSUTL1.C as:

void show_chains(int *mapp, int *map)                       //  1
{                                                           //  2
  int abort,i,i1;                                           //  3
  char s[81];                                               //  4
                                                            //  5
  abort=0;                                                  //  6
  nl();                                                     //  7
  for (i=0; (i<*mapp) && (!abort) && (!hangup); i++) {      //  8
    sprintf(s,"%d. %s",i+1, chains[map[i]].description);    //  9
    pla(s,&abort);                                          // 10
  }                                                         // 11
  nl();                                                     // 12
}                                                           // 13

Obviously, lines 8 through 11 do the actual printing. Line 9 writes the
number and name of the chain into string s (such as "1. Tradewars") and
line 9 sends it to the screen and modem, followed by a new line. sprintf()
format strings (like "%d. %s") work exactly like those used by printf() and
npr(). The '%' instructs the function to grab the next argument, and the 'd'
or 's' tells how to interpret it. These format specifies are very
powerful; you can specify how wide a certain item should be as well as
several other options. This is essential for arranging the data in columns.

How wide should they be?  There's no simple answer. You have to take into
account the actual length of an item, how much space to leave between them,
and the width of a screen (80 columns).

Something like this is needed:

"º xx ³ description ³"        (xx is the number of the chain).

 1234567???????????+2      Length= 7 + length(description) + 2

How long should the description be?  VARDEC.H says 81 characters, but that
won't fit. Let's trim it to sixty. Sixty characters for the description
plus nine (7+2) is well under our limit of 80. These numbers are placed
within a sprintf() format specifier. First comes the '%', then the amount
of space used, then the item type. If you want the item to be against the
left side of the field, rather than the right, place a '-' before the width.
This should be done in almost all cases, except with numbers.

    sprintf(s,"%2d %-60s",i+1, chains[map[i]].description);    //  9
                ^   ^^^

In the above line, the number will be printed within a two-space field,
against the right edge, while the description will be printed within a
60-space field, against the left edge. There is an error, though:  if
a description is greater than sixty characters, it will overflow the
space. This can be corrected by adding a "precision" specifier. These
tell sprintf() to only use a certain number of characters, and ignore
those that would normally cause "overflow". This is done by placing a
decimal point after the field width, and then the MAXIMUM number of
characters allowed:

    sprintf(s,"%2d %-60.60s",i+1, chains[map[i]].description);    //  9
                       ^^^

Everything is now in orderly columns. We can place them within a box
by adding vertical line characters. The single bar (³) can be produced by
holding down ALT and typing 179 on the numeric keypad, and the double
bar (º) with ALT-186. Place these characters within the sprintf()
format string, between the data items:

    sprintf(s,"º %2d ³ %-60.60s º",i+1, etc.);    //  9
               ^     ^          ^
Next, add color codes. These are produced by embedding a control-C in the
string, followed by a digit. If you're using the Borland editor or Qedit
or the DOS 5.0 editor, this is done by typing a control-P and then a
control-C. A heart symbol will appear. All the line characters
should be the same color, as they will be joined together eventually.

    sprintf(s,"1º2 %2d 1³5 %-60.60s 1º",i+1, etc.);    //  9

(If you read this from within WWIV you will see colors, otherwise you will
see hearts and digits.)

Your box will need a top and bottom also. Use your block-copy command to
make a copy of the sprintf line you've been working on. Cut out everything
but the string itself, and wrap a pl() (or pla()) around it:

pl("1º2 %2d 1³5 %-60.60s 1º");

Next, remove the colors:
pl("º %2d ³ %-60.60s º");

Replace vertical bars with corner pieces or T-shaped bars:

pl("É %2d Ñ %-60.60s »");

Next replace each of the format specifies with the proper number of
horizontal lines. (in this example, two and sixty)

pl("É ÍÍ Ñ ÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ »");

(block-copy commands work well here for making long horizontal lines)

Finally, replace the blank spaces with horizontal lines. Then clone this
line, and make the second copy look like the bottom of a box (replace the
corners), and put a color code at the beginning:


pl("1ÉÍÍÍÍÑÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»");

pl("1ÈÍÍÍÍÏÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼");

Insert these lines into the function just before and after the loop. You
can, if you want, put a title on the upper bar:

pl("1ÉÍÍÍÍÑÍÍÍOnline Programs AvailableÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»");

Your finished function might look like:

void show_chains(int *mapp, int *map)                       //  1
{                                                           //  2
  int abort,i,i1;                                           //  3
  char s[81];                                               //  4
                                                            //  5
  abort=0;                                                  //  6
  nl();                                                     //  7
  pl("1ÉÍÍÍÍÑÍÍÍOnline Programs AvailableÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ»");
  for (i=0; (i<*mapp) && (!abort) && (!hangup); i++) {      //  8
    sprintf(s,"1º2 %2d 1³5 %-60.60s 1º",               //  9
        i+1,chains[map[i]].description);                    /* Continued */
    pla(s,&abort);                                          // 10
  }                                                         // 11
  pl("1ÈÍÍÍÍÏÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍÍ¼");
  nl();                                                     // 12
}                                                           // 13

Not all listing commands are easy to change. Some use multiple strcpy(), 
strcat(), ansic(), outstr(), and similar non-sprintf() functions. (The function
to print file information, for example). It is necessary to convert these to 
use sprintf(), which I will demonstrate here. I encourage all mod writers to 
use this information... not only is it useful for "box mods", but many other 
mods use the older, cumbersome methods to output several pieces of data, when
a single sprintf() is easier.

The first thing to do is locate a string variable that is not used in that part
of the code. s, s1, s2, etc., often hold things only temporarily, and can be 
safely reused. If you're unsure about it, simply declare a new string of 
length 81 or more.

The functions to be replaced perform these actions:

Original function     sprintf code     result
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
strcpy(dest, src)       %s or constant   copy _src_ string into _dest_.
strcat(dest, src)       %s or constant   append _src_ string to end of _dest_
itoa(num, dest, rad)    %d               converts _num_ to string _dest_
ansic(num)              ctrl-C digit     send ANSI codes to change color
nl()                    \n               send CR and LF

When these functions are used, there will often be several of them in 
succession. The first will be a strcpy(), to begin the string to be sent out, 
followed by strcat()'s and possibly itoa()'s, which add successive items to 
the output string, which will eventually be sent with outstr() or pl(). 
Sometimes, small strings are composed and sent with outstr(), with ansic() 
between them (see printinfo() in xfer.c).

The format for sprintf() is:
    sprintf(buffer, "format string with %d %s etc.", var, var,...);

The first argument tells the program where to place the result. The second
tells what it should look like, with % meaning "fetch something and put it 
here", and the other arguments being the items that are "fetched". Standard 
WWIV source makes use of sprintf() in most instances where a box mod would be 
desired. The only exception is printinfo(), which prints the information for a 
file. Although it's not too difficult to convert it, the function is very long,
too long for this article. Let's try something simpler, a (hypothetical) mod 
that does something fairly interesting, but in a clumsy way:

       ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
       ³ WK-001.MOD by Joe Sysop #1@xxxx. This prints a     ³
       ³ Way-K00L message to your callers:                  ³
       ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ
  <magenta>Welcome to Way-K00L BBS, <fl. red> John Smith!
  <green>You are user #95, and you've called <cyan>17<green> times!

OK, put this somewhere in LILO.C:

  ansic(3); /* magenta */
  strcpy(s, "Welcome to ");
  strcat(s, syscfg.systemname);
  strcat(s, ", ");
  outstr(s);                       /* Welcome to Way-K00L BBS, */
  ansic(6); /* fl. red */
  outstr(thisuser.name);           /* John Smith */
  outchr('!');  nl();              /* ! \n*/
  ansic(5); /* green */
  strcpy(s, "You are user #");
  itoa(usernum, s1, 10);  /* convert num to string (base 10), store in s1 */
  strcat(s,s1);
  strcat(s,", and you've called ");
  outstr(s);             /* You are user #95, and you've called */
  ansic(1); /* cyan */
  itoa(thisuser.timeson, s1, 10);
  outstr(s1);            
  ansic(5); /* green */
  pl("times!");                                     /* End WK-001.MOD */

Obviously, there has to be a better way... let's take each item to be printed,
and put it in a sprintf(). I'll reproduce the desired result here:

  <magenta>Welcome to Way-K00L BBS, <fl. red> John Smith!
  <green>You are user #95, and you've called <cyan>17<green> times!

The first item is a change to color #3. This is done with ^C3.
  sprintf(s,"3          /* equivalent to ansic(3) */

Next comes a constant string, "Welcome to ":
  sprintf(s,"3Welcome to       /* we used strcpy in the badly-done example */

Then the system name, which is a string. Use "%s" to tell sprintf() to
fetch it, and pass the variable as a parameter:
  sprintf(s,"3Welcome to %s", syscfg.systemname); /* instead of strcat() */

Comma, space, then color #6:
  sprintf(s,"3Welcome to %s, 6", syscfg.systemname);

And the user's name, then a '!', and print it:
  sprintf(s,"3Welcome to %s, 6%s!", syscfg.systemname, thisuser.name);
  pl(s);    /* print the above, then a linefeed */

The first line has been sent, so we'll do the next line now:
  sprintf(s,"5You are user #

A number can be printed by placing "%d" in the string and the variable in
the argument list. sprintf() will do an itoa() conversion:
  sprintf(s,"5You are user #%d, ",usernum);

Another string constant follows, a color change, a number, a color change,
and finally the last word:
  sprintf(s,"5You are user #%d, and you've called 1%d5 times!",usernum,
         thisuser.timeson);          /* ^C1%d^C5 ^^^ */ 
  pl(s);

As you can see, the 19 lines of code in the original have been replaced by two 
sprintf() and two pl() calls. You could even use npr() to integrate the 
sprintf() and pl() sets into one line each (if you choose to do this, remember 
to add a \r\n to the end). sprintf() produces more compact code and allows easy
"Box Mods" using the procedure I detailed previously.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
Now you know how to make box mods - and so does almost everyone else. So please
do not flood the mod subs with mods created using the guidelines here! If 
someone asks how to box a listing, send them this file.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³          Filo's Mod of the Month            ³
               ³              by Filo (1@5252)               ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

The Mod-of-The-Month Selection represents my choice of what appears to be a 
useful, practical mod to WWIV. It does not mean it is the best mod posted or 
even that it works as I may not have tested it. Given the limitations of this
media, uuencoded mods are NOT eligible for selection as mod-of-the-month.

The offerings for February contained many mods as people were updating mods 
for v4.22. The one that I have selected will PROBABLY be a standard feature 
in v4.23 in one form or another.

ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³ Mod Name: SPV-012.MOD      Mod Authors: Papa Bear 1@5079 (WWIVNet)         ³
³ Difficulty: Pretty darn easy                      1@15061 (WWIVlink)       ³
³ WWIV Version: 4.21, 4.21a, 4.22                   1@5079 (IceNET           ³
³ Files Affected: XINIT,BBSUTL1,VARDEC  Date: February 6, 1993               ³
³ Description: Allow any number of chains (stock code is limited to 50)      ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

  Long Description:

Well, I had an urge on night, and I decided to add EVERY on-liner I had on my
archive floppies to the BBS. I already had 40 odd on-line when I decided to 
do this.

When I got to #50, I found that I couldn't add anymore, so I wrote this mod to
allow for ANY number of chains. At one time I was running 130 (until I found 
that some wouldn't run properly remotely <sigh>) chains. Now I'm right at 85.

A note here. Just like 4.22 will allow up to 999 subboards and message bases,
you can have 999 chains. But, just as Wayne suggests, only define as many as 
you need. Each chain defined takes up memory. So keep it close to what you 
have (in other words, don't define 999 chains if you are only gonna run 60. 
Instead, define maybe 70 [to give you some leeway]).

LEGEND:
== unchanged, search for
+= modify line
-- delete line
++ add line

-------
STEP 0:  Backup yer source. You installed it, yer responsible.

-------
STEP 1:  Open XINIT.C and change the following lines

==  num_dirs=(read(i,directories, (max_dirs*sizeof(directoryrec))))/
==           sizeof(directoryrec);
==  close(i);
==
=+  chains=(chainfilerec *) mallocx(MAX_CHAINS * sizeof(chainfilerec), "chains"
);
==  numextrn=0;
==  numchain=0;
==  numed=0;
==  sprintf(s,"%sCHAINS.DAT",syscfg.datadir);
==  i=open(s,O_RDWR | O_BINARY);
==  if (i>0) {
=+    numchain=(read(i,(void *)chains, MAX_CHAINS*sizeof(chainfilerec)))/sizeof
(chainfilerec);
==    numchain=numchain;
==    close(i);
==  }

  (Change the 50 in those to lines to MAX_CHAINS.)

-------
STEP 2:  Open BBSUTL1.C and change the line

==void do_chains(void)
=={
=+  int map[MAX_CHAINS],mapp,i,i1,ok,done;  /* change 50 to MAX_CHAINS */
==  char s[81],s1[81],*ss;
==  chainfilerec c;

-------
STEP 3:  Still in BBSUTL1.C, you *may* want to change these lines

==  show_chains(&mapp,map);
==  done=0;
==  do {
==    prt(2,get_string(621));
=+    mpl(3);                /* NOTE 1 */
--    ss=mmkey(0);           /* NOTE 2 */
++    input(ss,3);           /* NOTE 3 */
==    i=atoi(ss);
==    if ((i>0) && (i<=mapp)) {
==      done=1;
==      run_chain(map[i-1]);

NOTES:
-----
NOTE 1 - If running more than 99 chains change the 2 to a 3 in the mpl(2); 
statement. *This mpl(2); may note be there.*  I have a habit of adding mpl's 
before all my input and mmkey lines. If it is not in yours, ignore this. (Or 
add it, it'll work.)

NOTE 2 - Again, if more than 99 chains, this has got to go. Otherwise you'll 
never be able to run any chain over 99.

NOTE 3 - Here's the line if using more than 99 chains. Effectively replaces 
the mmkey line above it. You'll now have to press enter to execute any chain.
(Where mmkey would do it for you in certain circumstances.)

-------
STEP 4:  Open VARDEC.H and add this line

== #define max_buf 1024
== #define MSG_COLOR 0
== #define MAX_FILES 61
== #define MAX_BATCH 50
++ #define MAX_CHAINS 96        /* NOTE */
==
== #define INT_REAL_DOS 0x21

NOTE - this is where you specify the number of chains you want. You can 
increase or decrease this as needed (although you'll suffer through a complete
recompile each time you do). Remember, in the interests of saving memory, keep
this reasonably close to the number of chains you actually plan on having. I 
have it set to 86, and I run 85 chains. You do not have to do this in 32 chain 
increments like the subboards and directories. You can put 90 if you wanted, 
but I would stick to a 32 chain increment (32,64,96,128, etc.) just in case.

-------
STEP 5:  Do a complete recompile.


I've been using this mod for over a month now with ZERO problems. I waited to 
release it to see if Wayne changed the way the chains were handled, and he 
didn't. So this will definitely work on 4.21, 4.21a, 4.22 and even possibly 
for versions before those.

As always, if you use this I'd like to hear from you. If you are having 
problems, I'll give you all the help I can.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

The selection for March comes from Frank Reid in Spain. Frank has adapted Doug
Field's logoff lottery to v4.22, and improved it significantly.

ÚÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ¿
³ Mod Name: FR016.MOD         Mod Author: Frank Reid 1@870                  ³
³ Difficulty: Novice Modder         Date: March 14, 1993                    ³
³ WWIV Version: 4.22                                                        ³
³ Files Affected: BBS.C BBSUTL1.C FCNS.H                                    ³
³ Description: The Lucky Lotto!  Four number lottery to play at logoff or   ³
³ wherever else you might want!                                             ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

This mod is based (loosely) upon Doug Field's Logoff Lottery of many moons 
ago. It incorporates some routines from The Flying Chicken's TFC019.MOD Slot 
Machine mod. As provided, the mod is very simple, and usable by both ANSI and 
non-ANSI users. Using the functions from Tolkien's enhance.c you can really 
spruce this one up, but I'll leave that to you!  

Okay, on with the mod.
The following notations are used:

==  Existing 
=+  Modified 
++  Added 
--  Deleted

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ

** Step 1 **

Open <BBS.C>

Search for void mainmenu(void), then search for "case 'O'" and make the 
indicated changes:

==      case 'O':
==        nl();
==        nl();
==        prt(5,get_string(28));
==        helpl=12;
==        if (yn()) {
++          prt(5,"Try the Lucky Lotto? ");
++          if (yn())
++            lotto();      
==          outchr(12);
==          outstr(get_string(29));

Hop down to void dlmainmenu(void), find "case 'O'" again and change:

==      case 'O':
==        helpl=12;
==        nl();
==        nl();
==        prt(5,get_string(28));
==        if (yn()) {
++          prt(5,"Try the Lucky Lotto? ");
++          if (yn())
++            lotto();
==          outchr(12);

Save <BBS.C>

*** Step Two ***

File <BBSUTL1.C>

At the top of the file, search and add the following #include:

== #pragma hdrstop

++ #include <ctype.h>

== int ok_local(void)
Ctrl-PgDn to the very bottom of the file, and add the following function:

/* Begin Block Read */
void lotto(void)
{
  char            s[5], sr[5], stemp[5], s1[81], s2[81], ch;
  int             i, j, matches, any, done, bet, l0, l1, l2, l3;

  matches = any = done = 0;
  if (thisuser.gold > 10) {
    while (!done && !hangup) {
      done = 1;
      nl();
      pl("------= Lucky Lotto =------");
      pl("| Jackpot:      5000 Gold |");
      pl("| Four Any Order: 16 to 1 |");
      pl("| Three Numbers:   9 to 1 |");
      pl("| Two Numbers:     4 to 1 |");
      pl("| One Number: Returns Bet |");
      pl("--------------------------- ");
      nl();
      prt(5, "Enter your Lucky Lotto number: ");
      mpl(4);
      input(s, 4);
      if (strlen(s) < 4)
     done = 0;
      for (i = 0; i <= 3; i++)
     if (!isdigit(s[i]))
       done = 0;
      if (!done) {
     ansic(6);
     pl("Enter a four digit number only!");
     wait(1.0);
      }
    }
    done = 0;
    do {
      bet = 0;
      sprintf(s1, "Gold Remaining: %d", (int) thisuser.gold);
      ansic(3);
      pl(s1);
      prt(5, "Enter Your Wager: ");
      mpl(4);
      input(s1, 3);
      bet = atoi(s1);
      if ((thisuser.gold / 2) >= bet)
     done = 1;
      else {
     ansic(6);
     pl("You may bet up to half your gold!");
      }
    } while ((!done) && (!hangup));
    thisuser.gold -= bet;

    ansic(2);
    pl("Dropping the Balls...");
    ansic(3);
    npr("* * * *\b\b\b\b\b\b\b");

    for (i = 0; i <= 3; i++)
      sr[i] = (rand() % 10) + '0';

    sr[4] = 0;
    strcpy(stemp, sr);
    l3 = atoi(&(stemp[3]));
    stemp[3] = 0;
    l2 = atoi(&(stemp[2]));
    stemp[2] = 0;
    l1 = atoi(&(stemp[1]));
    stemp[1] = 0;
    l0 = atoi(&(stemp[0]));
    stemp[0] = 0;

    j = 0;
    do {
      ansic(0);
      i = (random(10));
      npr("%d\b", i);
      j++;
    } while (j < 1000);
    ansic(2);
    npr("%d ", l0);

    j = 0;
    do {
      ansic(0);
      i = (random(10));
      npr("%d\b", i);
      j++;
    } while (j < 1000);
    ansic(2);
    npr("%d ", l1);

    j = 0;
    do {
      ansic(0);
      i = (random(10));
      npr("%d\b", i);
      j++;
    } while (j < 1000);
    ansic(2);
    npr("%d ", l2);

    j = 0;
    do {
      ansic(0);
      i = (random(10));
      npr("%d\b", i);
      j++;
    } while (j < 1000);
    ansic(2);
    npr("%d ", l3);


    for (i = 0; i <= 3; i++) {
      if (sr[i] == s[i])
     matches++;
    }

    for (i = 0; i <= 3; i++)
      for (j = 0; j <= 3; j++)
     if (sr[i] == s[j])
       any++;


    nl();
    sprintf(s1, "Number: %s, Wager: %d, Lotto: %s, Matches: %d.",
         s, bet, sr, matches);
    ansic(3);
    pl(s1);
    if (matches)
      if (matches == 4) {
     sprintf(s1, "J-A-C-K-P-O-T! You just won 5000 gold pieces!");
     thisuser.gold += 5000;
     sprintf(s2, "*** Hit Lucky Lotto Jackpot. Received 5000 gold.");
      } else {
     if (any != 16) {
       if (matches == 1) {
         sprintf(s1, "You saved your bet of %d gold pieces!",
              (matches * matches * bet));
         thisuser.gold += (float) (matches * matches * bet);
         sprintf(s2, "*** Played Lucky Lotto: Won: %d, Net gain: %d.",
          (matches * matches * bet), (matches * matches * bet) - bet);
       } else {
         sprintf(s1, "You've just won %d gold pieces!",
              (matches * matches * bet));
         thisuser.gold += (float) (matches * matches * bet);
         sprintf(s2, "*** Played Lucky Lotto: Won: %d, Net gain: %d.",
          (matches * matches * bet), (matches * matches * bet) - bet);
       }
     } else {
       sprintf(s1, "Got all four in any order!  You win %d gold pieces!",
            (any * bet));
       thisuser.gold += (float) (any * bet);
       sprintf(s2, "*** Played Lucky Lotto: Won: %d, Net gain: %d.",
            (any * bet), (any * bet) - bet);
     }
    } else
      sprintf(s1, "Sorry, you didn't win any gold");
    ansic(2);
    pl(s1);
    pausescr();
    sysoplog(s2);
    return;
  } else
    pl("Sorry, you need at least 10 gold to play the Lucky Lotto!");
}
/* End Block Read */

*** Step Three ***

This is not necessary if you can/do use "MAKE FCNS" from the command line.

Open <FCNS.H>

Search for /* File: bbsutl1.c */ and add the new function:

== void show_chains(int *mapp, int *map);
== void run_chain(int cn);
== void do_chains(void);
++ void lotto(void);

Your done. Recompile and drop me a note to say "Hi!" 


ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³                  TechNOTES                  ³
               ³        Compiled by The WWIVnews Staff       ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

...Sound Blaster owners take nOTE: if ESS Technology has its way, your cards 
may soon be obsolete! A new inexpensive 8-bit audio processor chip is on the
way that quite a number of vendors are considering adding to their motherboards
with little or no cost passed on to the consumer. The chip is a single-chip
version of that contained in the Disney Sound Source, and is expected to appear
on newer 486-class motherboards by the end of 3rd quarter of this year. 

...Unlike the DSS, the new chip will reportedly be Sound Blaster and AdLib 
compatible, with versions for additional ProAudio support also being considered
for later development.

...Of course, if 8 and 16-bit sound isn't good enough for your tastes, Antex
Electronics has announced a digital audio board that has Dolby capabilites.
The Antex SX-20 is based on TI's TMS320C31 digital signal processor chip, and
provides Dolby AC-2 encoding with a frequency range of 20-20,000 kHz at
129 Kbps. While this allows you to add CD-quality sound to your applications,
this sound card comes with a hefty price tag of $2195! 

...with sound capabilites like this on the horizon, Filo had better get ready
for a flood of chatcall mods over on the Modnet!

...Tired of pressing your nose to the dhrystone in your efforts to find out
just how powerful your computer really is? Intel has come up with what they
claim is a new measurement standard for computing power that's based more on
what's important in a processor and not whether or not it can pass a whole
slew of simple tests.

...Called the iCOMP, this new CPU performance index uses four separate
components of measure that are weighted based on Intel's best guess at the
importance of each component in standard applications use. The four components
consist of 16-bit and 32-bit operations in both integer and floating point
computations, with 16-bit integer ops containing the bulk of the weight at 
67% of the total measure.

...What the iCOMP essentially establishes is a simplified measure for less
sophisticated system owners and users for determining whether one system is
truly better than another in overall power. While this might seem as the 
simple way of determining whether to buy one machine over another, the iCOMP
index has to date only been configured for comparing processors made by Intel
- none of the AMD or Cyrix chips have been tested for inclusion in the index.
Another problem with the iCOMP index is that the results are only an average 
and do not reflect subtle differences that normal benchmark tests would
detect. Video performance is currently not measured, and clock doubling is
not accurately reflected by weighing according to some critics.

...While the iCOMP might be better suited for Joe Punchclock when he
decides to buy his first system, it won't replace the benchmarks that help
more experienced computer owners understand just what's under the hood of 
that supposedly ultra-fast DX2. Finally, to make matters a bit worse, Intel
has yet to release a utility to measure your own system's iCOMP rating. While
one exists, it's currently an Intel internal product with no scheduled general
release date at press time.

...Touch screen fans will like this one: Visage Inc. has developed a monitor
stand that effectively turns any monitor into a touch screen unit. The
device, called a TouchMate, contains 8 capacitive sensors upon which the 
monitor rests, and constantly scans for any change in pressure caused by force
applied to the monitor screen. 

...The TouchMate contains drivers for Windows, but the resolution is only
40 DPI as opposed to 200 DPI for a mouse. While this is sufficient for 
moving icons around and pulling down menus, it's impractical for any sort
of high detail artwork. However, the $895 MSRP suggests that the target
market is intended to be information kiosk designers, who would benefit 
from not having to replace those stolen mice every other week!

...Redmond Rumor Time: insiders at Microsoft have leaked some interesting 
news about Windows NT. Seems that Gates himself is scared to death that
a buggy first release of NT would meet the same sort of derision that OS/2
1.0 received upon its disasterous release. This fear has reportedly pushed
the release of NT back to 4th Quarter of 1993, and the recent discovery of
a couple of bugs with the Mach kernal implementation may even extend this
delay to 1st Quarter of 1994!

...Not to take this breather lying down, IBM has pushed back the release
of OS/2 2.1 back to 2nd Quarter 1993 to allow for one last look for any
hidden stupid 32-bit tricks. While beta testers for this new version claim
the Win31 support is now essentially bug-free, "there are one or two bugs
that still need to be addressed to keep the nit-pickers from having a couple
of cows."

...While we're on the subject of rumors, word out of Borland is that Philippe
Kahn is mad as hell about the reception Microsoft got over its Access database,
and is even more ticked off at the rather slow sales of Paradox for Windows.
Word also has it that when Access was announced - reportedly six months ahead
of what Borland was informed - Kahn ordered all other development and 
production stopped and all resources diverted towards getting ParaWin out the
door before Access managed to get too good a foothold on the market.

...In the process, most retailers discovered that it was impossible to get
copies of quite a number of Borland products during 4th Quarter of 1992. The
major sufferers appear to be the people who helped Kahn buy his first Mercedes,
the programmers. According to a survey of several major software retailers,
supplies of Borland C++ 3.1, Turbo Pascal 7.0, and ObjectVision have been
either small and sporadic, or totally nonexistant. Some companies have ceased
keeping a waiting list, as the number of people begging for these products
have grown beyond the practicality of callbacks. As a result, sales of
Microsoft's competitive C++/Windows Developers Kit Upgrade have seen a jump
in recent weeks as disgruntled programmers begin to abandon the company that
apparently has abandoned them.

...Intel has given out the first details behind the Pentium's successor, the 
P6 chip. The P6 will reportedly incorporate over 10 million transistors, which
is about three times what the Pentium uses and about eight times that of a 
486DX. While this tends to fit industry predictions as to the number of 
transistors, what's shocking about the P6 is that Intel plans to ship it to 
developers in 2nd Quarter of 1994. If this chip arrives on the market at that
time, it will be the shortest generational gap of the 80x86 family of 
processors. Up to this time, the average generational span between processors
was about 44 months.

...Watchman enthusiasts will love this one: Hewlett Packard is reportedly
working on a version of the HP 95LX that will contain a built-in TV tuner!
The software will reportedly allow Palmtop owners to watch their favorite
programs in the same way inexpensive tuner boards allow computer users to 
hotkey toggle between applications and the TV screen. An interactive version
is also in the works to allow for video conferencing and e-mail from remote 
sites.

...So, the HP LaserJet 4 and 4M finally showed up on the market last month.
While the quality of the output is unquestionably the best that's out there
on the market - beating even the LaserWriter 600 series hands down - buyers
are still complaining about the lack of font cartridges. Despite the fact that
the printer has some 40 fonts already installed, most complaints seem to be
centered on the fact that the font styles normally used for income tax forms
were not included in the preinstalled set! As there are several companies
that make tax form preparation fontcarts for the LaserJet IIIP, some retailers
are noting that buyers are turning down the superior print capabilties for 
the immediate capability of printing your own 1040-EZ. Go figure.

...Cyrix has announced an alternative line of upgrade processors to compete
with Intel's OverDrive chips. The DRu series of chips come in two flavors,
one for 386DX upgrades, the other for clock doubling existing 486SX systems.
The 386DX upgrades are aimed at the DX-25 and DX-33 markets, and boost the 
performance of these chips 30-35% - around that of a 486SX-25. The clock
doubler chips, codenamed the DRu2, are aimed at the owners of older 486SX-16
and 486SX-20 systems, and will boost performance as much as 65 percent.

...On a related nOTE, Cyrix has also announced enhanced versions of its
Cx486 386 replacement series for use with faster 486 systems. Initial
reports place performance of these as-yet unnamed chips as much as 70% above
that of a stock 486SX. As with the DRu line of chips, these processors are
also intended to be "pop and drop" CPU replacements.

...In an effort to milk the established 386 user base one final time, AMD
has released an accellerated 386SX processor running at 40 MHz. Even with
most manufacturers abandoning production of 386 systems, AST, Dell and Zenith
have announced entry-level systems offering this new processor as an option.
Packard Bell, NEC, Compaq, Tandy and even IBM are reportedly considering 
using this chip for a line of low-cost simple workstations. Expect the first
clone boards to hit the parts stores in about four months.

...Thinking of buying Windows For Workgroups? Here's a couple of facts to
keep in mind that Microsoft doesn't want you to know right off the bat:

...First, the networking runs just fine, so long as all of your applications
are Windows-based. Anything that's a DOS app cannot access any of the network
features without purchasing a separate network extension package from
Microsoft. 

...Secondly, retailers have been telling potential buyers that while the DOS
apps won't have network resource access, they will eventually receive it as
the extensions will be part of DOS 6.0. Microsoft scrapped this with the 
second beta release, although the LapLink clone survived the final cut.

...In both cases, Bill Gates has gone on record and claimed that the reported
inclusion of DOS extensions in both WinGroups and DOS 6.0 was "just a big
misunderstanding". The truth of the matter, regardless of how Gates wants to
phrase it, is obviously this: Microsoft wants everyone to move to Windows, 
period. DOS apps, regardless of how well they work, will eventually be 
considered persona non grata in the Windows world, especially if you want to 
use the network resources of WinGroups.

...Those willing to argue against this observation are encouraged to take a
really hard look at the proposed specs for Windows 4.0, which will be a 
totally integrated DOS/Windows package in which you'll have to go through
Hell and high water to get to a DOS app, much less see a command prompt.

...While the future of the PCMCIA card format is questionable these days, some
companies are making a few careful steps onto that platform. IBM has announced
a series of cards for connecting laptops with PCMCIA slots into Ethernet and
Token-Ring networks, as well as a 3270 emulator for the platform. Prices are
expected to range from $400 to $900 depending on the configuration. Modems 
aren't being ignored in these halting steps. Data Race and MegaHertz have 
announced 14.4 Fax/Data modems, and IBM is also expected to release a 14.4 
modem for its ThinkPad line of laptops. 

...At the same time, Logitech is reportedly developing a PCMCIA interface
for its line of hand scanners, as well as a version to allow a HP ScanJet
to be interfaced with 486DX-class laptops. Always is also reportedly looking
into a PCMCIA-SCSI adapter, and Gravis reportedly has a twin joystick adapter
in the works.

...Pregnant Sysops take nOTE: Further study into VDT radiation and its
effects upon that bun in your oven are pointing to a far less threat than
the Sweedish studies would have us believe. According to research done by
the London School of Hygene and Tropical Medicine, there was virtually
no correlation found between spontaneous abortion and continued exposure to 
EMF through the use of computer terminals. 

...Other recent studies in England, France and Canada have shown only a slight
risk of spontaneous abortion in the first trimester of pregnancy, and that 
this risk is only about .5% higher than the normal risks during that period. 
Those same studies have also shown that the risk of spontaneous abortion may
actually decrease during the remainder of the term due to decreased physical
activity usually associated with extensive VDT work.

...A recent study by the WWIVnews staff, however, has shown that excessive
exposure to VDT radiation combined with RF emissions from high speed modems
may cause insomnia and loss of normal lifestyle for varying period of time.
Ulcers, headaches, eye strain, and high blood pressure may also develop 
depending on the type of data processed during the exposure period as well.

...On a side nOTE, those concerned about RF emissions of any sort eminating
from their PCs should grab a copy of the FCC's _Interference Handbook_. This
book outlines the rules that govern RFI and other forms of unnaturally
produced EMF, and outlines suggested methods for eliminating this sort of
interference. The book is only $2, and is available from the Government
Printing Office. The stock number you should ask for is 004-000-00482-5,
and while you're at it ask about any other computer-related publications
they may have in stock.

...Caveat Emptor: Those thinking of buying a removable hard drive system,
such as those made by PLI or SyDOS, should keep a couple of important facts 
in mind before purchasing such peripherals:

...First off, while containing the same platters as found in nonremovable
hard drives, removable units are not sealed from the environment. As a result,
they are more prone to head crashes caused by dust particles and other
contaminants, and therefor have a more limited life span.

...Secondly, to compensate for the higher level of contaminant threat, the
drive heads are restricted in how close they can travel above the surface of
the platters. This in turn imposes a theoretical limit of roughly 100 megs
per 4-platter cartridge, and a practical limit of 90 megs in actual use.

...While using the 3.5" format has allowed a slight increase in the limits,
those wishing to purchase a removable storage system for containing highly
valuable data should consider other alternatives, such as a Bernouli drive
for large amounts of data, or a Floptical for data sizes less than 20 megs
in size. 

...Who's NeXT? Word through the grapevine claims that NeXT CEO and founder
Steve Jobs has decided to cut back production of the NeXT 88000 machines,
and concentrate resources on developing the NeXTStep operating system for
a major push into the 80x86 platform market. Some 400 employees on the
hardware side were reportedly given their pink slips right after New Years,
while the software division has reportedly been hiring developers with 
advanced knowledge into Unix and Mach.

...4th Quarter 1992 was an interesting period for computer industry lawsuits.
Between September and December, three major lawsuits were either finally 
settled or brought to an effective conclusion; Apple v Microsoft and Hewlett-
Packard, Lotus v Borland, and Intel v Cyrix.

...In September, US District Judge Vaughn Walker reaffirmed his initial 
decision in the case between Apple and Microsoft/HP over Windows infringement
of the look and feel of the Macintosh interface. While this did not lead to a
final settlement in the case, Judge Walker requested additional briefs from 
all sides in the case be submitted pending a final judgement. As of press 
time, this judgement had still not been rendered.

...A more final decision was rendered in the case of Lotus v Borland. US 
District Judge Robert Keaton ruled in late September that a feature of 
Borland's Quatro Pro did infringe on Lotus' copyrights regarding the operation
of 1-2-3. The key issue was Quatro's 1-2-3 keystroke compatibility, which
Judge Keaton decided was indeed an infringement of Lotus' copyrights. While
damages have not been determined by jury, Borland has agreed to cease shipping
future copies of its Quatro line with the 1-2-3.mu compatibility file.

...Finally, US District Judge Paul Brown rendered a decision in favor of
Cyrix and SGS/Thompson over Intel's claims of copyright infringement over the
production of 486-compatible CPU's. The core arguement in Cyrix' favor lies in 
agreements signed between Intel and the now-defunkt Mostek Inc. SGS/Thompson
purchased Mostek in 1985 when the company defaulted due to its inability to
compete with Japanese competition, and acquired the rights to produce 80x86
processors through inheritance of these agreements.

...These cases have significant impact upon the computer industry. While the 
first and third cases effectively neutralize monopolistic practices that
would help keep consumer costs at a higher level than would exist under a
more competitive market, the second case has helped to muddle the picture as 
to what exactly justifies infringement of look and feel. 

...While a Microsoft victory would prevent Apple from inhibiting GUI 
development on 80x86 platforms - which would make the Macintosh more appealing
to those who need such a working environment - and the Cyrix victory will 
help keep newer platforms based on 80x86 technology affordable, the Lotus 
victory causes problems as it contradicts a previous decision concerning 
"copycat" or near-similar programs in a case between Computer Associates and 
Atari. The ruling basically stated that programs that closely mimic the 
features of older, competitive programs do not violate copyright. While
this ruling was made in a lower court, the precedent could pave way for an
eventual Supreme Court hearing on such a matter within the next two years.

...Short on desk space, but have a dog that simply can't tell the difference
between your tower case and a big tree? DataBusiness Systems may have the 
answer for you in the form of a combination keyboard case and CPU.

...The unit is slightly thicker and deeper than a 101-key unit, and contains
a 386SX-33 motherboard capable of holding 16MB of RAM. The unit has a 3.5"
internal floppy drive, and supports one internal IDE hard drive. External
ports include three parallel and two serial ports, as well as two separate 
onboard video ports capable of handling resolutions up to 1024x768, and 
supports all modes between Hercules and VGA.

...It should be noted that DataBusiness isn't the only company trying to fill
this interesting niche in the computer industry. Companies such as RightPoint,
Advanced Interlink, New World Technologies, Aamazing Technologies, and Linksys 
all offer similar systems with prices ranging from $1200 to $2100, with similar
capabilities across all platforms.

...While the obvious advantage of space savings at point-of-sale counters is
without question, these machines provide a reminder of the early days of
personal computing. How many of us remember leaning back in the recliners
with our C-64's in our laps, cables strung across the room to that 21" TV
screen, and playing Elite or Ultima IV for hours? Try doing that with your
486DX-66 tower of power, bunkie! With the right push, these systems could find
their way into that abandoned market with a great deal of ease.

...Anyone out there own a HP DeskJet? Great little printers, right? But what
won't they do that a dot matrix will? Yep, continuous feed paper, wide carrage,
and multi-part forms.

...Well, while there's naught to do for the multi-part forms, word from HP
is that development has begun on a new HP DeskJet that will handle wide sheets
and continuous feed paper. The initial version may simply be an expansion of
the DJ 500, which does not print in color, which will probably result in
an upgraded version with that capability hitting the market about six months
later.

...For owners of existing DeskJets, there's a compromise of sorts in the works
as well. A replacement for the paper receptical is being developed that will 
allow for rolls of banner paper to be mounted and run through the printer. 
Since the holder is adjustable, one HP representative joked during a 
demonstration about how this new add-on will allow those with creative minds
to make their own designer toilet paper. Talk about giving someone a gift to
show them exactly how you are thinking about them!!

...Cost and release dates havn't been established, but expect the initial MSRP
for the new DeskJet to be aroun $900, and the banner roll holder to be about
$100.

...Mac Geeks have something new to brag about, and this time it's something
that's justifiably braggable. Apple's new ergonomic adjustable keyboard has
hit the market, and despite the $299 MSRP - street prices are around $225 as
of press time - it's a keyboard that's worth the cost. The unit splits in the
middle and adjusts angularly to fit the natural position of the user's hands
more closely. When combined with removable wrist rests and adjustable tilt
supports, this keyboard helps to reduce wrist movements that can lead to Carpal
Tunnel Syndrome.

...While the alphanumeric portion of the keyboard contains special features,
such as volume controls for the speakers and a microphone switch, the even
better news for the Mac users is that the keyboard comes with a separate 10-key
numeric keypad in the same design. The keypad also contains function keys,
and can be used with or without the main keyboard installed.

...IBM users, of course, can't use this keyboard on their PC's. However, an
alternative to this keyboard is in the works thanks to the team of Spencer and
Albert. As with the Apple keyboard, the main unit is split in the middle. What
makes this keyboard different is that the two halves are totally separate,
and are mounted perpendicular to the desktop. This allows users to type with
their thumbs in an upward position, and eliminates any need to twist the wrist.

...While this keyboard is not yet available on the market, expect one to appear
in about six months.

...While we're talking about alternative keyboards, let's not forget 1992's
oddest alternative, the Twiddler. A cross between a mouse, a keyboard, and
a separate pointing device, the hand-held unit from HandyKey is probably
better suited for guitarists than for typists. Data entry is performed by
pressing 12 front buttons in conjunction with 6 back buttons to create 
characters in the same way you would form chords on a guitar. Mouse movement
is achived by simply moving the unit; a motion sensor translates the physical
movement into cursor positioning.

...While possibly helping to eliminate Carpal Tunnel Syndrome, the Twiddler is
probably best suited for lecturers who use computer-generated active displays
and need to be free of a standard keyboard during the lecture. 

...MSRP for the Twiddler is $199. Considering the chord-based nature of the
unit, expect to see signs above demo models that admonish customers not to
play "Stairway To Heaven"!

...Important side tip for potential Sound Blaster Original owners: That picture
on the box is very misleading with regards to the audio jack. Since August,
Creative Labs has been shipping the 8-bit SB cards with two standard RCA jacks
instead of the original single miniature jack. 

...While this does not mean the 8-bit cards are stereo, it does help eliminate
returns by irate and confused customers who are incapable of figuring out 
where to buy a mini to RCA split adapter, much less hook it up to their 
stereo. Since both outputs are the same mono signal, the hapless consumer can
use standard RCA cables to hook his system into his stereo and blow out his 
windows playing Falcon 3.0 to his heart's content.

...Those seeking 16-bit stereo sound should consider the Sound Blaster Pro
or the ProAudio Spectrum, but for a street price of $89 the 8-bit Sound
Blaster is perfect for those simply seeking better sound for their games and
.WAV files.

...Speaking of game playing machines, word from Nintendo hints at an agreement
with Microsoft to produce versions of Flight Simulator for the Super NES. This
agreement reportedly includes plans for Nintendo to release a 101 keyboard 
with a future upgrade to the SNES, and for Microsoft to look into ways of
bringing Windows into the Nintendo environment!

...From the Sucker Salvation File: Irwin EZTape owners, there's a bit of
hope for you on the horizon. Iomega has announced a new 250 MB tape drive
that will read both those hard-to-find-without-selling-your-sister Irwin
tapes and the standard QIC-80 cartridges.

...Granted, Irwin's Accutrak technology is patented, so the new Iomega drive
can't write in that format. However, what few people have been aware of is
that all QIC-80 drives have been capable since day one of *reading* the
proprietary Irwin format. What Iomega simply did was be the first tape drive
manufacturer to take advantage of this feature.

...Seeing as how getting tapes from Irwin is both and expensive and troublesome
proposition, the Iomega drive is a welcome addition to their extensive line 
of backup peripherals. The base drive is MSRP'd at $349, and comes with a copy
of Central Point Backup for Windows. A high-performance controller card is also
available for $150.

...As reported in a previous issue of WWIVnews, Iterated Systems has been
working on a new image file compression utility using fractal mathmatics as 
the compression algorithm. Iterated has finally released the utility as Images,
Incorporated, and given it a reasonable MSRP of $299. Also included with the
basic II package are a set of utilities for intelligent anti-aliasing of 
decompressed images, which can take a rather jagged scanned image and improve
the quality significantly.

...Average compression rates are pretty much what was initially announced. A
200 MB file can be compressed to about 5 MB, with compression times ranging
from 15 minutes to 45 minutes depending on the complexity of the image. Tests
run on a 360k .GIF file (of someone doing something you don't want to show your
kids until they get a bit older) reduced the file to 12k in under 3 minutes
on a 386DX-33 without a coprocessor. The anti-aliasing process can take as long
as an hour depending on the size and complexity of the image, but the results
can be well worth the wait.

...Word from Iterated is that a small, run-time decompressor for files that
have been fractally compressed may be released for general distribution on
bulletin boards by 2nd Quarter 1993. Expect the porno .GIF boards to take
full advantage of this opportunity and finally shrink those files that have
been their biggest hogs of disk space.

...Remember all the hoopla over the fountain pen that could write at any
angle without the ink running away from the tip? Well, Honeywell has done
something similar with the mouse that enables it to be used on walls.

...The primary difference between this $79 MSRP mouse and the traditional
Microsoft-type mouse is that the Honeywell version uses two disks on the end
of a rotatable shaft in lieu of a mouse ball. When the mouse is moved, the
disks in contact with the surface rotate and translate the movement to the
system. Since this method doesn't rely on the effects of gravity as with a
conventional mouse ball and roller assembly, the Honeywell mouse can actually
be used on walls and even ceilings if necessary.

...Another feature the Honeywell mouse provides is protection from 
contaminants. Unlike the ball and roller configuration, the disks themselves
never make any type of physical contact where contaminants could be transmitted
to the roller assembly. This eliminates the need for frequent mouse cleanings,
which would offer yet another disaster path for inexperienced users.

...Green Earth Computists take nOTE: That recycled paper you're so happy to
be using may actually be hurting the Earth through an unexpected side effect!
It seems that recycled paper is anywhere from 10% to 50% coarser than freshly
milled paper, and can decrease the life of a drum by as much as 50% depending
on the total print run. In turn, drums are disposed of at a faster rate, and
more plastic-based pollutants are added to the environment than before.

...In other words, for the want of paper the soil was lost. However, Kyocera
has announced that it will release a new silicon-based drum unit that is
guaranteed for 300,000 pages - essentially the life expectancy of most laser
printers. A ceramic-based toner cartridge helps keep the drum itself polished,
thus reducing the effects of any wear caused by the use of rougher, recycled
papers.

...While this drum will initially be available only on the Ecosys LED printer
line, Kyocera plans to offer upgrade kits for the rest of its line of laser
printers later this year. While the cost of the drum upgrade may appear a bit
expensive, once purchased the only thing users will have to purchase are the
toner refills, which in turn will drop the cost per page from an average 2.5
cents to around 3/4th of a cent.

...From the Caveat Emptor file: Purchasers of bundled discount systems should 
pay close attention as to whether or not the pre-installed software is
accompanied by the installation disks themselves. Some companies have been
granted license from Microsoft and other companies to pre-install and pre-
configure DOS, Windows, and other programs and utilities without having to
include the floppy installation disks. Owners are instead expected to 
back up their systems the very first time they turn the machine on - something
most novice users havn't a clue how to do in the first place, much less do
correctly.

...When this sort of marketing first appeared, it was blatantly illegal under
copyright. However, some system manufacturers went legit with this concept,
and oddly enough Microsoft bought the idea - and *they* were screaming the
loudest about the fact that the users weren't getting the installation disks
in the first place!

...In any case, there are a couple of companies that are being a bit more
honorable about this matter. A few companies are at least including the DOS
installation disks, as well as Windows 3.1 disk #6 for printer driver needs.
Going one step further, some of Compaq's Prolinea and DesqPro lines are sold
with pre-installed software, but the actual install disks are copied file for
file in individual subdirectories. The owner is expected to make his own copies
of the install disks from these directories, and then delete them to regain the
hard drive space. Registration cards are included for the software, so owners 
will still be eligible for support and upgrades from the respective software 
manufacturers.

...again, the word is still "buyer beware" on this matter. Make sure your 
bundled system contains at least the DOS install disks, and at least some
sort of setup similar to the Compaq offering before forking over your hard
earned cash. Otherwise you just might get burned when that drive finally
crashes!

...From the Censorship Watchdog Department: Since the service first went 
online, everyone's been bitching about Prodigy's policy of "pre-censoring" 
public postings. Regardless of the definite ethical and potential legal
issues, the Prodigy censors are now apparently using a program to pre-screen 
postings on message areas. The concept is similar to the "Cuss Mod" that
became (un)popular on the WWIV Modnet quite some time back, and is intended to 
censor posts with "dirty words" in them before they are made accessable for
public view.

...However, Prodigy appears to be letting the program make all the censoring 
decisions without any recourse to human input. One report over Usenet discussed
how a discussion regarding a person with the last name of "Fuchs" was censored,
as well as one regarding a local company CEO by the name of Richard Hedd - 
the first name being shortened in one reference, which triggered the flag.

...The best example so far of how banal Prodigy's automatic censoring operates
is the case of a recent musical discussion. The poster in question had a made a
posting which was returned with a note that he was using language that was
"inappropriate to the Prodigy service." 

He was discussing Bach's B Minor Mass - specifically, the movement titled 
"Cum Sancto Spiritu."

...Now tell me, do you *still* think the Pope would get an account on Prodigy?

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³     WWIVNet-Compatible Network Listing      ³
               ³              Compiled 4/1/93                ³
               ³           By Red Dwarf (1@6264)             ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
Contains updated entries for StarNet, TestMet, WEB, NorthStarNET, DragonsNET,
and ExpressNet.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
Network Coordinators wishing to have their networks included in this listing
should request an application from:

Red Dwarf
1@6264  WWIVNet
1@6256  IceNET
ICENET 1 AT 6256 @16259 
(WWIVLink address coming soon)

To acquire the latest, up-to-date network list, you may call:

The File Pile BBS [ASV]:
(612) 351-0144       
300/1200/2400 Baud
The "NETLIST" account is a guest account. The password is "NETLIST" and the 
last four digits are "0000". Sorry, but uploads and updates cannot be accepted
from this account, but feel free to use ASV to make a personal account on the
File Pile.

ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
APEX                            
WWIVNet @13600, WWIVLink @13600
Purgatory BBS - 306-665-0274
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
CaffNet
WWIVNet @3101
Star-Lit BBS - 301-229-2957
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
CHAOSnet
WWIVNet @9404
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
C/NET
WWIVNet @6956, IceNET @6956
Cold Fusion - 619-434-1482
Handles, Yes, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
DeathNet [] () ()
WWIVNet @19982
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
DEEPnet
WWIVNet @7405, IceNET @7405, WWIVLink @17405
Deep Space 8 - 704-553-0780
Handles, No, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
DragNET
WWIVNet @2936, IceNET @2913
Toon Town - 209-323-9412
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
DragonNET
WWIVNet @7670
Cool World - 716-681-7341
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
DragonsNet [Specific] () ()
WWIVNet @6263
Unlimited Enterprises - 612-871-7625
Handles, No, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
EliteNET [General] (29) (2-17-93)
IceNET @2462
Alley Closed BBS - 214-238-8121
Handles, Yes, Yes
"The No-Nonsense Network"  Totally democratic network using all
members' opinions and votes.  Close and friendly network.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
ExpressNET
WWIVNet @6754
Data Express - 617-247-3383
Handles, No, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
EagleNet [General] (12) (2-18-93)
IceNET @7676
Berek's Homeland - 716-826-4698
Handles, No, No
EagleNet was set up so that users and sysops could order things that
they use everyday and have it sent to their doorstep.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
FIITAnet
WWIVNet @9957
Baxter BBS - 919-878-0054
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
FILEnet [] () (1-28-93)
WWIVNet @8306
Pocket Universe - 803-552-8654
Handles, No, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
GayNet [Specific] (28) (2-1-93)
WWIVNet @15283, WWIVLink @25283
Handles, Yes, Yes
Alternate Lifestyles- don't have to be gay, lesbian, or bi to join.  No gay
bashing allowed.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
IceNET [General] (560) (1-31-93)
IceNET @1, WWIVNet @7663, WWIVLink @17652
The Great White North - 716-837-0044
Handles, Yes, Yes
Full featured network, fast updates, hundreds of message bases to choose 
from.  A friendly place to be.  Highly rated, one of the best.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
InfiNet [Specific]
WWIVNet @3082, WWIVLink @13051
The Dead Beat Club - 310-599-0479
Handles, Yes, Yes
An exclusively Southern California network.  We specialize in regional
topics and making the local BBS scene better.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
InsanityNet
WWIVNet @8355, IceNET @8385
Handles, No, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
LightNET
IceNET @5805
Storm Blade - 508-368-7971
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
M.A.G.Net [] () (1-30-93)
WWIVNet @7107
Psycho BBS - 701-780-9168
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
NorthStarNET [] () ()
WWIVNet @6259, IceNET @6259, WWIVLink @16259 
AeroTech BBS - 612-935-3505
Handles, Yes, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
NukeNet
WWIVLink @14063
The White House - 410-760-0712
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
SOLARnet
WWIVNet @3484, IceNET @3454, WWIVLink @13495 
Rap City [GSA] - 314-963-7960         
Handles, Yes, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
StarNet [Specific] (5) (4-1-93)
WWIVNet @3956, IceNET @3956  
Diamond's BBS - 319-277-0166
Handles, No, No
Local network of teenage boards to facilitate the transfer of files and
e-mail, to take the load off of the local WWIVNet/IceNET server.
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
SuperNET
IceNET @3402
The Empire - 304-465-5223
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TeenNet
WWIVNet @4053 WWIVLink @14064
Central Station - 410-315-9854
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TerraNET
WWIVNet @8861, IceNET @8857
Blue Thunder - 818-848-4101
Handles, Yes, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TestNet
WWIVNet @19960, IceNET @9994           
Test Site BBS - 919-760-4811
Handles, No, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TLCnet [] () (1-28-93)
WWIVNet @8306
Pocket Universe - 803-552-8654
Handles, No, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
TRINITY
WWIVNet @6919, IceNET @6903
No Realities - 609-825-4589
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
WEB [General] (10) (2-13-93)
IceNET @5802, WWIVNet @5813
Sanctuary - 508-892-8529
Handles, Yes, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
WWIVNet [General] (1400) (1-24-93)
WWIVNet @1
Amber - 310-798-9993
Handles, Yes, Yes
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
*.Net
IceNET @2459, WWIVLink @16976
Reynard's Keep - 214-406-1264
Handles, No, No
ÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÂÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ
               ³             Dateline: @#$*()#!              ³
               ³     Editor's Notes by Omega Man (1@5282)    ³
               ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ

From the WWIVNews Electronic Circular File:

"Dear Omega $%@$:"

"Where is the latest WWIVNews, you (#$%@!* sack of $%#%(*!?!?"

"Sincerely, your pal, 1@BR549"


Dear 1@BR549:

Ok, ok, so sue me. I'm late with the news once again. Same reasons as before,
but keep in mind even OM has to earn a living. In any case, things are sort
of back on track again, as this issue should demonstrate.

In any case, the next issue should be out about mid-May. Tenatively, I've 
gotten a couple of major articles lined up for that issue:

 - An in-depth look at DOS 6.0 and WWIV 4.22.
 - The highlights behind the SJ Games vs the US Secret Service case.

While I'm here, I should mention that there will be an updated copy of the
WWIVNews Writer's Guide out shortly, as well as a suggested article topic list.
We are requesting submissions once again, and welcome multi-part articles with
open arms!

Speaking of articles, in case you didn't notice I've been leaving in the color
codes in the Mod of the Month submissions. After viewing it through the G-Files
section of my board for a change, I decide to finally ask the question of the
WWIVNews readership as a whole: Should I start colorizing WWIVNews, or should
I stick to the more "Non-REAL-Computer Friendly" mode of B&W ANSI? E-Mail me
at 1@5282 and let me know how you feel on the matter, eh?

Finally, let me comment on an addition to WWIVNews, as well as re-announcing
a second new addition:

First, the Type 0 Forum joins WWIVNews this month as our answer to those
"Dear Editor" columns every publication has to offer. If you have something
to comment on regarding WWIV, the WWIV networks, or BBSing in general, feel
free to express those views by submitting them to the Type 0 Forum. If you
have a complaint, comment or anything else to say about WWIVNews or any of
the articles published herein, then Type 0 Forum is the place to make those
views public.

As stated in the header, submissions are edited only for punctuality and
clarity of message. We don't censor here at WWIVNews, so feel free to speak
your mind as you see fit.

(As an aside to our...er..."moralistic" readers, please try to keep the 
deletable expletives down to a bare minimum when submitting, eh?)

Secondly, I'm taking applications once again for three consultants who are
willing to act as correspondents for "The WWIVNews Advisor", which will be
WWIVNews' Q&A and problem report column. Applicants should be extremely 
familiar with setting up WWIV and at least one of the WWIV networks, as well
as being very fluent in DOS and Windows. OS/2, Novell and Lantastic experience
with WWIV is also a big plus. 

While knowledge of Turbo/Borland C++ and the WWIV source is required, it can 
be substituted depending on the level of fulfillment of the other position
qualifications listed. As everyone knows, one does not have to be a C++ guru
to be an expert at running a WWIV BBS on a network; in fact, some sysops 
register the source simply for the network access and never bother with the
headaches of modding the source! Again, it's a requirement, but a flexible
one.

Ok, I'm off my soapbox again. Remember, send all submissions, applications
and other correspondence to 1@5282!

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
³ WWIVNet node @5282. Requests for information regarding articles and other ³
³ editorial submissions, as well as back issue requests and the WWIVnews    ³
³ Writer's Guide, can be sent in e-mail to the WWIVnews editor, c/o 1@5282. ³
ÃÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄ´
³            WWIV and WWIVNet, copyright 1986,1990 by Wayne Bell            ³
³  Any product or company mentioned or reviewed herein are copyrighted of   ³
³  their respective owners, creators, and other corporate pseudoentities.   ³
ÀÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÄÙ


```
