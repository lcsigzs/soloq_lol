# Project Overview

This document explains the functionalities and details of the project.

## How This Project Works

### First Function: `get_puuId`
**Parameters:**
- `summonerId` - (str, default=None)
- `gameName` - (str, default=None)
- `tagLine` - (str, default=None)
- `region` - (str, default="americas")

Uses the return from the third function (`summonerId`) with the region to return the player's `puuid`.

### Second Function: `get_idtag_from_puuid`
**Parameters:**
- `puuid` - (str, default=None)

### Third Function: `get_ladder`
**Parameters:**
- `top` - (int, default=300)

This function returns a DataFrame of the top `x` players in solo queue.  
**Returns:** `summonerId`, `leaguePoints`, `wins`, `losses`, `veteran`, `inactive`, `freshBlood`, `hotStreak`.

### Fourth Function: `get_match_history`
**Parameters:**
- `region` - (str, default=None)
- `puuid` - (str, default=None)
- `start` - (int, default=0)
- `count` - (int, default=20)

**Returns:** The last 20 matches of the player with this `puuid`.

### Fifth Function: `get_match_data`
**Parameters:**
- `region` - (str, default=None)
- `match_Id` - (str, default=None)

Uses the return from the fourth function (`match_id`) to get the data from this match.

### Sixth Function: `process_match_json`
**Parameters:**
- `match_json` - (json) *This JSON comes from `get_match_data_from_id`*
- `puuid` - (str)

This function returns a DataFrame that provides all the match information for the team of the player I selected (`puuid`).

### Seventh Function: `json_extract`
**Parameters:**
- `obj` - (json) can be a `dict` or a `list`
- `key` - (str)

This function creates a dictionary that links the ID and the name from the perks.
