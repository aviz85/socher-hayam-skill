---
name: socher-hayam
description: "Play סוחר הים (Sea Merchant) - classic Hebrew DOS trading game in browser via DOSBox emulator. Use when user says 'play socher hayam', 'שחק סוחר הים', or wants to play the sea merchant game."
user_invocable: true
---

# סוחר הים (Socher Hayam) — Sea Merchant

Play the classic 1980s Hebrew DOS trading game through a web-based DOSBox emulator.

**URL:** https://www.old-games.org/onlineGame/socher1

## Setup

1. Load browser tools: `select:mcp__claude-in-chrome__tabs_context_mcp,mcp__claude-in-chrome__computer,mcp__claude-in-chrome__gif_creator`
2. Get tab context with `tabs_context_mcp`
3. Create new tab with `tabs_create_mcp`
4. Navigate to `https://www.old-games.org/onlineGame/socher1`
5. Wait 3–5 seconds for DOSBox to load
6. Start GIF recording immediately with `gif_creator` (action: start_recording)
7. Click the game canvas to focus keyboard input — click center of the DOSBox window (~760, 490)

## Critical UI Rules

### Color = Selection State
- **RED highlight** = currently SELECTED item (will be acted on)
- **GREEN** = not selected
- Navigate until the item you want turns RED, then press Enter

### Keyboard Controls
- **Up/Down arrows** — navigate menus and item lists
- **Enter** — confirm selection / advance
- **Escape** — go back / cancel
- **Number keys then Enter** — fill quantity/amount input fields
- **NO mouse** — everything is keyboard only

### Input Fields
When a prompt appears asking "how many?" or "כמה?":
- Type the number using number keys (e.g., press `1` then `2` for 12)
- Press Enter to confirm
- Do NOT press Enter before typing the number

### Hebrew Yes/No Prompts (כן/לא)
When the game asks a yes/no question like "האם אתה מוכן להסתכן? כן/לא":
- **Press `f` for כן (Yes)** — `f` maps to the Hebrew letter כ (Kaf)
- **Press `k` for לא (No)** — `k` maps to the Hebrew letter ל (Lamed)
- Then press Enter to confirm
- This is the Israeli Hebrew keyboard layout used by DOSBox

**Full Israeli Hebrew keyboard mapping (key → Hebrew letter):**
| Key | Hebrew | Key | Hebrew |
|-----|--------|-----|--------|
| f | כ | k | ל |
| t | א | b | נ |
| v | ה | n | מ |
| a | ש | s | ד |
| e | ק | r | ר |

### Map Navigation
- Arrow keys move between destination cities
- Selected destination shows a **blue box** outline
- Press Enter to confirm travel destination
- If you accidentally go past a destination, press the opposite arrow to go back

## Game Structure

**Goal:** Make the most money by Day 7 through arbitrage trading between cities.

**Status Panel (top-right):**
- Current city (תורכיה/ישראל/מצרים)
- Day (יום) + Time (שעה)
- Cargo: נחושת (Copper), זיתים (Olives), חיטה (Wheat)
- Cash: כסף מזומון

**Price Board (bottom):** Shows buy/sell prices in all 3 cities. Use this to find arbitrage opportunities.

**Ship capacity:** 14 units total across all goods.

## Main Menu Options

```
1. לקנות    — Buy
2. למכור    — Sell
3. לנסוע    — Travel
4. לגשת לבנק — Bank
5. לנוח עד למחרת — Rest until tomorrow
```

Navigate with Up/Down until desired option turns RED, then press Enter.

## Cities & Goods

| City | Hebrew | Notes |
|------|--------|-------|
| Turkey | תורכיה | Usually cheap wheat & copper |
| Israel | ישראל | Usually expensive copper & wheat |
| Egypt | מצרים | Usually expensive copper |

| Good | Hebrew | Notes |
|------|--------|-------|
| Copper | נחושת | High value, high profit |
| Olives | זיתים | Medium value |
| Wheat | חיטה | Cheap to buy, good margins |

## Trading Workflow

### Buying
1. Main menu → navigate to option 1 (לקנות) → Enter
2. Buy screen shows 3 goods: נחושת (top-right), זיתים (top-left), חיטה (bottom-center)
3. Navigate Up/Down until desired good turns RED → Enter
4. Input field appears: "כמה אתה רוצה?" — type quantity → Enter
5. Returns to main menu with updated inventory

### Selling
1. Main menu → navigate to option 2 (למכור) → Enter
2. Same item selection as buying, select item turning RED → Enter
3. Input field: "כמה אתה רוצה למכור?" — type quantity → Enter
4. Returns to main menu with updated cash

### Traveling
1. Main menu → navigate to option 3 (לנסוע) → Enter
2. Map appears with ship icon at current city
3. Press Down/Up to navigate between destinations
4. Target city gets a **blue box** outline when selected
5. Press Enter to confirm
6. Prompt: "כמה ספינות משמר?" (guard ships) — type 1 or 2, press Enter (200 shekels each)
7. Sailing animation plays — wait for arrival (can take 5–15 seconds)
8. If "הספינה נעצרה" appears — press Enter to continue
9. If pirate attack "שודדי ים !!" — press 1 (attack), 2 (flee), or 3 (compromise), then Enter

## Events During Travel

| Hebrew | Meaning | Action |
|--------|---------|--------|
| שודדי ים !! | Pirates! | Choose 1=attack, 2=flee, 3=ransom |
| הספינה נעצרה | Ship stopped | Press Enter to continue |
| הפיראטים התגברו | Pirates won | Press Enter (may lose cash) |
| שביתת פועלים | Workers strike (port closed) | Port unavailable, try again next day |

## Random Events (unavoidable)
- **Theft overnight** — random cash stolen while in port
- **Crew crisis** — crew threatens to leave; offer bribe or accept new crew
- **Pirates** — attack mid-voyage; guard ships help defend

## Strategies

### Day 1 (Start in Israel — ישראל)
Best opening move:
- Check price board bottom: buy olives (זיתים) or wheat in Israel if cheap
- OR travel directly to Turkey if Israel prices are high
- Buy goods that Turkey/Egypt sell at higher prices
- Fill ship to capacity (14 units)

### Core Arbitrage Loop
Best known routes:
1. **Israel → Turkey**: Buy olives cheap in Israel (~350), sell in Turkey (~650) = ~85% profit
2. **Turkey → Israel**: Buy wheat cheap in Turkey (~35), sell in Israel (~70) = 100% profit
3. **Turkey → Egypt**: Copper in Turkey (~2800), sell Egypt (~3300) = ~18% profit

### Maximize Each Trade
- Always fill ship to 14 units
- Check all 3 city prices before deciding destination
- Calculate: (sell price - buy price) × quantity = profit
- Prioritize highest ROI per day of travel

### Guard Ships
- 200 shekels each
- 1 guard ship = basic protection
- 2 guard ships = stronger defense
- 0 guard ships = pirates can steal freely
- Worth buying when carrying high-value cargo (copper)

### Bank (לגשת לבנק)
- Deposit cash to protect from theft
- Withdraw when needed for trading
- Useful if carrying large amounts of cash

### Day Management
- You have 7 days total
- Each voyage takes ~half a day
- Rest (option 5) advances to next morning
- Plan: aim for 2–3 complete trade round-trips

## Starting the Game

When the game loads, press Enter through any intro screens. The game starts automatically in Israel (ישראל) on Day 1 (יום ראשון / Sunday) at 8:00.

## GIF Recording

- Start recording BEFORE navigating to the URL
- Take screenshot immediately after starting to capture first frame
- Take screenshot before stopping to capture final frame
- Export when game ends: `gif_creator` (action: export, download: true, filename: "socher-hayam-gameplay.gif")

## Gotchas

- **Click game canvas before any keyboard input** — otherwise keys go to browser, not game
- **If keys don't register** — click the game area again to refocus
- **Red = selected** — never press Enter on a green item
- **Wait for animations** — don't press keys during sailing/event animations
- **Israel port strike** — if port closed, rest until next day and retry
- **Don't over-navigate on map** — go Down once for Egypt, Up once from Egypt for Israel
- **After buying, Escape returns to main menu** — use Escape if stuck in buy/sell screen
- **Extension disconnects** — call `tabs_context_mcp` to reconnect, then continue
- **כן/לא prompts** — press `f` (= כ) for Yes, `k` (= ל) for No, then Enter
- **Night sailing prompt** — say כן (`f` + Enter) to sail immediately; saying לא waits until morning (safer)
