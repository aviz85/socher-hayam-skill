# סוחר הים — Claude Code Skill

> AI שיכול לשחק משחק DOS עברי משנת 1989

A Claude Code skill that enables Claude to play the classic 1989 Hebrew DOS trading game **סוחר הים (Socher Hayam / Sea Merchant)** through a browser-based DOSBox emulator — autonomously and profitably.

## What is this?

סוחר הים is a Hebrew DOS game from 1989. You trade goods (copper, olives, wheat) between Israel, Turkey, and Egypt on a ship, maximizing profit over 7 days while avoiding pirates.

The game runs today in the browser via DOSBox at [old-games.org](https://www.old-games.org/onlineGame/socher1). No mouse, no modern UI — just keyboard navigation inside a Canvas element.

## Setup

### 1. Install Claude in Chrome Extension

This skill uses browser automation — Claude controls Chrome directly from the terminal.

1. Install the extension from the Chrome Web Store:
   **[Claude in Chrome](https://chromewebstore.google.com/detail/claude-in-chrome/bigdlbgbomaoamkiapnnjkcepfkjiifm)**

2. Sign in to [claude.ai](https://claude.ai) in Chrome (the extension connects automatically)

3. Launch Claude Code with the `--chrome` flag to enable browser tools:
   ```bash
   claude --chrome
   ```

### 2. Install the Skill

Paste this prompt into Claude Code — it will handle the rest:

```
I found a Claude Code skill I'd like to install: https://github.com/aviz85/socher-hayam-skill

Please consult the claude-code-guide agent to learn how skills work and how to install them,
then install this skill for me. The skill file is located at skill/SKILL.md in the repository
above. Create the folder ~/.claude/skills/socher-hayam/ if it doesn't exist, and place the
SKILL.md file there.
```

Or manually:
```bash
mkdir -p ~/.claude/skills/socher-hayam
curl -o ~/.claude/skills/socher-hayam/SKILL.md \
  https://raw.githubusercontent.com/aviz85/socher-hayam-skill/master/skill/SKILL.md
```

### 3. Restart Claude Code

> **Skills are only loaded at startup.** After installing, exit Claude Code and relaunch it.

```bash
# Always launch with --chrome for browser automation
claude --chrome
```

Before running the skill, verify:
- [ ] Claude in Chrome extension is installed
- [ ] Signed in to claude.ai in Chrome
- [ ] Extension icon is **active** (not greyed out) in the Chrome toolbar
- [ ] Skill file exists at `~/.claude/skills/socher-hayam/SKILL.md`
- [ ] Claude Code was restarted with `claude --chrome`

## Usage

Once installed, run with:
```bash
/socher-hayam
```

Claude will:
1. Open Chrome, navigate to the DOSBox game
2. Click the game canvas to focus keyboard input
3. Start GIF recording
4. Play the full 7-day game with arbitrage trading strategy
5. Export a gameplay GIF at the end

## The Skill

This Claude Code skill "patches" Claude's missing spatial intelligence for DOS-style UIs:

- **RED highlight** = currently selected item (act on it)
- **Arrow keys** navigate menus, **Enter** confirms
- **Blue box** on map = selected destination city
- Full buy/sell/travel workflow automation
- Pirate encounter handling, guard ship management
- Arbitrage strategy: Israel ↔ Turkey ↔ Egypt

## The "Skills as Patches" Concept

AI agents fail at non-standard UIs because they lack context-specific "common sense." Skills fill that gap — like OS patches. Give Claude a SKILL.md that explains the UI rules, and it transforms from clueless to capable.

This pattern works for any legacy system: old CRMs, insurance websites, Excel macros, DOS games.

## Skill File

```
skill/SKILL.md           ← the actual skill (install this)
~/.claude/skills/socher-hayam/SKILL.md  ← where it lives after install
```

## Website

[aviz85.github.io/socher-hayam-skill](https://aviz85.github.io/socher-hayam-skill)

---

Built with Claude Code · Powered by DOSBox & Anthropic
