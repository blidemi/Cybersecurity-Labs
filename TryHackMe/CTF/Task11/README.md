
# CTF Task 11 — Repairing a Corrupted PNG

## Task

> I accidentally messed up with this PNG file.
> Can you help me fix it? Thanks, ^^

## Objective

Repair the corrupted PNG file and find its content.

**Task file:** `spoil_1577979329740.png`

## Investigation

This challenge was different from the previous image-based tasks because the problem was not simply about finding hidden data.

The file itself appeared to be damaged.

My first step was to inspect the beginning of the file in hexadecimal rather than treating it only as an image.

I used:

```bash
head -c 16 spoil_1577979329740.png | xxd
```

This returned:

```text
00000000: 2333 445f 0d0a 1a0a 0000 000d 4948 4452
```

The first four bytes immediately looked suspicious:

```text
23 33 44 5F
```

In ASCII, these bytes correspond to:

```text
#3D_
```

However, a valid PNG file should begin with the PNG signature:

```text
89 50 4E 47 0D 0A 1A 0A
```

Comparing the two made the problem much clearer.

The first four bytes had been changed, while the following PNG signature bytes were still present:

```text
Corrupted:
23 33 44 5F 0D 0A 1A 0A

Expected:
89 50 4E 47 0D 0A 1A 0A
```

This suggested that the file had not been completely destroyed. The PNG structure was still there, but its signature had been intentionally modified.

That was the key observation.

## Checking for a Hidden Flag

Before repairing the image, I also tried searching the file for a readable TryHackMe flag:

```bash
strings spoil_1577979329740.png | grep -i "THM"
```

Nothing was returned.

This suggested that the flag was not simply stored as readable text in the corrupted file. Instead of continuing to search blindly, I focused on repairing the file first.

## Repairing the PNG

I decided to restore the first four bytes to the correct PNG signature.

### Method 1 — Python

I used Python directly from the terminal:

```bash
python3 -c "with open('spoil_1577979329740.png', 'rb') as f: d = f.read(); open('fixed.png', 'wb').write(b'\x89PNG' + d[4:])"
```

The important part of this command is:

```python
b'\x89PNG' + d[4:]
```

It replaces only the first four bytes and keeps the rest of the original file unchanged.

The result was saved as:

```text
fixed.png
```

### Method 2 — Hex Editor

I also considered a more visual approach using a hex editor in VS Code.

The first four bytes:

```text
23 33 44 5F
```

can be replaced with:

```text
89 50 4E 47
```

This produces the same repaired PNG header.

## Result

After repairing the file, `fixed.png` could be opened normally as an image.

The restored image contained the TryHackMe logo and a flag:

```text
THM{y35_w3_c4n}
```

![Recovered image](fixed.png)

## Extracting the Text with OCR

Instead of manually copying the flag from the image, I decided to experiment with OCR.

I installed the required Python library and Tesseract:

```bash
python3 -m pip install pytesseract pillow
brew install tesseract
```

Then I used:

```bash
python3 -c "import pytesseract, PIL.Image; print(pytesseract.image_to_string(PIL.Image.open('fixed.png')))"
```

The terminal returned:

```text
10 10
1110 Hack
01 010

THM{y35_w3_c4n}
```

The OCR output was not perfect, but it successfully recognized the flag.

## Flag

```text
THM{y35_w3_c4n}
```

## What I Learned

This challenge introduced me to a different type of file analysis: **repairing a corrupted file by inspecting its binary structure**.

The most important clue was not the visible image itself, but the bytes at the beginning of the file.

I learned that file formats often have specific signatures, or **magic bytes**, that can be used to identify the file type and verify whether its header is valid.

In this case, recognizing the PNG signature allowed me to identify exactly what had been damaged.

I also practiced:

* Hexadecimal inspection with `xxd`
* Working with binary files in Python
* Understanding file signatures / magic bytes
* Repairing a corrupted file
* Using OCR with Tesseract
* Combining command-line tools with Python

## Reflection

The interesting part of this challenge was that I initially approached the file as something that needed to be analyzed for hidden information.

The more useful question turned out to be:

> **"Is the file itself valid?"**

Inspecting the first bytes changed the direction of the investigation.

Instead of searching for the flag immediately, I first identified the structural problem, repaired the file, and then analyzed the recovered content.

This was a useful introduction to a forensic mindset:

```text
Inspect
   ↓
Identify the anomaly
   ↓
Form a hypothesis
   ↓
Repair the artifact
   ↓
Analyze the recovered file
   ↓
Extract the result
```

The flag was the final answer, but the more valuable lesson was learning to investigate the **file structure itself** when something appears to be broken.
