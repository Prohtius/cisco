# Single dNAT Rule
```
Object network obj-host-<internal ip address>
    host <internal ip address>
    nat (inside,outside) static <external ip address>
    exit

access-list outside extended permit tcp object-group Twotrees_Management object obj-host-<internal ip address>
```

# Create Network Group and allow dNAT on Specific Port
```
object-group network <group name>
    network-object host <external host ip address>
    exit

access-list outside extended permit tcp object-group <group name> object obj-host-<internal ip address> eq <port number>
```
## Real World example
```
! object network obj-net-10.3.137.112
! nat (inside,outside) static 128.177.100.72
!
object-group network Mgmt_Station
network-object host 8.8.8.8
!
no access-list outside extended permit tcp any object obj-net-10.0.0.15 eq 91
!
access-list outside extended permit tcp object-group Mgmt_Station object obj-net-10.0.0.15 eq 91
access-list outside extended permit tcp object-group Other_Group object obj-net-10.0.0.15 eq 91
```
