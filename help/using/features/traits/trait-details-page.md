---
description: De detailspagina voor een individueel bezit verstrekt overzicht van informatie zoals de het handelsnaam, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit bepalen, segmenten het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar Audience Data > Traits en klikt u op de naam van het kenmerk waarmee u wilt werken.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Detailpagina van eigenschappen
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: Onderverdeling van identiteitstype, identiteitsonderbreking, publieksidentificatierapportage, apparaatoverschrijdende id, apparaat-id
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '614'
ht-degree: 0%

---

# [!UICONTROL Trait] Detailpagina {#trait-details-page}

De detailpagina voor een individu [!UICONTROL trait] geeft een overzicht van de [!UICONTROL trait] gegevens, zoals [!UICONTROL trait] naam, id, prestatiewaarden, expressies die de [!UICONTROL trait], segmenten waartoe het behoort, en de [!UICONTROL trait] auditlogboek. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** en klik op de naam van de [!UICONTROL trait] u wilt met werken.

## [!UICONTROL Trait] Beheertools {#trait-management-tools}

De bovenkant van de [!UICONTROL trait] detailpagina bevat de gereedschappen die u kunt gebruiken om uw [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Gebruik deze optie om nieuwe [!UICONTROL rule-based], [!UICONTROL algorithmic], of [!UICONTROL onboarded traits].
2. **[!UICONTROL Edit]**: Gebruik deze optie om de configuratie van de huidige [!UICONTROL trait].
3. **[!UICONTROL Delete]**: Gebruik deze optie om de huidige [!UICONTROL trait] van uw Audience Manager account.
4. **[!UICONTROL Marketplace Recommendations]**: Met deze optie kunt u vergelijkbare [!UICONTROL traits] tot de versie die u bekijkt, van [!UICONTROL Audience Marketplace] kosten voor gegevens waarop je niet bent geabonneerd. Zie [Audience Marketplace voor gegevenskopers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) om te leren hoe u door de [!UICONTROL Marketplace] en vergelijkbare kenmerken vinden.

![basisinformatie](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informatie {#basics}

De [!UICONTROL Trait Information] in dit gedeelte worden de vereiste en optionele velden weergegeven die u hebt ingevuld bij het maken van de [!UICONTROL trait]. Dit omvat onder andere de [!UICONTROL trait] type, [!UICONTROL trait] ID, beschrijving, [!UICONTROL data source]en andere metagegevens. Deze details variëren afhankelijk van [!UICONTROL trait] type ([!UICONTROL folder], [!UICONTROL onboarded], of [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

De [!UICONTROL Trait Graph] biedt in één oogopslag prestatiemetriek voor uw geselecteerde [!UICONTROL trait]. Houd de cursor boven een trendlijn om aanvullende gegevens voor de geselecteerde code weer te geven [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] een aantal unieke gebruikers vertegenwoordigen die dit hebben toegevoegd [!UICONTROL trait] naar hun profiel over het opgegeven tijdbereik. De [!UICONTROL Total Trait Population] Hiermee wordt het aantal unieke gebruikers aangegeven dat momenteel voor dit probleem in aanmerking komt [!UICONTROL trait].

Voor [!UICONTROL rule-based traits], [!UICONTROL trait] de kwalificatie gebeurt in real time, aangezien de gebruikers voor [!UICONTROL trait] in hun browser.

Voor [!UICONTROL onboarded traits], [!UICONTROL trait] kwalificatie vindt plaats nadat een binnenkomend bestand is verwerkt, d.w.z. het binnenkomende bestand is [in de Audience Manager](../../faq/faq-inbound-data-ingestion.md) en dat is wanneer [!UICONTROL trait] kwalificatie gebeurt.

De [!UICONTROL Trait Graph] geeft u de volgende informatie weer:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Selecteer deze optie als u de resultaten wilt zien voor [!UICONTROL traits] die gegevens verzamelen voor geverifieerde profielen. Wanneer u deze optie selecteert, worden alleen gegevens weergegeven op het tabblad [!UICONTROL Cross-Device ID] en er zullen geen gegevens aanwezig zijn in het kader van de [!UICONTROL Device ID] verslag.
   * **[!UICONTROL Device ID]**: Selecteer deze optie als u de resultaten wilt zien voor [!UICONTROL traits] die gegevens verzamelen voor apparaatprofielen. Wanneer u deze optie selecteert, worden alleen gegevens weergegeven op het tabblad [!UICONTROL Device ID] en er zullen geen gegevens aanwezig zijn in het kader van de [!UICONTROL Cross-Device ID] verslag.

      ![grafiek](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Een aantal unieke gebruikers die dit hebben toegevoegd [!UICONTROL trait] naar hun profiel over het opgegeven tijdbereik.
* **[!UICONTROL Total Trait Population]**: Het aantal unieke gebruikers dat momenteel hiervoor in aanmerking komt [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: De eerste drie vermeldingen tonen de bovenste drie [!UICONTROL cross-device data sources] met de hoogste bevolkingsaantallen die in aanmerking zijn gekomen voor de [!UICONTROL trait], in aflopende volgorde. De vierde vermelding geeft de som van alle andere [!DNL DPUUIDs] ([!DNL CRM IDs]) die in aanmerking kwam voor de [!UICONTROL trait]van de [!UICONTROL cross-device data sources] die niet in de bovenste drie voorkomen. Dit rapport wordt alleen weergegeven als u [!UICONTROL Cross-device ID] in de [!UICONTROL Show Results By] vervolgkeuzemenu rechtsboven op de pagina. De standaardoptie voor vervolgkeuzelijsten is [!UICONTROL Device ID], waarbij dit rapport niet wordt weergegeven.

   ![grafiek](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager geeft alleen de [!UICONTROL Identity Type Breakdown] melden als u [!UICONTROL cross-device] ID&#39;s die in aanmerking komen voor de [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Uitdrukking {#trait-expression}

De [!UICONTROL Trait Expression] in deze sectie ziet u aan welke criteria gebruikers moeten voldoen om in aanmerking te komen voor de [!UICONTROL trait]. Deze regels worden ingesteld wanneer u [een kenmerk maken of bewerken](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait]Segmenten  {#trait-segments}

De [!UICONTROL Segments with this Trait] in de sectie worden alle segmenten weergegeven die u hebt geselecteerd [!UICONTROL trait] behoort tot. U kunt op een segmentnaam klikken om details over dat segment te zien.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Logboek voor controle/historie {#trait-audit-history}

Voor [!UICONTROL rule-based] en [!UICONTROL onboarded traits]de [!UICONTROL Trait Expression Change History] toont u de laatste 10 wijzigingen die zijn aangebracht in [!UICONTROL trait] en wie ze heeft gemaakt. Als uw [!UICONTROL trait] heeft meer dan 10 wijzigingen, klikt u op **[!UICONTROL Export to CSV]** om het volledige controlelogboek te downloaden. Het auditlogboek is niet beschikbaar voor [!UICONTROL folder] of [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] in de [!UICONTROL By User] kolom betekent dat de account voor die gebruiker is verwijderd.

![](assets/traitHistory.png)
