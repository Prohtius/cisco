# Create Port Channels
## Port channels go after interfaces in ASA config
```
    interface port-channel1
    nameif outside 
    security-level 0
    ip address <ip-address> <subnet-mask>
    no shutdown
    !
    interface port-channel2
    nameif inside 
    security-level 100
    ip address <ip-address> <subnet-mask>
    no shutdown
```

# Add Interfaces to Port Channels
## Modes
*Mode "on" = static*<br/>
*Mode "active" = lacp*
```
    interface Ethernet1/1
    no nameif
    no security-level
    no ip address
    !
    interface Ethernet1/2
    no nameif
    no security-level
    no ip address
    ! 
    interface Ethernet1/3
    channel-group 1 mode active
    no nameif
    no security-level
    no ip address
    no shutdown
    !
    interface Ethernet1/4
    channel-group 1 mode active
    no nameif
    no security-level
    no ip address
    no shutdown
    !
    interface Ethernet1/5
    channel-group 2 mode on
    no nameif
    no security-level
    no ip address
    no shutdown
    !
    interface Ethernet1/6
    channel-group 2 mode on
    no nameif
    no security-level
    no ip address
    no shutdown
    !
```
