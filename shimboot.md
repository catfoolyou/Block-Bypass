# Shimboot on FCPS Chromebooks

Shimboot is an exploit based on sh1mmer that boots a linux distribution off a USB or a spoofed unenrolled chromeOS.
It works because the rootfs of the shim (a recovery image) is not verified, meaning that it can be replaced with whatever else.

### If you just want the instructions, click [here](abc)

Shimboot is entirely case closed, but it has only been tested on Middle school chromebooks (`yavijo`).
FCPS High School chromebooks (`drawper`) have **NOT** been tested with shimboot yet.

Usually high schools will use `drawper` and middle schools will use `yavijo`.
However, it can sometimes vary.

#### To check the model of your chromebook,
  - Flip the chromebook over to the back
  - Find the **black** sticker
  - Check the model name which will be in the bottom right

If the model name is `HP Fortis 14 G11 Chromebook`, you have the `yavijo` chromebook.
If the model name is `HP Fortis 14 G10 Chromebook`, you have the `drawper` chromebook.
Remember the name of the chromebook! You will need it later.

## Bypassing Instructions

If you haven't already checked the name of your chromebook, do it [here](abc).

#### What you'll need:
- 1GB or over USB flash drive or SD Card (I recommend over 16GB if you want to use linux)
- Another Computer
- [Chromebook Recovery Utility](abc) (optional, use BalenaEtcher, Rufus, or `dd` if you can't use it)
- Shimboot Images (about 1.5GB, scroll down for download)

### Preparing the USB Drive/SD Card
If you haven't already, install Chromebook Recovery Utility from the chrome web store.
If you don't use chrome or simply don't want to use Chromebook Recovery Utility, you can use any other USB image writer like BalenaEtcher, Rufus, or `dd` if you're on linux.

#### Download the Shimboot Images from here:
HP Fortis G10 (`drawper`): Download
HP Fortis G11 (`yavijo`): Download

They will be about 1.5GB in size.

Next, open the Chromebook Recovery Utility from the extensions menu.
In the top right of the window, click the settings button and select "Use Local Image".
Select the shimboot image (`drawper.bin` or `yavijo.bin`) and start the process.

After you finished writing the image to the USB or SD Card, power off your chromebook completely.

### Booting into Shimboot

Hold ESC + Refresh + Power on your chromebook until it boots into the recovery menu.
Your screen should look like this:

insert image

**WARNING: DURING THIS STAGE, THE CHROMEBOOK WILL MAKE A LOUD BEEP! I DO NOT RECOMMEND DOING THIS IN A QUIET CLASS.**

Next, press CTRL + D. When it asks you to confirm, press enter.
Immediately after that, the screen will go black. As soon as it does, start holding ESC + Refresh + Power again.
The chromebook should make a loud BEEP when it returns back to the first screen.
It will show a warning that says "Developer mode is not allowed". Press Enter to ignore the warning.
You can now plug in the USB or SD Card.
If you did everything correctly, you should see it blackscreen for a second, then go to a screen with white text.
Once it finishes loading, your screen should look something like this.

insert image

From here, you have two options:
1. Boot a spoofed unenrolled ChromeOS
2. Boot into Debian Linux running off the USB

I highly recommend choosing the first option.
With either option, you can go back to the enrolled ChromeOS at any time by simply restarting.

If you chose the second option, follow the guide [here](abc). This writeup will not cover it.

To boot into spoofed unenrolled ChromeOS, press these keys in order:

```
1, enter, 1, enter, y, enter, y, enter
```

It should take a couple seconds for it to boot. 
As soon as the ChromeOS logo appears, you can remove the USB.
Your screen should look something like this:

insertimage

This behaviour is expected. Press "Skip for Now" to continue.
**DO NOT CONNECT TO ANY WIFI NETWORKS NOW!** 
If you do, the chromebook may potentially update.
Click "Browse As Guest" on the left side of the screen, in the text.
Only after that, you should connect to wifi. 
If you are in FCPS I recommend using FCPSGuest.
However, there is a little more you have to do for websites to be unblocked on school wifi.

Open Settings, and search "dns".
Turn On Secure DNS



