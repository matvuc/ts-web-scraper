# Web Crawler

A CLI tool that crawls a website and reports which internal pages are linked to most frequently — useful for understanding site structure and SEO link equity.

## How it works

1. Starts at a given URL and fetches the HTML.
2. Extracts all `<a>` links, resolves relative URLs, and filters to links that stay on the same hostname.
3. Crawls discovered pages concurrently (up to 5 in parallel by default), deduplicating visits.
4. Prints a report sorted by internal link count — the more a page is linked to, the higher it appears.

## Usage

```bash
npm start <url>
```

**Example:**

```bash
npm start <link>
```

## Requirements

- Node.js 22.x ([.nvmrc](.nvmrc) included)

## Setup

```bash
npm install
```

## Running tests

```bash
npm test
```

## Tech

- **TypeScript** — typed throughout
- **jsdom** — parses HTML to extract links
- **p-limit** — caps concurrent fetches to avoid overwhelming the target server
- **vitest** — unit tests for URL normalization, link extraction, and report sorting
