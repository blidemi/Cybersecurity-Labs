# CTF Task 21 — Read the Packet

## Task

> I just hacked my neighbor's WiFi and try to capture some packet. He must be up to no good. Help me find it.

**Question:**

> Did you capture my neighbor's flag?

## Objective

Analyze the captured network traffic and find the hidden flag inside the packet capture.

## Investigation

The challenge provided a packet capture file:

```text
flag.pcapng
```

The `.pcapng` extension immediately suggested that this was a **packet capture** that could be analyzed using a network analysis tool.

I used **Wireshark** to inspect the captured traffic.

Unlike the previous challenges where I was working mainly with images, encodings, or files, this time the information was hidden inside **network communication**.

## Opening the Capture

I opened the `.pcapng` file in Wireshark and started looking through the captured packets.

There were many packets, so inspecting every packet manually would not be efficient.

Instead, I focused on protocols that could contain readable application data.

The challenge mentioned a hacked WiFi connection and captured packets, so I looked specifically for **HTTP traffic**.

## Finding the HTTP Request

One useful approach was to filter the traffic using:

```text
http.request.method == GET
```

This reduced the number of packets and made the relevant HTTP request much easier to identify.

The request pointed to:

```text
/flag.txt
```

This was a strong indication that the captured traffic contained the file we were looking for.

## Following the HTTP Stream

I selected the relevant packet and used:

```text
Follow → HTTP Stream
```

Wireshark then reconstructed the HTTP communication between the client and server.

The response contained the contents of:

```text
flag.txt
```

Inside the response was the flag.

Another way to reach the same result is through:

```text
File → Export Objects → HTTP
```

Wireshark then displays the files transferred through HTTP, including:

```text
flag.txt
```

Opening the extracted content reveals the same flag.

## Result

The captured network traffic contained:

```text
THM{d0_n07_574lk_m3}
```

## Flag

```text
THM{d0_n07_574lk_m3}
```

## What I Learned

This challenge introduced me to **network traffic analysis** using Wireshark.

I learned that a packet capture is not simply a collection of random packets. It can contain reconstructed network conversations and transferred files.

Important concepts from this task were:

* PCAP / PCAPNG files
* Wireshark
* HTTP requests and responses
* HTTP GET requests
* Following a network stream
* Exporting objects from captured traffic

The important idea was that instead of looking for the flag directly in every packet, I could identify the relevant communication and reconstruct the data being transferred.

## Investigation Flow

```text
PCAPNG file
    ↓
Open in Wireshark
    ↓
Inspect captured traffic
    ↓
Filter HTTP GET requests
    ↓
Find /flag.txt
    ↓
Follow HTTP stream
    ↓
Read server response
    ↓
Recover the flag
```

## Reflection

This challenge changed the way I think about network data.

Previously, when I saw an unknown file, I mostly asked:

> "What is hidden inside this file?"

Here the better question was:

> **"What happened during this network communication?"**

A packet capture can preserve parts of an entire conversation, including requests, responses, and transferred files.

This was my first practical introduction to reading captured network traffic with Wireshark, and it showed me how useful packet analysis can be during a security investigation.

> **Packets are not just data — they are traces of communication.**

