# Nanopi-r2s-ubuntu-server-minimal-image

Ubuntu 19.10 Server for NanoPi R2S

This is the base Image for a small router, based on Kernel 5.4.25 and up for the NanoPi R2S

Release with Kernel version:

* v0.1 - Kernel 5.4.25

* v0.2 - Kernel 5.4.27

* v0.3 - Kernel 5.4.28

* v0.4 - Kernel 5.6.2


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

# BootLog

      [    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
      [    0.000000] Linux version 5.6.2 (ubuntu@nanopi-r2s) (gcc version 9.2.1 20191008 (Ubuntu 9.2.1-9ubuntu2)) #1 SMP PREEMPT Fri Apr 3 13:58:21 UTC 2020
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
      [    0.000000] Memory: 986684K/1046528K available (12668K kernel code, 1712K rwdata, 5028K rodata, 1344K init, 795K bss, 43460K reserved, 16384K cma-reserved)
      [    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
      [    0.000000] ftrace: allocating 43458 entries in 170 pages
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
      [    0.000857] Console: colour dummy device 80x25
      [    0.001518] printk: console [tty0] enabled
      [    0.001594] Calibrating delay loop (skipped), value calculated using timer frequency.. 48.00 BogoMIPS (lpj=96000)
      [    0.001639] pid_max: default: 32768 minimum: 301
      [    0.001863] LSM: Security Framework initializing
      [    0.002004] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.002047] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.035863] rcu: Hierarchical SRCU implementation.
      [    0.047234] EFI services will not be available.
      [    0.056022] smp: Bringing up secondary CPUs ...
      [    0.088357] Detected VIPT I-cache on CPU1
      [    0.088451] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
      [    0.120526] Detected VIPT I-cache on CPU2
      [    0.120612] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
      [    0.152676] Detected VIPT I-cache on CPU3
      [    0.152759] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
      [    0.152974] smp: Brought up 1 node, 4 CPUs
      [    0.153120] SMP: Total of 4 processors activated.
      [    0.153153] CPU features: detected: 32-bit EL0 Support
      [    0.153186] CPU features: detected: CRC32 instructions
      [    0.179137] CPU: All CPU(s) started at EL2
      [    0.179245] alternatives: patching kernel code
      [    0.181693] devtmpfs: initialized
      [    0.198197] Registered cp15_barrier emulation handler
      [    0.198256] Registered setend emulation handler
      [    0.198977] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
      [    0.199053] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
      [    0.200514] pinctrl core: initialized pinctrl subsystem
      [    0.201614] thermal_sys: Registered thermal governor 'fair_share'
      [    0.201622] thermal_sys: Registered thermal governor 'step_wise'
      [    0.202397] DMI not present or invalid.
      [    0.203417] NET: Registered protocol family 16
      [    0.206957] DMA: preallocated 256 KiB pool for atomic allocations
      [    0.207028] audit: initializing netlink subsys (disabled)
      [    0.207424] audit: type=2000 audit(0.204:1): state=initialized audit_enabled=0 res=1
      [    0.208829] cpuidle: using governor ladder
      [    0.208949] cpuidle: using governor menu
      [    0.209442] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
      [    0.209641] ASID allocator initialised with 65536 entries
      [    0.266312] HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
      [    0.266360] HugeTLB registered 32.0 MiB page size, pre-allocated 0 pages
      [    0.266394] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
      [    0.266425] HugeTLB registered 64.0 KiB page size, pre-allocated 0 pages
      [    0.273338] cryptd: max_cpu_qlen set to 1000
      [    0.297558] iommu: Default domain type: Translated 
      [    0.299497] SCSI subsystem initialized
      [    0.300024] libata version 3.00 loaded.
      [    0.300407] usbcore: registered new interface driver usbfs
      [    0.300524] usbcore: registered new interface driver hub
      [    0.300708] usbcore: registered new device driver usb
      [    0.300845] mc: Linux media interface: v0.10
      [    0.300924] videodev: Linux video capture interface: v2.00
      [    0.301019] pps_core: LinuxPPS API ver. 1 registered
      [    0.301044] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
      [    0.301098] PTP clock support registered
      [    0.302034] Advanced Linux Sound Architecture Driver Initialized.
      [    0.303134] Bluetooth: Core ver 2.22
      [    0.303227] NET: Registered protocol family 31
      [    0.303251] Bluetooth: HCI device and connection manager initialized
      [    0.303300] Bluetooth: HCI socket layer initialized
      [    0.303335] Bluetooth: L2CAP socket layer initialized
      [    0.303393] Bluetooth: SCO socket layer initialized
      [    0.303447] NetLabel: Initializing
      [    0.303468] NetLabel:  domain hash size = 128
      [    0.303495] NetLabel:  protocols = UNLABELED CIPSOv4 CALIPSO
      [    0.303626] NetLabel:  unlabeled traffic allowed by default
      [    0.304751] clocksource: Switched to clocksource arch_sys_counter
      [    1.892190] VFS: Disk quotas dquot_6.6.0
      [    1.892346] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
      [    1.892675] FS-Cache: Loaded
      [    1.907862] NET: Registered protocol family 2
      [    1.909053] tcp_listen_portaddr_hash hash table entries: 512 (order: 2, 20480 bytes, linear)
      [    1.909161] TCP established hash table entries: 8192 (order: 4, 65536 bytes, linear)
      [    1.909307] TCP bind hash table entries: 8192 (order: 6, 262144 bytes, linear)
      [    1.909677] TCP: Hash tables configured (established 8192 bind 8192)
      [    1.909970] UDP hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.910094] UDP-Lite hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.910822] NET: Registered protocol family 1
      [    1.911953] RPC: Registered named UNIX socket transport module.
      [    1.912007] RPC: Registered udp transport module.
      [    1.912033] RPC: Registered tcp transport module.
      [    1.912055] RPC: Registered tcp NFSv4.1 backchannel transport module.
      [    1.912105] PCI: CLS 0 bytes, default 64
      [    1.912500] Trying to unpack rootfs image as initramfs...
      [    1.995447] Freeing initrd memory: 1076K
      [    1.997339] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 counters available
      [    2.015085] Initialise system trusted keyrings
      [    2.015534] workingset: timestamp_bits=46 max_order=18 bucket_order=0
      [    2.030757] squashfs: version 4.0 (2009/01/31) Phillip Lougher
      [    2.031395] FS-Cache: Netfs 'nfs' registered for caching
      [    2.032509] NFS: Registering the id_resolver key type
      [    2.032583] Key type id_resolver registered
      [    2.032607] Key type id_legacy registered
      [    2.032651] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
      [    2.033188] fuse: init (API version 7.31)
      [    2.060541] Key type asymmetric registered
      [    2.060587] Asymmetric key parser 'x509' registered
      [    2.060706] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 247)
      [    2.061124] io scheduler mq-deadline registered
      [    2.061166] io scheduler kyber registered
      [    2.068957] rockchip-u3phy ff470000.usb3-phy: Rockchip u3phy initialized successfully
      [    2.074964] dma-pl330 ff1f0000.dmac: Loaded driver for PL330 DMAC-241330
      [    2.075017] dma-pl330 ff1f0000.dmac: 	DBUFF-128x8bytes Num_Chans-8 Num_Peri-20 Num_Events-16
      [    2.076038] Serial: 8250/16550 driver, 5 ports, IRQ sharing disabled
      [    2.079090] ff130000.serial: ttyS2 at MMIO 0xff130000 (irq = 12, base_baud = 1500000) is a 16550A
      [    2.149935] printk: console [ttyS2] enabled
      [    2.154227] rockchip-drm display-subsystem: [drm:rockchip_drm_platform_probe] *ERROR* No available vop found for display-subsystem.
      [    2.167846] brd: module loaded
      [    2.187921] loop: module loaded
      [    2.191472] libphy: Fixed MDIO Bus: probed
      [    2.193570] rk_gmac-dwmac ff540000.ethernet: IRQ eth_wake_irq not found
      [    2.194202] rk_gmac-dwmac ff540000.ethernet: IRQ eth_lpi not found
      [    2.194982] rk_gmac-dwmac ff540000.ethernet: PTP uses main clock
      [    2.195725] rk_gmac-dwmac ff540000.ethernet: clock input or output? (input).
      [    2.196376] rk_gmac-dwmac ff540000.ethernet: TX delay(0x24).
      [    2.196940] rk_gmac-dwmac ff540000.ethernet: RX delay(0x18).
      [    2.197484] rk_gmac-dwmac ff540000.ethernet: integrated PHY? (no).
      [    2.198189] rk_gmac-dwmac ff540000.ethernet: cannot get clock clk_mac_speed
      [    2.198830] rk_gmac-dwmac ff540000.ethernet: clock input from PHY
      [    2.204469] rk_gmac-dwmac ff540000.ethernet: init for RGMII
      [    2.205414] rk_gmac-dwmac ff540000.ethernet: User ID: 0x10, Synopsys ID: 0x35
      [    2.206086] rk_gmac-dwmac ff540000.ethernet: 	DWMAC1000
      [    2.206574] rk_gmac-dwmac ff540000.ethernet: DMA HW capability register supported
      [    2.207262] rk_gmac-dwmac ff540000.ethernet: RX Checksum Offload Engine supported
      [    2.207944] rk_gmac-dwmac ff540000.ethernet: COE Type 2
      [    2.208423] rk_gmac-dwmac ff540000.ethernet: TX Checksum insertion supported
      [    2.209110] rk_gmac-dwmac ff540000.ethernet: Wake-Up On Lan supported
      [    2.209762] rk_gmac-dwmac ff540000.ethernet: Normal descriptors
      [    2.210307] rk_gmac-dwmac ff540000.ethernet: Ring mode enabled
      [    2.210839] rk_gmac-dwmac ff540000.ethernet: Enable RX Mitigation via HW Watchdog Timer
      [    2.268776] libphy: stmmac: probed
      [    2.272284] PPP generic driver version 2.4.2
      [    2.273165] usbcore: registered new interface driver asix
      [    2.273754] usbcore: registered new interface driver ax88179_178a
      [    2.274372] usbcore: registered new interface driver cdc_ether
      [    2.274960] usbcore: registered new interface driver qmi_wwan
      [    2.277753] dwc3 ff600000.dwc3: Failed to get clk 'ref': -2
      [    2.278563] phy phy-ff470000.usb3-phy.2: u3phy u2 power on
      [    2.279113] phy phy-ff470000.usb3-phy.3: u3phy u3 power on
      [    2.281138] dwc2 ff580000.usb: ff580000.usb supply vusb_d not found, using dummy regulator
      [    2.282065] dwc2 ff580000.usb: ff580000.usb supply vusb_a not found, using dummy regulator
      [    2.412858] dwc2 ff580000.usb: EPs: 10, dedicated fifos, 972 entries in SPRAM
      [    2.414197] dwc2 ff580000.usb: DWC OTG Controller
      [    2.414686] dwc2 ff580000.usb: new USB bus registered, assigned bus number 1
      [    2.415407] dwc2 ff580000.usb: irq 29, io mem 0xff580000
      [    2.416203] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.417015] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.417678] usb usb1: Product: DWC OTG Controller
      [    2.418114] usb usb1: Manufacturer: Linux 5.6.2 dwc2_hsotg
      [    2.418618] usb usb1: SerialNumber: ff580000.usb
      [    2.420127] hub 1-0:1.0: USB hub found
      [    2.420550] hub 1-0:1.0: 1 port detected
      [    2.422273] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
      [    2.422914] ehci-pci: EHCI PCI platform driver
      [    2.423418] ehci-platform: EHCI generic platform driver
      [    2.426594] ehci-platform ff5c0000.usb: EHCI Host Controller
      [    2.427168] ehci-platform ff5c0000.usb: new USB bus registered, assigned bus number 2
      [    2.428130] ehci-platform ff5c0000.usb: irq 30, io mem 0xff5c0000
      [    2.440797] ehci-platform ff5c0000.usb: USB 2.0 started, EHCI 1.00
      [    2.441824] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.442581] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.443244] usb usb2: Product: EHCI Host Controller
      [    2.443697] usb usb2: Manufacturer: Linux 5.6.2 ehci_hcd
      [    2.444194] usb usb2: SerialNumber: ff5c0000.usb
      [    2.445674] hub 2-0:1.0: USB hub found
      [    2.446088] hub 2-0:1.0: 1 port detected
      [    2.447323] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
      [    2.447942] ohci-platform: OHCI generic platform driver
      [    2.449122] ohci-platform ff5d0000.usb: Generic Platform OHCI controller
      [    2.449786] ohci-platform ff5d0000.usb: new USB bus registered, assigned bus number 3
      [    2.450750] ohci-platform ff5d0000.usb: irq 31, io mem 0xff5d0000
      [    2.513162] usb usb3: New USB device found, idVendor=1d6b, idProduct=0001, bcdDevice= 5.06
      [    2.513934] usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.514601] usb usb3: Product: Generic Platform OHCI controller
      [    2.515149] usb usb3: Manufacturer: Linux 5.6.2 ohci_hcd
      [    2.515643] usb usb3: SerialNumber: ff5d0000.usb
      [    2.517110] hub 3-0:1.0: USB hub found
      [    2.517544] hub 3-0:1.0: 1 port detected
      [    2.519626] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.520184] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 4
      [    2.521201] xhci-hcd xhci-hcd.0.auto: hcc params 0x0220fe64 hci version 0x110 quirks 0x0000000002010010
      [    2.522160] xhci-hcd xhci-hcd.0.auto: irq 166, io mem 0xff600000
      [    2.523539] usb usb4: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.06
      [    2.524307] usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.525031] usb usb4: Product: xHCI Host Controller
      [    2.525483] usb usb4: Manufacturer: Linux 5.6.2 xhci-hcd
      [    2.525971] usb usb4: SerialNumber: xhci-hcd.0.auto
      [    2.527461] hub 4-0:1.0: USB hub found
      [    2.527878] hub 4-0:1.0: 1 port detected
      [    2.528941] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.529481] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 5
      [    2.530205] xhci-hcd xhci-hcd.0.auto: Host supports USB 3.0 SuperSpeed
      [    2.530931] usb usb5: We don't know the algorithms for LPM for this host, disabling LPM.
      [    2.531892] usb usb5: New USB device found, idVendor=1d6b, idProduct=0003, bcdDevice= 5.06
      [    2.532648] usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.533352] usb usb5: Product: xHCI Host Controller
      [    2.533805] usb usb5: Manufacturer: Linux 5.6.2 xhci-hcd
      [    2.534292] usb usb5: SerialNumber: xhci-hcd.0.auto
      [    2.535788] hub 5-0:1.0: USB hub found
      [    2.536219] hub 5-0:1.0: 1 port detected
      [    2.537539] usbcore: registered new interface driver cdc_acm
      [    2.538078] cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
      [    2.538887] usbcore: registered new interface driver cdc_wdm
      [    2.539487] usbcore: registered new interface driver uas
      [    2.540196] usbcore: registered new interface driver usb-storage
      [    2.540958] usbcore: registered new interface driver usbserial_generic
      [    2.541604] usbserial: USB Serial support registered for generic
      [    2.542238] usbcore: registered new interface driver ch341
      [    2.542777] usbserial: USB Serial support registered for ch341-uart
      [    2.543433] usbcore: registered new interface driver cp210x
      [    2.543983] usbserial: USB Serial support registered for cp210x
      [    2.544672] usbcore: registered new interface driver ftdi_sio
      [    2.545271] usbserial: USB Serial support registered for FTDI USB Serial Device
      [    2.546308] usbcore: registered new interface driver option
      [    2.546852] usbserial: USB Serial support registered for GSM modem (1-port)
      [    2.547983] usbcore: registered new interface driver pl2303
      [    2.548529] usbserial: USB Serial support registered for pl2303
      [    2.549242] usbcore: registered new interface driver qcserial
      [    2.549826] usbserial: USB Serial support registered for Qualcomm USB modem
      [    2.551308] mousedev: PS/2 mouse device common for all mice
      [    2.552929] i2c /dev entries driver
      [    2.557297] rk808 1-0018: chip id: 0x8050
      [    2.565859] rk808-regulator rk808-regulator: there is no dvs0 gpio
      [    2.566490] rk808-regulator rk808-regulator: there is no dvs1 gpio
      [    2.567200] DCDC_REG1: supplied by vcc_sys
      [    2.570622] DCDC_REG2: supplied by vcc_sys
      [    2.572957] DCDC_REG3: supplied by vcc_sys
      [    2.573899] DCDC_REG4: supplied by vcc_sys
      [    2.575824] LDO_REG1: supplied by vcc_io
      [    2.579638] LDO_REG2: supplied by vcc_io
      [    2.583424] LDO_REG3: supplied by vcc_io
      [    2.597174] rk808-rtc rk808-rtc: registered as rtc0
      [    2.599861] input: rk805 pwrkey as /devices/platform/ff160000.i2c/i2c-1/1-0018/rk805-pwrkey/input/input0
      [    2.601982] IR NEC protocol handler initialized
      [    2.607539] rockchip-thermal ff250000.tsadc: Missing tshut mode property, using default (cru)
      [    2.608348] rockchip-thermal ff250000.tsadc: Missing tshut-polarity property, using default (low)
      [    2.611760] device-mapper: uevent: version 1.0.3
      [    2.612893] device-mapper: ioctl: 4.42.0-ioctl (2020-02-27) initialised: dm-devel@redhat.com
      [    2.619176] sdhci: Secure Digital Host Controller Interface driver
      [    2.619770] sdhci: Copyright(c) Pierre Ossman
      [    2.620170] Synopsys Designware Multimedia Card Interface Driver
      [    2.622171] dwmmc_rockchip ff500000.dwmmc: IDMAC supports 32-bit address mode.
      [    2.622888] dwmmc_rockchip ff500000.dwmmc: Using internal DMA controller.
      [    2.623520] dwmmc_rockchip ff500000.dwmmc: Version ID is 270a
      [    2.624155] dwmmc_rockchip ff500000.dwmmc: DW MMC controller at irq 27,32 bit host data width,256 deep fifo
      [    2.625168] vcc_sd: supplied by vcc_io
      [    2.644182] mmc_host mmc0: Bus speed (slot 0) = 400000Hz (slot req 400000Hz, actual 400000HZ div = 0)
      [    2.658538] sdhci-pltfm: SDHCI platform and OF driver helper
      [    2.661122] ledtrig-cpu: registered to indicate activity on CPUs
      [    2.662322] hid: raw HID events driver (C) Jiri Kosina
      [    2.663453] usbcore: registered new interface driver usbhid
      [    2.663975] usbhid: USB HID core driver
      [    2.669107] drop_monitor: Initializing network drop monitor service
      [    2.670089] Initializing XFRM netlink socket
      [    2.671721] NET: Registered protocol family 10
      [    2.674662] Segment Routing with IPv6
      [    2.678958] bpfilter: Loaded bpfilter_umh pid 233
      [    2.680098] NET: Registered protocol family 17
      [    2.681088] Bluetooth: RFCOMM TTY layer initialized
      [    2.681586] Bluetooth: RFCOMM socket layer initialized
      [    2.682110] Bluetooth: RFCOMM ver 1.11
      [    2.682522] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
      [    2.683076] Bluetooth: HIDP socket layer initialized
      [    2.683676] Key type dns_resolver registered
      [    2.685228] registered taskstats version 1
      [    2.685631] Loading compiled-in X.509 certificates
      [    2.686245] Key type ._fscrypt registered
      [    2.686633] Key type .fscrypt registered
      [    2.686995] Key type fscrypt-provisioning registered
      [    2.732463] friendlyelec-board board: Serial		: 37cd0f845b1d0156
      [    2.734679] input: gpio-keys as /devices/platform/gpio-keys/input/input1
      [    2.738244] rk808-rtc rk808-rtc: setting system clock to 2020-04-03T22:06:37 UTC (1585951597)
      [    2.740234] ALSA device list:
      [    2.740527]   No soundcards found.
      [    2.745276] Freeing unused kernel memory: 1344K
      [    2.745867] Run /init as init process
      [    2.746214]   with arguments:
      [    2.746220]     /init
      [    2.746224]     earlyprintk
      [    2.746231]   with environment:
      [    2.746237]     HOME=/
      [    2.746241]     TERM=linux
      [    2.800943] random: fast init done
      [    2.876961] usb 5-1: new SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [    2.898857] usb 5-1: New USB device found, idVendor=0bda, idProduct=8153, bcdDevice=31.00
      [    2.899621] usb 5-1: New USB device strings: Mfr=1, Product=2, SerialNumber=6
      [    2.900195] mmc_host mmc0: Bus speed (slot 0) = 100000000Hz (slot req 100000000Hz, actual 100000000HZ div = 0)
      [    2.900274] usb 5-1: Product: USB 10/100/1000 LAN
      [    2.901613] usb 5-1: Manufacturer: Realtek
      [    2.901987] usb 5-1: SerialNumber: 000000000000
      [    4.757019] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 91
      [    4.757741] mmc0: new ultra high speed SDR50 SDHC card at address aaaa
      [    4.760507] mmcblk0: mmc0:aaaa SL16G 14.8 GiB 
      [    4.769808]  mmcblk0: p1 p2
      [    7.890672] EXT4-fs (mmcblk0p2): mounted filesystem without journal. Opts: (null)
      [    8.609121] phy phy-ff450000.syscon:usb2-phy@100.0: charger = USB_DCP_CHARGER
      [    8.623210] systemd[1]: systemd 242 running in system mode. (+PAM +AUDIT +SELINUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +XZ +LZ4 +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=hybrid)
      [    8.627141] systemd[1]: Detected architecture arm64.
      [    8.672881] systemd[1]: Set hostname to <nanopi-r2s>.
      [    8.678411] systemd[1]: Failed to bump fs.file-max, ignoring: Invalid argument
      [    9.185372] systemd[1]: /lib/systemd/system/dbus.socket:4: ListenStream= references a path below legacy directory /var/run/, updating /var/run/dbus/system_bus_socket → /run/dbus/system_bus_socket; please update the unit file accordingly.
      [    9.336363] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.337855] systemd[1]: Listening on udev Kernel Socket.
      [    9.339764] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.341104] systemd[1]: Listening on udev Control Socket.
      [    9.342708] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.343756] systemd[1]: Listening on initctl Compatibility Named Pipe.
      [    9.361034] systemd[1]: Created slice system-systemd\x2dfsck.slice.
      [    9.374626] systemd[1]: Created slice system-serial\x2dgetty.slice.
      [    9.612899] EXT4-fs (mmcblk0p2): re-mounted. Opts: commit=600,errors=remount-ro
      [   10.863334] usbcore: registered new interface driver r8152
      [   11.027528] usb 5-1: reset SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [   11.063617] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Invalid ether addr 00:00:00:00:00:00
      [   11.064467] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether addr aa:27:6d:76:21:55
      [   11.089644] r8152 5-1:1.0: load rtl8153b-2 v1 10/23/19 successfully
      [   11.122323] r8152 5-1:1.0 eth1: v1.11.11
      [   11.219782] systemd-journald[298]: Received request to flush runtime journal from PID 1
      [   11.304070] EXT4-fs (mmcblk0p1): mounted filesystem with ordered data mode. Opts: (null)
      [   11.304116] ext4 filesystem being mounted at /boot supports timestamps until 2038 (0x7fffffff)
      [   11.591724] rk_gmac-dwmac ff540000.ethernet eth0: PHY [stmmac-0:00] driver [RTL8211E Gigabit Ethernet] (irq=POLL)
      [   11.602240] rk_gmac-dwmac ff540000.ethernet eth0: No Safety Features support found
      [   11.602264] rk_gmac-dwmac ff540000.ethernet eth0: PTP not supported by HW
      [   11.602280] rk_gmac-dwmac ff540000.ethernet eth0: configuring for phy/rgmii link mode
      [   12.695428] IPv6: ADDRCONF(NETDEV_CHANGE): eth1: link becomes ready
      [   12.697052] r8152 5-1:1.0 eth1: carrier on
      [   12.721754] zram: Added device: zram0
      [   12.724203] zram: Added device: zram1
      [   12.726561] zram: Added device: zram2
      [   12.728700] zram: Added device: zram3
      [   12.802395] zram0: detected capacity change from 0 to 128704512
      [   13.885047] Adding 125684k swap on /dev/zram0.  Priority:5 extents:1 across:125684k SSFS
      [   13.905601] zram1: detected capacity change from 0 to 128704512
      [   14.980893] Adding 125684k swap on /dev/zram1.  Priority:5 extents:1 across:125684k SSFS
      [   14.984883] zram2: detected capacity change from 0 to 128704512
      [   16.056895] Adding 125684k swap on /dev/zram2.  Priority:5 extents:1 across:125684k SSFS
      [   16.060382] zram3: detected capacity change from 0 to 128704512
      [   16.705666] rk_gmac-dwmac ff540000.ethernet eth0: Link is Up - 1Gbps/Full - flow control rx/tx
      [   16.705754] IPv6: ADDRCONF(NETDEV_CHANGE): eth0: link becomes ready
      [   17.132894] Adding 125684k swap on /dev/zram3.  Priority:5 extents:1 across:125684k SSFS
      [   27.568767] random: crng init done
      [   27.568780] random: 7 urandom warning(s) missed due to ratelimiting

