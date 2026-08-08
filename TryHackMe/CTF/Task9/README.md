# CTF Task 9 — Caesar Cipher

## Task

> Left, right, left, right... Rot 13 is too mainstream. Solve this

```text
MAF{atbe_max_vtxltk}
```

## Goal

Decrypt the message and find the flag.

## Approach

The hint immediately made me think about a letter-shifting cipher.

I first looked into **ROT13**, because the challenge explicitly mentioned it. ROT13 shifts each letter by 13 positions in the alphabet.

However, ROT13 did not produce the expected result.

I then remembered that TryHackMe flags normally follow the `THM{...}` format. The encrypted prefix was:

```text
MAF
```

I used this as a clue to determine the shift:

```text
M → T
A → H
F → M
```

Each letter needs to be shifted **7 positions forward**.

This suggested that the challenge was using a **ROT7 / Caesar-style shift** instead of ROT13.

## First Attempt

I first tried to solve the problem manually and then wrote a simple Python script to automate the shift.

My first approach used `ord()` and `chr()`:

```python
encrypted = "MAF{atbe_max_vtxltk}"
shift = 7

result = ""

for char in encrypted:
    if char.isalpha():
        new_code = ord(char) + shift
        result += chr(new_code)
    else:
        result += char

print(result)
```

I was not completely sure this approach would work because I had not yet considered how to handle letters that go beyond `z`.

The first approach was therefore not the best solution.

## Second Approach

I remembered that Python has `str.maketrans()` and `translate()`, which can be used to create a substitution table.

I created an alphabet and another alphabet shifted by 7 positions:

```python
encrypted = "MAF{atbe_max_vtxltk}"

alphabet = "abcdefghijklmnopqrstuvwxyzABCDEFGHIJKLMNOPQRSTUVWXYZ"
shifted = "hijklmnopqrstuvwxyzabcdefgHIJKLMNOPQRSTUVWXYZABCDEFG"

table = str.maketrans(alphabet, shifted)

print(encrypted.translate(table))
```

The result was:

```text
THM{hail_the_caesar}
```

## Flag

```text
THM{hail_the_caesar}
```

## What I Learned

This challenge helped me understand the basic idea behind **Caesar ciphers and ROT-style transformations**.

I also learned that my first solution does not always have to be correct. Trying an approach, seeing why it fails, and finding another way is part of solving CTF challenges.

One useful clue was the expected `THM{...}` flag format. It helped me recognize the shift and determine that the cipher was using 7 positions instead of the more common ROT13.
