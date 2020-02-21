## Helpful Linux shell commands

### Change the group & permissions of *FILE*

- Change  the  group of each *FILE* to *GROUP* (-R: operate on files and directories recursively)  
`$ sudo chgrp -R julio foo/`

- Change the mode of each *FILE* to *MODE*  
`$ sudo chmod -R g+w foo/`

### Create a bootable USB drive

- Determine where the USB drive is mounted  
`$ lsblk`

- Copy ISO to USB drive  
`$ sudo dd if=path/to/input.iso of=/dev/sd<?> bs=4M conv=fdatasync  status=progress`