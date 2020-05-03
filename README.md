# Nanopi-r2s-ubuntu-server-minimal-image

Ubuntu 19.10 Server for NanoPi R2S

This is the base Image for a small router, based on Kernel 5.4.25 and up for the NanoPi R2S

Release with Kernel version:

* [v0.1 - Kernel 5.4.25](#v01---ubuntu-1910-server-nanopi-r2s)

* v0.2 - Kernel 5.4.27

* v0.3 - Kernel 5.4.28

* v0.4 - Kernel 5.6.2

* [v0.5 - Kernel 5.6.5](#v05---ubuntu-2004-lts-server-with-kernel-565-experimental)

* v0.5f - fix root owner (/) on Ubuntu 20.04 LTS

* [v0.6 - Kernel 5.6.7 - Ubuntu 20.04 LTS Server](#v06---kernel-567---ubuntu-2004-lts-server)

* v0.6k - Kernel 5.6.7

* v0.7k - Kernel 5.7.0-rc3

* [v0.7i - Kernel 5.7.0-rc3 Image](#v07i---kernel-570-rc3-image)

![NanoPi R2S](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/nanopi-r2s.jpg)

* i2c0 

![NanoPi R2S I2c](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/nanopi-r2s-i2c.jpg)

* Interfaces

      eth0: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
              inet 192.168.254.21  netmask 255.255.0.0  broadcast 192.168.255.255
              ether 2a:5e:77:5a:8f:4f  txqueuelen 1000  (Ethernet)
              RX packets 209  bytes 20463 (20.4 KB)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 148  bytes 19872 (19.8 KB)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
              device interrupt 28  

      eth1: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
              inet 192.168.254.22  netmask 255.255.0.0  broadcast 192.168.255.255
              inet6 2804:7f4:3081:9558:8470:9c35:984c:e8fe  prefixlen 64  scopeid 0x0<global>
              inet6 fe80::fc67:30ff:fe6c:b94b  prefixlen 64  scopeid 0x20<link>
              inet6 2804:7f4:3081:9558:fc67:30ff:fe6c:b94b  prefixlen 64  scopeid 0x0<global>
              ether fe:67:30:6c:b9:4b  txqueuelen 1000  (Ethernet)
              RX packets 1638  bytes 106543 (106.5 KB)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 1225  bytes 174911 (174.9 KB)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

      lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
              inet 127.0.0.1  netmask 255.0.0.0
              inet6 ::1  prefixlen 128  scopeid 0x10<host>
              loop  txqueuelen 1000  (Local Loopback)
              RX packets 54  bytes 4832 (4.8 KB)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 54  bytes 4832 (4.8 KB)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

# Releases

## v0.1 - Ubuntu 19.10 Server NanoPi R2S

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.1


## v0.2 - Mini Router NanoPi R2S

The "perfect" mini router with Ubuntu 19.10 for the NanoPi R2S. This mini router will isolate your local network from outside (internet / web).

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.2

**NanoPi R2S Mini router configuration**

![NanoPi R2S](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/router.png)

**rtl8821cu usb wlan**

rtl8xxxu should be enough, added rtl8821cu for the sake of compatibility.

      [48272.791672] usb 2-1: new high-speed USB device number 2 using ehci-platform
      [48272.822407] usb 2-1: New USB device found, idVendor=0bda, idProduct=8176, bcdDevice= 2.00
      [48272.822436] usb 2-1: New USB device strings: Mfr=1, Product=2, SerialNumber=3
      [48272.822461] usb 2-1: Product: 802.11n WLAN Adapter
      [48272.822477] usb 2-1: Manufacturer: Realtek
      [48272.822492] usb 2-1: SerialNumber: 00e04c000001
      [48273.267456] cfg80211: Loading compiled-in X.509 certificates for regulatory database
      [48273.290433] cfg80211: Loaded X.509 cert 'sforshee: 00b28ddf47aef9cea7'
      [48274.431150] rtl8192cu: Chip version 0x10
      [48274.532280] rtl8192cu: Board Type 0
      [48274.532601] rtl_usb: rx_max_size 15360, rx_urb_num 8, in_ep 1
      [48274.532781] rtl8192cu: Loading firmware rtlwifi/rtl8192cufw_TMSC.bin
      [48274.534434] ieee80211 phy0: Selected rate control algorithm 'rtl_rc'
      [48274.537632] usbcore: registered new interface driver rtl8192cu
      [48274.625790] usbcore: registered new interface driver rtl8xxxu
      [48274.654369] rtl8192cu 2-1:1.0 wlx7cdd902fdefa: renamed from wlan0

* Modules
      
      Module                  Size  Used by
      iptable_nat            16384  1
      xt_MASQUERADE          20480  1
      nf_nat                 65536  2 iptable_nat,xt_MASQUERADE
      xt_conntrack           16384  2
      nf_conntrack          151552  3 xt_conntrack,nf_nat,xt_MASQUERADE
      nf_defrag_ipv6         24576  1 nf_conntrack
      nf_defrag_ipv4         16384  1 nf_conntrack
      iptable_filter         16384  1
      zram                   40960  4
      zsmalloc               28672  1 zram
      r8152                  77824  0
      crct10dif_ce           16384  1
      uio_pdrv_genirq        16384  0
      uio                    24576  1 uio_pdrv_genirq
      sch_fq_codel           20480  3
      ip_tables              32768  2 iptable_filter,iptable_nat
      x_tables               40960  4 xt_conntrack,iptable_filter,ip_tables,xt_MASQUERADE
           
**filemanager-http**

If you are not concerned about security you could run a file manager using a web browser, and configure **nanopi-r2s** as a gateway.

just run :

    ubuntu@nanopi-r2s:~$ sudo /usr/local/bin/filemanager-httpd

![File manager](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/file-manager.png)

      ubuntu@nanopi-r2s:~$ ifconfig
      eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
              inet 192.168.254.21  netmask 255.255.0.0  broadcast 192.168.255.255
              inet6 fe80::285e:77ff:fe5a:8f4f  prefixlen 64  scopeid 0x20<link>
              inet6 2804:7f4:358b:2710:285e:77ff:fe5a:8f4f  prefixlen 64  scopeid 0x0<global>
              ether 2a:5e:77:5a:8f:4f  txqueuelen 1000  (Ethernet)
              RX packets 8636  bytes 11687238 (11.6 MB)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 5043  bytes 508024 (508.0 KB)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
              device interrupt 28  

      eth1: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
              inet 192.168.1.1  netmask 255.255.255.0  broadcast 255.255.1.255
              ether 3e:1b:ee:4b:8e:11  txqueuelen 1000  (Ethernet)
              RX packets 0  bytes 0 (0.0 B)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 0  bytes 0 (0.0 B)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

      lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
              inet 127.0.0.1  netmask 255.0.0.0
              inet6 ::1  prefixlen 128  scopeid 0x10<host>
              loop  txqueuelen 1000  (Local Loopback)
              RX packets 0  bytes 0 (0.0 B)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 0  bytes 0 (0.0 B)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

**Configuring WAN (eth0)**

You can configure your WAN interface as a DHCP, fixed IP or according to your service provider. Edit the file /etc/network/interfaces and change the eth0 configuration as desired, in my case i have DHCP (default):

* Edit the file:

      sudo jed /etc/network/interfaces      
      
 
 * File content
        
            # interfaces(5) file used by ifup(8) and ifdown(8)
            auto lo
            iface lo inet loopback

            auto eth0
            #allow-hotplug eth0
            iface eth0 inet dhcp

            #allow-hotplug eth1
            #iface eth1 inet dhcp
            auto eth1
            iface eth1 inet static
            address 192.168.1.1
            netmask 255.255.255.0
            broadcast 255.255.1.255    
            #gateway 192.168.1.1
            dns-nameservers 8.8.8.8 8.8.4.4

            #allow-hotplug wlan0
            #iface wlan0 inet dhcp
            #	wpa-ssid "foxy"
            #	wpa-psk "1234567890"
            #address 192.168.254.55
            #netmask 255.255.0.0
            #gateway 192.168.254.254
            #dns-nameservers 8.8.8.8 8.8.4.4
            ####wpa-conf /etc/wpa_supplicant/wpa_supplicant.conf
            # Disable power saving on compatible chipsets (prevents SSH/connection dropouts over WiFi)
            #wireless-mode Managed
            #wireless-power off

**Client connection (DHCP)**

A Linux desktop connected to the LAN interface of our mini router to surf the internet.

![File manager](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/client-1.png)

## v0.3 - Mini Router NanoPi R2S with eth-monitor

Kernel updated to 5.4.28 with eth-monitor to display the eth status for the WAN and LAN interface.
When the WAN is up, the WAN led will be ON, when down, WAN led will be OFF.

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.3

## v0.4  - Mini Router NanoPi R2S with eth-monitor

Kernel updated to 5.6.2 with eth-monitor to display the eth status for the WAN and LAN interface.
If WAN is up, the WAN led is ON, if down, WAN led is OFF. Same for the LAN interface.

eth-monitor runs as service. You can stop, start or see the status of the service.

      sudo systemctl status eth-monitor.service
      sudo systemctl stop eth-monitor.service
      sudo systemctl start eth-monitor.service
      

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.4


## v0.5 - Ubuntu 20.04 LTS Server with Kernel 5.6.5 (Experimental)

Our mini router is kind of slow on the iptable NAT routing/fowarding and i can't find a way to optimize it or don't know how to do it. For this reason we will try the Ubuntu Beta version and see what we can get, all from scratch.
In my experiments, the routing and forwarding  is 8x slower than using the Gigabit port directly, maybe the NAT rules are overkill somewhere.

Add Initial support for rtl8822bu with Ubuntu Focal, the smallest Image size i could get, just for evaluation on RK3328 boards.

**Ubuntu Focal 20.04 LTS Server**

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.5


## v0.5a -Kernel 5.6.5

**Fix** DTB file name after install Kernel 5.6.5 **before you reboot**


## v0.5f - Fix

 Fix root owner:
 
    sudo chown root:root /

## v0.6k - Kernel 5.6.7

## v0.6 - Ubuntu 20.04 LTS Server with Kernel 5.6.7

Ubuntu 20.04 LTS Server with kernel update and minor fix.

## v0.7k - Kernel 5.6.7

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.7k


## v0.7i - Kernel 5.7.0-rc3 Image

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.7i

* Burn SD Card with etcher or **Win32DiskImager**
* Use **7z** to unzip
* boot with this Img and login with: **ubuntu** / **ubuntu**
* resize rootfs manually or try **resize_rootfs.sh** to reclaim all space in the sd card
  after login, issue the command in the shell:
  
      sudo chmod +x resize_rootfs.sh
      sudo ./resize_rootfs.sh


## Boot

When you turn ON the board, the 3 leds will go ON for a few seconds and later WAN and LAN leds will show the status link.

## Latest Kernel - NanoPi R2S mini router - Ubuntu 19.10

Linux nanopi-r2s 5.6.1 #2 SMP PREEMPT Thu Apr 2 19:50:55 -03 2020 aarch64 aarch64 aarch64 GNU/Linux

## Status

* eth0 (ok)
* eth1 (ok)
* DVFS (ok)
* eth link status monitoring (ok)

## Cpu / Kernel Health

Checking the board health (manually)

      cat /sys/devices/virtual/thermal/thermal_zone0/temp
      38181
      cat /sys/devices/system/cpu/cpufreq/policy0/cpuinfo_cur_freq 
      408000
      cat /sys/devices/platform/ff160000.i2c/i2c-1/1-0018/regulator/regulator.8/microvolts 
      950000


## Interface monitoring

Kernel has support for leds so we can control the available leds on the board.

    sudo su
    cd /sys/class/leds/
    root@nanopi-r2s:/sys/class/leds# ls
    lan_led  status_led  wan_led


**The available options are:**

      [none] rc-feedback rfkill-any rfkill-none kbd-scrolllock kbd-numlock kbd-capslock kbd-kanalock kbd-shiftlock kbd-altgrlock kbd-ctrllock kbd-altlock kbd-shiftllock kbd-shiftrlock kbd-ctrlllock kbd-ctrlrlock mmc0 timer oneshot heartbeat gpio cpu cpu0 cpu1 cpu2 cpu3 default-on panic 


* To turn on the wan_led

    echo "default-on" > /sys/class/leds/wan_led/trigger 

* To turn off the wan_led

    echo "none" > /sys/class/leds/wan_led/trigger 
    
We can now move on and install a service to show the status of our WAN and LAN interfaces turning the wan_led and lan_led ON and OFF.

## htop 2.2.2

Monitor the health of NanoPi R2S with htop.

* Install

        wget https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/htop_2.2.2-1_arm64.deb
        sudo dpkg -i htop_2.2.2-1_arm64.deb 

![NanoPi R2S htop](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/NanoPi-R2S.png)

## Testing USB Realtek 8152

I did a simple test to check if the USB Realtek RTL8152-B is working at Gb speed and compared to my PCI Gb in my linux box.
My internet connections is 25 Mb, so i download 1GB of data and compare both.

**gigabit PCI (linux box X64)**

            [    2.079301] r8169 0000:02:00.0 eth0: RTL8168c/8111c, e0:cb:4e:81:11:5a, XID 3c4, IRQ 17
            
 *

      alex@svn:~$ wget https://speed.hetzner.de/1GB.bin
      --2020-04-04 15:43:25--  https://speed.hetzner.de/1GB.bin
      Resolving speed.hetzner.de (speed.hetzner.de)... 2a01:4f8:0:59ed::2, 88.198.248.254
      Connecting to speed.hetzner.de (speed.hetzner.de)|2a01:4f8:0:59ed::2|:443... connected.
      HTTP request sent, awaiting response... 200 OK
      Length: 1048576000 (1000M) [application/octet-stream]
      Saving to: ‘1GB.bin.1’

      1GB.bin.1             5%[>                   ]  50,87M  2,71MB/s    eta 8m 2s  ^C

**gigabit USB (NanoPi R2S eth1 = LAN)**

            [   11.032460] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether addr 4e:86:d7:06:7f:9d

* 

      ubuntu@nanopi-r2s:~$ wget https://speed.hetzner.de/1GB.bin
      --2020-04-04 18:44:02--  https://speed.hetzner.de/1GB.bin
      Resolving speed.hetzner.de (speed.hetzner.de)... 2a01:4f8:0:59ed::2, 88.198.248.254
      Connecting to speed.hetzner.de (speed.hetzner.de)|2a01:4f8:0:59ed::2|:443... connected.
      HTTP request sent, awaiting response... 200 OK
      Length: 1048576000 (1000M) [application/octet-stream]
      Saving to: ‘1GB.bin.1’

      1GB.bin.1             5%[>                   ]  50.91M  2.70MB/s    eta 8m 11s ^C

## Reading gpio-keys button

There is a button available called reset button and can be red as an event with mainline kernel.
You can check the status of the button like this:

      ubuntu@nanopi-r2s:~$ sudo evtest
      No device specified, trying to scan all of /dev/input/event*
      Available devices:
      /dev/input/event0:	rk805 pwrkey
      /dev/input/event1:	gpio-keys
      Select the device event number [0-1]: 1
      Input driver version is 1.0.1
      Input device ID: bus 0x19 vendor 0x1 product 0x1 version 0x100
      Input device name: "gpio-keys"
      Supported events:
        Event type 0 (EV_SYN)
        Event type 1 (EV_KEY)
          Event code 257 (BTN_1)
      Key repeat handling:
        Repeat type 20 (EV_REP)
          Repeat code 0 (REP_DELAY)
            Value    250
          Repeat code 1 (REP_PERIOD)
            Value     33
      Properties:
      Testing ... (interrupt to exit)
      Event: time 1587947451.537380, type 1 (EV_KEY), code 257 (BTN_1), value 1
      Event: time 1587947451.537380, -------------- SYN_REPORT ------------
      Event: time 1587947451.793277, type 1 (EV_KEY), code 257 (BTN_1), value 2
      Event: time 1587947451.793277, -------------- SYN_REPORT ------------
      Event: time 1587947451.793277, type 1 (EV_KEY), code 257 (BTN_1), value 0
      Event: time 1587947451.793277, -------------- SYN_REPORT ------------
      Event: time 1587947465.053375, type 1 (EV_KEY), code 257 (BTN_1), value 1
      Event: time 1587947465.053375, -------------- SYN_REPORT ------------
      Event: time 1587947465.309248, type 1 (EV_KEY), code 257 (BTN_1), value 2
      Event: time 1587947465.309248, -------------- SYN_REPORT ------------
      Event: time 1587947465.349248, type 1 (EV_KEY), code 257 (BTN_1), value 2
      Event: time 1587947465.349248, -------------- SYN_REPORT ------------
      Event: time 1587947465.389243, type 1 (EV_KEY), code 257 (BTN_1), value 2
      Event: time 1587947465.389243, -------------- SYN_REPORT ------------
      Event: time 1587947465.389243, type 1 (EV_KEY), code 257 (BTN_1), value 0
      Event: time 1587947465.389243, -------------- SYN_REPORT ------------

Or check if it is working like this:

      ubuntu@nanopi-r2s:~$ sudo cat /dev/input/event1|hexdump
      0000000 2751 5ea6 0000 0000 f482 0007 0000 0000
      0000010 0001 0101 0001 0000 2751 5ea6 0000 0000
      0000020 f482 0007 0000 0000 0000 0000 0000 0000
      0000030 2751 5ea6 0000 0000 bd51 000b 0000 0000
      0000040 0001 0101 0000 0000 2751 5ea6 0000 0000
      0000050 bd51 000b 0000 0000 0000 0000 0000 0000
      0000060 2756 5ea6 0000 0000 8e6a 000b 0000 0000
      0000070 0001 0101 0001 0000 2756 5ea6 0000 0000
      0000080 8e6a 000b 0000 0000 0000 0000 0000 0000
      0000090 2757 5ea6 0000 0000 33c5 0000 0000 0000
      00000a0 0001 0101 0002 0000 2757 5ea6 0000 0000
      00000b0 33c5 0000 0000 0000 0000 0000 0001 0000
      00000c0 2757 5ea6 0000 0000 d000 0000 0000 0000
      00000d0 0001 0101 0002 0000 2757 5ea6 0000 0000
      00000e0 d000 0000 0000 0000 0000 0000 0001 0000
      00000f0 2757 5ea6 0000 0000 6c3f 0001 0000 0000
      0000100 0001 0101 0002 0000 2757 5ea6 0000 0000
      0000110 6c3f 0001 0000 0000 0000 0000 0001 0000
      0000120 2757 5ea6 0000 0000 6c3f 0001 0000 0000
      0000130 0001 0101 0000 0000 2757 5ea6 0000 0000
      0000140 6c3f 0001 0000 0000 0000 0000 0000 0000
      0000150 2757 5ea6 0000 0000 e614 000c 0000 0000
      0000160 0001 0101 0001 0000 2757 5ea6 0000 0000
      0000170 e614 000c 0000 0000 0000 0000 0000 0000
      0000180 2758 5ea6 0000 0000 ef85 0000 0000 0000
      0000190 0001 0101 0000 0000 2758 5ea6 0000 0000
      00001a0 ef85 0000 0000 0000 0000 0000 0000 0000

## ChangeLog

* add Kernel 5.4.25 (initial commit)
* add support for rtl8821cu usb (v0.2)
* add Kernel 5.4.27 (v0.2)
* add NanoPi R2S mini router (v0.2)
* add Kernel 5.4.28 (v0.3)
* add NanoPi R2S mini router with eth-monitor (v0.3)
* add Kernel 5.6.2 (v0.4)
* add Kernel 5.6.5 and rtl8822bu (v0.5)
* add Kernel 5.6.7 and some fix (v0.6k and v0.6)
* add Ubuntu 20.04 LTS Focal Fossa
* add Kernel 5.7.0-rc3
* add Kernel 5.7.0-rc3 (2GB Image)

## BootLog

      [    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
      [    0.000000] Linux version 5.7.0-rc3-hdmi-sound-h6 (alex@svn) (gcc version 7.5.0 (Linaro GCC 7.5-2019.12-rc1), GNU ld (Linaro_Binutils-2019.12-rc1) 2.28.2.20170706) #1 SMP PREEMPT Fri May 1 10:29:12 -03 2020
      [    0.000000] Machine model: FriendlyElec NanoPi R2S
      [    0.000000] efi: UEFI not found.
      [    0.000000] cma: Reserved 16 MiB at 0x000000003f000000
      [    0.000000] On node 0 totalpages: 261632
      [    0.000000]   DMA zone: 4088 pages used for memmap
      [    0.000000]   DMA zone: 0 pages reserved
      [    0.000000]   DMA zone: 261632 pages, LIFO batch:63
      [    0.000000] psci: probing for conduit method from DT.
      [    0.000000] psci: PSCIv1.0 detected in firmware.
      [    0.000000] psci: Using standard PSCI v0.2 function IDs
      [    0.000000] psci: MIGRATE_INFO_TYPE not supported.
      [    0.000000] psci: SMC Calling Convention v1.0
      [    0.000000] percpu: Embedded 32 pages/cpu s90216 r8192 d32664 u131072
      [    0.000000] pcpu-alloc: s90216 r8192 d32664 u131072 alloc=32*4096
      [    0.000000] pcpu-alloc: [0] 0 [0] 1 [0] 2 [0] 3 
      [    0.000000] Detected VIPT I-cache on CPU0
      [    0.000000] CPU features: detected: ARM erratum 845719
      [    0.000000] Built 1 zonelists, mobility grouping on.  Total pages: 257544
      [    0.000000] Kernel command line: earlyprintk root=/dev/mmcblk0p2 rw rootfstype=ext4 rootwait fsck.repair=yes panic=10 no_console_suspend consoleblank=0
      [    0.000000] Dentry cache hash table entries: 131072 (order: 8, 1048576 bytes, linear)
      [    0.000000] Inode-cache hash table entries: 65536 (order: 7, 524288 bytes, linear)
      [    0.000000] mem auto-init: stack:off, heap alloc:off, heap free:off
      [    0.000000] Memory: 981740K/1046528K available (13372K kernel code, 1742K rwdata, 9216K rodata, 1344K init, 800K bss, 48404K reserved, 16384K cma-reserved)
      [    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
      [    0.000000] ftrace: allocating 43871 entries in 172 pages
      [    0.000000] ftrace: allocated 172 pages with 4 groups
      [    0.000000] rcu: Preemptible hierarchical RCU implementation.
      [    0.000000] rcu: 	RCU restricting CPUs from NR_CPUS=8 to nr_cpu_ids=4.
      [    0.000000] 	Tasks RCU enabled.
      [    0.000000] rcu: RCU calculated value of scheduler-enlistment delay is 25 jiffies.
      [    0.000000] rcu: Adjusting geometry for rcu_fanout_leaf=16, nr_cpu_ids=4
      [    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
      [    0.000000] GIC: Using split EOI/Deactivate mode
      [    0.000000] random: get_random_bytes called from start_kernel+0x314/0x4a0 with crng_init=0
      [    0.000000] arch_timer: cp15 timer(s) running at 24.00MHz (phys).
      [    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles: 0x588fe9dc0, max_idle_ns: 440795202592 ns
      [    0.000009] sched_clock: 56 bits at 24MHz, resolution 41ns, wraps every 4398046511097ns
      [    0.000937] Console: colour dummy device 80x25
      [    0.001640] printk: console [tty0] enabled
      [    0.001713] Calibrating delay loop (skipped), value calculated using timer frequency.. 48.00 BogoMIPS (lpj=96000)
      [    0.001760] pid_max: default: 32768 minimum: 301
      [    0.002010] LSM: Security Framework initializing
      [    0.002172] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.002217] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.005407] rcu: Hierarchical SRCU implementation.
      [    0.009309] EFI services will not be available.
      [    0.010322] smp: Bringing up secondary CPUs ...
      [    0.011426] Detected VIPT I-cache on CPU1
      [    0.011526] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
      [    0.012865] Detected VIPT I-cache on CPU2
      [    0.012958] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
      [    0.014190] Detected VIPT I-cache on CPU3
      [    0.014276] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
      [    0.014488] smp: Brought up 1 node, 4 CPUs
      [    0.014654] SMP: Total of 4 processors activated.
      [    0.014688] CPU features: detected: 32-bit EL0 Support
      [    0.014720] CPU features: detected: CRC32 instructions
      [    0.040023] CPU: All CPU(s) started at EL2
      [    0.040134] alternatives: patching kernel code
      [    0.042550] devtmpfs: initialized
      [    0.060381] Registered cp15_barrier emulation handler
      [    0.060447] Registered setend emulation handler
      [    0.061233] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
      [    0.061307] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
      [    0.062872] pinctrl core: initialized pinctrl subsystem
      [    0.063890] thermal_sys: Registered thermal governor 'fair_share'
      [    0.063898] thermal_sys: Registered thermal governor 'step_wise'
      [    0.064738] DMI not present or invalid.
      [    0.065848] NET: Registered protocol family 16
      [    0.069482] DMA: preallocated 256 KiB pool for atomic allocations
      [    0.069556] audit: initializing netlink subsys (disabled)
      [    0.069971] audit: type=2000 audit(0.068:1): state=initialized audit_enabled=0 res=1
      [    0.071447] cpuidle: using governor ladder
      [    0.071531] cpuidle: using governor menu
      [    0.071989] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
      [    0.072226] ASID allocator initialised with 65536 entries
      [    0.130804] HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
      [    0.130857] HugeTLB registered 32.0 MiB page size, pre-allocated 0 pages
      [    0.130890] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
      [    0.130921] HugeTLB registered 64.0 KiB page size, pre-allocated 0 pages
      [    0.137962] cryptd: max_cpu_qlen set to 1000
      [    0.163233] iommu: Default domain type: Translated 
      [    0.165153] SCSI subsystem initialized
      [    0.165679] libata version 3.00 loaded.
      [    0.166101] usbcore: registered new interface driver usbfs
      [    0.166226] usbcore: registered new interface driver hub
      [    0.166418] usbcore: registered new device driver usb
      [    0.166552] mc: Linux media interface: v0.10
      [    0.166622] videodev: Linux video capture interface: v2.00
      [    0.166711] pps_core: LinuxPPS API ver. 1 registered
      [    0.166738] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
      [    0.166795] PTP clock support registered
      [    0.167710] Advanced Linux Sound Architecture Driver Initialized.
      [    0.168888] Bluetooth: Core ver 2.22
      [    0.169073] NET: Registered protocol family 31
      [    0.169099] Bluetooth: HCI device and connection manager initialized
      [    0.169154] Bluetooth: HCI socket layer initialized
      [    0.169193] Bluetooth: L2CAP socket layer initialized
      [    0.169257] Bluetooth: SCO socket layer initialized
      [    0.169314] NetLabel: Initializing
      [    0.169338] NetLabel:  domain hash size = 128
      [    0.169363] NetLabel:  protocols = UNLABELED CIPSOv4 CALIPSO
      [    0.169491] NetLabel:  unlabeled traffic allowed by default
      [    0.170685] clocksource: Switched to clocksource arch_sys_counter
      [    1.774589] VFS: Disk quotas dquot_6.6.0
      [    1.774839] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
      [    1.775176] FS-Cache: Loaded
      [    1.790728] NET: Registered protocol family 2
      [    1.791850] tcp_listen_portaddr_hash hash table entries: 512 (order: 2, 20480 bytes, linear)
      [    1.791963] TCP established hash table entries: 8192 (order: 4, 65536 bytes, linear)
      [    1.792114] TCP bind hash table entries: 8192 (order: 6, 262144 bytes, linear)
      [    1.792645] TCP: Hash tables configured (established 8192 bind 8192)
      [    1.792940] UDP hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.793081] UDP-Lite hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.793822] NET: Registered protocol family 1
      [    1.795047] RPC: Registered named UNIX socket transport module.
      [    1.795103] RPC: Registered udp transport module.
      [    1.795128] RPC: Registered tcp transport module.
      [    1.795158] RPC: Registered tcp NFSv4.1 backchannel transport module.
      [    1.795207] PCI: CLS 0 bytes, default 64
      [    1.795614] Trying to unpack rootfs image as initramfs...
      [    1.876591] Freeing initrd memory: 1076K
      [    1.878421] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 counters available
      [    1.898359] Initialise system trusted keyrings
      [    1.898931] workingset: timestamp_bits=46 max_order=18 bucket_order=0
      [    1.914777] squashfs: version 4.0 (2009/01/31) Phillip Lougher
      [    1.915445] FS-Cache: Netfs 'nfs' registered for caching
      [    1.916592] NFS: Registering the id_resolver key type
      [    1.916671] Key type id_resolver registered
      [    1.916697] Key type id_legacy registered
      [    1.916737] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
      [    1.917158] fuse: init (API version 7.31)
      [    1.944098] Key type asymmetric registered
      [    1.944147] Asymmetric key parser 'x509' registered
      [    1.944265] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 247)
      [    1.944625] io scheduler mq-deadline registered
      [    1.944669] io scheduler kyber registered
      [    1.952747] rockchip-u3phy ff470000.usb3-phy: Rockchip u3phy initialized successfully
      [    1.959160] dma-pl330 ff1f0000.dmac: Loaded driver for PL330 DMAC-241330
      [    1.959219] dma-pl330 ff1f0000.dmac: 	DBUFF-128x8bytes Num_Chans-8 Num_Peri-20 Num_Events-16
      [    1.960291] Serial: 8250/16550 driver, 5 ports, IRQ sharing disabled
      [    1.963525] ff130000.serial: ttyS2 at MMIO 0xff130000 (irq = 12, base_baud = 1500000) is a 16550A
      [    2.034436] printk: console [ttyS2] enabled
      [    2.039027] rockchip-drm display-subsystem: [drm:rockchip_drm_platform_probe] *ERROR* No available vop found for display-subsystem.
      [    2.053771] brd: module loaded
      [    2.074617] loop: module loaded
      [    2.078353] libphy: Fixed MDIO Bus: probed
      [    2.080476] rk_gmac-dwmac ff540000.ethernet: IRQ eth_wake_irq not found
      [    2.081112] rk_gmac-dwmac ff540000.ethernet: IRQ eth_lpi not found
      [    2.081897] rk_gmac-dwmac ff540000.ethernet: PTP uses main clock
      [    2.082721] rk_gmac-dwmac ff540000.ethernet: clock input or output? (input).
      [    2.083375] rk_gmac-dwmac ff540000.ethernet: TX delay(0x24).
      [    2.083905] rk_gmac-dwmac ff540000.ethernet: RX delay(0x18).
      [    2.084443] rk_gmac-dwmac ff540000.ethernet: integrated PHY? (no).
      [    2.085131] rk_gmac-dwmac ff540000.ethernet: cannot get clock clk_mac_speed
      [    2.085767] rk_gmac-dwmac ff540000.ethernet: clock input from PHY
      [    2.091380] rk_gmac-dwmac ff540000.ethernet: init for RGMII
      [    2.092326] rk_gmac-dwmac ff540000.ethernet: User ID: 0x10, Synopsys ID: 0x35
      [    2.093007] rk_gmac-dwmac ff540000.ethernet: 	DWMAC1000
      [    2.093499] rk_gmac-dwmac ff540000.ethernet: DMA HW capability register supported
      [    2.094189] rk_gmac-dwmac ff540000.ethernet: RX Checksum Offload Engine supported
      [    2.094923] rk_gmac-dwmac ff540000.ethernet: COE Type 2
      [    2.095416] rk_gmac-dwmac ff540000.ethernet: TX Checksum insertion supported
      [    2.096058] rk_gmac-dwmac ff540000.ethernet: Wake-Up On Lan supported
      [    2.096717] rk_gmac-dwmac ff540000.ethernet: Normal descriptors
      [    2.097267] rk_gmac-dwmac ff540000.ethernet: Ring mode enabled
      [    2.097806] rk_gmac-dwmac ff540000.ethernet: Enable RX Mitigation via HW Watchdog Timer
      [    2.158700] libphy: stmmac: probed
      [    2.162221] PPP generic driver version 2.4.2
      [    2.163144] usbcore: registered new interface driver asix
      [    2.163734] usbcore: registered new interface driver ax88179_178a
      [    2.164342] usbcore: registered new interface driver cdc_ether
      [    2.164935] usbcore: registered new interface driver qmi_wwan
      [    2.168130] phy phy-ff470000.usb3-phy.2: u3phy u2 power on
      [    2.168703] phy phy-ff470000.usb3-phy.3: u3phy u3 power on
      [    2.170877] dwc2 ff580000.usb: supply vusb_d not found, using dummy regulator
      [    2.171764] dwc2 ff580000.usb: supply vusb_a not found, using dummy regulator
      [    2.302810] dwc2 ff580000.usb: EPs: 10, dedicated fifos, 972 entries in SPRAM
      [    2.304122] dwc2 ff580000.usb: DWC OTG Controller
      [    2.304607] dwc2 ff580000.usb: new USB bus registered, assigned bus number 1
      [    2.305308] dwc2 ff580000.usb: irq 29, io mem 0xff580000
      [    2.306142] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.07
      [    2.306958] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.307626] usb usb1: Product: DWC OTG Controller
      [    2.308067] usb usb1: Manufacturer: Linux 5.7.0-rc3-hdmi-sound-h6 dwc2_hsotg
      [    2.308713] usb usb1: SerialNumber: ff580000.usb
      [    2.310209] hub 1-0:1.0: USB hub found
      [    2.310628] hub 1-0:1.0: 1 port detected
      [    2.312450] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
      [    2.313097] ehci-pci: EHCI PCI platform driver
      [    2.313600] ehci-platform: EHCI generic platform driver
      [    2.316848] ehci-platform ff5c0000.usb: EHCI Host Controller
      [    2.317433] ehci-platform ff5c0000.usb: new USB bus registered, assigned bus number 2
      [    2.318371] ehci-platform ff5c0000.usb: irq 30, io mem 0xff5c0000
      [    2.334719] ehci-platform ff5c0000.usb: USB 2.0 started, EHCI 1.00
      [    2.335762] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.07
      [    2.336531] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.337193] usb usb2: Product: EHCI Host Controller
      [    2.337650] usb usb2: Manufacturer: Linux 5.7.0-rc3-hdmi-sound-h6 ehci_hcd
      [    2.338284] usb usb2: SerialNumber: ff5c0000.usb
      [    2.339825] hub 2-0:1.0: USB hub found
      [    2.340246] hub 2-0:1.0: 1 port detected
      [    2.341542] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
      [    2.342168] ohci-platform: OHCI generic platform driver
      [    2.343379] ohci-platform ff5d0000.usb: Generic Platform OHCI controller
      [    2.344044] ohci-platform ff5d0000.usb: new USB bus registered, assigned bus number 3
      [    2.345008] ohci-platform ff5d0000.usb: irq 31, io mem 0xff5d0000
      [    2.407076] usb usb3: New USB device found, idVendor=1d6b, idProduct=0001, bcdDevice= 5.07
      [    2.407856] usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.408524] usb usb3: Product: Generic Platform OHCI controller
      [    2.409073] usb usb3: Manufacturer: Linux 5.7.0-rc3-hdmi-sound-h6 ohci_hcd
      [    2.409710] usb usb3: SerialNumber: ff5d0000.usb
      [    2.411245] hub 3-0:1.0: USB hub found
      [    2.411660] hub 3-0:1.0: 1 port detected
      [    2.413867] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.414429] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 4
      [    2.415522] xhci-hcd xhci-hcd.0.auto: hcc params 0x0220fe64 hci version 0x110 quirks 0x0000000002010010
      [    2.416497] xhci-hcd xhci-hcd.0.auto: irq 166, io mem 0xff600000
      [    2.417866] usb usb4: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.07
      [    2.418635] usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.419346] usb usb4: Product: xHCI Host Controller
      [    2.419804] usb usb4: Manufacturer: Linux 5.7.0-rc3-hdmi-sound-h6 xhci-hcd
      [    2.420432] usb usb4: SerialNumber: xhci-hcd.0.auto
      [    2.421993] hub 4-0:1.0: USB hub found
      [    2.422415] hub 4-0:1.0: 1 port detected
      [    2.423524] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.424062] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 5
      [    2.424778] xhci-hcd xhci-hcd.0.auto: Host supports USB 3.0 SuperSpeed
      [    2.425507] usb usb5: We don't know the algorithms for LPM for this host, disabling LPM.
      [    2.426486] usb usb5: New USB device found, idVendor=1d6b, idProduct=0003, bcdDevice= 5.07
      [    2.427287] usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.427956] usb usb5: Product: xHCI Host Controller
      [    2.428409] usb usb5: Manufacturer: Linux 5.7.0-rc3-hdmi-sound-h6 xhci-hcd
      [    2.429048] usb usb5: SerialNumber: xhci-hcd.0.auto
      [    2.430515] hub 5-0:1.0: USB hub found
      [    2.430976] hub 5-0:1.0: 1 port detected
      [    2.432317] usbcore: registered new interface driver cdc_acm
      [    2.432857] cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
      [    2.433662] usbcore: registered new interface driver cdc_wdm
      [    2.434621] usbcore: registered new interface driver uas
      [    2.435446] usbcore: registered new interface driver usb-storage
      [    2.436176] usbcore: registered new interface driver usbserial_generic
      [    2.436821] usbserial: USB Serial support registered for generic
      [    2.437458] usbcore: registered new interface driver ch341
      [    2.437993] usbserial: USB Serial support registered for ch341-uart
      [    2.438648] usbcore: registered new interface driver cp210x
      [    2.439239] usbserial: USB Serial support registered for cp210x
      [    2.439935] usbcore: registered new interface driver ftdi_sio
      [    2.440496] usbserial: USB Serial support registered for FTDI USB Serial Device
      [    2.441565] usbcore: registered new interface driver option
      [    2.442111] usbserial: USB Serial support registered for GSM modem (1-port)
      [    2.443395] usbcore: registered new interface driver pl2303
      [    2.443965] usbserial: USB Serial support registered for pl2303
      [    2.444620] usbcore: registered new interface driver qcserial
      [    2.445182] usbserial: USB Serial support registered for Qualcomm USB modem
      [    2.446840] mousedev: PS/2 mouse device common for all mice
      [    2.448414] i2c /dev entries driver
      [    2.452908] rk808 1-0018: chip id: 0x8050
      [    2.461392] rk808-regulator rk808-regulator: there is no dvs0 gpio
      [    2.462017] rk808-regulator rk808-regulator: there is no dvs1 gpio
      [    2.462790] DCDC_REG1: supplied by vcc_sys
      [    2.466194] DCDC_REG2: supplied by vcc_sys
      [    2.468664] DCDC_REG3: supplied by vcc_sys
      [    2.469600] DCDC_REG4: supplied by vcc_sys
      [    2.471567] LDO_REG1: supplied by vcc_io
      [    2.475450] LDO_REG2: supplied by vcc_io
      [    2.479313] LDO_REG3: supplied by vcc_io
      [    2.493533] rk808-rtc rk808-rtc: registered as rtc0
      [    2.495831] rk808-rtc rk808-rtc: setting system clock to 2016-01-21T08:50:08 UTC (1453366208)
      [    2.498892] input: rk805 pwrkey as /devices/platform/ff160000.i2c/i2c-1/1-0018/rk805-pwrkey/input/input0
      [    2.500966] IR NEC protocol handler initialized
      [    2.506734] rockchip-thermal ff250000.tsadc: Missing tshut mode property, using default (cru)
      [    2.507546] rockchip-thermal ff250000.tsadc: Missing tshut-polarity property, using default (low)
      [    2.510976] device-mapper: uevent: version 1.0.3
      [    2.512011] device-mapper: ioctl: 4.42.0-ioctl (2020-02-27) initialised: dm-devel@redhat.com
      [    2.518471] sdhci: Secure Digital Host Controller Interface driver
      [    2.519236] sdhci: Copyright(c) Pierre Ossman
      [    2.519656] Synopsys Designware Multimedia Card Interface Driver
      [    2.521495] dwmmc_rockchip ff500000.dwmmc: IDMAC supports 32-bit address mode.
      [    2.522215] dwmmc_rockchip ff500000.dwmmc: Using internal DMA controller.
      [    2.522912] dwmmc_rockchip ff500000.dwmmc: Version ID is 270a
      [    2.523551] dwmmc_rockchip ff500000.dwmmc: DW MMC controller at irq 27,32 bit host data width,256 deep fifo
      [    2.524526] vcc_sd: supplied by vcc_io
      [    2.542881] mmc_host mmc0: Bus speed (slot 0) = 400000Hz (slot req 400000Hz, actual 400000HZ div = 0)
      [    2.557084] sdhci-pltfm: SDHCI platform and OF driver helper
      [    2.559546] ledtrig-cpu: registered to indicate activity on CPUs
      [    2.560778] hid: raw HID events driver (C) Jiri Kosina
      [    2.561849] usbcore: registered new interface driver usbhid
      [    2.562373] usbhid: USB HID core driver
      [    2.568328] drop_monitor: Initializing network drop monitor service
      [    2.569323] Initializing XFRM netlink socket
      [    2.571078] NET: Registered protocol family 10
      [    2.574084] Segment Routing with IPv6
      [    2.592507] bpfilter: Loaded bpfilter_umh pid 234
      [    2.593464] NET: Registered protocol family 17
      [    2.594277] Bluetooth: RFCOMM TTY layer initialized
      [    2.594855] Bluetooth: RFCOMM socket layer initialized
      [    2.595377] Bluetooth: RFCOMM ver 1.11
      [    2.595740] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
      [    2.596285] Bluetooth: HIDP socket layer initialized
      [    2.596865] Key type dns_resolver registered
      [    2.598083] registered taskstats version 1
      [    2.598477] Loading compiled-in X.509 certificates
      [    2.599195] Key type ._fscrypt registered
      [    2.599610] Key type .fscrypt registered
      [    2.599991] Key type fscrypt-provisioning registered
      [    2.640904] input: gpio-keys as /devices/platform/gpio-keys/input/input1
      [    2.643898] ALSA device list:
      [    2.644205]   No soundcards found.
      [    2.644858] dw-apb-uart ff130000.serial: forbid DMA for kernel console
      [    2.649181] Freeing unused kernel memory: 1344K
      [    2.649689] Run /init as init process
      [    2.650024]   with arguments:
      [    2.650031]     /init
      [    2.650037]     earlyprintk
      [    2.650041]   with environment:
      [    2.650048]     HOME=/
      [    2.650053]     TERM=linux
      [    2.659397] random: fast init done
      [    2.770805] usb 5-1: new SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [    2.793088] usb 5-1: New USB device found, idVendor=0bda, idProduct=8153, bcdDevice=31.00
      [    2.793855] usb 5-1: New USB device strings: Mfr=1, Product=2, SerialNumber=6
      [    2.794500] usb 5-1: Product: USB 10/100/1000 LAN
      [    2.794977] usb 5-1: Manufacturer: Realtek
      [    2.795358] usb 5-1: SerialNumber: 000000000000
      [    2.825768] mmc_host mmc0: Bus speed (slot 0) = 150000000Hz (slot req 150000000Hz, actual 150000000HZ div = 0)
      [    4.001078] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 273
      [    4.001807] mmc0: new ultra high speed SDR104 SDHC card at address aaaa
      [    4.004620] mmcblk0: mmc0:aaaa SL16G 14.8 GiB 
      [    4.010938]  mmcblk0: p1 p2
      [    7.805678] EXT4-fs (mmcblk0p2): mounted filesystem without journal. Opts: (null)
      [    8.260891] systemd[1]: System time before build time, advancing clock.
      [    8.376572] systemd[1]: systemd 245.4-4ubuntu3 running in system mode. (+PAM +AUDIT +SELINUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +XZ +LZ4 +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=hybrid)
      [    8.380172] systemd[1]: Detected architecture arm64.
      [    8.428237] systemd[1]: Set hostname to <nanopi-r2s>.
      [    8.921318] systemd[1]: /lib/systemd/system/dbus.socket:5: ListenStream= references a path below legacy directory /var/run/, updating /var/run/dbus/system_bus_socket → /run/dbus/system_bus_socket; please update the unit file accordingly.
      [    9.041904] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.046878] systemd[1]: Created slice system-modprobe.slice.
      [    9.062951] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.065296] systemd[1]: Created slice system-serial\x2dgetty.slice.
      [    9.075023] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.077439] systemd[1]: Created slice system-systemd\x2dfsck.slice.
      [    9.088991] systemd[1]: Created slice User and Session Slice.
      [    9.099487] systemd[1]: Started Dispatch Password Requests to Console Directory Watch.
      [    9.111428] systemd[1]: Started Forward Password Requests to Wall Directory Watch.
      [    9.124174] systemd[1]: Set up automount Arbitrary Executable File Formats File System Automount Point.
      [    9.135177] systemd[1]: Reached target Local Encrypted Volumes.
      [    9.147149] systemd[1]: Reached target Paths.
      [    9.159126] systemd[1]: Reached target Remote File Systems.
      [    9.171044] systemd[1]: Reached target Slices.
      [    9.183107] systemd[1]: Reached target Swap.
      [    9.196232] systemd[1]: Listening on Syslog Socket.
      [    9.208030] systemd[1]: Listening on fsck to fsckd communication Socket.
      [    9.219613] systemd[1]: Listening on initctl Compatibility Named Pipe.
      [    9.232634] systemd[1]: Listening on Journal Audit Socket.
      [    9.243954] systemd[1]: Listening on Journal Socket (/dev/log).
      [    9.256175] systemd[1]: Listening on Journal Socket.
      [    9.268273] systemd[1]: Listening on udev Control Socket.
      [    9.279748] systemd[1]: Listening on udev Kernel Socket.
      [    9.298792] systemd[1]: Mounting Huge Pages File System...
      [    9.321641] systemd[1]: Mounting POSIX Message Queue File System...
      [    9.344397] systemd[1]: Mounting Kernel Debug File System...
      [    9.365755] systemd[1]: Mounting Kernel Trace File System...
      [    9.392221] systemd[1]: Starting Journal Service...
      [    9.411275] systemd[1]: Starting Set the console keyboard layout...
      [    9.432026] systemd[1]: Starting Create list of static device nodes for the current kernel...
      [    9.443475] systemd[1]: Condition check resulted in Load Kernel Module drm being skipped.
      [    9.449242] systemd[1]: Condition check resulted in Set Up Additional Binary Formats being skipped.
      [    9.450435] systemd[1]: Condition check resulted in File System Check on Root Device being skipped.
      [    9.462228] systemd[1]: Starting Load Kernel Modules...
      [    9.481855] systemd[1]: Starting Remount Root and Kernel File Systems...
      [    9.503305] systemd[1]: Starting udev Coldplug all Devices...
      [    9.536760] systemd[1]: Mounted Huge Pages File System.
      [    9.547287] EXT4-fs (mmcblk0p2): re-mounted. Opts: commit=600,errors=remount-ro
      [    9.558127] systemd[1]: Mounted POSIX Message Queue File System.
      [    9.572261] systemd[1]: Mounted Kernel Debug File System.
      [    9.588256] systemd[1]: Mounted Kernel Trace File System.
      [    9.603789] systemd[1]: Finished Create list of static device nodes for the current kernel.
      [    9.620692] systemd[1]: Finished Load Kernel Modules.
      [    9.635685] systemd[1]: Finished Remount Root and Kernel File Systems.
      [    9.660303] systemd[1]: Mounting FUSE Control File System...
      [    9.671590] systemd[1]: Mounting Kernel Configuration File System...
      [    9.694062] systemd[1]: Condition check resulted in Rebuild Hardware Database being skipped.
      [    9.695237] systemd[1]: Condition check resulted in Platform Persistent Storage Archival being skipped.
      [    9.702764] systemd[1]: Starting Load/Save Random Seed...
      [    9.711816] systemd[1]: Starting Apply Kernel Variables...
      [    9.743777] systemd[1]: Starting Create System Users...
      [    9.752789] systemd[1]: Mounted FUSE Control File System.
      [    9.761535] systemd[1]: Mounted Kernel Configuration File System.
      [    9.808264] systemd[1]: Finished Set the console keyboard layout.
      [    9.836371] systemd[1]: Finished Apply Kernel Variables.
      [    9.860923] systemd[1]: Finished Create System Users.
      [    9.878189] systemd[1]: Starting Create Static Device Nodes in /dev...
      [    9.947778] systemd[1]: Finished Create Static Device Nodes in /dev.
      [    9.960246] systemd[1]: Reached target Local File Systems (Pre).
      [    9.977749] systemd[1]: Starting udev Kernel Device Manager...
      [    9.996128] systemd[1]: Finished udev Coldplug all Devices.
      [   10.019522] systemd[1]: Starting Helper to synchronize boot up for ifupdown...
      [   10.121478] systemd[1]: Started udev Kernel Device Manager.
      [   10.425757] systemd[1]: Found device /dev/ttyS2.
      [   10.545439] systemd[1]: Started Journal Service.
      [   10.614944] systemd-journald[293]: Received client request to flush runtime journal.
      [   10.928259] usbcore: registered new interface driver r8152
      [   11.015246] EXT4-fs (mmcblk0p1): mounted filesystem with ordered data mode. Opts: (null)
      [   11.015312] ext4 filesystem being mounted at /boot supports timestamps until 2038 (0x7fffffff)
      [   11.113888] usb 5-1: reset SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [   11.150432] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Invalid ether addr 00:00:00:00:00:00
      [   11.151389] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether addr 42:f0:63:81:c7:d9
      [   12.241314] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 273
      [   12.276335] r8152 5-1:1.0: load rtl8153b-2 v1 10/23/19 successfully
      [   12.308650] r8152 5-1:1.0 eth1: v1.11.11
      [   12.482777] rk_gmac-dwmac ff540000.ethernet eth0: PHY [stmmac-0:00] driver [RTL8211E Gigabit Ethernet] (irq=POLL)
      [   12.518760] rk_gmac-dwmac ff540000.ethernet eth0: No Safety Features support found
      [   12.518794] rk_gmac-dwmac ff540000.ethernet eth0: PTP not supported by HW
      [   12.518811] rk_gmac-dwmac ff540000.ethernet eth0: configuring for phy/rgmii link mode
      [   12.738745] random: crng init done
      [   12.738761] random: 7 urandom warning(s) missed due to ratelimiting
      [   16.607624] rk_gmac-dwmac ff540000.ethernet eth0: Link is Up - 1Gbps/Full - flow control rx/tx
      [   16.607725] IPv6: ADDRCONF(NETDEV_CHANGE): eth0: link becomes ready
