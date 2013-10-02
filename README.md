centos-image-resize
===================

Tool for resizing virtual machines during boot. I've made this tool for use 
with Openstack.

DEPENDS:
Depends on growpart tool https://launchpad.net/cloud-utils.
Add EPEL repo and install cloud-utils, or do it manually
For Openstack, I also recommend you to install cloud-init
Partitioning: A single partition on the disk (/boot can not be seperate). LVM not supported.

SETUP:
Run ./centos-image-mod.sh, it will modify initrd image and grub menu. 

It will install itself to /usr/libexec/centos-image-mod directory, since 
you need to run this after every kernel upgrade (if you wish to resize 
partition again).

it modifies:
- initrd
- grub.conf
 - elevator mode (noop by default)
 - redirects boot log from STDOUT to /dev/ttyS0
