Network Port Scanning Lab

Objective

The objective of this lab is to discover open ports on devices within a local network and understand potential security risks associated with exposed network services.

Tools Used

- Nmap (Network scanning tool)
- Wireshark (Optional – for packet analysis)

Network Information

- Local IP Address: "192.168.1.X"
- Network Range: "192.168.1.0/24"

Methodology

1. Identify Local Network

Used system commands ("ipconfig" / "ifconfig") to determine the local IP address and subnet range.

2. Discover Active Devices

Performed a ping scan to identify live hosts on the network:

nmap -sn 192.168.1.0/24

3. Scan for Open Ports

Executed a TCP SYN scan to identify open ports:

nmap -sS 192.168.1.0/24

4. Save Scan Results

Saved the output for analysis:

nmap -sS 192.168.1.0/24 -oN scan.txt

 Results

IP Address| Open Ports| Services
192.168.1.1| 80, 443| HTTP, HTTPS
192.168.1.5| 22| SSH

 Analysis

- Port 80 (HTTP) and 443 (HTTPS) indicate a web interface (likely router/admin panel).
- Port 22 (SSH) allows remote login access to a device.
- Open ports confirm active services running on network devices.

Security Risks Identified

- Open SSH port may be vulnerable to brute-force attacks.
- Web services may expose sensitive interfaces if not secured.
- Unnecessary open ports increase attack surface.

Mitigation Strategies

- Close unused ports.
- Use strong passwords and authentication.
- Enable firewall rules to restrict access.
- Keep systems updated with latest security patches.
- Monitor network traffic regularly.

 Optional Packet Analysis (Wireshark)

- Captured packets during scanning process.
- Observed TCP SYN and SYN-ACK responses.
- Verified how port scanning works at packet level.

 Key Concepts Learned

- Port Scanning
- TCP SYN Scan
- Network Reconnaissance
- Open Ports & Services
- Basic Network Security

 Conclusion

This lab provided hands-on experience with network scanning using Nmap. It helped in understanding how open ports expose services and how attackers might exploit them. Additionally, it highlighted the importance of securing network services and minimizing exposure.

 Disclaimer

This scan was performed on a local network for educational purposes only. Unauthorized scanning of networks without permission is illegal.

