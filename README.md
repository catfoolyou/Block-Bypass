# FCPS Tech exploits
A list of functioning offline downloads for all of the stuff on my website after it got blocked, as well as instructions for bypassing consorship and jailbreaking school computers in FCPS.

### Disclaimer
Sh1mmer will probably not be working on FCPS chromebooks. You will probably need some way to bypass the Fog or the Tsunami, as the chromebooks use ChromeOS 124.

These hacks might not work on computers outside of FCPS because every district and/or county uses different software and hardware.

Shimboot is currently being tested.

## 2024/2025 update
Based on the recent changes pushed by FCPS, the only viable way to bypass their restrictions is to BYOD. 

To properly do BYOD, **DO NOT** use the FCPS provided installer, it WILL screw stuff up on your computer. Instead, use the wifi passwords in this repo to connect to their WIFI directly.

~~# Windows Laptops
If you were given a Windows laptops (Dell Latiture 3310s, for CS and other classes that need software not installable on chromebooks) you are in luck. Breaking these is pretty simple.~~
~~## Lightspeed agent
The first step is to disable Lightspeed agent.~~

~~You can use the uploaded `.bat` files (`litspedagent.bat` and `test.bat`) to kill off Lightspeed agent and disable Classroom windows, respectively. This will unblock any website as well as `wss://` (websocket) conncections to blocked domains, as well as preventing admin from getting into your computer. However this only works on Windows computers, NOT ON CHROMEBOOKS. These were originally from [here](https://fcpsoff.github.io/lightspeed.html), though the website might be blocked or taken down entirely.~~

~~An easy way to make sure that Lightspeed has been disabled is to check [this url](https://localhost:6543/block), it should show a "website down" error if you did everything right and Lightspeed is actually dead.~~

~~## Applocker (Inability to install and/or run software)
It's practically impossible to run anything other than batchfiles on school computers without fully reinstalling Windows. Either crack the BIOS password with [this](https://bios-pw.org/) or [this](http://www.biospassword.net/) (might be blocked, disable Lightspeed first), or you can take the back cover off the laptop and short the jumper pins to hard reset the BIOS password if the above sites don't give you working passwords. I would recommend making a backup image of your (unmodified) school Windows install and then restore it before turning in your computer to avoid suspicion.~~

~~To enter the BIOS (after unlocking ofc) you need to restart the laptop while holding shift.~~

~~## LAN connections
LAN connections do not work on FCPS wifi, you will need some sort of proxy to conncet between computers.~~

# WARNING
FCPS no longer gives out dell laptops. The above methods have been patched on their course specific windows PCs.

# Chromebooks
Most people at FCPS have been switched to chromebooks, which are much harder to jailbreak than to old Windows laptops. 
~~The easiest way to crack FCPS chromebooks would be via [this method](https://github.com/CaenJones/Chromebook-Testing/blob/main/README.md) (Mirror available [here](https://github.com/catfoolyou/Block-Bypass/blob/main/Chromebooks.md) in case the site gets taken down or it's blocked.)~~

Apparently all of the methods on that page were patched and no longer work, so see below for proper instructions.

## Lightspeed agent - THIS HAS BEEN PATCHED!
~~The method described there does not actually work, the only way to kill Lightspeed agent on an FCPS chromebook is as follows:~~
~~1) Open the task manager (esc + the circle button)~~
~~2) Go to the bottom and look for the green lightspeed agent icon~~
~~3) Start spamming Enter to kill the extension (tabs will crash, but you can reopen them later)~~
~~4) Repeat step 3 until the extension icon no longer appears in the list~~
~~5) Go to a website you know that is blocked (such as [catfoolyou.github.io](https://catfoolyou.github.io)), If you did everything right the site should not be blocked.~~

~~Another way to remove extensions like Lightspeed would be to use [ext-remover](https://github.com/3kh0/ext-remover), although most of them have been patched.~~

## Disable automatic updates (Also patched)
~~To prevent chromeOS from updating and patching certain exploits, you need to disable updates. For this you will need to use [CAUB](https://github.com/red-stone-network/bypass-central/blob/main/chromebooks/caub.md), which is available [here](https://github.com/catfoolyou/Block-Bypass/blob/main/chrome%20automatic%20update%20blocker.html). Not sure if this works though.~~

## Downgrading (untested)
The chromebooks are on version 124, and it should theoretically be possible to downgrade to 120 (the lowest possible version in kernver 3)

## Unenrollment (untested, WIP)
FCPS chromebooks have `kernver=0x00010003`, so [CryptoSmite](https://github.com/FWSmasher/CryptoSmite) will not work.

The only viable way to do this is via [shimboot](https://shimboot.ading.dev/). More instructions on this are coming soon, I have not yet tested this method.
It would probaby be best to use an SD card instead of a USB for this.

## Chromebook specs
FCPS chromebook specs:
https://cros.tech/device/drawper/

HP specs sheet: https://h20195.www2.hp.com/v2/GetDocument.aspx?docname=c07811220

HP specs on website https://support.hp.com/us-en/document/ish_5492565-5492609-16

FCPS chromebook board and shims (recovery images):
https://chrome100.dev/board/dedede

# Browser games and other crap
If [catfoolyou.github.io](https://catfoolyou.github.io) is blocked, a mirror of my website is available [here](https://eldritchdev2.github.io/Website-v2/)
### Eaglercraft and FNAW:
The latest 1.5.2 and 1.8.8 offline clients are available for download, as well as Five Nights at Winston's.
### Java games
Windows laptops (NOT chromebooks) have Java 17 installed. You can use this to your advantage by installing and running Java source ports of games like Doom and Quake 2. 
Simply google "[game name] java port" to search up source ports, they exist for most older games.
### Other games:
Doom, Retal, Quake, Slope, Bananabread and all of the other games that must run in a web environment cannot be run locally. Might migrate my site soon.
