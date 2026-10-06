# World Cup Database

Solution for **World Cup Database** — [Relational Database (v8) certification](https://www.freecodecamp.org/certification/ueapisitkul/relational-database-v8) by freeCodeCamp.

## Files

- `worldcup.sql` — `pg_dump` of database `worldcup` (schema + data, 2014 + 2018 tournaments)
- `insert_data.sh` — loads `games.csv` (provided by freeCodeCamp curriculum, not committed) into `teams` + `games`
- `queries.sh` — 12 verification queries (total/average goals, champions, team lists)

## Schema (`worldcup`)

- `teams (team_id PK, name UNIQUE)` — 24 teams
- `games (game_id PK, year, round, winner_id FK -> teams, opponent_id FK -> teams, winner_goals, opponent_goals)` — 32 rows

## Restore / run

```bash
# rebuild from dump
psql --username=freecodecamp -f worldcup.sql

# or rebuild from CSV (needs games.csv from the curriculum next to the script)
./insert_data.sh

# run verification queries
./queries.sh
```
