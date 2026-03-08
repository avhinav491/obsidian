
Managing and analyzing networks is an important part of Linux administration. Below are key commands and concepts used for network configuration, troubleshooting, and DNS management.

---

# ifconfig Command

`ifconfig` (Interface Configuration) is used to view and configure network interfaces. It shows:

- IP address
    
- Netmask
    
- Broadcast address
    
- MAC address
    
- Interface status (UP/DOWN)
    

Example:  
`ifconfig`

Typical interfaces:

- **eth0** → Main Ethernet interface (external communication)
    
- **lo** → Loopback interface (127.0.0.1, internal communication)
    

Private IPs like **10.x.x.x** are used inside local networks and are not accessible from the public internet.

---

# Wireless Interfaces – iwconfig

`iwconfig` checks wireless network interfaces.  
If it says _“no wireless extensions”_, the interface is not wireless (e.g., eth0 or lo).

---

# Routing Tables

Routing tables determine where network traffic is sent.

View routing table:

- `route -n`
    
- `ip route show`
    

Key terms:

- **Default Gateway (0.0.0.0)** → Router that handles external traffic
    
- **Local Network (e.g., 10.0.2.0/24)** → Directly connected network
    

---

# Testing Connectivity – ping

`ping` tests network connectivity using ICMP requests.

Example:  
`ping google.com`

It shows:

- IP address
    
- Response time (latency)
    
- Packet loss
    

Successful replies mean the host is reachable.

---

# Changing Network Information

## Changing IP Address

You can manually assign an IP address:

```
sudo ifconfig eth0 10.0.0.5 netmask 255.255.255.0 broadcast 10.0.0.255
```

Verify with:  
`ifconfig`

---

## Changing MAC Address

MAC addresses uniquely identify devices.

Steps:

```
sudo ifconfig eth0 down
sudo ifconfig eth0 hw ether 00:11:22:33:44:55
sudo ifconfig eth0 up
```

This is called MAC spoofing.

---

## Getting a New IP from DHCP

Release current IP:  
`sudo dhclient -r eth0`

Request new IP:  
`sudo dhclient eth0`

---

# DNS (Domain Name System)

DNS converts domain names (e.g., google.com) into IP addresses.  
If compromised, it can redirect users to fake websites (DNS spoofing).

---

## dig Command

`dig` (Domain Information Groper) queries DNS servers and shows detailed DNS records.

Example:  
`dig google.com`

It can retrieve:

- A (IPv4) records
	dig domainname
- AAAA (IPv6) records
    dig domainname AAAA
- MX (mail servers)
    dig domainname mx
- NS (name servers)
    

---

# Changing DNS Server

DNS servers are defined in:  
`/etc/resolv.conf`

Example:

```
nameserver 8.8.8.8
nameserver 8.8.4.4
```

These are Google Public DNS servers.

---

# /etc/hosts File (Local DNS Mapping)

The `/etc/hosts` file maps IP addresses to domain names locally.

Example:

```
10.0.2.15   nca.com
```

Now typing `http://nca.com` in the browser resolves to `10.0.2.15` without querying external DNS.

This is useful for:

- Local development
    
- Testing websites
    
- Blocking domains
    

---

# Starting a Web Server

Start Apache server:  
`service apache2 start`

Once started, visiting `http://your-ip/` loads the hosted webpage.

---

These tools allow you to analyze networks, troubleshoot connectivity, configure interfaces, and manage DNS settings effectively in Linux.