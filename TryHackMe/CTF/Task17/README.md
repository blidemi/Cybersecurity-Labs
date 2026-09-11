# CTF Task 17 — A Sounding QR

## Task

> How good is your listening skill?

The challenge also specifies:

> The flag should be in ALL CAPS.

## Objective

Find out what the bot says and submit the flag in uppercase.

## Investigation

The task provided a QR code:

```text
QRCTF_1579095601577.png
```

Since the challenge was called **"A Sounding QR"**, I suspected that the QR code might contain something other than a simple text message.

My first step was to scan the QR code.

Instead of returning the flag directly, the QR code provided a link to an audio recording.

This was the important clue: the flag was not something I needed to decode from the QR itself. I needed to **listen to what the audio was saying**.

## Following the QR Code

I scanned the QR code and followed the resulting link to the audio recording.

The recording contained a voice message from a bot.

After listening to the recording, the spoken message revealed the flag:

```text
S O U N D I N G Q R
```

The challenge specifically required the flag to be submitted in uppercase, so I kept the result exactly as instructed.

## Flag

```text
THM{SOUNDINGQR}
```

## What I Learned

This challenge was a good reminder that a QR code does not necessarily contain the final answer.

A QR code can point to:

- Text
- A website
- A file
- An image
- An audio recording
- Other resources

In this case, the QR code acted as a **link to another source of information**.

The challenge therefore required two different steps:

```text
QR code
    ↓
Scan
    ↓
Audio link
    ↓
Listen to the recording
    ↓
Identify the spoken message
    ↓
Format it as required
    ↓
Flag
```

## Reflection

What I found interesting about this challenge was that the solution was not another encoding or cryptographic technique.

The important part was understanding what the QR code was actually pointing to.

It also reminded me to pay attention to the wording of a challenge. The title:

> **"A Sounding QR"**

and the question:

> **"How good is your listening skill?"**

were both clues that the next step involved audio rather than another decoding tool.

The main lesson was:

> **Don't assume the QR code itself contains the answer. Follow what it points to and analyze the new source.**
