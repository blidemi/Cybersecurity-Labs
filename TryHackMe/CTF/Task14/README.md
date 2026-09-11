# CTF Task 14 — XOR: An Exclusive!

## Task

> An exclusive!

The challenge provides two values:

```text
S1: 44585d6b2368737c65252166234f20262d
S2: 10101010101010101010101010101010
```

The task asks to crack them and find the flag.

## First Impression

At first, I was not sure what kind of encoding or encryption I was looking at.

The first value clearly looked like hexadecimal data because it consisted of hexadecimal characters:

```text
44585d6b2368737c65252166234f20262d
```

The second value looked like binary:

```text
10101010101010101010101010101010
```

I had already encountered several encoding techniques in previous challenges, but XOR was still unfamiliar to me.

Instead of randomly trying different decoders, I decided to investigate what operation the challenge was pointing toward.

## Understanding the Hint

The title of the challenge is:

```text
An exclusive!
```

This is a clue toward **exclusive OR**, commonly written as **XOR**.

XOR is a logical operation that compares two values bit by bit.

Its basic rule is:

| A | B | A XOR B |
|---|---|---------|
| 0 | 0 | 0 |
| 0 | 1 | 1 |
| 1 | 0 | 1 |
| 1 | 1 | 0 |

In other words, XOR produces `1` when the two input bits are different and `0` when they are the same.

## Using AI as a Learning Aid

Because XOR was a new concept for me, I used an AI assistant to help me understand the hint and determine what operation should be applied to the two values.

I specifically provided the challenge data together with the hint:

```text
S1 XOR S2
```

The important part was not simply getting the final answer, but understanding **why XOR was the relevant operation**.

The result of the XOR operation produced readable ASCII text.

![XOR result](./Снимок%20экрана%202026-09-11%20в%2014.49.35.png)

## Result

After applying XOR, the hexadecimal result could be interpreted as ASCII text.

The decoded output was:

```text
THM{3xclu51v3_06=}
```

## Flag

```text
THM{3xclu51v3_06=}
```

## What I Learned

This challenge introduced me to **XOR**, which I had not previously used in my CTF practice.

I learned that XOR is not simply another encoding format. It is a **bitwise logical operation** that is commonly used in programming, cryptography, data manipulation, and security-related tasks.

I also learned to pay attention to the wording of a challenge.

The title:

```text
An exclusive!
```

was not random text. It was a clue pointing toward **exclusive OR**.

## Reflection

This challenge was also a useful reminder that when I encounter something unfamiliar, I do not need to immediately know the answer.

My process was:

```text
Unknown data
    ↓
Identify the format
    ↓
Look for clues in the challenge
    ↓
Recognize "exclusive" → XOR
    ↓
Learn how XOR works
    ↓
Apply the operation
    ↓
Convert the result to readable text
    ↓
Flag
```

I also used AI as a learning tool rather than treating the output as something to blindly copy.

My goal was to understand what XOR was doing and why the operation produced readable data.

The main lesson from this challenge was:

> **When a technique is unfamiliar, understanding the operation is more valuable than simply obtaining the answer.**
