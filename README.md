# Ubuntu-network-dhcp-issue
Exported VM from AWS got network connection issue which got resolved by below command

```
sudo ip link set dev ens32 up
sudo dhclient ens32
```
