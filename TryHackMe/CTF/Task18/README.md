# CTF Task 18 — Dig Up the Past

## Task

> Sometimes we need a 'machine' to dig the past.

**Targeted website:** `https://www.embeddedhacker.com/`

**Targeted date:** `2 January 2020`

## Objective

Find the hidden information from an older version of the website.

## Investigation

At first, the task looked like it required searching through the current website.

However, the wording contained two important clues:

> **"machine"**
> **"past"**

This made me think about a tool that allows us to look at previous versions of websites.

That led me to the **Wayback Machine**.

The Wayback Machine is an Internet Archive service that stores snapshots of websites taken at different points in time. This makes it possible to investigate what a website looked like in the past.

## Searching the Archived Website

I opened the Wayback Machine and searched for:

```text
https://www.embeddedhacker.com/
```

The challenge gave me a very specific date:

```text
2 January 2020
```

So instead of looking through random snapshots, I focused on the archive from that date.

One available snapshot was:

```text
2 January 2020
```

I opened it and inspected the archived version of the website.

While looking through the old page, I found the relevant content containing the TryHackMe flag.

## Result

The archived page revealed:

```text
THM{ch3ck_th3_h4ckb4ck}
```

## Flag

```text
THM{ch3ck_th3_h4ckb4ck}
```

## What I Learned

This challenge introduced me to **web archives as an OSINT and investigation tool**.

A website should not always be treated as something that only exists in its current state. Previous versions can contain information that has since been removed or changed.

The important part of this challenge was recognizing that the date in the task was not just additional information — it was a clue telling me **when to look**.

## Investigation Flow

```text
Challenge wording
      ↓
"machine" + "past"
      ↓
Wayback Machine
      ↓
Search embeddedhacker.com
      ↓
Select 2 January 2020
      ↓
Inspect archived page
      ↓
Find hidden information
      ↓
Flag
```

## Reflection

This challenge was much less about using a complicated technical tool and more about **interpreting the clues correctly**.

Instead of asking:

> "Which tool can decode this?"

I had to ask:

> **"What kind of information is the challenge asking me to find, and where would that information exist?"**

That was the main lesson for me.

Sometimes the most important part of solving a CTF is not the tool itself, but recognizing what the clues are pointing toward.

> **When the present does not contain the answer, look at the past.**

