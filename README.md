# Cybersecurity Labs

> A hands-on cybersecurity learning repository focused on learning by doing, documenting mistakes, and building practical problem-solving skills.

## About This Repository

This repository documents my journey into cybersecurity through hands-on labs, CTF challenges, experiments, and small practical exercises.

I am building my cybersecurity knowledge step by step. Instead of only collecting completed tasks, I use this repository to document **how I approached a problem, what I expected to happen, what went wrong, and how I adapted my approach**.

The goal is not simply to collect flags.

The goal is to understand **why a technique works**, become comfortable with security tools, and gradually develop a way of thinking that can be applied to unfamiliar problems.

---

## How I Approach Challenges

When I encounter a new challenge, I try to follow a simple process:

```text
Observe
   ↓
Form a hypothesis
   ↓
Test the hypothesis
   ↓
Analyze the result
   ↓
If it fails → change the approach
   ↓
Understand why the solution works
   ↓
Document what I learned
```

I do not always get the right answer on the first attempt.

Sometimes I choose the wrong tool, misunderstand the file format, or make an incorrect assumption. I keep those moments in my write-ups because troubleshooting and changing direction are important parts of real technical work.

---

## What You Will Find Here

The repository currently contains hands-on **TryHackMe CTF challenges** covering areas such as:

- Web and HTML source inspection
- Hidden and invisible data
- File analysis
- Binary files
- Image analysis
- Steganography
- QR codes
- Base64 and Base58 encoding
- Caesar / ROT-style ciphers
- Python scripting
- Command-line tools
- Basic digital forensics concepts

As I progress, I plan to expand the repository with more challenging labs and additional cybersecurity topics.

---

## CTF Write-ups

| Task | Topic | Main technique |
|------|-------|----------------|
| [Task 2](TryHackMe/CTF/Task2/) | Base64 | Python / Base64 decoding |
| [Task 3](TryHackMe/CTF/Task3/) | Hidden data in image | `strings` + `grep` |
| [Task 4](TryHackMe/CTF/Task4/) | Steganography | Steganography analysis |
| [Task 5](TryHackMe/CTF/Task5/) | Hidden text | Visual inspection |
| [Task 6](TryHackMe/CTF/Task6/) | QR code | `zbarimg` |
| [Task 7](TryHackMe/CTF/Task7/) | Binary file analysis | File inspection |
| [Task 8](TryHackMe/CTF/Task8/) | Base58 | Python / Base58 decoding |
| [Task 9](TryHackMe/CTF/Task9/) | Caesar cipher | Python / substitution |
| [Task 10](TryHackMe/CTF/Task10/) | Hidden HTML data | Browser developer tools |

> The write-ups describe my actual solving process, including unsuccessful attempts and changes in approach.

---

## Tools & Technologies

### Currently practicing

```text
Python
Bash / Terminal
VS Code
Git & GitHub
Browser Developer Tools
```

### Security tools and techniques encountered

```text
strings
grep
zbarimg
steghide
Aperi'Solve
CyberChef
Base64 / Base58
Caesar / ROT ciphers
HTML inspection
Basic file analysis
```

I am learning these tools through practical use rather than trying to memorize them separately from real problems.

---

## Learning Philosophy

One of the main things I am trying to develop is the ability to work with **unknown problems**.

A CTF challenge does not always tell you:

> "Use this tool."

Instead, it may give you a file, an image, a strange string, or a webpage and expect you to figure out what you are looking at first.

Because of this, I try to ask questions such as:

- What exactly am I looking at?
- What assumptions am I making?
- What evidence supports my hypothesis?
- What can I test quickly?
- Why did my first approach fail?
- What other explanation could fit the evidence?
- What can I learn from the result?

This mindset is one of the main reasons I am interested in cybersecurity.

---

## What I Am Learning From CTFs

The biggest lesson so far is that solving a challenge is not always about knowing the answer immediately.

Sometimes the most useful result is a failed attempt.

For example:

```text
Wrong assumption
      ↓
Unexpected result
      ↓
Investigate the result
      ↓
Learn something new
      ↓
Better hypothesis
      ↓
Solution
```

This repository is therefore also a record of my **technical development**.

As the challenges become more difficult, I want the write-ups to show not only that I can solve them, but that my reasoning becomes more structured and my choice of tools becomes more deliberate.

---

## Current Focus

My current focus is building a strong foundation in:

- Linux and command-line usage
- Python for cybersecurity
- Networking fundamentals
- Web security fundamentals
- File and data analysis
- Cryptography fundamentals
- CTF methodology
- Security tooling

I am particularly interested in understanding how systems can be analyzed from an attacker's perspective and how vulnerabilities can be identified and understood.

---

## Progress

This repository will continue to evolve as I learn.

The early challenges are intentionally documented in detail because they show where my understanding started.

Over time, I want to be able to look back at these first write-ups and clearly see the progression:

```text
Learning the basics
        ↓
Understanding common techniques
        ↓
Using tools independently
        ↓
Combining multiple techniques
        ↓
Solving unfamiliar problems
        ↓
Building deeper security knowledge
```

---

## Why I Keep Write-ups

Writing down a solution forces me to explain **why** something worked instead of simply remembering the final answer.

For each challenge, I try to document:

1. What the challenge provided
2. What I noticed
3. What I initially suspected
4. What I tested
5. What failed and why
6. What eventually worked
7. What I learned from the challenge

The flag is the final result.

**The reasoning is the part I want to keep.**

---

## Disclaimer

These write-ups are created for educational purposes and document my personal learning process while solving authorized CTF and training challenges.

They should not be interpreted as professional security assessments or as a substitute for proper authorization when testing real systems.

---

## Next Steps

This repository is a work in progress.

My next goal is to move beyond basic encoding and file-analysis challenges and gradually explore more areas of cybersecurity, including:

- Web application security
- Networking
- Linux security
- Enumeration
- Authentication vulnerabilities
- Exploitation fundamentals
- Defensive security concepts
- More advanced CTF challenges

I am building the foundation first and increasing the difficulty as my understanding grows.

---

**Learning by doing. Breaking assumptions. Testing ideas. Improving one challenge at a time.**
