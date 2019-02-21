## How to install linux mint on a computer with a 1050ti (or maybe similar) nvidia graphics card

* Flash favorite mint to a usb with 
    * Windows: balenaEtcher
    * Linux: Usb Image Writer
* Go through install, reboot may not work may need to be forced
* After first install, boot with legacy boot mode (not uefi)
    * Unless you have a window bootload intermediary...
* Edit the boot command. Nvidia box drivers DON'T WORK and you'll end up with a black screen, so disable GPU drivers
    * Find and replace "silent splash" with "nomodeset" and control-x to run that custom commands
* System boots, woop woop. Get a terminal
> sudo apt-get remove --purge nvidia-*
> sudo apt-get upgrade
> sudo apt-get update
> sudo shudown -r now

* Get to the bootloader config again, edit the commands to nomodeset again, boot again
* Search for "driver manager", launch it
* GPU should be on some nouveau open source stuff... Select the "nvidia driver", apply, wait, reboot
* Should be good??? If not, run
> sudo add-apt-repository ppa:graphics-drivers
 - or maybe
> sudo ubuntu-drivers autoinstall
* But then definitely select nvidia driver and apply from the driver manager program... That's for sure the last step
