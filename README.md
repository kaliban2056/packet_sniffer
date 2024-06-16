# Network Packet Analyzer

This Python script captures and decodes network packets at the Ethernet frame level, providing detailed information about various network protocols. It is useful for network diagnostics, analysis, and learning purposes.

## Features

- Captures network packets using raw sockets.
- Decodes Ethernet frames.
- Analyzes IPv4 packets and extracts header details.
- Decodes and displays ICMP, TCP, and UDP packets.
- Formats and prints packet data in a human-readable format.

## Requirements

- Python 3.x
- Root or administrative privileges to create raw sockets.

## Usage

1. Ensure you have the necessary permissions to run raw socket operations.
2. Run the script using Python:

```
sudo python3 packet_analyzer.py
```

3. The script will start capturing and printing network packets.

## Functions

- main(): The main function that sets up the raw socket and starts capturing packets.
- ethernet_frame(data): Unpacks and returns Ethernet frame details.
- get_mac_addr(bytes_addr): Converts a MAC address from bytes to a human-readable format.
- ipv4_packet(data): Unpacks and returns IPv4 packet details.
- ipv4(addr): Converts an IPv4 address from bytes to a human-readable format.
- icmp_packet(data): Unpacks and returns ICMP packet details.
- tcp_segment(data): Unpacks and returns TCP segment details.
- udp_segment(data): Unpacks and returns UDP segment details.
- format_multi_line(prefix, string, size=80): Formats and returns multi-line packet data for better readability.

## Example Output

```
Ethernet Frame: 
Destination: AA:BB:CC:DD:EE:FF, Source: 11:22:33:44:55:66, Protocol: 8
    IPv4 Packet:
        Version: 4, Header Length: 20, TTL: 64
        Protocol: 6, Source: 192.168.0.1, Target: 192.168.0.2
            TCP Segment:
            Source Port: 443, Destination Port: 55678
            Sequence: 123456789, Acknowledgment: 987654321
            Flags:
                URG: 0, ACK: 1, PSH: 0, RST: 0, SYN: 1, FIN: 0
            Data:
                \x50\x61\x63\x6b\x65\x74\x20\x44\x61\x74\x61\x2e\x2e\x2e
```

## Notes

- This script must be run with root or administrative privileges to capture network packets.
- Ensure you have the necessary permissions and that capturing network packets is compliant with your network policies and local laws.
