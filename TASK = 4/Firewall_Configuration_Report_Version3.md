# Firewall Configuration & Usage Report

## Task Overview

Set up and manage basic firewall rules on Windows/Linux to control network traffic.

---

## Steps Performed

### 1. Open Firewall Configuration Tool

#### On Windows:
- Open **Control Panel > System and Security > Windows Defender Firewall**.
- Or, use **Windows Security > Firewall & network protection**.

#### On Linux (Ubuntu/Debian):
- Open Terminal.
- Use **UFW (Uncomplicated Firewall)**.

### 2. List Current Firewall Rules

#### Windows:
- In the Firewall settings, select "Advanced Settings" to view inbound/outbound rules.

#### Linux (UFW):
```sh
sudo ufw status numbered
```

### 3. Block Inbound Traffic on Port 23 (Telnet)

#### Windows:
- In "Inbound Rules", click "New Rule".
- Select "Port", specify TCP, port 23.
- Choose "Block the connection".

#### Linux (UFW):
```sh
sudo ufw deny 23/tcp
```

### 4. Test the Rule

- Attempt to connect to port 23 locally/remotely (e.g., via `telnet localhost 23`).
- Connection should be blocked/refused.

### 5. Allow SSH (Port 22) on Linux

```sh
sudo ufw allow 22/tcp
```

### 6. Remove Test Block Rule

#### Windows:
- Select the rule for port 23, right-click, and "Delete".

#### Linux:
```sh
sudo ufw delete deny 23/tcp
```

### 7. Document Commands/GUI Steps

- See above for command and menu steps.

### 8. Firewall Filtering Summary

A firewall acts as a barrier between your device and the network, filtering incoming and outgoing traffic based on defined rules. By blocking or allowing specific ports/services, you control access and enhance security.

---

## Example Screenshot

Please include:
- Windows Firewall rules screen showing the port 23 block
- Or Terminal output of `sudo ufw status numbered` showing the rules

**Save as:**
- `firewall_rules_screenshot.png`

---

## Outcome

- **Skill:** Basic firewall management
- **Understanding:** How firewall rules affect network traffic and protect systems
