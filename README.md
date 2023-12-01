# LinuxCNC configs for my 1994 Denford Starmill

Mesa 7i96S  
Mesa 7i73  
topcom.cz SMART.MER/2  
topcom.cz DIG3D.LP.M  
topcom.cz DIG3D.Fix  
Sprint 800 VFD  

NUC11TNHI50L  
2x8G CorsVeng SODIMM DDR4 3000  
480GB WD Green SN350 M.2  


Starmill-Mesa-PB is in used with probe_basic  
Starmill-Mesa was gmocappy test config, the used as base to convert to PB

![Starmill](/images/Starmill.jpeg)

Probes
![Probes](/images/Probes.jpeg)

Control Cabinet
![Control Cabinet](/images/ControlCabinet.jpeg)


```
ln -s ~/github/starmill-linuxcnc/Starmill-Mesa-PB ~/linuxcnc/configs/Starmill-Mesa-PB
ln -s ~/github/starmill-linuxcnc/nc_files/probe_basic ~/linuxcnc/nc_files/probe_basic
```
