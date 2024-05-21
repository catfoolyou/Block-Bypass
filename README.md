# Block-Bypass
A list of functioning offline downloads for all of the stuff on my website after it got blocked, as well as instructions for bypassing consorship and jailbreaking school computers in FCPS.
These hacks might not work on computers outside of FCPS because every district and/or county uses different software and hardware.

# Windows Laptops
If you were given a Windows laptops (Dell Latiture 3310s, for CS and other classes that need software not installable on chromebooks) you are in luck. Breaking these is pretty simple.
## Lightspeed agent
The first step is to disable Lightspeed agent.

You can use the uploaded `.bat` files (`litspedagent.bat` and `test.bat`) to kill off Lightspeed agent and disable Classroom windows (respectively). This will unblock any website as well as `wss://` (websocket) conncections to blocked domains, as well as disabling admin access to your computer. However this only works on Windows computers, NOT ON CHROMEBOOKS. These were originally from [here](https://fcpsoff.github.io/lightspeed.html), though the website might be blocked or taken down entirely.

An easy way to make sure that Lightspeed has been disabled is to check [this url](https://localhost:6543/block), it should show a "website down" error if you did evrything right and Lightspeed is actually dead.

## Applocker (Inability to install and/or run software)
It's practically impossible to run anything other than batchfiles on school computers without fully reinstalling Windows. Either crack the BIOS password with [this](https://bios-pw.org/) or [this](http://www.biospassword.net/) (might be blocked, disable Lightspeed first), or you can take the back cover off the laptop and short the jumper pins to hard reset the BIOS password if the above sites don't give you working passwords. I would recommend making a backup image of your (unmodified) school Windows install and then restore it before turning in your computer to avoid suspicion.

To enter the BIOS (after unlocking ofc) you need to restart the laptop while holding shift.

# Chromebooks


# Browser games and other crap
If [catfoolyou.github.io](https://catfoolyou.github.io) is blocked, a mirror of my website is available [here](https://eldritchdev2.github.io/Website-v2/)
### Eaglercraft:
The latest 1.5.2 and 1.8.8 offline clients are available for download. 
### Five nights at Winston's
The offline download is available.
### Other games:
Doom, Retal, Quake, Slope, Bananabread and all of the other games that must run in a web environment cannot be run locally. Might migrate my site soon.
