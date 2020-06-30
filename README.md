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

* Remove unwanted servicesrunning on background

	sudo apt-get remove whoopsie
	sudo apt-get remove snap
	sudo systemctl stop apt-daily.service
	sudo systemctl stop apt-daily-upgrade.service
	sudo systemctl mask apt-daily.service apt-daily-upgrade.service

https://github.com/avafinger/nanopi-r2s-ubuntu-server-minimal-image/releases/tag/v0.94


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

## TODO

* add NAT rules
* reduce boot times
* remove unwanted services
* Create SD CARD Image


## BootLog (Mainline Stable Kernel 5.7.0)

      [    0.000000] Booting Linux on physical CPU 0x0000000000 [0x410fd034]
      [    0.000000] Linux version 5.7.0 (ubuntu@nanopi-m4) (gcc version 9.2.1 20191008 (Ubuntu 9.2.1-9ubuntu2), GNU ld (GNU Binutils for Ubuntu) 2.33) #1 SMP PREEMPT Mon Jun 1 18:36:08 UTC 2020
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
      [    0.000000] Memory: 986464K/1046528K available (12796K kernel code, 1744K rwdata, 5084K rodata, 1344K init, 800K bss, 43680K reserved, 16384K cma-reserved)
      [    0.000000] SLUB: HWalign=64, Order=0-3, MinObjects=0, CPUs=4, Nodes=1
      [    0.000000] ftrace: allocating 43899 entries in 172 pages
      [    0.000000] ftrace: allocated 172 pages with 4 groups
      [    0.000000] rcu: Preemptible hierarchical RCU implementation.
      [    0.000000] rcu: 	RCU restricting CPUs from NR_CPUS=8 to nr_cpu_ids=4.
      [    0.000000] 	Tasks RCU enabled.
      [    0.000000] rcu: RCU calculated value of scheduler-enlistment delay is 25 jiffies.
      [    0.000000] rcu: Adjusting geometry for rcu_fanout_leaf=16, nr_cpu_ids=4
      [    0.000000] NR_IRQS: 64, nr_irqs: 64, preallocated irqs: 0
      [    0.000000] GIC: Using split EOI/Deactivate mode
      [    0.000000] random: get_random_bytes called from start_kernel+0x370/0x4f0 with crng_init=0
      [    0.000000] arch_timer: cp15 timer(s) running at 24.00MHz (phys).
      [    0.000000] clocksource: arch_sys_counter: mask: 0xffffffffffffff max_cycles: 0x588fe9dc0, max_idle_ns: 440795202592 ns
      [    0.000009] sched_clock: 56 bits at 24MHz, resolution 41ns, wraps every 4398046511097ns
      [    0.000843] Console: colour dummy device 80x25
      [    0.001495] printk: console [tty0] enabled
      [    0.001573] Calibrating delay loop (skipped), value calculated using timer frequency.. 48.00 BogoMIPS (lpj=96000)
      [    0.001617] pid_max: default: 32768 minimum: 301
      [    0.001860] LSM: Security Framework initializing
      [    0.002015] Mount-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.002058] Mountpoint-cache hash table entries: 2048 (order: 2, 16384 bytes, linear)
      [    0.005166] rcu: Hierarchical SRCU implementation.
      [    0.009077] EFI services will not be available.
      [    0.009994] smp: Bringing up secondary CPUs ...
      [    0.011069] Detected VIPT I-cache on CPU1
      [    0.011165] CPU1: Booted secondary processor 0x0000000001 [0x410fd034]
      [    0.012541] Detected VIPT I-cache on CPU2
      [    0.012630] CPU2: Booted secondary processor 0x0000000002 [0x410fd034]
      [    0.013823] Detected VIPT I-cache on CPU3
      [    0.013904] CPU3: Booted secondary processor 0x0000000003 [0x410fd034]
      [    0.014109] smp: Brought up 1 node, 4 CPUs
      [    0.014261] SMP: Total of 4 processors activated.
      [    0.014289] CPU features: detected: 32-bit EL0 Support
      [    0.014318] CPU features: detected: CRC32 instructions
      [    0.040530] CPU: All CPU(s) started at EL2
      [    0.040633] alternatives: patching kernel code
      [    0.042997] devtmpfs: initialized
      [    0.060179] Registered cp15_barrier emulation handler
      [    0.060239] Registered setend emulation handler
      [    0.060979] clocksource: jiffies: mask: 0xffffffff max_cycles: 0xffffffff, max_idle_ns: 7645041785100000 ns
      [    0.061046] futex hash table entries: 1024 (order: 4, 65536 bytes, linear)
      [    0.062483] pinctrl core: initialized pinctrl subsystem
      [    0.063487] thermal_sys: Registered thermal governor 'fair_share'
      [    0.063495] thermal_sys: Registered thermal governor 'step_wise'
      [    0.064306] DMI not present or invalid.
      [    0.065329] NET: Registered protocol family 16
      [    0.068763] DMA: preallocated 256 KiB pool for atomic allocations
      [    0.068834] audit: initializing netlink subsys (disabled)
      [    0.069238] audit: type=2000 audit(0.068:1): state=initialized audit_enabled=0 res=1
      [    0.070661] cpuidle: using governor ladder
      [    0.070738] cpuidle: using governor menu
      [    0.071175] hw-breakpoint: found 6 breakpoint and 4 watchpoint registers.
      [    0.071376] ASID allocator initialised with 65536 entries
      [    0.127234] HugeTLB registered 1.00 GiB page size, pre-allocated 0 pages
      [    0.127285] HugeTLB registered 32.0 MiB page size, pre-allocated 0 pages
      [    0.127315] HugeTLB registered 2.00 MiB page size, pre-allocated 0 pages
      [    0.127346] HugeTLB registered 64.0 KiB page size, pre-allocated 0 pages
      [    0.133756] cryptd: max_cpu_qlen set to 1000
      [    0.157152] iommu: Default domain type: Translated 
      [    0.158924] SCSI subsystem initialized
      [    0.159429] libata version 3.00 loaded.
      [    0.159830] usbcore: registered new interface driver usbfs
      [    0.159940] usbcore: registered new interface driver hub
      [    0.160119] usbcore: registered new device driver usb
      [    0.160260] mc: Linux media interface: v0.10
      [    0.160339] videodev: Linux video capture interface: v2.00
      [    0.160437] pps_core: LinuxPPS API ver. 1 registered
      [    0.160463] pps_core: Software ver. 5.3.6 - Copyright 2005-2007 Rodolfo Giometti <giometti@linux.it>
      [    0.160518] PTP clock support registered
      [    0.161425] Advanced Linux Sound Architecture Driver Initialized.
      [    0.162549] Bluetooth: Core ver 2.22
      [    0.162661] NET: Registered protocol family 31
      [    0.162686] Bluetooth: HCI device and connection manager initialized
      [    0.162735] Bluetooth: HCI socket layer initialized
      [    0.162773] Bluetooth: L2CAP socket layer initialized
      [    0.162826] Bluetooth: SCO socket layer initialized
      [    0.162877] NetLabel: Initializing
      [    0.162899] NetLabel:  domain hash size = 128
      [    0.162919] NetLabel:  protocols = UNLABELED CIPSOv4 CALIPSO
      [    0.163065] NetLabel:  unlabeled traffic allowed by default
      [    0.164224] clocksource: Switched to clocksource arch_sys_counter
      [    1.768980] VFS: Disk quotas dquot_6.6.0
      [    1.769128] VFS: Dquot-cache hash table entries: 512 (order 0, 4096 bytes)
      [    1.769445] FS-Cache: Loaded
      [    1.784464] NET: Registered protocol family 2
      [    1.785540] tcp_listen_portaddr_hash hash table entries: 512 (order: 2, 20480 bytes, linear)
      [    1.785633] TCP established hash table entries: 8192 (order: 4, 65536 bytes, linear)
      [    1.785780] TCP bind hash table entries: 8192 (order: 6, 262144 bytes, linear)
      [    1.786171] TCP: Hash tables configured (established 8192 bind 8192)
      [    1.786448] UDP hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.786572] UDP-Lite hash table entries: 512 (order: 3, 49152 bytes, linear)
      [    1.787262] NET: Registered protocol family 1
      [    1.788455] RPC: Registered named UNIX socket transport module.
      [    1.788508] RPC: Registered udp transport module.
      [    1.788531] RPC: Registered tcp transport module.
      [    1.788557] RPC: Registered tcp NFSv4.1 backchannel transport module.
      [    1.788602] PCI: CLS 0 bytes, default 64
      [    1.789006] Trying to unpack rootfs image as initramfs...
      [    1.872046] Freeing initrd memory: 1076K
      [    1.873888] hw perfevents: enabled with armv8_cortex_a53 PMU driver, 7 counters available
      [    1.891643] Initialise system trusted keyrings
      [    1.892037] workingset: timestamp_bits=46 max_order=18 bucket_order=0
      [    1.907191] squashfs: version 4.0 (2009/01/31) Phillip Lougher
      [    1.907868] FS-Cache: Netfs 'nfs' registered for caching
      [    1.909150] NFS: Registering the id_resolver key type
      [    1.909228] Key type id_resolver registered
      [    1.909255] Key type id_legacy registered
      [    1.909303] nfs4filelayout_init: NFSv4 File Layout Driver Registering...
      [    1.909815] fuse: init (API version 7.31)
      [    1.938154] Key type asymmetric registered
      [    1.938202] Asymmetric key parser 'x509' registered
      [    1.938327] Block layer SCSI generic (bsg) driver version 0.4 loaded (major 247)
      [    1.938663] io scheduler mq-deadline registered
      [    1.938692] io scheduler kyber registered
      [    1.946506] rockchip-u3phy ff470000.usb3-phy: Rockchip u3phy initialized successfully
      [    1.952785] dma-pl330 ff1f0000.dmac: Loaded driver for PL330 DMAC-241330
      [    1.952839] dma-pl330 ff1f0000.dmac: 	DBUFF-128x8bytes Num_Chans-8 Num_Peri-20 Num_Events-16
      [    1.953827] Serial: 8250/16550 driver, 5 ports, IRQ sharing disabled
      [    1.956873] ff130000.serial: ttyS2 at MMIO 0xff130000 (irq = 12, base_baud = 1500000) is a 16550A
      [    2.027605] printk: console [ttyS2] enabled
      [    2.031896] rockchip-drm display-subsystem: [drm:rockchip_drm_platform_probe] *ERROR* No available vop found for display-subsystem.
      [    2.045600] brd: module loaded
      [    2.065525] loop: module loaded
      [    2.069135] libphy: Fixed MDIO Bus: probed
      [    2.071122] rk_gmac-dwmac ff540000.ethernet: IRQ eth_wake_irq not found
      [    2.071743] rk_gmac-dwmac ff540000.ethernet: IRQ eth_lpi not found
      [    2.072583] rk_gmac-dwmac ff540000.ethernet: PTP uses main clock
      [    2.073329] rk_gmac-dwmac ff540000.ethernet: clock input or output? (input).
      [    2.073978] rk_gmac-dwmac ff540000.ethernet: TX delay(0x24).
      [    2.074507] rk_gmac-dwmac ff540000.ethernet: RX delay(0x18).
      [    2.075043] rk_gmac-dwmac ff540000.ethernet: integrated PHY? (no).
      [    2.075735] rk_gmac-dwmac ff540000.ethernet: cannot get clock clk_mac_speed
      [    2.076413] rk_gmac-dwmac ff540000.ethernet: clock input from PHY
      [    2.082000] rk_gmac-dwmac ff540000.ethernet: init for RGMII
      [    2.082926] rk_gmac-dwmac ff540000.ethernet: User ID: 0x10, Synopsys ID: 0x35
      [    2.083602] rk_gmac-dwmac ff540000.ethernet: 	DWMAC1000
      [    2.084095] rk_gmac-dwmac ff540000.ethernet: DMA HW capability register supported
      [    2.084823] rk_gmac-dwmac ff540000.ethernet: RX Checksum Offload Engine supported
      [    2.085509] rk_gmac-dwmac ff540000.ethernet: COE Type 2
      [    2.085987] rk_gmac-dwmac ff540000.ethernet: TX Checksum insertion supported
      [    2.086631] rk_gmac-dwmac ff540000.ethernet: Wake-Up On Lan supported
      [    2.087279] rk_gmac-dwmac ff540000.ethernet: Normal descriptors
      [    2.087824] rk_gmac-dwmac ff540000.ethernet: Ring mode enabled
      [    2.088380] rk_gmac-dwmac ff540000.ethernet: Enable RX Mitigation via HW Watchdog Timer
      [    2.148236] libphy: stmmac: probed
      [    2.151779] PPP generic driver version 2.4.2
      [    2.152674] usbcore: registered new interface driver asix
      [    2.153276] usbcore: registered new interface driver ax88179_178a
      [    2.153887] usbcore: registered new interface driver cdc_ether
      [    2.154494] usbcore: registered new interface driver qmi_wwan
      [    2.157526] phy phy-ff470000.usb3-phy.2: u3phy u2 power on
      [    2.158088] phy phy-ff470000.usb3-phy.3: u3phy u3 power on
      [    2.160113] dwc2 ff580000.usb: supply vusb_d not found, using dummy regulator
      [    2.161026] dwc2 ff580000.usb: supply vusb_a not found, using dummy regulator
      [    2.292343] dwc2 ff580000.usb: EPs: 10, dedicated fifos, 972 entries in SPRAM
      [    2.293617] dwc2 ff580000.usb: DWC OTG Controller
      [    2.294108] dwc2 ff580000.usb: new USB bus registered, assigned bus number 1
      [    2.294823] dwc2 ff580000.usb: irq 29, io mem 0xff580000
      [    2.295675] usb usb1: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.07
      [    2.296482] usb usb1: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.297143] usb usb1: Product: DWC OTG Controller
      [    2.297577] usb usb1: Manufacturer: Linux 5.7.0 dwc2_hsotg
      [    2.298079] usb usb1: SerialNumber: ff580000.usb
      [    2.299567] hub 1-0:1.0: USB hub found
      [    2.299982] hub 1-0:1.0: 1 port detected
      [    2.301707] ehci_hcd: USB 2.0 'Enhanced' Host Controller (EHCI) Driver
      [    2.302346] ehci-pci: EHCI PCI platform driver
      [    2.302854] ehci-platform: EHCI generic platform driver
      [    2.306030] ehci-platform ff5c0000.usb: EHCI Host Controller
      [    2.306600] ehci-platform ff5c0000.usb: new USB bus registered, assigned bus number 2
      [    2.307532] ehci-platform ff5c0000.usb: irq 30, io mem 0xff5c0000
      [    2.320266] ehci-platform ff5c0000.usb: USB 2.0 started, EHCI 1.00
      [    2.321272] usb usb2: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.07
      [    2.322033] usb usb2: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.322697] usb usb2: Product: EHCI Host Controller
      [    2.323146] usb usb2: Manufacturer: Linux 5.7.0 ehci_hcd
      [    2.323641] usb usb2: SerialNumber: ff5c0000.usb
      [    2.325115] hub 2-0:1.0: USB hub found
      [    2.325540] hub 2-0:1.0: 1 port detected
      [    2.326783] ohci_hcd: USB 1.1 'Open' Host Controller (OHCI) Driver
      [    2.327393] ohci-platform: OHCI generic platform driver
      [    2.328561] ohci-platform ff5d0000.usb: Generic Platform OHCI controller
      [    2.329219] ohci-platform ff5d0000.usb: new USB bus registered, assigned bus number 3
      [    2.330181] ohci-platform ff5d0000.usb: irq 31, io mem 0xff5d0000
      [    2.392610] usb usb3: New USB device found, idVendor=1d6b, idProduct=0001, bcdDevice= 5.07
      [    2.393375] usb usb3: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.394038] usb usb3: Product: Generic Platform OHCI controller
      [    2.394579] usb usb3: Manufacturer: Linux 5.7.0 ohci_hcd
      [    2.395070] usb usb3: SerialNumber: ff5d0000.usb
      [    2.396550] hub 3-0:1.0: USB hub found
      [    2.396966] hub 3-0:1.0: 1 port detected
      [    2.399069] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.399631] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 4
      [    2.400645] xhci-hcd xhci-hcd.0.auto: hcc params 0x0220fe64 hci version 0x110 quirks 0x0000000002010010
      [    2.401605] xhci-hcd xhci-hcd.0.auto: irq 166, io mem 0xff600000
      [    2.402915] usb usb4: New USB device found, idVendor=1d6b, idProduct=0002, bcdDevice= 5.07
      [    2.403683] usb usb4: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.404410] usb usb4: Product: xHCI Host Controller
      [    2.404874] usb usb4: Manufacturer: Linux 5.7.0 xhci-hcd
      [    2.405364] usb usb4: SerialNumber: xhci-hcd.0.auto
      [    2.406863] hub 4-0:1.0: USB hub found
      [    2.407285] hub 4-0:1.0: 1 port detected
      [    2.408368] xhci-hcd xhci-hcd.0.auto: xHCI Host Controller
      [    2.408907] xhci-hcd xhci-hcd.0.auto: new USB bus registered, assigned bus number 5
      [    2.409624] xhci-hcd xhci-hcd.0.auto: Host supports USB 3.0 SuperSpeed
      [    2.410353] usb usb5: We don't know the algorithms for LPM for this host, disabling LPM.
      [    2.411313] usb usb5: New USB device found, idVendor=1d6b, idProduct=0003, bcdDevice= 5.07
      [    2.412068] usb usb5: New USB device strings: Mfr=3, Product=2, SerialNumber=1
      [    2.412778] usb usb5: Product: xHCI Host Controller
      [    2.413229] usb usb5: Manufacturer: Linux 5.7.0 xhci-hcd
      [    2.413717] usb usb5: SerialNumber: xhci-hcd.0.auto
      [    2.415225] hub 5-0:1.0: USB hub found
      [    2.415641] hub 5-0:1.0: 1 port detected
      [    2.416970] usbcore: registered new interface driver cdc_acm
      [    2.417505] cdc_acm: USB Abstract Control Model driver for USB modems and ISDN adapters
      [    2.418308] usbcore: registered new interface driver cdc_wdm
      [    2.419336] usbcore: registered new interface driver uas
      [    2.420075] usbcore: registered new interface driver usb-storage
      [    2.420854] usbcore: registered new interface driver usbserial_generic
      [    2.421500] usbserial: USB Serial support registered for generic
      [    2.422129] usbcore: registered new interface driver ch341
      [    2.422669] usbserial: USB Serial support registered for ch341-uart
      [    2.423328] usbcore: registered new interface driver cp210x
      [    2.423882] usbserial: USB Serial support registered for cp210x
      [    2.424622] usbcore: registered new interface driver ftdi_sio
      [    2.425187] usbserial: USB Serial support registered for FTDI USB Serial Device
      [    2.426209] usbcore: registered new interface driver option
      [    2.426757] usbserial: USB Serial support registered for GSM modem (1-port)
      [    2.427880] usbcore: registered new interface driver pl2303
      [    2.428478] usbserial: USB Serial support registered for pl2303
      [    2.429146] usbcore: registered new interface driver qcserial
      [    2.429720] usbserial: USB Serial support registered for Qualcomm USB modem
      [    2.431274] mousedev: PS/2 mouse device common for all mice
      [    2.432933] i2c /dev entries driver
      [    2.437286] rk808 1-0018: chip id: 0x8050
      [    2.445288] rk808-regulator rk808-regulator: there is no dvs0 gpio
      [    2.445917] rk808-regulator rk808-regulator: there is no dvs1 gpio
      [    2.446612] DCDC_REG1: supplied by vcc_sys
      [    2.450018] DCDC_REG2: supplied by vcc_sys
      [    2.452376] DCDC_REG3: supplied by vcc_sys
      [    2.453287] DCDC_REG4: supplied by vcc_sys
      [    2.455246] LDO_REG1: supplied by vcc_io
      [    2.459090] LDO_REG2: supplied by vcc_io
      [    2.462862] LDO_REG3: supplied by vcc_io
      [    2.476610] rk808-rtc rk808-rtc: registered as rtc0
      [    2.478891] rk808-rtc rk808-rtc: setting system clock to 2020-06-01T22:28:10 UTC (1591050490)
      [    2.481878] input: rk805 pwrkey as /devices/platform/ff160000.i2c/i2c-1/1-0018/rk805-pwrkey/input/input0
      [    2.483948] IR NEC protocol handler initialized
      [    2.489659] rockchip-thermal ff250000.tsadc: Missing tshut mode property, using default (cru)
      [    2.490465] rockchip-thermal ff250000.tsadc: Missing tshut-polarity property, using default (low)
      [    2.493855] device-mapper: uevent: version 1.0.3
      [    2.494858] device-mapper: ioctl: 4.42.0-ioctl (2020-02-27) initialised: dm-devel@redhat.com
      [    2.501419] sdhci: Secure Digital Host Controller Interface driver
      [    2.502007] sdhci: Copyright(c) Pierre Ossman
      [    2.502411] Synopsys Designware Multimedia Card Interface Driver
      [    2.504135] dwmmc_rockchip ff500000.dwmmc: IDMAC supports 32-bit address mode.
      [    2.504940] dwmmc_rockchip ff500000.dwmmc: Using internal DMA controller.
      [    2.505574] dwmmc_rockchip ff500000.dwmmc: Version ID is 270a
      [    2.506199] dwmmc_rockchip ff500000.dwmmc: DW MMC controller at irq 27,32 bit host data width,256 deep fifo
      [    2.507174] vcc_sd: supplied by vcc_io
      [    2.524455] mmc_host mmc0: Bus speed (slot 0) = 400000Hz (slot req 400000Hz, actual 400000HZ div = 0)
      [    2.538851] sdhci-pltfm: SDHCI platform and OF driver helper
      [    2.542062] ledtrig-cpu: registered to indicate activity on CPUs
      [    2.543427] hid: raw HID events driver (C) Jiri Kosina
      [    2.544746] usbcore: registered new interface driver usbhid
      [    2.545356] usbhid: USB HID core driver
      [    2.551782] drop_monitor: Initializing network drop monitor service
      [    2.552798] Initializing XFRM netlink socket
      [    2.554530] NET: Registered protocol family 10
      [    2.557276] Segment Routing with IPv6
      [    2.561159] bpfilter: Loaded bpfilter_umh pid 235
      [    2.562177] NET: Registered protocol family 17
      [    2.563104] Bluetooth: RFCOMM TTY layer initialized
      [    2.563598] Bluetooth: RFCOMM socket layer initialized
      [    2.564113] Bluetooth: RFCOMM ver 1.11
      [    2.564536] Bluetooth: HIDP (Human Interface Emulation) ver 1.2
      [    2.565090] Bluetooth: HIDP socket layer initialized
      [    2.565681] Key type dns_resolver registered
      [    2.566938] registered taskstats version 1
      [    2.567337] Loading compiled-in X.509 certificates
      [    2.568004] Key type ._fscrypt registered
      [    2.568506] Key type .fscrypt registered
      [    2.568913] Key type fscrypt-provisioning registered
      [    2.612326] input: gpio-keys as /devices/platform/gpio-keys/input/input1
      [    2.614882] ALSA device list:
      [    2.615177]   No soundcards found.
      [    2.615844] dw-apb-uart ff130000.serial: forbid DMA for kernel console
      [    2.619915] Freeing unused kernel memory: 1344K
      [    2.620463] Run /init as init process
      [    2.620805]   with arguments:
      [    2.620811]     /init
      [    2.620816]     earlyprintk
      [    2.620820]   with environment:
      [    2.620826]     HOME=/
      [    2.620830]     TERM=linux
      [    2.621473] random: fast init done
      [    2.624277] mmc_host mmc0: Bus speed (slot 0) = 150000000Hz (slot req 150000000Hz, actual 150000000HZ div = 0)
      [    3.822792] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 273
      [    3.823507] mmc0: new ultra high speed SDR104 SDHC card at address aaaa
      [    3.826364] mmcblk0: mmc0:aaaa SL16G 14.8 GiB 
      [    3.835660]  mmcblk0: p1 p2
      [    4.768494] usb 5-1: new SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [    4.789857] usb 5-1: New USB device found, idVendor=0bda, idProduct=8153, bcdDevice=31.00
      [    4.790636] usb 5-1: New USB device strings: Mfr=1, Product=2, SerialNumber=6
      [    4.791307] usb 5-1: Product: USB 10/100/1000 LAN
      [    4.791754] usb 5-1: Manufacturer: Realtek
      [    4.792155] usb 5-1: SerialNumber: 000000000000
      [    7.755978] EXT4-fs (mmcblk0p2): mounted filesystem without journal. Opts: (null)
      [    8.352541] systemd[1]: systemd 245.4-4ubuntu3.1 running in system mode. (+PAM +AUDIT +SELINUX +IMA +APPARMOR +SMACK +SYSVINIT +UTMP +LIBCRYPTSETUP +GCRYPT +GNUTLS +ACL +XZ +LZ4 +SECCOMP +BLKID +ELFUTILS +KMOD +IDN2 -IDN +PCRE2 default-hierarchy=hybrid)
      [    8.355930] systemd[1]: Detected architecture arm64.
      [    8.395534] systemd[1]: Set hostname to <nanopi-r2s>.
      [    8.862745] systemd[1]: /lib/systemd/system/dbus.socket:5: ListenStream= references a path below legacy directory /var/run/, updating /var/run/dbus/system_bus_socket → /run/dbus/system_bus_socket; please update the unit file accordingly.
      [    8.972443] random: systemd: uninitialized urandom read (16 bytes read)
      [    8.976911] systemd[1]: Created slice system-modprobe.slice.
      [    8.988527] random: systemd: uninitialized urandom read (16 bytes read)
      [    8.990625] systemd[1]: Created slice system-serial\x2dgetty.slice.
      [    9.000435] random: systemd: uninitialized urandom read (16 bytes read)
      [    9.002630] systemd[1]: Created slice system-systemd\x2dfsck.slice.
      [    9.014240] systemd[1]: Created slice User and Session Slice.
      [    9.024830] systemd[1]: Started Dispatch Password Requests to Console Directory Watch.
      [    9.036805] systemd[1]: Started Forward Password Requests to Wall Directory Watch.
      [    9.049662] systemd[1]: Set up automount Arbitrary Executable File Formats File System Automount Point.
      [    9.060688] systemd[1]: Reached target Local Encrypted Volumes.
      [    9.072628] systemd[1]: Reached target Paths.
      [    9.084665] systemd[1]: Reached target Remote File Systems.
      [    9.096602] systemd[1]: Reached target Slices.
      [    9.108817] systemd[1]: Reached target Swap.
      [    9.121510] systemd[1]: Listening on Syslog Socket.
      [    9.133447] systemd[1]: Listening on fsck to fsckd communication Socket.
      [    9.135732] systemd[1]: Listening on initctl Compatibility Named Pipe.
      [    9.149807] systemd[1]: Listening on Journal Audit Socket.
      [    9.161272] systemd[1]: Listening on Journal Socket (/dev/log).
      [    9.173685] systemd[1]: Listening on Journal Socket.
      [    9.185665] systemd[1]: Listening on udev Control Socket.
      [    9.188180] systemd[1]: Listening on udev Kernel Socket.
      [    9.208079] systemd[1]: Mounting Huge Pages File System...
      [    9.229199] systemd[1]: Mounting POSIX Message Queue File System...
      [    9.249563] systemd[1]: Mounting Kernel Debug File System...
      [    9.269559] systemd[1]: Mounting Kernel Trace File System...
      [    9.289676] systemd[1]: Starting Journal Service...
      [    9.307647] systemd[1]: Starting Set the console keyboard layout...
      [    9.329399] systemd[1]: Starting Create list of static device nodes for the current kernel...
      [    9.340816] systemd[1]: Condition check resulted in Load Kernel Module drm being skipped.
      [    9.344740] systemd[1]: Condition check resulted in Set Up Additional Binary Formats being skipped.
      [    9.345907] systemd[1]: Condition check resulted in File System Check on Root Device being skipped.
      [    9.356158] systemd[1]: Starting Load Kernel Modules...
      [    9.365414] systemd[1]: Starting Remount Root and Kernel File Systems...
      [    9.391241] systemd[1]: Starting udev Coldplug all Devices...
      [    9.419460] EXT4-fs (mmcblk0p2): re-mounted. Opts: commit=600,errors=remount-ro
      [    9.429115] systemd[1]: Mounted Huge Pages File System.
      [    9.442054] systemd[1]: Mounted POSIX Message Queue File System.
      [    9.457578] systemd[1]: Mounted Kernel Debug File System.
      [    9.469647] systemd[1]: Mounted Kernel Trace File System.
      [    9.484768] systemd[1]: Finished Create list of static device nodes for the current kernel.
      [    9.501228] systemd[1]: Finished Load Kernel Modules.
      [    9.520675] systemd[1]: Finished Remount Root and Kernel File Systems.
      [    9.544511] systemd[1]: Mounting FUSE Control File System...
      [    9.563551] systemd[1]: Mounting Kernel Configuration File System...
      [    9.577428] systemd[1]: Condition check resulted in Rebuild Hardware Database being skipped.
      [    9.578527] systemd[1]: Condition check resulted in Platform Persistent Storage Archival being skipped.
      [    9.585330] systemd[1]: Starting Load/Save Random Seed...
      [    9.602894] systemd[1]: Starting Apply Kernel Variables...
      [    9.630478] systemd[1]: Starting Create System Users...
      [    9.641827] systemd[1]: Finished Set the console keyboard layout.
      [    9.657194] systemd[1]: Mounted FUSE Control File System.
      [    9.669917] systemd[1]: Mounted Kernel Configuration File System.
      [    9.703067] systemd[1]: Finished Apply Kernel Variables.
      [    9.725500] systemd[1]: Finished Create System Users.
      [    9.743145] systemd[1]: Starting Create Static Device Nodes in /dev...
      [    9.799817] systemd[1]: Finished udev Coldplug all Devices.
      [    9.816336] systemd[1]: Finished Create Static Device Nodes in /dev.
      [    9.829761] systemd[1]: Reached target Local File Systems (Pre).
      [    9.850932] systemd[1]: Starting Helper to synchronize boot up for ifupdown...
      [    9.866227] systemd[1]: Starting udev Kernel Device Manager...
      [   10.012581] systemd[1]: Started udev Kernel Device Manager.
      [   10.285909] systemd[1]: Started Journal Service.
      [   10.353176] systemd-journald[294]: Received client request to flush runtime journal.
      [   10.712390] usbcore: registered new interface driver r8152
      [   10.839579] EXT4-fs (mmcblk0p1): mounted filesystem with ordered data mode. Opts: (null)
      [   10.839630] ext4 filesystem being mounted at /boot supports timestamps until 2038 (0x7fffffff)
      [   10.874736] usb 5-1: reset SuperSpeed Gen 1 USB device number 2 using xhci-hcd
      [   10.915920] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Invalid ether addr 00:00:00:00:00:00
      [   10.917558] r8152 5-1:1.0 (unnamed net_device) (uninitialized): Random ether addr 4a:2f:e3:e1:4f:3c
      [   10.937709] r8152 5-1:1.0: load rtl8153b-2 v1 10/23/19 successfully
      [   10.974975] r8152 5-1:1.0 eth1: v1.11.11
      [   11.112539] rk_gmac-dwmac ff540000.ethernet eth0: PHY [stmmac-0:00] driver [RTL8211E Gigabit Ethernet] (irq=POLL)
      [   11.135342] rk_gmac-dwmac ff540000.ethernet eth0: No Safety Features support found
      [   11.135367] rk_gmac-dwmac ff540000.ethernet eth0: PTP not supported by HW
      [   11.135383] rk_gmac-dwmac ff540000.ethernet eth0: configuring for phy/rgmii link mode
      [   11.780280] random: crng init done
      [   11.780293] random: 7 urandom warning(s) missed due to ratelimiting
      [   13.618389] dwmmc_rockchip ff500000.dwmmc: Successfully tuned phase to 273
      [   13.794566] zram: Added device: zram0
      [   13.795702] zram: Added device: zram1
      [   13.797232] zram: Added device: zram2
      [   13.805689] zram: Added device: zram3
      [   13.882679] zram0: detected capacity change from 0 to 128675840
      [   13.964511] Adding 125656k swap on /dev/zram0.  Priority:5 extents:1 across:125656k SSFS
      [   13.972592] zram1: detected capacity change from 0 to 128675840
      [   14.028291] Adding 125656k swap on /dev/zram1.  Priority:5 extents:1 across:125656k SSFS
      [   14.030512] zram2: detected capacity change from 0 to 128675840
      [   14.084345] Adding 125656k swap on /dev/zram2.  Priority:5 extents:1 across:125656k SSFS
      [   14.086792] zram3: detected capacity change from 0 to 128675840
      [   14.136444] Adding 125656k swap on /dev/zram3.  Priority:5 extents:1 across:125656k SSFS
      [   15.237501] rk_gmac-dwmac ff540000.ethernet eth0: Link is Up - 1Gbps/Full - flow control rx/tx
      [   15.237549] IPv6: ADDRCONF(NETDEV_CHANGE): eth0: link becomes ready
	      
      
      
# Credits

I would like to thank the Folks at FriendlyElec for the sample board and the work on the kernel side.
The current Kernel version 5.7.0 release is the stable Linux Kernel with the FriendlyElec's work on USB3.
The benchmark sample was taken with nanoPi R2S without case, your results may vary.
