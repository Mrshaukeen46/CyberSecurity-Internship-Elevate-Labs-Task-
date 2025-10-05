# Task 1: Scan Your Local Network for Open Ports

## Objective
Learn to discover open ports on devices in your local network to understand network exposure.

## Tools Required
- **Nmap** (Free, official site: https://nmap.org/)
- **Wireshark** (Optional, for packet analysis)

---

## Step-by-Step Guide

1. **Install Nmap**
   - Download and install from [the official site](https://nmap.org/download.html).

2. **Find Your Local IP Range**
   - On Windows: Run `ipconfig` in Command Prompt.
   - On Linux/macOS: Run `ifconfig` or `ip addr` in Terminal.
   - Look for the IPv4 address and subnet mask, e.g., `192.168.1.x` with subnet `/24`.

3. **Run Nmap Scan**
   - Open Terminal or Command Prompt.
   - Run the following command (replace with your actual IP range if different):
     ```sh
     nmap -sS 192.168.1.0/24
     ```
   - This performs a TCP SYN scan across the local subnet.

4. **Record Results**
   - Note down discovered IP addresses and their open ports.
   - Save results:
     - As text:
       ```sh
       nmap -sS 192.168.1.0/24 -oN scan_results.txt
       ```
     - As HTML:
       ```sh
       nmap -sS 192.168.1.0/24 -oX scan_results.xml
       xsltproc scan_results.xml -o scan_results.html
       ```

5. **(Optional) Analyze Packets with Wireshark**
   - Capture network traffic while running Nmap.
   - Filter by Nmap scan activity (e.g., TCP SYN packets).

6. **Research Common Services**
   - Identify services running on open ports (e.g., port 22 for SSH, port 80 for HTTP).
   - Use [this list of common ports](https://en.wikipedia.org/wiki/List_of_TCP_and_UDP_port_numbers).

7. **Identify Security Risks**
   - Open ports may expose sensitive services.
   - Research vulnerabilities for exposed services/versions.

8. **Save and Document Your Results**
   - Keep scan output for reference.
   - Summarize findings in your project documentation (e.g., risks, unexpected open ports).

---





## Outcome
- **Skill Developed:** Basic network reconnaissance
- **Understanding:** Awareness of which services/devices are exposed on your local network, potential risks, and mitigation strategies.
