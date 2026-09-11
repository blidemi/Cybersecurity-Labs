# CTF Task 15 — Binary Walk

## Task

> Please exfiltrate my file :)

> Flag! Flag! Flag!

## Objective

Analyze the provided image and extract the hidden file containing the flag.

**Task file:** `hell_1578018688127.jpg`

## Investigation

At first glance, the file looked like an ordinary JPEG image.

However, the wording of the challenge was interesting:

> "Please exfiltrate my file :)"

This made me think that the important part might not be the visible image itself, but something **hidden inside the file**.

Instead of opening the image and looking for visible clues, I decided to inspect the file structure.

The hint for this challenge was:

```text
binwalk
```

That immediately suggested checking whether the image contained additional embedded files.

## File Analysis with Binwalk

I used:

```bash
binwalk hell_1578018688127.jpg
```

The output showed that the file contained more than just JPEG image data.

Among the detected structures was a ZIP archive:

```text
JPEG image data
TIFF image data
ZIP archive data
```

This was the important discovery.

The file was not simply an image — another file had been embedded inside it.

## Extracting the Embedded File

I used the extraction option:

```bash
binwalk -e hell_1578018688127.jpg
```

The `-e` option tells Binwalk to automatically extract recognized embedded files.

After extraction, Binwalk created an extracted directory containing:

```text
hello_there.txt
```

I then inspected the file:

```bash
cat hello_there.txt
```

The contents were:

```text
Thank you for extracting me, you are the best!

THM{y0u_w4lk_m3_0u7}
```

The flag was successfully recovered.

## Flag

```text
THM{y0u_w4lk_m3_0u7}
```

## What I Learned

This challenge introduced me to **Binwalk** and the idea that one file can contain additional data that is not immediately visible.

I learned that when analyzing a suspicious file, it is useful to look beyond its apparent format.

A file named `.jpg` does not necessarily mean that it contains only JPEG data.

Binwalk can help identify:

- Embedded files
- File signatures
- Archives
- Additional data inside a file
- Different file formats contained within a larger file

In this case, the JPEG contained a ZIP archive, which in turn contained the text file with the flag.

## Investigation Flow

The whole process can be summarized as:

```text
JPEG file
    ↓
Inspect file structure
    ↓
Run Binwalk
    ↓
Detect embedded ZIP archive
    ↓
Extract embedded data
    ↓
Find hello_there.txt
    ↓
Read the file
    ↓
Flag found
```

## Reflection

The main lesson from this challenge was to **not trust a file extension alone**.

Before this task, I mostly thought of an image as an image that needed to be visually inspected.

Here, the useful information was not visible at all.

The important question became:

> **"What else is inside this file?"**

This changed the way I think about file analysis. When a challenge gives me a seemingly normal file, I should consider whether it contains additional data or another embedded file format.

This was my first practical experience with **file carving / embedded-file extraction**, and it showed me why tools such as Binwalk are useful during basic digital forensics.

> **A file can look like one thing while containing something completely different inside.**
