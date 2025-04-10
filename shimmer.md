# Sh1mmer on FCPS Chromebooks
As of September 16th, sh1mmer with the tsunami bypass has been confirmed working with ChromeOS r128. 
This exploit allows for unenrollment and the ability to switch into developer mode, plus other things.

# Exploit Instructions

FCPS Chromebooks come in two models - HP Fortis G10 and G11. You can check this on the underside of the chromebook, which will usually be under the FCPS barcode (this varies from school to school).

## What you'll need
- Conductive Material: Staple, Tin Foil, etc. I highly recommend you to purchase a [chip clip](https://www.amazon.com/HiLetgo-Socket-Adapter-150MIL-205MIL/dp/B01HTC5FTM) ($7 avg).
- Scissors
- Tape (Recommended, but optional)
- 1GB or larger USB flash drive or SD card
- Relatively small phillips screwdriver
- Prying tool: Credit card, flathead screwdriver, etc.
- Another computer
- A functioning brain

### Getting ready for the exploit
Once you have checked the model of your chromebook, you need to download a couple files for the exploit.
#### G11 Chromebook:
  - Board: `nissa`
  - [Pre-Injected RMA shim](insert download link here later)
  - [Chromebook Recovery Utility (ignore if using linux)](https://chromewebstore.google.com/detail/chromebook-recovery-utili/pocpnlppkickgojjlmhdmidojbmbodfm)
#### G10 Chromebook:
  - Board: `dedede`
  - [Pre-Injected RMA shim](insert download link here later)
  - [Chromebook Recovery Utility (ignore if using linux)](https://chromewebstore.google.com/detail/chromebook-recovery-utili/pocpnlppkickgojjlmhdmidojbmbodfm)

Once you've downloaded the shims, open the chromebook recovery utility. If you're using linux, skip to the bottom of this section.
The utility will open in a new window. Press the settings gear in the top right, and click "Use Local Image", as indicated in the picture.

#### **WARNING: THIS <ins>WILL</ins> ERASE ALL DATA ON YOUR USB DRIVE <ins>PERMANENTLY</ins>!!**

![image](https://github.com/user-attachments/assets/93fd81e3-7cef-4d8d-9873-9459915ebde4)

It will then prompt you to select a file. Navigate to wherever you downloaded your shim to, and double click it (the file should be called either `dedede.bin` or `nissa.bin` depending on your model's board). 
After this, plug in your USB and select it from the list. Press Start in the utility. It should only take about a minute maximum, depending on your USB drive. 
If you're on linux, use the command `sudo dd if=name_of_shim.bin of=/dev/sdX` making sure to replace sdX with the actual id of your USB drive and `name_of_shim.bin` with `dedede.bin` or `nissa.bin`
Once it finishes, you can close out of it. Next, you'll need to remove the case of the chromebook. Pop off the bottom and slide up the top part of the case, and pop off the bottom half, as indicated in the picture.

![image](https://github.com/user-attachments/assets/a73c963a-3db3-4220-b4a0-578f836da0d6)

Once the case is off, unscrew the back cover as shown in the picture, and insert your pry tool into the spots marked with the blue arrows. Pry gently around the laptop.

**The back cover breaks VERY easily!! Please be careful.**

![image](https://github.com/user-attachments/assets/fa7f0900-d4ed-4397-a5dc-a037fa06aced)

Next, find the battery connector on the chromebook and disconnect it. 
After this, you need to find the BIOS chip on the chromebook, which I have marked in the picture along with the battery connector which will usually be covered with black tape.

![image](https://github.com/user-attachments/assets/7d9ec270-d334-4906-b1d3-4c905d11e91b)

To do the exploit properly, pins 3 and 8 on the chip need to be bridged. If you're using a chip clip, you can skip to the bottom of this section.
Place your conductive material on the pins and secure it firmly with the tape. I have outlined the path between the pins in red in this image.

![image](https://github.com/user-attachments/assets/ecb1ca3c-73df-4466-94e1-7cab3deb76cb)

If using a chip clip, clip it to the chip so the red wire matches the pin that has the indent next to it, then use a paperclip or safety pin to bridge the pins on the other side of the clip, like in this image.
The pins that need to be bridged (when holding it notch side up) are pin 3 (2 to the right of the top left pin) and pin 8 (bottom left pin)

![image](https://github.com/user-attachments/assets/1ce490e3-29f3-4fcb-997e-0ef23489d210)

Next, hold ESC + Refresh + Power on your chromebook to boot it into recovery mode. It should look like this: 

insert image later lolol

DO NOT INSERT YOUR USB DRIVE. Press CTRL + D on this screen, and hit confirm to turn on developer mode. Right after this, hold ESC + Refresh + Power again. Now, plug in your USB.
It will boot into the sh1mmer menu. This will take about 30 seconds.
Go to Utilities > Un-enroll device. This should error, but it's required for the exploit.
Next, go to Utilities > Bash Shell (navigate with arrow keys).
Your screen should look something like this:

insert image later lololol

Make sure the pins are bridged on the chip at this point, or push down hard on the paperclip/safety pin if using a chip clip.
Run these commands in the shell:
```bash
flashrom --wp-disable
/usr/share/vboot/set_gbb_flags.sh 0x8090
```
If the commands exit with success, conrgatulations!
If they error, the pins are not bridged correctly and you need to try again.

Reboot the chromebook and select "Boot from internal disk".
Your device will transition to developer mode for 5 minutes, then reboot.
**DO NOT CONTINUE WITH THE SETUP, AND DO NOT CONNECT TO WIFI!**
Switch to VT2 with CTRL + ALT + Refresh immediately.
Login as `root` and run these commands:
```bash
tpm_manager_client take_ownership
cryptohome --action=remove_firmware_management_parameters
```

The last command will error because my chromebook died lolol dw i'll finish this writeup once I get my charger back

## The rest of the process

**Completely usure if this section even works, proceed at your own risk**   ⠀  -Catfoolyou

Run one more command:
```
crossystem dev_boot_usb=1
```
Reconnect the battery to the motherboard, and run gsctool -a -o. Follow the prompts to push the power button and the system should automatically reboot. When the device turns back on, re-open the recovery menu and re-enable devmode.

Afterward, go to the VT2 console, run gsctool -a -I AllowUnverifiedRo:always, and the device should be unenrolled.

![image](https://github.com/user-attachments/assets/f24fbdf5-5e84-4ab3-90f7-e7a71e1f383a)


