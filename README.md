# My guide for fixing Dell XPS 15 9570 Sound Issues (probably will work for simillar laptops)

# Introduction

I bought my Dell XPS 15 mainy because I need powerfull machine for work.  
During my initial days of usage I decided to install fresh Windows 10 and install only essential Dell software and drivers and try to optimize it a bit, so I can get a best experience.  
What I have noticed is clacking sound when playing sound from any source (Youtube, Spotify, files etc.) on any output (internal/external speakers, headphones).  
This issue seemd to be almost impossible to fix, until I've found [Kevin Shroff's Modded Realtek Audio Drivers (KSMRD)](https://github.com/kevinshroff/KSMRD-Modded-Realtek-Audio-Drivers/blob/master/README.md) which seemd to fix most of cracking noise, including 100% time during cinebench load (this was nasty) and most during my normal use.  

Additional steps I propose should fix +99% of cracking noise with small (additional) effort over KSMRD.

## Requirements
* Dell XPS 15 (tested on 9570, but probably will work for older models)
* Windows 10 x64 (I'm using latest 17143 build)
* Patience
* Backup (in case you mess up something)

## Steps
1. If your Windows 10 is bloated or you are using stock Dell's Windows installation. Just make bootable Windows 10 (I recommend latest avaliable build iso, there are plenty guides online) usb drive (I recommend (rufus)[http://rufus.akeo.ie/]), after getting drivers for wifi and RAID (or just switch do AHCI mode like I did) to be safe and make clean install.
2. Carefully perform steps mentioned in [Kevin Shroff's awesome guide](https://github.com/kevinshroff/KSMRD-Modded-Realtek-Audio-Drivers/releases). I've used 3.0.2 version of his modified drivers.
3. Make sure (again) you disabled Waves MaxxAudio Service Application and Realtek HD Audio Universal Service in startup tap of Task Manager.
4. Stop and Turn of Waves Audio Serices (fixes audio watching Youtube clips) and Realtek Audio Universal Service (fixes audio during Cinebench benchmarking and other loads) in Windows Services Manager.
5. Check if after reboot any key you were to look for (and change to) has reverted to default value and if so replace it with ff ff ff ff instead of ff ff ff. [Info](http://www.surfacetablethelp.com/2017/11/fix-sound-popping-issues-in-windows-10-fall-creators-update.html).  
   On my laptop it was: HKEY_LOCAL_MACHINE\SYSTEM\CurrentControlSet\Control\Class\{4d36e96c-e325-11ce-bfc1-08002be10318}\0012\PowerSettings
6. Reboot.
7. Test if issue is fixed.

## Big thanks to
* [Kevin Shroff](https://github.com/kevinshroff) for drivers and guide
* [Reddit](https://www.reddit.com/r/dell) for great Dell/XPS community

## Disclaimer
 Those tools are provided as is and you are using them at your own risk. I am not responsible for any damage or lost data.