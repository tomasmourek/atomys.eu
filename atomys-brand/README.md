# ATOMYS — logo (SVG)

Vektorové (SVG) verze loga ATOMYS, **strojově vektorizované z originálních PNG**
(`Downloads/nejvetsilogoatomys.png` + `nejvetsisamostatnelogo.png`). Všechny
tvary — značka, nápis ATOMYS i tagline — jsou čisté křivky obkreslené z pixelů
předlohy se subpixelovou přesností a následně geometricky vyčištěné (rovné
hrany, symetrický trojúhelník, jednotné účaří). Žádný font není potřeba,
všude se zobrazí identicky. Prošlo nezávislou verifikací proti originálu
(geometrie, typografie, diakritika, barvy, technická kvalita SVG).

## Soubory

| Soubor | Co obsahuje | Kam se hodí |
|--------|-------------|-------------|
| `atomys-mark.svg` | jen značka „A" (průhledné pozadí) | ikona, avatar, watermark |
| `atomys-mark-tile.svg` | značka na tmavé dlaždici se zaoblenými rohy | favicon, app ikona, dlaždice |
| `atomys-logo.svg` | značka + nápis + tagline + světelná linka, průhledné pozadí — **jen na tmavé podklady** (text je bílý) | tmavé / fotografické podklady |
| `atomys-logo-dark.svg` | totéž na tmavém pozadí (věrná kopie předlohy) | hlavička webu, prezentace, OG obrázky |
| `atomys-logo-light.svg` | značka + grafitový nápis, bez linky; kov značky mírně ztmaven kvůli čitelnosti na bílé | světlé / bílé podklady |

## Jak použít

**HTML — obrázkem:**
```html
<img src="atomys-brand/atomys-logo.svg" alt="ATOMYS" width="400">
```

**Favicon / app ikona:**
```html
<link rel="icon" type="image/svg+xml" href="atomys-brand/atomys-mark-tile.svg">
```

**CSS pozadí:**
```css
.logo { background: url("atomys-mark.svg") no-repeat center / contain; }
```

**Inline vložení:** obsah `.svg` lze vložit přímo do stránky. Každý soubor má
unikátní prefix `id` gradientů (`m`/`t`/`wD`/`w`/`wL`), takže **libovolná
kombinace různých souborů inline v jedné stránce je bezpečná** — jen stejný
soubor nevkládej inline dvakrát.

Soubory mají `width`/`height` i `viewBox` — škálují se CSS bez omezení
a fungují i v e-mailech, Office a CMS náhledech.

## Barvy značky (navzorkováno z originálu)

| Prvek | Hodnoty |
|-------|---------|
| Kov — horní díl (Λ) | `#fcfcfd` → `#f1f4f7` → `#c4cdd8` → `#97a5b7` |
| Kov — spodní díl nohy | `#e3e7ed` → `#d4dae3` → `#c0c9d5` → `#aebbc9` |
| Modrý trojúhelník | `#1d80f6` → `#0166f0` |
| Nápis (tmavé verze) | bílá `#ffffff` → `#f6f8fa` (téměř plochá) |
| Tagline (tmavé verze) | `#b6c1ce` |
| Nápis (světlá verze) | `#525d6b` → `#232a34`, tagline `#5f6a78` |
| Pozadí banneru | `#010916` |
| Světelná linka | jádro bílé, záře `#2f9bff` / `#0566db` |

## Poznámka k původu

Logo bylo původně vygenerováno AI (GPT) jako rastr — neexistuje k němu žádný
„skutečný" font ani zdrojový vektor. Tyto SVG vznikly trasováním originálních
pixelů (marching squares + Douglas-Peucker + fit přímek/křivek), takže tvarově
odpovídají předloze 1:1; drobné AI nepravidelnosti hran byly záměrně
narovnány, aby logo bylo čisté i v tiskových velikostech.
