---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences Overview
solution: Audience Manager
title: Predictieve doelgroepen in Audience Manager
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1485'
ht-degree: 7%

---

# [!UICONTROL Predictive Audiences] Overzicht {#predictive-audiences}

[!UICONTROL Predictive Audiences] kunt u een onbekend publiek in real-time in verschillende personen classificeren met behulp van geavanceerde technieken voor gegevenswetenschap.

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

In een marketingcontext is een persona een doelgroepsegment dat wordt gedefinieerd door bezoekers, gebruikers of potentiële kopers die een specifieke reeks kenmerken delen zoals demografie, browsegewoonten, koopgeschiedenis, enz.

[!UICONTROL Predictive Audiences]-modellen gaan met dit concept een stap verder: hiermee kunt u de Audience Manager-mogelijkheden voor machine learning gebruiken om onbekende doelgroepen te classificeren als verschillende persona&#39;s. Audience Manager helpt u hierbij door de neigingen van uw onbekende eigen doelgroep te berekenen voor een reeks bekende eigen doelgroepen.

Wanneer u een [!UICONTROL Predictive Audiences] model, de eerste stap is het kiezen van de basislijneigenschappen of de segmenten die u uw doelpubliek wilt worden geclassificeerd door. Met deze kenmerken of segmenten worden uw persona&#39;s gedefinieerd.

Tijdens de evaluatiefase creëert het model een nieuwe [!UICONTROL Predictive Audiences] segment voor elk kenmerk of segment dat u als basislijn hebt gedefinieerd. De volgende keer dat de Audience Manager een bezoeker van uw doelpubliek ziet die niet geclassificeerd is voor een persona (kwalificeerde niet voor om het even welk van uw basislijnkenmerken of segmenten), [!UICONTROL Predictive Audiences] het model zal bepalen tot welke van de vooruitlopende segmenten de bezoeker zou moeten behoren, en de bezoeker aan dat segment toevoegen.

U kunt de voorspelbare segmenten identificeren die door het model worden gecreeerd, in [!UICONTROL Segments] pagina. Elk [!UICONTROL Predictive Audiences] model heeft een eigen map onder [!UICONTROL Predictive Audiences] en u kunt de segmenten van elk model zien door op de modelmap te klikken.

![voorspellend publiek-segmenten](assets/predictive-audiences-segments.png)

## Gevallen gebruiken {#use-cases}

Om u te helpen beter begrijpen hoe en wanneer u kon gebruiken [!UICONTROL Predictive Audiences], hier zijn een paar gebruiksgevallen die de klanten van de Audience Manager kunnen oplossen door deze eigenschap te gebruiken.

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

### Hoofdletters en kleine letters gebruiken #6

Als mediabedrijf wil ik mijn publiek categoriseren, zodat ik mijn advertentieruimte tegen een hoge prijs kan verkopen en mijn bezoekers relevante advertenties kan aanbieden.

## Hoe [!UICONTROL Predictive Audiences] Modellen werken {#how-predictive-audiences-models-work}

Wanneer u een [!UICONTROL Predictive Audiences] model, gaat u door drie stappen:

1. Eerst selecteert u minimaal twee kenmerken of twee segmenten die uw persona&#39;s definiëren.
1. Vervolgens kiest u een kenmerk of segment dat het doelpubliek definieert dat u wilt classificeren.
1. Tot slot kiest u een naam voor het model, een gegevensbron die de vooruitlopende segmenten, en zal opslaan [!UICONTROL Profile Merge Rule] voor het model.

### Selectiecriteria voor personeel {#selection-personas}

U kunt om het even welk van uw eerstepartijeigenschappen of segmenten kiezen om uw karakters te bepalen. Voor optimale resultaten is er echter een set aanbevolen aanbevolen procedures:

* Kies uw persoonlijke kenmerken of segmenten zodat elke persoon minstens een paar honderd personen heeft [apparaat-id&#39;s](../../reference/ids-in-aam.md).
* Als uw kenmerken zijn gebaseerd op [apparaat-id&#39;s](../../reference/ids-in-aam.md), kunt u deze in segmenten laten omlopen [Regels voor samenvoegen van profielen](../profile-merge-rules/merge-rules-overview.md) die [apparaat-id&#39;s](../../reference/ids-in-aam.md), zoals [!UICONTROL Device Graph]. Dit zal ervoor zorgen dat er voldoende [apparaat-id&#39;s](../../reference/ids-in-aam.md) dat het algoritme van kan leren.
* Wij adviseren het kiezen van eigenschappen of eenvoudige segmenten voor uw persona&#39;s, die uit 1 tot 3 eigenschappen bestaan.
* Kies basislijnkenmerken of segmenten met minimale overlapping.
* Zorg ervoor dat u granulaire kenmerken vastlegt over de digitale eigenschappen.

### Selectiecriteria voor doelgroep {#selection-audience}

Afhankelijk van uw gebruiksgeval, of u gebruikers in real time, in partij, of allebei wilt classificeren, kies een doelpubliek ([!UICONTROL trait] of [!UICONTROL segment]) met een aanzienlijke reële en/of totale bevolking. Net als voor persoonlijke selectie raden we je doelgroep aan [!UICONTROL trait] of [!UICONTROL segment] heeft gebruikers met rijke profielen (rijke reeksen van [!UICONTROL traits]).

Wanneer het selecteren van het doelpubliek, analyseer uw gebruiksgeval en besluit welke types van identiteitskaarts u wilt classificeren: [!UICONTROL device IDs] of [!UICONTROL cross-device IDs]. De [!UICONTROL Profile Merge Rule] die u bij het maken van het model selecteert, definieert de gegevens die worden gebruikt om elke gebruiker in de voorspelling te plaatsen [!UICONTROL segments].

We raden u aan een [!UICONTROL Profile Merge Rule] die dezelfde configuratie heeft als uw doelpubliek [!UICONTROL Profile Merge Rule]of een profiel dat het profieltype (apparaatprofiel of geverifieerd profiel) van de doelgroep bevat.

### [!UICONTROL Predictive Audiences] Modeltrainingsfase {#model-training}

Voordat het algoritme je publiek van de eerste partij in de juiste persona&#39;s kan indelen, moet het zichzelf op de gegevens trainen.

Voor elke persoon die u definieert, analyseert het algoritme zijn respectieve publiek en evalueert het elke activiteit in real time en/of ongeboekt trait voor zijn gebruikers in de laatste 30 dagen.
Deze stap vindt om de 24 uur plaats om rekening te houden met wijzigingen in uw eerstepartijpubliek.

### [!UICONTROL Predictive Audiences] Modelindelingsfase {#model-classification}

Voor publieksclassificatie in real time en batch, controleert het model eerst of een gebruiker tot het doelpubliek behoort. Als de gebruiker voor het doelpubliek kwalificeert en niet tot om het even welke persona&#39;s behoort, wijst het model hen een persona kwalificatiescore toe.

Bij het evalueren van het eerste publiek en het toewijzen van scores, gebruikt het model het gebrek **[!UICONTROL Profile Merge Rule]** gedefinieerd in uw account. Tot slot wordt de bezoeker geclassificeerd in de persoon waarvoor hij de hoogste score heeft ontvangen.

![voorspellend publiek-grafiek](assets/predictive-audiences-graph.png)

## Overwegingen en beperkingen {#considerations}

>[!IMPORTANT]
> Lees deze sectie zorgvuldig door voordat u verdergaat met de implementatiefase.

Wanneer u uw [!UICONTROL Predictive Audiences] de modellen, houd rekening met de volgende overwegingen en beperkingen:

* U kunt maximaal tien [!UICONTROL Predictive Audiences]-modellen maken.
* Voor elk model kunt u maximaal 50 basiskenmerken/segmenten kiezen.
* Gegevens van de tweede en derde partij worden momenteel niet ondersteund in [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] voert publieksclassificatie uit die op uw eerste partijeigenschappen, van al uw eerste-partijgegevensbronnen wordt gebaseerd.
* Segmentbeoordeling voor [!UICONTROL Predictive Audiences] gebruikt de **[!UICONTROL Profile Merge Rule]** die u kiest tijdens het maken van het model. Meer informatie over [!UICONTROL Profile Merge Rules] zie de toegewijde [documentatie](../profile-merge-rules/merge-rules-overview.md).
* Sommige kenmerken en segmenten worden niet ondersteund als basislijnen of doelgroepen. [!UICONTROL Predictive Audiences] modellen kunnen niet worden opgeslagen wanneer u een van de volgende opties kiest als basislijn of doelpubliek:
   * voorspellende kenmerken en segmenten die met voorspellende kenmerken zijn gecreëerd;
   * [Adobe Experience Platform](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) kenmerken of segmenten;
   * Algoritmische kenmerken;
   * Tweede en derdekenmerken.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] kan niet worden gebruikt in [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

Voorspelende segmenten gemaakt door [!UICONTROL Predictive Audiences] modellen nemen de [Besturingselementen voor gegevensexport](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=nl-NL) uit de volgende bronnen van eerstepartijgegevens:

1. De eerste gegevensbron die u kiest bij het bouwen van het model.
1. De gegevensbronnen van de eerste partij van uw doelpubliek. Met name de controle op de uitvoer van gegevens van de [!UICONTROL traits] of [!UICONTROL segments] die uw doelgroep vormen.
1. De [Besturingselementen voor gegevensexport](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=nl-NL) van de [!UICONTROL Profile Merge Rule] die u voor het model hebt geselecteerd.

De nieuwe voorspellingen [!UICONTROL traits] en [!UICONTROL segments] dezelfde privacybeperkingen zullen hebben als de samenvoeging van de hierboven beschreven bronnen met gegevens van de eerste partij.

Handgrepen met aanvullende beperkingen die geen deel uitmaken van de [!UICONTROL Predictive Audiences] de beperkingen op de privacy van segmenten zullen van de opleidingsfase worden uitgesloten en zullen niet van invloed worden op het model .

## [!UICONTROL Profile Merge Rules] {#pmr}

Alle vooruitlopende segmenten worden toegewezen aan de [!UICONTROL Profile Merge Rule] die u hebt geselecteerd bij het maken van het model. De [!UICONTROL Profile Merge Rule] die u kiest, is om de volgende redenen belangrijk:

* Daarin wordt bepaald met welke apparaten en/of geverifieerde profielen rekening moet worden gehouden wanneer het model de invloedrijke [!UICONTROL traits], op het moment dat een gebruiker wordt geclassificeerd als een voorspelbare gebruiker [!UICONTROL segment].
* Het bepaalt welke [!UICONTROL trait] typen (apparaatniveau of niveau tussen apparaten) moeten tijdens de modelopleiding worden gebruikt en als invloedrijk worden beschouwd [!UICONTROL traits]. Predictief [!UICONTROL segments] Dit zijn subsets van uw doelpubliek.
   * Als het doelpubliek een segment is, raden we u aan hetzelfde te selecteren [!UICONTROL Profile Merge Rule] voor het model als model dat is toegewezen aan uw doelpubliek, of een [!UICONTROL Profile Merge Rule] dat het profieltype van uw doelpubliek omvat.
   * Als het doelpubliek een [!UICONTROL trait]We raden u aan een [!UICONTROL Profile Merge Rule] die toegang hebben tot hetzelfde type gegevens als de doeldoelgroep (apparaatprofielgegevens of apparaatprofielgegevens).
* [!UICONTROL Profile Merge Rules] met de [!UICONTROL Current Authenticated Profiles] en [!UICONTROL No Device Profile] worden alleen ondersteund voor publieksclassificatie in realtime. Zie voor meer informatie [Opties voor regels voor het samenvoegen van profielen gedefinieerd](../profile-merge-rules/merge-rule-definitions.md).

Een [!UICONTROL Profile Merge Rule] dat zowel apparaatgegevens als apparaatgegevens gebruikt, maximaliseert het aantal [!UICONTROL traits] die kunnen worden gebruikt voor modeltraining en gebruikersclassificatie in de voorspellende [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

De kenmerken en segmenten die u kiest voor persona&#39;s en publieksclassificatie zijn onderhevig aan Audience Manager [Op rollen gebaseerde toegangscontroles](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html?lang=nl-NL).

Gebruikers van Audience Managers kunnen alleen sporen of segmenten voor personen en doelgroepen selecteren die ze hebben [machtiging om te bekijken](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html?lang=nl-NL#wild-card-permissions).
