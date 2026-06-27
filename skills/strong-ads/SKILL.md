---
name: strong-ads
description: Generate high-converting Google Ads copy in English (RSA + Performance Max). Starts with a deep business analysis (who really buys, at what price, what they fear), then finds and analyzes competitors (their sites + live Google ads), researches the real buyer's pains, and writes headlines, long headlines, and descriptions with no AI slop, exact character limits, and no promises beyond the business's real scope. Trigger when the user types "strong ads", "/strong-ads", or asks to write Google Ads headlines, long headlines, or descriptions.
metadata:
  trigger: User types "strong ads" / "/strong-ads", or asks for Google Ads headlines/descriptions
  author: marketing@techvill.ca
---

# Strong Ads

Write Google Ads copy that converts: headlines, long headlines, and descriptions for **Search (RSA)** and **Performance Max** campaigns. Output is in **English**. Copy must read like a sharp human marketer wrote it — never like AI.

This skill is self-contained. It carries its own anti-AI rules (from stop-slop), its own character limits, and its own headline structure. Do not depend on other skills.

## Step 0 — Deep business analysis (DO THIS FIRST — it is the difference between dumb and smart ads)

The most common failure of an AI writing ads: it analyzes the **product** instead of the **business**. It takes the noun ("software", "yoga mats", "coffee"), googles "[noun] problems", and writes ads against generic category pain. That produces flat, wrong ads.

A smart analyst does the opposite: before any keyword or competitor search, **reconstruct the actual buyer and the actual transaction.** Fetch the site, then answer ALL of these in writing. Do not skip any. If the answer isn't on the site, reason it out from price, product, and market — and say it's an inference.

1. **Price and what the price means.** What does it cost? Is this a $20 impulse buy or a $5,000 considered decision? Price reframes everything: a $5,000 product is not bought the way a $50 one is.
2. **Who actually pays — a portrait, not a demographic.** Not "homeowners" or "businesses." A specific person in a specific situation. For a $5,000 hand-built product that is a serious enthusiast or a professional buying for a project — NOT a casual one-time shopper. Ask: who has both the money and the reason to buy THIS, at THIS price?
3. **Emotional or functional?** Are they fixing a problem (functional) or buying a dream / status / beauty / identity (emotional)? High-price, one-of-a-kind, aesthetic, or heritage products are emotional. This decides the whole tone.
4. **What do they buy INSTEAD?** The real alternative is rarely "a competitor's version of the same thing." For a premium handcrafted product it's "buy a cheap mass-made version" vs "invest in a real handcrafted one." Name the true alternative — the ads must win that comparison.
5. **The deep fear — specific to THIS buyer at THIS price.** Not category pain. The fear at this price is "is it genuine? is it right for my exact need? will it arrive in perfect condition?" — NOT a trivial how-to worry. Find the fear of the person from #2, spending the money from #1.
6. **The buying trigger.** What happened in their life that makes them search now? (Started a big project, furnishing a new space, preparing for an event.) The trigger is the moment the ad must meet.
7. **What the product really is to them.** A functional object, or an art piece / heirloom / statement / proof of taste? A premium handcrafted item is a centerpiece and a story, not just a commodity.

Write a short **Business Brief** from these 7 answers and show it to the user before continuing. Everything downstream — keywords, competitors, pains, headlines — must serve THIS brief. If the brief is wrong, the ads are wrong.

**The test:** if your analysis would read identically for a cheap mass-market version of the product, you analyzed the product, not the business. Go deeper.

## Step 1 — Gather remaining context

After the Business Brief, fill gaps. Ask the user only for what you cannot find or infer:

1. **Website URL** — required. Fetch it and pull real facts (offers, proof, product details).
2. **What the business actually does / its limits** — the real scope. (e.g. "we customize" can mean adjust-down only, not scale-up; "we coordinate setup" vs "we just ship.") Confirm scope so ads never promise more than the business delivers.
3. **Target keywords** — infer from the site + the Business Brief; confirm with the user.
4. **Offers / proof** — discounts, guarantees, years in business, ratings, certifications. Pull what you can; ask only for what's missing.
5. **Campaign type** — RSA, Performance Max, or both (default: both).
6. **Competitors** — DO NOT ask the user. Find them yourself (Step 2).

Always fetch the user's site before writing. Never invent claims, numbers, or guarantees. Never promise a capability the business does not have.

## Step 2 — Find and analyze competitors (automatic)

The skill finds competitors itself. The user should not have to supply them.

### 2a. Discover competitors

1. From the user's site + target keywords, search for real competitors:
   - `WebSearch` / `perplexity_search`: `[main keyword] + [city/region if local]`, `best [product] [region]`, `[product] alternatives`, `[brand] competitors`.
   - Pick the **top 3-5 direct competitors** (same product, same audience, same market). Skip aggregators/marketplaces unless they are the real competition.
2. **Show the list to the user for confirmation** before deep analysis:
   `Found these competitors: [A], [B], [C]. Analyzing these — tell me if you'd swap any.`
   Proceed after they confirm or stay silent; swap any they reject.

### 2b. Analyze each competitor (two sources)

For each confirmed competitor, pull from BOTH:

1. **Their full website** — read the homepage AND key pages (pricing, product, about, shipping/returns). Extract every stated strength and claim: price, speed, warranty, support hours, materials, certifications, social proof.
2. **Their live Google ads** — search the brand name, check the **Google Ads Transparency Center** (`adstransparency.google.com`) and brand + "reviews"/"vs" searches to see the actual ad headlines they run.

### 2c. Find the gaps (where we win)

For each competitor, list:
- **What they say** (site + ads).
- **What they DON'T say** — strong selling points true for OUR business that are absent from their messaging.

Those gaps feed the "better than competitors" headline block. Rule: highlight what is true for us AND missing from their messaging.

Summarize before writing copy:

| Competitor | Stated strengths (site + ads) | What they DON'T say (our angle) |
|-----------|-------------------------------|-----------------------------------|

## Step 2.5 — Customer pain research (for the Pain → Solution block)

Find the real tension of the **buyer from the Business Brief (Step 0)** — NOT generic pain of the product category.

**Critical rule:** research the pains of the PERSON, at THEIR price point, in THEIR situation. The pain of someone buying an $80 commodity ("how do I use it") is NOT the pain of someone buying a $5,000 premium item ("is it genuine, is it right for my need, will it arrive perfect"). Searching "[product] problems" gives you the wrong, low-value buyer's pain. Search for the Step 0 buyer instead.

1. Build queries around the BUYER and the STAKES, not just the product:
   - `[buyer type] [product] [what they fear]` — e.g. `[product] authentic worried buyers reddit`, `[professional] sourcing [product] problem`.
   - Forums where THAT buyer talks: for enthusiasts → niche subreddits and hobby forums; for pros → industry communities; for B2B → industry subreddits, G2.
   - Reviews/complaints about competitors serving the same buyer.
   - Use `perplexity_research` for a deep multi-source sweep — tell it the buyer portrait, price, and product so it finds the right pains.
2. **Group pains by type, but keep them specific to this buyer.** Buckets vary by business. For a high-value premium product they are usually: **authenticity** (is it real?), **suitability** (is it right for my exact need?), **scarcity** (will I find the right one / will it sell first?), **condition vs photos** (will it look as good in person?), **safe arrival** (fragile, expensive, will it ship intact?), **trust/communication** (will the seller actually respond?). For a SaaS or service they differ. Derive the buckets from the Brief, do not reuse a fixed list.
3. Map each pain bucket to OUR solution, within the business's real scope (Step 1). Never promise a fix the business can't deliver (e.g. don't claim "fits any size" if you can only adjust down, not scale up). Write the Pain → Solution headlines only from buckets where we genuinely win.

Summarize:

| Pain bucket | What customers say | Our solution (the headline angle) |
|-------------|--------------------|-----------------------------------|

## Step 3 — Character limits (hard rules — never exceed)

Count every character including spaces. If a line is over the limit, rewrite it shorter — do not deliver anything over limit.

**Search — Responsive Search Ads (RSA):**
- Headlines: **30 characters** max — provide **15**
- Descriptions: **90 characters** max — provide **4**
- (Optional) Display path: 15 characters each, 2 fields

**Performance Max:**
- Short headlines: **30 characters** max — provide **5**
- Long headlines: **90 characters** max — provide **5**
- Descriptions: **90 characters** max — provide up to **5** (one short description: 60 max)
- Long description (where applicable): **90 characters**

After every line, show the character count in brackets, e.g. `Fast Same-Day Delivery [22]`. Double-check counts — being 1 over gets the asset rejected.

## Step 4 — Headline structure (30 headlines, 6 blocks of 5)

Always produce these six blocks, 5 headlines each. Each headline ≤ 30 characters.

1. **General / business & product** (5) — broad descriptive lines about the business and what it offers.
2. **Product characteristics / features** (5) — concrete specs, materials, sizes, specifics of the product.
3. **Value & values** (5) — the value the customer gets and what sets us apart on principle/quality.
4. **Pain → solution** (5) — style: "Problem? We fix it." Use the real pain buckets from Step 2.5, each mapped to our solution.
5. **Better than competitors** (5) — surface what competitors leave unsaid (from Step 2 gaps).
6. **CTA** (5) — real calls to action relevant to the business: Order Now, Book Today, Call Us, Get a Quote, Shop the Sale, Start Free. NOT generic AI CTAs.

Then add:
- **Long headlines** (Performance Max): 5 lines ≤ 90 chars, expanding the strongest angles.
- **Descriptions**: RSA → 4 lines ≤ 90 chars. PMax → up to 5 lines ≤ 90 chars (+ one ≤ 60). Each description = benefit + proof/specific + CTA where it fits.

## Step 4.5 — Make headlines interesting (angles + structure)

The 6 blocks decide WHAT each headline is about. This step decides HOW it hooks. Without it, headlines come out flat and descriptive. Apply both layers to every block.

### Layer 1 — Give each headline an angle (the hook)

Don't write a flat description. Pick an angle that gives the reader a reason to click. Rotate through these so the 30 headlines don't all sound the same:

| Angle | What it does | Example (coffee brand) |
|-------|--------------|------------------------|
| **Curiosity** | Opens a loop the reader wants closed | `Coffee Roasted This Morning` |
| **Contrarian** | Challenges a common belief | `Store Coffee Is Already Stale` |
| **Identity** | Names the buyer ("built for X") | `For Serious Coffee Drinkers` |
| **Social proof** | Numbers, who else bought | `12,000 Cups Shipped Monthly` |
| **Specificity** | A concrete number/spec beats vague | `Roasted, Shipped in 24 Hours` |
| **Outcome** | The end state the buyer wants | `Mornings Worth Waking Up For` |
| **Pain/tension** | Names the frustration first | `Tired of Stale Supermarket Beans?` |
| **Sensory/emotional** | Evokes feel, look, taste | `Rich, Slow-Roasted Aroma` |

Rule: at least 3-4 different angles should appear across the 30 headlines. A block of 5 should not be 5 flat descriptions.

### Layer 2 — Vary the sentence structure

Even good angles get monotonous if every line is a noun phrase. Mix these shapes within each block:

- **Statement:** `Roasted Fresh to Order`
- **Question:** `Tired of Stale Coffee?`
- **Command:** `Start Your Subscription`
- **Number-led:** `Shipped Within 24 Hours`
- **Fragment with tension:** `Stale Beans? Not Anymore.`

Rule: in any block of 5, use at least 2 different structures. Never 5 identical noun phrases in a row.

### Quick test for "is this flat?"

If a headline could appear on a competitor's site word-for-word, it's flat. Add an angle, a number, or a hook. `Fresh Roasted Coffee` is flat. `Coffee Roasted This Morning` has specificity. `Roasted Today, Delivered Tomorrow` has specificity + outcome.

## Step 5 — No AI slop (apply to every line)

Ad copy has its own AI tells. Ban these outright. See [references/no-ai-slop.md](references/no-ai-slop.md) for the full list and replacements.

**Banned words/phrases in ads (English):**
Unlock, Unleash, Elevate, Discover, Seamless, Seamlessly, Effortless, Effortlessly, Empower, Revolutionize, Game-changer, Cutting-edge, Transform your, Take it to the next level, Look no further, Say goodbye to, In today's world, Dive in, Supercharge, Level up, Best-in-class, World-class, State-of-the-art, Premium quality (as filler), Experience the difference, Your one-stop shop, We've got you covered, Tailored to your needs, Solutions that..., Embark on a journey.

**Also:**
- No adverbs (-ly), no hype filler, no em dashes.
- Be specific: name the thing, the number, the spec. "24/7 Support" beats "Great Support."
- Active voice, real verbs.
- Vary the lines — don't make all 5 in a block the same shape.
- Use real numbers, offers, and proof ONLY if the user gave them. Never fabricate.

## Step 6 — Output format

1. Business Brief (Step 0) — the 7 answers, short.
2. Competitor analysis table (Step 2c).
3. Customer pain table (Step 2.5).
4. The 6 headline blocks (30 headlines), each line with `[char count]`.
5. Long headlines (5).
6. Descriptions (RSA: 4 / PMax: up to 5), each with `[char count]`.
7. A one-line note: which keywords were woven in, which competitor gaps the "better than" block used, and which pain buckets the "Pain → Solution" block used.

Keep the whole thing copy-paste ready into Google Ads Editor.

## Quick self-check before delivering

- Did you write a Business Brief (Step 0) BEFORE keywords/competitors? Did you analyze the business (who/why/price/fear), not just the product?
- Would your analysis read identically for a cheap version of the product? If yes, you went too shallow — redo Step 0.
- Are the pains the BUYER's pains (right person, right price), not generic category pains?
- Does any headline promise something outside the business's real scope (Step 1)? Cut it.
- Were competitors found and confirmed (not asked from the user)?
- Did each competitor get analyzed from BOTH their site and their live ads?
- Every line at or under its character limit? (Recount the longest ones.)
- Any banned AI word slipped in? Remove it.
- Any adverb or em dash? Remove it.
- All 6 blocks present, 5 each?
- Is each block flat? Apply Step 4.5: at least 3-4 angles across the 30, at least 2 sentence structures per block.
- Could any headline sit on a competitor's site word-for-word? If yes, add an angle/number/hook.
- Does the "better than competitors" block use real gaps from Step 2c, not guesses?
- Does the "Pain → Solution" block use real pain buckets from Step 2.5?
- Any invented claim/number? Cut it.
