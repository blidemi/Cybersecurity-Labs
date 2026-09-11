# CTF Task 19 — Uncrackable!

## Task

> Can you solve the following? By the way, I lost the key. Sorry >.<

```text
MYKAHODTQ{RVG_YVGGK_FAL_WXF}
```

The challenge gives an important hint:

```text
Flag format: TRYHACKME{FLAG IN ALL CAP}
```

## Objective

Decrypt the Vigenère cipher and recover the missing key.

## Investigation

At first, the ciphertext did not look like the encodings I had already encountered in previous challenges.

The challenge also explicitly mentioned that the key was lost.

The hint confirmed that this was a **Vigenère cipher**, so the main problem was not identifying the cipher anymore.

The problem was:

> **How can I decrypt a Vigenère cipher without knowing the key?**

## The Important Clue

The challenge tells us exactly what the beginning of the plaintext should look like:

```text
TRYHACKME{...
```

while the encrypted text begins with:

```text
MYKAHODTQ{...
```

This is called **known-plaintext information**: we know part of the original plaintext and can compare it with the ciphertext.

I aligned the two strings:

```text
Ciphertext:  M Y K A H O D T Q
Plaintext:   T R Y H A C K M E
```

Because Vigenère encryption uses a repeating key, comparing the known plaintext with the ciphertext allows us to determine the corresponding key characters.

The resulting key pattern is:

```text
THM
```

Since the Vigenère key repeats, the effective key becomes:

```text
THMTHMTHM...
```

This was the missing piece.

## Decrypting with CyberChef

I used CyberChef's **Vigenère Decode** operation and supplied the repeating key:

```text
THMTHMTHM
```

The ciphertext:

```text
MYKAHODTQ{RVG_YVGGK_FAL_WXF}
```

then decoded to:

```text
TRYHACKME{YOU_FOUND_THE_KEY}
```

## Flag

```text
TRYHACKME{YOU_FOUND_THE_KEY}
```

## What I Learned

This challenge introduced me to a more interesting use of the Vigenère cipher.

The important part was not simply knowing that Vigenère uses a key. It was learning that **known plaintext can sometimes be used to recover information about the key**.

I also learned that the required flag format itself can become a useful clue.

The challenge effectively gave me:

```text
Ciphertext:
MYKAHODTQ

Known plaintext:
TRYHACKME

↓
Compare the two

↓
Recover the repeating key

THM
```

## Reflection

The biggest lesson from this challenge was that information provided by the challenge should not be treated as decoration.

The line:

```text
Flag format: TRYHACKME{FLAG IN ALL CAP}
```

looked like a formatting requirement at first, but it also gave me known plaintext that could be used to attack the cipher.

The solving process became:

```text
Unknown ciphertext
        ↓
Identify Vigenère
        ↓
No key available
        ↓
Use known flag format
        ↓
Compare plaintext and ciphertext
        ↓
Recover key: THM
        ↓
Vigenère decode
        ↓
Flag
```

This was one of the first challenges where I had to use information about the **expected plaintext** to work backwards toward the key.

> **Sometimes the information you need to solve a cipher is hidden in the format of the answer itself.**

