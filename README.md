# logg

Enkel arbetslogg som nås från alla Claude Code-trådar och från terminalen.

- `logg` – skalkommandot. Länkat till `~/.local/bin/logg`.
- `skill/` – skillen `/logg`. Länkad till `~/.claude/skills/logg`.
- Loggfilen ligger i `~/Projekt 2026/logg/logg.md` (ändra med miljövariabeln `LOGG_FIL`).

## Använda

```
/logg                      Claude sammanfattar tråden och loggar
/logg Bytte till sqlite     loggar exakt den texten
/logg visa                 senaste veckan
/logg visa idag | igår | månad | alla | 20 | -p projektnamn
```

Samma sak i terminalen: `logg add "text"`, `logg visa idag`, `logg fil`.

## Idéer som inte är byggda

- Hook som loggar automatiskt när en session avslutas.
- HTML-tidslinje över loggen.
