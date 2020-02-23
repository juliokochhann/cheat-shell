# Cheat Shell

This is a cheat sheet of must-have linux commands.

## Create bootable USB drive

+ Determine where the USB drive is mounted:
: `$ lsblk`

+ Copy the disk image to the USB drive:
: `$ sudo dd if=/path/to/input.iso of=/dev/sd<?> bs=4M conv=fdatasync  status=progress`
> Replace <?> with the letter corresponding to the USB drive found on the previous step

## Extract tarballs

+ Extract/Uncompress the tarball to a specific directory:
+ `$ tar -xvf file.tar.gz -C /path/to/directory`
> GNU tar recognizes the compression method (gzip, bzip2, xz ...) by the file extension (tar.gz, tar.bz2, tar.xz ...)

## Linux file permissions:

+ Change a file's group:
: `$ sudo chgrp -R group foo/`
> In this example *foo/* is a directory (-R = --recursive). But remember, in Linux everything is a FILE!

+ Control users access to a file:
: `$ sudo chmod u+w foo.bar`