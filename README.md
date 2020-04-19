# Nanopi-r2s-ubuntu-server-minimal-image

Ubuntu 19.10 Server for NanoPi R2S

This is the base Image for a small router, based on Kernel 5.4.25 and up for the NanoPi R2S

Release with Kernel version:

* v0.1 - Kernel 5.4.25

* v0.2 - Kernel 5.4.27

* v0.3 - Kernel 5.4.28

* v0.4 - Kernel 5.6.2

* v0.5 - Kernel 5.6.5


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


**Boot behaviour**

When you turn ON the board, the 3 leds will go ON for a few seconds and later WAN and LAN leds will show the status link.

# Latest Kernel - NanoPi R2S mini router - Ubuntu 19.10

Linux nanopi-r2s 5.6.1 #2 SMP PREEMPT Thu Apr 2 19:50:55 -03 2020 aarch64 aarch64 aarch64 GNU/Linux

# Status

* eth0 (ok)
* eth1 (ok)
* DVFS (seems ok)
* eth link status monitoring (ok?)

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

# ChangeLog

* add Kernel 5.4.25 (initial commit)
* add support for rtl8821cu usb (v0.2)
* add Kernel 5.4.27 (v0.2)
* add NanoPi R2S mini router (v0.2)
* add Kernel 5.4.28 (v0.3)
* add NanoPi R2S mini router with eth-monitor (v0.3)
* add Kernel 5.6.2 (v0.4)
* add Kernel 5.6.5 and rtl8822bu (v0.5)

# BootLog

      [    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
      [    0.000000] Linux version 5.6.5 (ubuntu@nanopi-r2s) (gcc version 9.2.1 201910
      08 (Ubuntu 9.2.1-9ubuntu2)) #1 SMP PREEMPT Sat Apr 18 01:51:49 UTC 2020
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
      [    0.000000] Kernel command line: earlyprintk root=/dev/mmcblk0p2 rw rootfstyp
      e=ext4 rootwait fsck.repair=yes panic=10 no_console_suspend consoleblank=0
      [    0.000000] Dentry cache hash table entries: 131072 (order: 8, 1048576 bytes,
       linear)
      [    0.000000] Inode-cache hash table entries: 65536 (order: 7, 524288 bytes, li
      near)
      [    0.000000] mem auto-init: stack:off, heap alloc:off, heap free:off
      [    0.000000] Memory: 986684K/1046528K available (12668K kernel code, 1714K rwd
      ata, 5028K rodata, 1344K init, 793K bss, 43460K reserved, 16384K cma-reserved)
      [    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
      [    0.000000] ftrace: allocating 43464 entries in 170 pages
      [    0.000000] ftrace: allocated 170 pages with 4 groups
      [    0.000000] rcu: Preemptible hierarchical RCU implementation.
      [    0.000000] rcu: 	RCU restricting CPUs from NR_CPUS=8 to nr_cpu_ids=4.
      [    0.000000] 	Tasks RCU enabled.
      [    0.000000] rcu: RCU calculated value of scheduler-enlistment delay is 25 jif
      fies.
      [    0.000000] rcu: Adjusting geometry for rcu_fanout_leaf=16, nr_cpu_ids=4
      [    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
      [    0.000000] GIC: Using split EOI/Deactivate mode
      [    0.000000] random: get_random_bytes called from start_kernel+0x310/0x494 wit
      h crng_init=0
      [    0.000000] arch_timer: cp15 timer(s) running at 24.00MHz (phys).
      [    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles:
       0x588fe9dc0, max_idle_ns: 440795202592 ns
      [    0.000009] sched_clock: 56 bits at 24MHz, resolution 41ns, wraps every 43980
      46511097ns
      [    0.000837] Console: colour dummy device 80x25
      [    0.001499] printk: console [tty0] enabled
      [    0.001574] Calibrating delay loop (skipped), value calculated using timer fr
      equency.. 48.00 BogoMIPS (lpj=96000)
      [    0.001620] pid_max: default: 32768 minimum: 301
      [    0.001836] LSM: Security Framework initializing
      [    0.001988] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes, line
      ar)
      [    0.002032] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes,
       linear)
      [    0.035859] rcu: Hierarchical SRCU implementation.
      [    0.047139] EFI services will not be available.
      [    0.056015] smp: Bringing up secondary CPUs ...
      [    0.088332] Detected VIPT I-cache on CPU1
      [    0.088422] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
      [    0.120483] Detected VIPT I-cache on CPU2
      [    0.120570] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
      [    0.152637] Detected VIPT I-cache on CPU3
      [    0.152718] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
      [    0.152938] smp: Brought up 1 node, 4 CPUs
      [    0.153086] SMP: Total of 4 processors activated.
      [    0.153119] CPU features: detected: 32-bit EL0 Support
      [    0.153151] CPU features: detected: CRC32 instructions
      [    0.178985] CPU: All CPU(s) started at EL2
      [    0.179098] alternatives: patching kernel code
      [    0.181535] devtmpfs: initialized
      [    0.198005] Registered cp15_barrier emulation handler
      [    0.198070] Registered setend emulation handler
      [    0.198795] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, ma
      x_idle_ns: 7645041785100000 ns
      [    0.198865] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
      [    0.200292] pinctrl core: initialized pinctrl subsystem
      [    0.201368] thermal_sys: Registered thermal governor 'fair_share'
      [    0.201374] thermal_sys: Registered thermal governor 'step_wise'
      [    0.202150] DMI not present or invalid.
      [    0.203164] NET: Registered protocol family 16
      [    0.206922] DMA: preallocated 256 KiB pool for atomic allocations
      [    0.206993] audit: initializing netlink subsys (disabled)
      [    0.207385] audit: type=2000 audit(0.204:1): state=initialized audit_enabled=
      0 res=1
      [    0.208786] cpuidle: using governor ladder
      [    0.208903] cpuidle: using governor menu
      [    0.209397] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
      [    0.209598] ASID allocator initialised with 65536 entries
      [    0.265977] HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
      [    0.266027] HugeTLB registered 32.0 MiB page size, pre-allocated 0 pages
      [    0.266058] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
      [    0.266088] HugeTLB registered 64.0 KiB page size, pre-allocated 0 pages
      [    0.272474] cryptd: max_cpu_qlen set to 1000
      [    0.296986] iommu: Default domain type: Translated 
      [    0.298829] SCSI subsystem initialized
      [    0.299314] libata version 3.00 loaded.
      [    0.299688] usbcore: registered new interface driver usbfs
      [    0.299815] usbcore: registered new interface driver hub
      [    0.299988] usbcore: registered new device driver usb
      [    0.300131] mc: Linux media interface: v0.10
      [    0.300205] videodev: Linux video capture interface: v2.00
      [    0.300299] pps_core: LinuxPPS API ver. 1 registered
      [    0.300330] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giome
      tti <giometti@linux.it>
      [    0.300384] PTP clock support registered
      [    0.301793] Advanced Linux Sound Architecture Driver Initialized.
      [    0.302941] Bluetooth: Core ver 2.22
      [    0.303060] NET: Registered protocol family 31
      [    0.303087] Bluetooth: HCI device and connection manager initialized
      [    0.303133] Bluetooth: HCI socket layer initialized
      [    0.303169] Bluetooth: L2CAP socket layer initialized
      [    0.303233] Bluetooth: SCO socket layer initialized
      [    0.303289] NetLabel: Initializing
      [    0.303312] NetLabel:  domain hash size = 128
      [    0.303335] NetLabel:  protocols = UNLABELED CIPSOv4 CALIPSO
      [    0.303463] NetLabel:  unlabeled traffic allowed by default
      [    0.304677] clocksource: Switched to clocksource arch_sys_counter
      [    1.891282] VFS: Disk quotas dquot_6.6.0
      [    1.891438] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
      [    1.891737] FS-Cache: Loaded
      [    1.906713] NET: Registered protocol family 2
      [    1.907729] tcp_listen_portaddr_hash hash table entries: 512 (order: 2, 20480
       bytes, linear)
      [    1.907832] TCP established hash table entries: 8192 (order: 4, 65536 bytes, 
      linear)
      [    1.907984] TCP bind hash table entries: 8192 (order: 6, 262144 bytes, linear
      )
      [    1.908351] TCP: Hash tables configured (established 8192 bind 8192)
      [    1.908633] UDP hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.908845] UDP-Lite hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.909559] NET: Registered protocol family 1
      [    1.910672] RPC: Registered named UNIX socket transport module.
      [    1.910716] RPC: Registered udp transport module.
      [    1.910743] RPC: Registered tcp transport module.
      [    1.910770] RPC: Registered tcp NFSv4.1 backchannel transport module.
      [    1.910816] PCI: CLS 0 bytes, default 64
      [    1.911191] Trying to unpack rootfs image as initramfs...
      [    1.994380] Freeing initrd memory: 1076K
      [    1.996110] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 counte
      rs available
      [    2.014722] Initialise system trusted keyrings
      [    2.015155] workingset: timestamp_bits=46 max_order=18 bucket_order=0
      [    2.030588] squashfs: version 4.0 (2009/01/31) Phillip Lougher
      [    2.031228] FS-Cache: Netfs 'nfs' registered for caching
      [    2.032312] NFS: Registering the id_resolver key type
      [    2.032389] Key type id_resolver registered
      [    2.032413] Key type id_legacy registered
      [    2.032458] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
      [    2.032972] fuse: init (API version 7.31)
      [    2.059671] Key type asymmetric registered
      [    2.059719] Asymmetric key parser 'x509' registered
      [    2.059848] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 2
      47)
      [    2.060195] io scheduler mq-deadline registered
      [    2.060236] io scheduler kyber registered
      [    2.068058] rockchip-u3phy ff470000.usb3-phy: Rockchip u3phy initialized succ
      essfully
      [    2.074057] dma-pl330 ff1f0000.dmac: Loaded driver for PL330 DMAC-241330
      [    2.074115] dma-pl330 ff1f0000.dmac: 	DBUFF-128x8bytes Num_Chans-8 Num
      _Peri-20 Num_Events-16
      [    2.075101] Serial: 8250/16550 driver, 5 ports, IRQ sharing disabled
      [    2.078184] ff130000.serial: ttyS2 at MMIO 0xff130000 (irq = 12, base_baud = 
      1500000) is a 16550A
      [    2.149020] printk: console [ttyS2] enabled
      [    2.153337] rockchip-drm display-subsystem: [drm:rockchip_drm_platform_probe]
       *ERROR* No available vop found for display-subsystem.
      [    2.167005] brd: module loaded
      [    2.186917] loop: module loaded
      [    2.190400] libphy: Fixed MDIO Bus: probed
      [    2.192384] rk_gmac-dwmac ff540000.ethernet: IRQ eth_wake_irq not found
      [    2.193091] rk_gmac-dwmac ff540000.ethernet: IRQ eth_lpi not found
      [    2.193883] rk_gmac-dwmac ff540000.ethernet: PTP uses main clock
      [    2.194638] rk_gmac-dwmac ff540000.ethernet: clock input or output? (input).
      [    2.195293] rk_gmac-dwmac ff540000.ethernet: TX delay(0x24).
      [    2.195823] rk_gmac-dwmac ff540000.ethernet: RX delay(0x18).
      [    2.196356] rk_gmac-dwmac ff540000.ethernet: integrated PHY? (no).
      [    2.197090] rk_gmac-dwmac ff540000.ethernet: cannot get clock clk_mac_speed
      [    2.197731] rk_gmac-dwmac ff540000.ethernet: clock input from PHY
      [    2.203338] rk_gmac-dwmac ff540000.ethernet: init for RGMII
      [    2.204252] rk_gmac-dwmac ff540000.ethernet: User ID: 0x10, Synopsys ID: 0x35
      [    2.204962] rk_gmac-dwmac ff540000.ethernet: 	DWMAC1000
      [    2.205451] rk_gmac-dwmac ff540000.ethernet: DMA HW capability register suppo
      rted
      [    2.206140] rk_gmac-dwmac ff540000.ethernet: RX Checksum Offload Engine suppo
      rted
      [    2.206826] rk_gmac-dwmac ff540000.ethernet: COE Type 2
      [    2.207306] rk_gmac-dwmac ff540000.ethernet: TX Checksum insertion supported
      [    2.207946] rk_gmac-dwmac ff540000.ethernet: Wake-Up On Lan supported
      [    2.208596] rk_gmac-dwmac ff540000.ethernet: Normal descriptors
      [    2.209160] rk_gmac-dwmac ff540000.ethernet: Ring mode enabled
      [    2.209702] rk_gmac-dwmac ff540000.ethernet: Enable RX Mitigation via HW Watc
      hdog Timer
      [    2.268696] libphy: stmmac: probed
      [    2.272157] PPP generic driver version 2.4.2
      [    2.273080] usbcore: registered new interface driver asix
      [    2.273660] usbcore: registered new interface driver ax88179_178a
      [    2.274268] usbcore: registered new interface driver cdc_ether
      [    2.274861] usbcore: registered new interface driver qmi_wwan
      [    2.277636] dwc3 ff600000.dwc3: Failed to get clk 'ref': -2
      [    2.278442] phy phy-ff470000.usb3-phy.2: u3phy u2 power on
      [    2.278989] phy phy-ff470000.usb3-phy.3: u3phy u3 power on
      [    2.281008] dwc2 ff580000.usb: ff580000.usb supply vusb_d not found, using du
      mmy regulator
      [    2.281948] dwc2 ff580000.usb: ff580000.usb supply vusb_a not found, using du
      mmy regulator
      [    2.412800] dwc2 ff580000.usb: EPs: 10, dedicated fifos, 972 entries in SPRAM
      [    2.414108] dwc2 ff580000.usb: DWC OTG Controller
      [    2.414599] dwc2 ff580000.usb: new USB bus registered, assigned bus number 1
      [    2.415293] dwc2 ff580000.usb: irq 29, io mem 0xff580000
      [    2.416077] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bc
      dDevice= 5.06
      [    2.416881] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=
      1
      [    2.417541] usb usb1: Product: DWC OTG Controller
      [    2.417976] usb usb1: Manufacturer: Linux 5.6.5 dwc2_hsotg
      [    2.418485] usb usb1: SerialNumber: ff580000.usb
      [    2.419980] hub 1-0:1.0: USB hub found
      [    2.420394] hub 1-0:1.0: 1 port detected
      [    2.422111] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
      [    2.422754] ehci-pci: EHCI PCI platform driver
      [    2.423253] ehci-platform: EHCI generic platform driver
      [    2.426457] ehci-platform ff5c0000.usb: EHCI Host Controller
      [    2.427027] ehci-platform ff5c0000.usb: new USB bus registered, assigned bus 
      number 2
      [    2.427963] ehci-platform ff5c0000.usb: irq 30, io mem 0xff5c0000
      [    2.440715] ehci-platform ff5c0000.usb: USB 2.0 started, EHCI 1.00
      [    2.441712] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002, bc
      dDevice= 5.06
      [    2.442479] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=
      1
      [    2.443139] usb usb2: Product: EHCI Host Controller
      [    2.443587] usb usb2: Manufacturer: Linux 5.6.5 ehci_hcd
      [    2.444081] usb usb2: SerialNumber: ff5c0000.usb
      [    2.445595] hub 2-0:1.0: USB hub found
      [    2.446015] hub 2-0:1.0: 1 port detected
      [    2.447209] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
      [    2.447830] ohci-platform: OHCI generic platform driver
      [    2.449001] ohci-platform ff5d0000.usb: Generic Platform OHCI controller
      [    2.449669] ohci-platform ff5d0000.usb: new USB bus registered, assigned bus 
      number 3
      [    2.450632] ohci-platform ff5d0000.usb: irq 31, io mem 0xff5d0000
      [    2.513042] usb usb3: New USB device found, idVendor=1d6b, idProduct=0001, bc
      dDevice= 5.06
      [    2.513808] usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=
      1
      [    2.514473] usb usb3: Product: Generic Platform OHCI controller
      [    2.515014] usb usb3: Manufacturer: Linux 5.6.5 ohci_hcd
      [    2.515507] usb usb3: SerialNumber: ff5d0000.usb
      [    2.517003] hub 3-0:1.0: USB hub found
      [    2.517421] hub 3-0:1.0: 1 port detected
      [    2.519498] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.520055] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus nu
      mber 4
      [    2.521074] xhci-hcd xhci-hcd.0.auto: hcc params 0x0220fe64 hci version 0x110
       quirks 0x0000000002010010
      [    2.522040] xhci-hcd xhci-hcd.0.auto: irq 166, io mem 0xff600000
      [    2.523360] usb usb4: New USB device found, idVendor=1d6b, idProduct=0002, bc
      dDevice= 5.06
      [    2.524122] usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=
      1
      [    2.524850] usb usb4: Product: xHCI Host Controller
      [    2.525309] usb usb4: Manufacturer: Linux 5.6.5 xhci-hcd
      [    2.525811] usb usb4: SerialNumber: xhci-hcd.0.auto
      [    2.527310] hub 4-0:1.0: USB hub found
      [    2.527739] hub 4-0:1.0: 1 port detected
      [    2.528804] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.529343] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus nu
      mber 5
      [    2.530066] xhci-hcd xhci-hcd.0.auto: Host supports USB 3.0 SuperSpeed
      [    2.530786] usb usb5: We don't know the algorithms for LPM for this host, dis
      abling LPM.
      [    2.531741] usb usb5: New USB device found, idVendor=1d6b, idProduct=0003, bc
      dDevice= 5.06
      [    2.532498] usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=
      1
      [    2.533201] usb usb5: Product: xHCI Host Controller
      [    2.533652] usb usb5: Manufacturer: Linux 5.6.5 xhci-hcd
      [    2.534149] usb usb5: SerialNumber: xhci-hcd.0.auto
      [    2.535628] hub 5-0:1.0: USB hub found
      [    2.536052] hub 5-0:1.0: 1 port detected
      [    2.537423] usbcore: registered new interface driver cdc_acm
      [    2.537963] cdc_acm: USB Abstract Control Model driver for USB modems and ISD
      N adapters
      [    2.538769] usbcore: registered new interface driver cdc_wdm
      [    2.539362] usbcore: registered new interface driver uas
      [    2.540056] usbcore: registered new interface driver usb-storage
      [    2.540816] usbcore: registered new interface driver usbserial_generic
      [    2.541457] usbserial: USB Serial support registered for generic
      [    2.542089] usbcore: registered new interface driver ch341
      [    2.542636] usbserial: USB Serial support registered for ch341-uart
      [    2.543289] usbcore: registered new interface driver cp210x
      [    2.543834] usbserial: USB Serial support registered for cp210x
      [    2.544530] usbcore: registered new interface driver ftdi_sio
      [    2.545113] usbserial: USB Serial support registered for FTDI USB Serial Devi
      ce
      [    2.546144] usbcore: registered new interface driver option
      [    2.546693] usbserial: USB Serial support registered for GSM modem (1-port)
      [    2.547817] usbcore: registered new interface driver pl2303
      [    2.548368] usbserial: USB Serial support registered for pl2303
      [    2.549077] usbcore: registered new interface driver qcserial
      [    2.549645] usbserial: USB Serial support registered for Qualcomm USB modem
      [    2.551123] mousedev: PS/2 mouse device common for all mice
      [    2.552716] i2c /dev entries driver
      [    2.557176] rk808 1-0018: chip id: 0x8050
      [    2.565752] rk808-regulator rk808-regulator: there is no dvs0 gpio
      [    2.566379] rk808-regulator rk808-regulator: there is no dvs1 gpio
      [    2.567075] DCDC_REG1: supplied by vcc_sys
      [    2.570450] DCDC_REG2: supplied by vcc_sys
      [    2.572776] DCDC_REG3: supplied by vcc_sys
      [    2.573732] DCDC_REG4: supplied by vcc_sys
      [    2.575621] LDO_REG1: supplied by vcc_io
      [    2.579385] LDO_REG2: supplied by vcc_io
      [    2.583109] LDO_REG3: supplied by vcc_io
      [    2.596736] rk808-rtc rk808-rtc: registered as rtc0
      [    2.599419] input: rk805 pwrkey as /devices/platform/ff160000.i2c/i2c-1/1-001
      8/rk805-pwrkey/input/input0
      [    2.601550] IR NEC protocol handler initialized
      [    2.607078] rockchip-thermal ff250000.tsadc: Missing tshut mode property, usi
      ng default (cru)
      [    2.607885] rockchip-thermal ff250000.tsadc: Missing tshut-polarity property,
       using default (low)
      [    2.611248] device-mapper: uevent: version 1.0.3
      [    2.612255] device-mapper: ioctl: 4.42.0-ioctl (2020-02-27) initialised: dm-d
      evel@redhat.com
      [    2.618492] sdhci: Secure Digital Host Controller Interface driver
      [    2.619085] sdhci: Copyright(c) Pierre Ossman
      [    2.619488] Synopsys Designware Multimedia Card Interface Driver
      [    2.621352] dwmmc_rockchip ff500000.dwmmc: IDMAC supports 32-bit address mode
      .
      [    2.622070] dwmmc_rockchip ff500000.dwmmc: Using internal DMA controller.
      [    2.622701] dwmmc_rockchip ff500000.dwmmc: Version ID is 270a
      [    2.623326] dwmmc_rockchip ff500000.dwmmc: DW MMC controller at irq 27,32 bit
       host data width,256 deep fifo
      [    2.624305] vcc_sd: supplied by vcc_io
      [    2.643336] mmc_host mmc0: Bus speed (slot 0) = 400000Hz (slot req 400000Hz, 
      actual 400000HZ div = 0)
      [    2.657491] sdhci-pltfm: SDHCI platform and OF driver helper
      [    2.660393] ledtrig-cpu: registered to indicate activity on CPUs
      [    2.661748] hid: raw HID events driver (C) Jiri Kosina
      [    2.662962] usbcore: registered new interface driver usbhid
      [    2.663488] usbhid: USB HID core driver
      [    2.669387] drop_monitor: Initializing network drop monitor service
      [    2.670303] Initializing XFRM netlink socket
      [    2.671793] NET: Registered protocol family 10
      [    2.674553] Segment Routing with IPv6
      [    2.678292] bpfilter: Loaded bpfilter_umh pid 233
      [    2.679330] NET: Registered protocol family 17
      [    2.680273] Bluetooth: RFCOMM TTY layer initialized
      [    2.680810] Bluetooth: RFCOMM socket layer initialized
      [    2.681335] Bluetooth: RFCOMM ver 1.11
      [    2.681711] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
      [    2.682275] Bluetooth: HIDP socket layer initialized
      [    2.682864] Key type dns_resolver registered
      [    2.684293] registered taskstats version 1
      [    2.684745] Loading compiled-in X.509 certificates
      [    2.685370] Key type ._fscrypt registered
      [    2.685751] Key type .fscrypt registered
      [    2.686116] Key type fscrypt-provisioning registered
      [    2.733147] friendlyelec-board board: Serial		: 37cd0f845b1d0156
      [    2.735246] input: gpio-keys as /devices/platform/gpio-keys/input/input1
      [    2.738528] rk808-rtc rk808-rtc: setting system clock to 2020-04-18T13:10:10 
      UTC (1587215410)
      [    2.740824] ALSA device list:
      [    2.741128]   No soundcards found.
      [    2.746680] Freeing unused kernel memory: 1344K
      [    2.747273] Run /init as init process
      [    2.747620]   with arguments:
      [    2.747625]     /init
      [    2.747632]     earlyprintk
      [    2.747637]   with environment:
      [    2.747644]     HOME=/
      [    2.747649]     TERM=linux
      [    2.789527] random: fast init done
      [    2.905671] mmc_host mmc0: Bus speed (slot 0) = 100000000Hz (slot req 1000000
      00Hz, actual 100000000HZ div = 0)
      [    4.215579] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 91
      [    4.216290] mmc0: new ultra high speed SDR50 SDHC card at address aaaa
      [    4.219137] mmcblk0: mmc0:aaaa SL16G 14.8 GiB 
      [    4.225596]  mmcblk0: p1 p2
      [    4.888875] usb 5-1: new SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [    4.910206] usb 5-1: New USB device found, idVendor=0bda, idProduct=8153, bcd
      Device=31.00
      [    4.910993] usb 5-1: New USB device strings: Mfr=1, Product=2, SerialNumber=6
      [    4.911667] usb 5-1: Product: USB 10/100/1000 LAN
      [    4.912115] usb 5-1: Manufacturer: Realtek
      [    4.912511] usb 5-1: SerialNumber: 000000000000
      [    7.890619] EXT4-fs (mmcblk0p2): mounted filesystem without journal. Opts: (n
      ull)
      [    8.580919] systemd[1]: systemd 242 running in system mode. (+PAM +AUDIT +SEL
      INUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +
      XZ +LZ4 +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=hybr
      id)
      [    8.583862] systemd[1]: Detected architecture arm64.
      [    8.608827] phy phy-ff450000.syscon:usb2-phy@100.0: charger = USB_DCP_CHARGER
      [    8.625527] systemd[1]: Set hostname to <nanopi-r2s>.
      [    8.629285] systemd[1]: Failed to bump fs.file-max, ignoring: Invalid argumen
      t
      [    9.110097] systemd[1]: /lib/systemd/system/dbus.socket:4: ListenStream= refe
      rences a path below legacy directory /var/run/, updating /var/run/dbus/system_bu
      s_socket → /run/dbus/system_bus_socket; please update the unit file accordingly.
      [    9.260185] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.263622] systemd[1]: Created slice User and Session Slice.
      [    9.277045] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.278354] systemd[1]: Listening on Syslog Socket.
      [    9.288926] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.292181] systemd[1]: Created slice system-systemd\x2dfsck.slice.
      [    9.305659] systemd[1]: Listening on fsck to fsckd communication Socket.
      [    9.317406] systemd[1]: Started Dispatch Password Requests to Console Directo
      ry Watch.
      [    9.522952] EXT4-fs (mmcblk0p2): re-mounted. Opts: commit=600,errors=remount-
      ro
      [   10.498505] systemd-journald[294]: Received request to flush runtime journal 
      from PID 1
      [   10.811448] usbcore: registered new interface driver r8152
      [   10.979218] usb 5-1: reset SuperSpeed Gen 1 USB device number 2 using xhci-hc
      d
      [   11.015698] r8152 5-1:1.0: Direct firmware load for rtl_nic/rtl8153b-2.fw
      [   11.016215] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Invalid ether
       addr 00:00:00:00:00:00
      [   11.017333] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether 
      addr 3a:f5:08:91:15:9e
      [   11.038117] r8152 5-1:1.0: load rtl8153b-2 v1 10/23/19 successfully
      [   11.070387] r8152 5-1:1.0 eth1: v1.11.11
      [   11.266402] EXT4-fs (mmcblk0p1): mounted filesystem with ordered data mode. O
      pts: (null)
      [   11.266442] ext4 filesystem being mounted at /boot supports timestamps until 
      2038 (0x7fffffff)
      ubuntu@nanopi-r2s:~$ dmesg
      [    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
      [    0.000000] Linux version 5.6.5 (ubuntu@nanopi-r2s) (gcc version 9.2.1 20191008 (Ubuntu 9.2.1-9ubuntu2)) #1 SMP PREEMPT Sat Apr 18 01:51:49 UTC 2020
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
      [    0.000000] ftrace: allocating 43464 entries in 170 pages
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
      [    0.000837] Console: colour dummy device 80x25
      [    0.001499] printk: console [tty0] enabled
      [    0.001574] Calibrating delay loop (skipped), value calculated using timer frequency.. 48.00 BogoMIPS (lpj=96000)
      [    0.001620] pid_max: default: 32768 minimum: 301
      [    0.001836] LSM: Security Framework initializing
      [    0.001988] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.002032] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.035859] rcu: Hierarchical SRCU implementation.
      [    0.047139] EFI services will not be available.
      [    0.056015] smp: Bringing up secondary CPUs ...
      [    0.088332] Detected VIPT I-cache on CPU1
      [    0.088422] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
      [    0.120483] Detected VIPT I-cache on CPU2
      [    0.120570] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
      [    0.152637] Detected VIPT I-cache on CPU3
      [    0.152718] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
      [    0.152938] smp: Brought up 1 node, 4 CPUs
      [    0.153086] SMP: Total of 4 processors activated.
      [    0.153119] CPU features: detected: 32-bit EL0 Support
      [    0.153151] CPU features: detected: CRC32 instructions
      [    0.178985] CPU: All CPU(s) started at EL2
      [    0.179098] alternatives: patching kernel code
      [    0.181535] devtmpfs: initialized
      [    0.198005] Registered cp15_barrier emulation handler
      [    0.198070] Registered setend emulation handler
      [    0.198795] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
      [    0.198865] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
      [    0.200292] pinctrl core: initialized pinctrl subsystem
      [    0.201368] thermal_sys: Registered thermal governor 'fair_share'
      [    0.201374] thermal_sys: Registered thermal governor 'step_wise'
      [    0.202150] DMI not present or invalid.
      [    0.203164] NET: Registered protocol family 16
      [    0.206922] DMA: preallocated 256 KiB pool for atomic allocations
      [    0.206993] audit: initializing netlink subsys (disabled)
      [    0.207385] audit: type=2000 audit(0.204:1): state=initialized audit_enabled=0 res=1
      [    0.208786] cpuidle: using governor ladder
      [    0.208903] cpuidle: using governor menu
      [    0.209397] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
      [    0.209598] ASID allocator initialised with 65536 entries
      [    0.265977] HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
      [    0.266027] HugeTLB registered 32.0 MiB page size, pre-allocated 0 pages
      [    0.266058] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
      [    0.266088] HugeTLB registered 64.0 KiB page size, pre-allocated 0 pages
      [    0.272474] cryptd: max_cpu_qlen set to 1000
      [    0.296986] iommu: Default domain type: Translated 
      [    0.298829] SCSI subsystem initialized
      [    0.299314] libata version 3.00 loaded.
      [    0.299688] usbcore: registered new interface driver usbfs
      [    0.299815] usbcore: registered new interface driver hub
      [    0.299988] usbcore: registered new device driver usb
      [    0.300131] mc: Linux media interface: v0.10
      [    0.300205] videodev: Linux video capture interface: v2.00
      [    0.300299] pps_core: LinuxPPS API ver. 1 registered
      [    0.300330] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
      [    0.300384] PTP clock support registered
      [    0.301793] Advanced Linux Sound Architecture Driver Initialized.
      [    0.302941] Bluetooth: Core ver 2.22
      [    0.303060] NET: Registered protocol family 31
      [    0.303087] Bluetooth: HCI device and connection manager initialized
      [    0.303133] Bluetooth: HCI socket layer initialized
      [    0.303169] Bluetooth: L2CAP socket layer initialized
      [    0.303233] Bluetooth: SCO socket layer initialized
      [    0.303289] NetLabel: Initializing
      [    0.303312] NetLabel:  domain hash size = 128
      [    0.303335] NetLabel:  protocols = UNLABELED CIPSOv4 CALIPSO
      [    0.303463] NetLabel:  unlabeled traffic allowed by default
      [    0.304677] clocksource: Switched to clocksource arch_sys_counter
      [    1.891282] VFS: Disk quotas dquot_6.6.0
      [    1.891438] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
      [    1.891737] FS-Cache: Loaded
      [    1.906713] NET: Registered protocol family 2
      [    1.907729] tcp_listen_portaddr_hash hash table entries: 512 (order: 2, 20480 bytes, linear)
      [    1.907832] TCP established hash table entries: 8192 (order: 4, 65536 bytes, linear)
      [    1.907984] TCP bind hash table entries: 8192 (order: 6, 262144 bytes, linear)
      [    1.908351] TCP: Hash tables configured (established 8192 bind 8192)
      [    1.908633] UDP hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.908845] UDP-Lite hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.909559] NET: Registered protocol family 1
      [    1.910672] RPC: Registered named UNIX socket transport module.
      [    1.910716] RPC: Registered udp transport module.
      [    1.910743] RPC: Registered tcp transport module.
      [    1.910770] RPC: Registered tcp NFSv4.1 backchannel transport module.
      [    1.910816] PCI: CLS 0 bytes, default 64
      [    1.911191] Trying to unpack rootfs image as initramfs...
      [    1.994380] Freeing initrd memory: 1076K
      [    1.996110] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 counters available
      [    2.014722] Initialise system trusted keyrings
      [    2.015155] workingset: timestamp_bits=46 max_order=18 bucket_order=0
      [    2.030588] squashfs: version 4.0 (2009/01/31) Phillip Lougher
      [    2.031228] FS-Cache: Netfs 'nfs' registered for caching
      [    2.032312] NFS: Registering the id_resolver key type
      [    2.032389] Key type id_resolver registered
      [    2.032413] Key type id_legacy registered
      [    2.032458] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
      [    2.032972] fuse: init (API version 7.31)
      [    2.059671] Key type asymmetric registered
      [    2.059719] Asymmetric key parser 'x509' registered
      [    2.059848] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 247)
      [    2.060195] io scheduler mq-deadline registered
      [    2.060236] io scheduler kyber registered
      [    2.068058] rockchip-u3phy ff470000.usb3-phy: Rockchip u3phy initialized successfully
      [    2.074057] dma-pl330 ff1f0000.dmac: Loaded driver for PL330 DMAC-241330
      [    2.074115] dma-pl330 ff1f0000.dmac: 	DBUFF-128x8bytes Num_Chans-8 Num_Peri-20 Num_Events-16
      [    2.075101] Serial: 8250/16550 driver, 5 ports, IRQ sharing disabled
      [    2.078184] ff130000.serial: ttyS2 at MMIO 0xff130000 (irq = 12, base_baud = 1500000) is a 16550A
      [    2.149020] printk: console [ttyS2] enabled
      [    2.153337] rockchip-drm display-subsystem: [drm:rockchip_drm_platform_probe] *ERROR* No available vop found for display-subsystem.
      [    2.167005] brd: module loaded
      [    2.186917] loop: module loaded
      [    2.190400] libphy: Fixed MDIO Bus: probed
      [    2.192384] rk_gmac-dwmac ff540000.ethernet: IRQ eth_wake_irq not found
      [    2.193091] rk_gmac-dwmac ff540000.ethernet: IRQ eth_lpi not found
      [    2.193883] rk_gmac-dwmac ff540000.ethernet: PTP uses main clock
      [    2.194638] rk_gmac-dwmac ff540000.ethernet: clock input or output? (input).
      [    2.195293] rk_gmac-dwmac ff540000.ethernet: TX delay(0x24).
      [    2.195823] rk_gmac-dwmac ff540000.ethernet: RX delay(0x18).
      [    2.196356] rk_gmac-dwmac ff540000.ethernet: integrated PHY? (no).
      [    2.197090] rk_gmac-dwmac ff540000.ethernet: cannot get clock clk_mac_speed
      [    2.197731] rk_gmac-dwmac ff540000.ethernet: clock input from PHY
      [    2.203338] rk_gmac-dwmac ff540000.ethernet: init for RGMII
      [    2.204252] rk_gmac-dwmac ff540000.ethernet: User ID: 0x10, Synopsys ID: 0x35
      [    2.204962] rk_gmac-dwmac ff540000.ethernet: 	DWMAC1000
      [    2.205451] rk_gmac-dwmac ff540000.ethernet: DMA HW capability register supported
      [    2.206140] rk_gmac-dwmac ff540000.ethernet: RX Checksum Offload Engine supported
      [    2.206826] rk_gmac-dwmac ff540000.ethernet: COE Type 2
      [    2.207306] rk_gmac-dwmac ff540000.ethernet: TX Checksum insertion supported
      [    2.207946] rk_gmac-dwmac ff540000.ethernet: Wake-Up On Lan supported
      [    2.208596] rk_gmac-dwmac ff540000.ethernet: Normal descriptors
      [    2.209160] rk_gmac-dwmac ff540000.ethernet: Ring mode enabled
      [    2.209702] rk_gmac-dwmac ff540000.ethernet: Enable RX Mitigation via HW Watchdog Timer
      [    2.268696] libphy: stmmac: probed
      [    2.272157] PPP generic driver version 2.4.2
      [    2.273080] usbcore: registered new interface driver asix
      [    2.273660] usbcore: registered new interface driver ax88179_178a
      [    2.274268] usbcore: registered new interface driver cdc_ether
      [    2.274861] usbcore: registered new interface driver qmi_wwan
      [    2.277636] dwc3 ff600000.dwc3: Failed to get clk 'ref': -2
      [    2.278442] phy phy-ff470000.usb3-phy.2: u3phy u2 power on
      [    2.278989] phy phy-ff470000.usb3-phy.3: u3phy u3 power on
      [    2.281008] dwc2 ff580000.usb: ff580000.usb supply vusb_d not found, using dummy regulator
      [    2.281948] dwc2 ff580000.usb: ff580000.usb supply vusb_a not found, using dummy regulator
      [    2.412800] dwc2 ff580000.usb: EPs: 10, dedicated fifos, 972 entries in SPRAM
      [    2.414108] dwc2 ff580000.usb: DWC OTG Controller
      [    2.414599] dwc2 ff580000.usb: new USB bus registered, assigned bus number 1
      [    2.415293] dwc2 ff580000.usb: irq 29, io mem 0xff580000
      [    2.416077] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.416881] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.417541] usb usb1: Product: DWC OTG Controller
      [    2.417976] usb usb1: Manufacturer: Linux 5.6.5 dwc2_hsotg
      [    2.418485] usb usb1: SerialNumber: ff580000.usb
      [    2.419980] hub 1-0:1.0: USB hub found
      [    2.420394] hub 1-0:1.0: 1 port detected
      [    2.422111] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
      [    2.422754] ehci-pci: EHCI PCI platform driver
      [    2.423253] ehci-platform: EHCI generic platform driver
      [    2.426457] ehci-platform ff5c0000.usb: EHCI Host Controller
      [    2.427027] ehci-platform ff5c0000.usb: new USB bus registered, assigned bus number 2
      [    2.427963] ehci-platform ff5c0000.usb: irq 30, io mem 0xff5c0000
      [    2.440715] ehci-platform ff5c0000.usb: USB 2.0 started, EHCI 1.00
      [    2.441712] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.442479] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.443139] usb usb2: Product: EHCI Host Controller
      [    2.443587] usb usb2: Manufacturer: Linux 5.6.5 ehci_hcd
      [    2.444081] usb usb2: SerialNumber: ff5c0000.usb
      [    2.445595] hub 2-0:1.0: USB hub found
      [    2.446015] hub 2-0:1.0: 1 port detected
      [    2.447209] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
      [    2.447830] ohci-platform: OHCI generic platform driver
      [    2.449001] ohci-platform ff5d0000.usb: Generic Platform OHCI controller
      [    2.449669] ohci-platform ff5d0000.usb: new USB bus registered, assigned bus number 3
      [    2.450632] ohci-platform ff5d0000.usb: irq 31, io mem 0xff5d0000
      [    2.513042] usb usb3: New USB device found, idVendor=1d6b, idProduct=0001, bcdDevice= 5.06
      [    2.513808] usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.514473] usb usb3: Product: Generic Platform OHCI controller
      [    2.515014] usb usb3: Manufacturer: Linux 5.6.5 ohci_hcd
      [    2.515507] usb usb3: SerialNumber: ff5d0000.usb
      [    2.517003] hub 3-0:1.0: USB hub found
      [    2.517421] hub 3-0:1.0: 1 port detected
      [    2.519498] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.520055] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 4
      [    2.521074] xhci-hcd xhci-hcd.0.auto: hcc params 0x0220fe64 hci version 0x110 quirks 0x0000000002010010
      [    2.522040] xhci-hcd xhci-hcd.0.auto: irq 166, io mem 0xff600000
      [    2.523360] usb usb4: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.524122] usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.524850] usb usb4: Product: xHCI Host Controller
      [    2.525309] usb usb4: Manufacturer: Linux 5.6.5 xhci-hcd
      [    2.525811] usb usb4: SerialNumber: xhci-hcd.0.auto
      [    2.527310] hub 4-0:1.0: USB hub found
      [    2.527739] hub 4-0:1.0: 1 port detected
      [    2.528804] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.529343] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 5
      [    2.530066] xhci-hcd xhci-hcd.0.auto: Host supports USB 3.0 SuperSpeed
      [    2.530786] usb usb5: We don't know the algorithms for LPM for this host, disabling LPM.
      [    2.531741] usb usb5: New USB device found, idVendor=1d6b, idProduct=0003, bcdDevice= 5.06
      [    2.532498] usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.533201] usb usb5: Product: xHCI Host Controller
      [    2.533652] usb usb5: Manufacturer: Linux 5.6.5 xhci-hcd
      [    2.534149] usb usb5: SerialNumber: xhci-hcd.0.auto
      [    2.535628] hub 5-0:1.0: USB hub found
      [    2.536052] hub 5-0:1.0: 1 port detected
      [    2.537423] usbcore: registered new interface driver cdc_acm
      [    2.537963] cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
      [    2.538769] usbcore: registered new interface driver cdc_wdm
      [    2.539362] usbcore: registered new interface driver uas
      [    2.540056] usbcore: registered new interface driver usb-storage
      [    2.540816] usbcore: registered new interface driver usbserial_generic
      [    2.541457] usbserial: USB Serial support registered for generic
      [    2.542089] usbcore: registered new interface driver ch341
      [    2.542636] usbserial: USB Serial support registered for ch341-uart
      [    2.543289] usbcore: registered new interface driver cp210x
      [    2.543834] usbserial: USB Serial support registered for cp210x
      [    2.544530] usbcore: registered new interface driver ftdi_sio
      [    2.545113] usbserial: USB Serial support registered for FTDI USB Serial Device
      [    2.546144] usbcore: registered new interface driver option
      [    2.546693] usbserial: USB Serial support registered for GSM modem (1-port)
      [    2.547817] usbcore: registered new interface driver pl2303
      [    2.548368] usbserial: USB Serial support registered for pl2303
      [    2.549077] usbcore: registered new interface driver qcserial
      [    2.549645] usbserial: USB Serial support registered for Qualcomm USB modem
      [    2.551123] mousedev: PS/2 mouse device common for all mice
      [    2.552716] i2c /dev entries driver
      [    2.557176] rk808 1-0018: chip id: 0x8050
      [    2.565752] rk808-regulator rk808-regulator: there is no dvs0 gpio
      [    2.566379] rk808-regulator rk808-regulator: there is no dvs1 gpio
      [    2.567075] DCDC_REG1: supplied by vcc_sys
      [    2.570450] DCDC_REG2: supplied by vcc_sys
      [    2.572776] DCDC_REG3: supplied by vcc_sys
      [    2.573732] DCDC_REG4: supplied by vcc_sys
      [    2.575621] LDO_REG1: supplied by vcc_io
      [    2.579385] LDO_REG2: supplied by vcc_io
      [    2.583109] LDO_REG3: supplied by vcc_io
      [    2.596736] rk808-rtc rk808-rtc: registered as rtc0
      [    2.599419] input: rk805 pwrkey as /devices/platform/ff160000.i2c/i2c-1/1-0018/rk805-pwrkey/input/input0
      [    2.601550] IR NEC protocol handler initialized
      [    2.607078] rockchip-thermal ff250000.tsadc: Missing tshut mode property, using default (cru)
      [    2.607885] rockchip-thermal ff250000.tsadc: Missing tshut-polarity property, using default (low)
      [    2.611248] device-mapper: uevent: version 1.0.3
      [    2.612255] device-mapper: ioctl: 4.42.0-ioctl (2020-02-27) initialised: dm-devel@redhat.com
      [    2.618492] sdhci: Secure Digital Host Controller Interface driver
      [    2.619085] sdhci: Copyright(c) Pierre Ossman
      [    2.619488] Synopsys Designware Multimedia Card Interface Driver
      [    2.621352] dwmmc_rockchip ff500000.dwmmc: IDMAC supports 32-bit address mode.
      [    2.622070] dwmmc_rockchip ff500000.dwmmc: Using internal DMA controller.
      [    2.622701] dwmmc_rockchip ff500000.dwmmc: Version ID is 270a
      [    2.623326] dwmmc_rockchip ff500000.dwmmc: DW MMC controller at irq 27,32 bit host data width,256 deep fifo
      [    2.624305] vcc_sd: supplied by vcc_io
      [    2.643336] mmc_host mmc0: Bus speed (slot 0) = 400000Hz (slot req 400000Hz, actual 400000HZ div = 0)
      [    2.657491] sdhci-pltfm: SDHCI platform and OF driver helper
      [    2.660393] ledtrig-cpu: registered to indicate activity on CPUs
      [    2.661748] hid: raw HID events driver (C) Jiri Kosina
      [    2.662962] usbcore: registered new interface driver usbhid
      [    2.663488] usbhid: USB HID core driver
      [    2.669387] drop_monitor: Initializing network drop monitor service
      [    2.670303] Initializing XFRM netlink socket
      [    2.671793] NET: Registered protocol family 10
      [    2.674553] Segment Routing with IPv6
      [    2.678292] bpfilter: Loaded bpfilter_umh pid 233
      [    2.679330] NET: Registered protocol family 17
      [    2.680273] Bluetooth: RFCOMM TTY layer initialized
      [    2.680810] Bluetooth: RFCOMM socket layer initialized
      [    2.681335] Bluetooth: RFCOMM ver 1.11
      [    2.681711] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
      [    2.682275] Bluetooth: HIDP socket layer initialized
      [    2.682864] Key type dns_resolver registered
      [    2.684293] registered taskstats version 1
      [    2.684745] Loading compiled-in X.509 certificates
      [    2.685370] Key type ._fscrypt registered
      [    2.685751] Key type .fscrypt registered
      [    2.686116] Key type fscrypt-provisioning registered
      [    2.733147] friendlyelec-board board: Serial		: 37cd0f845b1d0156
      [    2.735246] input: gpio-keys as /devices/platform/gpio-keys/input/input1
      [    2.738528] rk808-rtc rk808-rtc: setting system clock to 2020-04-18T13:10:10 UTC (1587215410)
      [    2.740824] ALSA device list:
      [    2.741128]   No soundcards found.
      [    2.746680] Freeing unused kernel memory: 1344K
      [    2.747273] Run /init as init process
      [    2.747620]   with arguments:
      [    2.747625]     /init
      [    2.747632]     earlyprintk
      [    2.747637]   with environment:
      [    2.747644]     HOME=/
      [    2.747649]     TERM=linux
      [    2.789527] random: fast init done
      [    2.905671] mmc_host mmc0: Bus speed (slot 0) = 100000000Hz (slot req 100000000Hz, actual 100000000HZ div = 0)
      [    4.215579] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 91
      [    4.216290] mmc0: new ultra high speed SDR50 SDHC card at address aaaa
      [    4.219137] mmcblk0: mmc0:aaaa SL16G 14.8 GiB 
      [    4.225596]  mmcblk0: p1 p2
      [    4.888875] usb 5-1: new SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [    4.910206] usb 5-1: New USB device found, idVendor=0bda, idProduct=8153, bcdDevice=31.00
      [    4.910993] usb 5-1: New USB device strings: Mfr=1, Product=2, SerialNumber=6
      [    4.911667] usb 5-1: Product: USB 10/100/1000 LAN
      [    4.912115] usb 5-1: Manufacturer: Realtek
      [    4.912511] usb 5-1: SerialNumber: 000000000000
      [    7.890619] EXT4-fs (mmcblk0p2): mounted filesystem without journal. Opts: (null)
      [    8.580919] systemd[1]: systemd 242 running in system mode. (+PAM +AUDIT +SELINUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +XZ +LZ4 +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=hybrid)
      [    8.583862] systemd[1]: Detected architecture arm64.
      [    8.608827] phy phy-ff450000.syscon:usb2-phy@100.0: charger = USB_DCP_CHARGER
      [    8.625527] systemd[1]: Set hostname to <nanopi-r2s>.
      [    8.629285] systemd[1]: Failed to bump fs.file-max, ignoring: Invalid argument
      [    9.110097] systemd[1]: /lib/systemd/system/dbus.socket:4: ListenStream= references a path below legacy directory /var/run/, updating /var/run/dbus/system_bus_socket → /run/dbus/system_bus_socket; please update the unit file accordingly.
      [    9.260185] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.263622] systemd[1]: Created slice User and Session Slice.
      [    9.277045] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.278354] systemd[1]: Listening on Syslog Socket.
      [    9.288926] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.292181] systemd[1]: Created slice system-systemd\x2dfsck.slice.
      [    9.305659] systemd[1]: Listening on fsck to fsckd communication Socket.
      [    9.317406] systemd[1]: Started Dispatch Password Requests to Console Directory Watch.
      [    9.522952] EXT4-fs (mmcblk0p2): re-mounted. Opts: commit=600,errors=remount-ro
      [   10.498505] systemd-journald[294]: Received request to flush runtime journal from PID 1
      [   10.811448] usbcore: registered new interface driver r8152
      [   10.979218] usb 5-1: reset SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [   11.015698] r8152 5-1:1.0: Direct firmware load for rtl_nic/rtl8153b-2.fw
      [   11.016215] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Invalid ether addr 00:00:00:00:00:00
      [   11.017333] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether addr 3a:f5:08:91:15:9e
      [   11.038117] r8152 5-1:1.0: load rtl8153b-2 v1 10/23/19 successfully
      [   11.070387] r8152 5-1:1.0 eth1: v1.11.11
      [   11.266402] EXT4-fs (mmcblk0p1): mounted filesystem with ordered data mode. Opts: (null)
      [   11.266442] ext4 filesystem being mounted at /boot supports timestamps until 2038 (0x7fffffff)
      [   11.594952] rk_gmac-dwmac ff540000.ethernet eth0: PHY [stmmac-0:00] driver [RTL8211E Gigabit Ethernet] (irq=POLL)
      [   11.598693] rk_gmac-dwmac ff540000.ethernet eth0: No Safety Features support found
      [   11.598720] rk_gmac-dwmac ff540000.ethernet eth0: PTP not supported by HW
      [   11.598739] rk_gmac-dwmac ff540000.ethernet eth0: configuring for phy/rgmii link mode
      [   12.581351] zram: Added device: zram0
      [   12.586600] zram: Added device: zram1
      [   12.589370] zram: Added device: zram2
      [   12.591308] zram: Added device: zram3
      [   12.663753] zram0: detected capacity change from 0 to 128704512
      [   13.200167] random: crng init done
      [   13.200183] random: 7 urandom warning(s) missed due to ratelimiting
      [   13.668840] Adding 125684k swap on /dev/zram0.  Priority:5 extents:1 across:125684k SSFS
      [   13.677258] zram1: detected capacity change from 0 to 128704512
      [   13.773136] Adding 125684k swap on /dev/zram1.  Priority:5 extents:1 across:125684k SSFS
      [   13.775783] zram2: detected capacity change from 0 to 128704512
      [   13.828924] Adding 125684k swap on /dev/zram2.  Priority:5 extents:1 across:125684k SSFS
      [   13.831476] zram3: detected capacity change from 0 to 128704512
      [   13.880859] Adding 125684k swap on /dev/zram3.  Priority:5 extents:1 across:125684k SSFS
      [   16.705440] rk_gmac-dwmac ff540000.ethernet eth0: Link is Up - 1Gbps/Full - flow control rx/tx
      [   16.705531] IPv6: ADDRCONF(NETDEV_CHANGE): eth0: link becomes ready
