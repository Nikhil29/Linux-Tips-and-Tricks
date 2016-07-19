# Mint-brightness-issue-solved
The brightness increase/decrease was not working.

Steps:

1. In terminal, execute command:

        sudo gedit /etc/default/grub

2. Locate this line GRUB_CMDLINE_LINUX_DEFAULT="quiet splash" or something like that. 

3. Change it to something like this:

        GRUB_CMDLINE_LINUX_DEFAULT="quiet splash acpi_osi=Linux acpi_backlight=vendor"

4. In terminal, execute command:

        sudo update-grub

5. Reboot and see if now it works.
