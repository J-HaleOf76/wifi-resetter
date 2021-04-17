@@ WIFI-RESETTER
Iwlwifi wlan (Wi-fi) adapter solution as tested in Intel Centrino 6205 
THIS IS NOT A PERMANENT SOLUTION

iwlwifi driver in linux seems to have a bug towards unable to establish device connection on wireless Networks
This is just a temporary fix though, haven't receive any updates from the driver creator

How to use:

1. Check first your wireless adapter  by using  `lspci` command for linux
   You will be provided with a list of drivers but not their indexes/numbers :
   It will show like this:

    ` 01:00.1 Audio device: Advanced Micro Devices, Inc. [AMD/ATI] Turks HDMI Audio [Radeon HD 6500/6600 / 6700M Series]
     `24:00.0 FireWire (IEEE 1394): JMicron Technology Corp. IEEE 1394 Host Controller (rev 30)
     `24:00.1 System peripheral: JMicron Technology Corp. SD/MMC Host Controller (rev 30)
     `24:00.2 SD Host controller: JMicron Technology Corp. Standard SD Host Controller (rev 30)`
     `25:00.0 Network controller: Intel Corporation Centrino Advanced-N 6205 [Taylor Peak] (rev 34)`
 
      My adapter shows as `25:00.0` so I need to find the correct indicator for the driver.
      
      Type command `cd /sys/bus/pci/devices` and you will be provided by a list of numbers
      `0000:00:1d.0  0000:00:1f.2  0000:01:00.1  0000:24:00.1  0000:25:00.0`
  
2. Find and copy the filename that corresponds to the pci device number
   For example : `25:00.0 Network controller` , it will be `0000:25:00.0`
   Open and edit the file before executing
   
3. Make executable by `chmod +x wifi-resetter`
 
4. Run as `sudo ./wifi-resetter` on your terminal

I highly recommend to push the file onto your system so that everytime you wifi goes down and unable to connect, you can just run it at any point on the terminal.
Advised to maintain good proximity with the Router that you are trying to connect as the wifi ranged highly affects my device to experience such weird issues. 

THIS IS NOT A PERMANENT SOLUTION



