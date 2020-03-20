# Nanopi-r2s-ubuntu-server-minimal-image

Ubuntu 19.10 Server for NanoPi R2S

This is the base Image for a small router, based on Kernel 5.4.25 and up for the NanoPi R2S

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

**Mini router configuration**

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


# Status

* eth0 (ok)
* eth1 (ok)
* DVFS (seems ok)

# Cpu / Kernel Health

Checking the board health (manually)

      cat /sys/devices/virtual/thermal/thermal_zone0/temp
      38181
      cat /sys/devices/system/cpu/cpufreq/policy0/cpuinfo_cur_freq 
      408000
      cat /sys/devices/platform/ff160000.i2c/i2c-1/1-0018/regulator/regulator.8/microvolts 
      950000


# ChangeLog

* add Kernel 5.4.25 (initial commit)
* add support for rtl8821cu usb (v0.2)

# BootLog

      [    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
      [    0.000000] Linux version 5.4.25 (ubuntu@nanopi-r2s) (gcc version 9.2.1 20191008 (Ubuntu 9.2.1-9ubuntu2)) #1 SMP PREEMPT Sun Mar 15 13:03:04 UTC 2020
      [    0.000000] Machine model: FriendlyElec NanoPi R2S
      [    0.000000] efi: Getting EFI parameters from FDT:
      [    0.000000] efi: UEFI not found.
      [    0.000000] cma: Reserved 16 MiB at 0x000000003f000000
      [    0.000000] On node 0 totalpages: 261632
      [    0.000000]   DMA32 zone: 4088 pages used for memmap
      [    0.000000]   DMA32 zone: 0 pages reserved
      [    0.000000]   DMA32 zone: 261632 pages, LIFO batch:63
      [    0.000000] psci: probing for conduit method from DT.
      [    0.000000] psci: PSCIv1.0 detected in firmware.
      [    0.000000] psci: Using standard PSCI v0.2 function IDs
      [    0.000000] psci: MIGRATE_INFO_TYPE not supported.
      [    0.000000] psci: SMC Calling Convention v1.0
      [    0.000000] percpu: Embedded 32 pages/cpu s90280 r8192 d32600 u131072
      [    0.000000] pcpu-alloc: s90280 r8192 d32600 u131072 alloc=32*4096
      [    0.000000] pcpu-alloc: [0] 0 [0] 1 [0] 2 [0] 3 
      [    0.000000] Detected VIPT I-cache on CPU0
      [    0.000000] CPU features: detected: ARM erratum 845719
      [    0.000000] Built 1 zonelists, mobility grouping on.  Total pages: 257544
      [    0.000000] Kernel command line: earlyprintk root=/dev/mmcblk0p2 rw rootfstype=ext4 rootwait fsck.repair=yes panic=10 no_console_suspend consoleblank=0
      [    0.000000] Dentry cache hash table entries: 131072 (order: 8, 1048576 bytes, linear)
      [    0.000000] Inode-cache hash table entries: 65536 (order: 7, 524288 bytes, linear)
      [    0.000000] mem auto-init: stack:off, heap alloc:off, heap free:off
      [    0.000000] Memory: 986872K/1046528K available (12668K kernel code, 1548K rwdata, 4856K rodata, 1472K init, 784K bss, 43272K reserved, 16384K cma-reserved)
      [    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
      [    0.000000] ftrace: allocating 42845 entries in 168 pages
      [    0.000000] rcu: Preemptible hierarchical RCU implementation.
      [    0.000000] rcu: 	RCU restricting CPUs from NR_CPUS=8 to nr_cpu_ids=4.
      [    0.000000] 	Tasks RCU enabled.
      [    0.000000] rcu: RCU calculated value of scheduler-enlistment delay is 25 jiffies.
      [    0.000000] rcu: Adjusting geometry for rcu_fanout_leaf=16, nr_cpu_ids=4
      [    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
      [    0.000000] GIC: Using split EOI/Deactivate mode
      [    0.000000] random: get_random_bytes called from start_kernel+0x31c/0x4a4 with crng_init=0
      [    0.000000] arch_timer: cp15 timer(s) running at 24.00MHz (phys).
      [    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles: 0x588fe9dc0, max_idle_ns: 440795202592 ns
      [    0.000009] sched_clock: 56 bits at 24MHz, resolution 41ns, wraps every 4398046511097ns
      [    0.000872] Console: colour dummy device 80x25
      [    0.001577] printk: console [tty0] enabled
      [    0.001653] Calibrating delay loop (skipped), value calculated using timer frequency.. 48.00 BogoMIPS (lpj=96000)
      [    0.001698] pid_max: default: 32768 minimum: 301
      [    0.001922] LSM: Security Framework initializing
      [    0.002056] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.002101] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.027915] ASID allocator initialised with 32768 entries
      [    0.035888] rcu: Hierarchical SRCU implementation.
      [    0.047220] EFI services will not be available.
      [    0.056056] smp: Bringing up secondary CPUs ...
      [    0.088373] Detected VIPT I-cache on CPU1
      [    0.088468] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
      [    0.120539] Detected VIPT I-cache on CPU2
      [    0.120627] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
      [    0.152697] Detected VIPT I-cache on CPU3
      [    0.152784] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
      [    0.153010] smp: Brought up 1 node, 4 CPUs
      [    0.153163] SMP: Total of 4 processors activated.
      [    0.153197] CPU features: detected: 32-bit EL0 Support
      [    0.153230] CPU features: detected: CRC32 instructions
      [    0.172540] CPU: All CPU(s) started at EL2
      [    0.172681] alternatives: patching kernel code
      [    0.175119] devtmpfs: initialized
      [    0.191965] Registered cp15_barrier emulation handler
      [    0.192029] Registered setend emulation handler
      [    0.192770] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
      [    0.192843] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
      [    0.194557] pinctrl core: initialized pinctrl subsystem
      [    0.195625] DMI not present or invalid.
      [    0.196272] NET: Registered protocol family 16
      [    0.204068] DMA: preallocated 256 KiB pool for atomic allocations
      [    0.204140] audit: initializing netlink subsys (disabled)
      [    0.204503] audit: type=2000 audit(0.200:1): state=initialized audit_enabled=0 res=1
      [    0.206006] cpuidle: using governor ladder
      [    0.206101] cpuidle: using governor menu
      [    0.206589] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
      [    0.263430] HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
      [    0.263486] HugeTLB registered 32.0 MiB page size, pre-allocated 0 pages
      [    0.263517] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
      [    0.263547] HugeTLB registered 64.0 KiB page size, pre-allocated 0 pages
      [    0.270446] cryptd: max_cpu_qlen set to 1000
      [    0.290376] sdmmc-regulator GPIO handle specifies active low - ignored
      [    0.299554] iommu: Default domain type: Translated 
      [    0.301315] SCSI subsystem initialized
      [    0.301835] libata version 3.00 loaded.
      [    0.302263] usbcore: registered new interface driver usbfs
      [    0.302371] usbcore: registered new interface driver hub
      [    0.302548] usbcore: registered new device driver usb
      [    0.302676] mc: Linux media interface: v0.10
      [    0.302756] videodev: Linux video capture interface: v2.00
      [    0.302856] pps_core: LinuxPPS API ver. 1 registered
      [    0.302881] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
      [    0.302934] PTP clock support registered
      [    0.303730] Advanced Linux Sound Architecture Driver Initialized.
      [    0.304854] Bluetooth: Core ver 2.22
      [    0.304969] NET: Registered protocol family 31
      [    0.304995] Bluetooth: HCI device and connection manager initialized
      [    0.305038] Bluetooth: HCI socket layer initialized
      [    0.305076] Bluetooth: L2CAP socket layer initialized
      [    0.305145] Bluetooth: SCO socket layer initialized
      [    0.305201] NetLabel: Initializing
      [    0.305222] NetLabel:  domain hash size = 128
      [    0.305247] NetLabel:  protocols = UNLABELED CIPSOv4 CALIPSO
      [    0.305448] NetLabel:  unlabeled traffic allowed by default
      [    0.306689] clocksource: Switched to clocksource arch_sys_counter
      [    1.553585] VFS: Disk quotas dquot_6.6.0
      [    1.553742] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
      [    1.554077] FS-Cache: Loaded
      [    1.569426] thermal_sys: Registered thermal governor 'fair_share'
      [    1.569434] thermal_sys: Registered thermal governor 'step_wise'
      [    1.570260] NET: Registered protocol family 2
      [    1.571443] tcp_listen_portaddr_hash hash table entries: 512 (order: 2, 20480 bytes, linear)
      [    1.571558] TCP established hash table entries: 8192 (order: 4, 65536 bytes, linear)
      [    1.571705] TCP bind hash table entries: 8192 (order: 6, 262144 bytes, linear)
      [    1.572236] TCP: Hash tables configured (established 8192 bind 8192)
      [    1.572521] UDP hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.572668] UDP-Lite hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.573415] NET: Registered protocol family 1
      [    1.574546] RPC: Registered named UNIX socket transport module.
      [    1.574596] RPC: Registered udp transport module.
      [    1.574623] RPC: Registered tcp transport module.
      [    1.574647] RPC: Registered tcp NFSv4.1 backchannel transport module.
      [    1.574789] PCI: CLS 0 bytes, default 64
      [    1.575199] Trying to unpack rootfs image as initramfs...
      [    1.658122] Freeing initrd memory: 1076K
      [    1.659947] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 counters available
      [    1.678523] Initialise system trusted keyrings
      [    1.679165] workingset: timestamp_bits=46 max_order=18 bucket_order=0
      [    1.694063] squashfs: version 4.0 (2009/01/31) Phillip Lougher
      [    1.694777] FS-Cache: Netfs 'nfs' registered for caching
      [    1.695968] NFS: Registering the id_resolver key type
      [    1.696062] Key type id_resolver registered
      [    1.696087] Key type id_legacy registered
      [    1.696132] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
      [    1.696622] fuse: init (API version 7.31)
      [    1.722619] Key type asymmetric registered
      [    1.722710] Asymmetric key parser 'x509' registered
      [    1.722839] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 247)
      [    1.723191] io scheduler mq-deadline registered
      [    1.723228] io scheduler kyber registered
      [    1.731143] rockchip-u3phy ff470000.usb3-phy: Rockchip u3phy initialized successfully
      [    1.737341] dma-pl330 ff1f0000.dmac: Loaded driver for PL330 DMAC-241330
      [    1.737395] dma-pl330 ff1f0000.dmac: 	DBUFF-128x8bytes Num_Chans-8 Num_Peri-20 Num_Events-16
      [    1.738424] Serial: 8250/16550 driver, 5 ports, IRQ sharing disabled
      [    1.741577] ff130000.serial: ttyS2 at MMIO 0xff130000 (irq = 12, base_baud = 1500000) is a 16550A
      [    1.812688] printk: console [ttyS2] enabled
      [    1.817083] rockchip-drm display-subsystem: [drm:rockchip_drm_platform_probe] *ERROR* No available vop found for display-subsystem.
      [    1.831657] brd: module loaded
      [    1.851984] loop: module loaded
      [    1.855236] libphy: Fixed MDIO Bus: probed
      [    1.857206] rk_gmac-dwmac ff540000.ethernet: IRQ eth_wake_irq not found
      [    1.857840] rk_gmac-dwmac ff540000.ethernet: IRQ eth_lpi not found
      [    1.858618] rk_gmac-dwmac ff540000.ethernet: PTP uses main clock
      [    1.859438] rk_gmac-dwmac ff540000.ethernet: clock input or output? (input).
      [    1.860095] rk_gmac-dwmac ff540000.ethernet: TX delay(0x24).
      [    1.860625] rk_gmac-dwmac ff540000.ethernet: RX delay(0x18).
      [    1.861167] rk_gmac-dwmac ff540000.ethernet: integrated PHY? (no).
      [    1.861859] rk_gmac-dwmac ff540000.ethernet: cannot get clock clk_mac_speed
      [    1.862494] rk_gmac-dwmac ff540000.ethernet: clock input from PHY
      [    1.868110] rk_gmac-dwmac ff540000.ethernet: init for RGMII
      [    1.869019] rk_gmac-dwmac ff540000.ethernet: User ID: 0x10, Synopsys ID: 0x35
      [    1.869691] rk_gmac-dwmac ff540000.ethernet: 	DWMAC1000
      [    1.870178] rk_gmac-dwmac ff540000.ethernet: DMA HW capability register supported
      [    1.870913] rk_gmac-dwmac ff540000.ethernet: RX Checksum Offload Engine supported
      [    1.871606] rk_gmac-dwmac ff540000.ethernet: COE Type 2
      [    1.872092] rk_gmac-dwmac ff540000.ethernet: TX Checksum insertion supported
      [    1.872735] rk_gmac-dwmac ff540000.ethernet: Wake-Up On Lan supported
      [    1.873384] rk_gmac-dwmac ff540000.ethernet: Normal descriptors
      [    1.873931] rk_gmac-dwmac ff540000.ethernet: Ring mode enabled
      [    1.874470] rk_gmac-dwmac ff540000.ethernet: Enable RX Mitigation via HW Watchdog Timer
      [    1.934706] libphy: stmmac: probed
      [    1.938305] PPP generic driver version 2.4.2
      [    1.939214] usbcore: registered new interface driver asix
      [    1.939807] usbcore: registered new interface driver ax88179_178a
      [    1.940421] usbcore: registered new interface driver cdc_ether
      [    1.941020] usbcore: registered new interface driver qmi_wwan
      [    1.943908] dwc3 ff600000.dwc3: Failed to get clk 'ref': -2
      [    1.944653] phy phy-ff470000.usb3-phy.2: u3phy u2 power on
      [    1.945199] phy phy-ff470000.usb3-phy.3: u3phy u3 power on
      [    1.947177] dwc2 ff580000.usb: ff580000.usb supply vusb_d not found, using dummy regulator
      [    1.948115] dwc2 ff580000.usb: ff580000.usb supply vusb_a not found, using dummy regulator
      [    2.078809] dwc2 ff580000.usb: EPs: 10, dedicated fifos, 972 entries in SPRAM
      [    2.080369] dwc2 ff580000.usb: DWC OTG Controller
      [    2.080864] dwc2 ff580000.usb: new USB bus registered, assigned bus number 1
      [    2.081570] dwc2 ff580000.usb: irq 29, io mem 0xff580000
      [    2.082405] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.04
      [    2.083222] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.083885] usb usb1: Product: DWC OTG Controller
      [    2.084327] usb usb1: Manufacturer: Linux 5.4.25 dwc2_hsotg
      [    2.084838] usb usb1: SerialNumber: ff580000.usb
      [    2.086289] hub 1-0:1.0: USB hub found
      [    2.086758] hub 1-0:1.0: 1 port detected
      [    2.088407] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
      [    2.089043] ehci-pci: EHCI PCI platform driver
      [    2.089562] ehci-platform: EHCI generic platform driver
      [    2.092689] ehci-platform ff5c0000.usb: EHCI Host Controller
      [    2.093270] ehci-platform ff5c0000.usb: new USB bus registered, assigned bus number 2
      [    2.094213] ehci-platform ff5c0000.usb: irq 30, io mem 0xff5c0000
      [    2.110718] ehci-platform ff5c0000.usb: USB 2.0 started, EHCI 1.00
      [    2.111792] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.04
      [    2.112553] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.113221] usb usb2: Product: EHCI Host Controller
      [    2.113671] usb usb2: Manufacturer: Linux 5.4.25 ehci_hcd
      [    2.114168] usb usb2: SerialNumber: ff5c0000.usb
      [    2.115685] hub 2-0:1.0: USB hub found
      [    2.116107] hub 2-0:1.0: 1 port detected
      [    2.117330] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
      [    2.117957] ohci-platform: OHCI generic platform driver
      [    2.119064] ohci-platform ff5d0000.usb: Generic Platform OHCI controller
      [    2.119725] ohci-platform ff5d0000.usb: new USB bus registered, assigned bus number 3
      [    2.120695] ohci-platform ff5d0000.usb: irq 31, io mem 0xff5d0000
      [    2.183066] usb usb3: New USB device found, idVendor=1d6b, idProduct=0001, bcdDevice= 5.04
      [    2.183843] usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.184504] usb usb3: Product: Generic Platform OHCI controller
      [    2.185056] usb usb3: Manufacturer: Linux 5.4.25 ohci_hcd
      [    2.185553] usb usb3: SerialNumber: ff5d0000.usb
      [    2.187081] hub 3-0:1.0: USB hub found
      [    2.187499] hub 3-0:1.0: 1 port detected
      [    2.189540] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.190104] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 4
      [    2.191157] xhci-hcd xhci-hcd.0.auto: hcc params 0x0220fe64 hci version 0x110 quirks 0x0000000002010010
      [    2.192126] xhci-hcd xhci-hcd.0.auto: irq 166, io mem 0xff600000
      [    2.193463] usb usb4: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.04
      [    2.194223] usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.194940] usb usb4: Product: xHCI Host Controller
      [    2.195392] usb usb4: Manufacturer: Linux 5.4.25 xhci-hcd
      [    2.195888] usb usb4: SerialNumber: xhci-hcd.0.auto
      [    2.197362] hub 4-0:1.0: USB hub found
      [    2.197783] hub 4-0:1.0: 1 port detected
      [    2.198878] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.199417] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 5
      [    2.200135] xhci-hcd xhci-hcd.0.auto: Host supports USB 3.0 SuperSpeed
      [    2.200881] usb usb5: We don't know the algorithms for LPM for this host, disabling LPM.
      [    2.201852] usb usb5: New USB device found, idVendor=1d6b, idProduct=0003, bcdDevice= 5.04
      [    2.202608] usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.203320] usb usb5: Product: xHCI Host Controller
      [    2.203772] usb usb5: Manufacturer: Linux 5.4.25 xhci-hcd
      [    2.204269] usb usb5: SerialNumber: xhci-hcd.0.auto
      [    2.205699] hub 5-0:1.0: USB hub found
      [    2.206113] hub 5-0:1.0: 1 port detected
      [    2.207428] usbcore: registered new interface driver cdc_acm
      [    2.207972] cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
      [    2.208775] usbcore: registered new interface driver cdc_wdm
      [    2.209387] usbcore: registered new interface driver uas
      [    2.210103] usbcore: registered new interface driver usb-storage
      [    2.210888] usbcore: registered new interface driver usbserial_generic
      [    2.211533] usbserial: USB Serial support registered for generic
      [    2.212175] usbcore: registered new interface driver ch341
      [    2.212714] usbserial: USB Serial support registered for ch341-uart
      [    2.213373] usbcore: registered new interface driver cp210x
      [    2.213914] usbserial: USB Serial support registered for cp210x
      [    2.214608] usbcore: registered new interface driver ftdi_sio
      [    2.215195] usbserial: USB Serial support registered for FTDI USB Serial Device
      [    2.216247] usbcore: registered new interface driver option
      [    2.216794] usbserial: USB Serial support registered for GSM modem (1-port)
      [    2.217991] usbcore: registered new interface driver pl2303
      [    2.218542] usbserial: USB Serial support registered for pl2303
      [    2.219253] usbcore: registered new interface driver qcserial
      [    2.219835] usbserial: USB Serial support registered for Qualcomm USB modem
      [    2.221343] mousedev: PS/2 mouse device common for all mice
      [    2.222982] i2c /dev entries driver
      [    2.227316] rk808 1-0018: chip id: 0x8050
      [    2.234367] rk808-regulator rk808-regulator: there is no dvs0 gpio
      [    2.235059] rk808-regulator rk808-regulator: there is no dvs1 gpio
      [    2.235768] DCDC_REG1: supplied by vcc_sys
      [    2.239177] DCDC_REG2: supplied by vcc_sys
      [    2.241456] DCDC_REG3: supplied by vcc_sys
      [    2.242389] DCDC_REG4: supplied by vcc_sys
      [    2.244414] LDO_REG1: supplied by vcc_io
      [    2.248205] LDO_REG2: supplied by vcc_io
      [    2.252040] LDO_REG3: supplied by vcc_io
      [    2.265643] rk808-rtc rk808-rtc: registered as rtc0
      [    2.268337] input: rk805 pwrkey as /devices/platform/ff160000.i2c/i2c-1/1-0018/rk805-pwrkey/input/input0
      [    2.270389] IR NEC protocol handler initialized
      [    2.276227] rockchip-thermal ff250000.tsadc: Missing tshut mode property, using default (cru)
      [    2.277043] rockchip-thermal ff250000.tsadc: Missing tshut-polarity property, using default (low)
      [    2.280234] device-mapper: uevent: version 1.0.3
      [    2.281269] device-mapper: ioctl: 4.41.0-ioctl (2019-09-16) initialised: dm-devel@redhat.com
      [    2.287330] sdhci: Secure Digital Host Controller Interface driver
      [    2.287925] sdhci: Copyright(c) Pierre Ossman
      [    2.288333] Synopsys Designware Multimedia Card Interface Driver
      [    2.290082] dwmmc_rockchip ff500000.dwmmc: IDMAC supports 32-bit address mode.
      [    2.290930] dwmmc_rockchip ff500000.dwmmc: Using internal DMA controller.
      [    2.291576] dwmmc_rockchip ff500000.dwmmc: Version ID is 270a
      [    2.292218] dwmmc_rockchip ff500000.dwmmc: DW MMC controller at irq 27,32 bit host data width,256 deep fifo
      [    2.293201] vcc_sd: supplied by vcc_io
      [    2.312332] mmc_host mmc0: Bus speed (slot 0) = 400000Hz (slot req 400000Hz, actual 400000HZ div = 0)
      [    2.326652] sdhci-pltfm: SDHCI platform and OF driver helper
      [    2.329604] ledtrig-cpu: registered to indicate activity on CPUs
      [    2.330978] hidraw: raw HID events driver (C) Jiri Kosina
      [    2.332198] usbcore: registered new interface driver usbhid
      [    2.332734] usbhid: USB HID core driver
      [    2.340493] drop_monitor: Initializing network drop monitor service
      [    2.341390] Initializing XFRM netlink socket
      [    2.343165] NET: Registered protocol family 10
      [    2.345728] Segment Routing with IPv6
      [    2.349574] bpfilter: Loaded bpfilter_umh pid 234
      [    2.350564] NET: Registered protocol family 17
      [    2.351395] Bluetooth: RFCOMM TTY layer initialized
      [    2.351892] Bluetooth: RFCOMM socket layer initialized
      [    2.352413] Bluetooth: RFCOMM ver 1.11
      [    2.352786] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
      [    2.353339] Bluetooth: HIDP socket layer initialized
      [    2.353944] Key type dns_resolver registered
      [    2.355388] registered taskstats version 1
      [    2.355821] Loading compiled-in X.509 certificates
      [    2.356502] Key type ._fscrypt registered
      [    2.356893] Key type .fscrypt registered
      [    2.401791] friendlyelec-board board: Serial		: 37cd0f845b1d0156
      [    2.403459] rk3328-dmc-freq dmc: current ATF version 0x101
      [    2.409508] input: gpio-keys as /devices/platform/gpio-keys/input/input1
      [    2.412490] rk808-rtc rk808-rtc: setting system clock to 2020-03-15T22:51:02 UTC (1584312662)
      [    2.414399] ALSA device list:
      [    2.414751]   No soundcards found.
      [    2.420507] Freeing unused kernel memory: 1472K
      [    2.421064] Run /init as init process
      [    2.495310] random: fast init done
      [    2.542822] usb 5-1: new SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [    2.563908] usb 5-1: New USB device found, idVendor=0bda, idProduct=8153, bcdDevice=31.00
      [    2.564672] usb 5-1: New USB device strings: Mfr=1, Product=2, SerialNumber=6
      [    2.565315] usb 5-1: Product: USB 10/100/1000 LAN
      [    2.565764] usb 5-1: Manufacturer: Realtek
      [    2.566154] usb 5-1: SerialNumber: 000000000000
      [    2.576033] mmc_host mmc0: Bus speed (slot 0) = 100000000Hz (slot req 100000000Hz, actual 100000000HZ div = 0)
      [    2.780251] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 113
      [    2.780941] mmc0: new ultra high speed SDR50 SDHC card at address aaaa
      [    2.783008] mmcblk0: mmc0:aaaa SL16G 14.8 GiB 
      [    2.792068]  mmcblk0: p1 p2
      [    7.549389] EXT4-fs (mmcblk0p2): mounted filesystem without journal. Opts: (null)
      [    8.257155] systemd[1]: systemd 242 running in system mode. (+PAM +AUDIT +SELINUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +XZ +LZ4 +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=hybrid)
      [    8.261224] systemd[1]: Detected architecture arm64.
      [    8.313610] systemd[1]: Set hostname to <nanopi-r2s>.
      [    8.317810] systemd[1]: Failed to bump fs.file-max, ignoring: Invalid argument
      [    8.358978] phy phy-ff450000.syscon:usb2-phy@100.0: charger = USB_DCP_CHARGER
      [    8.801734] systemd[1]: /lib/systemd/system/dbus.socket:4: ListenStream= references a path below legacy directory /var/run/, updating /var/run/dbus/system_bus_socket → /run/dbus/system_bus_socket; please update the unit file accordingly.
      [    8.945858] random: systemd: uninitialized urandom read (16 bytes read)
      [    8.947225] systemd[1]: Listening on Syslog Socket.
      [    8.949031] random: systemd: uninitialized urandom read (16 bytes read)
      [    8.950059] systemd[1]: Listening on initctl Compatibility Named Pipe.
      [    8.962881] random: systemd: uninitialized urandom read (16 bytes read)
      [    8.966176] systemd[1]: Created slice User and Session Slice.
      [    8.967919] systemd[1]: Reached target Swap.
      [    8.981732] systemd[1]: Created slice system-serial\x2dgetty.slice.
      [    9.181237] EXT4-fs (mmcblk0p2): re-mounted. Opts: commit=600,errors=remount-ro
      [   10.279549] usbcore: registered new interface driver r8152
      [   10.441251] usb 5-1: reset SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [   10.476913] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Invalid ether addr 00:00:00:00:00:00
      [   10.477758] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether addr e2:4b:59:31:d3:ec
      [   10.512249] r8152 5-1:1.0 eth1: v1.10.11
      [   10.726049] systemd-journald[304]: Received request to flush runtime journal from PID 1
      [   10.816883] EXT4-fs (mmcblk0p1): mounted filesystem with ordered data mode. Opts: (null)
      [   10.816924] ext4 filesystem being mounted at /boot supports timestamps until 2038 (0x7fffffff)
      [   11.155811] rk_gmac-dwmac ff540000.ethernet eth0: PHY [stmmac-0:00] driver [RTL8211E Gigabit Ethernet]
      [   11.166773] rk_gmac-dwmac ff540000.ethernet eth0: No Safety Features support found
      [   11.166800] rk_gmac-dwmac ff540000.ethernet eth0: PTP not supported by HW
      [   11.166816] rk_gmac-dwmac ff540000.ethernet eth0: configuring for phy/rgmii link mode
      [   12.300739] zram: Added device: zram0
      [   12.301758] zram: Added device: zram1
      [   12.302913] zram: Added device: zram2
      [   12.305773] zram: Added device: zram3
      [   12.385906] zram0: detected capacity change from 0 to 128745472
      [   12.982921] random: crng init done
      [   12.982938] random: 7 urandom warning(s) missed due to ratelimiting
      [   13.114828] Adding 125724k swap on /dev/zram0.  Priority:5 extents:1 across:125724k SSFS
      [   13.117585] zram1: detected capacity change from 0 to 128745472
      [   13.174778] Adding 125724k swap on /dev/zram1.  Priority:5 extents:1 across:125724k SSFS
      [   13.177354] zram2: detected capacity change from 0 to 128745472
      [   13.226796] Adding 125724k swap on /dev/zram2.  Priority:5 extents:1 across:125724k SSFS
      [   13.229796] zram3: detected capacity change from 0 to 128745472
      [   13.278809] Adding 125724k swap on /dev/zram3.  Priority:5 extents:1 across:125724k SSFS
      [   14.122525] IPv6: ADDRCONF(NETDEV_CHANGE): eth1: link becomes ready
      [   14.123609] r8152 5-1:1.0 eth1: carrier on


