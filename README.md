# Winning Minds × Wisconsin Badgers Women's Tennis

Info web pro kemp **26. 8. - 1. 9. 2026** v Madisonu (University of Wisconsin-Madison).
Premium one-page web v modro-bílém stylu. Vše je v jednom souboru `index.html`, žádný build není potřeba.

## Jak web upravit

Celý web je jeden soubor: **`index.html`**. Stačí ho otevřít, upravit a commitnout.

### Rozvrh (nejčastější úprava)

Rozvrh se needituje v HTML, ale v datech na konci souboru: najdi v `index.html` blok `const SCHEDULE = [...]`.
Každý den je jedna položka:

```js
{
  d:"26", m:"AUG", day:"Wednesday", title:"Arrival & Kickoff", tag:"Intro",
  am:"Text dopoledního bloku...",
  pm:"Text odpoledního bloku..."
},
```

Změň texty `am` / `pm` / `title` podle potřeby a stránka se vykreslí automaticky.

### Dokumenty ke stažení

1. Nahraj soubor do složky `documents/` (např. `documents/wm-overview.pdf`)
2. V `index.html` najdi `const DOCUMENTS = [` a přidej řádek:

```js
{ name:"WM Performance System Overview", file:"documents/wm-overview.pdf", desc:"PDF · Kompletní metodika" },
```

Dokud je seznam prázdný, sekce zobrazuje „Nothing here yet".

### Loga

Web má vestavěné vektorové rekonstrukce obou log a zároveň automatickou výměnu za originály:

1. Nahrajte originální exporty do složky `assets/` pod přesnými názvy:
   - `assets/logo.svg` = logo Winning Minds (samotný znak, SVG export z Illustratoru/Figmy)
   - `assets/motion-w.svg` = oficiální Motion W Wisconsinu
2. Nic dalšího není potřeba. Stránka si soubory při načtení sama natáhne a použije je v hlavičce, hero vodoznaku, kartě týmu i patičce. Logo Winning Minds se automaticky přebarvuje podle podkladu (bílé na tmavé, tmavé na bílé), Motion W si nechává své barvy.

Dokud soubory neexistují, zobrazují se vestavěné rekonstrukce (symboly `#wm-mark` a `#uw-w` v `index.html`). Favicona používá vestavěný znak; po nahrání originálu ji na požádání překreslím. Použití ochranné známky UW si nechte odsouhlasit programem.

### Ostatní texty

Všechny sekce (Partnership, The System, Process, For Players, Team) jsou běžné HTML. Texty najdeš přímo v `index.html` a upravíš na místě.

## Publikace

Web je statický a funguje na GitHub Pages (Settings → Pages → Deploy from branch), Vercelu, Netlify i kdekoliv jinde bez jakékoliv konfigurace.
