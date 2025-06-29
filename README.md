# 🐍 Python Network Sniffer (Scapy-Based)

A command-line network packet sniffer written in Python using the Scapy library. This tool captures and displays in-depth information about IP, TCP, and UDP traffic on a specified network interface.

## ✨ Key Features

* Monitor traffic on a specific interface or across all available interfaces
* Apply BPF (Berkeley Packet Filter) expressions for precise capture control
* Optional filtering by TCP or UDP port
* Displays detailed packet information including:

  * Timestamp
  * Source and Destination IP addresses
  * Protocol type (TCP, UDP, etc.)
  * Packet size
  * Source and destination ports (if available)
  * First 50 bytes of the payload (when present)
* Ability to limit capture by packet count or time duration
* Graceful handling when no matching packets are detected

## 🚀 Usage

To run the sniffer:

```bash
python3 sniffer.py [OPTIONS]
```

### Available Options

| Option              | Description                                            |
| ------------------- | ------------------------------------------------------ |
| `-i`, `--interface` | Network interface to listen on (e.g., eth0, lo)        |
| `-f`, `--filter`    | BPF filter string (default: `ip`)                      |
| `-p`, `--port`      | Filter packets by specific port (e.g., `53`)           |
| `-c`, `--count`     | Number of packets to capture (0 for unlimited)         |
| `-t`, `--timeout`   | Stop after a set duration in seconds (0 for unlimited) |

### Example

```bash
python3 sniffer.py -i lo -f udp -p 53 -c 20 -t 30
```

## 🛠 Installation

1. Clone the repository:

```bash
git clone https://github.com/kingkobra5575/Network-Sniffer.git
cd Network-Sniffer
```

2. (Optional) Create and activate a virtual environment:

```bash
python3 -m venv venv
source venv/bin/activate  # On Windows: venv\Scripts\activate
```

3. Install required packages:

```bash
sudo apt install python3-scapy
```

## ⚠️ Important Notes

* **Administrator/root privileges are required** to capture network packets:

  ```bash
  sudo python3 sniffer.py ...
  ```

* Ensure the selected network interface exists and is active.

* Scapy must be installed for the script to function properly.

* Recommended for **Linux/macOS** environments. Windows may require additional setup and administrative access to support Scapy.

