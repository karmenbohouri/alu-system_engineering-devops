# firewall

## Description

This project covers the basics of firewalls: what they are, their main
function, and the two common types (network-based and host-based). It then
applies these concepts in practice using `ufw` (Uncomplicated Firewall) on
`web-01`.

## Concepts

- A firewall is a hardware or software security system that filters incoming
  and outgoing network traffic.
- Two common types of firewalls:
  - **Network firewall**: protects an entire network (e.g. at the gateway
    level, or a cloud provider's security groups).
  - **Host-based firewall**: runs on an individual machine and manages its
    own rules (e.g. `ufw` or `iptables` on a single server).

## Tasks

### 0. Block all incoming traffic but

**File:** `0-block_all_incoming_traffic_but`

Installs `ufw` on `web-01` and configures it to block all incoming traffic
except on the following TCP ports:

- `22` (SSH)
- `80` (HTTP)
- `443` (HTTPS)

**Commands used:**

```bash
sudo apt update
sudo apt install -y ufw

sudo ufw allow 22/tcp
sudo ufw allow 80/tcp
sudo ufw allow 443/tcp

sudo ufw default deny incoming
sudo ufw default allow outgoing

sudo ufw enable
```

**Verification:**

```bash
$ sudo ufw status
Status: active
To                         Action      From
--                         ------      ----
22/tcp                     ALLOW       Anywhere
80/tcp                     ALLOW       Anywhere
443/tcp                    ALLOW       Anywhere
22/tcp (v6)                ALLOW       Anywhere (v6)
80/tcp (v6)                ALLOW       Anywhere (v6)
443/tcp (v6)                ALLOW       Anywhere (v6)
```

## Author

Karmen Bohouri