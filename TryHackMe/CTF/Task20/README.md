# CTF Task 20 — Small Bases

## Task

> Decode the following text.

```text
581695969015253365094191591547859387620042736036246486373595515576333693
```

## Objective

Convert the given number into readable text and find the flag.

## Investigation

At first, the value looked like a huge random number.

However, the challenge hint gave a very useful direction:

```text
dec → hex → ascii
```

This meant that the number should be treated as a **decimal representation**, then converted to hexadecimal, and finally interpreted as ASCII characters.

So the solving process was:

```text
Decimal
   ↓
Hexadecimal
   ↓
ASCII
   ↓
Readable text
```

## Step 1 — Decimal to Hexadecimal

The original value was:

```text
581695969015253365094191591547859387620042736036246486373595515576333693
```

I converted this decimal number to hexadecimal.

The resulting hexadecimal data represents the bytes of the final text.

## Step 2 — Hexadecimal to ASCII

Next, I converted the hexadecimal representation into ASCII.

This produced:

```text
THM{17_ju57_4n_0rd1n4ry_b4535}
```

The apparently random decimal number was therefore simply another representation of the same underlying data.

## Flag

```text
THM{17_ju57_4n_0rd1n4ry_b4535}
```

## What I Learned

This challenge helped me understand that the same data can be represented in completely different ways.

A long decimal number may look meaningless at first, but it can represent a sequence of bytes that becomes readable after the correct conversions.

The important distinction is:

```text
Decimal
   ↓
Hexadecimal
   ↓
ASCII
```

This is **encoding / representation conversion**, not encryption.

I also became more comfortable recognizing that a CTF challenge may require identifying the **representation of the data** before trying to decode it.

## Reflection

The most useful clue in this challenge was the hint itself.

Instead of trying random decoding methods, I followed the specified conversion chain:

```text
581695969015253365094191591547859387620042736036246486373595515576333693
                              ↓
                         Decimal → Hex
                              ↓
                           Hex → ASCII
                              ↓
              THM{17_ju57_4n_0rd1n4ry_b4535}
```

This was a relatively simple challenge, but it reinforced an important habit:

> **Before trying to decode something, first determine what representation you are looking at.**

