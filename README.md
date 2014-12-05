soem-rosbuild
=============

This project is dedicated to run the Simple Open EtherCAT Master (SOEM) within ROS environment 


=============

Changelog comments:

4. add elmo emergency code dictionary
(SHA: c387ad7e6e0cad95209c0ebb2e56371c063e74c5)
based on EtherCAT Application Manual v.1.403 November 2012, section 6.1 Emergency Error Description (p.73)

3. replace Linux timer with realtime timer - avoid mode switch in Xenomai
(SHA: d3aa73b8cbfab8d5709d7a3a3310cd22f330118d)
use CLOCK_HOST_REALTIME instead of CLOCK_MONOTONIC
lib Posix of Xenomai replaces Posix Linux
for more explanation, see: 
http://www.xenomai.org/pipermail/xenomai/2014-September/031720.html

2. elmo pdo mapping - readmap without complete access:
(SHA: 9a7e73493bef7458c1d273ed2f7ebc035de61709)
When read PDO mapping of slaves, skip the method using Complete Access (CA) & use directly CAN over EtherCAT (CoE), which give the right size of EtherCAT frame input & output buffer. 

1. rtnet define added, work now with realtime Ethernet protocol:
(SHA: 89a1a48b38231df0e9d6690260011d255553ce34)
put some define to work with RTNet, using realtime transfer through Ethernet ports instead of normal socket comm. Patch taken from here: 
http://lists.mech.kuleuven.be/pipermail/orocos-users/2013-June/007165.html
