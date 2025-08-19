---
description: Een samenvatting van de steekproefmethode die voor sommige rapporten wordt gebruikt, foutenpercentages van de steekproef, en een lijst van rapporten die informatie terugkeren die op bemonsterde gegevens wordt gebaseerd.
seo-description: A summary of the sampling methodology used for some reports, sampling error rates, and a list of reports that return information based on sampled data.
seo-title: Data Sampling and Error Rates in Selected Audience Manager Reports
solution: Audience Manager
title: Gegevensbemonstering en foutenpercentages in geselecteerde Audience Manager-rapporten
uuid: 3d8bd764-a9da-40f1-8794-54304457bb9a
feature: Reporting Reference
exl-id: 0b7f9423-0859-4fa8-926b-e4858eed2294
source-git-commit: 92e2fcb5cea6560e9288ee5f819df52e9e4768b7
workflow-type: tm+mt
source-wordcount: '449'
ht-degree: 0%

---

# Gegevensbemonstering en foutenpercentages in geselecteerde Audience Manager-rapporten{#data-sampling-and-error-rates-in-selected-audience-manager-reports}

Een samenvatting van de steekproefmethode die voor sommige rapporten wordt gebruikt, foutenpercentages van de steekproef, en een lijst van rapporten die informatie terugkeren die op bemonsterde gegevens wordt gebaseerd.

## Bemonsteringsverhouding gegevens {#data-sampling-ratio}

Sommige [!DNL Audience Manager] -rapporten geven resultaten weer op basis van een gesamplede set van de totale hoeveelheid beschikbare gegevens. De bemonsterde gegevensverhouding is 1 :54. Voor rapporten die bemonsterde gegevens gebruiken, betekent dit uw resultaten op 1 verslag van elke reeks 54 verslagen worden gebaseerd.

Deze rapporten gebruiken statistische gesamplede gegevens omdat ze een enorme hoeveelheid verwerkingskracht nodig hebben om resultaten te genereren. Bemonstering helpt een evenwicht te vinden tussen lagere computervereisten, het handhaven van systeemprestaties en het verstrekken van nauwkeurige resultaten.

<!--

## Minimum Requirements {#minimum-requirements}

>[!NOTE]
>
>The minimum requirements listed below apply to Overlap reports only.

Overlap reports ([trait-to-trait](/help/using/reporting/dynamic-reports/trait-trait-overlap-report.md), [segment-to-trait](/help/using/reporting/dynamic-reports/segment-trait-overlap-report.md), and [segment-to-segment](/help/using/reporting/dynamic-reports/segment-segment-overlap-report.md)) exclude traits and segments when they do not meet the minimum unique visitor requirements. These minimum requirements are as follows:

* Traits: 28,000 [unique trait realizations](/help/using/features/traits/trait-and-segment-qualification-reference).
* Segments: 70,000 real-time users over a 14-day period.

-->

## Foutpercentages {#error-rates}

Er kunnen fouten optreden in rapporten die overlappende gegevens genereren. Een fout wordt gedefinieerd als het percentage records dat:

* Was niet in een rapport opgenomen maar toch toegevoegd.
* Het had in een verslag moeten worden opgenomen, maar het werd weggelaten.

Het is belangrijk om op te merken dat onze tests en modellen tonen dat het foutentarief ** in een omgekeerde verhouding aan het aantal verslagen in uw gegevensreeks vermindert. Gegevenssets met veel records genereren minder fouten dan gegevenssets met een klein aantal records. Laten we deze bewering op een meer kwantitatieve manier bekijken. Zoals getoond in de volgende lijst, voor een bepaald aantal verslagen, zal 95% van uw rapportresultaten onder een specifiek foutenpercentage zijn.

| Aantal records | Foutfrequentie |
|--- |--- |
| 500 - 1.000 | 95% is lager dan een 42%-foutenpercentage. |
| 1.000 - 1.500 | 95% is lager dan een foutpercentage van 34%. |
| 10.000 - 50.000 | 95% is lager dan een foutpercentage van 14%. |
| 50.000 | 95% is lager dan een foutenpercentage van 6%. |
| 100.000 | 95% is lager dan een foutpercentage van 4%. |
| 500.000 (of meer) | 95% is lager dan een foutpercentage van 2%. |

## De methode voor het nemen van minihashmonsters gebruiken {#minhash}

Gebaseerd op de [ minihash ](https://en.wikipedia.org/wiki/MinHash) steekproefmethodologie, gebruikt Audience Manager een nieuwe methode om eigenschap en segmentschatters bovenop een Één Permutatie het gegevensschets van het Hakken van de Permutatie te berekenen. Deze nieuwe methode produceert een lagere variantie dan de standaardschatter voor gelijkenis Jaccard. Zie de volgende sectie voor de rapporten die deze methodologie gebruiken.

<!--

Some Audience Manager reports use the minhash sampling methodology to compute trait and segment overlaps and similarity scores. Audience Manager calculates the [!UICONTROL Trait Similarity Score] between two traits by computing the intersection and union in terms of the number of [!UICONTROL Unique User IDs] (UUIDs) and then divides the two. For two traits A and B, the calculation looks like this:

![jaccard-similarity](/help/using/features/segments/assets/jaccard_similarity.png)

-->

## Rapporten waarin voorbeeldgegevens worden gebruikt {#reports-using-sampled-data}

De rapporten van [!DNL Audience Manager] die statistische bemonsterde gegevens en de Minhash steekproefmethodologie gebruiken omvatten:

<!--

* [Overlap reports](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (trait-to-trait, segment-to-trait, and segment-to-segment).
* [Addressable Audience](../features/addressable-audiences.md) data (customer- and segment-level data). 
* The [Total Devices](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metric for a [!UICONTROL Profile Merge Rule].
* [Data Explorer](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) uses sampled data in the [!UICONTROL Search] tab and any [!UICONTROL Saved Searches].

Reports that use Minhash sampling methodology:

-->

| Statistische bemonstering | Methode voor het nemen van minihash |
|--- |--- |
| [ Adressable Gegevens van het publiek ](../features/addressable-audiences.md) (klant en segment-vlakke gegevens). | [ overlap rapporten ](../reporting/dynamic-reports/dynamic-reports.md#interactive-and-overlap-reports) (spoor-aan-spoor, segment-aan-spoor, en segment-aan-segment) |
| [ Totale Apparaten ](../features/profile-merge-rules/profile-link-metrics.md#merge-rule-metrics) metrisch voor a [!UICONTROL Profile Merge Rule]. | [Trait Recommendations](/help/using/features/segments/trait-recommendations.md) |
| [ Data Explorer ](../features/data-explorer/data-explorer-signals-search/data-explorer-search-pairs.md) gebruikt bemonsterde gegevens in het [!UICONTROL Search] lusje en om het even welk [!UICONTROL Saved Searches] | [ de Aanbevelingen van Audience Marketplace ](/help/using/features/audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md#finding-similar-traits) |
