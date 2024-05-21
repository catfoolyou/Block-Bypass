# FCPSOff Chromebook Testing
List of working exploits for the FCPS school chromebooks. (pr 25-26)

## Disable Updates (IMPORTANT)
In order to ensure that these exploits KEEP WORKING and are not patched by FCPS we must employ some methods to prevent security patches and group policy changes from being applied. 

  1. Go to chrome://flags#show-metered-toggle or search "metered" in chrome://flags instead.
  2. Enable it and restart your device.
  3. Open the Settings app.
  4. Go to your Network >> Advanced >> Show metered toggle and turn it on

## Enable Devmode (ALSO IMPORTANT)
Some exploits like the policy editor one require chrome devmode, here is how you can enable it in a couple simple steps:

  1. Press and hold Esc+Refresh+Power simultaneously.
  2. Press Ctrl+D when asked to insert recovery media.
  3. Press Enter on “To turn OS verification OFF, press ENTER.”
  4. Press Ctrl+D when it states that the OS verification is off.
  5. Wait for the system transitioning into Developer Mode and it'll boot up on its own.
  6. Press Ctrl+D (or wait for an audible beep) instead of space bar when it says “OS verification is OFF. Press SPACE to re-enable.”, otherwise you'd have          to start all over again.

## DNS Misconfig [patch in progress]
Changing the Domain Name System (DNS) settings on your School Chromebook can currently bypass some restrictions on the browser. 
<br>
1. Click on the system tray at the bottom-right corner of your Chromebook’s screen.
2. Select “Settings” to open the menu.
3. Scroll down and click on “Wi-Fi” or “Internet connection.”
4. Find your active Wi-Fi connection and click on the network name.
5. In the pop-up window, click on the “Network” tab.
6. Under the “Name servers” section, click on “Custom name servers.”
7. Enter the preferred DNS server addresses. You can use public DNS servers like Google DNS (8.8.8.8, 8.8.4.4), Cloudflare (1.1.1.1, 1.0.0.1), or OpenDNS (208.67.222.222, 208.67.220.220).
8. Click on “Save” to apply the changes to your School Chromebook’s DNS settings.

## Disable Extensions [patch in progress]
Find a page linking to the extension you want to disable like `chrome://extensions` or `chrome://extensions-internals` and `chrome://process-internals`. Next you need to find  the extension's ID which is a 32-character lowercase string. You can also do a Google search. Once you have your ID, replace the hostname with it in the chrome page below:
<br>
```
chrome-extension://extensionidhereblahblah/manifest.json
```
Now bookmark the extension page (A). Then, bookmark `chrome://kill` (B) and `chrome://hang` (C).
On the extension page (A), click the `chrome://kill` bookmark (B). The page should crash. You should already prepare for the next step.
Now start spamming `chrome://hang` (C) and reload the page while spamming (with ctrl+R).
If the extension page (A) no longer loads, then it worked! You can close your tabs, and the extension will be dead. Restart your chromebook to put it back to normal.

## Policy Editor [needs dev mode]
Disabling RootFS **will** Soft-Brick your Chromebook when booting back into normal mode.

1. Open Crosh (Ctrl+Alt+T)
2. Run the following commands:
```sh
shell
sudo su
curl -Ls https://github.com/FCPSOff/Chromebook-Testing/blob/main/policy.sh) | bash
```
3. Reboot
4. Go Through Steps 1-3 Again
5. Run the following command:
```sh
curl -Ls https://github.com/FCPSOff/Chromebook-Testing/blob/main/policy.sh | bash
```



