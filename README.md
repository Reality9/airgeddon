#airgeddon
This is a multi-use bash script for Linux systems to audit wireless networks.<br/>
![We'll conquer the earth!!][1]

#Features
- Interface mode switcher (Monitor-Managed) keeping selection even on interface name changing.<br/>
- DoS over wireless networks using different methods.<br/>
- Assisted Handshake file capturing.<br/>
- Cleaning and optimizing Handshake captured files.<br/>
- Offline password decrypting on WPA/WPA2 captured files (dictionary, bruteforce and rule based).<br/>
- 4 Evil Twin attacks: Evil Twin with integrated sniffing, sslstrip mode, "only AP" version to sniff using external sniffer and "black hole" captive portal to capture wifi passwords.<br/>
- WPS features: WPS scanning (wash). WPS Custom pin association. WPS Pixie Dust attacks integrated using reaver and bully. WPS bruteforce PIN attacks.<br/>
- Compatibility with many Linux distros (see requirements section).<br/>
- Easy targeting and selection in every section.<br/>
- Drag and drop files on console window for entering file paths.<br/>
- Dynamic screen resolution detection and windows auto-sizing for optimal viewing.<br/>
- Controlled Exit. Cleaning tasks and temp files. Option to keep monitor mode if desired.<br/>
- Multilanguage support and autodetect OS language feature (see supported languages section).<br/>
- Help hints in every zone/menu for easy use.<br/>
- Auto-update. Script checks for newer version if possible.

#Coming soon
- WPS PIN Database search for "easy AP" known PINs and integration of most common PIN generation algorithms

#Requirements
Bash version 4.0 or later needed.<br/>
<br/>
Tested on these compatible Linux distros:<br/>
*-Kali 2.0, 2016.1, 2016.2 and arm versions (Raspberry Pi)*<br/>
*-Wifislax 4.11.1 and 4.12*<br/>
*-Backbox 4.5.1 and 4.6*<br/>
*-Parrot 2.2.1, 3.1.1 and arm versions (Raspberry Pi)*<br/>
*-Blackarch 2016.01.10 and 2016.04.28*<br/>
*-Cyborg Hawk 1.1*<br/>
*-Debian 7 (Wheezy) and 8 (Jessie)*<br/>
*-Ubuntu/Xubuntu 15.10, 16.04 and 16.04.1*<br/>
*-OpenSUSE Leap 42.1*<br/>
*-CentOS 6 and 7*<br/>
*-Gentoo 20160514 and 20160704*<br/>
*-Fedora 24*<br/>
*-Red Hat 7 (Maipo)*<br/>
*-Arch 4.6.2-1, 4.7.5-1, 4.8.4-1 and 4.8.6-1*<br/>
*-Raspbian 7 (Wheezy) and 8 (Jessie) (Raspberry Pi)*<br/>
*-OpenMandriva LX3*<br/>
<br/>
It's already available in <a href="https://archstrike.org/wiki">ArchStrike</a> repositories used by some distros based on Arch Linux.<br/>
Repositories versions will have auto-update feature disabled in order to avoid breaking dependencies. There is a var at the beginning of the file, *"auto_update"* can be set to 0 to turn off the auto-update feature.<br/>
<br/>
Anyway, can be used with any Linux distro if you have installed the tools what script needs. The script checks for them at the beginning.<br/>
<br/>
We will enumerate the categories and tools. The format will be: "command -> possible package name". The command can be included in different packages depending of the distro.<br/>
<br/>
Essential tools: <- *the script doesn't work if you don't have installed all of them*
```
iwconfig -> wireless-tools
iw -> iw
awk -> awk / gawk
airmon-ng -> aircrack-ng
airodump-ng -> aircrack-ng
aircrack-ng -> aircrack-ng
xterm -> xterm
```
Optional tools: <- *not necessary to work, only needed for some features*
```
wpaclean -> aircrack-ng
crunch -> crunch
aireplay-ng -> aircrack-ng
mdk3 -> mdk3
hashcat -> hashcat
hostapd -> hostapd
dhcpd -> isc-dhcp-server / dhcp-server / dhcp
iptables -> iptables
ettercap -> ettercap / ettercap-text-only / ettercap-graphical
etterlog -> ettercap / ettercap-text-only / ettercap-graphical
sslstrip -> sslstrip
lighttpd -> lighttpd
dnsspoof -> dsniff
wash -> reaver
reaver -> reaver
bully -> bully
```
Update tools: <- *not necessary to work, only used for auto-update*<br/>
```
curl -> curl
```
Internal tools: <- *these are internally checked. Not necessary to work, good to have*<br/>
```
xdpyinfo -> x11-utils / xdpyinfo / xorg-xdpyinfo
ethtool -> ethtool
lspci -> pciutils
rfkill -> rfkill
```
Is highly recommended to have the internal tools installed. They improve functionality and performance. For example, xdpyinfo allow the script to detect the desktop resolution in order to print windows in a better way.

#Known incompatibilities
Impossible compatibility for Mac OSX at the moment. Some reasons:<br/>
*-Bash version* <- it can be avoided upgrading to 4 or later, this is not the real problem :smile:<br/>
*-Aircrack suite* <- this suite for OSX doesn't support airodump and aireplay<br/>
*-Wireless tools* <- iwconfig doesn't exists for OSX, and airport command can't be used. It generates very different outputs<br/>

Incompatible with OpenBSD and FreeBSD. They are Unix systems but they have some differences with Linux:<br/>
*-Bash* <- They have no bash. It can be installed, this is not the real problem again :sweat_smile:<br/>
*-Wireless tools* <- iwconfig doesn't exists for these systems, they use ifconfig instead and it generates very different outputs

#Disclaimer
This script must be used only for educational purposes and Pen testing.<br/>
Use it only on your own networks.<br/>
We are not responsible of its use.<br/>
This script is under GPLv3 (or later) License.

#Use
Must be launched only using bash (not sh). Example `bash /path/airgeddon.sh`<br/>
If you launch the script using sh and a *"Syntax error"* appears, launch it with bash instead of sh.<br/>

#Supported Languages
English, Spanish, French, Catalan, Portuguese, Russian and Greek.

#Project Collaboration
You can join the project:<br/>
-Translations to other languages are welcome.<br/>
-More distros support compatibility.<br/>
-New features.<br/>
-Testing and feedback is needed too.<br/>
<br/>
*For collaborating translators:*<br/>
You can take the strings to translate from the code or you can ask me directly by mail. I'll inform you how to proceed or to add you as a collaborator on github.<br/>
<br/>
*For collaborating developers:*<br/>
Debug mode was implemented for faster development skipping intro and initial checks. Use it setting var *"debug_mode"* to 1<br/>
Please, respect the tab indentation, code style and the UTF-8 files format only using at the end of the lines LF (not CRLF).<br/>
Airgeddon code is 100% clean of warnings. Use <a href="https://github.com/koalaman/shellcheck">shellcheck</a> to search for errors and warnings on code. <- Thanks xtonousou for the tip :wink:<br/>
<br/>
*For beta testers:*<br/>
You can download the master version or the beta testing version from the development branch called `dev`

#Changelog
See [Changelog](changelog.txt) file to review changes.

#Special Thanks to
Thanks to the "Spanish pentesting crew", the <a href="http://www.wifislax.com/">Wifislax</a> staff, the <a href="http://foro.seguridadwireless.net">Seguridadwireless.net</a>, <a href="https://www.wifi-libre.com">Wifi-libre.com</a> and <a href="http://lampiweb.com/foro/">Lampiweb.com</a> forum people that helped me.<br/>
Thanks to the <a href="https://hackware.ru">Hackware.ru</a> admins.<br/>
<br/>
**Kcdtv** for French translations, beta testing, suggestions about new features and support received since the beginning.<br/>
**USUARIONUEVO** for helping me to improve the script, suggestions about new features and for the support received.<br/>
**El padrino** for Catalan translations.<br/>
**Luan** for Portuguese translations.<br/>
**MiAl** for Russian translations.<br/>
**xtonousou** for Greek translations, beta testing, suggestions and the help received fixing code warnings and other stuff.<br/>
<br/>
Thank you too to other authors who inspired me with their scripts:<br/>
*vk496 -> Linset*<br/>
*MI1 -> Airstorm*<br/>
*MatToufoutu -> Ap-fucker*<br/>
*Coeman76 -> Handshaker*

#Donate
If you enjoyed the script, feel free to give a donation. Invite me to a coffee through Paypal or send me a fraction of a bitcoin:<br/>
Paypal: *v1s1t0r.1s.h3r3&#64;gmail.com*<br/>
Bitcoin: *1AKnTXbomtwUzrm81FRzi5acSSXxGteGTH*<br/>
<br/>
[![paypal][2]](https://www.paypal.com/cgi-bin/webscr?cmd=_s-xclick&hosted_button_id=7ELM486P7XKKG)
&nbsp;
[![bitcoin][3]](https://blockchain.info/address/1AKnTXbomtwUzrm81FRzi5acSSXxGteGTH)

[1]: /imgs/airgeddon_banner.png "We'll conquer the earth!!"
[2]: /imgs/paypal_donate.png "Show me the money!"
[3]: /imgs/bitcoin_donate.png "Show me the money!"
