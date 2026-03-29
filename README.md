# PAGCOR CEGS - Approved Electronic Games Data

Structured dataset of all EGLD-approved electronic games listed on the [PAGCOR CEGS](https://www.pagcor.ph/regulatory/cegs.php) regulatory page.

PAGCOR (Philippine Amusement and Gaming Corporation) publishes PDF lists of approved electronic games for each licensed game provider. This repository converts those PDFs into machine-readable JSON and tracks changes over time via git history.

## Data Structure

```
├── index.json              # Summary of all providers
└── providers/
    ├── JILI.json           # One file per provider
    ├── CQ9.json
    ├── PRAGMATIC-PLAY.json
    └── ...
```

## index.json

```json
{
  "source_url": "https://www.pagcor.ph/regulatory/cegs.php",
  "total_providers": 78,
  "total_games": 4834,
  "providers": [
    { "name": "JILI", "file": "JILI.json", "total_games": 217 }
  ]
}
```

## Provider JSON

```json
{
  "provider": "JILI",
  "source_url": "https://www.pagcor.ph/regulatory/pdf/App%20Kits/JILI.pdf",
  "last_updated": "March 19, 2026",
  "total_games": 217,
  "games": [
    {
      "no": 1,
      "game_offering": "eBINGO GAMES",
      "game_name": "BINGO ADVENTURE",
      "game_id": "177",
      "game_version": "V. 1",
      "game_type": "eBINGO"
    }
  ]
}
```

## Fields

| Field | Description |
|-------|-------------|
| `game_offering` | Category: eBINGO GAMES, eCASINO GAMES, SPORTS BETTING, SPECIALTY GAMES, NUMERIC GAMES |
| `game_name` | Game title |
| `game_id` | Game identifier (some providers don't have this) |
| `game_version` | Game version |
| `game_type` | Type: SLOT, TABLE, ARCADE-TYPE, eBINGO, NUMERIC, LIVE DEALER TABLE GAME, etc. |

## How Changes Are Tracked

Each commit represents a change detected on the PAGCOR website. Check `git log` for the full history of additions, updates, and removals.

## Data Source

All data is sourced from [PAGCOR's official CEGS page](https://www.pagcor.ph/regulatory/cegs.php). This repository only reformats the publicly available information into a structured format.

## License

The game approval data is published by PAGCOR, a Philippine government agency. This repository provides the data in a structured format for informational purposes.
