---
description: Een samenvatting van de steekproefmethode die voor sommige rapporten wordt gebruikt, foutenpercentages van de steekproef, en een lijst van rapporten die informatie terugkeren die op bemonsterde gegevens wordt gebaseerd.
seo-description: Een samenvatting van de steekproefmethode die voor sommige rapporten wordt gebruikt, foutenpercentages van de steekproef, en een lijst van rapporten die informatie terugkeren die op bemonsterde gegevens wordt gebaseerd.
seo-title: Gegevensbemonstering en foutenpercentages in geselecteerde rapporten van het Manager van de Publiek
solution: Audience Manager
title: Gegevensbemonstering en foutenpercentages in geselecteerde rapporten van het Manager van de Publiek
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Gegevensbemonstering en foutenpercentages in geselecteerde rapporten van het Manager van de Publiek{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Een samenvatting van de steekproefmethode die voor sommige rapporten wordt gebruikt, foutenpercentages van de steekproef, en een lijst van rapporten die informatie terugkeren die op bemonsterde gegevens wordt gebaseerd.

## Bemonsteringsfrequentie en minimumeisen {#data-sampling-ratio}

Sommige [!DNL Audience Manager] rapporten tonen resultaten die op een bemonsterde reeks van de totale hoeveelheid beschikbare gegevens worden gebaseerd. De gegevensverhouding in het monster is 1:54. Voor rapporten die bemonsterde gegevens gebruiken, betekent dit uw resultaten op 1 verslag van elke reeks 54 verslagen worden gebaseerd.

Deze rapporten gebruiken gesamplede gegevens omdat ze een enorme hoeveelheid verwerkingskracht nodig hebben om resultaten te genereren. Bemonstering helpt een evenwicht te vinden tussen lagere computervereisten, het handhaven van systeemprestaties en het verstrekken van nauwkeurige resultaten.

Rapporten waarin gebruik wordt gemaakt van steekproeven sluiten kenmerken en segmenten uit wanneer deze niet voldoen aan de minimale unieke bezoekersvereisten. Deze minimumeisen zijn als volgt:

* Tanden: 28.000 [unieke karakteristieken](/help/using/features/traits/trait-and-segment-qualification-reference.md#unique-trait-realizations) over een periode van 14 dagen.
* Segmenten: 70.000 real-time gebruikers over een periode van 14 dagen.

## Foutpercentages {#error-rates}

Er kunnen fouten optreden in rapporten die overlappende gegevens genereren. Een fout wordt gedefinieerd als het percentage records dat:

* Was niet in een rapport opgenomen maar toch toegevoegd.
* Het had in een verslag moeten worden opgenomen, maar het werd weggelaten.

Het is belangrijk om op te merken dat onze tests en modellen tonen dat het foutenpercentage in omgekeerde verhouding *vermindert* aan het aantal verslagen in uw gegevensreeks. Gegevenssets met veel records genereren minder fouten dan gegevenssets met een klein aantal records. Laten we deze bewering op een meer kwantitatieve manier bekijken. Zoals getoond in de volgende lijst, voor een bepaald aantal verslagen, zal 95% van uw rapportresultaten onder een specifiek foutenpercentage zijn.

| Aantal records | Foutfrequentie |
|--- |--- |
| 500 - 1,000 | 95% is lager dan een 42%-foutenpercentage. |
| 1,000 - 1,500 | 95% is lager dan een foutpercentage van 34%. |
| 10,000 - 50,000 | 95% is lager dan een foutpercentage van 14%. |
| 50,000 | 95% is lager dan een foutenpercentage van 6%. |
| 100,000 | 95% is lager dan een foutpercentage van 4%. |
| 500.000 (of meer) | 95% is lager dan een foutpercentage van 2%. |

## Rapporten waarin voorbeeldgegevens worden gebruikt {#reports-using-sampled-data}

De [!DNL Audience Manager] rapporten die bemonsterde gegevens gebruiken omvatten:

* [Overlap rapporten](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait en segment-to-segment).
* [Adresseerbare gegevens van het publiek](../features/addressable-audiences.md) (klant- en segment-vlakke gegevens).
* De [Totale metrische apparaten](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) voor een [!UICONTROL Profile Merge Rule].
