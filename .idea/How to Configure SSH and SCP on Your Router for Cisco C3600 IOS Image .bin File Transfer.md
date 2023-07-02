
 
# How to Upgrade Cisco 3600 Series Router with .bin File
 
If you have a Cisco 3600 series router that needs a software upgrade, you might wonder how to use a .bin file to do so. A .bin file is a binary file that contains the Cisco IOS software image. Unlike some other Cisco devices, such as Catalyst switches, the 3600 series routers do not use .tar files or the archive command to upgrade their software. Instead, you need to use one of these methods:
 
1. Use another router to get a valid Cisco IOS software image into the PCMCIA card.
2. Download using Xmodem from ROMmon.
3. Download using tftpdnld ROMmon command (Cisco 3800 only).

In this article, we will explain each of these methods in detail and provide some tips and tricks to make the process easier.
 
**Download Zip ↔ [https://urllio.com/2uycMs](https://urllio.com/2uycMs)**


  
## Use Another Router to Get a Valid Cisco IOS Software Image into the PCMCIA Card
 
If you have a similar router, or at least one other router that has a compatible PCMCIA Flash card filesystem, you can use that Flash card to recover the router. Refer to [PCMCIA Filesystem Compatibility Matrix and Filesystem Information](https://www.cisco.com/c/en/us/support/docs/routers/3600-series-multiservice-platforms/15080-recovery-c3600.html#pcmcia) for more information. If both routers are identical, or same series, you can use the Flash card from the other router to boot the one you want to recover. 3600/3700/3800 series routers run their Cisco IOS software from dynamic RAM (DRAM), so you can remove a PCMCIA card while the router runs. If both routers are different but have a compatible PCMCIA Flash card filesystem, you can use the other router to load a Cisco IOS software image into a Flash card, which you can then move to the router you want to recover. From the router that works, copy the image into the PCMCIA card.
 
Here are the steps to follow:

- Insert an empty PCMCIA card into slot 0 of the working router.
- Copy the .bin file from your TFTP server or another source to the PCMCIA card using the `copy` command. For example: `copy tftp://10.10.10.10/c3600-adventerprisek9-mz.124-10.bin slot0:`
- Verify that the file is copied correctly using the `dir` and `verify` commands. For example: `dir slot0:` and `verify slot0:c3600-adventerprisek9-mz.124-10.bin`
- Eject the PCMCIA card from slot 0 of the working router.
- Insert the PCMCIA card into slot 0 of the router you want to recover.
- Boot from that image using the `boot` command from ROMmon mode. For example: `boot slot0:c3600-adventerprisek9-mz.124-10.bin`
- If the file is valid, this brings you back to normal operation mode.

## Download Using Xmodem from ROMmon
 
If you do not have another router or a compatible PCMCIA card, you can use Xmodem to download the .bin file from your PC or laptop to the router's Flash memory. This method is slow and requires a console connection and a terminal emulator software that supports Xmodem protocol, such as HyperTerminal or Tera Term.
 
Here are the steps to follow:
 
cisco c3600 ios image download,  cisco c3600 ios image for gns3,  cisco c3600 ios image free,  cisco c3600 ios image upgrade,  cisco c3600 ios image recovery,  cisco c3600 ios image checksum,  cisco c3600 ios image backup,  cisco c3600 ios image size,  cisco c3600 ios image features,  cisco c3600 ios image compatibility,  cisco c3600 ios image license,  cisco c3600 ios image archive,  cisco c3600 ios image decompress,  cisco c3600 ios image boot,  cisco c3600 ios image configuration,  cisco c3600 ios image verification,  cisco c3600 ios image encryption,  cisco c3600 ios image password,  cisco c3600 ios image error,  cisco c3600 ios image troubleshooting,  cisco c3600 ios image guide,  cisco c3600 ios image manual,  cisco c3600 ios image tutorial,  cisco c3600 ios image documentation,  cisco c3600 ios image support,  how to install cisco c3600 ios image,  how to copy cisco c3600 ios image to flash,  how to delete cisco c3600 ios image from flash,  how to extract .bin file from .tar file for Cisco C3600 IOS Image ,  how to use tftp server to transfer Cisco C3600 IOS Image ,  how to use xmodem to transfer Cisco C3600 IOS Image ,  how to use rommon mode to load Cisco C3600 IOS Image ,  how to use usb flash drive to load Cisco C3600 IOS Image ,  how to use ftp server to transfer Cisco C3600 IOS Image ,  how to use scp server to transfer Cisco C3600 IOS Image ,  how to use rcp server to transfer Cisco C3600 IOS Image ,  how to use sftp server to transfer Cisco C3600 IOS Image ,  how to use http server to transfer Cisco C3600 IOS Image ,  how to use snmp server to transfer Cisco C3600 IOS Image ,  how to use netconf server to transfer Cisco C3600 IOS Image ,  how to use telnet server to transfer Cisco C3600 IOS Image ,  how to use ssh server to transfer Cisco C3600 IOS Image ,  how to use console port to transfer Cisco C3600 IOS Image ,  how to use auxiliary port to transfer Cisco C3600 IOS Image ,  how to use ethernet port to transfer Cisco C3600 IOS Image ,  how to use serial port to transfer Cisco C3600 IOS Image ,  how to use isdn port to transfer Cisco C3600 IOS Image ,  how to use atm port to transfer Cisco C3600 IOS Image ,  how to use frame relay port to transfer Cisco C3600 IOS Image

- Erase the Flash memory of the router using the `erase flash:` command from ROMmon mode.
- Set the console speed to 115200 bps using the `confreg` command from ROMmon mode. For example: `confreg 0x2102`
- Reset the router 8cf37b1e13


