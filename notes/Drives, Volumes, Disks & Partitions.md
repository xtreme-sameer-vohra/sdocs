**Drives, Volumes, Disks & Partitions**


**Drive** 
Physical storage device such as a hard disk, solid-state disk, removable USB flash drive etc. In Unix-like operating systems devices are represented by special file system objects called device nodes which are visible under the  `/dev directory`

**Partions**
A physical storage device can be divided into multiple logical storage units known as partitions. 

**Volume**
The term volume in Linux is related to the Logical Volume Manager (LVM), which can be used to manage mass storage devices. A physical volume is a storage device or partition. A logical volume created by the LVM is a logical storage device which can span multiple physical volumes.

*Volume* implies formatting while a *partition* does not



On Linux
	/dev/sda1

	`sd` SCSI device
	`a`	 First drive detected by the OS
	`1`	 First partition 

**Mount**
Mount provides the filesystem on some device to be accessible at some path on a unix system. It places the root of the filesytem of the device at the specified path

`mount -t type device dir`

here,

* `type` is the device's type
* `dir` is the path to make the files available at

`findmnt` can be used to list all the mounts

**References**
https://unix.stackexchange.com/questions/87300/differences-between-volume-partition-and-drive

http://man7.org/linux/man-pages/man8/mount.8.html
