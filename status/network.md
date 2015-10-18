# Network

## ethtool -query or control network driver and hardware setting

check physical link

    $ sudo ethtool eth0

## ifconfig - configure a network interface

check the network interface

    $ sudo ifconfig eth0

    $ sudo ifup et0
    
check config file

    ## Debian
    $ cat /etc/network/interfaces
    ## Red Hat
    $ cat /etc/sysconfig/network_scripts/ifcfg-<interface>

## route - show / manupulate the IP routing table

check default gateway

    $ sudo route -n

    ## Debian
    $ sudo service networking restart
    ## Red Hat
    $ sudo service network restart

ping gateway

    $ ping -c 5 <gateway-ip>

## nslookup - query Internet name servers interactively

    $ nslookup

check dns config

    $ cat /etc/resolv.conf

