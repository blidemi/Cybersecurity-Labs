# CTF Task 5 — Hidden Flag in HTML Source

## Task

> Huh, where is the flag?

**Task file:** `task5_result.png`

## Goal

Find the hidden flag.

## Approach

This challenge took me much longer than I expected.

At first, I could not understand where the flag was supposed to be or what I should look for. I tried to inspect the page visually, but there was no obvious clue that pointed directly to the answer.

After spending quite some time on the challenge, I decided to go back to one of the basic techniques I had already used before: checking the webpage's source code.

I selected the visible text on the page and inspected the HTML using the browser's developer tools.

To my surprise, the flag was hidden in the HTML source.

It was one of those moments when I was both very happy that I found it and slightly annoyed that I had spent so much time looking for something that was actually right there. 😅

## Result

```text
THM{wh173_fl46}
```

## Flag

```text
THM{wh173_fl46}
```

## What I Learned

This challenge reminded me not to overcomplicate a problem when there are no obvious clues.

When a webpage does not reveal anything useful visually, checking the **HTML source code** and the browser's **developer tools** should be one of the basic things to try.

Sometimes the simplest approach is the one that works.
