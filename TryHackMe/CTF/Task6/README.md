# CTF Task 6 — QR Code

## Task

> Such technology is quite reliable.

**Task file:** `ctfimg3.png`

## Goal

Decode the QR code and find the flag.

## Approach

Since the provided file was a QR code image, the first thing that came to my mind was to scan it.

I tried several different approaches to see which one would work.

### 1. Scanning with a phone

The simplest method was to scan the QR code using my phone.

### 2. Online QR decoders

I also tried several online tools:

- [ZXing Decoder](https://zxing.org/w/decode.jspx/)
- [Web QR](https://webqr.com/)

These tools can analyze a QR code image and extract the data stored inside it.

### 3. Using the terminal

Since I am learning cybersecurity and want to become comfortable with command-line tools, I also decided to solve the task from the terminal instead of relying only on online services.

I used **ZBar**, a command-line barcode and QR code scanning utility.

On macOS, I installed it using Homebrew:

```bash
brew install zbar
```

Then I ran:

```bash
zbarimg ctfimg3.png
```

The utility automatically detected and decoded the QR code and printed the text stored inside it.

## Result

```text
THM{qr_m4k3_l1f3_345y}
```

## Flag

```text
THM{qr_m4k3_l1f3_345y}
```

## What I Learned

This challenge showed me that the same task can often be solved using different tools.

A QR code does not require manual decryption. It contains encoded data that can be extracted using a QR scanner or a suitable command-line utility.

I also practiced using a command-line tool instead of relying only on graphical or online solutions.

For future challenges, I want to become more comfortable with command-line tools because they are commonly used in cybersecurity and CTF environments.
