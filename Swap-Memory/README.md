# Increasing performance of linux system by changing swappiness index
Decreasing swappiness index to increase performance of system.Swappiness index tells about how frequently the pages must be swapped out to the harddisk. Swappiness is directly propotional to the swapping of pages.

Procedure:

1. Open the /etc/sysctl.conf file in root mode.

2. Add the following lines to it:

	# swappiness value decreased to 10 to increase performance

	vm.swappiness = 10

3. Reboot the System.


How to check the current swappiness of system:

	cat /proc/sys/vm/swappiness  


Sometimes the system uses swap area even if memory space is available. To empty swap area at that time:

1. Disable swapping. 

	sudo swapoff -av

2. Re Enable swapping.

	sudo swapon -av