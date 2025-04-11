# FCPS Tech exploits
A list of functioning offline downloads for all of the stuff on my website after it got blocked, as well as instructions for bypassing consorship and jailbreaking school computers in FCPS.

> [!IMPORTANT]
> This document is aimed mainly at FCPS systems and students *inside* FCPS. If you are **OUTSIDE** of FCPS, you will need to check your chromebook model [here](https://docs.mrchromebox.tech/docs/supported-devices.html#device-listing).
> If your device is listed under `Intel Alderlake-N` OR `AMD Mendocino`, this means that you have a Ti50 board, and you are [SOL](https://en.wikipedia.org/wiki/List_of_U.S._government_and_military_acronyms#:~:text=SOL%20%E2%80%93%20Shit%20Out%20of%20Luck%20(U.S.%20Army)) and unenrolling is only possible via the Pencil Method (see below). Otherwise, you have an older system and you can unenroll via sh1mmer, shimboot or other "conventional methods"

> [!WARNING]
> Sh1mmer and most recent unenrollement exploits work on FCPS chromebooks. If you somehow have a Ti50 board (which you probably dont, so things SHOULD work normally) use the Ti50 version of the Pencil Bypass[^1] . View the writeup [here](https://github.com/catfoolyou/Block-Bypass/blob/main/shimmer.md).
>
> Recent leaks from inside DIT have proven than most, if not ALL chromebooks in FCPS have cr50 boards.
> 
> These hacks might not work on computers outside of FCPS because every district and/or county uses different software and hardware.
>
> Shimboot works, PROBABLY with similar issues.

## Legal disclaimer and anti-censorship statement

This repo has been created to help students bypass and combat district censorship and restrictions. I **DO NOT** endorse or encourage the useage of the following exploits for cheating, theft, and/or harmful activity (including, but not limited to exploiting cybersecurity). 

To FCPS DIT:
CIPA does **NOT** give you the legal right to compromise student privacy on the internet and/or limit access to information on the internet, which **IS** a right of all students. The purpose of this "exploit doc" is to help people protest excessive censorship and unethical DIT practices. Action taken against people who use these exploits can be ground for legal counteraction.

To learn more, please visit https://redflagmachine.com/research/ for an example of the censorship and rights violations that are incurred via internet censorship.

# Chromebooks
Most people at FCPS have been switched to chromebooks, which are much harder to jailbreak than to old Windows laptops. 

G10 chromebooks (drawper) have cr50 chips, which the G11 ones (yavijo) have might, but probably dont have ti50, making it harder to unenroll if you have a ti50.  

According to a high-level leak from inside DIT, *MOST*, if not all FCPS chromebooks have Cr50. Highschool Drawper chromebooks ALL have Cr50 chips [(proof)](https://docs.mrchromebox.tech/docs/supported-devices.html#:~:text=HP%20Fortis%2014%20G10,CR50%20(SuzyQ)%2C%20jumper), while the middle school Yavijo ones are Ti50 *capable*, but we have older models that have Cr50 chips [(proof)](https://docs.mrchromebox.tech/docs/supported-devices.html#:~:text=HP%20Fortis%2014%20inch,CR50/Ti50%20(SuzyQ)).

**The problem is that some middle schools have gotten Ti50 `yavijo` chromebooks in later deployments, so that will depend on your school**

See the Pencil Sharpener section below for a full explanation of this exploit

If something doesnt work for some reason, it *MIGHT* be because you are unfortunate enough to have a Ti50, in which case you are shit outta luck, unless you can BYOD.

To prevent admin from finding out about your unenrollment, use **fakemurk** or **murkmod** (recommended) to fake enrollment. See the corresponding section below for more details.

## Lightspeed killer (LTMEAT print) - NOT unenrollment!

1) Open a new tab.
2) Put `chrome-extension://adkcpkpghahmbopkjchobieckeoaoeem/manifest.json` in the URL bar BUT DO NOT PRESS ENTER (Don't open the page)
3) Drag the tab to a new window, while dragging press enter to open the link.
4) The link should open successfully.
5) Ctrl + p, then click More settings. Switch both Margins and Scale from Default to Custom. Set Scale to 200.
6) Bring the dotted-blue box borders: right to completely left; down to completely up. (This makes it so a few pages makes a lot more than it should).
7) Open another tab
8) Put `chrome-extension://adkcpkpghahmbopkjchobieckeoaoeem/main.js` in the URL bar BUT DO NOT PRESS ENTER (Don't open the page)
9) Drag the tab to a new window, while dragging press enter to open the link.
10) Immediately after opening it, drag the tab again, holding your mouse for 4-5 seconds. (This will bypass the second auto-close check)
11) Drag it back into the window.
12) ctrl + p, then wait until 203,000≈ pages appear in the top right corner.
13) ↻ , and while it is refreshing, two-finger-click/right-click the current tab bar. Click Duplicate. Then open `chrome://extensions/?id=adkcpkpghahmbopkjchobieckeoaoeem` into a completely new tab
14) Click Allow access to file URLs and the duplicated tab will close automatically. Lightspeed will now be forced to read 2(203,106) pages of its own data, rendering it useless. You are now able to close all tabs.


## Icarus
An exploit that allows you to unenroll by managing the chromebook from an arbitrary device.

Has not yet been tested, but it should work on FCPS chromebooks, since they have Cr50 chips.

You will need to downgrade to v127 first, using recovery images from [chrome100](https://chrome100.dev/board/dedede) (this is for `drawper` chromebooks only, `yavijo` ones have `nissa` boards)

1) Get a USB and burn the [recovery image](https://dl.google.com/dl/edgedl/chromeos/recovery/chromeos_15917.71.0_dedede_recovery_stable-channel_mp-v50.bin.zip) onto it (link is for v127 for `dedede`)
2) ESC + POWER + REFRESH (you MIGHT need to do this twice (idk)), then follow instructions to recover from USB.
3) Use the v127 USB from step 1 to recover and downgrade to v127

You will need a shim prebuild for you chromebook for this exploit (from [here?](https://dl.fanqyxl.net/ChromeOS/Prebuilts/Icarus))

1) Burn the shim onto a USB (find the one for your board)
2) ESC + POWER + REFRESH, recover from USB, then boot from it
3) Run the server on a linux pc/laptop ON THE SAME WIFI as the chromebook (i.e. school wifi)
4) After rebooting into ChromeOS verified mode following using an Icarus shim, do not click "continue". Instead, manually open the Network Configuration by clicking on the bottom-right icons which contain the time, WiFi, and Battery status.
5) Once in Network Configuration, connect to your WiFi and enter the proxy settings.
6) Set "Connection Type" to Manual
7) Set the "Secure HTTP" IP address to the IP Icarus Lite gives you
8) Set the "Secure HTTP" port to the port Icarus Lite gives you
9) Click "Save"
10) Resume the ChromeOS setup process as normal and Icarus Lite should unenroll you.

Full explanation and writeup available here: https://github.com/fanqyxl/icarus?tab=readme-ov-file

Important files: https://git.kxtz.dev/kxtzownsu/Icarus-Lite.git

## Pencil sharpener (ti50 only)
Full writeup: https://github.com/truekas/PencilSharpener/tree/main

This is basically sh1mmer but for `yavijo` chromebooks WITH Ti50 chips, which are present ONLY in certain middle schools.

If you have the `dedede` chromebooks, this does not apply to you and you can unenroll via "conventional methods", i.e. sh1mmer, shimboot, icarus, etc.

## Sh1mmer
As of September 16th (2024 I think), sh1mmer with the tsunami bypass has been confirmed working with ChromeOS r128. This exploit allows for unenrollment and the ability to switch into developer mode, plus other things.

FCPS Chromebooks come in two models - HP Fortis G10 and G11. You can check this on the underside of the chromebook, which will usually be under the FCPS barcode (this varies from school to school).

G11 Chromebook: `nissa`

G10 Chromebook: `dedede`

Full writeup is available here: https://github.com/catfoolyou/Block-Bypass/blob/main/shimmer.md

## Shimboot
Shimboot is an exploit based on sh1mmer that boots a linux distribution off a USB or a spoofed unenrolled chromeOS. It works because the rootfs of the shim (a recovery image) is not verified, meaning that it can be replaced with whatever else.

FCPS High School chromebooks (`drawper`) have NOT been tested with shimboot yet.

Full writeup is available here: https://github.com/catfoolyou/Block-Bypass/blob/main/shimboot.md

## Br1ck
It is capable of unenrolling all devices with a Cr50 chip on the latest version, v130. It has a low chance of being patched without a release of a new Chromebook model.

Theoretically it should work on all FCPS chromebooks, and some people have actually used it successfully.

`nissa` chromebooks (the G11 ones) *might* not work. Don't come back here bitching about it.

Full writeup and instructions are here: https://br1ck.vercel.app/

## BadApple (pretty sure we don't have miniOS lmfao)
Basically an exploit that does the same thing that sh1mmer does but for keyrolled boards like `nissa` (the `yavijo` chromebooks!)

WILL NOT WORK IF YOU HAVE Kv5!

How it works:

1) enter developer mode with ESC+REFRESH+POWER and CTRL+D
2) when you reach the block screen, press ESC+REFRESH+POWER again
3) select Internet Recovery
4) when miniOS loads in, press CTRL+ALT+REFRESH(open the VT3)
5) you now have a shell you can run commands in

Then follow the instructions here: https://github.com/applefritter-inc/BadApple-icarus?tab=readme-ov-file#2-usbless-method

Full writeup: https://github.com/applefritter-inc/BadApple

## SuzyQ cable exploit (requires unenrollment)
Full explanation here: https://docs.mrchromebox.tech/docs/firmware/wp/disabling.html and here https://docs.mrchromebox.tech/images/wp/Drawman_wp.jpg

This will allow you to disable Hardware WP without opening your device, and this may not work on all devices. You also need to be unenrolled first or have FWMP off with Developer Mode on.

Please note to do this Kajig you need to own a SuzyQ cable or adapter, I won't be guiding you on where to buy one but if you would like to make one here are some schematics:  https://cdn.sparkfun.com/assets/9/e/f/8/2/951-00273-01_20180607_suzyqable_SCH_1.pdf

Now that you got your SuzyQ, here's what you do next.

Open a root shell on your Chromebook, this can be on a shim or within crosh, doesn't matter

Run `gsctool -a -o`, whenever it tells you to Press PP, press the power button

At the end of that process it'll restart and you'll be out of Developer Mode, turn it back on and head back to the terminal

Plug in your SuzyQ, on most devices you'd use the Right USB C port and then plug the USB A in anywhere, try your other ports if that doesn't work for you.

Once it's plugged in, in the `lsusb` command you should see the CR50 with an `18d1:5014` USB ID, if you don't see this try replugging.

Now that you see that, make sure that the TTY is open via running `ls /dev/ttyUSB*`, you should see TTY 0, 1, and 2.

To disable WP, run each of these one by one
`echo "wp false" > /dev/ttyUSB0`

`echo "wp false atboot" > /dev/ttyUSB0`

`echo "ccd reset factory" > /dev/ttyUSB0`

Reboot, then run
`flashrom --wp-disable`

Run `crossystem wpsw_cur`, this should output 0.

## Downgrading kernel versions (kernver version switcher), requires unenrollment

To prevent most exploits being patched, you can downgrade both chrome version and kernver to something manageable.

Use KVS, with a full writeup and instructions available here: https://github.com/kxtzownsu/KVS

Get images from chrome100.dev

G11 Chromebook: `nissa`

G10 Chromebook: `dedede`

Full instructions are available here: https://chrome100.dev/guide

## GBB flags (requires unenrollment)

Use Rigtools to set GBB flags and fix shit on your chromebook

https://binbashbanana.github.io/gbbflaginator/

https://docs.titaniumnetwork.org/kajigs/rigtools/

## Idfk what this is, Jones was bitching about it so it could be good
It may be possible on unenrolled Chromebooks with developer mode enabled to run `vpd—i RW_VPD -s check_enrollment=1` in VT2 to bypass policy and re-enroll. An exploit kit named Rigtoolsv2 also claims to have functionality called `Riienrollment`, which can also bypass enrollment policy set in the admin console.

## Fakemurk/murkmod (requires unenrollment)
To prevent admin from checking unenrollment via GAC (admin console) and finding unenrolled chromebooks, use FakeMurk or Murkmod.

Note that [Fakemurk](https://github.com/MercuryWorkshop/fakemurk) is UNMAINTAINED, so murkmod is recommended.

Murkmod REQUIRES devmode (set GBB flags to `0x8000`, `0x8090`, or `0x8091`), though you probaby should have that enabled if you unenrolled.

Installation instructions are available here: https://github.com/rainestorme/murkmod/blob/main/docs/installation.md

## OLYBmmer/BadRecovery (patched maybe)
BadRecovery unenrolls ALL devices that are EOL before 2024, and can unenroll current supported devices on kernel version 3 or lower.

Instructions are available here: (I am too lazy to make a proper writeup)

https://github.com/BinBashBanana/badrecovery

## Webview exploit
A random hole in chrome login that allows for unrestriced browsing (one tab only)

1) Add an account to chrome or go to chrome://chrome-signin on a chromebook
2) Enter `google@d11.org` as the email and complete the captcha/security check
3) Click sign-in options
4) When prompted, click Sign in with Github
5) Click on Docs
6) Scroll to the bottom and click on Pricing
7) In the search bar type "google"
8) In the right sidebar click on `google.com`
9) You now have a tab that is unaffected by any extensions

## RMA shims
Misc. info and documentation on RMA shims

https://chromium.googlesource.com/chromiumos/platform/factory/+/HEAD/setup/RMA_SHIM.md

https://chromium.googlesource.com/chromiumos/platform/factory_installer/+/HEAD/README.md

## Misc exploits
A series of exploits for different ChromeOS versions, some might be outdated or patched.
Some might work, I didnt test any of this

https://github.com/Burvyn/Corellium

**Unenrollment:**

https://github.com/Burvyn/Corellium/tree/main/Exploits%20and%20Tools

## Chromebook specs
FCPS chromebook specs:
https://cros.tech/device/drawper/

HP specs sheet: https://h20195.www2.hp.com/v2/GetDocument.aspx?docname=c07811220

HP specs on website https://support.hp.com/us-en/document/ish_5492565-5492609-16

FCPS chromebook board and shims (recovery images):
https://chrome100.dev/board/dedede

# BYOD shits and bypasses

## Wifi instructions
Based on the recent changes pushed by FCPS, the best way to bypass their restrictions is to BYOD. 

**You can also do this if you unenrolled your chromebook or flashed a Windows laptop (if you have one somehow)**

To properly do BYOD, you *probably* shouldn't use the FCPS provided installer as your go-to option. Instead, use the wifi passwords in this repo to connect to their wifi directly (if that works).
The certs that I managed to get my hands on may or may not work. Afaik it depends on the computer and/or the OS.

To use the installer, sign in a GUEST, NOT with your FCPS username. Download the certs manually and install as per the instructions provided. DO NOT use `2.2.2.2`, use `https://xprsscnctvm.fcps.edu/enroll/FairfaxCountyPublicSchools/Production/reset` instead.

## Chrome DNS (BYOD only)

If you are bringing your own computer, you can do this to prevent sites being blocked

[Explanation for dumbasses like me](https://simpledns.plus/kb/195-how-to-enable-dns-over-https-doh-in-chrome)

![image](https://github.com/user-attachments/assets/9bcbfb46-ba32-4f2e-a4c4-6a0c6bf86684)

# Windows laptops and PCs

FCPS no longer gives out windows laptops to everyone. The previously working methods have been patched on their course specific windows PCs and most likely on the personal windows laptops as well.

CS students are now given access to personal windows laptops instead of chromebooks, but again they will need to be flashed and have their BIOS passwords reset so as to reinstall the OS. 

Windows PCs and laptops have a bundled installation of Java 17, located in `C:/Program Files (x86)/jGRASP/bundled/java/bin/java.exe`. This can be used to run modern Java software, including (but not limited to) Java based source ports of many older games. Look [here](https://github.com/catfoolyou/Block-Bypass/edit/main/README.md#windows-pc-games) instructions on running Java ports of Doom and Quake 2 (included as examples.) 

The following [script](https://github.com/catfoolyou/EaglerGradleScripts/blob/main/EaglerGradle.bat) is linked as an example of setting up gradle to work with a bundled Java installation. The same repo contains modified `build.gradle` and `gradle.properties` for compiling Java applications with a bundled installation.


### Eaglercraft and FNAW:
The latest 1.5.2 and 1.8.8 offline clients are available for download, as well as Five Nights at Winston's.

### Other games:
Doom, Retal, Quake, Slope, Bananabread and all of the other games that must run in a web environment cannot be run locally. Might migrate my site soon.

# Windows PC games

### Quake 2
Download [platform_wx_full.zip](https://www.dropbox.com/scl/fi/f1yspvrcart3delf87uss/platform_wx_full.zip?rlkey=q0yu8x3ab4yn6ktwwrvcmk1ux&st=swq45p8a&dl=0), extract, go to the `bin` folder and run `fullgame.bat +set basedir "Quake 2"`

### Doom
Download `mochadoom.jar`, get the IWADS and run `java -jar mochadoom.jar -iwad file.wad` replacing `file.wad` with your IWAD file

### Build engine games (Blood, Duke Nukem, etc)
Download [BuildGDX](https://m210.duke4.net/index.php/downloads/send/8-java/54-buildgdx), then get your hands on the game files (usually from the internet archive), and play it. 

Blood: https://www.mediafire.com/file/o19ch8bxtxj6i59/Blood_DOS_Files_EN.zip/file

Duke Nukem 3d: https://archive.org/download/DUKE3D_DOS/DUKE3D.zip

[^1]: Tf is this about?? None of them have ti50 afaik, at least none of the highschool ones
