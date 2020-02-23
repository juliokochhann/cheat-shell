# Cheat Shell

This is a cheat sheet of must-have linux commands.

## Create bootable USB drive

1. Determine where the USB drive is mounted  
`$ lsblk`

2. Copy the disk image to the USB drive  
`$ sudo dd if=path/to/input.iso of=/dev/sd<?> bs=4M conv=fdatasync  status=progress`
> Replace <?> with the letter corresponding to the USB drive found on the previous step

____________________________________________________________________________________________________

## Fonts

### Install new fonts manually
1. Download the font file(s) ([from here](https://fonts.google.com/) for example)

2. Copy the downloaded file(s) or folder(s) to `/home/user_name/.fonts`

3. If the `.fonts` folder doesn't exist you can create it  
`$ mkdir .fonts`

4. Update font information cache files  
`$ sudo fc-cache -f -v`

____________________________________________________________________________________________________

## Linux file permissions

### Change the user and/or group ownership of each given file  
- Change the owner of `/foo` to "root"  
`$ sudo chown root /foo`

- Likewise, but also change its group to "staff"  
`$ sudo chown root:staff /foo`

- Change the owner of `bar/` and subfiles to "root"  
`$ sudo chown -hR root bar/`
> In this example *bar/* is a directory (-R = --recursive). But remember, in Linux everything is a FILE!

### Change file mode bits

- Give the user who owns the file write access  
`$ sudo chmod u+w foo.bar`
> A  combination  of the letters **ugoa** controls which users' access to the file will be changed
>
> The  letters  **rwxXst** select file mode bits for the affected users

____________________________________________________________________________________________________

## Tarballs

- Extract/Uncompress tarball to specific directory  
`$ tar -xvf file.tar.gz -C path/to/directory/`
> GNU tar recognizes the compression method (gzip, bzip2, xz ...) by the file extension (tar.gz, tar.bz2, tar.xz ...)