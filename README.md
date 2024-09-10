# INTEL-NVIDIA-BIOS with XFCE LINUX

Some old Motherboard with AMIBIOS running LINUX would sometimes freeze with XFCE. The following LINUX parameters would benefit the INTEL-NVIDIA-BIOS systems.

NOTE: These parameters may not work on your system. Use with caution!

ADD TO KERNEL BOOT:<br>
acpi_osi=! acpi_osi='Windows 2009'<br>

XFCE:<br>
CHECK VBLANK MODE => xfconf-query -c xfwm4 -p /general/vblank_mode --verbose<br>
DISABLE XFCE GLX => xfconf-query -c xfwm4 -p /general/vblank_mode -t string -s off --create<br>

WINDOWS COMPOSITOR:<br>
compton --vsync opengl-swc --paint-on-overlay --shadow-exclude "! name~=''" --use-ewmh-active-win -b<br>
or<br>
picom --vsync --shadow-exclude "! name~=''" --use-ewmh-active-win -b<br>
or<br>
picom --use-ewmh-active-win --backend glx --glx-no-stencil --vsync -b<br>
