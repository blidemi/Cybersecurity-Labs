# CTF Task 13 — Brainfuck

## Task

> What is this?

```text
++++++++++[>+>+++>+++++++>++++++++++<<<<-]>>>++++++++++++++.
------------.+++++.>+++++++++++++++++++++++.
<<++++++++++++++++++.>>-------------------.
---------.++++++++++++++.++++++++++++.<++++++++++++++++++.
+++++++++.<+++.+.>----.>++++.
```

**Goal:** Decode the given code and find the flag.

## Investigation

At first, I assumed that the strange sequence might be some kind of encryption or encoding.

It definitely did not look like Base64, Base58, hexadecimal, or any of the other formats I had already encountered.

The string was made almost entirely of a small set of symbols:

```text
+ - < > [ ] . ,
```

Instead of trying random decoders, I checked the challenge hint.

The hint was:

```text
binaryfuck
```

This led me to **Brainfuck**, an esoteric programming language designed around an extremely small instruction set.

At this point, the challenge finally started to make sense.

## What Is Brainfuck?

Brainfuck is not an encryption algorithm.

It is a programming language that uses only eight main commands:

| Symbol | Meaning |
|--------|---------|
| `>` | Move the data pointer to the right |
| `<` | Move the data pointer to the left |
| `+` | Increment the current memory cell |
| `-` | Decrement the current memory cell |
| `.` | Output the value of the current cell |
| `,` | Read one byte of input |
| `[` | Start a loop |
| `]` | End a loop |

The language is intentionally minimal, which makes even simple programs extremely difficult to read manually.

That explained why the challenge looked so strange.

## Decoding

I decided not to try to manually execute the Brainfuck instructions.

Instead, I used an online Brainfuck interpreter and pasted the code into it.

The interpreter executed the program and converted its output into readable text.

![Brainfuck decoder result](./Снимок%20экрана%202026-08-18%20в%2016.00.28.png)

The output was:

```text
THM{0h_my_h34d}
```

## Flag

```text
THM{0h_my_h34d}
```

## What I Learned

The main lesson from this challenge was that **not every strange-looking string is encrypted data**.

Sometimes the data is actually a program.

Before this challenge, I was mainly thinking in terms of:

```text
Cipher / Encoding
        ↓
Decode
        ↓
Text
```

This challenge introduced a different possibility:

```text
Unknown symbols
        ↓
Identify the language
        ↓
Execute / interpret the program
        ↓
Read the output
```

I also learned to pay more attention to the **character set** of an unknown string.

Seeing almost exclusively:

```text
+ - < > [ ] . ,
```

was a useful clue because these are the eight core Brainfuck instructions.

## Reflection

This was one of the more confusing challenges for me because I initially tried to classify the input as a cipher.

The important step was realizing that I was asking the wrong question.

Instead of:

> "What encryption is this?"

the better question was:

> **"What kind of code am I looking at?"**

Once I identified Brainfuck, the solution became much simpler: find an appropriate interpreter and execute the code.

This challenge taught me to avoid forcing an unfamiliar piece of data into a familiar category.

Sometimes the first step in solving a CTF is not decoding the data — it is **correctly identifying what the data actually is.**
