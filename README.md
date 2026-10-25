# Claude Prompt Index

An interactive, single-page index of **80 AI prompts** extracted from
[@claudepromptsadvantage](https://www.threads.com/@claudepromptsadvantage) on Threads.

**Live:** https://logansolaman.github.io/claude-prompt-index/

## Features

- **Category filters** — 8 categories (Web & Design, Business & Clients, Career & Jobs, YouTube, Health & Fitness, Freelance Income, Instagram & Social, Brand & Positioning)
- **Tag filters** — combine with categories (`#beginner`, `#money`, `#30-day`, `#website-build`, `#audit`, `#plan`)
- **Live search** across prompt text, titles, categories and tags
- **Sort** by category, A→Z, newest, or longest
- **Copy to clipboard** on every card, plus source link back to the original post
- **Dark / light theme**, remembered per browser
- `⌘K`-style shortcut: press `/` to focus search, `Esc` to clear
- Zero dependencies, zero tracking, no build step — one HTML file

## Files

| File | Purpose |
|---|---|
| `index.html` | The entire site. Data is inlined as JSON — no fetch, works offline and from `file://`. |
| `prompts.json` | The dataset on its own, if you want to consume it programmatically. |

## Dataset shape

```json
{
  "meta": { "source": "…", "collected": "2026-10-22", "posts_crawled": 183, "total": 80, "categories": {…} },
  "prompts": [
    {
      "id": 1,
      "title": "Zero To $1,000 Service",
      "prompt": "Act as a beginner resume business coach…",
      "category": "Career & Jobs",
      "tags": ["money", "beginner", "30-day", "plan"],
      "posted": "22m",
      "url": "https://www.threads.com/@claudepromptsadvantage/post/DezeDShEw9G"
    }
  ]
}
```

## Notes

- 183 individual posts were crawled; a Threads "thread" spans several posts (hook → prompt → call-to-action), which is why the profile shows ~109 threads but yields 80 distinct prompts.
- Prompts are reproduced verbatim from the public posts. Credit and source links belong to the original author.
- Category assignment is keyword-based, so a few prompts arguably fit more than one bucket.

## Rebuilding

`index.html` is generated. To regenerate after editing `prompts.json`, render the inline data block and the
markup from the dataset — the shipped file is the single source of truth for the UI itself.
