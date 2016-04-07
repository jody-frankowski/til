# xxd

You can use `xxd` to generate a hex dump from a binary file or vice versa.
Another cool thing to do with `xxd` is to convert the hex dump output of
`tshark` to a binary file:

```sh
tshark -r usb.pcap -T fields -e usb.capdata -Y "usb.capdata" | xxd -r -p > data.bin
```
