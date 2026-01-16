
# Kernel Parameters

## Linux Boot Options

| kernel Option | Description |
| --- | --- |
| allowcddma | Enables DMA for CD/DVD drive |
| apic | Works around a bug commonly encoutnered in the Intel 440GX Chipset BIOS and executes only with the installation program kernel |
| acpi=off | Disables ACPI in case problems with it occur |
| dd | Prompts for a driver disk during the installation of Red Hat Linux |
| display=IP\_address:0 | Causes the installer GUI to appear on the remote system identified by the ip address (Make sure that you run the command xhost +hostname on the remote system, where hostname is the hsot where you run the installer) |
| driverdisk | Prompts for a driver diskk during installaton of Red Hat Linux |
| enforcing=0 | Turns off Security Enhanced Linux (SELinux) mandatory access control |
| expert | Enables you to parition removable media and prompts for a driver disk |
| ide=nodma | Disables DMA on all IDE devices and can be useful when you're having IDE related problems |
| ks | Configures the Ethernet card using DHCP and runs a kickstart installation by using a kickstart file from an NFS server identified by the boot server parameters provided by the DHCP server |
| ks=kickstartfile | Runs a kickstart installation by using the kickstart fie, specified by kickstartfile (The idea behind kicstart is to create a text file with all the installation options and then kickstart the installationb y booting and providing the kickstart file as input) |
| lowres | Forces the installer GUI to run at a lower resolution (640 x480) |
| mediacheck | Prompts you to check the intergity of teh CD image (also called the ISO image) The image is checked by computing the MD5 checksum and comparing that with the official Fedora value. Checking a CD-ROM can take a few minutes |
| mem=xxxM | Overrides the amount of memory that the kernel detects on the PC. (Some older machiens could detect onl 16MB of memory, and on some new machines, the video card may use a portion of the main memory.) Make sure to replace xxx with the number representing the megabytes of memory on your pc |
| nmi\_watchdog=1 | Enables the built-in kernel deadlock detector that makes use of Non-Maskable Interrupt (NMI) |
| noapic | Prevents the kernel from using the Advanced Programmable Interrupt Controller (APIC) chip. (You can use this command on motherboards known to have ea bad APIC) |
| nofirewire | Doesn't load support for Firewire |
| noht | Disables hyperthreading, which is a feature that enables a single processor to act as multiple virtual processors at the hardware level |
| nomce | Disables self-diagnosis checks performed on the CPU by using Machine Check Exception (MCE). On some machines, these checks are performed too often and need to be disabled |
| nomount | Doesn't automatically moount any installed Linux partitions in rescue mode |
| nopass | Doesn't pass the keyboard and mouse information to stage 2 of the installation program. |
| nopcmcia | Ignores any PCMCIA controllers in the system |
| noprobe | Disables automatic hardware detection, and prompts the user for information about SCSI and network hardware installed on the PC. You can pass parameters to modules by using the approach |
| noshell | Disables shell access on virtual console 2 (the one you get by pressing CTRL+ALT+F2) during installation |
| nousb | Disables the loading of USB support during the installation (Booting without USB support may be useful if the installation program hands early in the process) |
| nousbstorage | Disables the loading fo teh usbstorage module in the installation prgorma's loader. This option may help with device ordering on SCSI systems. |
| reboot=b | Changes the way that the kernel tries to reboot the PC so that it can reboot even if the kernel hands during system shutdown |
| pci=noacpi | Causes the kernel to not use ACPI to route interrupt requests |
| pci=biosirq | Causes he kernel to use BIOS settings to route interrupt requests (IRQs) |
| rescue | Starts the kernel in rescue mode, where you get a shell prompt and try to fix problems |
| resolution=HHHxVVV | Causes the installer GUI to run in the specified video mode (where HHH and VVV are standard resolution numbers, such as 640x480,800x600, or 1024x768) |
| selinux=0 | Disables the SELinux kernel extensions |
| serial | Turns on serial console support during installation |
| skipddc | Skips the Display Data Channel (DDC) probe of monitors. (This option is useful if probing causes problems) |
| vnc | Starts a VNC (Virtual Network Computing) server so that you can control the GU installer from another networked system that runs a VNC client |

## Kernel Module Commands

| Command | Description |
| --- | --- |
| insmod | Inserts a module into ther kernel |
| rmmod | Removes a module from the kernel |
| depmod | Deteremines interdependencies among modules |
| ksyms | Displays a list of symbols along with the name of the module that defines the symbol |
| lsmod | Lists all currently loaded modules |
| modinfo | Displays information about a kernel module |
| modprobe | Inserts or removes a module or a set of modules intelligently (If module A requires B, for example, modprobe automatically loads B when asked to load A) |