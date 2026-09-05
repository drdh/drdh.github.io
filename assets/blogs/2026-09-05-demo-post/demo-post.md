---
layout: post
title: "Hello World: Rendering Every Markdown Element on This Blog"
permalink: /blog/demo-post.html
date: 2026-09-05 09:00:00 +0800
description: A demo post that exercises headings, lists, tables, code blocks, quotes, and images so we can verify the blog rendering pipeline end to end.
---

This is a demo post: it intentionally uses **every common markdown element** so we can eyeball the result once and trust the rest of the pipeline. If you are reading this on the live site, everything below rendered correctly. 🎉

## Text Formatting

Plain paragraph with **bold**, *italic*, and ***bold italic*** inline. Mix in some `inline code`, a [regular link](https://jekyllrb.com/docs/liquid/), and an angle-bracket autolink: <https://github.com/drdh>. Strikethrough works too: ~~this was a mistake~~. Emojis are plain unicode and just work 🚀.

## Lists

### Unordered (nested)

- First level item
  - Second level item
    - Third level item
- Another first level item
- Task list items (GitHub-Flavored Markdown):
  - [x] This task is done
  - [ ] This task is not done yet

### Ordered

1. Step one: write the post
2. Step two: run `bundle exec jekyll build`
3. Step three: click the title from the homepage
   1. Nested ordered item
   2. Another nested item

## Blockquote

> Blogging is just gradient descent on your own understanding: each post is a forward pass that forces you to expose the gaps.
>
> — the author of this demo post

## Code Blocks

```python
def greet(name: str) -> str:
    # Python syntax highlighting test
    message = f"Hello, {name}!"
    return message

if __name__ == "__main__":
    print(greet("world"))
```

```bash
# shell block, second language check
jekyll build && echo "done"
```

## Table

| Feature | Status | Confidence |
|:---|:---:|---:|
| Headings | works | 100% |
| Lists | works | 95% |
| Tables | under test | 87% |

## Image

![Teaser of the demo post](/assets/blogs/2026-09-05-demo-post/teaser.svg)

*The teaser above doubles as the homepage entry thumbnail — two birds, one SVG.*

## Raw HTML (Inline)

Some inline raw HTML passes through fine: <mark>highlighted text</mark>, H<sub>2</sub>O, x<sup>2</sup>, and a <span style="color:#e74d3c">colored span</span>. Block-level raw HTML (like `<details>`) is a different story — see the notes at the bottom.

## The End

That is the whole kitchen sink — a horizontal rule follows, then we are done.

---

Thanks for reading. If you spot anything mis-rendered, the fix lives in one of three places: the markdown above, `_layouts/post.html`, or the blog section inside `_includes/publications.md`.

## Rendering Notes

Verified in a local build of this site (GitHub Pages kramdown pipeline):

- ✅ Headings, bold/italic, inline code, nested lists, blockquotes, tables (column alignment works), fenced code blocks with syntax highlighting, images, inline raw HTML, strikethrough (`~~`), and task lists (`- [ ]`).
- ❌ Footnotes (`[^1]`) are **not** rendered — use regular links instead.
- ❌ Bare URLs are **not** auto-linked — wrap them in angle brackets: `<https://github.com/drdh>`.
- ⚠️ Block-level raw HTML (e.g. `<details>`) makes kramdown stop parsing every markdown that follows it — keep such HTML at the very end of a post, or avoid it.
