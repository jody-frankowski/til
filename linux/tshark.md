# tshark

`tshark` is the cli part of wireshark. It can be really handy compared to `tcpdump`
because you can filter traffic based on its application protocol knowledge.

For example you can extract the transferred data of a usb conversation from a pcap:

```sh
tshark -r usb.pcap -T fields -e usb.capdata -Y "usb.capdata"
```
