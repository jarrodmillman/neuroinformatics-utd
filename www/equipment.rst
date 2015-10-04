Resources
=========

Compute server
--------------

The compute server has two 12-core Intel Xeon E5-2680v3 (Haswell-EP)
processors with 192GB of DDR4-2133 ECC RAM running CentOS 7.1.

RAID storage
------------

The RAID storage unit is a JetStor NAS 724UX 10G. The unit has ten 8TB
SAS enterprise Hitachi drives configured using RAID 6 with 1 hot spare. RAID
6 uses 2 drives for redundancy, which means that 3 drives would need to fail
before you would lose any data. In the event that a drive did fail, the RAID
unit would immediately start using the hot spare instead of the failed disk.

The RAID drives use ZFS. ZFS is an advanced filesystem supporting (among other
features) protection against data corruption, support for high storage capacities,
efficient data compression, integration of the concepts of filesystem and volume
management, snapshots and copy-on-write clones, continuous integrity checking
and automatic repair. The unit exports the filesystem using NFS version 3.

In the near future, we double the capacity of the unit with additional harddrives
and will add SSD Caching to boost random I/O intensive application.

Secure access
-------------

The only way to access the compute cluster from the internet is over Secure
Shell (SSH). SSH is the standard cryptographic (encrypted) network protocol
for (secure) text-based shell sessions on remote machines.

Remote graphical desktop access is enabled via X2Go. X2Go is a remote desktop
solution, which is securely tunneled over SSH. It works well over both low
bandwidth and high bandwidth connections and has the ability to disconnect
and reconnect to a session, even from another client. You can connect from a
computer running Linux, Windows or Mac OS X.

We use Fail2ban, an intrusion prevention software framework, to protect the
system from brute-force attack.

Network
-------

Currently the compute server and RAID storage are connected over 1 Gigabit
Ethernet. In the near future, this will be upgraded to a 10 Gigabit Ethernet
network.
