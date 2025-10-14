---
description: De detailspagina voor een individueel bezit verstrekt overzicht van informatie zoals de het handelsnaam, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit bepalen, segmenten het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar Audience Data > Traits en klikt u op de naam van het kenmerk waarmee u wilt werken.
seo-description: The details page for an individual trait provides overview of information like the trait name, ID, performance metrics, expressions that define the trait, segments it belongs to, and the trait audit log. To vew these details, go to Audience Data > Traits and click the name of the trait you want to work with.
seo-title: Trait Details Page
solution: Audience Manager
title: Detailpagina van taak
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: Onderverdeling van identiteitstype, identiteitsonderbreking, publieksidentificatierapportage, apparaatoverschrijdende id, apparaat-id
feature: Traits
exl-id: c0b4791f-885e-4b14-b7e8-3c2d618fb80e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '616'
ht-degree: 0%

---

# [!UICONTROL Trait] Detailpagina {#trait-details-page}

De detailpagina voor een individu [!UICONTROL trait] biedt een overzicht van de [!UICONTROL trait] -details, zoals de [!UICONTROL trait] naam, id, prestatiewaarden, expressies die de [!UICONTROL trait] definiëren, segmenten waartoe het behoort en het [!UICONTROL trait] controlelogboek. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** en klik op de naam van de [!UICONTROL trait] waarmee u wilt werken.

## [!UICONTROL Trait] Hulpprogramma&#39;s voor beheer {#trait-management-tools}

Boven aan de pagina met details van [!UICONTROL trait] staan de gereedschappen die u kunt gebruiken om uw [!UICONTROL traits] te beheren:

1. **[!UICONTROL Add New]**: Gebruik deze optie om nieuwe [!UICONTROL rule-based] , [!UICONTROL algorithmic] of [!UICONTROL onboarded traits] te maken.
2. **[!UICONTROL Edit]**: Gebruik deze optie om de configuratie van de huidige [!UICONTROL trait] te wijzigen.
3. **[!UICONTROL Delete]**: Gebruik deze optie om de huidige [!UICONTROL trait] uit uw Audience Manager-account te verwijderen.
4. **[!UICONTROL Marketplace Recommendations]**: met deze optie lijkt [!UICONTROL traits] op de optie die u bekijkt, aan de hand van [!UICONTROL Audience Marketplace] gegevenskosten waarop u niet bent geabonneerd. Zie [&#x200B; Audience Marketplace voor de Kopers van Gegevens &#x200B;](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) leren hoe te om [!UICONTROL Marketplace] te navigeren en gelijkaardige eigenschappen te vinden.

![&#x200B; basis-eigenschap-informatie &#x200B;](assets/basic-trait-information.png)

## [!UICONTROL Trait] Informatie {#basics}

In de sectie [!UICONTROL Trait Information] vindt u meer informatie over de vereiste en optionele velden die u hebt ingevuld bij het maken van de [!UICONTROL trait] -pagina. Dit zijn onder andere het type [!UICONTROL trait] , [!UICONTROL trait] ID, description [!UICONTROL data source] en andere metagegevens. Deze details variëren afhankelijk van [!UICONTROL trait] type ([!UICONTROL folder], [!UICONTROL onboarded], of [!UICONTROL rule-based]).

## [!UICONTROL Trait Graph] {#trait-graph}

[!UICONTROL Trait Graph] verstrekt prestaties in één oogopslag metriek voor uw geselecteerde [!UICONTROL trait]. Houd de cursor boven een trendlijn om aanvullende gegevens voor de geselecteerde [!UICONTROL trait] weer te geven.

[!UICONTROL Unique Trait Realizations] geeft een aantal unieke gebruikers aan die dit [!UICONTROL trait] binnen het opgegeven tijdbereik aan hun profiel hebben toegevoegd. De instructie [!UICONTROL Total Trait Population] geeft het aantal unieke gebruikers aan dat momenteel voor dit [!UICONTROL trait] in aanmerking komt.

Voor [!UICONTROL rule-based traits] vindt [!UICONTROL trait] -kwalificatie plaats in realtime, aangezien gebruikers in aanmerking komen voor een [!UICONTROL trait] -kwalificatie in hun browser.

Voor [!UICONTROL onboarded traits], [!UICONTROL trait] gebeurt de kwalificatie nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier wordt [&#x200B; gevoederd in Audience Manager &#x200B;](../../faq/faq-inbound-data-ingestion.md) en dat is wanneer de [!UICONTROL trait] kwalificatie gebeurt.

In [!UICONTROL Trait Graph] ziet u de volgende informatie:

* **[!UICONTROL Show results by]**
   * **[!UICONTROL Cross-Device ID]**: selecteer deze optie om de resultaten weer te geven voor [!UICONTROL traits] die gegevens verzamelen voor geverifieerde profielen. Wanneer u deze optie selecteert, ziet u alleen gegevens in het [!UICONTROL Cross-Device ID] -rapport en zijn er geen gegevens aanwezig in het [!UICONTROL Device ID] -rapport.
   * **[!UICONTROL Device ID]**: selecteer deze optie om de resultaten te bekijken voor [!UICONTROL traits] die gegevens verzamelen voor apparaatprofielen. Wanneer u deze optie selecteert, ziet u alleen gegevens in het [!UICONTROL Device ID] -rapport en zijn er geen gegevens aanwezig in het [!UICONTROL Cross-Device ID] -rapport.

     ![&#x200B; lijn-grafiek &#x200B;](assets/trait-summary.gif)

* **[!UICONTROL Unique Trait Realizations]**: Een aantal unieke gebruikers die dit [!UICONTROL trait] binnen het opgegeven tijdbereik aan hun profiel hebben toegevoegd.
* **[!UICONTROL Total Trait Population]**: Het aantal unieke gebruikers dat momenteel voor dit [!UICONTROL trait] in aanmerking komt.

* **[!UICONTROL Identity Type Breakdown]**: De eerste drie vermeldingen tonen de bovenste drie [!UICONTROL cross-device data sources] met het hoogste aantal inwoners dat in aflopende volgorde voor de [!UICONTROL trait] is gekwalificeerd. De vierde vermelding toont de som van alle andere [!DNL DPUUIDs] ([!DNL CRM IDs]) die in aanmerking komen voor de [!UICONTROL trait] , van de [!UICONTROL cross-device data sources] die niet in de bovenste drie voorkomen. Dit rapport wordt alleen weergegeven als u [!UICONTROL Cross-device ID] selecteert in het vervolgkeuzemenu [!UICONTROL Show Results By] rechtsboven op de pagina. De standaardoptie voor de vervolgkeuzelijst is [!UICONTROL Device ID] , waarbij dit rapport niet wordt weergegeven.

  ![&#x200B; lijn-grafiek &#x200B;](assets/trait-identity.png)

  >[!NOTE]
  >
  >Audience Manager geeft het [!UICONTROL Identity Type Breakdown] -rapport alleen weer als u [!UICONTROL cross-device] ID&#39;s hebt die in aanmerking komen voor de [!UICONTROL trait] .

  >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## [!UICONTROL Trait] Uitdrukking {#trait-expression}

In de sectie [!UICONTROL Trait Expression] ziet u de criteria waaraan gebruikers moeten voldoen om in aanmerking te komen voor de [!UICONTROL trait] . Deze regels worden geplaatst wanneer u [&#x200B; creeert of een spoor &#x200B;](../../features/traits/about-trait-builder.md) uitgeeft.

![](assets/traitExpression.png)

## [!UICONTROL Trait] Segmenten {#trait-segments}

In de sectie [!UICONTROL Segments with this Trait] worden alle segmenten weergegeven waartoe de geselecteerde [!UICONTROL trait] behoort. U kunt op een segmentnaam klikken om details over dat segment te zien.

![](assets/traitSegments.png)

## [!UICONTROL Trait] Logboek voor controle/historie {#trait-audit-history}

Voor [!UICONTROL rule-based] en [!UICONTROL onboarded traits] toont [!UICONTROL Trait Expression Change History] u de laatste 10 wijzigingen die in [!UICONTROL trait] -expressieregels zijn aangebracht en door wie. Als uw [!UICONTROL trait] meer dan 10 veranderingen heeft, klik **[!UICONTROL Export to CSV]** om het volledige controlelogboek te downloaden. Het auditlogboek is niet beschikbaar voor [!UICONTROL folder] of [!UICONTROL algorithmic traits] .

>[!NOTE]
>
>[!UICONTROL Not Available] in de kolom [!UICONTROL By User] betekent dat de account voor die gebruiker is verwijderd.

![](assets/traitHistory.png)
