---
description: De detailspagina voor een individueel bezit verstrekt overzicht van informatie zoals de het handelsnaam, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit bepalen, segmenten het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar Audience Data > Traits en klikt u op de naam van het kenmerk waarmee u wilt werken.
seo-description: De detailspagina voor een individueel bezit verstrekt overzicht van informatie zoals de het handelsnaam, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit bepalen, segmenten het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar Audience Data > Traits en klikt u op de naam van het kenmerk waarmee u wilt werken.
seo-title: Detailpagina Trait
solution: Audience Manager
title: Detailpagina Trait
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting, cross-device, cross-device ID, device ID
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '657'
ht-degree: 0%

---


# [!UICONTROL Trait] Detailpagina {#trait-details-page}

De detailspagina voor een individu [!UICONTROL trait] verstrekt een overzicht van de [!UICONTROL trait] details, zoals de [!UICONTROL trait] naam, identiteitskaart, prestatiesmetriek, uitdrukkingen die de [!UICONTROL trait], de segmenten bepalen het tot, en het [!UICONTROL trait] controlelogboek behoort. Als u deze details wilt weergeven, gaat u naar **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** en klikt u op de naam van het bestand [!UICONTROL trait] waarmee u wilt werken.

## [!UICONTROL Trait] Beheertools {#trait-management-tools}

Boven aan de pagina met [!UICONTROL trait] details staan de gereedschappen die u kunt gebruiken om uw [!UICONTROL traits]:

1. **[!UICONTROL Add New]**: Gebruik deze optie om nieuwe [!UICONTROL rule-based], [!UICONTROL algorithmic]of [!UICONTROL onboarded traits]te creëren.
2. **[!UICONTROL Edit]**: Gebruik deze optie om de configuratie van de huidige [!UICONTROL trait]te wijzigen.
3. **[!UICONTROL Delete]**: Gebruik deze optie om de huidige versie [!UICONTROL trait] van uw Audience Manager-account te verwijderen.
4. **[!UICONTROL Marketplace Recommendations]**: Met deze optie kunt u vinden wat vergelijkbaar is [!UICONTROL traits] met de optie die u bekijkt, aan [!UICONTROL Audience Marketplace] gegevenskosten waarop u geen abonnement hebt. Zie [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) om te leren hoe u door de objecten kunt navigeren [!UICONTROL Marketplace] en vergelijkbare kenmerken kunt vinden.

![basisinformatie](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informatie {#basics}

In de [!UICONTROL Trait Information] sectie ziet u details over vereiste en optionele velden die u hebt ingevuld bij het maken van de [!UICONTROL trait]sectie. Dit omvat zaken zoals het [!UICONTROL trait] type, [!UICONTROL trait] identiteitskaart, beschrijving, [!UICONTROL data source]en andere meta-gegevens. Deze details variëren afhankelijk van [!UICONTROL trait] type ([!UICONTROL folder], [!UICONTROL onboarded], of [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

Het [!UICONTROL Trait Graph] biedt in één oogopslag prestatiemetriek voor uw geselecteerde toepassing [!UICONTROL trait]. Houd de cursor boven een trendlijn om aanvullende gegevens voor de geselecteerde code weer te geven [!UICONTROL trait].

[!UICONTROL Unique Trait Realizations] Hiermee wordt een aantal unieke gebruikers weergegeven die dit binnen het opgegeven tijdbereik aan hun profiel hebben toegevoegd. [!UICONTROL trait] Het [!UICONTROL Total Trait Population] geeft het aantal unieke gebruikers aan dat momenteel hiervoor in aanmerking komt [!UICONTROL trait].

De kwalificatie vindt bijvoorbeeld plaats in real-time, omdat gebruikers in aanmerking komen voor een kwalificatie [!UICONTROL rule-based traits][!UICONTROL trait] [!UICONTROL trait] in hun browser.

Bijvoorbeeld, [!UICONTROL onboarded traits]gebeurt de kwalificatie nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier wordt [!UICONTROL trait] gevoerd in Audience Manager [en dat is wanneer de](../../faq/faq-inbound-data-ingestion.md) [!UICONTROL trait] kwalificatie gebeurt.

In dit [!UICONTROL Trait Graph] venster ziet u de volgende informatie:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: Selecteer deze optie als u de resultaten wilt zien [!UICONTROL traits] die gegevens voor geverifieerde profielen verzamelen. Wanneer u deze optie selecteert, ziet u alleen gegevens in het [!UICONTROL Cross-Device ID] rapport en zijn er geen gegevens in het [!UICONTROL Device ID] rapport.
   * **[!UICONTROL Device ID]**: Selecteer deze optie als u resultaten wilt zien [!UICONTROL traits] die gegevens voor apparaatprofielen verzamelen. Wanneer u deze optie selecteert, ziet u alleen gegevens in het [!UICONTROL Device ID] rapport en zijn er geen gegevens in het [!UICONTROL Cross-Device ID] rapport.

      ![grafiek](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Een aantal unieke gebruikers die dit binnen het opgegeven tijdbereik [!UICONTROL trait] aan hun profiel hebben toegevoegd.
* **[!UICONTROL Total Trait Population]**: Het aantal unieke gebruikers dat momenteel hiervoor in aanmerking komt [!UICONTROL trait].

* **[!UICONTROL Identity Type Breakdown]**: De eerste drie items tonen de bovenste drie items [!UICONTROL cross-device data sources] met het hoogste aantal inwoners dat voor de [!UICONTROL trait]code in aflopende volgorde is gekwalificeerd. De vierde ingang toont de som alle andere [!DNL DPUUIDs] ([!DNL CRM IDs]) die voor [!UICONTROL trait], van [!UICONTROL cross-device data sources] die niet in hoogste drie kwalificeren. Dit rapport wordt alleen weergegeven als u [!UICONTROL Cross-device ID] in het [!UICONTROL Show Results By] vervolgkeuzemenu rechtsboven op de pagina selecteert. De standaardoptie drop-down is, [!UICONTROL Device ID]waar dit rapport niet wordt getoond.

   ![grafiek](assets/trait-identity.png)

   >[!NOTE]
   >
   >Audience Manager geeft het [!UICONTROL Identity Type Breakdown] rapport alleen weer als u id&#39; [!UICONTROL cross-device] s hebt gekwalificeerd voor de [!UICONTROL trait].

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Uitdrukking {#trait-expression}

In het [!UICONTROL Trait Expression] gedeelte ziet u aan welke criteria gebruikers moeten voldoen om in aanmerking te komen voor de [!UICONTROL trait]opdracht. Deze regels worden ingesteld wanneer u een kenmerk [maakt of bewerkt](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## [!UICONTROL Trait] Segmenten {#trait-segments}

In de [!UICONTROL Segments with this Trait] sectie worden alle segmenten weergegeven waartoe de geselecteerde segmenten [!UICONTROL trait] behoren. U kunt op een segmentnaam klikken om details over dat segment te zien.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Logboek voor controle/historie {#trait-audit-history}

Voor [!UICONTROL rule-based] en [!UICONTROL onboarded traits], [!UICONTROL Trait Expression Change History] toont u de laatste 10 veranderingen die in [!UICONTROL trait] uitdrukkingsregels worden aangebracht en wie hen aanbracht. Als uw [!UICONTROL trait] meer dan 10 veranderingen heeft, klik **[!UICONTROL Export to CSV]** om het volledige controlelogboek te downloaden. Het auditlogboek is niet beschikbaar voor [!UICONTROL folder] of [!UICONTROL algorithmic traits].

>[!NOTE]
>
>[!UICONTROL Not Available] in de [!UICONTROL By User] kolom betekent dat de account voor die gebruiker is verwijderd.

![](assets/traitHistory.png)