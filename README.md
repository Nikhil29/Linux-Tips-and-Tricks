### Linux-Tips-and-Tricks
It contains solutions to some common problems faced by Linux mint users.

#### <ins>Mint Brightness Issue</ins>
The brightness increase/decrease is not working.
##### Solution: 
- In terminal, execute command:
````
    sudo gedit /etc/default/grub
````
- Locate the below line
````
    GRUB_CMDLINE_LINUX_DEFAULT="quiet splash" or something like that. 
````
- Change it to something like this:
````
    GRUB_CMDLINE_LINUX_DEFAULT="quiet splash acpi_osi=Linux acpi_backlight=vendor"
````
- In terminal, execute command:
````
    sudo update-grub
````
- Reboot and see if now it works.

#### <ins>Performance issue due to low memory</ins>
If there are performance issues due to low memory.
##### Solution:
You can increase the performance of the system by changing swapiness index.
Swappiness index tells about how frequently the pages must be swapped out to the swap space(harddisk).
Swappiness is directly propotional to the swapping of pages.
Decreasing swappiness index allows to increase performance of system.

- Open the /etc/sysctl.conf file in root mode.
- Add the following lines to it:
````
    vm.swappiness = 10
````
- Reboot the System.
##### How to check the current swappiness of system:
````
    cat /proc/sys/vm/swappiness 
````
##### Sometimes the system uses swap area even if memory space is available. To empty swap area at that time: 
- Disable swapping:
````
    sudo swapoff -av
````
- Re Enable swapping:
````
    sudo swapon -av
````

#### <ins>Night Light Filter</ins>
To enable night light filter in linux.
##### Solution
- Install redshift by using below command
````
    sudo apt-get install redshift redshift-gtk
````
- Now you can set a temp of the screen which changes the screen color. You can play around by setting one time temp of screen by using below command. Note that the default temp of screen is 6500K. Below we are setting a temp of 4000K
````
    redshift -O 4000
````
- To reset to neutral:
````
    redshift -x
````
- Now to permanently set both day time and night time temperatures, use below syntax:
````
    redshift -t DAY:NIGHT
````
Eg:
````
    redshift -t 6500:5000
````
- To explore more about redshift, use below command for help:
````
    redshift -h
````
