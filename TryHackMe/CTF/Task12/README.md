# CTF Task 12 — OSINT: Finding a Hidden Flag on Reddit

## Task

> Read it.

> Some hidden flag inside TryHackMe social account.

## Objective

Find the hidden flag in a TryHackMe-related social media account.

## Investigation

This challenge was different from the previous ones because the information was not hidden inside a file or encoded directly in the task.

Instead, I had to **find the right information source first**.

The hint suggested looking for a TryHackMe social media account, so I initially searched through several platforms, including Twitter and Instagram.

These searches did not lead anywhere useful.

At this point, I realized that simply searching for accounts containing `THM` was too broad. I needed to narrow down the search.

## Finding the Right Platform

I went back to the task hint and eventually focused on Reddit.

I searched within the TryHackMe-related Reddit community and spent some time looking through posts and comments.

The important clue came from a comment that suggested a more specific way to search for the information.

This changed my approach from manually browsing social media to using **search operators**.

## Search Strategy

The search query I ended up using was:

```text
site:"reddit.com" intext:"THM" intitle:"tryhackme"
```

This query combines several search operators:

- `site:"reddit.com"` — restricts the search to Reddit
- `intext:"THM"` — looks for pages containing `THM`
- `intitle:"tryhackme"` — looks for pages with `tryhackme` in the title

This made the search much more targeted than simply searching for `THM` across social media.

## Decoding the Clue

During this challenge I also discovered **CyberChef**, a web-based tool that provides many operations for decoding, encoding, encryption, hashing, and data manipulation.

I used the **From Base64** operation to decode the provided string.

The decoded result gave me an additional search instruction:

```text
JUST ONE MORE STEP !!!!!!!
site:"reddit.com" intext:"THM" intitle:"tryhackme"
```

![CyberChef result](./Снимок%20экрана%202026-08-18%20в%2015.40.14.png)

This was the key step that connected the encoded data with the OSINT investigation.

## Finding the Flag

After applying the search query to Reddit, I found the relevant TryHackMe-related post.

The flag was visible directly in the post:

```text
THM{50c14l_4cc0un7_15_p4r7_0f_051n7}
```

![Reddit result](./Снимок%20экрана%202026-08-18%20в%2015.32.10.png)

The final answer was accepted by TryHackMe:

![TryHackMe result](./Снимок%20экрана%202026-08-18%20в%2015.34.12.png)

## Flag

```text
THM{50c14l_4cc0un7_15_p4r7_0f_051n7}
```

## What I Learned

This challenge introduced me to **OSINT (Open-Source Intelligence)** in a practical way.

I learned that finding information online is not always about searching harder. It is often about **searching more precisely**.

I also learned how search operators can significantly reduce irrelevant results and help locate specific information.

Another useful discovery was **CyberChef**. It provides a large collection of operations for working with encoded and transformed data, which makes it useful when investigating an unfamiliar string.

## Reflection

The main difficulty in this challenge was not the decoding itself.

The harder part was figuring out **where to look and how to search**.

My first searches across social media were too broad and did not produce useful results. Instead of continuing to search randomly, I had to use the clues provided by the challenge and change my strategy.

The process became:

```text
Broad search
    ↓
No useful results
    ↓
Reconsider the clue
    ↓
Identify Reddit as the relevant platform
    ↓
Find a search hint
    ↓
Decode the clue with CyberChef
    ↓
Use targeted search operators
    ↓
Find the Reddit post
    ↓
Flag found
```

This challenge showed me that **OSINT is not simply "searching Google."** It involves recognizing useful clues, choosing the right source, constructing precise queries, and continuously refining the investigation based on the results.

The most valuable lesson for me was:

> **When a search produces too much noise, the solution is often not more searching — it is better search logic.**
