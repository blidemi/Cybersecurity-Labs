# CTF Task 2 — Base64 Decoding

## Task

> Can you decode the following?

```text
VEhNe2p1NTdfZDNjMGQzXzdoM19iNDUzfQ==
```

> Feed me the flag!

## Objective

Decode the given string and find the flag.

## Investigation

I had seen strings that looked similar to this one in everyday life, but I had never actually studied what they were or how they worked.

The first thing I needed to determine was what kind of encoding was being used.

The string immediately caught my attention because it ended with:

```text
==
```

This is a common sign of **Base64 encoding**, where `=` characters can be used as padding at the end of the encoded data.

I learned that Base64 is an **encoding scheme**, not an encryption algorithm. It is used to represent binary data using a limited set of printable characters.

## Decoding with Python

I decided to solve the task in VS Code because I was already comfortable working with Python there.

I created a `solve.py` file and used Python's built-in `base64` module:

```python
import base64

text = "VEhNe2p1NTdfZDNjMGQzXzdoM19iNDUzfQ=="

print(base64.b64decode(text).decode())
```

Then I ran the script from the terminal:

```bash
python3 solve.py
```

The output was:

```text
THM{ju57_d3c0d3_7h3_b453}
```

## Flag

```text
THM{ju57_d3c0d3_7h3_b453}
```

## What I Learned

This challenge introduced me to **Base64 encoding** and showed me how encoded data can be recognized and decoded.

I also learned an important distinction between **encoding and encryption**:

- **Encoding** changes the representation of data so it can be stored or transmitted in a convenient format.
- **Encryption** is designed to protect the confidentiality of data and normally requires a key to decrypt it.

I had seen Base64-like strings before but had never investigated how they worked. This challenge gave me a practical reason to learn it and decode one myself.

## Reflection

One of the useful things I learned from this challenge is that recognizing a familiar pattern can provide an important starting point.

The `==` at the end made me suspect Base64, but instead of simply guessing the answer, I researched what the format was and then used Python to verify the hypothesis.

This was also my first step toward becoming more comfortable with recognizing common encodings during CTF challenges.
