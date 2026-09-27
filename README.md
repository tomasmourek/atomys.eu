# ATOMYS — firemní web (atomys.eu / atomys.cz)

Firemní rozcestník značky **ATOMYS**. Obsah, texty ve 13 jazycích a skript jsou
v jednom souboru `index.html`; vzhled dává sjednocený styl **Atomys 2.0** ve složce
`atomys/`. Žádná databáze, žádný build, žádné externí načítání (písma IBM Plex jsou
ve složce `atomys/fonty`, web nepoužívá Google Fonts ani cizí CDN).

**Hosting:** GitHub Pages z větve `main` — repozitáře
[`tomasmourek/atomys.eu`](https://github.com/tomasmourek/atomys.eu) a
[`tomasmourek/atomys.cz`](https://github.com/tomasmourek/atomys.cz).
**Doména + DNS:** Wedos.

## Co web obsahuje
- Úvod s větou o tom, co ATOMYS dělá, a přehledem systémů se stavem
  (Atomys Auto v provozu s odkazem na mujautoservis.eu; Care, Retail a Vision ve vývoji)
- Tlačítko „Napište nám“ (e-mail s předvyplněným předmětem) pod přehledem systémů
- Sekci **O nás** (krátký odstavec o vlastním vývoji) a **Kontakt** (e-mail, telefon)
- Patičku s tiráží provozovatele a informací o úložišti v prohlížeči
- Volbu jazyka (13 jazyků; výchozí podle domény: `.cz` česky, jinak anglicky)
  a barevného motivu (systém, světlý, tmavý); plně responzivní od 320 px

## Vzhled: styl Atomys 2.0
- `<html data-area="atomys" data-vzhled="tiskopis" data-vzhled-pevny>`: web produktu má
  podle pravidel design systému (PRAVIDLA.md, oddíl 1) pevný vzhled Tiskopis a neutrální
  akcent oblasti `atomys`. Návštěvník si volí jen motiv; barvu lišty mobilního prohlížeče
  (`meta theme-color`) skript sladí se zvoleným motivem.
- Složka `atomys/` je převzatý balíček design systému
  ([atomys-design-system](https://github.com/tomasmourek/atomys-design-system)).
  **Needitovat ručně.** Aktualizace z kořene tohoto repozitáře:
  ```bash
  node <atomys-design-system>/tools/prevzit.mjs atomys
  ```
  Potom v `index.html` zvýšit `?v=` u odkazů na `atomys/` na novou verzi
  (`atomys/VERZE`), aby prohlížeče nenačetly starý soubor z cache.
- `.gitattributes` drží `atomys/**` bez převodu konců řádků (jinak by nesouhlasily
  kontrolní součty v `atomys/manifest.json`).
- Vlastní CSS webu je krátký blok `<style>` v `index.html` a používá jen proměnné `--at-*`.
- Plochá jednobarevná značka v patičce: `atomys-brand/atomys-lockup-plochy.svg`.
- Kontrola stylu: `node <atomys-design-system>/tools/kontrola-stylu.mjs .`

## Dva repozitáře, jeden obsah
`atomys.cz` a `atomys.eu` mají **stejný** `index.html`, `atomys/`, `atomys-brand/`,
`og.png`, `.gitattributes` a tento README. Liší se jen `CNAME`, `robots.txt` a
`sitemap.xml` (vlastní doména) a `atomys.eu` má navíc prezentaci `prezentace/`.
Každou změnu obsahu proto udělejte v obou repozitářích stejně. Kanonickou adresu a
`og:url` nastaví skript podle domény, na které stránka běží.

## Úložiště v prohlížeči
Web nenastavuje cookies a nemá analytiku. Do `localStorage` zapisuje jen po změně
uživatelem: `atomys-lang` (zvolený jazyk) a `atomys-theme` (zvolený motiv; klíč převzatý
z předchozí verze webu atributem `data-klic-motiv`). Tentýž popis je v patičce webu.

---

## Jak web aktualizovat

Web je nasazený přes **GitHub Pages** z větve `main`. Commit do `main` se do ~1 minuty
projeví na webu. Úpravy dělejte na pracovní větvi a do `main` slučujte až po kontrole.

Živá adresa (než se napojí doména): <https://tomasmourek.github.io/atomys.eu/>

---

## Napojení domény atomys.eu (DNS na Wedosu)

Aby web běžel na **https://atomys.eu**, je potřeba v DNS na Wedosu
(Zákaznické centrum → DNS → doména atomys.eu) přidat tyto záznamy:

**A záznamy** (kořen domény `@` → GitHub Pages):
```
@   A   185.199.108.153
@   A   185.199.109.153
@   A   185.199.110.153
@   A   185.199.111.153
```

**AAAA záznamy** (IPv6, doporučené):
```
@   AAAA   2606:50c0:8000::153
@   AAAA   2606:50c0:8001::153
@   AAAA   2606:50c0:8002::153
@   AAAA   2606:50c0:8003::153
```

**CNAME** (verze s www → přesměruje na GitHub Pages):
```
www   CNAME   tomasmourek.github.io.
```

Poté v repozitáři nastavit **Settings → Pages → Custom domain = `atomys.eu`**
a zaškrtnout **Enforce HTTPS** (certifikát vystaví GitHub automaticky, chvíli to
trvá). DNS propagace může trvat i pár hodin.

### atomys.cz
Doporučeno: nechat běžet hlavní web na atomys.eu a **atomys.cz na něj
přesměrovat** (ve Wedos nastavení domény / přesměrování) — kvůli SEO (duplicitní
obsah). Případně lze stejné DNS záznamy nastavit i pro atomys.cz a v Pages přidat
druhou custom doménu.

### Známý problém: HTTPS
Podle plánu převzetí stylu nefunguje HTTPS na vlastních doménách (certifikát GitHub
Pages). Řeší ho samostatná úloha; změna vzhledu na něj nemá vliv a v jejím rámci se
neověřovalo.

---

## Než web „vypustíš“ — doplň reálné údaje
Větev se změnou vzhledu do `main` neslučujte, dokud není hotový bod 1: `main` se nasazuje
automaticky a zástupné hodnoty by se zveřejnily ve všech 13 jazycích.

1. **Tiráž v patičce** — nahradit zástupné hodnoty `[doplnit: obchodní firma]`,
   `[doplnit: IČO]`, `[doplnit: DIČ]`, `[doplnit: sídlo]`, `[doplnit: zápis v OR]`
   (v `index.html`, v obou repozitářích).
2. **Kontakt** — nyní `info@atomys.eu` a `+420 604 964 867` (sekce Kontakt a patička).
3. **Odkazy produktů** — Atomys Auto → `mujautoservis.eu`; Care, Retail a Vision mají
   stav „Ve vývoji“ bez odkazu, odkaz doplníš, až budou v provozu.
4. **Tvrzení v textech** — neověřená tvrzení „Provoz 24/7“ a „v souladu s pravidly“ byla
   odstraněna. Nové tvrzení (dostupnost, certifikace, lhůty) přidávejte jen doložené.

## Volitelná vylepšení
- **Sekce Reference** — až budou reálné reference od zákazníků (žádné vymyšlené).
