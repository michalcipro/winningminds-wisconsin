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

### Fotky do sekce Team a Contact

Nahrajte portréty jako `assets/michal.jpg` a `assets/milan.jpg` (čtvercové, min. 600 px) a stránka je automaticky použije místo iniciál, v sekci Team i na kontaktních kartách. Dokud soubory neexistují, zobrazují se iniciály.

### Náhledový obrázek pro sdílení

Soubor `og.png` v kořeni je náhledová karta, která se ukáže, když někdo pošle odkaz mailem, v iMessage nebo na sociální síti. Musí ležet přímo v kořeni webu vedle `index.html`.

### Loga

Logo Winning Minds je originální vektor zapracovaný přímo v `index.html`: symbol `#wm-mark` je samotný znak (hero vodoznak, favicona), symbol `#wm-lockup` je znak s nápisem (hlavička, patička). Barvu si bere automaticky z podkladu. Zdrojový soubor je uložený v `assets/winning-minds-lockup.svg`.

Logo Wisconsinu je zatím stylizované červené "W". Až budete mít oficiální Motion W, nahrajte ho jako `assets/motion-w.svg` a stránka ho automaticky použije v hlavičce, kartě týmu i patičce. Použití ochranné známky UW si nechte odsouhlasit programem.

### Kontakty a FAQ

E-mailové adresy jsou v sekci Contact a v patičce `index.html`, hledejte `mailto:`. Otázky a odpovědi v sekci FAQ jsou běžné HTML bloky `<details>`, přidání další otázky je zkopírování jednoho bloku.

### Ostatní texty

Všechny sekce (Partnership, The System, Process, For Players, Team) jsou běžné HTML. Texty najdeš přímo v `index.html` a upravíš na místě.

## Publikace (Vercel)

1. Na https://vercel.com/new se přihlaste přes GitHub a importujte repo `michalcipro/winningminds-wisconsin`
2. Framework preset **Other**, Build Command i Output Directory nechte prázdné, klikněte **Deploy**
3. Vercel od té chvíle nasadí každý push automaticky a dá vám URL ve tvaru `*.vercel.app`; ostrou verzi pak přepnete přidáním vlastní domény v Settings → Domains

Web je čistě statický, takže funguje stejně i na GitHub Pages nebo Netlify.
