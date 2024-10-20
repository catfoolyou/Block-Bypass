# FCPS Tech exploits
A list of functioning offline downloads for all of the stuff on my website after it got blocked, as well as instructions for bypassing consorship and jailbreaking school computers in FCPS.

### Disclaimer
~~Sh1mmer will probably not be working on FCPS chromebooks. You will probably need some way to bypass the Fog or the Tsunami, as the chromebooks use ChromeOS 128.~~

Sh1mmer works on FCPS chromebooks ONLY with the Ti50 version of the Pencil Bypass. View the writeup [here](https://github.com/catfoolyou/Block-Bypass/blob/main/pencilbypass-ti50.md)
These hacks might not work on computers outside of FCPS because every district and/or county uses different software and hardware.

Shimboot ~~is currently being tested~~ works.

## 2024/2025 update
Based on the recent changes pushed by FCPS, the only viable way to bypass their restrictions is to BYOD. 

To properly do BYOD, you *probably* shouldn't use the FCPS provided installer as your go-to option. Instead, use the wifi passwords in this repo to connect to their wifi directly (if that works).
You can also use guest wifi or download the certs from school Windows PCs (if you have access). The certs that I managed to get my hands on may or may not work. Afaik it depends on the computer and/or the OS.

Certs are available [here](https://github.com/catfoolyou/Block-Bypass/blob/9296220291856a560ac57edf9a657a80288d8eb7/FairfaxWifi.crt) and [here](https://github.com/catfoolyou/Block-Bypass/blob/9296220291856a560ac57edf9a657a80288d8eb7/certs.zip)

# WARNING
FCPS no longer gives out windows laptops to everyone. The previously working methods have been patched on their course specific windows PCs and most likely on the personal windows laptops as well.

CS students are now given access to personal windows laptops instead of chromebooks, but again they will need to be flashed and have their BIOS passwords reset so as to reinstall the OS. 

## Chrome DNS (BYOD only)

If you are bringing your own computer, you can do this to prevent sites being blocked

[Explanation for dumbasses like me](https://simpledns.plus/kb/195-how-to-enable-dns-over-https-doh-in-chrome)


![image](https://github.com/user-attachments/assets/9bcbfb46-ba32-4f2e-a4c4-6a0c6bf86684)

# Chromebooks
Most people at FCPS have been switched to chromebooks, which are much harder to jailbreak than to old Windows laptops. 
~~The easiest way to crack FCPS chromebooks would be via [this method](https://github.com/CaenJones/Chromebook-Testing/blob/main/README.md) (Mirror available [here](https://github.com/catfoolyou/Block-Bypass/blob/main/Chromebooks.md) in case the site gets taken down or it's blocked.)~~

## Sh1mmer

As of September 16th, sh1mmer with the tsunami bypass has been confirmed working with ChromeOS r128. This exploit allows for unenrollment and the ability to switch into developer mode, plus other things.

FCPS Chromebooks come in two models - HP Fortis G10 and G11. You can check this on the underside of the chromebook, which will usually be under the FCPS barcode (this varies from school to school).

G11 Chromebook: `nissa`

G10 Chromebook: `dedede`

Full writeup is available here: https://github.com/catfoolyou/Block-Bypass/blob/main/shimmer.md

## Shimboot

Shimboot is an exploit based on sh1mmer that boots a linux distribution off a USB or a spoofed unenrolled chromeOS. It works because the rootfs of the shim (a recovery image) is not verified, meaning that it can be replaced with whatever else.

FCPS High School chromebooks (`drawper`) have NOT been tested with shimboot yet.

Full writeup is available here: https://github.com/catfoolyou/Block-Bypass/blob/main/shimboot.md

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

## CRSH2TTY - Universal unenrollment (any kernver/version)
It was real the whole time

CRSH2TTY is a universal unenrollment method created by @TN Partnered and @TN Partnered 2 

How do I do it?
1) Powerwash (ctrl + alt + shift + r on the login screen)
2) Proceed through setup as normal
3) When it starts to enroll wait 1-2 seconds (no longer) and perform an EC reset (refresh + power)
4) When it starts to enroll again wait 1-2 seconds (no longer) and enter recovery (esc + refresh + power)
5) Leave if off for at least 15 hours (or longer, I would just leave it overnight)
6) When you turn it on you should be unenrolled!

discord.gg/unblock

Writeup: https://github.com/kuromuiroha/crsh2tty

## OLYBmmer/BadRecovery
BadRecovery unenrolls ALL devices that are EOL before 2024, and can unenroll current supported devices on kernel version 3 or lower.

Instructions are available here: (I am too lazy to make a proper writeup)

https://github.com/BinBashBanana/badrecovery

## Skiovox exploit

https://github.com/3kh0/ext-remover/discussions/929

## Downgrading (untested)
The chromebooks are on version 128, and it should theoretically be possible to downgrade to 120 (the lowest possible version in kernver 3)

## Unenrollment via Shimboot
FCPS chromebooks have `kernver=0x00010003`, so [CryptoSmite](https://github.com/FWSmasher/CryptoSmite) will not work.

The only viable way to do this is via [shimboot](https://shimboot.ading.dev/). More instructions on this are coming soon, I have not yet tested this method.

Instructions on shimboot are available [here](https://github.com/catfoolyou/Block-Bypass/blob/main/shimboot.md)

Instructions on sh1mmmer are available [here](https://github.com/catfoolyou/Block-Bypass/blob/main/shimmer.md)

Shimboot download: https://github.com/ading2210/shimboot/releases/download/v1.2.1/shimboot_dedede.zip

## Chromebook specs
FCPS chromebook specs:
https://cros.tech/device/drawper/

HP specs sheet: https://h20195.www2.hp.com/v2/GetDocument.aspx?docname=c07811220

HP specs on website https://support.hp.com/us-en/document/ish_5492565-5492609-16

FCPS chromebook board and shims (recovery images):
https://chrome100.dev/board/dedede

# Browser games and other crap
Again, use a [proxy](https://github.com/catfoolyou/Ultraviolet-App) to access blocked websites. Be advised that games (and sometimes yt) are somewhat laggy over a proxy connection.

If [catfoolyou.github.io](https://catfoolyou.github.io) is blocked, a mirror of my website is available [here](https://eldritchdev2.github.io/Website-v2/)

### Eaglercraft and FNAW:
The latest 1.5.2 and 1.8.8 offline clients are available for download, as well as Five Nights at Winston's.

### Other games:
Doom, Retal, Quake, Slope, Bananabread and all of the other games that must run in a web environment cannot be run locally. Might migrate my site soon.
