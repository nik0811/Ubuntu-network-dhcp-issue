# Ubuntu-network-dhcp-issue
Exported VM from AWS got network connection issue which got resolved by below command

```
sudo ip link set dev ens32 up
sudo dhclient ens32
```


```
nikhil@nikhil:~$ cat /etc/netplan/00-installer-config.yaml
network:
  ethernets:
    ens32:
       dhcp4: true
       nameservers:
           search: [google.com]
           addresses: [10.142.7.1, 10.142.7.2]
  version: 2
```

## Generate Netplan

`sudo netplan generate `

## Configure Static IP

```
enp0s8:				
      dhcp4: no
      dhcp6: no
      addresses: [192.168.56.110/24, ]
      gateway4:  192.168.56.1
      nameservers:
              addresses: [8.8.8.8, 8.8.4.4]
 ```
 
 ## Apply Changes
 
 `sudo netplan apply`
