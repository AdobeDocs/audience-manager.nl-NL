---
description: Met voorspellende doelgroepen kunt u een onbekend publiek in real-time in verschillende personen indelen met behulp van gegevenswetenschap.
seo-description: Met voorspellende doelgroepen kunt u een onbekend publiek in real-time in verschillende personen indelen met behulp van gegevenswetenschap.
seo-title: Overzicht van voorspellende doelgroepen
solution: Audience Manager
title: Audience Manager voorspellend publiek
translation-type: tm+mt
source-git-commit: ef098c35da49ae663d201b9b7f96034fb5c76323
workflow-type: tm+mt
source-wordcount: '1261'
ht-degree: 0%

---


# [!UICONTROL Predictive Audiences] Overzicht {#predictive-audiences}

[!UICONTROL Predictive Audiences] kunt u een onbekend publiek in real-time in verschillende personen classificeren met behulp van geavanceerde technieken voor gegevenswetenschap.

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

In een marketingcontext is een persoon een publiekssegment dat wordt gedefinieerd door bezoekers, gebruikers of potentiële kopers en dat een specifieke reeks kenmerken deelt, zoals demografie, bruisende gewoonten, winkelgeschiedenis, enz.

[!UICONTROL Predictive Audiences] modellen zetten dit concept een stap verder door u in staat te stellen de computer leermogelijkheden van de Audience Manager te gebruiken om onbekend publiek in verschillende personen te classificeren. Audience Manager helpt u dit te bereiken door de neiging van uw onbekend publiek van de eerste partij voor een reeks bekende eerstepartijpubliek te berekenen.

Wanneer u een [!UICONTROL Predictive Audiences] model creeert, de eerste stap de basislijnkenmerken of de segmenten kiest die u uw doelpubliek wilt worden geclassificeerd door. Met deze kenmerken of segmenten worden uw persona&#39;s gedefinieerd.

Tijdens de evaluatiefase, leidt het model tot een nieuw [!UICONTROL Predictive Audiences] segment voor elk bezit of segment dat u als basislijn bepaalde. De volgende keer dat de Audience Manager een bezoeker van uw doelpubliek ziet die niet voor een persoon (kwalificeerde niet voor om het even welk van uw basislijnkenmerken of segmenten) wordt geclassificeerd, zal het [!UICONTROL Predictive Audiences] model bepalen tot welke van de vooruitlopende segmenten de bezoeker zou moeten behoren, en zal de bezoeker aan dat segment toevoegen.

U kunt de voorspellende segmenten identificeren die door het model, in de [!UICONTROL Segments] pagina worden gecreeerd. Elk [!UICONTROL Predictive Audiences] model heeft zijn eigen omslag onder de [!UICONTROL Predictive Audiences] omslag, en u kunt de segmenten van elk model zien door de modelomslag te klikken.

![voorspellend publiek-segmenten](assets/predictive-audiences-segments.png)

## Gevallen gebruiken {#use-cases}

Om u beter te helpen begrijpen hoe en wanneer u kon gebruiken [!UICONTROL Predictive Audiences], zijn hier een paar gebruiksgevallen die de klanten van de Audience Manager door deze eigenschap kunnen oplossen.

### Hoofdletters en kleine letters gebruiken 1

Als een marketeer in een e-commercebedrijf, wil ik al mijn Web en mobiele bezoekers in diverse merkaffiniteitscategorieën classificeren, zodat ik hun gebruikerservaring kan personaliseren.

### Hoofdletters en kleine letters gebruiken 2

Als een marketeer in een mediabedrijf wil ik mijn ongeautoriseerde web- en mobiele bezoekers classificeren met favoriete genres, zodat ik ze gepersonaliseerde inhoud op alle kanalen kan voorstellen.

### Hoofdletters gebruiken #3

Als adverteerder voor een luchtvaartmaatschappij wil ik ervoor zorgen dat ik mijn publiek classificeer op basis van hun interesse in reisbestemmingen, zodat ik ze in real time kan adverteren, binnen een kort herrichtingsvenster.

### Hoofdletters gebruiken #4

Als adverteerder wil ik mijn eerste-partijpubliek in real-time classificeren, zodat ik snel kan reageren op trending news.

### Hoofdletters en kleine letters gebruiken 5

Als marketeer wil ik voorspellen in welke reisfase mijn websitebezoekers verkeren, zoals detectie, betrokkenheid, aankoop of retentie, zodat ik hen dienovereenkomstig kan richten.

### Hoofdletters gebruiken #6

Als mediabedrijf wil ik mijn publiek categoriseren, zodat ik mijn advertentieruimte tegen een hoge prijs kan verkopen en mijn bezoekers relevante advertenties kan aanbieden.

## Hoe [!UICONTROL Predictive Audiences] Modellen werken {#how-predictive-audiences-models-work}

Wanneer u een [!UICONTROL Predictive Audiences] model creeert, gaat u door drie stappen:

1. Eerst selecteert u minimaal twee kenmerken of twee segmenten die uw persona&#39;s definiëren.
1. Vervolgens kiest u een kenmerk of segment dat het doelpubliek definieert dat u wilt classificeren.
1. Tot slot kiest u een naam voor het model en selecteert u een gegevensbron die de voorspellende segmenten opslaat.

### Selectiecriteria voor personeel {#selection-personas}

U kunt om het even welk van uw eerstepartijeigenschappen of segmenten kiezen om uw karakters te bepalen. Voor optimale resultaten is er echter een set aanbevolen aanbevolen procedures:

* Kies uw persoonlijke kenmerken of segmenten zodat elke persoon minstens een paar honderd [apparaat-id&#39;s heeft](../../reference/ids-in-aam.md).
* Als uw eigenschappen op [cross-device IDs](../../reference/ids-in-aam.md)gebaseerd zijn, kunt u hen in segmenten met de Regels [van de Fusie van het](../profile-merge-rules/merge-rules-overview.md) Profiel verpakken die [apparaat IDs](../../reference/ids-in-aam.md), zoals [!UICONTROL Device Graph]. gebruiken. Dit zal ervoor zorgen er genoeg [apparaat IDs](../../reference/ids-in-aam.md) zijn dat het algoritme van kan leren.
* Wij adviseren het kiezen van eigenschappen of eenvoudige segmenten voor uw personen, die uit 1 tot 3 eigenschappen bestaan.
* Kies basislijnkenmerken of segmenten met minimale overlapping.
* Zorg ervoor dat u granulaire kenmerken vastlegt over de digitale eigenschappen.

### Selectiecriteria voor de Target-doelgroep {#selection-audience}

Net als een persoonlijke selectie moet u uw kenmerk of segment kiezen dat het doelpubliek zo definieert dat het realtime gebruikers met rijke sets kenmerken heeft, zodat het kan worden ingedeeld in de juiste persoon.

### [!UICONTROL Predictive Audiences] Modeltrainingsfase {#model-training}

Voordat het algoritme je publiek van de eerste partij in de juiste persona&#39;s kan indelen, moet het zichzelf op de gegevens trainen.

Voor elke persoon die u definieert, analyseert het algoritme zijn respectieve publiek en evalueert het elke activiteit in real time en/of ongeboekt trait voor zijn gebruikers in de laatste 30 dagen.
Deze stap vindt om de 24 uur plaats om rekening te houden met wijzigingen in uw eerstepartijpubliek.

### [!UICONTROL Predictive Audiences] Modelindelingsfase {#model-classification}

Wanneer een bezoeker die deel uitmaakt van het doelpubliek in real time wordt gezien, evalueert het model of de bezoeker deel van de bepaalde karakters uitmaakt. Voor elke bezoeker die niet bij een van de personen hoort, wijst het model een kwalificatiescore voor personen toe.

Bij het evalueren van het publiek van de eerste partij en het toewijzen van scores, gebruikt het model de standaard **[!UICONTROL Profile Merge Rule]** die in uw account is gedefinieerd. Tot slot wordt de bezoeker geclassificeerd in de persoon waarvoor hij de hoogste score heeft ontvangen.

![voorspellend publiek-grafiek](assets/predictive-audiences-graph.png)

## Overwegingen en beperkingen {#considerations}

>[!IMPORTANT]
> Lees deze sectie zorgvuldig door voordat u verdergaat met de implementatiefase.

Houd bij het configureren van uw [!UICONTROL Predictive Audiences] modellen rekening met de volgende overwegingen en beperkingen:

* U kunt maximaal 10 [!UICONTROL Predictive Audiences] modellen maken.
* Voor elk model kunt u maximaal 50 basiskenmerken/segmenten kiezen.
* Gegevens van derden en derden worden momenteel niet ondersteund in [!UICONTROL Predictive Audiences].
* De classificatie van het publiek wordt gedaan slechts voor echt - tijd eerste-partijpubliek. In een toekomstige update wordt mogelijk ondersteuning geboden voor gebruikers met de classificatie van eerste partijen aan boord.
   >[!IMPORTANT]
   > Momenteel, wordt de [!UICONTROL Total Segment Population] van uw vooruitlopende segmenten getoond als 0, en de [Uitgaande Overdrachten](../../integration/receiving-audience-data/batch-outbound-transfers/batch-outbound-overview.md) van Gegevens van de Partij worden niet gesteund voor [!UICONTROL Predictive Audiences]. Dit gedrag verandert in een toekomstige update.
* [!UICONTROL Predictive Audiences] voert publieksclassificatie uit die op uw eerste partijeigenschappen, van al uw eerste-partijgegevensbronnen wordt gebaseerd.
* De evaluatie van het segment voor [!UICONTROL Predictive Audiences] gebruikt het gebrek **[!UICONTROL Profile Merge Rule]** dat u in uw rekening bepaalde. Meer informatie over [!UICONTROL Profile Merge Rules] zie de specifieke [documentatie](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/profile-merge-rules/merge-rules-overview.html).
* Sommige kenmerken en segmenten worden niet ondersteund als basislijnen of doelgroepen. [!UICONTROL Predictive Audiences] modellen kunnen niet worden opgeslagen wanneer u een van de volgende opties kiest als basislijn of doelpubliek:
   * voorspellende kenmerken en segmenten die met voorspellende kenmerken zijn gecreëerd;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) -kenmerken of -segmenten;
   * Algoritmische kenmerken;
   * Tweede en derdekenmerken.

## [!UICONTROL Data Export Controls] {#dec}

De voorspellende segmenten die door [!UICONTROL Predictive Audiences] modellen worden gecreeerd erven de Controles [van de Uitvoer van](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-export-controls.html) Gegevens van de volgende eerste gegevensbronnen:

1. De eerste gegevensbron die u kiest bij het bouwen van het model.
1. De gegevensbronnen van de eerste partij van uw doelpubliek. Specifiek, de controles van de gegevensuitvoer van de eigenschappen of de segmenten die omhoog uw doelpubliek maken.

De nieuwe voorspellende kenmerken en segmenten zullen dezelfde privacybeperkingen hebben als de samenvoeging van de hierboven beschreven bronnen van de eerste partij.

Traits die aanvullende beperkingen hebben die geen deel uitmaken van de privacybeperkingen voor [!UICONTROL Predictive Audiences] segmenten, worden uitgesloten van de trainingsfase en zullen niet van invloed worden op het model.

## [!UICONTROL Role-Based Access Controls] {#rbac}

De eigenschappen en de segmenten die u voor persona&#39;s en publieksclassificatie kiest zijn onderworpen aan Audience Manager op [Rol-Gebaseerde Controles](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html)van de Toegang.

Gebruikers van Audience Managers kunnen alleen sporen of segmenten voor personen en doelgroepen selecteren, die ze [mogen bekijken](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions).
