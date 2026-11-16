# Výletník pro rodiny

Výletník je no-code AI agent v n8n vytvořený jako domácí úkol
pro kurz AI agenti. Doporučuje rodinné výlety v Praze a Středočeském kraji
podle dotazu uživatele.

Po přijetí zprávy agent zavolá Data Table Tool a načte z databáze
20 výletů. Jazykový model z vrácených údajů sestaví odpověď v češtině.

## Soubory

- `Výletník pro rodiny.json` – export workflow z n8n
- `vylety.csv` – data připravená pro import do n8n
- `vyletnik-pro-rodiny.xlsx` – zdrojová tabulka výletů

## Jak agenta vyzkoušet

1. V projektu v n8n vytvoř Data Table volbou **Import CSV**
   a nahraj `vylety.csv`.
2. Do stejného projektu importuj `Výletník pro rodiny.json`.
3. V uzlu **Data Table Tool** vyber právě naimportovanou tabulku.
4. V uzlu **OpenAI Chat Model** vyber vlastní OpenAI připojení
   nebo Gateway credits, pokud je tvoje instance nabízí.
5. Otevři testovací chat v editoru workflow a zadej dotaz níže.

## Ukázkový test

**Dotaz:** Kolik stojí vstup pro jednoho dospělého a čtyřleté dítě
do Národního technického muzea?

**Očekávaná odpověď:** Dospělý 330 Kč, čtyřleté dítě zdarma,
celkem 330 Kč podle dat v tabulce.

V detailu spuštění lze ověřit, že agent zavolal Data Table Tool.
