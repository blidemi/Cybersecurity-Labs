# CTF Task 8 — Base58 Decoding

## Task

> Can you decode it?

```text
3agrSy1CewF9v8ukcSkPSYm3oKUoByUpKG4L
```

## Goal

Decode the given string and find the flag.

## Approach

I had already encountered **Base64** encoding before, so I first checked whether this string could be Base64.

The string did not look like the Base64 strings I had seen before, so I decided to investigate other Base encoding schemes.

I considered several common Base encodings:

- Base16
- Base32
- Base58
- Base85
- Base91

Based on the characters used in the string and its overall format, I determined that it was most likely **Base58**.

## Decoding

I could have used an online tool such as [CyberChef](https://gchq.github.io/CyberChef/) to decode the string, but I wanted to practice doing it myself with Python.

First, I installed the `base58` Python package from the terminal:

```bash
python3 -m pip install base58
```

Then I created a `solve.py` file and used the `base58` library to decode the string:

```python
import base58
text = "3agrSy1CewF9v8ukcSkPSYm3oKUoByUpKG4L"
print(base58.b58decode(text).decode())

```

I ran the script from the terminal:

```bash
python3 solve.py
```

The decoded result was:

```text
THM{17_h45_l3553r_l3773r5}
```

## Flag

```text
THM{17_h45_l3553r_l3773r5}
```

## What I Learned

This challenge helped me understand the difference between several Base encoding schemes and how to recognize them by their character sets and format.

I also learned how to use a Python library to decode Base58 data instead of relying on an online decoder.

Although tools such as CyberChef can make decoding much faster, implementing the process with Python is useful for understanding what is happening and for practicing the command-line workflow.
