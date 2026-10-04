# DNS Lab Notes

## Objective

Capture a DNS query and its response using Wireshark.

## What I did

I generated a DNS lookup for `google.com` and captured the
traffic in Wireshark.

## DNS Query

Source: 192.168.0.112
Destination: 192.168.0.1
Protocol: DNS over UDP
Destination Port: 53
Query: google.com
Query Type: A

The client asked the DNS server for the IPv4 address of google.com.

## DNS Response

Source: 192.168.0.1
Destination: 192.168.0.112
Protocol: DNS over UDP
Source Port: 53
Response: No error

The DNS server returned the answer to the client.

## What I observed

1. The client sends a DNS query to the DNS server.
2. DNS traffic in this captxure uses UDP.
3. Port 53 is used by the DNS server.
4. The response has the same transaction ID as the query.
5. The response contains multiple answers for google.com.

## Evidence

- `dns-query-google.png`
- `dns-response-google.png`
