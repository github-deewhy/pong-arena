# 🎮 PONG ARENA — Progression & Monetization Design

**Phase 3 Complete: Cosmetic Shop UI + Paddle/Ball Skins**

## Core Philosophy

**Cosmetic + convenience purchases only** — nothing that changes game balance. Paying players look cooler and unlock things faster, but a free player with skill always wins.

---

## 1. 🎯 XP & LEVEL SYSTEM

Every match awards XP based on performance:

| Action | XP Awarded |
|--------|------------|
| Win | +100 XP |
| Loss | +40 XP |
| Each point scored | +5 XP |
| Perfect win (opponent scores 0) | +75 XP bonus |
| Comeback win (trailing by 3+) | +50 XP bonus |

**Levels 1-100**, each unlock something. Free to earn, purchasable to skip.

---

## 2. ✨ COSMETIC UNLOCKS (Earnable & Purchasable)

| Item | Unlock (free) | Fast-track (paid) |
|------|---------------|-------------------|
| Paddle skins | Level 5, 15, 30, 50 | $0.99 each |
| Ball trails | Level 10, 25, 45 | $0.99 each |
| Win animations | Level 20, 40 | $1.99 each |
| Player titles | Ranked achievements | $0.49 each |
| Arena themes | Level 60, 80, 100 | $2.99 each |

### Current Shop Items

**Paddle Skins:**
- Classic 🏓 (Free, default)
- Fire 🔥 (Level 5, 50 coins)
- Ice ❄️ (Level 15, 80 coins)
- Neon ⚡ (Level 30, 120 coins)
- Galaxy 🌌 (Level 50, 200 coins)
- Gold 👑 (Level 75, 350 coins)

**Ball Trails:**
- Classic ⚪ (Free, default)
- Comet ☄️ (Level 10, 60 coins)
- Flame 🔥 (Level 25, 100 coins)
- Rainbow 🌈 (Level 45, 180 coins)
- Ghost 👻 (Level 60, 250 coins)

---

## 3. ⚡ POWER-UP EXPANSION (Earnable Slots) *[Phase 6]*

Currently power-ups are random. Future loadout system:

- **Free players**: 1 loadout slot, random power-ups
- **Level 20+**: Choose which 2 power-ups appear
- **Level 50+**: 3 power-up slots
- **Premium**: Unlock all power-up types immediately

### Planned Power-up Types

| Power-up | Effect |
|----------|--------|
| Fireball 🔥 | Ball passes through paddle once |
| Magnet 🧲 | Bend ball trajectory slightly |
| Ghost ball 👻 | Ball invisible for 2 seconds |
| Explosion 💥 | Reset opponent's paddle position |
| Shield 🛡️ | One-time block that saves a point |

---

## 4. 🏆 RANKED SEASONS *[Phase 4]*

- **Season lasts 30 days**
- **Ranks**: Bronze → Silver → Gold → Platinum → Diamond → Legend
- **Season-end rewards**: Exclusive cosmetics for top % of players
- **Season Pass ($4.99)**: Double XP, exclusive skin, premium badge

---

## 5. 👑 PREMIUM MEMBERSHIP ($2.99/month) *[Phase 5]*

- Double XP on all matches
- Exclusive premium paddle skin
- Custom player title color
- Priority matchmaking
- No ads (when/if ads are introduced)
- Access to private rooms with custom rules

---

## 6. 🪙 COIN SYSTEM (Virtual Currency)

**Earn:**
- Win: 10 coins
- Loss: 5 coins
- Daily first win: +25 coins bonus
- Login streak bonuses: 5-100 coins

**Buy:** Coin packs at $0.99 / $2.99 / $7.99

**Spend:** Cosmetics, XP boosts, custom room settings

*This is the critical monetization bridge — players grind coins or buy them.*

---

## 📋 Implementation Roadmap

| Phase | Status | Description |
|-------|--------|-------------|
| **Phase 1** | ✅ Complete | XP + Levels (server-side, stored in Firebase) |
| **Phase 2** | ✅ Complete | Coin system + daily rewards |
| **Phase 3** | ✅ Complete | Cosmetic shop UI + paddle/ball skins in canvas |
| **Phase 4** | 🔜 Planned | Ranked seasons + season pass |
| **Phase 5** | 🔜 Planned | Premium membership + Stripe integration |
| **Phase 6** | 🔜 Planned | Power-up loadouts + new power-up types |

---

## 📊 Database Schema

### `leaderboard/{uid}`

```javascript
{
  uid: string,
  displayName: string,
  wins: number,
  losses: number,
  matchesPlayed: number,
  xp: number,
  level: number,
  coins: number,
  loginStreak: number,
  lastLoginDate: string,  // YYYY-MM-DD
  lastWinDate: string,    // YYYY-MM-DD
  ownedItems: string[],   // item IDs
  equippedItems: {
    paddle: string,
    trail: string
  },
  createdAt: string,
  updatedAt: string
}