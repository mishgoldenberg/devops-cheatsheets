# SQL cheat sheet

The answers from every SQL quiz on [@mish.builds](https://www.instagram.com/mish.builds/), plus the one line that explains each.

## Deleting things

| Task | Command | Why |
|---|---|---|
| Empty the table, keep it | `TRUNCATE TABLE users` | DELETE and TRUNCATE empty it. |
| ⚠ Remove the table itself | `DROP TABLE users` | Gone, structure and all. |
| ⚠ UPDATE with no WHERE | changes every row | Run the SELECT with the same WHERE first. |
| Undo uncommitted changes | `ROLLBACK` | Inside a transaction, throws the changes away. |

## Querying

| Task | Command | Why |
|---|---|---|
| Matches in both tables only | `INNER JOIN` | Drops rows with no match. |
| Keep left rows with no match | `LEFT JOIN` | Missing right side becomes NULL. |
| Starts with A | `name LIKE 'A%'` | `%` = any characters, `_` = exactly one. |
| Find NULLs | `WHERE name IS NULL` | `= NULL` returns no rows: NULL equals nothing. |
| Each value once | `SELECT DISTINCT city` | Removes duplicate rows. |
| Filter after GROUP BY | `HAVING` | WHERE filters rows before grouping. |
| COUNT(*) vs COUNT(email) | COUNT(email) skips NULLs | COUNT(*) counts rows. |
| UNION vs UNION ALL | UNION removes duplicates | UNION ALL keeps every row and is faster. |
| What runs first | `FROM` | FROM → WHERE → GROUP BY → HAVING → SELECT → ORDER BY. |

## Speed and structure

| Task | Command | Why |
|---|---|---|
| Fast lookup by email | `CREATE INDEX ... (email)` | Without it, the database reads every row. |
| See the query plan | `EXPLAIN` | Which indexes, which scans. |
| PRIMARY KEY guarantees | unique, never NULL | It also gets an index. |

More: [Linux](linux.md) · [Git](git.md) · [Bash](bash.md)
