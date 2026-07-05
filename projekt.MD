# Myší dárkovník – zadání

## Cíl
Jednoduchá mobilní PWA pro plánování a sdílení dárků mezi rodinnými příslušníky, bez přihlášení, zdarma.

## Funkce
- Příležitosti: Vánoce, Narozeniny, Den dětí, Mikuláš + možnost „Další…" pro vlastní hodnotu
- Dárky: název, příjemce, cena (volitelná), datum koupit, nákupčí, odkaz kde koupit, stav (koupeno/nekoupeno), důležité, tajné
- Příjemce: An, Marek, Daník, Naty, Kari + možnost „Další…" pro další osoby
- Nákupčí (osoba která bude koupit): An, Marek, Daník, Naty, Kari + možnost „Další…"
- Filtr dárků podle příležitosti, příjemce, nákupčího, data koupit
- Přehled: po příležitosti → Dnes / Brzy (do týdne) / Později / Bez termínu → Koupeno
- Důležité = připomenutí (vizuální indikátor)
- Odznak na ikoně appky (🔴 číslo) = počet mých nehotových dárků k nákupu; přepočítá se při otevření appky
- Úprava i mazání dárku (tužka / ×)
- „Kdo jsem": každý si na svém telefonu jednou vybere svoji myšku — zámek, není možné jednoduše změnit
- Po výběru appka defaultně ukazuje vlastní dárky (co já mám koupit); lze přepnout na jinou osobu nebo „Vše"
- Tajné dárky (🔒): vidí je jen ten, kdo je zadal (např. dárky na překvapení)

## Technologie (stejný přístup jako Myší úkolárna)
- Frontend: jeden soubor `index.html` (HTML + CSS + JavaScript), bez buildu
- Data dárků: sdílená cloudová databáze **Supabase** (tabulka `gifts`, živá synchronizace)
- Identita „kdo jsem": uložená v telefonu (`localStorage`, klíč `mysi-darkovnik-me`) — po výběru bez možnosti změny
- Přístup: bez přihlášení
- Hosting: GitHub Pages (appka dostupná odkazem, „Přidat na plochu")

> Poznámka: Stejný jednoduchý přístup jako u Myší úkolárny — bez React, Vite, TypeScript.

> Zámek identity: Po prvním výběru myšky se neukazuje tlačítko „Změnit". Pokud by se někdo splétl, může data vymazat jen ručně přes DevTools (záměrná akce).

> Tajné dárky: V aplikaci je vidí jen jejich autor. Nejsou technicky neprůstřelné (data jsou ve sdílené databázi), ale pro rodinná překvapení to stačí.

> Odznak na ikoně: Zobrazí se jen u appky **přidané na plochu** (ne při otevření odkazu v prohlížeči). Počet se přepočítá při každém otevření appky.

## Stav
- [x] Zadání
- [x] Návrh vizualizace a funkcí
- [x] Příprava: separátní složka Mysi-darkovnik (bez rizika pro Myší úkolárnu)
- [x] Fáze 1: appka jako jeden `index.html` (příležitosti, dárky, příjemci, nákupčí, přehledy, filtr)
- [x] Fáze 1: výběr „kdo jsem" a zámek identity
- [x] Fáze 1: tajné dárky (vidí jen autor)
- [ ] Fáze 1: vyzkoušet v mobilu (otevřít soubor / odkaz)
- [ ] Vytvořit tabulku `gifts` v Supabase
- [ ] Fáze 2: sdílení mezi telefony přes cloud (Supabase)
- [ ] Nahrát novou verzi na GitHub Pages a rozeslat odkaz rodině
- [ ] Odznak na ikoně appky (počet mých nehotových dárků k nákupu)
- [ ] (Volitelně) Plné push notifikace – číslo i se zavřenou appkou (větší projekt)
