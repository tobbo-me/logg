---
name: logg
description: Arbetslogg. Använd när användaren skriver /logg, "logga det här", "logga vad vi gjort" eller vill se sin logg ("visa loggen", "vad gjorde jag igår"). Lägger till en kort post i ~/Projekt 2026/logg/logg.md via kommandot `logg`, eller visar poster.
---

# /logg – arbetslogg över alla trådar

Loggen är en enda markdownfil, `~/Projekt 2026/logg/logg.md`, med en rad per post:

```
- 2026-09-08 10:24 [projektnamn] Vad som gjordes, i en till tre meningar.
```

Allt går via skalkommandot `logg` (ligger i `~/.local/bin`). Skriv aldrig direkt i filen.

## Tolka argumenten

`$ARGUMENTS` avgör vad som ska göras:

1. **Tomt** → sammanfatta och logga (se nedan).
2. **Börjar med `visa`** (eller användaren ber att få se loggen) → kör
   `logg visa <resten av argumenten>` och visa resultatet oförändrat.
   Giltiga filter: `idag`, `igår`, `vecka` (standard), `månad`, `alla`, ett tal (antal senaste poster), samt `-p projekt`.
3. **Annars** → argumenten är loggtexten. Logga den som den är, utan att skriva om den.

## Logga

Kör, med texten som ett enda citerat argument:

```bash
logg add "texten här"
```

Projektnamnet sätts automatiskt från git-roten eller arbetskatalogen. Ange `-p namn` bara om användaren uttryckligen vill ha ett annat projektnamn.

När argumenten är tomma: skriv själv en sammanfattning av vad som gjorts i den här tråden sedan senaste loggposten (eller sedan trådens början). Krav på texten:

- Svenska, en till tre meningar, en rad.
- Konkret: vad som byggdes, ändrades, beslutades eller upptäcktes. Inte "diskuterade olika alternativ".
- Inga filsökvägar om de inte är poängen.
- Om tråden inte innehåller något arbete värt att logga, säg det och logga inget.

Efter att posten är sparad: visa raden som kommandot skrev ut, inget mer.
