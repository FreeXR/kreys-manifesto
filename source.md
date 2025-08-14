Please rewrite the following manifesto to sound more professional and representative without diving into the marketing lingo, remain academic and objective, but make sure that the manifesto is understandable by the general population. Use deep thinking and do not miss any detail.

---

# Kreyren's Manifesto for FreeXR Project

SOME PREAMBLE HERE

## Glossary of terms

* Eureka - Official codename for META Quest 3
* Panther - Official codename for META Quest 3S
* XR - eXtended Reality being Virtual Reality + Altered Reality also called as Mixed Reality ("MR")
* SoC - System on a Chip being the main processing unit on the device resposible

---

FreeXR is a new project created to promote, advocate and contribute to Open-Source Extended Reality ("XR") ecosystem

### Open Ecosystem

Giving everyone the access to be part of the XR community without forced Operating System and gatekeeping while making sure that the developers have secure platform, promotion and stable environment to develop their products.

### Enable Hardware Modding

Providing 3D scans of the parts to enable the development of custom hardware modifications and documentation if needs be for an engineering of more complicated parts.

### Manage anti-repair tactics

Namely on Eureka which was subject to the research: The device is built as anti-repair as possible:
* bending flex cables for the cameras in an extreme angle behind the face shield to artificially induce work hardening of the cable upon frequent re-assemblies
- FreeXR Should Reverse-engineer the flex PCB in KiCAD and make it widely available

* Lack of magnetic screws for the displays making it very difficult to get the screw in the correct position deep inside of the headset
- FreeXR Should provide these screws in alternative material to make it easier to work with without the need to use adhesive on the tip of the screwdriver

* the gasket for the plastic cover that diverts air towards the heatsink is stuck on using very weak glue which upon disassembly falls apart and makes it not seal correctly leading to lesser air circulation potentially leading to the overheating of the SoC
- FreeXR should make a 3D printable replacement part

* thin plastic piece next to strong clips on the rubber face guard leading to early damage (https://youtu.be/liVll-GVF3Q?t=80) 
* lack of repair manuals
* Over 40 screws of different lenghts making screw management a living nightmare
- Should author a repair manual including a video implementation

* Inability to get spare parts without buying new headset and then dissassembling it for parts
- FreeXR should 3D scan the plastic parts and provide them for injection moulding or 3D printing to the public
- Reverse-engineer the parts that we can reverse-engineer and find compatible component replacements

* The lenses do not provide a sufficiantly good implementation for people with various eye conditions often leading to people often having to wear eye glasses in the headset which scratch the resin lenses eventually causing the headset to be unusable and resulting in eye strain and headaches
- I was able to research a very economical and user-friendly way which involves using micromeshes and water to re-polish these lenses to be implemented into video instructions, but are still missing a solution to re-applying the anti-reflective coating.

### Locked Ecosystem of META Horizon platform

META is apparently illegaly [https://github.com/FreeXR/FreeXR/issues/2] abusing the Qualcomm fuse programmable read only memory ("QFPROM") which is a secure boot implementation which has a memory inside of the SoC to which the user or the manufacturer can write a public key and then blow an efuse making the memory inaccessible and unrewritable which is the enforced by the BootROM. If this is done by the manufacture it's impossible for the user to make changes to the system without having the private cryptographical key.

This process is called tivoization and since META is using Horizon OS on these headsets which is a fork of Android AOSP which uses the GPLv2-licensed Linux Kernel they are likely in violation of this license and when approached about access to the private cryptographical keys they stonewalled us, refuse to answer or refuse to provide them while calling us cheaters https://communityforums.atmeta.com/discussions/dev-quest/request-for-qfprom-unlock-keys-for-meta-quest-3-development/1339550

Quote by The Free Software Foundation (author of the GPLv2 license) representative: https://github.com/FreeXR/FreeXR/issues/2

### Support of The Modding Community

We cooperate with the byteus community and want to foster healthy software modding community while being strongly against cheating.

### Game Security

The game developers shouldn't be in position where they have to handle security.. We should provide guidelines and maintain an open security standard so that ideally the game developers can fully focus on developing their products and provide a crowdsourced community to find issues in their games.

Integrate the following feedback:

> Hey, meta developer here (I make games) this would ruin everything as they could install a custom os and then cheat engine if they really wanted to, being able to change variables and player prefs in real time

Reply:

```
Heyo,

i want to reply to the message you left in our form at 
<https://cryptpad.disroot.org/form/#/2/form/view/LYGT02dAJiM8mNGPRmUii2x-ZnmNBENzuNYy6jZzU00>.

As i understood you said that bootloader unlocking would be terrible 
for you as a meta developer as the end users could install custom OS, 
use cheat engine and change variables and player prefs.

So first of all, we do not support or condone cheating, I and lot of 
others in FreeXR are Kernel Developers, it's thanks to our work that 
META can have a functional OS that runs without major issues on power 
consumption and efficiency on this formfactor and you being able to 
develop your games.
This kernel is provided under GPLv2 that mandates it to be open-source 
including all executable scripts which is subject to the lawsuit.

This access is mandated by the license so that we can go in the source 
code and fix any issues as they appear which currently is not possible 
and as a result of that the META Quest platform has been riddled with 
critical bugs that META is not fixing which enables us to use CVEs to 
elevate root.. This is otherwise not even remotely possible on any 
mainstream linux distribution and is not meant to be possible by design 
which is why CVEs are public, META is just really bad at security of 
their OS fork which is what enables us to be able to get root in the 
first place.

Ragarding the security of your game. Root is being actively used ever 
since the quest was released. As you would with any 
Android/windows/linux/bsd/macos/etc.. game META is not any special 
platform to be treated differently. If you care about security of your 
game then you have to work with the assumption that client can send any 
packets to the server to gain an unfair advantage. Attestation API, 
etc.. is just a really not enough and show how fundamentally is META 
incompetent in security.

If META is mandated to comply with the license then we can make the 
whole platform much more secure for everyone to mitigate the as we 
shown very real risk of security and privacy to the user.

If you want we also actively cooperate with game developers to patch 
their games and you can contact us about it. We do this for free as we 
consider that this is our ethical obligation to manage the META's 
screwups.

~ Krey
```

## Recognized issues

### Opsec failures

1. After the root exploit was discovered Clash went on online games and started to tell in the chat the she has root.
* Clash was given mentoring on the importance of operational security and are now considered to be sufficiently reliable.

2. ilovecats went on xda forum to tell everyone that we have found root and then went to troll META reddit with rainbow LEDs post.
* ilovecats has been given mentoring as well with recommendation for self-control, i (krey) trust him that he took this to heart and learned from his mistakes.

3. The root was leaked (likely) by BreakXR
* There is an ideological difference between BreakXR and FreeXR which is why BreakXR split from us. FreeXR recognizing the risks and damage of the root wanted to keep the root private and then underground knowledge while breakXR believes in free access. After the first root exploit has been released we were able to do the needed research and cooperate with the affected game developers on securing their games and the needed cultural and ideological changes (META platform is not a unicorn with special requirements, treat as standard android game and assume that the client can send any packet to the server). After FreeXR were able to risk manage and ensure that this is recognized we no longer feel the need to obstruct these CVE re-implementations, so in this area this ideological conflict no longer exists. For novel root vulnerabilities FreeXR insist on following developer ethique and recognize that as kernel developers we have a duty to report new vulnerabilities prior to releasing. BreakXR seems to be more careless in this area where the idealogical difference stands to remain.

### Failures of the Management

After the root repository was leaked some members of the administration panicked and wanted to panic-release the root for everyone (ilovecats, noah, mandi and others) which lead to some of the members panic-making announcements with chaotic messaging. This failure must be recognized as FreeXR must work in unity and with consensus to be able to work efficiently while learning from the failures of similar projects most notably the anonymous movement. We are not black hats, it's in our best interest that those who develop for the platform stand the least risk in being able to sustain their development so our messaging and coortination must be well coordinated.
Even with the root leaked, if we released it we would have complicated the lifes of cooperating developers who asked us to delay the root release until they are able to implement sufficient managements so at this situation it was the right choice to try to limit the access to the root as much as possible.

Now it's my opinion that these developers were given very early heads up with lot of informations and resources on how to secure their products to now move on release without limits if the root is derived from public Common Vulnerabilities and Exposured ("CVE"). CVE's are by design released AFTER the developers were given early headsup with a reasonable amount of time to fix these security issues. META, inc. has repeatedly proven their incompetence to act quickly enough on managing these issues which is why the BreakXR and FreeXR are able to discover and utilize root elevantion vulnerabilities in a white hat way. Even if FreeXR tries it's best to contain the affected vulnerabilities in the wild the required resources to be able to do so are beyond unreasonable and are solely caused by META's own incompetence namely:

* https://github.com/Anonymous941/zygote-injection-toolkit made by our member Anonymous941 implementing Android Zygote injection vulnerability (CVE-2024-31317)
* https://github.com/metaredteam/external-disclosures/security/advisories/GHSA-wmcc-g67r-9962 was disclosed by META's own red team 2 years ago yet the vulnerability remained present until present day on many devices.
* https://github.com/tamirzb/CVE-2021-1961 - still vulnerable in 2025, but would take a lot of resources to abuse for KASL defeat.
* CVE-2023-4622, a UAF in the Android kernel which appears to still be unpatched to this day while being too difficult and unreliable to reproduce to gain root
* 

These are just few highlights, these software vulnerabilities grow nearly exponentially as time goes to the point where we are confident that we can find root vulnerability for each firmware release. These incidents to me highlight the systematical and cultural problems related to platform security on META's side, FreeXR's responsibility related to security ends after disclosure of the vulnerabilities to the Linux Kernel Mainline.

### The Endless Cat and Mouse Game with META

FreeXR is not the "find root vulnerability" project and it's frenkly horrible that we are in this situation to begin with. We are developers who are excited about XR and want to develop on the platform, but are gatekept by apparent META's abuse of Qualcomm's QFPROM tivoization which appears to be illegal under the GPLv2 license as per statement by the Free Software Foundation's (author of the license) representative:

Quote:
> People who write that the GPLv2 permits tivotization have never read the GPLv2. gnu.org/licenses/old-licenses/gpl-2.0.en.html "The source code for a work means the preferred form of the work for making modifications to it. For an executable work, complete source code means all the source code for all modules it contains, plus any associated interface definition files, plus the scripts used to control compilation and installation of the executable." - as you can see, it does not say; "object code that does not execute", it says execute-able. Enforcing that part is up to the copyright holder and the FSF determined it was too big of a gamble whether a court would know English, so they wrote the GPLv3, fixing many problems found in the GPLv3, which in fact permits tivotization for commercial-only hardware (as some businesses wanted that). As you can see, unless they provide a script that installs an executeable, they are not in compliance with the the GPLv2. I figure they haven't supplied the relevant install script, but if they have supplied and install script that installs a non-executable, they are not in compliance either.

Among other apparent violations of the EU law which makes it impossible for us to load our own Operating System on the devices without hardware attacks and are currently in contact with a lawfirm about approaching META about this legally as when we approached META about this they gave us automated reply about cheating and stone walled us.

