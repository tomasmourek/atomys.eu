# Netcup sifrovane zalohy – informace o aplikaci

Projekt: atomys.eu. Větev: pracovni/atomys-eu-informace-zalohovaci-aplikace.
Datum: 23. října 2026. Účel: kontext dvou veřejných informačních stránek pro vlastní zálohovací aplikaci a její konfiguraci Google OAuth.

## Účel a rozsah

Stránky vysvětlují soukromému provozovateli a návštěvníkům účel aplikace, oprávnění Google Drive, ukládání údajů a odvolání přístupu. Neobsahují přihlášení, registraci ani správu záloh. Administrace Atomys je mimo rozsah této změny.

- `index.html`: účel aplikace, kopírování a ověřování, omezené oprávnění `drive.file`, kontakt a odkaz na soukromí.
- `soukromi/index.html`: přístup k údajům, použití, ochrana, uchovávání, odstranění a provoz webu.

## Převzatý vzhled

Zachovat logo a tmavé pozadí `#080b12` stávajícího webu Atomys, systémové písmo, jednoduchou sazbu do 72 znaků a modré odkazy. Jde o rozšíření existujícího webu, nikoli o nový vizuální návrh. Obě stránky používají stejnou navigaci, viditelný focus, odkaz pro přeskočení navigace a mobilní rozvržení. Nevyžadují JavaScript, externí fonty ani obrázky kromě existujícího loga.

## Provozní podklad

Obsah vychází z místního řešení Restic/rclone: zálohy se šifrují před přenosem, aplikace žádá jen `drive.file`, kontroluje účet a kapacitu a ukládá technické manifesty. Přístup je chráněn Windows DPAPI. Kopie obnovovacího klíče používá samostatný heslem šifrovaný archiv. Automatický výmaz kopií není zaveden. Stránky popisují mechanismus ověřování; netvrdí dokončení konkrétního testu obnovy.

Samotný web nepoužívá analytiku, formuláře, cookies ani místní úložiště. Ve veřejném zdroji nejsou zálohy, obnovovací klíče ani přístupové údaje. Poskytovatel hostingu může zpracovávat technické údaje návštěvy.

## Ověření a publikování

Ověřena místní odpověď HTTP obou stránek a loga, vzájemné odkazy a zobrazení na počítači i při šířce 390 px. Dokončovací review nenašlo materiální závadu v HTML ani na čtyřech snímcích. Publikování a konfigurace Google OAuth vyžadují samostatné ověření skutečných veřejných adres; místní kontrola není důkaz nasazení.
