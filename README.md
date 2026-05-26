# LOG650 – Etterspørselsprognoser og KI-støttet lagerstyring
### Byggmakker Gravdal

**Student:** Oskar Eide  
**Kurs:** LOG650 – Kvantitative metoder i logistikk  
**Institusjon:** Høgskolen i Molde, 2026

---

## Problemstilling

> Hvordan kan etterspørselsprognoser og kunstig intelligens brukes til å forbedre lagerstyringen for utvalgte varer hos Byggmakker Gravdal?

---

## Om prosjektet

Byggmakker Gravdal er en byggevarebedrift tilknyttet Byggmakker-kjeden som betjener et betydelig B2B-segment av håndverkere og entreprenører. Bedriften bruker i dag erfaringsbasert varebestilling og opplever tilbakevendende utsalgssituasjoner for trelast i høysesong.

Prosjektet analyserer ukentlige salgsdata (jan 2024 – apr 2026) for fire produkter og sammenligner tre prognosemodeller for å finne det beste grunnlaget for datadrevne bestillingsbeslutninger.

---

## Analyserte produkter

| Produkt | Dimensjon | Kategori | Sesongmønster |
|---|---|---|---|
| Terrassebord | 28x120 mm | Trelast | Sterk sesong (vår/sommer) |
| Konstruksjonstre | 48x98 mm | Trelast | Sesong (vår/sommer) |
| Terrasseskrue | 4,2x55 mm | Festemidler | Sesong (følger terrassebord) |
| Universalskrue | 5x90 mm | Festemidler | Jevn hele året |

---

## Metode

- **Data:** 116 ukentlige observasjoner per produkt fra Byggmakker Gravdals ERP-system
- **Modeller:** Naiv referansemodell, SARIMA(1,1,1)(1,0,1)₁₃, Gradient Boosting Regressor
- **Evaluering:** 80/20 trenings-/testsplit — RMSE, MAE og MAPE
- **Lagerstyring:** Sikkerhetslager (SS), bestillingspunkt (ROP) og EOQ ved 95 % servicegrad
- **Verktøy:** Python (pandas, statsmodels, scikit-learn)

---

## Nøkkelresultater

SARIMA gir lavest prognosefeil i testperioden (lavsesong) for alle fire produkter. Det KI-støttede innkjøpssystemet reduserer utsalgssituasjoner markant sammenlignet med erfaringsbasert styring.

| Produkt | SS | ROP | Q* |
|---|---|---|---|
| Terrassebord (28x120) | 917 | 1 499 | 2 245 |
| Planke (48x98) | 1 345 | 2 522 | 2 906 |
| Terrasseskrue (4,2x55) | 8 | 12 | 94 |
| Skrue 5x90 | 13 | 19 | 120 |

---

## Innhold i dette repoet

```
├── 001 info/          README (denne filen)
├── 003 references/    Referanseliste med DOI-er (APA 7)
├── 004 data/          Rådata (Excel) og prosesserte analyseresultater (CSV)
├── 005 report/        Rapportkapitler (Markdown), Python-skript og figurer
└── 014 fase 4/        Ferdig rapport (rapport.docx)
```
