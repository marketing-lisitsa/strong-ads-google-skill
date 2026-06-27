# Strong Ads for Google Ads — a Claude Code skill

> 🔵 **For Google Ads only** (Search / RSA + Performance Max). Not for Meta, Facebook, or Instagram ads.

Write **high-converting Google Ads copy** that sounds like a sharp human marketer wrote it — not AI.

Unlike a quick "write me some headlines" prompt, this skill **does the homework first**:

- 🧠 **Deep business analysis** — who really buys, at what price, what they fear, and what they buy *instead*. It analyzes the *business*, not just the *product*.
- 🔎 **Automatic competitor research** — finds your real competitors, reads their sites and live Google ads, and spots the gaps you can own.
- 💔 **Real buyer pain research** — pulls the actual frustrations of *your* buyer from forums and reviews (not generic category complaints).
- ✍️ **30 headlines in 6 angles** + long headlines + descriptions, all within **exact Google Ads character limits**.
- 🚫 **No AI slop** — bans the tells (Unlock, Elevate, Seamless, Discover…) and writes specific, human copy.

It outputs everything in a clean table, copy-paste ready for Google Ads Editor.

---

## What you get

Run it on any business and you get:

| Output | Detail |
|--------|--------|
| **Business Brief** | Who buys, why, price, fear, trigger |
| **Competitor table** | Their claims + the gaps you can attack |
| **Pain table** | Your buyer's real frustrations → your answer |
| **30 headlines** | 6 blocks × 5, each ≤ 30 chars, with angles |
| **5 long headlines** | ≤ 90 chars (Performance Max) |
| **Descriptions** | RSA (4) + PMax (5), ≤ 90 chars |

---

## The 6 headline blocks

The 30 headlines come grouped into 6 blocks of 5, so each one earns its spot instead of repeating the same idea. Every block is written from your Business Brief, competitor gaps, and real buyer pains — never generic filler.

| # | Block | What it covers | Example |
|---|-------|----------------|---------|
| **1** | **General / business & product** | Broad lines about the business and what it sells | `Small-Batch Coffee Roaster` |
| **2** | **Product features** | Concrete specs, materials, sizes, the actual product | `Roasted Fresh, Shipped in 24h` |
| **3** | **Value to the buyer** | What the buyer gets out of it | `Coffee Worth Waking Up For` |
| **4** | **Pain → solution** | A real buyer frustration and how you fix it | `Stale Beans? Not Anymore` |
| **5** | **Better than competitors** | What rivals leave unsaid, pulled from their live ads | `Roasted to Order, Never Stored` |
| **6** | **Call to action** | Real CTAs that fit the business, not generic AI ones | `Start Your Subscription` |

Then on top of the 30 headlines you get **5 long headlines** (≤ 90 chars, for Performance Max) and **descriptions** (4 for RSA, up to 5 for PMax) — each built to pair with the headlines and pass Google's character limits.

---

## Install

This is a [Claude Code](https://claude.com/claude-code) skill. Skills are just folders in `~/.claude/skills/`. Pick either way:

### Option A — one-line install (recommended)

```bash
git clone https://github.com/marketing-lisitsa/strong-ads-google-skill.git /tmp/strong-ads-google-skill \
  && mkdir -p ~/.claude/skills \
  && cp -r /tmp/strong-ads-google-skill/skills/strong-ads ~/.claude/skills/ \
  && rm -rf /tmp/strong-ads-google-skill \
  && echo "✅ Installed. Restart Claude Code and type: strong ads"
```

### Option B — manual

1. Download or clone this repo.
2. Copy the folder `skills/strong-ads` into your `~/.claude/skills/` directory.
3. Your final path should be: `~/.claude/skills/strong-ads/SKILL.md`
4. Restart Claude Code.

> **Windows:** the skills folder is at `C:\Users\<you>\.claude\skills\`. Copy `skills\strong-ads` there.

---

## Use

In Claude Code, type either:

```
strong ads
```

or

```
/strong-ads
```

Then give it your website URL. The skill will:

1. Read your site and write a **Business Brief**.
2. Find and analyze your **competitors** (shows them to you to confirm).
3. Research your buyer's **real pains**.
4. Write **30 headlines + long headlines + descriptions** in a table.

That's it. Paste the output into Google Ads Editor.

### Tip

Give it real proof points (years in business, ratings, number sold, any offer) and it will weave them into stronger, fact-based headlines. It never invents claims or numbers.

---

## What's inside

```
strong-ads/
├── SKILL.md              # the skill logic (analysis → competitors → pains → copy)
└── references/
    └── no-ai-slop.md     # banned AI words + human replacements
```

The skill is **self-contained** — it carries its own anti-AI rules, character limits, and structure. No other skills or API keys required (it uses Claude Code's built-in web search; Perplexity is used if available for deeper research).

---

## Requirements

- [Claude Code](https://claude.com/claude-code)
- Web search available in your Claude Code setup (used for competitor and pain research)

---

## License

[MIT](LICENSE) — free to use, copy, modify, and share. Built for marketers who are tired of robotic ad copy.
