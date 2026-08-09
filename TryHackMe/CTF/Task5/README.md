# CTF Task 5 — Hidden Text

## Task

> Huh, where is the flag?

## Objective

Find the hidden flag on the page.

## Investigation

At first, there was no obvious location or clue indicating where the flag was hidden.

Instead of immediately using external tools, I started by examining the page visually and looking for anything unusual.

One detail caught my attention: there was an apparently empty area on the page. I considered that the area might not actually be empty and decided to test this hypothesis by selecting the text.

After selecting the content, previously invisible text became visible.

The hidden text contained the flag:

```text
THM{wh173_fl46}
```

## Why It Worked

The flag was hidden by making the text visually indistinguishable from the page background.

The content therefore existed on the page, but it was not immediately visible during normal browsing.

This is a useful example of why visual inspection should not be limited to what is immediately visible to the user.

## Flag

```text
THM{wh173_fl46}
```

## Key Takeaways

- Apparently empty areas of a webpage may still contain text or other content.
- Selecting text can reveal content that is visually hidden.
- When a challenge provides no obvious clue, it is useful to investigate anomalies rather than immediately assuming that a complex technique is required.
- A good first step is to form a hypothesis and test it instead of trying tools randomly.

## Reflection

This challenge initially took me longer than expected because I was looking for a more complicated hiding technique.

The main lesson for me was that **simple observations can be just as important as technical tools**. Before escalating to more advanced analysis, I should first make sure I have fully investigated what is already in front of me.
