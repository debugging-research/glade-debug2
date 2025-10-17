# Glade

[![app version][app-version]][website]
[![License][license-src]][license-href]

A virtual whiteboard

[website]: https://zhengyuzi.github.io/glade/
[app-version]: https://img.shields.io/badge/dynamic/json?url=https%3A%2F%2Fraw.githubusercontent.com%2Fzhengyuzi%2Fglade%2Fmain%2Fglade%2Fpackage.json&query=%24.version&label=glade&labelColor=e5e7eb&color=6b7280
[license-src]: https://img.shields.io/github/license/zhengyuzi/glade.svg?style=flat&colorA=e5e7eb&colorB=6b7280
[license-href]: https://github.com/zhengyuzi/glade/blob/main/LICENSE

---
# Bug 2
---
## How to Run The Code
1. In your terminal, git clone this repository using `git clone https://github.com/debugging-research/glade-debug2.git`
2. Open the glade folder in VSCode that you just cloned
3. In VSCode terminal run the following commands:
   
`pnpm install`

`pnpm -r build`

`pnpm -C glade run dev`

4. The last command should print a URL like http://localhost:5173/glade/, click that to see the working project in action
---
## Directions
- Inspect the issues (image provided below of what this looks like)
- Document yourself every 5-10 mins with the strategies used and steps taken to debug the errors shown
- Give yourself no more than 45 minutes to complete this task
- If you do not solve the bugs, no problem! Still, document everything and stop when the time is up
- Good luck :)

---
## Error Message Shown:
![](errormessage2.png)
---
## Hints
- inspect the type parameter you gave to the variable in the error message versus the default value and how it is used elsewhere in the code
---
## Intended Behavior Error
---
This bug does not necessarily always occur.

Intended behavior: when you open the app, it should restore your last session’s nodes (shapes/images/text) from local storage (GLADE). If you added nodes, then reload the page, you should see them again.

With the bug: the app treats GLADE as a single node type instead of an array. That mismatch can cause either:
- A crash/overlay during startup when the code tries to iterate/spread the nodes, or
- The board loads empty or behaves inconsistently because it can’t reliably read/write the saved nodes collection.
