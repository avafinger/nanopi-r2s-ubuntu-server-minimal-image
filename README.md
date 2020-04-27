# Nanopi-r2s-ubuntu-server-minimal-image

Ubuntu 19.10 Server for NanoPi R2S

This is the base Image for a small router, based on Kernel 5.4.25 and up for the NanoPi R2S

Release with Kernel version:

* v0.1 - Kernel 5.4.25

* v0.2 - Kernel 5.4.27

* v0.3 - Kernel 5.4.28

* v0.4 - Kernel 5.6.2

* v0.5 - Kernel 5.6.5

* v0.5f - fix root owner (/) on Ubuntu 20.04 LTS

* v0.6 - Kernel 5.6.7 - Ubuntu 20.04 LTS Server

* v0.6k - Kernel 5.6.7

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

* v0.1 - Ubuntu 19.10 Server NanoPi R2S

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.1


* v0.2 - Mini Router NanoPi R2S

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

* v0.3 - Mini Router NanoPi R2S with eth-monitor

Kernel updated to 5.4.28 with eth-monitor to display the eth status for the WAN and LAN interface.
When the WAN is up, the WAN led will be ON, when down, WAN led will be OFF.

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.3

* v0.4  - Mini Router NanoPi R2S with eth-monitor

Kernel updated to 5.6.2 with eth-monitor to display the eth status for the WAN and LAN interface.
If WAN is up, the WAN led is ON, if down, WAN led is OFF. Same for the LAN interface.

eth-monitor runs as service. You can stop, start or see the status of the service.

      sudo systemctl status eth-monitor.service
      sudo systemctl stop eth-monitor.service
      sudo systemctl start eth-monitor.service
      

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.4


* v0.5 - Ubuntu 20.04 LTS Server with Kernel 5.6.5 (Experimental)

Our mini router is kind of slow on the iptable NAT routing/fowarding and i can't find a way to optimize it or don't know how to do it. For this reason we will try the Ubuntu Beta version and see what we can get, all from scratch.
In my experiments, the routing and forwarding  is 8x slower than using the Gigabit port directly, maybe the NAT rules are overkill somewhere.

Add Initial support for rtl8822bu with Ubuntu Focal, the smallest Image size i could get, just for evaluation on RK3328 boards.

**Ubuntu Focal 20.04 LTS Server**

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.5


* v0.5a -Kernel 5.6.5

**Fix** DTB file name after install Kenrle 5.6.5 **before you reboot**


* v0.5f - Fix

 Fix root owner:
 
    sudo chown root:root /

* v0.6k - Kernel 5.6.7

* v0.6 - Ubuntu 20.04 LTS Server with Kernel 5.6.7

Ubuntu 20.04 LTS Server with kernel update and minor fix.

**Boot behaviour**

When you turn ON the board, the 3 leds will go ON for a few seconds and later WAN and LAN leds will show the status link.

# Latest Kernel - NanoPi R2S mini router - Ubuntu 19.10

Linux nanopi-r2s 5.6.1 #2 SMP PREEMPT Thu Apr 2 19:50:55 -03 2020 aarch64 aarch64 aarch64 GNU/Linux

# Status

* eth0 (ok)
* eth1 (ok)
* DVFS (ok)
* eth link status monitoring (ok)

# Cpu / Kernel Health

Checking the board health (manually)

      cat /sys/devices/virtual/thermal/thermal_zone0/temp
      38181
      cat /sys/devices/system/cpu/cpufreq/policy0/cpuinfo_cur_freq 
      408000
      cat /sys/devices/platform/ff160000.i2c/i2c-1/1-0018/regulator/regulator.8/microvolts 
      950000


# Interface monitoring

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

# htop 2.2.2

Monitor the health of NanoPi R2S with htop.

* Install

        wget https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/htop_2.2.2-1_arm64.deb
        sudo dpkg -i htop_2.2.2-1_arm64.deb 

![NanoPi R2S htop](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/NanoPi-R2S.png)

# Testing USB Realtek 8152

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

# Reading gpio-keys button

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

# ChangeLog

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

# BootLog

      [    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
      [    0.000000] Linux version 5.6.7 (ubuntu@nanopi-r2s) (gcc version 9.2.1 20191008 (Ubuntu 9.2.1-9ubuntu2)) #1 SMP PREEMPT Sun Apr 26 12:55:25 UTC 2020
      [    0.000000] Machine model: FriendlyElec NanoPi R2S
      [    0.000000] efi: Getting EFI parameters from FDT:
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
      [    0.000000] percpu: Embedded 32 pages/cpu s90152 r8192 d32728 u131072
      [    0.000000] pcpu-alloc: s90152 r8192 d32728 u131072 alloc=32*4096
      [    0.000000] pcpu-alloc: [0] 0 [0] 1 [0] 2 [0] 3 
      [    0.000000] Detected VIPT I-cache on CPU0
      [    0.000000] CPU features: detected: ARM erratum 845719
      [    0.000000] Built 1 zonelists, mobility grouping on.  Total pages: 257544
      [    0.000000] Kernel command line: earlyprintk root=/dev/mmcblk0p2 rw rootfstype=ext4 rootwait fsck.repair=yes panic=10 no_console_suspend consoleblank=0
      [    0.000000] Dentry cache hash table entries: 131072 (order: 8, 1048576 bytes, linear)
      [    0.000000] Inode-cache hash table entries: 65536 (order: 7, 524288 bytes, linear)
      [    0.000000] mem auto-init: stack:off, heap alloc:off, heap free:off
      [    0.000000] Memory: 986684K/1046528K available (12668K kernel code, 1714K rwdata, 5028K rodata, 1344K init, 793K bss, 43460K reserved, 16384K cma-reserved)
      [    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
      [    0.000000] ftrace: allocating 43467 entries in 170 pages
      [    0.000000] ftrace: allocated 170 pages with 4 groups
      [    0.000000] rcu: Preemptible hierarchical RCU implementation.
      [    0.000000] rcu: 	RCU restricting CPUs from NR_CPUS=8 to nr_cpu_ids=4.
      [    0.000000] 	Tasks RCU enabled.
      [    0.000000] rcu: RCU calculated value of scheduler-enlistment delay is 25 jiffies.
      [    0.000000] rcu: Adjusting geometry for rcu_fanout_leaf=16, nr_cpu_ids=4
      [    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
      [    0.000000] GIC: Using split EOI/Deactivate mode
      [    0.000000] random: get_random_bytes called from start_kernel+0x310/0x494 with crng_init=0
      [    0.000000] arch_timer: cp15 timer(s) running at 24.00MHz (phys).
      [    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles: 0x588fe9dc0, max_idle_ns: 440795202592 ns
      [    0.000009] sched_clock: 56 bits at 24MHz, resolution 41ns, wraps every 4398046511097ns
      [    0.000853] Console: colour dummy device 80x25
      [    0.001510] printk: console [tty0] enabled
      [    0.001582] Calibrating delay loop (skipped), value calculated using timer frequency.. 48.00 BogoMIPS (lpj=96000)
      [    0.001633] pid_max: default: 32768 minimum: 301
      [    0.001854] LSM: Security Framework initializing
      [    0.001992] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.002035] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.035869] rcu: Hierarchical SRCU implementation.
      [    0.047169] EFI services will not be available.
      [    0.056011] smp: Bringing up secondary CPUs ...
      [    0.088331] Detected VIPT I-cache on CPU1
      [    0.088424] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
      [    0.120491] Detected VIPT I-cache on CPU2
      [    0.120579] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
      [    0.152625] Detected VIPT I-cache on CPU3
      [    0.152708] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
      [    0.152920] smp: Brought up 1 node, 4 CPUs
      [    0.153068] SMP: Total of 4 processors activated.
      [    0.153102] CPU features: detected: 32-bit EL0 Support
      [    0.153133] CPU features: detected: CRC32 instructions
      [    0.178968] CPU: All CPU(s) started at EL2
      [    0.179079] alternatives: patching kernel code
      [    0.181503] devtmpfs: initialized
      [    0.197842] Registered cp15_barrier emulation handler
      [    0.197905] Registered setend emulation handler
      [    0.198616] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
      [    0.198688] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
      [    0.200110] pinctrl core: initialized pinctrl subsystem
      [    0.201189] thermal_sys: Registered thermal governor 'fair_share'
      [    0.201198] thermal_sys: Registered thermal governor 'step_wise'
      [    0.201951] DMI not present or invalid.
      [    0.202955] NET: Registered protocol family 16
      [    0.206898] DMA: preallocated 256 KiB pool for atomic allocations
      [    0.206965] audit: initializing netlink subsys (disabled)
      [    0.207365] audit: type=2000 audit(0.204:1): state=initialized audit_enabled=0 res=1
      [    0.208721] cpuidle: using governor ladder
      [    0.208865] cpuidle: using governor menu
      [    0.209359] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
      [    0.209563] ASID allocator initialised with 65536 entries
      [    0.264809] HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
      [    0.264864] HugeTLB registered 32.0 MiB page size, pre-allocated 0 pages
      [    0.264896] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
      [    0.264926] HugeTLB registered 64.0 KiB page size, pre-allocated 0 pages
      [    0.271845] cryptd: max_cpu_qlen set to 1000
      [    0.296049] iommu: Default domain type: Translated 
      [    0.297938] SCSI subsystem initialized
      [    0.298400] libata version 3.00 loaded.
      [    0.298756] usbcore: registered new interface driver usbfs
      [    0.298861] usbcore: registered new interface driver hub
      [    0.299033] usbcore: registered new device driver usb
      [    0.299173] mc: Linux media interface: v0.10
      [    0.299240] videodev: Linux video capture interface: v2.00
      [    0.299331] pps_core: LinuxPPS API ver. 1 registered
      [    0.299358] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
      [    0.299422] PTP clock support registered
      [    0.300246] Advanced Linux Sound Architecture Driver Initialized.
      [    0.301421] Bluetooth: Core ver 2.22
      [    0.301533] NET: Registered protocol family 31
      [    0.301560] Bluetooth: HCI device and connection manager initialized
      [    0.301603] Bluetooth: HCI socket layer initialized
      [    0.301640] Bluetooth: L2CAP socket layer initialized
      [    0.301703] Bluetooth: SCO socket layer initialized
      [    0.301755] NetLabel: Initializing
      [    0.301777] NetLabel:  domain hash size = 128
      [    0.301805] NetLabel:  protocols = UNLABELED CIPSOv4 CALIPSO
      [    0.301935] NetLabel:  unlabeled traffic allowed by default
      [    0.303088] clocksource: Switched to clocksource arch_sys_counter
      [    1.884966] VFS: Disk quotas dquot_6.6.0
      [    1.885111] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
      [    1.885478] FS-Cache: Loaded
      [    1.900297] NET: Registered protocol family 2
      [    1.901340] tcp_listen_portaddr_hash hash table entries: 512 (order: 2, 20480 bytes, linear)
      [    1.901439] TCP established hash table entries: 8192 (order: 4, 65536 bytes, linear)
      [    1.901599] TCP bind hash table entries: 8192 (order: 6, 262144 bytes, linear)
      [    1.901968] TCP: Hash tables configured (established 8192 bind 8192)
      [    1.902251] UDP hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.902372] UDP-Lite hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.903179] NET: Registered protocol family 1
      [    1.904293] RPC: Registered named UNIX socket transport module.
      [    1.904342] RPC: Registered udp transport module.
      [    1.904369] RPC: Registered tcp transport module.
      [    1.904391] RPC: Registered tcp NFSv4.1 backchannel transport module.
      [    1.904443] PCI: CLS 0 bytes, default 64
      [    1.904824] Trying to unpack rootfs image as initramfs...
      [    1.987893] Freeing initrd memory: 1076K
      [    1.989584] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 counters available
      [    2.008313] Initialise system trusted keyrings
      [    2.008748] workingset: timestamp_bits=46 max_order=18 bucket_order=0
      [    2.023906] squashfs: version 4.0 (2009/01/31) Phillip Lougher
      [    2.024556] FS-Cache: Netfs 'nfs' registered for caching
      [    2.025603] NFS: Registering the id_resolver key type
      [    2.025681] Key type id_resolver registered
      [    2.025704] Key type id_legacy registered
      [    2.025748] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
      [    2.026157] fuse: init (API version 7.31)
      [    2.053039] Key type asymmetric registered
      [    2.053086] Asymmetric key parser 'x509' registered
      [    2.053220] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 247)
      [    2.053564] io scheduler mq-deadline registered
      [    2.053605] io scheduler kyber registered
      [    2.061350] rockchip-u3phy ff470000.usb3-phy: Rockchip u3phy initialized successfully
      [    2.067353] dma-pl330 ff1f0000.dmac: Loaded driver for PL330 DMAC-241330
      [    2.067405] dma-pl330 ff1f0000.dmac: 	DBUFF-128x8bytes Num_Chans-8 Num_Peri-20 Num_Events-16
      [    2.068385] Serial: 8250/16550 driver, 5 ports, IRQ sharing disabled
      [    2.071431] ff130000.serial: ttyS2 at MMIO 0xff130000 (irq = 12, base_baud = 1500000) is a 16550A
      [    2.142311] printk: console [ttyS2] enabled
      [    2.146567] rockchip-drm display-subsystem: [drm:rockchip_drm_platform_probe] *ERROR* No available vop found for display-subsystem.
      [    2.160027] brd: module loaded
      [    2.179552] loop: module loaded
      [    2.182827] libphy: Fixed MDIO Bus: probed
      [    2.184835] rk_gmac-dwmac ff540000.ethernet: IRQ eth_wake_irq not found
      [    2.185463] rk_gmac-dwmac ff540000.ethernet: IRQ eth_lpi not found
      [    2.186242] rk_gmac-dwmac ff540000.ethernet: PTP uses main clock
      [    2.186979] rk_gmac-dwmac ff540000.ethernet: clock input or output? (input).
      [    2.187672] rk_gmac-dwmac ff540000.ethernet: TX delay(0x24).
      [    2.188204] rk_gmac-dwmac ff540000.ethernet: RX delay(0x18).
      [    2.188744] rk_gmac-dwmac ff540000.ethernet: integrated PHY? (no).
      [    2.189440] rk_gmac-dwmac ff540000.ethernet: cannot get clock clk_mac_speed
      [    2.190081] rk_gmac-dwmac ff540000.ethernet: clock input from PHY
      [    2.195671] rk_gmac-dwmac ff540000.ethernet: init for RGMII
      [    2.196564] rk_gmac-dwmac ff540000.ethernet: User ID: 0x10, Synopsys ID: 0x35
      [    2.197236] rk_gmac-dwmac ff540000.ethernet: 	DWMAC1000
      [    2.197720] rk_gmac-dwmac ff540000.ethernet: DMA HW capability register supported
      [    2.198405] rk_gmac-dwmac ff540000.ethernet: RX Checksum Offload Engine supported
      [    2.199127] rk_gmac-dwmac ff540000.ethernet: COE Type 2
      [    2.199615] rk_gmac-dwmac ff540000.ethernet: TX Checksum insertion supported
      [    2.200255] rk_gmac-dwmac ff540000.ethernet: Wake-Up On Lan supported
      [    2.200904] rk_gmac-dwmac ff540000.ethernet: Normal descriptors
      [    2.201449] rk_gmac-dwmac ff540000.ethernet: Ring mode enabled
      [    2.201988] rk_gmac-dwmac ff540000.ethernet: Enable RX Mitigation via HW Watchdog Timer
      [    2.263111] libphy: stmmac: probed
      [    2.266683] PPP generic driver version 2.4.2
      [    2.267537] usbcore: registered new interface driver asix
      [    2.268129] usbcore: registered new interface driver ax88179_178a
      [    2.268741] usbcore: registered new interface driver cdc_ether
      [    2.269332] usbcore: registered new interface driver qmi_wwan
      [    2.272119] dwc3 ff600000.dwc3: Failed to get clk 'ref': -2
      [    2.272923] phy phy-ff470000.usb3-phy.2: u3phy u2 power on
      [    2.273471] phy phy-ff470000.usb3-phy.3: u3phy u3 power on
      [    2.275524] dwc2 ff580000.usb: ff580000.usb supply vusb_d not found, using dummy regulator
      [    2.276450] dwc2 ff580000.usb: ff580000.usb supply vusb_a not found, using dummy regulator
      [    2.407220] dwc2 ff580000.usb: EPs: 10, dedicated fifos, 972 entries in SPRAM
      [    2.408493] dwc2 ff580000.usb: DWC OTG Controller
      [    2.408985] dwc2 ff580000.usb: new USB bus registered, assigned bus number 1
      [    2.409695] dwc2 ff580000.usb: irq 29, io mem 0xff580000
      [    2.410521] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.411337] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.411997] usb usb1: Product: DWC OTG Controller
      [    2.412432] usb usb1: Manufacturer: Linux 5.6.7 dwc2_hsotg
      [    2.412942] usb usb1: SerialNumber: ff580000.usb
      [    2.414430] hub 1-0:1.0: USB hub found
      [    2.414856] hub 1-0:1.0: 1 port detected
      [    2.416577] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
      [    2.417218] ehci-pci: EHCI PCI platform driver
      [    2.417721] ehci-platform: EHCI generic platform driver
      [    2.420872] ehci-platform ff5c0000.usb: EHCI Host Controller
      [    2.421444] ehci-platform ff5c0000.usb: new USB bus registered, assigned bus number 2
      [    2.422394] ehci-platform ff5c0000.usb: irq 30, io mem 0xff5c0000
      [    2.435139] ehci-platform ff5c0000.usb: USB 2.0 started, EHCI 1.00
      [    2.436145] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.436912] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.437574] usb usb2: Product: EHCI Host Controller
      [    2.438023] usb usb2: Manufacturer: Linux 5.6.7 ehci_hcd
      [    2.438514] usb usb2: SerialNumber: ff5c0000.usb
      [    2.439952] hub 2-0:1.0: USB hub found
      [    2.440370] hub 2-0:1.0: 1 port detected
      [    2.441571] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
      [    2.442185] ohci-platform: OHCI generic platform driver
      [    2.443361] ohci-platform ff5d0000.usb: Generic Platform OHCI controller
      [    2.444027] ohci-platform ff5d0000.usb: new USB bus registered, assigned bus number 3
      [    2.444996] ohci-platform ff5d0000.usb: irq 31, io mem 0xff5d0000
      [    2.507537] usb usb3: New USB device found, idVendor=1d6b, idProduct=0001, bcdDevice= 5.06
      [    2.508307] usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.508981] usb usb3: Product: Generic Platform OHCI controller
      [    2.509522] usb usb3: Manufacturer: Linux 5.6.7 ohci_hcd
      [    2.510013] usb usb3: SerialNumber: ff5d0000.usb
      [    2.511456] hub 3-0:1.0: USB hub found
      [    2.511878] hub 3-0:1.0: 1 port detected
      [    2.513940] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.514496] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 4
      [    2.515530] xhci-hcd xhci-hcd.0.auto: hcc params 0x0220fe64 hci version 0x110 quirks 0x0000000002010010
      [    2.516500] xhci-hcd xhci-hcd.0.auto: irq 166, io mem 0xff600000
      [    2.517869] usb usb4: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.518638] usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.519367] usb usb4: Product: xHCI Host Controller
      [    2.519819] usb usb4: Manufacturer: Linux 5.6.7 xhci-hcd
      [    2.520316] usb usb4: SerialNumber: xhci-hcd.0.auto
      [    2.521798] hub 4-0:1.0: USB hub found
      [    2.522224] hub 4-0:1.0: 1 port detected
      [    2.523284] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.523823] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 5
      [    2.524545] xhci-hcd xhci-hcd.0.auto: Host supports USB 3.0 SuperSpeed
      [    2.525268] usb usb5: We don't know the algorithms for LPM for this host, disabling LPM.
      [    2.526238] usb usb5: New USB device found, idVendor=1d6b, idProduct=0003, bcdDevice= 5.06
      [    2.526992] usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.527697] usb usb5: Product: xHCI Host Controller
      [    2.528147] usb usb5: Manufacturer: Linux 5.6.7 xhci-hcd
      [    2.528638] usb usb5: SerialNumber: xhci-hcd.0.auto
      [    2.530073] hub 5-0:1.0: USB hub found
      [    2.530519] hub 5-0:1.0: 1 port detected
      [    2.531834] usbcore: registered new interface driver cdc_acm
      [    2.532370] cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
      [    2.533171] usbcore: registered new interface driver cdc_wdm
      [    2.533762] usbcore: registered new interface driver uas
      [    2.534465] usbcore: registered new interface driver usb-storage
      [    2.535231] usbcore: registered new interface driver usbserial_generic
      [    2.535863] usbserial: USB Serial support registered for generic
      [    2.536512] usbcore: registered new interface driver ch341
      [    2.537042] usbserial: USB Serial support registered for ch341-uart
      [    2.537692] usbcore: registered new interface driver cp210x
      [    2.538238] usbserial: USB Serial support registered for cp210x
      [    2.538925] usbcore: registered new interface driver ftdi_sio
      [    2.539519] usbserial: USB Serial support registered for FTDI USB Serial Device
      [    2.540586] usbcore: registered new interface driver option
      [    2.541136] usbserial: USB Serial support registered for GSM modem (1-port)
      [    2.542258] usbcore: registered new interface driver pl2303
      [    2.542811] usbserial: USB Serial support registered for pl2303
      [    2.543522] usbcore: registered new interface driver qcserial
      [    2.544086] usbserial: USB Serial support registered for Qualcomm USB modem
      [    2.545545] mousedev: PS/2 mouse device common for all mice
      [    2.547048] i2c /dev entries driver
      [    2.551485] rk808 1-0018: chip id: 0x8050
      [    2.560708] rk808-regulator rk808-regulator: there is no dvs0 gpio
      [    2.561334] rk808-regulator rk808-regulator: there is no dvs1 gpio
      [    2.562025] DCDC_REG1: supplied by vcc_sys
      [    2.565507] DCDC_REG2: supplied by vcc_sys
      [    2.567856] DCDC_REG3: supplied by vcc_sys
      [    2.568731] DCDC_REG4: supplied by vcc_sys
      [    2.570688] LDO_REG1: supplied by vcc_io
      [    2.574544] LDO_REG2: supplied by vcc_io
      [    2.578410] LDO_REG3: supplied by vcc_io
      [    2.592468] rk808-rtc rk808-rtc: registered as rtc0
      [    2.595220] input: rk805 pwrkey as /devices/platform/ff160000.i2c/i2c-1/1-0018/rk805-pwrkey/input/input0
      [    2.597282] IR NEC protocol handler initialized
      [    2.602834] rockchip-thermal ff250000.tsadc: Missing tshut mode property, using default (cru)
      [    2.603705] rockchip-thermal ff250000.tsadc: Missing tshut-polarity property, using default (low)
      [    2.607134] device-mapper: uevent: version 1.0.3
      [    2.608160] device-mapper: ioctl: 4.42.0-ioctl (2020-02-27) initialised: dm-devel@redhat.com
      [    2.614261] sdhci: Secure Digital Host Controller Interface driver
      [    2.614851] sdhci: Copyright(c) Pierre Ossman
      [    2.615406] Synopsys Designware Multimedia Card Interface Driver
      [    2.617210] dwmmc_rockchip ff500000.dwmmc: IDMAC supports 32-bit address mode.
      [    2.617926] dwmmc_rockchip ff500000.dwmmc: Using internal DMA controller.
      [    2.618557] dwmmc_rockchip ff500000.dwmmc: Version ID is 270a
      [    2.619245] dwmmc_rockchip ff500000.dwmmc: DW MMC controller at irq 27,32 bit host data width,256 deep fifo
      [    2.620235] vcc_sd: supplied by vcc_io
      [    2.639401] mmc_host mmc0: Bus speed (slot 0) = 400000Hz (slot req 400000Hz, actual 400000HZ div = 0)
      [    2.653611] sdhci-pltfm: SDHCI platform and OF driver helper
      [    2.656263] ledtrig-cpu: registered to indicate activity on CPUs
      [    2.657486] hid: raw HID events driver (C) Jiri Kosina
      [    2.658618] usbcore: registered new interface driver usbhid
      [    2.659184] usbhid: USB HID core driver
      [    2.665244] drop_monitor: Initializing network drop monitor service
      [    2.666281] Initializing XFRM netlink socket
      [    2.667910] NET: Registered protocol family 10
      [    2.670842] Segment Routing with IPv6
      [    2.674679] bpfilter: Loaded bpfilter_umh pid 233
      [    2.675819] NET: Registered protocol family 17
      [    2.676799] Bluetooth: RFCOMM TTY layer initialized
      [    2.677291] Bluetooth: RFCOMM socket layer initialized
      [    2.677844] Bluetooth: RFCOMM ver 1.11
      [    2.678216] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
      [    2.678770] Bluetooth: HIDP socket layer initialized
      [    2.679481] Key type dns_resolver registered
      [    2.680962] registered taskstats version 1
      [    2.681370] Loading compiled-in X.509 certificates
      [    2.681976] Key type ._fscrypt registered
      [    2.682357] Key type .fscrypt registered
      [    2.682720] Key type fscrypt-provisioning registered
      [    2.721790] friendlyelec-board board: Serial		: 37cd0f845b1d0156
      [    2.724553] input: gpio-keys as /devices/platform/gpio-keys/input/input1
      [    2.728282] rk808-rtc rk808-rtc: setting system clock to 2016-01-21T08:50:08 UTC (1453366208)
      [    2.730690] random: fast init done
      [    2.730790] ALSA device list:
      [    2.731319]   No soundcards found.
      [    2.736205] Freeing unused kernel memory: 1344K
      [    2.736766] Run /init as init process
      [    2.737107]   with arguments:
      [    2.737111]     /init
      [    2.737115]     earlyprintk
      [    2.737118]   with environment:
      [    2.737123]     HOME=/
      [    2.737129]     TERM=linux
      [    2.871301] usb 5-1: new SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [    2.892501] usb 5-1: New USB device found, idVendor=0bda, idProduct=8153, bcdDevice=31.00
      [    2.893260] usb 5-1: New USB device strings: Mfr=1, Product=2, SerialNumber=6
      [    2.893905] usb 5-1: Product: USB 10/100/1000 LAN
      [    2.894332] usb 5-1: Manufacturer: Realtek
      [    2.894708] usb 5-1: SerialNumber: 000000000000
      [    2.898374] mmc_host mmc0: Bus speed (slot 0) = 150000000Hz (slot req 150000000Hz, actual 150000000HZ div = 0)
      [    4.064948] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 273
      [    4.065665] mmc0: new ultra high speed SDR104 SDHC card at address aaaa
      [    4.068276] mmcblk0: mmc0:aaaa SL16G 14.8 GiB 
      [    4.073773]  mmcblk0: p1 p2
      [    7.875476] EXT4-fs (mmcblk0p2): mounted filesystem without journal. Opts: (null)
      [    8.335831] systemd[1]: System time before build time, advancing clock.
      [    8.462087] systemd[1]: systemd 245.4-4ubuntu3 running in system mode. (+PAM +AUDIT +SELINUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +XZ +LZ4 +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=hybrid)
      [    8.465822] systemd[1]: Detected architecture arm64.
      [    8.509287] systemd[1]: Set hostname to <nanopi-r2s>.
      [    8.607309] phy phy-ff450000.syscon:usb2-phy@100.0: charger = USB_DCP_CHARGER
      [    8.995205] systemd[1]: /lib/systemd/system/dbus.socket:5: ListenStream= references a path below legacy directory /var/run/, updating /var/run/dbus/system_bus_socket → /run/dbus/system_bus_socket; please update the unit file accordingly.
      [    9.114017] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.118839] systemd[1]: Created slice system-modprobe.slice.
      [    9.120684] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.122919] systemd[1]: Created slice system-serial\x2dgetty.slice.
      [    9.135507] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.137867] systemd[1]: Created slice system-systemd\x2dfsck.slice.
      [    9.153309] systemd[1]: Created slice User and Session Slice.
      [    9.155478] systemd[1]: Started Dispatch Password Requests to Console Directory Watch.
      [    9.167806] systemd[1]: Started Forward Password Requests to Wall Directory Watch.
      [    9.180427] systemd[1]: Set up automount Arbitrary Executable File Formats File System Automount Point.
      [    9.191527] systemd[1]: Reached target Local Encrypted Volumes.
      [    9.193394] systemd[1]: Reached target Paths.
      [    9.203391] systemd[1]: Reached target Remote File Systems.
      [    9.205032] systemd[1]: Reached target Slices.
      [    9.215431] systemd[1]: Reached target Swap.
      [    9.228196] systemd[1]: Listening on Syslog Socket.
      [    9.240075] systemd[1]: Listening on fsck to fsckd communication Socket.
      [    9.251873] systemd[1]: Listening on initctl Compatibility Named Pipe.
      [    9.264674] systemd[1]: Listening on Journal Audit Socket.
      [    9.267369] systemd[1]: Listening on Journal Socket (/dev/log).
      [    9.270078] systemd[1]: Listening on Journal Socket.
      [    9.284476] systemd[1]: Listening on udev Control Socket.
      [    9.286824] systemd[1]: Listening on udev Kernel Socket.
      [    9.295682] systemd[1]: Mounting Huge Pages File System...
      [    9.315799] systemd[1]: Mounting POSIX Message Queue File System...
      [    9.326613] systemd[1]: Mounting Kernel Debug File System...
      [    9.337285] systemd[1]: Mounting Kernel Trace File System...
      [    9.350529] systemd[1]: Starting Journal Service...
      [    9.370400] systemd[1]: Starting Set the console keyboard layout...
      [    9.390217] systemd[1]: Starting Create list of static device nodes for the current kernel...
      [    9.392670] systemd[1]: Condition check resulted in Load Kernel Module drm being skipped.
      [    9.397469] systemd[1]: Condition check resulted in Set Up Additional Binary Formats being skipped.
      [    9.398661] systemd[1]: Condition check resulted in File System Check on Root Device being skipped.
      [    9.409893] systemd[1]: Starting Load Kernel Modules...
      [    9.418778] systemd[1]: Starting Remount Root and Kernel File Systems...
      [    9.446933] systemd[1]: Starting udev Coldplug all Devices...
      [    9.462044] systemd[1]: Mounted Huge Pages File System.
      [    9.465191] systemd[1]: Mounted POSIX Message Queue File System.
      [    9.468642] systemd[1]: Mounted Kernel Debug File System.
      [    9.469950] EXT4-fs (mmcblk0p2): re-mounted. Opts: commit=600,errors=remount-ro
      [    9.480591] systemd[1]: Mounted Kernel Trace File System.
      [    9.487668] systemd[1]: Finished Create list of static device nodes for the current kernel.
      [    9.504358] systemd[1]: Finished Load Kernel Modules.
      [    9.510380] systemd[1]: Finished Remount Root and Kernel File Systems.
      [    9.521272] systemd[1]: Mounting FUSE Control File System...
      [    9.539861] systemd[1]: Mounting Kernel Configuration File System...
      [    9.561922] systemd[1]: Condition check resulted in Rebuild Hardware Database being skipped.
      [    9.563214] systemd[1]: Condition check resulted in Platform Persistent Storage Archival being skipped.
      [    9.570185] systemd[1]: Starting Load/Save Random Seed...
      [    9.593423] systemd[1]: Starting Apply Kernel Variables...
      [    9.620302] systemd[1]: Starting Create System Users...
      [    9.636648] systemd[1]: Mounted FUSE Control File System.
      [    9.648797] systemd[1]: Mounted Kernel Configuration File System.
      [    9.709035] systemd[1]: Finished Create System Users.
      [    9.719878] systemd[1]: Starting Create Static Device Nodes in /dev...
      [    9.751952] systemd[1]: Finished Apply Kernel Variables.
      [    9.765834] systemd[1]: Finished Set the console keyboard layout.
      [    9.792323] systemd[1]: Finished Create Static Device Nodes in /dev.
      [    9.794628] systemd[1]: Reached target Local File Systems (Pre).
      [    9.815396] systemd[1]: Starting udev Kernel Device Manager...
      [    9.928909] systemd[1]: Finished udev Coldplug all Devices.
      [    9.947699] systemd[1]: Starting Helper to synchronize boot up for ifupdown...
      [    9.966061] systemd[1]: Started udev Kernel Device Manager.
      [   10.250562] systemd[1]: Found device /dev/ttyS2.
      [   10.453675] systemd[1]: Started Journal Service.
      [   11.602105] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 273
      [   11.643802] systemd-journald[292]: Received client request to flush runtime journal.
      [   11.795434] usbcore: registered new interface driver r8152
      [   11.852561] random: crng init done
      [   11.852576] random: 7 urandom warning(s) missed due to ratelimiting
      [   11.965058] EXT4-fs (mmcblk0p1): mounted filesystem with ordered data mode. Opts: (null)
      [   11.965127] ext4 filesystem being mounted at /boot supports timestamps until 2038 (0x7fffffff)
      [   11.967314] usb 5-1: reset SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [   12.005459] r8152 5-1:1.0: Direct firmware load for rtl_nic/rtl8153b-2.fw
      [   12.006202] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Invalid ether addr 00:00:00:00:00:00
      [   12.007299] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether addr 16:cf:35:c2:5b:d8
      [   12.044875] r8152 5-1:1.0: load rtl8153b-2 v1 10/23/19 successfully
      [   12.081172] r8152 5-1:1.0 eth1: v1.11.11
      [   12.218011] rk_gmac-dwmac ff540000.ethernet eth0: PHY [stmmac-0:00] driver [RTL8211E Gigabit Ethernet] (irq=POLL)
      [   12.230306] rk_gmac-dwmac ff540000.ethernet eth0: No Safety Features support found
      [   12.230337] rk_gmac-dwmac ff540000.ethernet eth0: PTP not supported by HW
      [   12.230354] rk_gmac-dwmac ff540000.ethernet eth0: configuring for phy/rgmii link mode
      [   17.343777] rk_gmac-dwmac ff540000.ethernet eth0: Link is Up - 1Gbps/Full - flow control rx/tx
      [   17.343848] IPv6: ADDRCONF(NETDEV_CHANGE): eth0: link becomes ready
