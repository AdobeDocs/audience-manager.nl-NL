---
description: De detailspagina voor een individueel bezit verstrekt overzicht van informatie zoals de het handelsnaam, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit bepalen, segmenten het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar Audience Data > Traits en klikt u op de naam van het kenmerk waarmee u wilt werken.
seo-description: De detailspagina voor een individueel bezit verstrekt overzicht van informatie zoals de het handelsnaam, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit bepalen, segmenten het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar Audience Data > Traits en klikt u op de naam van het kenmerk waarmee u wilt werken.
seo-title: Detailpagina van eigenschappen
solution: Audience Manager
title: Detailpagina van eigenschappen
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 1%

---


# [!UICONTROL Trait] Detailpagina  {#trait-details-page}

De detailpagina voor een individu [!UICONTROL trait] verstrekt een overzicht van [!UICONTROL trait] details, zoals [!UICONTROL trait] naam, identiteitskaart, prestatiesmetriek, uitdrukkingen die [!UICONTROL trait] bepalen, segmenten het tot, en [!UICONTROL trait] controlelogboek behoort. Als u deze details wilt weergeven, gaat u naar **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** en klikt u op de naam van de [!UICONTROL trait] waarmee u wilt werken.

## [!UICONTROL Trait] Beheertools  {#trait-management-tools}

Bovenaan op de detailpagina [!UICONTROL trait] staan de gereedschappen die u kunt gebruiken om uw [!UICONTROL traits] te beheren:

1. **[!UICONTROL Add New]**: Gebruik deze optie om nieuwe  [!UICONTROL rule-based],  [!UICONTROL algorithmic]of  [!UICONTROL onboarded traits]te creëren.
2. **[!UICONTROL Edit]**: Gebruik deze optie om de configuratie van de huidige  [!UICONTROL trait]te wijzigen.
3. **[!UICONTROL Delete]**: Gebruik deze optie om de huidige versie  [!UICONTROL trait] van uw Audience Manager-account te verwijderen.
4. **[!UICONTROL Marketplace Recommendations]**: Met deze optie lijkt  [!UICONTROL traits] het op wat u bekijkt, aan  [!UICONTROL Audience Marketplace] gegevenskosten waarop u zich niet hebt geabonneerd. Zie [Audience Marketplace voor Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) om te leren hoe te om [!UICONTROL Marketplace] te navigeren en gelijkaardige eigenschappen te vinden.

![basisinformatie](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informatie  {#basics}

In de sectie [!UICONTROL Trait Information] staan details over vereiste en optionele velden die u hebt voltooid bij het maken van de [!UICONTROL trait]. Dit omvat zaken zoals [!UICONTROL trait] type, [!UICONTROL trait] identiteitskaart, beschrijving, [!UICONTROL data source], en andere meta-gegevens. Deze details variëren afhankelijk van [!UICONTROL trait] type ([!UICONTROL folder], [!UICONTROL onboarded], of [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

De [!UICONTROL Trait Graph] biedt in één oogopslag prestatiemetriek voor uw geselecteerde [!UICONTROL trait]. Houd de cursor boven een trendlijn om aanvullende gegevens voor de geselecteerde [!UICONTROL trait] weer te geven.

[!UICONTROL Unique Trait Realizations] Hiermee wordt een aantal unieke gebruikers weergegeven die dit binnen het opgegeven tijdbereik  [!UICONTROL trait] aan hun profiel hebben toegevoegd. [!UICONTROL Total Trait Population] geeft het aantal unieke gebruikers aan dat momenteel voor dit [!UICONTROL trait] is gekwalificeerd.

Voor [!UICONTROL rule-based traits] gebeurt [!UICONTROL trait] kwalificatie in real time, aangezien de gebruikers voor [!UICONTROL trait] in hun browser kwalificeren.

Voor [!UICONTROL onboarded traits], [!UICONTROL trait] gebeurt de kwalificatie nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier is [input in Audience Manager](../../faq/faq-inbound-data-ingestion.md) en dat is wanneer de [!UICONTROL trait] kwalificatie gebeurt.

In [!UICONTROL Trait Graph] ziet u de volgende informatie:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Selecteer deze optie als u de resultaten wilt zien  [!UICONTROL traits] die gegevens voor geverifieerde profielen verzamelen. Wanneer u deze optie selecteert, ziet u alleen gegevens in het [!UICONTROL Cross-Device ID]-rapport en zijn er geen gegevens aanwezig in het [!UICONTROL Device ID]-rapport.
   * **[!UICONTROL Device ID]**: Selecteer deze optie als u resultaten wilt zien  [!UICONTROL traits] die gegevens voor apparaatprofielen verzamelen. Wanneer u deze optie selecteert, ziet u alleen gegevens in het [!UICONTROL Device ID]-rapport en zijn er geen gegevens aanwezig in het [!UICONTROL Cross-Device ID]-rapport.

      ![grafiek](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Een aantal unieke gebruikers die dit binnen het opgegeven tijdbereik  [!UICONTROL trait] aan hun profiel hebben toegevoegd.
* **[!UICONTROL Total Trait Population]**: Het aantal unieke gebruikers dat momenteel hiervoor in aanmerking komt  [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: De eerste drie items tonen de bovenste drie items  [!UICONTROL cross-device data sources]   [!UICONTROL trait]met het hoogste aantal inwoners dat voor de code in aanmerking is gekomen, in aflopende volgorde. De vierde ingang toont de som van alle andere [!DNL DPUUIDs] ([!DNL CRM IDs]) die voor [!UICONTROL trait], van [!UICONTROL cross-device data sources] kwalificeren die niet in top drie zijn. Dit rapport wordt alleen weergegeven als u [!UICONTROL Cross-device ID] selecteert in het vervolgkeuzemenu [!UICONTROL Show Results By] rechtsboven op de pagina. De standaarddrop-down optie is [!UICONTROL Device ID], waar dit rapport niet wordt getoond.

   ![grafiek](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager toont slechts [!UICONTROL Identity Type Breakdown] rapport als u [!UICONTROL cross-device] IDs geschikt voor [!UICONTROL trait] hebt.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Uitdrukking  {#trait-expression}

In de sectie [!UICONTROL Trait Expression] ziet u de criteria waaraan gebruikers moeten voldoen om in aanmerking te komen voor [!UICONTROL trait]. Deze regels worden geplaatst wanneer u [een eigenschap ](../../features/traits/about-trait-builder.md) creeert of uitgeeft.

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmenten {#trait-segments}

In de sectie [!UICONTROL Segments with this Trait] worden alle segmenten weergegeven waartoe de geselecteerde [!UICONTROL trait] behoort. U kunt op een segmentnaam klikken om details over dat segment te zien.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Logboek voor controle/historie  {#trait-audit-history}

Voor [!UICONTROL rule-based] en [!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History] toont u de laatste 10 veranderingen die aan [!UICONTROL trait] uitdrukkingsregels worden aangebracht en wie hen aanbracht. Als uw [!UICONTROL trait] meer dan 10 veranderingen heeft, klik **[!UICONTROL Export to CSV]** om het volledige controlelogboek te downloaden. Het auditlogboek is niet beschikbaar voor [!UICONTROL folder] of [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] in de  [!UICONTROL By User] kolom betekent dat de account voor die gebruiker is verwijderd.

![](assets/traitHistory.png)