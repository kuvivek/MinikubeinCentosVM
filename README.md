## Prerequisites

1) You have [installed Docker](https://docs.docker.com/install). 

2) Your computer is an RHEL/CentOS/Fedora-based workstation. I have used    Centos 7 VM hosted in VMware Workstation. 

3) Install the Virtualization Tools

Using the below commands

    [kuvivek@vivekcentos ~]$ sudo yum groupinstall "Virtualization Host"
    [sudo] password for kuvivek: 
    Loaded plugins: fastestmirror, langpacks
    There is no installed groups file.
    Maybe run: yum groups mark convert (see man yum)
    Loading mirror speeds from cached hostfile
    epel/x86_64/metalink                                     |  27 kB     00:00     
     * base: mirror.ratiokontakt.de
     * epel: ftp.lysator.liu.se
     * extras: mirror.init7.net
     * rpmfusion-free-updates: mirror.ehv.weppel.nl
     * updates: centos.bio.lmu.de
    base                                                     | 3.6 kB     00:00     
    docker-ce-stable                                         | 3.5 kB     00:00     
    epel                                                     | 5.4 kB     00:00     
    extras                                                   | 2.9 kB     00:00     
    rpmfusion-free-updates                                   | 3.0 kB     00:00     
    updates                                                  | 2.9 kB     00:00     
    (1/6): base/7/x86_64/group_gz                              | 165 kB   00:00     
    (2/6): epel/x86_64/updateinfo                              | 1.0 MB   00:00     
    (3/6): base/7/x86_64/primary_db                            | 6.0 MB   00:04     
    (4/6): epel/x86_64/primary_db                              | 6.8 MB   00:03     
    (5/6): extras/7/x86_64/primary_db                          | 152 kB   00:03     
    (6/6): updates/7/x86_64/primary_db                         | 1.1 MB   00:06     
    Warning: Group core does not have any packages to install.
    Warning: Group virtualization-hypervisor does not have any packages to install.
    Resolving Dependencies
    --> Running transaction check
    ---> Package libguestfs.x86_64 1:1.40.2-5.el7_7.1 will be installed
    --> Processing Dependency: supermin5 >= 5.1.16-2 for package: 1:libguestfs-1.40.2-5.el7_7.1.x86_64
    --> Processing Dependency: hivex >= 1.3.10-5.8.el7 for package: 1:libguestfs-1.40.2-5.el7_7.1.x86_64
    --> Processing Dependency: syslinux-extlinux for package: 1:libguestfs-1.40.2-5.el7_7.1.x86_64
    --> Processing Dependency: syslinux for package: 1:libguestfs-1.40.2-5.el7_7.1.x86_64
    --> Processing Dependency: squashfs-tools for package: 1:libguestfs-1.40.2-5.el7_7.1.x86_64
    --> Processing Dependency: scrub for package: 1:libguestfs-1.40.2-5.el7_7.1.x86_64
    --> Processing Dependency: hivex for package: 1:libguestfs-1.40.2-5.el7_7.1.x86_64
    ---> Package rubygem-abrt.noarch 0:0.3.0-1.el7 will be installed
    --> Running transaction check
    ---> Package hivex.x86_64 0:1.3.10-6.9.el7 will be installed
    --> Processing Dependency: perl(Win::Hivex::Regedit) for package: hivex-1.3.10-6.9.el7.x86_64
    --> Processing Dependency: perl(Win::Hivex) for package: hivex-1.3.10-6.9.el7.x86_64
    ---> Package scrub.x86_64 0:2.5.2-7.el7 will be installed
    ---> Package squashfs-tools.x86_64 0:4.3-0.21.gitaae0aff4.el7 will be installed
    ---> Package supermin5.x86_64 0:5.1.19-1.el7 will be installed
    ---> Package syslinux.x86_64 0:4.05-15.el7 will be installed
    ---> Package syslinux-extlinux.x86_64 0:4.05-15.el7 will be installed
    --> Running transaction check
    ---> Package perl-hivex.x86_64 0:1.3.10-6.9.el7 will be installed
    --> Finished Dependency Resolution
    
    Dependencies Resolved
    
    ================================================================================
     Package              Arch      Version                        Repository  Size
    ================================================================================
    Installing for group install "Virtualization Tools":
     libguestfs           x86_64    1:1.40.2-5.el7_7.1             updates    2.4 M
    Installing:
     rubygem-abrt         noarch    0.3.0-1.el7                    base       8.1 k
    Installing for dependencies:
     hivex                x86_64    1.3.10-6.9.el7                 base       101 k
     perl-hivex           x86_64    1.3.10-6.9.el7                 base        41 k
     scrub                x86_64    2.5.2-7.el7                    base        41 k
     squashfs-tools       x86_64    4.3-0.21.gitaae0aff4.el7       base       101 k
     supermin5            x86_64    5.1.19-1.el7                   base       637 k
     syslinux             x86_64    4.05-15.el7                    base       990 k
     syslinux-extlinux    x86_64    4.05-15.el7                    base       364 k
    
    Transaction Summary
    ================================================================================
    Install  2 Packages (+7 Dependent packages)
    
    Total download size: 4.7 M
    Installed size: 10 M
    Is this ok [y/d/N]: y
    Downloading packages:
    (1/9): libguestfs-1.40.2-5.el7_7.1.x86_64.rpm              | 2.4 MB   00:01     
    (2/9): perl-hivex-1.3.10-6.9.el7.x86_64.rpm                |  41 kB   00:03     
    (3/9): supermin5-5.1.19-1.el7.x86_64.rpm                   | 637 kB   00:00     
    (4/9): syslinux-4.05-15.el7.x86_64.rpm                     | 990 kB   00:00     
    (5/9): syslinux-extlinux-4.05-15.el7.x86_64.rpm            | 364 kB   00:00     
    (6/9): squashfs-tools-4.3-0.21.gitaae0aff4.el7.x86_64.rpm  | 101 kB   00:02     
    (7/9): scrub-2.5.2-7.el7.x86_64.rpm                        |  41 kB   00:04     
    (8/9): rubygem-abrt-0.3.0-1.el7.noarch.rpm                 | 8.1 kB   00:04     
    (9/9): hivex-1.3.10-6.9.el7.x86_64.rpm                     | 101 kB   00:04     
    --------------------------------------------------------------------------------
    Total                                              929 kB/s | 4.7 MB  00:05     
    Running transaction check
    Running transaction test
    Transaction test succeeded
    Running transaction
      Installing : perl-hivex-1.3.10-6.9.el7.x86_64                                                                                                                                                                1/9 
      Installing : hivex-1.3.10-6.9.el7.x86_64                                                                                                                                                                     2/9 
      Installing : syslinux-4.05-15.el7.x86_64                                                                                                                                                                     3/9 
      Installing : syslinux-extlinux-4.05-15.el7.x86_64                                                                                                                                                            4/9 
      Installing : squashfs-tools-4.3-0.21.gitaae0aff4.el7.x86_64                                                                                                                                                  5/9 
      Installing : scrub-2.5.2-7.el7.x86_64                                                                                                                                                                        6/9 
      Installing : supermin5-5.1.19-1.el7.x86_64                                                                                                                                                                   7/9 
      Installing : 1:libguestfs-1.40.2-5.el7_7.1.x86_64                                                                                                                                                            8/9 
      Installing : rubygem-abrt-0.3.0-1.el7.noarch                                                                                                                                                                 9/9 
      Verifying  : rubygem-abrt-0.3.0-1.el7.noarch                                                                                                                                                                 1/9 
      Verifying  : supermin5-5.1.19-1.el7.x86_64                                                                                                                                                                   2/9 
      Verifying  : scrub-2.5.2-7.el7.x86_64                                                                                                                                                                        3/9 
      Verifying  : squashfs-tools-4.3-0.21.gitaae0aff4.el7.x86_64                                                                                                                                                  4/9 
      Verifying  : syslinux-extlinux-4.05-15.el7.x86_64                                                                                                                                                            5/9 
      Verifying  : hivex-1.3.10-6.9.el7.x86_64                                                                                                                                                                     6/9 
      Verifying  : syslinux-4.05-15.el7.x86_64                                                                                                                                                                     7/9 
      Verifying  : 1:libguestfs-1.40.2-5.el7_7.1.x86_64                                                                                                                                                            8/9 
      Verifying  : perl-hivex-1.3.10-6.9.el7.x86_64                                                                                                                                                                9/9 
    
    Installed:
      libguestfs.x86_64 1:1.40.2-5.el7_7.1                                                                      rubygem-abrt.noarch 0:0.3.0-1.el7                                                                     
    
    Dependency Installed:
      hivex.x86_64 0:1.3.10-6.9.el7       perl-hivex.x86_64 0:1.3.10-6.9.el7           scrub.x86_64 0:2.5.2-7.el7       squashfs-tools.x86_64 0:4.3-0.21.gitaae0aff4.el7       supermin5.x86_64 0:5.1.19-1.el7      
      syslinux.x86_64 0:4.05-15.el7       syslinux-extlinux.x86_64 0:4.05-15.el7      
    
    Complete!
    [kuvivek@vivekcentos ~]$ 
    [kuvivek@vivekcentos ~]$ 

and 

    [kuvivek@vivekcentos ~]$
    [kuvivek@vivekcentos ~]$ sudo yum install qemu-kvm libvirt libvirt-python libguestfs-tools virt-install
    [sudo] password for kuvivek: 
    Loaded plugins: fastestmirror, langpacks
    Loading mirror speeds from cached hostfile
     * base: mirror.ratiokontakt.de
     * epel: ftp.lysator.liu.se
     * extras: mirror.init7.net
     * rpmfusion-free-updates: mirror.ehv.weppel.nl
     * updates: centos.bio.lmu.de
    Resolving Dependencies
    --> Running transaction check
    ---> Package libguestfs-tools.noarch 1:1.40.2-5.el7_7.1 will be installed
    --> Processing Dependency: libguestfs-tools-c = 1:1.40.2-5.el7_7.1 for package: 1:libguestfs-tools-1.40.2-5.el7_7.1.noarch
    --> Processing Dependency: perl(Sys::Virt) for package: 1:libguestfs-tools-1.40.2-5.el7_7.1.noarch
    --> Processing Dependency: perl(Sys::Guestfs) for package: 1:libguestfs-tools-1.40.2-5.el7_7.1.noarch
    --> Processing Dependency: perl(Locale::TextDomain) for package: 1:libguestfs-tools-1.40.2-5.el7_7.1.noarch
    ---> Package libvirt.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt.x86_64 0:4.5.0-23.el7_7.1 will be an update
    --> Processing Dependency: libvirt-libs = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-storage = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-secret = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-qemu = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-nwfilter = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-nodedev = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-network = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-lxc = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-interface = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-config-nwfilter = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-config-network = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-client = 4.5.0-23.el7_7.1 for package: libvirt-4.5.0-23.el7_7.1.x86_64
    ---> Package libvirt-python.x86_64 0:4.5.0-1.el7 will be installed
    ---> Package qemu-kvm.x86_64 10:1.5.3-160.el7_6.3 will be updated
    ---> Package qemu-kvm.x86_64 10:1.5.3-167.el7_7.1 will be an update
    --> Processing Dependency: qemu-kvm-common = 10:1.5.3-167.el7_7.1 for package: 10:qemu-kvm-1.5.3-167.el7_7.1.x86_64
    --> Processing Dependency: qemu-img = 10:1.5.3-167.el7_7.1 for package: 10:qemu-kvm-1.5.3-167.el7_7.1.x86_64
    ---> Package virt-install.noarch 0:1.5.0-7.el7 will be installed
    --> Processing Dependency: virt-manager-common = 1.5.0-7.el7 for package: virt-install-1.5.0-7.el7.noarch
    --> Running transaction check
    ---> Package libguestfs-tools-c.x86_64 1:1.40.2-5.el7_7.1 will be installed
    --> Processing Dependency: /usr/bin/hexedit for package: 1:libguestfs-tools-c-1.40.2-5.el7_7.1.x86_64
    ---> Package libvirt-client.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-client.x86_64 0:4.5.0-23.el7_7.1 will be an update
    --> Processing Dependency: libvirt-bash-completion = 4.5.0-23.el7_7.1 for package: libvirt-client-4.5.0-23.el7_7.1.x86_64
    ---> Package libvirt-daemon.x86_64 0:4.5.0-10.el7_6.12 will be updated
    --> Processing Dependency: libvirt-daemon = 4.5.0-10.el7_6.12 for package: libvirt-daemon-kvm-4.5.0-10.el7_6.12.x86_64
    --> Processing Dependency: libvirt-daemon = 4.5.0-10.el7_6.12 for package: libvirt-daemon-driver-storage-core-4.5.0-10.el7_6.12.x86_64
    ---> Package libvirt-daemon.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-config-network.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-config-network.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-config-nwfilter.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-config-nwfilter.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-interface.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-interface.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-lxc.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-lxc.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-network.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-network.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-nodedev.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-nodedev.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-nwfilter.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-nwfilter.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-qemu.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-qemu.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-secret.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-secret.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage.x86_64 0:4.5.0-23.el7_7.1 will be an update
    --> Processing Dependency: libvirt-daemon-driver-storage-scsi = 4.5.0-23.el7_7.1 for package: libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-storage-rbd = 4.5.0-23.el7_7.1 for package: libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-storage-mpath = 4.5.0-23.el7_7.1 for package: libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-storage-logical = 4.5.0-23.el7_7.1 for package: libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-storage-iscsi = 4.5.0-23.el7_7.1 for package: libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-storage-gluster = 4.5.0-23.el7_7.1 for package: libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64
    --> Processing Dependency: libvirt-daemon-driver-storage-disk = 4.5.0-23.el7_7.1 for package: libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64
    ---> Package libvirt-libs.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-libs.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package perl-Sys-Guestfs.x86_64 1:1.40.2-5.el7_7.1 will be installed
    ---> Package perl-Sys-Virt.x86_64 0:4.5.0-2.el7 will be installed
    ---> Package perl-libintl.x86_64 0:1.20-12.el7 will be installed
    ---> Package qemu-img.x86_64 10:1.5.3-160.el7_6.3 will be updated
    ---> Package qemu-img.x86_64 10:1.5.3-167.el7_7.1 will be an update
    ---> Package qemu-kvm-common.x86_64 10:1.5.3-160.el7_6.3 will be updated
    ---> Package qemu-kvm-common.x86_64 10:1.5.3-167.el7_7.1 will be an update
    ---> Package virt-manager-common.noarch 0:1.5.0-7.el7 will be installed
    --> Processing Dependency: python-requests for package: virt-manager-common-1.5.0-7.el7.noarch
    --> Processing Dependency: python-ipaddr for package: virt-manager-common-1.5.0-7.el7.noarch
    --> Running transaction check
    ---> Package hexedit.x86_64 0:1.2.13-5.el7 will be installed
    ---> Package libvirt-bash-completion.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-bash-completion.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage-core.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage-core.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage-disk.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage-disk.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage-gluster.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage-gluster.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage-iscsi.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage-iscsi.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage-logical.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage-logical.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage-mpath.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage-mpath.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage-rbd.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage-rbd.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-driver-storage-scsi.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-driver-storage-scsi.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package libvirt-daemon-kvm.x86_64 0:4.5.0-10.el7_6.12 will be updated
    ---> Package libvirt-daemon-kvm.x86_64 0:4.5.0-23.el7_7.1 will be an update
    ---> Package python-ipaddr.noarch 0:2.1.11-2.el7 will be installed
    ---> Package python-requests.noarch 0:2.6.0-5.el7 will be installed
    --> Processing Dependency: python-urllib3 >= 1.10.2-1 for package: python-requests-2.6.0-5.el7.noarch
    --> Running transaction check
    ---> Package python-urllib3.noarch 0:1.10.2-7.el7 will be installed
    --> Finished Dependency Resolution
    
    Dependencies Resolved
    
    ===================================================================================================================================================================================================================
     Package                                                               Arch                                   Version                                                Repository                               Size
    ===================================================================================================================================================================================================================
    Installing:
     libguestfs-tools                                                      noarch                                 1:1.40.2-5.el7_7.1                                     updates                                  28 k
     libvirt-python                                                        x86_64                                 4.5.0-1.el7                                            base                                    343 k
     virt-install                                                          noarch                                 1.5.0-7.el7                                            base                                     97 k
    Updating:
     libvirt                                                               x86_64                                 4.5.0-23.el7_7.1                                       updates                                 197 k
     qemu-kvm                                                              x86_64                                 10:1.5.3-167.el7_7.1                                   updates                                 1.9 M
    Installing for dependencies:
     hexedit                                                               x86_64                                 1.2.13-5.el7                                           base                                     39 k
     libguestfs-tools-c                                                    x86_64                                 1:1.40.2-5.el7_7.1                                     updates                                 4.9 M
     perl-Sys-Guestfs                                                      x86_64                                 1:1.40.2-5.el7_7.1                                     updates                                 306 k
     perl-Sys-Virt                                                         x86_64                                 4.5.0-2.el7                                            base                                    296 k
     perl-libintl                                                          x86_64                                 1.20-12.el7                                            base                                    875 k
     python-ipaddr                                                         noarch                                 2.1.11-2.el7                                           base                                     35 k
     python-requests                                                       noarch                                 2.6.0-5.el7                                            base                                     94 k
     python-urllib3                                                        noarch                                 1.10.2-7.el7                                           base                                    103 k
     virt-manager-common                                                   noarch                                 1.5.0-7.el7                                            base                                    1.2 M
    Updating for dependencies:
     libvirt-bash-completion                                               x86_64                                 4.5.0-23.el7_7.1                                       updates                                 198 k
     libvirt-client                                                        x86_64                                 4.5.0-23.el7_7.1                                       updates                                 495 k
     libvirt-daemon                                                        x86_64                                 4.5.0-23.el7_7.1                                       updates                                 841 k
     libvirt-daemon-config-network                                         x86_64                                 4.5.0-23.el7_7.1                                       updates                                 199 k
     libvirt-daemon-config-nwfilter                                        x86_64                                 4.5.0-23.el7_7.1                                       updates                                 204 k
     libvirt-daemon-driver-interface                                       x86_64                                 4.5.0-23.el7_7.1                                       updates                                 236 k
     libvirt-daemon-driver-lxc                                             x86_64                                 4.5.0-23.el7_7.1                                       updates                                 330 k
     libvirt-daemon-driver-network                                         x86_64                                 4.5.0-23.el7_7.1                                       updates                                 410 k
     libvirt-daemon-driver-nodedev                                         x86_64                                 4.5.0-23.el7_7.1                                       updates                                 236 k
     libvirt-daemon-driver-nwfilter                                        x86_64                                 4.5.0-23.el7_7.1                                       updates                                 260 k
     libvirt-daemon-driver-qemu                                            x86_64                                 4.5.0-23.el7_7.1                                       updates                                 745 k
     libvirt-daemon-driver-secret                                          x86_64                                 4.5.0-23.el7_7.1                                       updates                                 226 k
     libvirt-daemon-driver-storage                                         x86_64                                 4.5.0-23.el7_7.1                                       updates                                 197 k
     libvirt-daemon-driver-storage-core                                    x86_64                                 4.5.0-23.el7_7.1                                       updates                                 435 k
     libvirt-daemon-driver-storage-disk                                    x86_64                                 4.5.0-23.el7_7.1                                       updates                                 227 k
     libvirt-daemon-driver-storage-gluster                                 x86_64                                 4.5.0-23.el7_7.1                                       updates                                 235 k
     libvirt-daemon-driver-storage-iscsi                                   x86_64                                 4.5.0-23.el7_7.1                                       updates                                 225 k
     libvirt-daemon-driver-storage-logical                                 x86_64                                 4.5.0-23.el7_7.1                                       updates                                 229 k
     libvirt-daemon-driver-storage-mpath                                   x86_64                                 4.5.0-23.el7_7.1                                       updates                                 224 k
     libvirt-daemon-driver-storage-rbd                                     x86_64                                 4.5.0-23.el7_7.1                                       updates                                 230 k
     libvirt-daemon-driver-storage-scsi                                    x86_64                                 4.5.0-23.el7_7.1                                       updates                                 225 k
     libvirt-daemon-kvm                                                    x86_64                                 4.5.0-23.el7_7.1                                       updates                                 197 k
     libvirt-libs                                                          x86_64                                 4.5.0-23.el7_7.1                                       updates                                 4.2 M
     qemu-img                                                              x86_64                                 10:1.5.3-167.el7_7.1                                   updates                                 699 k
     qemu-kvm-common                                                       x86_64                                 10:1.5.3-167.el7_7.1                                   updates                                 435 k
    
    Transaction Summary
    ===================================================================================================================================================================================================================
    Install  3 Packages (+ 9 Dependent packages)
    Upgrade  2 Packages (+25 Dependent packages)
    
    Total download size: 22 M
    Is this ok [y/d/N]: y
    Downloading packages:
    No Presto metadata available for updates
    (1/39): libguestfs-tools-1.40.2-5.el7_7.1.noarch.rpm                                                                                                                                        |  28 kB  00:00:00     
    (2/39): hexedit-1.2.13-5.el7.x86_64.rpm                                                                                                                                                     |  39 kB  00:00:00     
    (3/39): libvirt-bash-completion-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                                 | 198 kB  00:00:00     
    (4/39): libvirt-client-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                                          | 495 kB  00:00:00     
    (5/39): libvirt-daemon-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                                          | 841 kB  00:00:00     
    (6/39): libvirt-daemon-config-network-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                           | 199 kB  00:00:00     
    (7/39): libvirt-daemon-config-nwfilter-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                          | 204 kB  00:00:00     
    (8/39): libvirt-daemon-driver-interface-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                         | 236 kB  00:00:00     
    (9/39): libvirt-daemon-driver-network-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                           | 410 kB  00:00:00     
    (10/39): libvirt-daemon-driver-nodedev-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                          | 236 kB  00:00:00     
    (11/39): libvirt-daemon-driver-lxc-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                              | 330 kB  00:00:00     
    (12/39): libvirt-daemon-driver-nwfilter-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                         | 260 kB  00:00:00     
    (13/39): libvirt-daemon-driver-qemu-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                             | 745 kB  00:00:00     
    (14/39): libvirt-daemon-driver-secret-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                           | 226 kB  00:00:00     
    (15/39): libguestfs-tools-c-1.40.2-5.el7_7.1.x86_64.rpm                                                                                                                                     | 4.9 MB  00:00:01     
    (16/39): libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                          | 197 kB  00:00:00     
    (17/39): libvirt-daemon-driver-storage-core-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                     | 435 kB  00:00:00     
    (18/39): libvirt-daemon-driver-storage-disk-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                     | 227 kB  00:00:00     
    (19/39): libvirt-daemon-driver-storage-iscsi-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                    | 225 kB  00:00:00     
    (20/39): libvirt-daemon-driver-storage-mpath-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                    | 224 kB  00:00:00     
    (21/39): libvirt-daemon-driver-storage-logical-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                  | 229 kB  00:00:00     
    (22/39): libvirt-daemon-driver-storage-rbd-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                      | 230 kB  00:00:00     
    (23/39): libvirt-daemon-driver-storage-scsi-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                     | 225 kB  00:00:00     
    (24/39): libvirt-daemon-kvm-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                                     | 197 kB  00:00:00     
    (25/39): perl-Sys-Guestfs-1.40.2-5.el7_7.1.x86_64.rpm                                                                                                                                       | 306 kB  00:00:00     
    (26/39): libvirt-python-4.5.0-1.el7.x86_64.rpm                                                                                                                                              | 343 kB  00:00:00     
    (27/39): libvirt-libs-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                                           | 4.2 MB  00:00:00     
    (28/39): perl-libintl-1.20-12.el7.x86_64.rpm                                                                                                                                                | 875 kB  00:00:00     
    (29/39): python-requests-2.6.0-5.el7.noarch.rpm                                                                                                                                             |  94 kB  00:00:00     
    (30/39): python-urllib3-1.10.2-7.el7.noarch.rpm                                                                                                                                             | 103 kB  00:00:00     
    (31/39): qemu-img-1.5.3-167.el7_7.1.x86_64.rpm                                                                                                                                              | 699 kB  00:00:00     
    (32/39): qemu-kvm-1.5.3-167.el7_7.1.x86_64.rpm                                                                                                                                              | 1.9 MB  00:00:00     
    (33/39): qemu-kvm-common-1.5.3-167.el7_7.1.x86_64.rpm                                                                                                                                       | 435 kB  00:00:00     
    (34/39): virt-install-1.5.0-7.el7.noarch.rpm                                                                                                                                                |  97 kB  00:00:00     
    (35/39): virt-manager-common-1.5.0-7.el7.noarch.rpm                                                                                                                                         | 1.2 MB  00:00:00     
    (36/39): python-ipaddr-2.1.11-2.el7.noarch.rpm                                                                                                                                              |  35 kB  00:00:02     
    (37/39): perl-Sys-Virt-4.5.0-2.el7.x86_64.rpm                                                                                                                                               | 296 kB  00:00:03     
    (38/39): libvirt-daemon-driver-storage-gluster-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                  | 235 kB  00:00:04     
    (39/39): libvirt-4.5.0-23.el7_7.1.x86_64.rpm                                                                                                                                                | 197 kB  00:00:11     
    -------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------
    Total                                                                                                                                                                              1.9 MB/s |  22 MB  00:00:11     
    Running transaction check
    Running transaction test
    Transaction test succeeded
    Running transaction
      Updating   : libvirt-libs-4.5.0-23.el7_7.1.x86_64                                                                                                                                                           1/66 
      Updating   : libvirt-daemon-4.5.0-23.el7_7.1.x86_64                                                                                                                                                         2/66 
      Updating   : libvirt-daemon-driver-network-4.5.0-23.el7_7.1.x86_64                                                                                                                                          3/66 
      Updating   : libvirt-daemon-driver-nwfilter-4.5.0-23.el7_7.1.x86_64                                                                                                                                         4/66 
      Updating   : 10:qemu-img-1.5.3-167.el7_7.1.x86_64                                                                                                                                                           5/66 
      Updating   : libvirt-daemon-driver-storage-core-4.5.0-23.el7_7.1.x86_64                                                                                                                                     6/66 
      Updating   : libvirt-daemon-driver-qemu-4.5.0-23.el7_7.1.x86_64                                                                                                                                             7/66 
      Updating   : libvirt-daemon-driver-nodedev-4.5.0-23.el7_7.1.x86_64                                                                                                                                          8/66 
      Updating   : libvirt-daemon-driver-interface-4.5.0-23.el7_7.1.x86_64                                                                                                                                        9/66 
      Updating   : libvirt-daemon-driver-secret-4.5.0-23.el7_7.1.x86_64                                                                                                                                          10/66 
      Updating   : libvirt-daemon-driver-storage-mpath-4.5.0-23.el7_7.1.x86_64                                                                                                                                   11/66 
      Updating   : libvirt-daemon-driver-storage-rbd-4.5.0-23.el7_7.1.x86_64                                                                                                                                     12/66 
      Updating   : libvirt-daemon-driver-storage-iscsi-4.5.0-23.el7_7.1.x86_64                                                                                                                                   13/66 
      Updating   : libvirt-daemon-driver-storage-logical-4.5.0-23.el7_7.1.x86_64                                                                                                                                 14/66 
      Updating   : libvirt-daemon-driver-storage-gluster-4.5.0-23.el7_7.1.x86_64                                                                                                                                 15/66 
      Updating   : libvirt-daemon-driver-storage-scsi-4.5.0-23.el7_7.1.x86_64                                                                                                                                    16/66 
      Updating   : libvirt-daemon-driver-storage-disk-4.5.0-23.el7_7.1.x86_64                                                                                                                                    17/66 
      Updating   : libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64                                                                                                                                         18/66 
      Updating   : libvirt-daemon-config-nwfilter-4.5.0-23.el7_7.1.x86_64                                                                                                                                        19/66 
      Updating   : libvirt-daemon-config-network-4.5.0-23.el7_7.1.x86_64                                                                                                                                         20/66 
      Updating   : libvirt-daemon-driver-lxc-4.5.0-23.el7_7.1.x86_64                                                                                                                                             21/66 
      Installing : libvirt-python-4.5.0-1.el7.x86_64                                                                                                                                                             22/66 
      Installing : perl-Sys-Virt-4.5.0-2.el7.x86_64                                                                                                                                                              23/66 
      Installing : 1:perl-Sys-Guestfs-1.40.2-5.el7_7.1.x86_64                                                                                                                                                    24/66 
      Installing : python-ipaddr-2.1.11-2.el7.noarch                                                                                                                                                             25/66 
      Installing : perl-libintl-1.20-12.el7.x86_64                                                                                                                                                               26/66 
      Installing : python-urllib3-1.10.2-7.el7.noarch                                                                                                                                                            27/66 
      Installing : python-requests-2.6.0-5.el7.noarch                                                                                                                                                            28/66 
      Installing : virt-manager-common-1.5.0-7.el7.noarch                                                                                                                                                        29/66 
      Installing : hexedit-1.2.13-5.el7.x86_64                                                                                                                                                                   30/66 
      Installing : 1:libguestfs-tools-c-1.40.2-5.el7_7.1.x86_64                                                                                                                                                  31/66 
      Updating   : libvirt-bash-completion-4.5.0-23.el7_7.1.x86_64                                                                                                                                               32/66 
      Updating   : libvirt-client-4.5.0-23.el7_7.1.x86_64                                                                                                                                                        33/66 
      Updating   : 10:qemu-kvm-common-1.5.3-167.el7_7.1.x86_64                                                                                                                                                   34/66 
      Updating   : 10:qemu-kvm-1.5.3-167.el7_7.1.x86_64                                                                                                                                                          35/66 
      Updating   : libvirt-daemon-kvm-4.5.0-23.el7_7.1.x86_64                                                                                                                                                    36/66 
      Installing : virt-install-1.5.0-7.el7.noarch                                                                                                                                                               37/66 
      Updating   : libvirt-4.5.0-23.el7_7.1.x86_64                                                                                                                                                               38/66 
      Installing : 1:libguestfs-tools-1.40.2-5.el7_7.1.noarch                                                                                                                                                    39/66 
      Cleanup    : libvirt-4.5.0-10.el7_6.12.x86_64                                                                                                                                                              40/66 
      Cleanup    : libvirt-daemon-kvm-4.5.0-10.el7_6.12.x86_64                                                                                                                                                   41/66 
      Cleanup    : libvirt-daemon-driver-storage-4.5.0-10.el7_6.12.x86_64                                                                                                                                        42/66 
      Cleanup    : libvirt-daemon-driver-qemu-4.5.0-10.el7_6.12.x86_64                                                                                                                                           43/66 
      Cleanup    : libvirt-daemon-driver-lxc-4.5.0-10.el7_6.12.x86_64                                                                                                                                            44/66 
      Cleanup    : libvirt-daemon-config-network-4.5.0-10.el7_6.12.x86_64                                                                                                                                        45/66 
      Cleanup    : libvirt-daemon-config-nwfilter-4.5.0-10.el7_6.12.x86_64                                                                                                                                       46/66 
      Cleanup    : libvirt-daemon-driver-nwfilter-4.5.0-10.el7_6.12.x86_64                                                                                                                                       47/66 
      Cleanup    : libvirt-daemon-driver-network-4.5.0-10.el7_6.12.x86_64                                                                                                                                        48/66 
      Cleanup    : libvirt-daemon-driver-storage-disk-4.5.0-10.el7_6.12.x86_64                                                                                                                                   49/66 
      Cleanup    : libvirt-daemon-driver-storage-logical-4.5.0-10.el7_6.12.x86_64                                                                                                                                50/66 
      Cleanup    : libvirt-daemon-driver-storage-scsi-4.5.0-10.el7_6.12.x86_64                                                                                                                                   51/66 
      Cleanup    : libvirt-daemon-driver-storage-iscsi-4.5.0-10.el7_6.12.x86_64                                                                                                                                  52/66 
      Cleanup    : libvirt-daemon-driver-storage-mpath-4.5.0-10.el7_6.12.x86_64                                                                                                                                  53/66 
      Cleanup    : libvirt-daemon-driver-storage-gluster-4.5.0-10.el7_6.12.x86_64                                                                                                                                54/66 
      Cleanup    : libvirt-daemon-driver-storage-rbd-4.5.0-10.el7_6.12.x86_64                                                                                                                                    55/66 
      Cleanup    : libvirt-daemon-driver-storage-core-4.5.0-10.el7_6.12.x86_64                                                                                                                                   56/66 
      Cleanup    : libvirt-daemon-driver-interface-4.5.0-10.el7_6.12.x86_64                                                                                                                                      57/66 
      Cleanup    : libvirt-daemon-driver-nodedev-4.5.0-10.el7_6.12.x86_64                                                                                                                                        58/66 
      Cleanup    : libvirt-daemon-driver-secret-4.5.0-10.el7_6.12.x86_64                                                                                                                                         59/66 
      Cleanup    : 10:qemu-kvm-1.5.3-160.el7_6.3.x86_64                                                                                                                                                          60/66 
      Cleanup    : libvirt-client-4.5.0-10.el7_6.12.x86_64                                                                                                                                                       61/66 
      Cleanup    : libvirt-daemon-4.5.0-10.el7_6.12.x86_64                                                                                                                                                       62/66 
      Cleanup    : libvirt-bash-completion-4.5.0-10.el7_6.12.x86_64                                                                                                                                              63/66 
      Cleanup    : libvirt-libs-4.5.0-10.el7_6.12.x86_64                                                                                                                                                         64/66 
      Cleanup    : 10:qemu-img-1.5.3-160.el7_6.3.x86_64                                                                                                                                                          65/66 
      Cleanup    : 10:qemu-kvm-common-1.5.3-160.el7_6.3.x86_64                                                                                                                                                   66/66 
      Verifying  : libvirt-daemon-driver-nodedev-4.5.0-23.el7_7.1.x86_64                                                                                                                                          1/66 
      Verifying  : 10:qemu-kvm-common-1.5.3-167.el7_7.1.x86_64                                                                                                                                                    2/66 
      Verifying  : libvirt-daemon-driver-storage-mpath-4.5.0-23.el7_7.1.x86_64                                                                                                                                    3/66 
      Verifying  : libvirt-bash-completion-4.5.0-23.el7_7.1.x86_64                                                                                                                                                4/66 
      Verifying  : libvirt-daemon-4.5.0-23.el7_7.1.x86_64                                                                                                                                                         5/66 
      Verifying  : libvirt-python-4.5.0-1.el7.x86_64                                                                                                                                                              6/66 
      Verifying  : libvirt-daemon-driver-storage-rbd-4.5.0-23.el7_7.1.x86_64                                                                                                                                      7/66 
      Verifying  : hexedit-1.2.13-5.el7.x86_64                                                                                                                                                                    8/66 
      Verifying  : libvirt-daemon-config-network-4.5.0-23.el7_7.1.x86_64                                                                                                                                          9/66 
      Verifying  : 10:qemu-kvm-1.5.3-167.el7_7.1.x86_64                                                                                                                                                          10/66 
      Verifying  : 1:libguestfs-tools-1.40.2-5.el7_7.1.noarch                                                                                                                                                    11/66 
      Verifying  : libvirt-daemon-driver-interface-4.5.0-23.el7_7.1.x86_64                                                                                                                                       12/66 
      Verifying  : libvirt-daemon-driver-storage-iscsi-4.5.0-23.el7_7.1.x86_64                                                                                                                                   13/66 
      Verifying  : python-urllib3-1.10.2-7.el7.noarch                                                                                                                                                            14/66 
      Verifying  : libvirt-daemon-driver-storage-logical-4.5.0-23.el7_7.1.x86_64                                                                                                                                 15/66 
      Verifying  : libvirt-libs-4.5.0-23.el7_7.1.x86_64                                                                                                                                                          16/66 
      Verifying  : libvirt-daemon-config-nwfilter-4.5.0-23.el7_7.1.x86_64                                                                                                                                        17/66 
      Verifying  : libvirt-daemon-driver-storage-4.5.0-23.el7_7.1.x86_64                                                                                                                                         18/66 
      Verifying  : perl-libintl-1.20-12.el7.x86_64                                                                                                                                                               19/66 
      Verifying  : 10:qemu-img-1.5.3-167.el7_7.1.x86_64                                                                                                                                                          20/66 
      Verifying  : libvirt-daemon-driver-qemu-4.5.0-23.el7_7.1.x86_64                                                                                                                                            21/66 
      Verifying  : libvirt-daemon-driver-storage-gluster-4.5.0-23.el7_7.1.x86_64                                                                                                                                 22/66 
      Verifying  : virt-install-1.5.0-7.el7.noarch                                                                                                                                                               23/66 
      Verifying  : libvirt-daemon-driver-network-4.5.0-23.el7_7.1.x86_64                                                                                                                                         24/66 
      Verifying  : python-ipaddr-2.1.11-2.el7.noarch                                                                                                                                                             25/66 
      Verifying  : libvirt-daemon-driver-storage-scsi-4.5.0-23.el7_7.1.x86_64                                                                                                                                    26/66 
      Verifying  : libvirt-daemon-driver-nwfilter-4.5.0-23.el7_7.1.x86_64                                                                                                                                        27/66 
      Verifying  : perl-Sys-Virt-4.5.0-2.el7.x86_64                                                                                                                                                              28/66 
      Verifying  : python-requests-2.6.0-5.el7.noarch                                                                                                                                                            29/66 
      Verifying  : 1:libguestfs-tools-c-1.40.2-5.el7_7.1.x86_64                                                                                                                                                  30/66 
      Verifying  : libvirt-daemon-driver-storage-disk-4.5.0-23.el7_7.1.x86_64                                                                                                                                    31/66 
      Verifying  : virt-manager-common-1.5.0-7.el7.noarch                                                                                                                                                        32/66 
      Verifying  : libvirt-daemon-driver-storage-core-4.5.0-23.el7_7.1.x86_64                                                                                                                                    33/66 
      Verifying  : libvirt-daemon-kvm-4.5.0-23.el7_7.1.x86_64                                                                                                                                                    34/66 
      Verifying  : libvirt-client-4.5.0-23.el7_7.1.x86_64                                                                                                                                                        35/66 
      Verifying  : libvirt-daemon-driver-secret-4.5.0-23.el7_7.1.x86_64                                                                                                                                          36/66 
      Verifying  : 1:perl-Sys-Guestfs-1.40.2-5.el7_7.1.x86_64                                                                                                                                                    37/66 
      Verifying  : libvirt-4.5.0-23.el7_7.1.x86_64                                                                                                                                                               38/66 
      Verifying  : libvirt-daemon-driver-lxc-4.5.0-23.el7_7.1.x86_64                                                                                                                                             39/66 
      Verifying  : libvirt-daemon-driver-storage-rbd-4.5.0-10.el7_6.12.x86_64                                                                                                                                    40/66 
      Verifying  : libvirt-daemon-kvm-4.5.0-10.el7_6.12.x86_64                                                                                                                                                   41/66 
      Verifying  : libvirt-daemon-driver-network-4.5.0-10.el7_6.12.x86_64                                                                                                                                        42/66 
      Verifying  : libvirt-daemon-driver-storage-iscsi-4.5.0-10.el7_6.12.x86_64                                                                                                                                  43/66 
      Verifying  : libvirt-daemon-driver-storage-mpath-4.5.0-10.el7_6.12.x86_64                                                                                                                                  44/66 
      Verifying  : libvirt-daemon-driver-storage-disk-4.5.0-10.el7_6.12.x86_64                                                                                                                                   45/66 
      Verifying  : libvirt-daemon-driver-interface-4.5.0-10.el7_6.12.x86_64                                                                                                                                      46/66 
      Verifying  : libvirt-daemon-driver-storage-core-4.5.0-10.el7_6.12.x86_64                                                                                                                                   47/66 
      Verifying  : libvirt-daemon-driver-qemu-4.5.0-10.el7_6.12.x86_64                                                                                                                                           48/66 
      Verifying  : 10:qemu-img-1.5.3-160.el7_6.3.x86_64                                                                                                                                                          49/66 
      Verifying  : libvirt-daemon-driver-secret-4.5.0-10.el7_6.12.x86_64                                                                                                                                         50/66 
      Verifying  : libvirt-daemon-4.5.0-10.el7_6.12.x86_64                                                                                                                                                       51/66 
      Verifying  : libvirt-daemon-config-nwfilter-4.5.0-10.el7_6.12.x86_64                                                                                                                                       52/66 
      Verifying  : libvirt-daemon-driver-lxc-4.5.0-10.el7_6.12.x86_64                                                                                                                                            53/66 
      Verifying  : libvirt-daemon-driver-storage-gluster-4.5.0-10.el7_6.12.x86_64                                                                                                                                54/66 
      Verifying  : libvirt-bash-completion-4.5.0-10.el7_6.12.x86_64                                                                                                                                              55/66 
      Verifying  : 10:qemu-kvm-common-1.5.3-160.el7_6.3.x86_64                                                                                                                                                   56/66 
      Verifying  : libvirt-daemon-driver-nwfilter-4.5.0-10.el7_6.12.x86_64                                                                                                                                       57/66 
      Verifying  : libvirt-daemon-driver-storage-logical-4.5.0-10.el7_6.12.x86_64                                                                                                                                58/66 
      Verifying  : libvirt-daemon-config-network-4.5.0-10.el7_6.12.x86_64                                                                                                                                        59/66 
      Verifying  : libvirt-daemon-driver-nodedev-4.5.0-10.el7_6.12.x86_64                                                                                                                                        60/66 
      Verifying  : libvirt-client-4.5.0-10.el7_6.12.x86_64                                                                                                                                                       61/66 
      Verifying  : 10:qemu-kvm-1.5.3-160.el7_6.3.x86_64                                                                                                                                                          62/66 
      Verifying  : libvirt-4.5.0-10.el7_6.12.x86_64                                                                                                                                                              63/66 
      Verifying  : libvirt-daemon-driver-storage-scsi-4.5.0-10.el7_6.12.x86_64                                                                                                                                   64/66 
      Verifying  : libvirt-daemon-driver-storage-4.5.0-10.el7_6.12.x86_64                                                                                                                                        65/66 
      Verifying  : libvirt-libs-4.5.0-10.el7_6.12.x86_64                                                                                                                                                         66/66 
    
    Installed:
      libguestfs-tools.noarch 1:1.40.2-5.el7_7.1                                 libvirt-python.x86_64 0:4.5.0-1.el7                                 virt-install.noarch 0:1.5.0-7.el7                                
    
    Dependency Installed:
      hexedit.x86_64 0:1.2.13-5.el7         libguestfs-tools-c.x86_64 1:1.40.2-5.el7_7.1   perl-Sys-Guestfs.x86_64 1:1.40.2-5.el7_7.1   perl-Sys-Virt.x86_64 0:4.5.0-2.el7         perl-libintl.x86_64 0:1.20-12.el7  
      python-ipaddr.noarch 0:2.1.11-2.el7   python-requests.noarch 0:2.6.0-5.el7           python-urllib3.noarch 0:1.10.2-7.el7         virt-manager-common.noarch 0:1.5.0-7.el7  
    
    Updated:
      libvirt.x86_64 0:4.5.0-23.el7_7.1                                                                      qemu-kvm.x86_64 10:1.5.3-167.el7_7.1                                                                     
    
    Dependency Updated:
      libvirt-bash-completion.x86_64 0:4.5.0-23.el7_7.1                     libvirt-client.x86_64 0:4.5.0-23.el7_7.1                            libvirt-daemon.x86_64 0:4.5.0-23.el7_7.1                             
      libvirt-daemon-config-network.x86_64 0:4.5.0-23.el7_7.1               libvirt-daemon-config-nwfilter.x86_64 0:4.5.0-23.el7_7.1            libvirt-daemon-driver-interface.x86_64 0:4.5.0-23.el7_7.1            
      libvirt-daemon-driver-lxc.x86_64 0:4.5.0-23.el7_7.1                   libvirt-daemon-driver-network.x86_64 0:4.5.0-23.el7_7.1             libvirt-daemon-driver-nodedev.x86_64 0:4.5.0-23.el7_7.1              
      libvirt-daemon-driver-nwfilter.x86_64 0:4.5.0-23.el7_7.1              libvirt-daemon-driver-qemu.x86_64 0:4.5.0-23.el7_7.1                libvirt-daemon-driver-secret.x86_64 0:4.5.0-23.el7_7.1               
      libvirt-daemon-driver-storage.x86_64 0:4.5.0-23.el7_7.1               libvirt-daemon-driver-storage-core.x86_64 0:4.5.0-23.el7_7.1        libvirt-daemon-driver-storage-disk.x86_64 0:4.5.0-23.el7_7.1         
      libvirt-daemon-driver-storage-gluster.x86_64 0:4.5.0-23.el7_7.1       libvirt-daemon-driver-storage-iscsi.x86_64 0:4.5.0-23.el7_7.1       libvirt-daemon-driver-storage-logical.x86_64 0:4.5.0-23.el7_7.1      
      libvirt-daemon-driver-storage-mpath.x86_64 0:4.5.0-23.el7_7.1         libvirt-daemon-driver-storage-rbd.x86_64 0:4.5.0-23.el7_7.1         libvirt-daemon-driver-storage-scsi.x86_64 0:4.5.0-23.el7_7.1         
      libvirt-daemon-kvm.x86_64 0:4.5.0-23.el7_7.1                          libvirt-libs.x86_64 0:4.5.0-23.el7_7.1                              qemu-img.x86_64 10:1.5.3-167.el7_7.1                                 
      qemu-kvm-common.x86_64 10:1.5.3-167.el7_7.1                          
    
    Complete!
    [kuvivek@vivekcentos ~]$ 
    [kuvivek@vivekcentos ~]$ 


Proper installation of KVM and libvirt is highly specific to each Linux distribution.
Once configured, validate that libvirt reports no errors:

```shell
[kuvivek@vivekcentos ~]$ 
[kuvivek@vivekcentos ~]$ virt-host-validate
  QEMU: Checking for hardware virtualization                                 : FAIL (Only emulated CPUs are available, performance will be significantly limited)
  QEMU: Checking if device /dev/vhost-net exists                             : PASS
  QEMU: Checking if device /dev/net/tun exists                               : PASS
  QEMU: Checking for cgroup 'memory' controller support                      : PASS
  QEMU: Checking for cgroup 'memory' controller mount-point                  : PASS
  QEMU: Checking for cgroup 'cpu' controller support                         : PASS
  QEMU: Checking for cgroup 'cpu' controller mount-point                     : PASS
  QEMU: Checking for cgroup 'cpuacct' controller support                     : PASS
  QEMU: Checking for cgroup 'cpuacct' controller mount-point                 : PASS
  QEMU: Checking for cgroup 'cpuset' controller support                      : PASS
  QEMU: Checking for cgroup 'cpuset' controller mount-point                  : PASS
  QEMU: Checking for cgroup 'devices' controller support                     : PASS
  QEMU: Checking for cgroup 'devices' controller mount-point                 : PASS
  QEMU: Checking for cgroup 'blkio' controller support                       : PASS
  QEMU: Checking for cgroup 'blkio' controller mount-point                   : PASS
WARN (Unknown if this platform has IOMMU support)
   LXC: Checking for Linux >= 2.6.26                                         : PASS
   LXC: Checking for namespace ipc                                           : PASS
   LXC: Checking for namespace mnt                                           : PASS
   LXC: Checking for namespace pid                                           : PASS
   LXC: Checking for namespace uts                                           : PASS
   LXC: Checking for namespace net                                           : PASS
   LXC: Checking for namespace user                                          : PASS
   LXC: Checking for cgroup 'memory' controller support                      : PASS
   LXC: Checking for cgroup 'memory' controller mount-point                  : PASS
   LXC: Checking for cgroup 'cpu' controller support                         : PASS
   LXC: Checking for cgroup 'cpu' controller mount-point                     : PASS
   LXC: Checking for cgroup 'cpuacct' controller support                     : PASS
   LXC: Checking for cgroup 'cpuacct' controller mount-point                 : PASS
   LXC: Checking for cgroup 'cpuset' controller support                      : PASS
   LXC: Checking for cgroup 'cpuset' controller mount-point                  : PASS
   LXC: Checking for cgroup 'devices' controller support                     : PASS
   LXC: Checking for cgroup 'devices' controller mount-point                 : PASS
   LXC: Checking for cgroup 'blkio' controller support                       : PASS
   LXC: Checking for cgroup 'blkio' controller mount-point                   : PASS
   LXC: Checking if device /sys/fs/fuse/connections exists                   : PASS
[kuvivek@vivekcentos ~]$ 
[kuvivek@vivekcentos ~]$ 
```

Since it is failed. Poweroff the VMware Virtual Machine and in the VM settings, enable all the check boxes within the Virtualization Engine.

![VMware Worstation: VM -> Hardware -> Processors -> Virtualization Engine](https://github.com/kuvivek/MinikubeinCentosVM/blob/master/images/VMwareWorkstationProcessorsSettings.JPG)

## Download, install, and start Minikube

4.  Open a terminal window and run the following command to install minikube.
    
    `curl -Lo minikube https://storage.googleapis.com/minikube/releases/latest/minikube-linux-amd64`
    
    Note that the minikube version (e.g., minikube-linux-amd64) may differ based on your computer's specs.

5.  **chmod** to make it executable.
    
    `chmod +x minikube`
    

6.  Move the file to the **/usr/local/bin** path so you can run it as a command.
    
    `mv minikube /usr/local/bin`
    

7.  Install kubectl using the following command (similar to the minikube installation process).
    
    `curl -Lo kubectl https://storage.googleapis.com/kubernetes-release/release/$(curl -s https://storage.googleapis.com/kubernetes-release/release/stable.txt)/bin/linux/amd64/kubectl`
    
    Use the **curl** command to determine the latest version of Kubernetes.

8.  **chmod** to make kubectl executable.
    
    `chmod +x kubectl`
    

9.  Move kubectl to the **/usr/local/bin** path to run it as a command.
    
    `mv kubectl /usr/local/bin`
    

10. Now start the minikube 

```
    [kuvivek@vivekcentos k8sInstaller]$ 
    [kuvivek@vivekcentos k8sInstaller]$ minikube start --vm-driver=kvm2
    😄  minikube v1.3.1 on Centos 7.6.1810
    💿  Downloading VM boot image ...
    minikube-v1.3.0.iso.sha256: 65 B / 65 B [--------------------] 100.00% ? p/s 0s
    minikube-v1.3.0.iso: 131.07 MiB / 131.07 MiB [-------] 100.00% 9.84 MiB p/s 14s
    🔥  Creating kvm2 VM (CPUs=2, Memory=2000MB, Disk=20000MB) ...
    🐳  Preparing Kubernetes v1.15.2 on Docker 18.09.8 ...
    💾  Downloading kubelet v1.15.2
    💾  Downloading kubeadm v1.15.2
    🚜  Pulling images ...
    🚀  Launching Kubernetes ... 
    ⌛  Waiting for: apiserver proxy etcd scheduler controller dns
    🏄  Done! kubectl is now configured to use  "minikube"
    [kuvivek@vivekcentos k8sInstaller]$ 
```
11. Minikube should download and start. Use the following command to make sure it was successful.

```
    [kuvivek@vivekcentos k8sInstaller]$ 
    [kuvivek@vivekcentos k8sInstaller]$ cat ~/.kube/config
    apiVersion: v1
    clusters:
    - cluster:
        certificate-authority: /home/kuvivek/.minikube/ca.crt
        server: https://192.168.39.76:8443
      name: minikube
    contexts:
    - context:
        cluster: minikube
        user: minikube
      name: minikube
    current-context: minikube
    kind: Config
    preferences: {}
    users:
    - name: minikube
      user:
        client-certificate: /home/kuvivek/.minikube/client.crt
        client-key: /home/kuvivek/.minikube/client.key
    [kuvivek@vivekcentos k8sInstaller]$ 
```

12. Finally, run the following command to open a browser with the Kubernetes dashboard.

```
[kuvivek@vivekcentos k8sInstaller]$ 
[kuvivek@vivekcentos k8sInstaller]$ minikube dashboard
🔌  Enabling dashboard ...
🤔  Verifying dashboard health ...
🚀  Launching proxy ...
🤔  Verifying proxy health ...
🎉  Opening http://127.0.0.1:42716/api/v1/namespaces/kube-system/services/http:kubernetes-dashboard:/proxy/ in your default browser...
This tool has been deprecated, use 'gio open' instead.
See 'gio help open' for more info.


```


