# Nanopi-r2s-ubuntu-server-minimal-image

Ubuntu 19.10 Server for NanoPi R2S

Ubuntu 20.04 LTS for NanoPi R2S Mainline Kernel 5.7.y

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

* [v0.7i - Kernel 5.7.0-rc3 (2GB Image)](#v07i---kernel-570-rc3-image)

* [v0.7s - Boost to 1.5 GHz](#v07s---boost-to-15-GHz)

* [v0.8 - Kernel 5.7.0 linux-image](#v08---mainline-kernel-570)

* [v0.9 - Kernel 5.7.1 linux-image](#v09---stable-kernel-571)

* [v0.92 - Kernel 5.7.2 linux-image](#v092---stable-kernel-572)

* [v0.93 - Kernel 5.8.0-rc1 - Testing](#v093---kernel-580-rc1) - Ext4 BUG fix

* [v0.94 - Kernel 5.8.0-rc3 - Testing](#v094---kernel-580-rc3)

* [v0.95 - Kernel 5.8.0](#v095---kernel-580)

* [v0.96 - Kernel 5.8.1](#v096---kernel-581)

* [v0.97 - Kernel 5.9.0 RC1](#v097---kernel-590-rc)

* [v0.98 - Kernel 5.9.0 RC8](#v098---kernel-590-rc8)

* [pwm0 - fan speed control](#controlling-fan-speed-control-with-pwm0)

* [v0.99 - Kernel 5.10.0 RC1](#v099---kernel-5100-rc1)

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


## v0.7s - Boost to 1.5 GHz

It is safe to boost the NanoPi R2S to 1.5 GHz.

**Instructions:**
https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.7s


## v0.8 - Mainline Kernel 5.7.0

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.8

* **Update to Mainline Kernel 5.7.0** Instructions


      alex@svn:~/Downloads/arm/temp/linux-image-r2s$ssh ubuntu@192.168.254.28
      ubuntu@192.168.254.28's password: 
      Welcome to Ubuntu 20.04 LTS (GNU/Linux 5.7.0-rc3 aarch64)

       * Documentation:  https://help.ubuntu.com
       * Management:     https://landscape.canonical.com
       * Support:        https://ubuntu.com/advantage

      Last login: Mon Jun  1 21:27:16 2020 from 192.168.254.253
      ubuntu@nanopi-r2s:~$ uname -ra
      Linux nanopi-r2s 5.7.0-rc3 #1 SMP PREEMPT Fri May 1 19:05:56 UTC 2020 aarch64 aarch64 aarch64 GNU/Linux
      ubuntu@nanopi-r2s:~$ sudo dpkg -i linux-image-5.7.0_1.0-4.deb 
      [sudo] password for ubuntu: 
      Selecting previously unselected package linux-image-5.7.0.
      (Reading database ... 27521 files and directories currently installed.)
      Preparing to unpack linux-image-5.7.0_1.0-4.deb ...
      INFO: Updating Kernel 5.7.0-rc3 to 5.7.0
      INFO: Updating...
      Unpacking linux-image-5.7.0 (1.0-4) ...
      Setting up linux-image-5.7.0 (1.0-4) ...
      OK: Kernel update success! Please reboot with: sync && sudo reboot
      ubuntu@nanopi-r2s:~$ sync && sudo reboot
      alex@svn:~/Downloads/arm/temp/linux-image-r2s$ ssh ubuntu@192.168.254.28
      ssh: connect to host 192.168.254.28 port 22: Connection refused
      alex@svn:~/Downloads/arm/temp/linux-image-r2s$ ssh ubuntu@192.168.254.28
      ubuntu@192.168.254.28's password: 
      Welcome to Ubuntu 20.04 LTS (GNU/Linux 5.7.0 aarch64)

       * Documentation:  https://help.ubuntu.com
       * Management:     https://landscape.canonical.com
       * Support:        https://ubuntu.com/advantage

      Last login: Mon Jun  1 21:51:41 2020 from 192.168.254.253
      ubuntu@nanopi-r2s:~$ uname -ra
      Linux nanopi-r2s 5.7.0 #1 SMP PREEMPT Mon Jun 1 18:36:08 UTC 2020 aarch64 aarch64 aarch64 GNU/Linux
      ubuntu@nanopi-r2s:~$ ifconfig
      eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
              inet 192.168.254.28  netmask 255.255.0.0  broadcast 192.168.255.255
              inet6 2804:7f4:3582:7134:48c0:a9ff:fe05:7e21  prefixlen 64  scopeid 0x0<global>
              inet6 fe80::48c0:a9ff:fe05:7e21  prefixlen 64  scopeid 0x20<link>
              ether 4a:c0:a9:05:7e:21  txqueuelen 1000  (Ethernet)
              RX packets 113  bytes 13611 (13.6 KB)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 80  bytes 10844 (10.8 KB)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
              device interrupt 28  

      eth1: flags=4099<UP,BROADCAST,MULTICAST>  mtu 1500
              inet 192.168.1.1  netmask 255.255.255.0  broadcast 192.168.1.255
              ether 36:74:22:27:e5:47  txqueuelen 1000  (Ethernet)
              RX packets 0  bytes 0 (0.0 B)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 0  bytes 0 (0.0 B)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

      lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
              inet 127.0.0.1  netmask 255.0.0.0
              inet6 ::1  prefixlen 128  scopeid 0x10<host>
              loop  txqueuelen 1000  (Local Loopback)
              RX packets 80  bytes 5920 (5.9 KB)
              RX errors 0  dropped 0  overruns 0  frame 0
              TX packets 80  bytes 5920 (5.9 KB)
              TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

      ubuntu@nanopi-r2s:~$ lsmod
      Module                  Size  Used by
      r8152                  86016  0
      crct10dif_ce           20480  1
      uio_pdrv_genirq        16384  0
      uio                    24576  1 uio_pdrv_genirq
      sch_fq_codel           20480  3
      ip_tables              32768  0
      x_tables               36864  1 ip_tables

* Benchmarking NanoPi R2S (Ubuntu 20.04 LTS)


	      ubuntu@nanopi-r2s:~$ 7z b

	      7-Zip [64] 16.02 : Copyright (c) 1999-2016 Igor Pavlov : 2016-05-21
	      p7zip Version 16.02 (locale=C.UTF-8,Utf16=on,HugeFiles=on,64 bits,4 CPUs LE)

	      LE
	      CPU Freq: - - - - - - - - -

	      RAM size:     981 MB,  # CPU hardware threads:   4
	      RAM usage:    882 MB,  # Benchmark threads:      4

				     Compressing  |                  Decompressing
	      Dict     Speed Usage    R/U Rating  |      Speed Usage    R/U Rating
		       KiB/s     %   MIPS   MIPS  |      KiB/s     %   MIPS   MIPS

	      22:       1756   335    511   1708  |      52699   399   1126   4496
	      23:       1704   346    503   1736  |      50621   399   1098   4380
	      24:       1681   357    506   1808  |      48775   398   1075   4282
	      25:       1554   357    497   1775  |      46682   398   1043   4155
	      ----------------------------------  | ------------------------------
	      Avr:             349    504   1757  |              399   1086   4328
	      Tot:             374    795   3043
	      ubuntu@nanopi-r2s:~$ openssl speed -elapsed -evp aes-128-gcm aes-128-cbc sha256
	      You have chosen to measure elapsed time instead of user CPU time.
	      Doing sha256 for 3s on 16 size blocks: 9157906 sha256's in 3.00s
	      Doing sha256 for 3s on 64 size blocks: 7005608 sha256's in 3.00s
	      Doing sha256 for 3s on 256 size blocks: 4197370 sha256's in 3.00s
	      Doing sha256 for 3s on 1024 size blocks: 1604346 sha256's in 3.00s
	      Doing sha256 for 3s on 8192 size blocks: 238620 sha256's in 3.00s
	      Doing sha256 for 3s on 16384 size blocks: 120819 sha256's in 3.00s
	      Doing aes-128 cbc for 3s on 16 size blocks: 10272884 aes-128 cbc's in 3.00s
	      Doing aes-128 cbc for 3s on 64 size blocks: 2789016 aes-128 cbc's in 3.00s
	      Doing aes-128 cbc for 3s on 256 size blocks: 717614 aes-128 cbc's in 3.00s
	      Doing aes-128 cbc for 3s on 1024 size blocks: 180497 aes-128 cbc's in 3.00s
	      Doing aes-128 cbc for 3s on 8192 size blocks: 22631 aes-128 cbc's in 3.00s
	      Doing aes-128 cbc for 3s on 16384 size blocks: 11311 aes-128 cbc's in 3.00s
	      Doing aes-128-gcm for 3s on 16 size blocks: 15047618 aes-128-gcm's in 3.00s
	      Doing aes-128-gcm for 3s on 64 size blocks: 10948206 aes-128-gcm's in 3.00s
	      Doing aes-128-gcm for 3s on 256 size blocks: 5234187 aes-128-gcm's in 3.00s
	      Doing aes-128-gcm for 3s on 1024 size blocks: 1714462 aes-128-gcm's in 3.00s
	      Doing aes-128-gcm for 3s on 8192 size blocks: 233941 aes-128-gcm's in 3.00s
	      Doing aes-128-gcm for 3s on 16384 size blocks: 117441 aes-128-gcm's in 3.00s
	      OpenSSL 1.1.1f  31 Mar 2020
	      built on: Mon Apr 20 11:53:50 2020 UTC
	      options:bn(64,64) rc4(char) des(int) aes(partial) blowfish(ptr) 
	      compiler: gcc -fPIC -pthread -Wa,--noexecstack -Wall -Wa,--noexecstack -g -O2 -fdebug-prefix-map=/build/openssl-9j6sUa/openssl-1.1.1f=. -fstack-protector-strong -Wformat -Werror=format-security -DOPENSSL_TLS_SECURITY_LEVEL=2 -DOPENSSL_USE_NODELETE -DOPENSSL_PIC -DOPENSSL_CPUID_OBJ -DOPENSSL_BN_ASM_MONT -DSHA1_ASM -DSHA256_ASM -DSHA512_ASM -DKECCAK1600_ASM -DVPAES_ASM -DECP_NISTZ256_ASM -DPOLY1305_ASM -DNDEBUG -Wdate-time -D_FORTIFY_SOURCE=2
	      The 'numbers' are in 1000s of bytes per second processed.
	      type             16 bytes     64 bytes    256 bytes   1024 bytes   8192 bytes  16384 bytes
	      aes-128 cbc      54788.71k    59499.01k    61236.39k    61609.64k    61797.72k    61773.14k
	      aes-128-gcm      80253.96k   233561.73k   446650.62k   585203.03k   638814.89k   641384.45k
	      sha256           48842.17k   149452.97k   358175.57k   547616.77k   651591.68k   659832.83k
	      ubuntu@nanopi-r2s:~$


## v0.9 - Stable Kernel 5.7.1

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.9

**Bump to 5.7.2**

* **Update to Mainline Kernel 5.7.1** Instructions


		ubuntu@nanopi-r2s:~$ uname -ra
		Linux nanopi-r2s 5.7.0 #1 SMP PREEMPT Mon Jun 1 18:36:08 UTC 2020 aarch64 aarch64 aarch64 GNU/Linux
		ubuntu@nanopi-r2s:~$ sudo dpkg -i linux-image-5.7.1_1.0-5.deb 
		[sudo] password for ubuntu: 
		Selecting previously unselected package linux-image-5.7.1.
		(Reading database ... 30596 files and directories currently installed.)
		Preparing to unpack linux-image-5.7.1_1.0-5.deb ...
		INFO: Updating Kernel 5.7.0 to 5.7.1
		INFO: Updating...
		Unpacking linux-image-5.7.1 (1.0-5) ...
		Setting up linux-image-5.7.1 (1.0-5) ...
		OK: Kernel update success! Please reboot with: sync && sudo reboot
		ubuntu@nanopi-r2s:~$ sync && sudo reboot
		Connection to 192.168.254.28 closed by remote host.
		Connection to 192.168.254.28 closed.
		alex@svn:~$ ssh ubuntu@192.168.254.28
		ubuntu@192.168.254.28's password: 
		Welcome to Ubuntu 20.04 LTS (GNU/Linux 5.7.1 aarch64)

		 * Documentation:  https://help.ubuntu.com
		 * Management:     https://landscape.canonical.com
		 * Support:        https://ubuntu.com/advantage

		Last login: Wed Jun 10 23:16:02 2020 from 192.168.254.253
		ubuntu@nanopi-r2s:~$ uname -ra
		Linux nanopi-r2s 5.7.1 #1 SMP PREEMPT Wed Jun 10 16:33:02 UTC 2020 aarch64 aarch64 aarch64 GNU/Linux

## v0.92 - Stable Kernel 5.7.2

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.92

* Update with:

		ubuntu@nanopi-r2s:~$ sudo dpkg -i linux-image-5.7.2_1.0-6.deb 
		[sudo] password for ubuntu: 
		Selecting previously unselected package linux-image-5.7.2.
		(Reading database ... 32256 files and directories currently installed.)
		Preparing to unpack linux-image-5.7.2_1.0-6.deb ...
		INFO: Updating Kernel 5.7.1 to 5.7.2
		INFO: Updating...
		Unpacking linux-image-5.7.2 (1.0-6) ...
		Setting up linux-image-5.7.2 (1.0-6) ...
		OK: Kernel update success! Please reboot with: sync && sudo reboot
		ubuntu@nanopi-r2s:~$ sync && sudo reboot
		Connection to 192.168.254.28 closed by remote host.
		Connection to 192.168.254.28 closed.
		alex@svn:~/Downloads/arm/temp/linux-image-r2s$ ssh ubuntu@192.168.254.28
		ubuntu@192.168.254.28's password: 
		Welcome to Ubuntu 20.04 LTS (GNU/Linux 5.7.2 aarch64)

		 * Documentation:  https://help.ubuntu.com
		 * Management:     https://landscape.canonical.com
		 * Support:        https://ubuntu.com/advantage

		Last login: Thu Jun 11 22:29:48 2020 from 192.168.254.253
		ubuntu@nanopi-r2s:~$ uname -ra
		Linux nanopi-r2s 5.7.2 #1 SMP PREEMPT Thu Jun 11 16:07:17 UTC 2020 aarch64 aarch64 aarch64 GNU/Linux
		ubuntu@nanopi-r2s:~$ 

* Benchmark

		openssl speed -elapsed -evp aes-128-gcm aes-128-cbc sha256 rsa2048
		You have chosen to measure elapsed time instead of user CPU time.
		Doing sha256 for 3s on 16 size blocks: 9122873 sha256's in 3.00s
		Doing sha256 for 3s on 64 size blocks: 7017831 sha256's in 3.00s
		Doing sha256 for 3s on 256 size blocks: 4204660 sha256's in 3.00s
		Doing sha256 for 3s on 1024 size blocks: 1606222 sha256's in 3.00s
		Doing sha256 for 3s on 8192 size blocks: 238559 sha256's in 3.00s
		Doing sha256 for 3s on 16384 size blocks: 120868 sha256's in 3.00s
		Doing aes-128 cbc for 3s on 16 size blocks: 10255999 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 64 size blocks: 2788401 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 256 size blocks: 717431 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 1024 size blocks: 180434 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 8192 size blocks: 22623 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 16384 size blocks: 11311 aes-128 cbc's in 3.00s
		Doing aes-128-gcm for 3s on 16 size blocks: 15163053 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 64 size blocks: 10972686 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 256 size blocks: 5234202 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 1024 size blocks: 1715158 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 8192 size blocks: 233819 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 16384 size blocks: 117411 aes-128-gcm's in 3.00s
		Doing 2048 bits private rsa's for 10s: 1385 2048 bits private RSA's in 10.00s
		Doing 2048 bits public rsa's for 10s: 51916 2048 bits public RSA's in 10.00s
		OpenSSL 1.1.1f  31 Mar 2020
		built on: Mon Apr 20 11:53:50 2020 UTC
		options:bn(64,64) rc4(char) des(int) aes(partial) blowfish(ptr) 
		compiler: gcc -fPIC -pthread -Wa,--noexecstack -Wall -Wa,--noexecstack -g -O2 -fdebug-prefix-map=/build/openssl-9j6sUa/openssl-1.1.1f=. -fstack-protector-strong -Wformat -Werror=format-security -DOPENSSL_TLS_SECURITY_LEVEL=2 -DOPENSSL_USE_NODELETE -DOPENSSL_PIC -DOPENSSL_CPUID_OBJ -DOPENSSL_BN_ASM_MONT -DSHA1_ASM -DSHA256_ASM -DSHA512_ASM -DKECCAK1600_ASM -DVPAES_ASM -DECP_NISTZ256_ASM -DPOLY1305_ASM -DNDEBUG -Wdate-time -D_FORTIFY_SOURCE=2
		The 'numbers' are in 1000s of bytes per second processed.
		type             16 bytes     64 bytes    256 bytes   1024 bytes   8192 bytes  16384 bytes
		aes-128 cbc      54698.66k    59485.89k    61220.78k    61588.14k    61775.87k    61773.14k
		aes-128-gcm      80869.62k   234083.97k   446651.90k   585440.60k   638481.75k   641220.61k
		sha256           48655.32k   149713.73k   358797.65k   548257.11k   651425.11k   660100.44k
				  sign    verify    sign/s verify/s
		rsa 2048 bits 0.007220s 0.000193s    138.5   5191.6

## v0.93 - Kernel 5.8.0-rc1

Initial support for kernel 5.8.0 , problems ahead...

Bootlog: https://gist.github.com/avafinger/5d4a65f27f856b479c5283854a556754

BUG fix: https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.93

**Patch**

	https://git.kernel.org/pub/scm/linux/kernel/git/tytso/ext4.git/commit/?h=ext4-for-linus-5.8-rc1-2&id=7b97d868b7ab2448859668de9222b8af43f76e78

	https://git.kernel.org/pub/scm/linux/kernel/git/tytso/ext4.git/diff/fs/ext4/mballoc.c?h=dev&id=811985365378df01386c3cfb7ff716e74ca376d5


* Benchmark:

		openssl speed -elapsed -evp aes-128-gcm aes-128-cbc sha256 rsa2048
		You have chosen to measure elapsed time instead of user CPU time.
		Doing sha256 for 3s on 16 size blocks: 9173284 sha256's in 3.00s
		Doing sha256 for 3s on 64 size blocks: 7022912 sha256's in 3.00s
		Doing sha256 for 3s on 256 size blocks: 4207141 sha256's in 3.00s
		Doing sha256 for 3s on 1024 size blocks: 1606144 sha256's in 3.00s
		Doing sha256 for 3s on 8192 size blocks: 238573 sha256's in 3.00s
		Doing sha256 for 3s on 16384 size blocks: 119780 sha256's in 3.00s
		Doing aes-128 cbc for 3s on 16 size blocks: 10257397 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 64 size blocks: 2788000 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 256 size blocks: 717399 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 1024 size blocks: 180442 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 8192 size blocks: 22625 aes-128 cbc's in 3.00s
		Doing aes-128 cbc for 3s on 16384 size blocks: 11281 aes-128 cbc's in 3.00s
		Doing aes-128-gcm for 3s on 16 size blocks: 15111849 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 64 size blocks: 10972668 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 256 size blocks: 5235309 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 1024 size blocks: 1714633 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 8192 size blocks: 233792 aes-128-gcm's in 3.00s
		Doing aes-128-gcm for 3s on 16384 size blocks: 116256 aes-128-gcm's in 3.00s
		Doing 2048 bits private rsa's for 10s: 1386 2048 bits private RSA's in 10.01s
		Doing 2048 bits public rsa's for 10s: 51920 2048 bits public RSA's in 10.00s
		OpenSSL 1.1.1f  31 Mar 2020
		built on: Mon Apr 20 11:53:50 2020 UTC
		options:bn(64,64) rc4(char) des(int) aes(partial) blowfish(ptr) 
		compiler: gcc -fPIC -pthread -Wa,--noexecstack -Wall -Wa,--noexecstack -g -O2 -fdebug-prefix-map=/build/openssl-9j6sUa/openssl-1.1.1f=. -fstack-protector-strong -Wformat -Werror=format-security -DOPENSSL_TLS_SECURITY_LEVEL=2 -DOPENSSL_USE_NODELETE -DOPENSSL_PIC -DOPENSSL_CPUID_OBJ -DOPENSSL_BN_ASM_MONT -DSHA1_ASM -DSHA256_ASM -DSHA512_ASM -DKECCAK1600_ASM -DVPAES_ASM -DECP_NISTZ256_ASM -DPOLY1305_ASM -DNDEBUG -Wdate-time -D_FORTIFY_SOURCE=2
		The 'numbers' are in 1000s of bytes per second processed.
		type             16 bytes     64 bytes    256 bytes   1024 bytes   8192 bytes  16384 bytes
		aes-128 cbc      54706.12k    59477.33k    61218.05k    61590.87k    61781.33k    61609.30k
		aes-128-gcm      80596.53k   234083.58k   446746.37k   585261.40k   638408.02k   634912.77k
		sha256           48924.18k   149822.12k   359009.37k   548230.49k   651463.34k   654158.51k
				  sign    verify    sign/s verify/s
		rsa 2048 bits 0.007222s 0.000193s    138.5   5192.0


## v0.94 - Kernel 5.8.0-rc3

* Remove unwanted services running on background

		sudo apt-get remove whoopsie
		sudo apt autoremove --purge snapd
		sudo systemctl stop apt-daily.service
		sudo systemctl stop apt-daily-upgrade.service
		sudo systemctl mask apt-daily.service apt-daily-upgrade.service

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.94


## v0.95 - Kernel 5.8.0

Mainline Kernel 5.8.0 built on-board with gcc 9.3 to ensure it is **really stable**. Build was done with the yellow case.
Thermal throttling has been adjusted to hit at **80ºC** , so if you plan to use intensive cpu applications the board can reach **80ºC** and scale down to **1.3 GHz**, can also reach **85ºC** really easy but will scale down to **1.2 GHz** or even **1 GHz**. During the kernel build with 4 cores 100% the board was running with 1.3 GHz most of the time.

Download linux-image 5.8.0 from here: https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.95

	Welcome to Ubuntu 20.04 LTS (GNU/Linux 5.8.0+ aarch64)

	 * Documentation:  https://help.ubuntu.com
	 * Management:     https://landscape.canonical.com
	 * Support:        https://ubuntu.com/advantage

	Last login: Tue Aug  4 21:48:01 2020 from 192.168.254.103


* Installation

Before you upgrade kernel, make sure you have 26 MB free in /boot partition.
Remove old kernels like this:

	ubuntu@nanopi-r2s:~$ dpkg -l|grep linux-image
	ii  linux-image-5.6.7           1.0-2                             arm64        Linux kernel 5.6.7
	ii  linux-image-5.7.0           1.0-4                             arm64        Linux kernel 5.7.0
	ii  linux-image-5.7.0-rc3       1.0-3                             arm64        Linux kernel 5.7.0-rc3
	ii  linux-image-5.7.1           1.0-5                             arm64        Linux kernel 5.7.1
	ii  linux-image-5.7.2           1.0-6                             arm64        Linux kernel 5.7.2
	ii  linux-image-5.8.0+          1.0-9                             arm64        Linux kernel 5.8.0+
	ii  linux-image-5.8.0-rc1       1.0-6                             arm64        Linux kernel 5.8.0-rc1
	ii  linux-image-5.8.0-rc3       1.0-8                             arm64        Linux kernel 5.8.0-rc3
	ubuntu@nanopi-r2s:~$ sudo dpkg -r linux-image-5.8.0-rc1
	[sudo] password for ubuntu: 
	(Reading database ... 43043 files and directories currently installed.)
	Removing linux-image-5.8.0-rc1 (1.0-6) ...
	ubuntu@nanopi-r2s:~$ sudo dpkg -r linux-image-5.8.0-rc3
	(Reading database ... 40306 files and directories currently installed.)
	Removing linux-image-5.8.0-rc3 (1.0-8) ...
	ubuntu@nanopi-r2s:~$ sudo dpkg -r linux-image-5.7.1
	(Reading database ... 37571 files and directories currently installed.)
	Removing linux-image-5.7.1 (1.0-5) ...
	ubuntu@nanopi-r2s:~$ sudo dpkg -r linux-image-5.6.7
	(Reading database ... 35941 files and directories currently installed.)
	Removing linux-image-5.6.7 (1.0-2) ...
	ubuntu@nanopi-r2s:~$ sudo dpkg -r linux-image-5.7.0-rc3
	(Reading database ... 33374 files and directories currently installed.)
	Removing linux-image-5.7.0-rc3 (1.0-3) ...
	ubuntu@nanopi-r2s:~$ dpkg -l|grep linux-image
	ii  linux-image-5.7.0           1.0-4                             arm64        Linux kernel 5.7.0
	ii  linux-image-5.7.2           1.0-6                             arm64        Linux kernel 5.7.2
	ii  linux-image-5.8.0+          1.0-9                             arm64        Linux kernel 5.8.0+
	ubuntu@nanopi-r2s:~$ 

	ubuntu@nanopi-r2s:~$ df -lh
	Filesystem      Size  Used Avail Use% Mounted on
	/dev/mmcblk0p2   15G   14G  652M  96% /
	devtmpfs        478M     0  478M   0% /dev
	tmpfs           489M     0  489M   0% /dev/shm
	tmpfs            98M  3.1M   95M   4% /run
	tmpfs           5.0M     0  5.0M   0% /run/lock
	tmpfs           489M     0  489M   0% /sys/fs/cgroup
	/dev/mmcblk0p1  113M   52M   53M  50% /boot
	tmpfs            98M     0   98M   0% /run/user/1000
	ubuntu@nanopi-r2s:~$ 

## v0.96 - Kernel 5.8.1

Kernel 5.8.1 (mainline stable) for NanoPi R2S, Ubuntu 20.04 LTS

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.96


![NanoPi R2S htop 2.2.2-2](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/htop_2.2.2-2.png)


## v0.97 - Kernel 5.9.0 (RC)

First impression with Kernel 5.9.0-rc1 (mainline RC) for NanoPi R2S, Ubuntu 20.04 LTS.
Currently working:

* eth0
* eth1
* DVFS

**issues**
* no led on Eth1 interface (Link or Activities), but it's working.

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.97

![NanoPi R2S htop 2.2.2-4](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/kernel_5.9.0-rc1.png)


## v0.98 - Kernel 5.9.0 (RC8)

First impression with Kernel 5.9.0-rc8 (mainline RC) for NanoPi R2S, Ubuntu 20.04 LTS.
Currently working:

* eth0
* eth1
* DVFS
* pwm0 (fan)
* shutdown && reboot (fix)

**Boot log**

https://gist.github.com/avafinger/7f9b6ae613a2549fc834034dd4d81fd4


## Controlling FAN speed control with pwm0

We are going to build a service to control the fan speed according to the cpu temperature.
Mainline kernel has exposed the pwm0 where we can output voltage from 2.6v to 5.0v and control the fan speed.

**Enabling the pwm0**
     
    sudo su
    echo -n 0 > /sys/class/pwm/pwmchip0/export

pwm0 is now exposed as **/sys/class/pwm/pwmchip0/pwm0**

	** Temp: 50000, duty: 999991, 0%
	** Temp: 49545, duty: 999991, 0%
	** Temp: 50000, duty: 999991, 0%
	** Temp: 48636, duty: 999991, 0%
	** Temp: 49545, duty: 999991, 0%
	** Temp: 50416, duty: 999991, 0%
	** Temp: 50416, duty: 999991, 0%
	** Temp: 63750, duty: 491901, 75%
	** Temp: 66923, duty: 491901, 75%
	** Temp: 64583, duty: 491901, 75%
	** Temp: 53750, duty: 891901, 25%
	** Temp: 51250, duty: 991901, 5%
	** Temp: 51666, duty: 991901, 5%
	** Temp: 50416, duty: 999991, 0%
	** Temp: 51250, duty: 991901, 5%
	** Temp: 50416, duty: 999991, 0%
	** Temp: 49090, duty: 999991, 0%
	** Temp: 50833, duty: 999991, 0%
	** Temp: 51250, duty: 991901, 5%
	** Temp: 49545, duty: 999991, 0%

Source code for the tiny systemd service is available here: https://github.com/avafinger/fan-speed-control

At startup, the **pwm0 pin** drives 5v and make Fan full speed.
The service will check the CPU Temp and try to drive the speed of the Fan, so the noise is minimum, or should be.

The service has been tested with good results with the snowfan that comes with NanoPi M3.

![NanoPi R2S fan](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/fan-speed.jpg)


## v0.99 - Kernel 5.10.0 (RC1)

Testing the Kernel 5.10.0-rc1 (confirmed LTS ?) for NanoPi R2S.
Currently working:

* eth0
* eth1
* DVFS
* pwm0 (fan)
* halt && reboot (halt )

After some testing, the **shutdown** command still not working and you need to use:

**sudo halt** 

**issues**

* eth1 freezes the board, cannot boot with eth1 connected to the LAN
* eth0 bug (using the previous RTL driver)

		Nov  1 13:22:00 nanopi-r2s kernel: [   15.906125] rk_gmac-dwmac ff540000.ethernet eth0: Link is Up - 1Gbps/Full - flow control rx/tx
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.906234] IPv6: ADDRCONF(NETDEV_CHANGE): eth0: link becomes ready
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.924903] BUG: spinlock bad magic on CPU#3, swapper/3/0
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.925429]  lock: 0xffffff8001aa1690, .magic: 00000000, .owner: <none>/-1, .owner_cpu: 0
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.926163] CPU: 3 PID: 0 Comm: swapper/3 Not tainted 5.10.0-rc1 #1
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.926722] Hardware name: FriendlyElec NanoPi R2S (DT)
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.927191] Call trace:
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.927430]  dump_backtrace+0x0/0x1e8
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.927767]  show_stack+0x2c/0x80
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.928075]  dump_stack+0xc8/0x11c
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.928386]  spin_dump+0x80/0xa0
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.928680]  do_raw_spin_lock+0xf4/0x118
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.929039]  _raw_spin_lock_irqsave+0x60/0xc0
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.929438]  stmmac_tx_timer+0x5c/0xc0
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.929788]  call_timer_fn+0x3c/0x200
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.930126]  run_timer_softirq+0x530/0x568
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.930498]  __do_softirq+0x140/0x3fc
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.930841]  irq_exit+0xd4/0xe0
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.931134]  __handle_domain_irq+0x90/0xf8
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.931512]  efi_header_end+0xb4/0xd8
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.931847]  el1_irq+0xb8/0x180
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.932141]  cpuidle_enter_state+0xbc/0x448
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.932522]  cpuidle_enter+0x3c/0x50
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.932856]  call_cpuidle+0x44/0x78
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.933183]  do_idle+0x22c/0x290
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.933486]  cpu_startup_entry+0x28/0x68
		Nov  1 13:22:00 nanopi-r2s kernel: [   15.933854]  secondary_start_kernel+0x190/0x1e0
		Nov  1 17:50:06 nanopi-r2s kernel: [15971.531102] rk_gmac-dwmac ff540000.ethernet eth0: Link is Down
		Nov  1 17:50:11 nanopi-r2s kernel: [15976.080915] IPv6: ADDRCONF(NETDEV_CHANGE): eth1: link becomes ready
		Nov  1 17:50:11 nanopi-r2s kernel: [15976.083507] r8152 5-1:1.0 eth1: carrier on

The problem seems to be the RTL eth0 driver, but the same driver works just fine on NanoPi M4.

* Bootlog with eth0 and eth1 connected to the LAN

https://gist.github.com/avafinger/9e60f1d607e3ba66f06158334b3165a0

	ubuntu@nanopi-r2s:~$ ifconfig
	eth0: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
		inet 192.168.254.28  netmask 255.255.0.0  broadcast 192.168.255.255
		inet6 2804:7f4:3580:4e5c:387a:74ff:fe7a:4334  prefixlen 64  scopeid 0x0<global>
		inet6 fe80::387a:74ff:fe7a:4334  prefixlen 64  scopeid 0x20<link>
		ether 3a:7a:74:7a:43:34  txqueuelen 1000  (Ethernet)
		RX packets 596  bytes 49830 (49.8 KB)
		RX errors 0  dropped 0  overruns 0  frame 0
		TX packets 74  bytes 7504 (7.5 KB)
		TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0
		device interrupt 36  

	eth1: flags=4163<UP,BROADCAST,RUNNING,MULTICAST>  mtu 1500
		inet 192.168.254.67  netmask 255.255.0.0  broadcast 192.168.255.255
		inet6 2804:7f4:3580:4e5c:d0c2:994e:11fb:7959  prefixlen 64  scopeid 0x0<global>
		inet6 2804:7f4:3580:4e5c:40f7:a7ff:fe28:de72  prefixlen 64  scopeid 0x0<global>
		inet6 fe80::40f7:a7ff:fe28:de72  prefixlen 64  scopeid 0x20<link>
		ether 42:f7:a7:28:de:72  txqueuelen 1000  (Ethernet)
		RX packets 367  bytes 30985 (30.9 KB)
		RX errors 0  dropped 0  overruns 0  frame 0
		TX packets 598  bytes 104090 (104.0 KB)
		TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0

	lo: flags=73<UP,LOOPBACK,RUNNING>  mtu 65536
		inet 127.0.0.1  netmask 255.0.0.0
		inet6 ::1  prefixlen 128  scopeid 0x10<host>
		loop  txqueuelen 1000  (Local Loopback)
		RX packets 0  bytes 0 (0.0 B)
		RX errors 0  dropped 0  overruns 0  frame 0
		TX packets 0  bytes 0 (0.0 B)
		TX errors 0  dropped 0 overruns 0  carrier 0  collisions 0


![NanoPi R2S htop Kernel 5.10.0-c1](https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/raw/master/kernel_5.10.0-rc1.png)


## Boot Info

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

* Source code (updated)

      https://github.com/avafinger/htop_2.2.2


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
* add Kernel 5.7.0 (mainline kernel)
* add Kernel 5.7.1 (stable kernel)
* add Kernel 5.7.2 (stable kernel)
* add Kernel 5.8.0-rc (mainline kernel rc)
* add Kernel 5.8.0 (linus mainline kernel)
* add Kernel 5.9.0 (mainline)

## TODO

* add NAT rules
* reduce boot times
* remove unwanted services
* Create SD CARD Image


## BootLog (Mainline Kernel 5.8.0)

	[    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
	[    0.000000] Linux version 5.8.0 (ubuntu@nanopi-r2s) (gcc (Ubuntu 9.3.0-10ubuntu2) 9.3.0, GNU ld (GNU Binutils for Ubuntu) 2.34) #1 SMP PREEMPT Tue Aug 4 13:30:59 UTC 2020
	[    0.000000] Machine model: FriendlyElec NanoPi R2S
	[    0.000000] efi: UEFI not found.
	[    0.000000] cma: Reserved 16 MiB at 0x000000003f000000
	[    0.000000] Zone ranges:
	[    0.000000]   DMA      [mem 0x0000000000200000-0x000000003fffffff]
	[    0.000000]   DMA32    empty
	[    0.000000]   Normal   empty
	[    0.000000] Movable zone start for each node
	[    0.000000] Early memory node ranges
	[    0.000000]   node   0: [mem 0x0000000000200000-0x000000003fffffff]
	[    0.000000] Initmem setup node 0 [mem 0x0000000000200000-0x000000003fffffff]
	[    0.000000] On node 0 totalpages: 261632
	[    0.000000]   DMA zone: 4088 pages used for memmap
	[    0.000000]   DMA zone: 0 pages reserved
	[    0.000000]   DMA zone: 261632 pages, LIFO batch:63
	[    0.000000] psci: probing for conduit method from DT.
	[    0.000000] psci: PSCIv1.0 detected in firmware.
	[    0.000000] psci: Using standard PSCI v0.2 function IDs
	[    0.000000] psci: MIGRATE_INFO_TYPE not supported.
	[    0.000000] psci: SMC Calling Convention v1.0
	[    0.000000] percpu: Embedded 32 pages/cpu s91112 r8192 d31768 u131072
	[    0.000000] pcpu-alloc: s91112 r8192 d31768 u131072 alloc=32*4096
	[    0.000000] pcpu-alloc: [0] 0 [0] 1 [0] 2 [0] 3 
	[    0.000000] Detected VIPT I-cache on CPU0
	[    0.000000] CPU features: detected: ARM erratum 845719
	[    0.000000] Built 1 zonelists, mobility grouping on.  Total pages: 257544
	[    0.000000] Kernel command line: earlyprintk root=/dev/mmcblk0p2 rw rootfstype=ext4 rootwait fsck.repair=yes panic=10 no_console_suspend consoleblank=0
	[    0.000000] Dentry cache hash table entries: 131072 (order: 8, 1048576 bytes, linear)
	[    0.000000] Inode-cache hash table entries: 65536 (order: 7, 524288 bytes, linear)
	[    0.000000] mem auto-init: stack:off, heap alloc:off, heap free:off
	[    0.000000] Memory: 982048K/1046528K available (13436K kernel code, 1782K rwdata, 5164K rodata, 4992K init, 800K bss, 48096K reserved, 16384K cma-reserved)
	[    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
	[    0.000000] ftrace: allocating 44405 entries in 174 pages
	[    0.000000] ftrace: allocated 174 pages with 5 groups
	[    0.000000] rcu: Preemptible hierarchical RCU implementation.
	[    0.000000] rcu: 	RCU restricting CPUs from NR_CPUS=8 to nr_cpu_ids=4.
	[    0.000000] 	Trampoline variant of Tasks RCU enabled.
	[    0.000000] 	Rude variant of Tasks RCU enabled.
	[    0.000000] rcu: RCU calculated value of scheduler-enlistment delay is 25 jiffies.
	[    0.000000] rcu: Adjusting geometry for rcu_fanout_leaf=16, nr_cpu_ids=4
	[    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
	[    0.000000] GIC: Using split EOI/Deactivate mode
	[    0.000000] random: get_random_bytes called from start_kernel+0x378/0x538 with crng_init=0
	[    0.000000] arch_timer: cp15 timer(s) running at 24.00MHz (phys).
	[    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles: 0x588fe9dc0, max_idle_ns: 440795202592 ns
	[    0.000011] sched_clock: 56 bits at 24MHz, resolution 41ns, wraps every 4398046511097ns
	[    0.000846] Console: colour dummy device 80x25
	[    0.001645] printk: console [tty0] enabled
	[    0.001726] Calibrating delay loop (skipped), value calculated using timer frequency.. 48.00 BogoMIPS (lpj=96000)
	[    0.001769] pid_max: default: 32768 minimum: 301
	[    0.002016] LSM: Security Framework initializing
	[    0.002176] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
	[    0.002220] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
	[    0.005517] rcu: Hierarchical SRCU implementation.
	[    0.009452] EFI services will not be available.
	[    0.010506] smp: Bringing up secondary CPUs ...
	[    0.011648] Detected VIPT I-cache on CPU1
	[    0.011754] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
	[    0.013183] Detected VIPT I-cache on CPU2
	[    0.013277] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
	[    0.014586] Detected VIPT I-cache on CPU3
	[    0.014672] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
	[    0.014896] smp: Brought up 1 node, 4 CPUs
	[    0.015045] SMP: Total of 4 processors activated.
	[    0.015077] CPU features: detected: 32-bit EL0 Support
	[    0.015112] CPU features: detected: CRC32 instructions
	[    0.041594] CPU: All CPU(s) started at EL2
	[    0.041709] alternatives: patching kernel code
	[    0.044090] devtmpfs: initialized
	[    0.062810] Registered cp15_barrier emulation handler
	[    0.062876] Registered setend emulation handler
	[    0.063793] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
	[    0.063867] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
	[    0.065439] pinctrl core: initialized pinctrl subsystem
	[    0.066498] thermal_sys: Registered thermal governor 'fair_share'
	[    0.066504] thermal_sys: Registered thermal governor 'step_wise'
	[    0.067261] DMI not present or invalid.
	[    0.068350] NET: Registered protocol family 16
	[    0.069324] DMA: preallocated 128 KiB GFP_KERNEL pool for atomic allocations
	[    0.069420] DMA: preallocated 128 KiB GFP_KERNEL|GFP_DMA pool for atomic allocations
	[    0.069503] DMA: preallocated 128 KiB GFP_KERNEL|GFP_DMA32 pool for atomic allocations
	[    0.069661] audit: initializing netlink subsys (disabled)
	[    0.070033] audit: type=2000 audit(0.068:1): state=initialized audit_enabled=0 res=1
	[    0.071433] cpuidle: using governor ladder
	[    0.071511] cpuidle: using governor menu
	[    0.071986] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
	[    0.072230] ASID allocator initialised with 65536 entries
	[    0.140987] HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
	[    0.141040] HugeTLB registered 32.0 MiB page size, pre-allocated 0 pages
	[    0.141070] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
	[    0.141099] HugeTLB registered 64.0 KiB page size, pre-allocated 0 pages
	[    0.144336] cryptd: max_cpu_qlen set to 1000
	[    0.158098] iommu: Default domain type: Translated 
	[    0.160063] SCSI subsystem initialized
	[    0.160552] libata version 3.00 loaded.
	[    0.160936] usbcore: registered new interface driver usbfs
	[    0.161059] usbcore: registered new interface driver hub
	[    0.161257] usbcore: registered new device driver usb
	[    0.161415] mc: Linux media interface: v0.10
	[    0.161488] videodev: Linux video capture interface: v2.00
	[    0.161604] pps_core: LinuxPPS API ver. 1 registered
	[    0.161631] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
	[    0.161688] PTP clock support registered
	[    0.162688] Advanced Linux Sound Architecture Driver Initialized.
	[    0.163892] Bluetooth: Core ver 2.22
	[    0.164011] NET: Registered protocol family 31
	[    0.164037] Bluetooth: HCI device and connection manager initialized
	[    0.164083] Bluetooth: HCI socket layer initialized
	[    0.164128] Bluetooth: L2CAP socket layer initialized
	[    0.164189] Bluetooth: SCO socket layer initialized
	[    0.164249] NetLabel: Initializing
	[    0.164273] NetLabel:  domain hash size = 128
	[    0.164295] NetLabel:  protocols = UNLABELED CIPSOv4 CALIPSO
	[    0.164424] NetLabel:  unlabeled traffic allowed by default
	[    0.165652] clocksource: Switched to clocksource arch_sys_counter
	[    1.824696] VFS: Disk quotas dquot_6.6.0
	[    1.824863] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
	[    1.825198] FS-Cache: Loaded
	[    1.841298] NET: Registered protocol family 2
	[    1.842540] tcp_listen_portaddr_hash hash table entries: 512 (order: 2, 20480 bytes, linear)
	[    1.842642] TCP established hash table entries: 8192 (order: 4, 65536 bytes, linear)
	[    1.842803] TCP bind hash table entries: 8192 (order: 6, 262144 bytes, linear)
	[    1.843236] TCP: Hash tables configured (established 8192 bind 8192)
	[    1.843530] UDP hash table entries: 512 (order: 3, 49152 bytes, linear)
	[    1.843659] UDP-Lite hash table entries: 512 (order: 3, 49152 bytes, linear)
	[    1.844402] NET: Registered protocol family 1
	[    1.845563] RPC: Registered named UNIX socket transport module.
	[    1.845608] RPC: Registered udp transport module.
	[    1.845708] RPC: Registered tcp transport module.
	[    1.845734] RPC: Registered tcp NFSv4.1 backchannel transport module.
	[    1.845780] PCI: CLS 0 bytes, default 64
	[    1.846191] Trying to unpack rootfs image as initramfs...
	[    1.926681] Freeing initrd memory: 1076K
	[    1.928480] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 counters available
	[    1.938236] Initialise system trusted keyrings
	[    1.938700] workingset: timestamp_bits=46 max_order=18 bucket_order=0
	[    1.954061] squashfs: version 4.0 (2009/01/31) Phillip Lougher
	[    1.954701] FS-Cache: Netfs 'nfs' registered for caching
	[    1.955813] NFS: Registering the id_resolver key type
	[    1.955899] Key type id_resolver registered
	[    1.955926] Key type id_legacy registered
	[    1.955971] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
	[    1.956466] fuse: init (API version 7.31)
	[    2.031094] Key type asymmetric registered
	[    2.031147] Asymmetric key parser 'x509' registered
	[    2.031263] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 247)
	[    2.031633] io scheduler mq-deadline registered
	[    2.031669] io scheduler kyber registered
	[    2.039911] rockchip-u3phy ff470000.usb3-phy: Rockchip u3phy initialized successfully
	[    2.046699] dma-pl330 ff1f0000.dmac: Loaded driver for PL330 DMAC-241330
	[    2.046755] dma-pl330 ff1f0000.dmac: 	DBUFF-128x8bytes Num_Chans-8 Num_Peri-20 Num_Events-16
	[    2.047765] Serial: 8250/16550 driver, 5 ports, IRQ sharing disabled
	[    2.051134] ff130000.serial: ttyS2 at MMIO 0xff130000 (irq = 12, base_baud = 1500000) is a 16550A
	[    2.127111] printk: console [ttyS2] enabled
	[    2.131621] rockchip-drm display-subsystem: [drm:rockchip_drm_platform_probe] *ERROR* No available vop found for display-subsystem.
	[    2.146516] brd: module loaded
	[    2.168081] loop: module loaded
	[    2.171852] libphy: Fixed MDIO Bus: probed
	[    2.174003] rk_gmac-dwmac ff540000.ethernet: IRQ eth_wake_irq not found
	[    2.174633] rk_gmac-dwmac ff540000.ethernet: IRQ eth_lpi not found
	[    2.175432] rk_gmac-dwmac ff540000.ethernet: PTP uses main clock
	[    2.176197] rk_gmac-dwmac ff540000.ethernet: clock input or output? (input).
	[    2.176848] rk_gmac-dwmac ff540000.ethernet: TX delay(0x24).
	[    2.177373] rk_gmac-dwmac ff540000.ethernet: RX delay(0x18).
	[    2.177962] rk_gmac-dwmac ff540000.ethernet: integrated PHY? (no).
	[    2.178656] rk_gmac-dwmac ff540000.ethernet: cannot get clock clk_mac_speed
	[    2.179291] rk_gmac-dwmac ff540000.ethernet: clock input from PHY
	[    2.184879] rk_gmac-dwmac ff540000.ethernet: init for RGMII
	[    2.185872] rk_gmac-dwmac ff540000.ethernet: User ID: 0x10, Synopsys ID: 0x35
	[    2.186550] rk_gmac-dwmac ff540000.ethernet: 	DWMAC1000
	[    2.187038] rk_gmac-dwmac ff540000.ethernet: DMA HW capability register supported
	[    2.187721] rk_gmac-dwmac ff540000.ethernet: RX Checksum Offload Engine supported
	[    2.188407] rk_gmac-dwmac ff540000.ethernet: COE Type 2
	[    2.188889] rk_gmac-dwmac ff540000.ethernet: TX Checksum insertion supported
	[    2.189539] rk_gmac-dwmac ff540000.ethernet: Wake-Up On Lan supported
	[    2.190221] rk_gmac-dwmac ff540000.ethernet: Normal descriptors
	[    2.190767] rk_gmac-dwmac ff540000.ethernet: Ring mode enabled
	[    2.191303] rk_gmac-dwmac ff540000.ethernet: Enable RX Mitigation via HW Watchdog Timer
	[    2.253668] libphy: stmmac: probed
	[    2.258741] PPP generic driver version 2.4.2
	[    2.259592] usbcore: registered new interface driver asix
	[    2.260183] usbcore: registered new interface driver ax88179_178a
	[    2.260796] usbcore: registered new interface driver cdc_ether
	[    2.261396] usbcore: registered new interface driver qmi_wwan
	[    2.265861] phy phy-ff470000.usb3-phy.2: u3phy u2 power on
	[    2.266429] phy phy-ff470000.usb3-phy.3: u3phy u3 power on
	[    2.269563] dwc2 ff580000.usb: supply vusb_d not found, using dummy regulator
	[    2.270521] dwc2 ff580000.usb: supply vusb_a not found, using dummy regulator
	[    2.401767] dwc2 ff580000.usb: EPs: 10, dedicated fifos, 972 entries in SPRAM
	[    2.402978] dwc2 ff580000.usb: DWC OTG Controller
	[    2.403466] dwc2 ff580000.usb: new USB bus registered, assigned bus number 1
	[    2.404169] dwc2 ff580000.usb: irq 29, io mem 0xff580000
	[    2.405055] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.08
	[    2.405869] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
	[    2.406536] usb usb1: Product: DWC OTG Controller
	[    2.406971] usb usb1: Manufacturer: Linux 5.8.0 dwc2_hsotg
	[    2.407479] usb usb1: SerialNumber: ff580000.usb
	[    2.409024] hub 1-0:1.0: USB hub found
	[    2.409443] hub 1-0:1.0: 1 port detected
	[    2.411564] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
	[    2.412216] ehci-pci: EHCI PCI platform driver
	[    2.412719] ehci-platform: EHCI generic platform driver
	[    2.415991] ehci-platform ff5c0000.usb: EHCI Host Controller
	[    2.416576] ehci-platform ff5c0000.usb: new USB bus registered, assigned bus number 2
	[    2.417522] ehci-platform ff5c0000.usb: irq 30, io mem 0xff5c0000
	[    2.433686] ehci-platform ff5c0000.usb: USB 2.0 started, EHCI 1.00
	[    2.434725] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.08
	[    2.435495] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
	[    2.436163] usb usb2: Product: EHCI Host Controller
	[    2.436612] usb usb2: Manufacturer: Linux 5.8.0 ehci_hcd
	[    2.437101] usb usb2: SerialNumber: ff5c0000.usb
	[    2.438633] hub 2-0:1.0: USB hub found
	[    2.439072] hub 2-0:1.0: 1 port detected
	[    2.440360] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
	[    2.440981] ohci-platform: OHCI generic platform driver
	[    2.442187] ohci-platform ff5d0000.usb: Generic Platform OHCI controller
	[    2.442855] ohci-platform ff5d0000.usb: new USB bus registered, assigned bus number 3
	[    2.443812] ohci-platform ff5d0000.usb: irq 31, io mem 0xff5d0000
	[    2.506059] usb usb3: New USB device found, idVendor=1d6b, idProduct=0001, bcdDevice= 5.08
	[    2.506828] usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
	[    2.507496] usb usb3: Product: Generic Platform OHCI controller
	[    2.508037] usb usb3: Manufacturer: Linux 5.8.0 ohci_hcd
	[    2.508532] usb usb3: SerialNumber: ff5d0000.usb
	[    2.510051] hub 3-0:1.0: USB hub found
	[    2.510478] hub 3-0:1.0: 1 port detected
	[    2.512742] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
	[    2.513307] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 4
	[    2.514406] xhci-hcd xhci-hcd.0.auto: hcc params 0x0220fe64 hci version 0x110 quirks 0x0000000002010010
	[    2.515386] xhci-hcd xhci-hcd.0.auto: irq 166, io mem 0xff600000
	[    2.516767] usb usb4: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.08
	[    2.517533] usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
	[    2.518309] usb usb4: Product: xHCI Host Controller
	[    2.518765] usb usb4: Manufacturer: Linux 5.8.0 xhci-hcd
	[    2.519260] usb usb4: SerialNumber: xhci-hcd.0.auto
	[    2.520803] hub 4-0:1.0: USB hub found
	[    2.521235] hub 4-0:1.0: 1 port detected
	[    2.522378] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
	[    2.522925] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 5
	[    2.523645] xhci-hcd xhci-hcd.0.auto: Host supports USB 3.0 SuperSpeed
	[    2.524397] usb usb5: We don't know the algorithms for LPM for this host, disabling LPM.
	[    2.525385] usb usb5: New USB device found, idVendor=1d6b, idProduct=0003, bcdDevice= 5.08
	[    2.526246] usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=1
	[    2.526908] usb usb5: Product: xHCI Host Controller
	[    2.527358] usb usb5: Manufacturer: Linux 5.8.0 xhci-hcd
	[    2.527846] usb usb5: SerialNumber: xhci-hcd.0.auto
	[    2.529452] hub 5-0:1.0: USB hub found
	[    2.529917] hub 5-0:1.0: 1 port detected
	[    2.531243] usbcore: registered new interface driver cdc_acm
	[    2.531778] cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
	[    2.532585] usbcore: registered new interface driver cdc_wdm
	[    2.533684] usbcore: registered new interface driver uas
	[    2.534442] usbcore: registered new interface driver usb-storage
	[    2.535181] usbcore: registered new interface driver usbserial_generic
	[    2.535817] usbserial: USB Serial support registered for generic
	[    2.536470] usbcore: registered new interface driver ch341
	[    2.537007] usbserial: USB Serial support registered for ch341-uart
	[    2.537706] usbcore: registered new interface driver cp210x
	[    2.538249] usbserial: USB Serial support registered for cp210x
	[    2.538936] usbcore: registered new interface driver ftdi_sio
	[    2.539498] usbserial: USB Serial support registered for FTDI USB Serial Device
	[    2.540535] usbcore: registered new interface driver option
	[    2.541083] usbserial: USB Serial support registered for GSM modem (1-port)
	[    2.542328] usbcore: registered new interface driver pl2303
	[    2.542901] usbserial: USB Serial support registered for pl2303
	[    2.543562] usbcore: registered new interface driver qcserial
	[    2.544129] usbserial: USB Serial support registered for Qualcomm USB modem
	[    2.545699] mousedev: PS/2 mouse device common for all mice
	[    2.547349] i2c /dev entries driver
	[    2.553317] rk808 1-0018: chip id: 0x8050
	[    2.561612] rk808-regulator rk808-regulator: there is no dvs0 gpio
	[    2.562315] rk808-regulator rk808-regulator: there is no dvs1 gpio
	[    2.563017] DCDC_REG1: supplied by vcc_sys
	[    2.566438] DCDC_REG2: supplied by vcc_sys
	[    2.568799] DCDC_REG3: supplied by vcc_sys
	[    2.569799] DCDC_REG4: supplied by vcc_sys
	[    2.571811] LDO_REG1: supplied by vcc_io
	[    2.575713] LDO_REG2: supplied by vcc_io
	[    2.579573] LDO_REG3: supplied by vcc_io
	[    2.593375] rk808-rtc rk808-rtc: registered as rtc0
	[    2.595731] rk808-rtc rk808-rtc: setting system clock to 2020-08-04T22:32:51 UTC (1596580371)
	[    2.598807] input: rk805 pwrkey as /devices/platform/ff160000.i2c/i2c-1/1-0018/rk805-pwrkey/input/input0
	[    2.600934] IR NEC protocol handler initialized
	[    2.606952] rockchip-thermal ff250000.tsadc: Missing tshut mode property, using default (cru)
	[    2.607763] rockchip-thermal ff250000.tsadc: Missing tshut-polarity property, using default (low)
	[    2.611233] device-mapper: uevent: version 1.0.3
	[    2.612263] device-mapper: ioctl: 4.42.0-ioctl (2020-02-27) initialised: dm-devel@redhat.com
	[    2.619298] sdhci: Secure Digital Host Controller Interface driver
	[    2.619892] sdhci: Copyright(c) Pierre Ossman
	[    2.620293] Synopsys Designware Multimedia Card Interface Driver
	[    2.622225] dwmmc_rockchip ff500000.dwmmc: IDMAC supports 32-bit address mode.
	[    2.622951] dwmmc_rockchip ff500000.dwmmc: Using internal DMA controller.
	[    2.623582] dwmmc_rockchip ff500000.dwmmc: Version ID is 270a
	[    2.624206] dwmmc_rockchip ff500000.dwmmc: DW MMC controller at irq 27,32 bit host data width,256 deep fifo
	[    2.625199] vcc_sd: supplied by vcc_io
	[    2.644401] mmc_host mmc0: Bus speed (slot 0) = 400000Hz (slot req 400000Hz, actual 400000HZ div = 0)
	[    2.658649] sdhci-pltfm: SDHCI platform and OF driver helper
	[    2.661886] ledtrig-cpu: registered to indicate activity on CPUs
	[    2.663276] hid: raw HID events driver (C) Jiri Kosina
	[    2.664618] usbcore: registered new interface driver usbhid
	[    2.665162] usbhid: USB HID core driver
	[    2.671805] drop_monitor: Initializing network drop monitor service
	[    2.672746] Initializing XFRM netlink socket
	[    2.674393] NET: Registered protocol family 10
	[    2.677442] Segment Routing with IPv6
	[    2.681704] bpfilter: Loaded bpfilter_umh pid 153
	[    2.682939] NET: Registered protocol family 17
	[    2.683921] Bluetooth: RFCOMM TTY layer initialized
	[    2.684423] Bluetooth: RFCOMM socket layer initialized
	[    2.684942] Bluetooth: RFCOMM ver 1.11
	[    2.685313] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
	[    2.685937] Bluetooth: HIDP socket layer initialized
	[    2.686567] Key type dns_resolver registered
	[    2.688074] registered taskstats version 1
	[    2.688498] Loading compiled-in X.509 certificates
	[    2.689100] Key type ._fscrypt registered
	[    2.689479] Key type .fscrypt registered
	[    2.689900] Key type fscrypt-provisioning registered
	[    2.742535] input: gpio-keys as /devices/platform/gpio-keys/input/input1
	[    2.745471] ALSA device list:
	[    2.745539] mmc_host mmc0: Bus speed (slot 0) = 100000000Hz (slot req 100000000Hz, actual 100000000HZ div = 0)
	[    2.745832]   No soundcards found.
	[    2.747444] dw-apb-uart ff130000.serial: forbid DMA for kernel console
	[    2.747459] random: fast init done
	[    2.754856] Freeing unused kernel memory: 4992K
	[    2.755391] Run /init as init process
	[    2.755730]   with arguments:
	[    2.755737]     /init
	[    2.755741]     earlyprintk
	[    2.755748]   with environment:
	[    2.755754]     HOME=/
	[    2.755759]     TERM=linux
	[    4.241202] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 91
	[    4.241978] mmc0: new ultra high speed SDR50 SDHC card at address aaaa
	[    4.244739] mmcblk0: mmc0:aaaa SL16G 14.8 GiB 
	[    4.254350]  mmcblk0: p1 p2
	[    4.913985] usb 5-1: new SuperSpeed Gen 1 USB device number 2 using xhci-hcd
	[    4.936256] usb 5-1: New USB device found, idVendor=0bda, idProduct=8153, bcdDevice=31.00
	[    4.937050] usb 5-1: New USB device strings: Mfr=1, Product=2, SerialNumber=6
	[    4.937774] usb 5-1: Product: USB 10/100/1000 LAN
	[    4.938225] usb 5-1: Manufacturer: Realtek
	[    4.938619] usb 5-1: SerialNumber: 000000000000
	[    7.903077] EXT4-fs (mmcblk0p2): mounted filesystem without journal. Opts: (null)
	[    8.671037] systemd[1]: systemd 242 running in system mode. (+PAM +AUDIT +SELINUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +XZ +LZ4 +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=hybrid)
	[    8.675174] systemd[1]: Detected architecture arm64.
	[    8.736649] systemd[1]: Set hostname to <nanopi-r2s>.
	[    8.742876] systemd[1]: Failed to bump fs.file-max, ignoring: Invalid argument
	[    9.253404] systemd[1]: /lib/systemd/system/dbus.socket:4: ListenStream= references a path below legacy directory /var/run/, updating /var/run/dbus/system_bus_socket → /run/dbus/system_bus_socket; please update the unit file accordingly.
	[    9.357084] random: systemd: uninitialized urandom read (16 bytes read)
	[    9.358715] systemd[1]: Listening on fsck to fsckd communication Socket.
	[    9.369929] random: systemd: uninitialized urandom read (16 bytes read)
	[    9.370932] systemd[1]: Listening on initctl Compatibility Named Pipe.
	[    9.381898] random: systemd: uninitialized urandom read (16 bytes read)
	[    9.383201] systemd[1]: Listening on udev Control Socket.
	[    9.385140] systemd[1]: Started Dispatch Password Requests to Console Directory Watch.
	[    9.398697] systemd[1]: Listening on Journal Socket.
	[    9.625961] EXT4-fs (mmcblk0p2): re-mounted. Opts: commit=600,errors=remount-ro
	[   10.646309] systemd-journald[224]: Received request to flush runtime journal from PID 1
	[   10.957517] usbcore: registered new interface driver r8152
	[   11.132697] usb 5-1: reset SuperSpeed Gen 1 USB device number 2 using xhci-hcd
	[   11.168807] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Invalid ether addr 00:00:00:00:00:00
	[   11.169708] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether addr 9e:4b:18:5c:76:07
	[   11.190593] r8152 5-1:1.0: load rtl8153b-2 v1 10/23/19 successfully
	[   11.232519] r8152 5-1:1.0 eth1: v1.11.11
	[   11.406329] EXT4-fs (mmcblk0p1): mounted filesystem with ordered data mode. Opts: (null)
	[   11.406389] ext4 filesystem being mounted at /boot supports timestamps until 2038 (0x7fffffff)
	[   11.697249] rk_gmac-dwmac ff540000.ethernet eth0: PHY [stmmac-0:00] driver [RTL8211E Gigabit Ethernet] (irq=POLL)
	[   11.717790] rk_gmac-dwmac ff540000.ethernet eth0: No Safety Features support found
	[   11.717817] rk_gmac-dwmac ff540000.ethernet eth0: PTP not supported by HW
	[   11.717836] rk_gmac-dwmac ff540000.ethernet eth0: configuring for phy/rgmii link mode
	[   12.778878] zram: Added device: zram0
	[   12.782334] zram: Added device: zram1
	[   12.783518] zram: Added device: zram2
	[   12.784568] zram: Added device: zram3
	[   12.915028] zram0: detected capacity change from 0 to 128577536
	[   13.993737] Adding 125560k swap on /dev/zram0.  Priority:5 extents:1 across:125560k SSFS
	[   14.006647] zram1: detected capacity change from 0 to 128577536
	[   15.073718] Adding 125560k swap on /dev/zram1.  Priority:5 extents:1 across:125560k SSFS
	[   15.078087] zram2: detected capacity change from 0 to 128577536
	[   15.806907] rk_gmac-dwmac ff540000.ethernet eth0: Link is Up - 1Gbps/Full - flow control rx/tx
	[   15.807003] IPv6: ADDRCONF(NETDEV_CHANGE): eth0: link becomes ready
	[   16.145716] Adding 125560k swap on /dev/zram2.  Priority:5 extents:1 across:125560k SSFS
	[   16.149344] zram3: detected capacity change from 0 to 128577536
	[   16.477703] random: crng init done
	[   16.477722] random: 7 urandom warning(s) missed due to ratelimiting
	[   16.581862] Adding 125560k swap on /dev/zram3.  Priority:5 extents:1 across:125560k SSFS
	      
      
      
# Credits

I would like to thank the Folks at FriendlyElec for the sample board and the work on the kernel side.
The current Kernel version 5.7.0 release is the stable Linux Kernel with the FriendlyElec's work on USB3.
The benchmark sample was taken with nanoPi R2S without case, your results may vary.
