# ATOMYS — logo (SVG)

Vektorové (SVG) verze loga ATOMYS. SVG je bezztrátové a škáluje se do libovolné
velikosti — jeden soubor použiješ na web, favicon, tisk, prezentaci i aplikaci.

## Soubory

| Soubor | Co obsahuje | Kam se hodí |
|--------|-------------|-------------|
| `atomys-mark.svg` | jen značka „A" (průhledné pozadí) | ikona, avatar, watermark na tmavém/foto podkladu |
| `atomys-mark-tile.svg` | značka na tmavé dlaždici | favicon, app ikona, dlaždice na webu |
| `atomys-logo.svg` | značka + nápis + tagline, bílý text (průhledné) | tmavé / fotografické podklady |
| `atomys-logo-light.svg` | značka + nápis + tagline, grafitový text | světlé / bílé podklady |
| `atomys-logo-dark.svg` | celé logo na tmavém banneru (vč. modrého podtržení) | hlavička webu, patička, prezentace |

## Jak použít

**HTML — obrázkem:**
```html
<img src="atomys-brand/atomys-logo.svg" alt="ATOMYS" width="320">
```

**HTML — vložené inline** (jde stylovat CSS, mění barvu přes `fill`):
```html
<!-- zkopíruj obsah .svg přímo do stránky -->
```

**CSS pozadí:**
```css
.logo { background: url("atomys-mark.svg") no-repeat center / contain; }
```

**Favicon:**
```html
<link rel="icon" type="image/svg+xml" href="atomys-mark-tile.svg">
```

## Barvy značky

| Prvek | HEX |
|-------|-----|
| Modrá (trojúhelník / akcent) | `#1466d8` → `#47a0ff` |
| Stříbrná plocha (světlá) | `#ffffff` → `#7f8b9a` |
| Tmavé pozadí (banner/dlaždice) | `#0d1a30` → `#05090f` |

## Poznámka k písmu nápisu

Nápis „ATOMYS" je vykreslen jako **vektorové cesty** (ne systémovým fontem),
takže se všude zobrazí identicky a nevyžaduje žádný nainstalovaný font.
Tagline je zatím sázen fontem Arial/Helvetica přes `<text>` — pro 100%
shodu na všech zařízeních ho lze převést do křivek.
