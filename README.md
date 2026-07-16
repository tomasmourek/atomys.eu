# ATOMYS — firemní web (atomys.eu / atomys.cz)

Jednoduchý, moderní firemní rozcestník značky **ATOMYS**. Celý web je v jednom
souboru `index.html` (HTML + CSS + JS pohromadě). Žádná databáze, žádné
závislosti, žádné externí načítání (kvůli GDPR nepoužívá Google Fonts ani cizí
CDN).

**Hosting:** GitHub Pages (zdarma, včetně HTTPS) — repozitář
[`tomasmourek/atomys.eu`](https://github.com/tomasmourek/atomys.eu).
**Doména + DNS:** Wedos.

## Co web obsahuje
- Hero „Provoz pod kontrolou. Data, která rozhodují.“
- Sekci **Naše systémy** se 4 produkty: Atomys Auto, Care, Retail, Vision
- Sekci **Proč ATOMYS** (Inteligence, Automatizace, Přehled, Bezpečnost)
- Sekci **O nás / Kdo jsme** a **Kontakt** (e-mail + tlačítko „Napište nám“)
- Přepínač **denní / noční režim**, plně responzivní

---

## Jak web funguje / jak ho aktualizovat

Web je nasazený přes **GitHub Pages** z větve `main`. Cokoli commitneš do
`index.html` a pushneš, se do ~1 minuty automaticky projeví na webu.

```bash
# úprava obsahu
git add index.html
git commit -m "úprava textu"
git push
```

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

---

## Než web „vypustíš“ — doplň reálné údaje
1. **Kontaktní e-mail** — nyní `info@atomys.eu` (sekce Kontakt + patička).
2. **Telefon** — připravený zakomentovaný v sekci Kontakt (`<!-- Telefon… -->`).
3. **Odkazy produktů** — Atomys Auto → `mujautoservis.eu`; Care/Retail/Vision
   mají štítek „Připravujeme“, odkaz doplníš, až budou live.
4. **IČO / sídlo** — volitelně do patičky.

## Volitelná vylepšení
- **Vlastní geometrické písmo** (self-hosted, GDPR-clean) pro přesnější match
  s brand fontem — např. Michroma / Orbitron / Space Grotesk přes `@font-face`.
- **Sekce Reference** — až budou reálné reference od zákazníků (žádné vymyšlené).

## Poznámka ke kvalitě
Web prošel kontrolou přístupnosti (WCAG AA kontrast v obou režimech, klávesová
navigace, struktura nadpisů), responzivity (mobil 360 px → desktop, bez
vodorovného posuvníku) a české typografie (pomlčky, nedělitelné mezery).
