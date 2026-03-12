# Linux-Mint-Nvidia-GPU-Fix-Tutorial
Linux mint config with two built in GPU's specifically 1 misc and 1 NVIDIA.  A way to toggle each GPU to reduce heat and save battery life. 
----------------------------------------------------------------------------------------------------------------------

If you are reading this guide, you are in the same boat as I was with my Victus by HP Gaming Laptop and a fresh installation of linux mint. My cpu would over-heat and my battery would drain from constant power-draw from the NVIDIA gpu being used when it wasn't needed. This is a solution I've come up with to solve my issues

----------------------------------------------------------------------------------------------------------------------
# PC Specs
- **OS:** Linux Mint 22.3 x86_64
- **Host:** Victus by HP Gaming Laptop 16
- **Kernel:** 6.14.0-37-generic
- **Uptime:** 2 hours, 14 mins
- **Packages:** 1960 (dpkg)
- **Shell:** bash 5.2.21
- **Resolution:** 1920x1080
- **DE:** Cinnamon 6.6.4
- **WM:** Mutter (Muffin)
- **WM Theme:** Mint-Y-Dark-Aqua (Mint-Y)
- **Theme:** Mint-Y-Dark-Aqua [GTK2/3]
- **Icons:** Mint-Y-Aqua [GTK2/3]
- **Terminal:** gnome-terminal
- **CPU:** 13th Gen Intel i7-13700HX (24 cores)
- **GPU 1:** NVIDIA GeForce RTX 4060 Max-Q
- **GPU 2:** Intel Alder Lake-HX GT1 [UHD Graphics]
- **Memory:** 4259 MiB / 31780 MiB
----------------------------------------------------------------------------------------------------------------------
# Tutorial

**Make sure you all all drivers installed and secureboot disabled in the BIOS before continuing** 

## Manual Switching
Open the Terminal and run these commands.

To check which GPU is currently running
- prime select query

Should say one of the threee things
- Other GPU (the actual name)
- NVIDIA driver
- On-Demand
  
Run:
 - sudo prime-select (desired GPU of choice)
(i.e) sudo prime-select intel

This will switch to the intel gpu and shut off the NVIDIA GPU

### How To Switch With KeyBoard Shortcuts
- Go to Keyboard Settings and on the left hand side look for custom shortcut category
- add custom shortcut
- Name it what you prefer I stick with Intel,NVIDIA, On-Demand

  add image here

  ### Intel Commmand
  - sh -c "pkexec prime-select intel"
  will bring up a prompt - enter password and it will switch GPU
  Use prime select query in terminal, should return intel


  ### NVIDIA Commnad
  - sh -c "pkexec prime-select nvidia && reboot"
  When turning NVIDIA back on a system reboot **IS NEEDED**
  Use prime select query in terminal, should retrurn NVIDIA


  ### On-Demand Command
  - sh -c "pkexec prime-select on-demand && reboot"
  When turning NVIDIA back on a system reboot **IS NEEDED**
  Use prime select query in terminal, should retrurn On-Demand

Configure with your preferred keybinds

enjoy
----------------------------------------------------------------------------------------------------------------------
fennerii 

Last Updated 3/11/26

