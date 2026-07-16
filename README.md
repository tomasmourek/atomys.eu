# ATOMYS — firemní web (atomys.eu / atomys.cz)

Jednoduchý, moderní firemní rozcestník značky **ATOMYS**. Celý web je
v jednom souboru `index.html` (HTML + CSS + JS pohromadě), takže se nahrává
a spravuje maximálně snadno. Žádná databáze, žádné závislosti, žádné externí
načítání (kvůli GDPR nepoužívá Google Fonts ani cizí CDN).

## Co web obsahuje
- Hero „Provoz pod kontrolou. Data, která rozhodují.“
- Sekci **Naše systémy** se 4 produkty: Atomys Auto, Care, Retail, Vision
- Sekci **Proč ATOMYS** (Inteligence, Automatizace, Přehled, Bezpečnost)
- Sekci **O nás / Kdo jsme**
- Sekci **Kontakt** (e-mail + tlačítko „Napište nám“)
- Patičku s odkazy a doménami
- Přepínač **světlý / tmavý režim** (pamatuje si volbu, respektuje systémové nastavení)
- Plně responzivní (mobil, tablet, desktop)

---

## Než web nasadíte — doplňte reálné údaje
V `index.html` upravte tyto věci (stačí najít text a přepsat):

1. **Kontaktní e-mail** — nyní `info@atomys.eu`. Nahraďte, pokud chcete jiný.
   Vyskytuje se na několika místech (sekce Kontakt + patička).
2. **Telefon** — je připravený, ale zakomentovaný. V sekci Kontakt najděte
   `<!-- Telefon doplňte podle potřeby:` a odkomentujte + doplňte číslo.
3. **Odkazy na produkty** — `Atomys Auto` míří na `https://mujautoservis.eu`.
   Až budou spuštěné Care / Retail / Vision, přidejte jim odkazy stejným
   způsobem (nyní mají štítek „Připravujeme“).
4. **IČO / sídlo / fakturační údaje** — pokud je chcete zobrazit (např. kvůli
   důvěryhodnosti nebo zákonným povinnostem), přidejte je do patičky.

---

## Nasazení na Wedos (webhosting)

1. Přihlaste se do **[client.wedos.com](https://client.wedos.com)**.
2. Otevřete svůj **webhosting** pro doménu `atomys.eu`.
3. Připojte se přes **File Manager** (ve Wedos administraci) nebo přes **FTP**
   (údaje najdete ve Wedos → Webhosting → FTP účty).
4. Nahrajte soubor **`index.html`** do kořenové složky webu — u Wedos je to
   obvykle složka **`www/`** (někdy `public_html` / `web`). Soubor musí být
   přímo v ní, ne v podsložce.
5. Otevřete `https://atomys.eu` — web by měl naskočit.

### Druhá doména (atomys.cz)
Máte dvě možnosti:
- **A) Stejný obsah na obou** — nahrajte `index.html` i na webhosting
  `atomys.cz` (stejný postup). Nezapomeňte pak upravit `og:url` a `canonical`,
  pokud chcete .cz řešit samostatně.
- **B) Přesměrování** (doporučeno kvůli SEO) — nechte hlavní web na `atomys.eu`
  a `atomys.cz` na něj přesměrujte. Ve Wedos to jde v nastavení domény/webhostingu
  (přesměrování / alias). Tím se vyhnete duplicitnímu obsahu.

### HTTPS / certifikát
Wedos nabízí **Let's Encrypt zdarma** — zapněte SSL certifikát v administraci
webhostingu, aby web běžel na `https://`.

---

## Úpravy do budoucna
- **Barvy** se mění nahoře v CSS v blocích `:root`, `[data-theme="dark"]`
  a `[data-theme="light"]`.
- **Texty** jsou přímo v HTML, česky, snadno dohledatelné.
- **Přidání produktu** = zkopírovat jeden blok `<article class="card">`.

Web je záměrně bez cookies, trackingu a externích služeb — nevyžaduje cookie
lištu a je v pohodě z pohledu GDPR.

## Volitelná vylepšení (nice-to-have)
- **Vlastní geometrické písmo** — nadpisy a wordmark teď běží na systémovém
  fontu (kvůli GDPR a rychlosti bez externího Google Fonts). Pokud budete chtít
  přesnější match s brand fontem, dá se doplnit *self-hosted* geometrický font
  (např. Michroma, Orbitron, Space Grotesk) přes `@font-face` z vlastního
  serveru — pořád GDPR-clean, protože se nenačítá z ciziny.
- **Sekce Reference / recenze** — až budete mít reálné reference od zákazníků
  (např. z provozu mujautoservis.eu), dá se přidat sekce „Reference" s citacemi
  nebo logy klientů. Záměrně tam teď nejsou žádné vymyšlené recenze.
- **Telefon / IČO / sídlo** — připravené jako placeholdery, viz sekce výše.

## Poznámka ke kvalitě
Web prošel kontrolou na přístupnost (kontrast textu WCAG AA v obou režimech,
klávesová navigace, struktura nadpisů), responzivitu (mobil 360 px → desktop,
bez vodorovného posuvníku) a českou typografii (pomlčky, nedělitelné mezery).
