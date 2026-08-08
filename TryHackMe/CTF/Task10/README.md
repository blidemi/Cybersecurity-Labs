# CTF Task 10 — Hidden Flag in HTML Source

## Task

> No downloadable file, no ciphered or encoded text. Huh.......
> I'm hungry now... I need the flag.

## Goal

Find the flag without any obvious clues, files, or encoded text.

## Approach

There was no downloadable file, encrypted text, or other visible information that could be analyzed.

Since the task provided almost no information, my first assumption was that something might be hidden in the webpage itself.

I selected the author's text and inspected the page source using the browser's developer tools. In the **Elements** tab, I checked the HTML structure of the page.

The flag was directly hidden in the HTML source.

The result can be seen in the screenshot `10taskresult.png`.

## Flag

```text
THM{4lw4y5_ch3ck_7h3_c0m3mn7}
```

## What I Learned

When a CTF challenge provides no obvious files, encoded data, or clues, one of the first things to check is the **HTML source code** and the browser's developer tools.

Not all information is necessarily visible on the page itself. Sometimes the flag or another clue is hidden in the HTML, comments, attributes, or other elements of the webpage.
