# סוחר הים — Claude Code Skill

> AI שיכול לשחק משחק DOS עברי משנת 1989

A Claude Code skill that enables Claude to play the classic 1989 Hebrew DOS trading game **סוחר הים (Socher Hayam / Sea Merchant)** through a browser-based DOSBox emulator — autonomously and profitably.

## What is this?

סוחר הים is a Hebrew DOS game from 1989. You trade goods (copper, olives, wheat) between Israel, Turkey, and Egypt on a ship, maximizing profit over 7 days while avoiding pirates.

The game runs today in the browser via DOSBox at [old-games.org](https://www.old-games.org/onlineGame/socher1). No mouse, no modern UI — just keyboard navigation inside a Canvas element.

## The Skill

This Claude Code skill "patches" Claude's missing spatial intelligence for DOS-style UIs:

- **RED highlight** = currently selected item (act on it)
- **Arrow keys** navigate menus, **Enter** confirms
- **Blue box** on map = selected destination city
- Full buy/sell/travel workflow automation
- Pirate encounter handling, guard ship management
- Arbitrage strategy: Israel ↔ Turkey ↔ Egypt

## Usage

```bash
/socher-hayam
```

Claude will:
1. Open browser, navigate to DOSBox game
2. Click game canvas to focus keyboard input
3. Start GIF recording
4. Play the full 7-day game with trading strategy
5. Export gameplay GIF at the end

## The "Skills as Patches" Concept

AI agents fail at non-standard UIs because they lack context-specific "common sense." Skills fill that gap — like OS patches. Give Claude a SKILL.md that explains the UI rules, and it transforms from clueless to capable.

This pattern works for any legacy system: old CRMs, insurance websites, Excel macros, DOS games.

## Skill Location

```
~/.claude/skills/socher-hayam/SKILL.md
```

## Website

[socher-hayam-skill GitHub Pages](https://aviz85.github.io/socher-hayam-skill)

---

Built with Claude Code · Powered by DOSBox & Anthropic
