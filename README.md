# FCPS Tech exploits
A list of functioning offline downloads for all of the stuff on my website after it got blocked, as well as instructions for bypassing consorship and jailbreaking school computers in FCPS.
Credit to [CaenJones](https://github.com/CaenJones) for writeups on FCPS-specific exploits, [Mercury Workshop](https://mercurywork.shop/) and [CryptoSmite](https://github.com/FWSmasher/CryptoSmite) for various Chromebook exploits, as well as [3kh0](https://github.com/3kh0) for ext-remover

### Disclaimer

Sh1mmer might not be working on FCPS chromebooks (I never tested lmao). You will probably need some way to bypass the Fog or the Tsunami. [CryptoSmite](https://github.com/FWSmasher/CryptoSmite) might be useful.

These hacks might not work on computers outside of FCPS because every district and/or county uses different software and hardware.

# Windows Laptops
If you were given a Windows laptops (Dell Latiture 3310s, for CS and other classes that need software not installable on chromebooks) you are in luck. Breaking these is pretty simple.
## Lightspeed agent
The first step is to disable Lightspeed agent.

You can use the uploaded `.bat` files (`litspedagent.bat` and `test.bat`) to kill off Lightspeed agent and disable Classroom windows, respectively. This will unblock any website as well as `wss://` (websocket) conncections to blocked domains, as well as preventing admin from getting into your computer. However this only works on Windows computers, NOT ON CHROMEBOOKS. These were originally from [here](https://fcpsoff.github.io/lightspeed.html), though the website might be blocked or taken down entirely.

An easy way to make sure that Lightspeed has been disabled is to check [this url](https://localhost:6543/block), it should show a "website down" error if you did everything right and Lightspeed is actually dead.

## Applocker (Inability to install and/or run software)
It's practically impossible to run anything other than batchfiles on school computers without fully reinstalling Windows. Either crack the BIOS password with [this](https://bios-pw.org/) or [this](http://www.biospassword.net/) (might be blocked, disable Lightspeed first), or you can take the back cover off the laptop and short the jumper pins to hard reset the BIOS password if the above sites don't give you working passwords. I would recommend making a backup image of your (unmodified) school Windows install and then restore it before turning in your computer to avoid suspicion.

To enter the BIOS (after unlocking ofc) you need to restart the laptop while holding shift.

# Chromebooks
Most people at FCPS have been switched to chromebooks, which are much harder to jailbreak than to old Windows laptops. 
The easiest way to crack FCPS chromebooks would be via [this method](https://github.com/CaenJones/Chromebook-Testing/blob/main/README.md) (Mirror available [here](https://github.com/catfoolyou/Block-Bypass/blob/main/Chromebooks.md) in case the site gets taken down or it's blocked.)

The method described there does not actually work, the only way to kill Lightspeed agent on an FCPS chromebook is as follows:
1) Open the task manager (esc + the circle button)
2) Go to the bottom and look for the green lightspeed agent icon
3) Start spamming Enter to kill the extension (tabs will crash, but you can reopen them later)
4) Repeat step 3 until the extension icon no longer appears in the list
5) Go to a website you know that is blocked (such as [catfoolyou.github.io](https://catfoolyou.github.io)), If you did everything right the site should not be blocked.

Another way to remove extensions like Lightspeed would be to use [ext-remover](https://github.com/3kh0/ext-remover), although the site is blocked so obtaining it could be a pain.

The best way to jailbreak a school chromebook (although it is the hardest way) would be to use Sh1mmer or [Cryptosmite](https://github.com/FWSmasher/CryptoSmite). All of the related sites are blocked, so use a proxy or a VPN.

FCPS chromebook specs:
https://cros.tech/device/drawper/

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
