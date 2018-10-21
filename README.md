# Xilinux
Linux Operating System built for ZedBoard

Official Website: http://xillybus.com/xillinux

Linux Image (~1.1GB): http://xillybus.com/downloads/xillinux-2.0.img.gz

Some extra files: http://xillybus.com/downloads/xillinux-eval-zedboard-2.0c.zip

Manual: http://xillybus.com/downloads/doc/xillybus_getting_started_zynq.pdf

The manual shows how to put our design in this Linux. 

# How to setup linux for Zedboard
To burn Linux Image file into SD card (not recommend do in Linux, somehow after burning, Linux does NOT recognize SD's Linux partition's file system): (Following commands can be performed in Terminal in Mac OS X. Assume the file is downloaded into the folder "Downloads")

```cd ~/Downloads/```

```gunzip xillinux-2.0.img.gz```

You need to check the mounting point of SD card

```diskutil list```

```unmount /Volumes/(SD card's Name)```

```sudo dd if=xillinux-2.0.img of=/dev/(mounting point, it looks like disk#) bs=512```

It may need 1 hour and 15 seconds to finish burning. I forgot to try put "r" in front of disk#, as ```of=/dev/rdisk#```. It may speed up the process.

After burning, you can only be able to see one SD card's partition in Mac OS X, capacity ~15 MB, with file "uImage" in there. 

Then we need the bitstream file, xillydemo.bit, can be found in this repo, /vivado/xillydemo.runs/impl_1/
We also need boot.bin and devicetree.dtb files can be found in the folder "bootfiles" from the zip in "Some extra files: " 

Put xillydemo.bit, boot.bin, devicetree.dtb files in the partition where "uImage" is. Then insert the SD card back to Zedboard, and you should be good to go. 
