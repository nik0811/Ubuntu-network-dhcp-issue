# Ubuntu-network-dhcp-issue
Exported VM from AWS got network connection issue which got resolved by below command

```
sudo ip link set dev ens32 up
sudo dhclient ens32
```


```
aviuser@aviuser:~$ cat /etc/netplan/00-installer-config.yaml
network:
  ethernets:
    ens32:
       dhcp4: true
       nameservers:
           search: [google.com]
           addresses: [10.142.7.1, 10.142.7.2]
  version: 2
```
