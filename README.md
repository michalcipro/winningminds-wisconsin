# Winning Minds × University of Wisconsin

Info web pro **Sport Performance Consulting & Education Program** pro University of Wisconsin Women's Tennis, **25. 8. - 1. 9. 2026** v Madisonu.

Web je jeden soubor `index.html` bez buildu. Loga jsou vložená přímo v něm, takže na hosting se nahrává jen `index.html` a `og.png`.

## Právní rámec

Web je psaný tak, aby odpovídal schválenému rozsahu programu. **Při jakékoliv úpravě textů se držte tohoto rozsahu:**

Program je **sport-performance consulting a vzdělávání**. Pracuje se s pozorovatelným chováním na kurtu: příprava, rutiny mezi body, pozornost, rozhodování, exekuce pod tlakem, komunikace, týmové standardy a vzdělávání trenérů.

Program **není a web nesmí tvrdit**, že poskytuje: psychologickou diagnostiku, psychologické testování, hodnocení osobnosti, hodnocení duševního zdraví, psychoterapii, klinické poradenství, léčbu psychických poruch, hypnózu, hypnoterapii, klinický biofeedback, lékařskou diagnostiku ani léčbu.

Tato omezení jsou na webu vypsaná v sekci **Professional Scope**. Objeví-li se během programu klinické téma, je mimo rozsah a předává se licencovanému odborníkovi University of Wisconsin.

Sekce Professional Scope obsahuje i **Delivery and compliance** doložku o koordinaci s UW Athletics a o alternativním způsobu dodání, pokud by athlete-facing část nebyla vhodná vzhledem k imigračnímu statusu konzultantů.

## Jak web upravit

Vše je v `index.html`.

### Rozvrh (kalendář)

Na konci `index.html` najděte `const CALENDAR = {`. Každý den je klíč (číslo dne) a v něm časové sloty:

```js
"25":{
  "9:00":  {split:[M("Katya"), M("Masha")]},   // dělený slot: vlevo Michal, vpravo Milan
  "11:00": {full:DR("Katya · Masha · Elli · Parker")},
},
```

Zkratky nad daty: `M()` mapping session, `R()` review session, `O()` 1:1 session, `W()` planner session, `DR()` visual & reaction drills, `BRK` pauza. Témata dnů a popisky sloupců jsou v `const DAYS`.

Pojmenování slotů drží terminologii schváleného rozsahu programu. Při úpravách nepoužívejte slova jako diagnostika, testování nebo vyhodnocení ve smyslu psychologického posouzení.

### Dokumenty ke stažení

1. Nahrajte soubor do složky `documents/`
2. V `index.html` najděte `const DOCUMENTS = [` a přidejte:

```js
{ name:"Competition Routine Framework", file:"documents/routines.pdf", desc:"PDF · Pre-match, pre-point, between points" },
```

### Fotky konzultantů

Nahrajte `assets/michal.jpg` a `assets/milan.jpg` (čtvercové, min. 600 px). Web je použije automaticky místo iniciál v sekci The Consultants i na kontaktních kartách.

### Kontakty a FAQ

E-maily jsou v sekci Contact a v patičce, hledejte `mailto:`. FAQ jsou bloky `<details>`, přidání otázky je zkopírování jednoho bloku.

### Loga

Logo Winning Minds je originální vektor jako SVG symbol `#wm-mark` (znak) a `#wm-lockup` (znak s nápisem), zdroj v `assets/winning-minds-lockup.svg`. Oficiální Motion W je vložený jako obrázek v datovém formátu, zdroj v `assets/motion-w.png`, maskot Bucky v `assets/bucky.png`. Použití ochranné známky UW si nechte odsouhlasit programem.

### Náhledový obrázek pro sdílení

`og.png` v kořeni je karta, která se ukáže při sdílení odkazu. Musí ležet vedle `index.html`.

## Nasazení (Webglobe)

1. admin.webglobe.cz → Hosting → FTP a soubory → Správa souborů
2. Vybrat doménu, otevřít složku `public_html`
3. Nahrát `index.html` a `og.png`, staré verze přepsat
4. SSL certifikát → Let's Encrypt aktivní, zaškrtnout vynucení https

Web je statický, funguje stejně na GitHub Pages, Vercelu i Netlify.
