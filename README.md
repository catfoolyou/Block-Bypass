# FCPS Tech exploits
A list of functioning offline downloads for all of the stuff on my website after it got blocked, as well as instructions for bypassing consorship and jailbreaking school computers in FCPS.

### Disclaimer
Sh1mmer will probably not be working on FCPS chromebooks. You will probably need some way to bypass the Fog or the Tsunami, as the chromebooks use ChromeOS 128.

These hacks might not work on computers outside of FCPS because every district and/or county uses different software and hardware.

Shimboot is currently being tested.

## 2024/2025 update
Based on the recent changes pushed by FCPS, the only viable way to bypass their restrictions is to BYOD. 

To properly do BYOD, you *probably* shouldn't use the FCPS provided installer as your go-to option. Instead, use the wifi passwords in this repo to connect to their wifi directly (if that works).
You can also use guest wifi or download the certs from school Windows PCs (if you have access). The certs that I managed to get my hands on may or may not work. Afaik it depends on the computer and/or the OS.

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

## Accessing blocked websites

The easiest way to access blocked websites (such as mercuryworkshop or 3kh0 writeups) is to use a proxy. The best way to do so is to deploy said proxy on Github Codespaces or Gitpod. You might need a personal Github account to do this.

A proxy with instruction on deployment is available here: https://github.com/catfoolyou/Ultraviolet-App

After you get access to blocked websites via the proxy, it is advised to use [**shimboot**](https://github.com/catfoolyou/Block-Bypass/blob/main/shimboot.md) to properly jailbreak your chromebook (see below)

## Incognito exploit (chromeos v123, idk if it works on v128)

https://s-pscripts.github.io/incognito-v123/

A proper technical writeup of the exploit exists here, though it may be blocked. https://github.com/3kh0/ext-remover/discussions/1100

This might work on 128, I havent tested yet: https://s-pscripts.github.io/incognito-rises/

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
