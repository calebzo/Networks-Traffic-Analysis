 Network Traffic Analysis Using Wireshark

## Project Overview
This project demonstrates the analysis of **DNS**, **HTTP**, and **TCP** traffic using Wireshark. Each capture is explained with details on the type of traffic and the corresponding packet analysis.

---

## DNS Traffic Capture
### 📝 Task: Capture DNS Query for `google.com`
1. Opened Wireshark and started capturing packets.
2. Ran the following command to perform a DNS query for `google.com`:
   ```sh
   nslookup google.com   # Windows
   dig google.com        # Linux/macOS

   Captured the DNS request and response.
3. Filtered DNS traffic with:
   dns

Capture Details:
Query Name: google.com
Response IP: 192.168.5.16

Captured File: captures/dns_lookup_google_20250403.pcap


## HTTP Traffic Capture
### 📝 Task: Capture HTTP Request for 'http://example.com'
1. Opened Wireshark and started capturing packets.

2. Visited http://example.com in a browser.

3. Filtered HTTP traffic with:
tcp.port == 80

Capture Details:
Request Type: GET / HTTP/1.1
Response Status: HTTP/1.1 200 OK
Content-Type: text/html

Captured File: captures/http_request_20250403.pcap

## TCP Handshake Capture
### 📝 Task: Capture TCP Three-Way Handshake
1. Opened Wireshark and started capturing packets.

2. Ran the following command to initiate a TCP connection:
   curl http://example.com

3. Filtered TCP handshake packets with:
tcp.flags.syn == 1

Capture Details:
SYN Packet: Client requests connection to server on port 80.
SYN-ACK Packet: Server acknowledges the request.
ACK Packet: Client confirms the connection.

Captured File: captures/tcp_handshake_20250403.pcap


## How to Reproduce These Captures
To reproduce these captures on your own:

Open Wireshark and start capturing on your network interface.

Perform one of the following tasks:

1. Run nslookup or dig to generate DNS traffic.

2. Visit http://example.com to generate HTTP traffic.

3. Use telnet or curl to establish a TCP connection.

Use the relevant Wireshark filter to capture the desired traffic:

For DNS traffic, use the filter:
dns

For HTTP traffic, use the filter:
tcp.port == 80

For TCP handshake traffic, use the filter:
tcp.flags.syn == 1

Save the captured file for analysis in .pcap format.