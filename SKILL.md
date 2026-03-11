---
name: deal-finder
description: find underpriced pokemon card deals for a whatnot business and rank them by first-show usefulness. use when the user wants help searching ebay, estatesales.net, and shopgoodwill for pokemon singles, binders, lots, collections, japanese cards, and bulk with sort potential. use when the user wants telegram-ready deal alerts, google sheet logging fields, bankroll-aware buy decisions, or show-building recommendations for a $500 starting budget.
---

# deal-finder

## Overview

Find Pokémon card deals for a Whatnot-first resale business. Search eBay, EstateSales.net, and ShopGoodwill, filter weak leads, estimate resale potential, and rank each find by how useful it is for building a first Whatnot show from a $500 bankroll.

Use a strict sourcing posture:
- prioritize Pokémon only
- prefer binders, small collections, underpriced singles lots, bulk with sort potential, Japanese Pokémon, vintage lots, and recognizable modern hits
- avoid sealed-above-msrp flips and vague buys with no resale path
- prefer deals that help build a first show with 50 to 80 sellable items/lots

## Workflow

Follow this sequence:

1. Search the sources in this priority order:
   - eBay
   - EstateSales.net
   - ShopGoodwill
2. Extract the listing facts:
   - source
   - title
   - ask price
   - shipping if visible
   - condition clues
   - lot size clues
   - link
   - why it looks interesting
3. Filter out weak listings before deeper analysis.
4. Estimate gross value, net profit, confidence, and flip path.
5. Score the listing for first-show usefulness.
6. Return a Telegram-ready alert and Google Sheet logging row.

Do not auto-buy, auto-message sellers, or place bids.

## Search rules

### Prioritize these listing patterns

Prioritize listings with words or evidence like:
- pokemon lot
- binder
- collection
- bulk
- old cards
- trading cards
- japanese pokemon
- holo lot
- reverse holo lot
- childhood collection
- ex lot
- vintage pokemon
- mixed pokemon cards

### Deprioritize or skip these patterns

Deprioritize or skip listings that are:
- sealed product priced above msrp for a quick flip
- obvious repacks or mystery products
- random junk lots with no visible signal
- single low-value cards with no bundle logic
- overhyped modern singles at full retail
- listings where fees and shipping obviously kill the margin

## Bankroll and show-plan rules

Work from this operating plan:
- starting bankroll: $500
- first-show target: 50 to 80 sellable items or lots
- preferred show mix:
  - 30 to 45 lower-ticket items
  - 15 to 25 mid-tier items
  - 5 to 10 headline items
- first-show sell target: 20 to 35 items

Prefer deals that help fill one of these three buckets:
1. filler velocity items
2. mid-tier anchors
3. headline cards or standout lots

When two deals are similarly profitable, prefer the one that improves show balance.

## Deal thresholds

Use these default thresholds unless the user overrides them:
- projected net profit target: $40 to $60 minimum
- confidence target: 3 out of 5 minimum
- favor ask prices that fit a $500 bankroll
- avoid concentrating too much bankroll in one listing unless the upside is unusually strong and clearly explained

## Evaluation method

For each candidate, answer these in order:
1. What is it likely to be?
2. Is the ask price attractive after shipping?
3. What is the most realistic resale path?
4. Is it better as singles, mini lots, themed lots, or hold inventory?
5. What is the estimated gross value range?
6. What is the estimated net profit range after platform fees and likely shipping/packaging?
7. How useful is it for building the first show?

If data is weak, reduce confidence. Do not fake precision.

## First-show usefulness scoring

Label each deal with one of these:
- `high show usefulness`: directly helps fill a needed bucket for the first 50 to 80 item show and is easy to run live
- `medium show usefulness`: profitable, but not ideal for the first show or needs sorting/work
- `low show usefulness`: maybe profitable, but weak for show-building or too awkward for early streams

Prefer live-friendly inventory:
- recognizable cards
- easy-to-explain lots
- clean mini bundles
- items buyers can understand quickly on stream

## Output format

Always return each deal in this exact structure:

Verdict: Buy Now / Review / Ignore  
Source:  
Title:  
Ask Price:  
Shipping:  
Estimated Gross Value:  
Estimated Net Profit:  
Confidence: 1 to 5  
Best Flip Path:  
Show Usefulness: High / Medium / Low  
Why It Fits the $500 Show Plan:  
Top Risks:  
Next Move:  
Link:  

After listing the deal analysis, provide this Google Sheet row format:

Sheet Row:
Date Found | Source | Title | Ask Price | Shipping | Gross Low | Gross High | Net Low | Net High | Confidence | Flip Path | Show Usefulness | Verdict | Link | Notes

## Telegram alert format

When sending or drafting alerts, use this short format:

🔴 DEAL FOUND  
Source: [source]  
Title: [short title]  
Ask: [price]  
Net: [range]  
Confidence: [score]  
Show Usefulness: [high/medium/low]  
Why: [1 short sentence]  
Link: [url]

Only use the red alert format for deals that clear the threshold. Use 🟡 for watch items.

## Operating notes

- Prefer sold-market logic over active-listing logic when possible.
- Treat weak photos, vague titles, and missing condition details as confidence penalties, not hidden upside by default.
- Prefer inventory that can be broken into multiple sellable units.
- Favor listings that create flexibility for the first three Whatnot shows, not just one flip.
- If Google Sheets logging is requested but not configured, still return the exact Sheet Row text so the user can paste it manually.
- If a source blocks automation or requires login, explain the limitation clearly and continue with accessible sources.

## Example decisions

### Example 1
A 150-card binder with visible modern hits, listed cheaply, with enough cards to break into singles and mini lots:
- likely `buy now`
- likely `high show usefulness`

### Example 2
A single modern card at near-market price with shipping that kills the spread:
- likely `ignore`
- likely `low show usefulness`

### Example 3
A mixed Japanese Pokémon lot with identifiable hits but some uncertainty:
- likely `review`
- likely `medium to high show usefulness` depending on ask and photos
