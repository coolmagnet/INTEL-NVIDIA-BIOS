# INTEL-NVIDIA-BIOS with LINUX

Some old Motherboard with AMIBIOS running LINUX would sometimes unknowingly freeze within the Desktop (e.g. XFCE).  The following LINUX parameters would benefit the INTEL-NVIDIA-BIOS systems.

ADD TO KERNEL BOOT:
acpi_osi=! acpi_osi='Windows 2009'

XFCE:
CHECK VBLANK MODE =>  xfconf-query -c xfwm4 -p /general/vblank_mode --verbose

DISABLE XFCE GLX =>  xfconf-query -c xfwm4 -p /general/vblank_mode -t string -s off --create

WINDOWS COMPOSITOR:
compton --vsync opengl-swc --paint-on-overlay --shadow-exclude "! name~=''" --use-ewmh-active-win -b
OR
picom --vsync --shadow-exclude "! name~=''" --use-ewmh-active-win -b
  
