---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-title: Overzicht van Predictieve doelgroepen
solution: Audience Manager
title: Predictieve doelgroepen in Audience Manager
feature: Algorithmic Models
exl-id: 57eaeb09-0e0e-4ce9-9b25-f1a27f4f35ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1505'
ht-degree: 8%

---

# [!UICONTROL Predictive Audiences] Overzicht {#predictive-audiences}

[!UICONTROL Predictive Audiences] kunt u een onbekend publiek in real-time in verschillende personen classificeren met behulp van geavanceerde technieken voor gegevenswetenschap.

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

In een marketingcontext is een persona een doelgroepsegment dat wordt gedefinieerd door bezoekers, gebruikers of potentiële kopers die een specifieke reeks kenmerken delen zoals demografie, browsegewoonten, koopgeschiedenis, enz.

[!UICONTROL Predictive Audiences]-modellen gaan met dit concept een stap verder: hiermee kunt u de Audience Manager-mogelijkheden voor machine learning gebruiken om onbekende doelgroepen te classificeren als verschillende persona&#39;s. Audience Manager helpt u hierbij door de neigingen van uw onbekende eigen doelgroep te berekenen voor een reeks bekende eigen doelgroepen.

Wanneer u een model [!UICONTROL Predictive Audiences] creeert, de eerste stap de basislijnkenmerken of de segmenten kiest die u uw doelpubliek wilt worden geclassificeerd door. Met deze kenmerken of segmenten worden uw persona&#39;s gedefinieerd.

Tijdens de evaluatiefase, leidt het model tot een nieuw [!UICONTROL Predictive Audiences] segment voor elk bezit of segment dat u als basislijn bepaalde. De volgende keer dat de Audience Manager een bezoeker van uw doelpubliek ziet die niet voor een persoon (kwalificeerde niet voor om het even welk van uw basislijnkenmerken of segmenten) wordt geclassificeerd, zal het [!UICONTROL Predictive Audiences] model bepalen tot welke van de vooruitlopende segmenten de bezoeker zou moeten behoren, en zal de bezoeker aan dat segment toevoegen.

U kunt de voorspellende segmenten identificeren die door het model, in [!UICONTROL Segments] pagina worden gecreeerd. Elk [!UICONTROL Predictive Audiences] model heeft zijn eigen omslag onder [!UICONTROL Predictive Audiences] omslag, en u kunt de segmenten van elk model zien door de modelomslag te klikken.

![voorspellend publiek-segmenten](assets/predictive-audiences-segments.png)

## Gevallen gebruiken {#use-cases}

Om u beter te helpen begrijpen hoe en wanneer u [!UICONTROL Predictive Audiences] kon gebruiken, zijn hier een paar gebruiksgevallen die de klanten van de Audience Manager door deze eigenschap kunnen oplossen.

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

Wanneer u een model [!UICONTROL Predictive Audiences] creeert, gaat u door drie stappen:

1. Eerst selecteert u minimaal twee kenmerken of twee segmenten die uw persona&#39;s definiëren.
1. Vervolgens kiest u een kenmerk of segment dat het doelpubliek definieert dat u wilt classificeren.
1. Tot slot kiest u een naam voor het model, een gegevensbron die de voorspellende segmenten zal opslaan, en [!UICONTROL Profile Merge Rule] voor het model.

### Selectiecriteria voor personeel {#selection-personas}

U kunt om het even welk van uw eerstepartijeigenschappen of segmenten kiezen om uw karakters te bepalen. Voor optimale resultaten is er echter een set aanbevolen aanbevolen procedures:

* Kies uw persoonlijke kenmerken of segmenten zodat elke persoon minstens een paar honderd [apparaat-id&#39;s](../../reference/ids-in-aam.md) heeft.
* Als uw eigenschappen op [cross-device IDs](../../reference/ids-in-aam.md) gebaseerd zijn, kunt u hen in segmenten met [de Regels van de Fusie van het Profiel](../profile-merge-rules/merge-rules-overview.md) verpakken die [apparaat IDs](../../reference/ids-in-aam.md), zoals [!UICONTROL Device Graph] gebruiken. Dit zal ervoor zorgen er genoeg [apparaat IDs](../../reference/ids-in-aam.md) zijn dat het algoritme van kan leren.
* Wij adviseren het kiezen van eigenschappen of eenvoudige segmenten voor uw persona&#39;s, die uit 1 tot 3 eigenschappen bestaan.
* Kies basislijnkenmerken of segmenten met minimale overlapping.
* Zorg ervoor dat u granulaire kenmerken vastlegt over de digitale eigenschappen.

### Selectiecriteria voor doelgroep {#selection-audience}

Afhankelijk van uw gebruiksgeval, of u gebruikers in real time, in partij, of allebei wilt classificeren, kies een doelpubliek ([!UICONTROL trait] of [!UICONTROL segment]) dat een significante real-time en/of totale bevolking heeft. Net als bij een persoonlijke selectie raden we aan dat gebruikers met rijke profielen (rijke sets [!UICONTROL traits]) voor het doelpubliek [!UICONTROL trait] of [!UICONTROL segment] staan.

Wanneer het selecteren van het doelpubliek, analyseer uw gebruiksgeval en besluit welke types van identiteitskaarts u wilt classificeren: [!UICONTROL device IDs] of [!UICONTROL cross-device IDs]. De [!UICONTROL Profile Merge Rule] die u selecteert wanneer het creëren van het model bepaalt de gegevens die zullen worden gebruikt om elke gebruiker in vooruitlopende [!UICONTROL segments] te plaatsen.

Als beste praktijken, adviseren wij het kiezen van [!UICONTROL Profile Merge Rule] die de zelfde configuratie zoals uw doelpubliek [!UICONTROL Profile Merge Rule] heeft, of één die het profieltype (apparatenprofiel of voor authentiek verklaard profiel) van uw doelpubliek omvat.

### [!UICONTROL Predictive Audiences] Modeltrainingsfase {#model-training}

Voordat het algoritme je publiek van de eerste partij in de juiste persona&#39;s kan indelen, moet het zichzelf op de gegevens trainen.

Voor elke persoon die u definieert, analyseert het algoritme zijn respectieve publiek en evalueert het elke activiteit in real time en/of ongeboekt trait voor zijn gebruikers in de laatste 30 dagen.
Deze stap vindt om de 24 uur plaats om rekening te houden met wijzigingen in uw eerstepartijpubliek.

### [!UICONTROL Predictive Audiences] Modelindelingsfase {#model-classification}

Voor publieksclassificatie in real time en batch, controleert het model eerst of een gebruiker tot het doelpubliek behoort. Als de gebruiker voor het doelpubliek kwalificeert en niet tot om het even welke persona&#39;s behoort, wijst het model hen een persona kwalificatiescore toe.

Bij het evalueren van het publiek van de eerste partij en het toewijzen van scores, gebruikt het model de standaard **[!UICONTROL Profile Merge Rule]** die in uw account is gedefinieerd. Tot slot wordt de bezoeker geclassificeerd in de persoon waarvoor hij de hoogste score heeft ontvangen.

![voorspellend publiek-grafiek](assets/predictive-audiences-graph.png)

## Overwegingen en beperkingen {#considerations}

>[!IMPORTANT]
> Lees deze sectie zorgvuldig door voordat u verdergaat met de implementatiefase.

Houd bij het configureren van uw [!UICONTROL Predictive Audiences]-modellen rekening met de volgende overwegingen en beperkingen:

* U kunt maximaal tien [!UICONTROL Predictive Audiences]-modellen maken.
* Voor elk model kunt u maximaal 50 basiskenmerken/segmenten kiezen.
* Gegevens van derden en derden worden momenteel niet ondersteund in [!UICONTROL Predictive Audiences].
* [!UICONTROL Predictive Audiences] voert publieksclassificatie uit die op uw eerste partijeigenschappen, van al uw eerste-partijgegevensbronnen wordt gebaseerd.
* De evaluatie van het segment voor [!UICONTROL Predictive Audiences] gebruikt **[!UICONTROL Profile Merge Rule]** die u tijdens modelverwezenlijking kiest. Zie de specifieke [documentatie](../profile-merge-rules/merge-rules-overview.md) voor meer informatie over [!UICONTROL Profile Merge Rules].
* Sommige kenmerken en segmenten worden niet ondersteund als basislijnen of doelgroepen. [!UICONTROL Predictive Audiences] modellen kunnen niet worden opgeslagen wanneer u een van de volgende opties kiest als basislijn of doelpubliek:
   * voorspellende kenmerken en segmenten die met voorspellende kenmerken zijn gecreëerd;
   * [Adobe Experience ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) Platformtraits of segmenten;
   * Algoritmische kenmerken;
   * Tweede en derdekenmerken.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] kan niet worden gebruikt in  [!UICONTROL Audience Lab].

## [!UICONTROL Data Export Controls] {#dec}

De voorspellende segmenten die door [!UICONTROL Predictive Audiences] modellen worden gecreeerd erven [de Controles van de Uitvoer van Gegevens](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) van de volgende eerstepartijgegevensbronnen:

1. De eerste gegevensbron die u kiest bij het bouwen van het model.
1. De gegevensbronnen van de eerste partij van uw doelpubliek. Specifiek, de controles van de gegevensuitvoer van [!UICONTROL traits] of [!UICONTROL segments] die omhoog uw doelpubliek maken.
1. De [Controles van de Uitvoer van Gegevens](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html) van [!UICONTROL Profile Merge Rule] die u voor het model selecteerde.

De nieuwe voorspellende [!UICONTROL traits] en [!UICONTROL segments] hebben dezelfde privacybeperkingen als de samenvoeging van de hierboven beschreven gegevensbronnen van de eerste partij.

Traits die aanvullende beperkingen hebben die geen deel uitmaken van de [!UICONTROL Predictive Audiences]-beperkingen voor de privacy van segmenten, worden uitgesloten van de trainingsfase en zullen niet van invloed worden op het model.

## [!UICONTROL Profile Merge Rules] {#pmr}

Aan alle vooruitlopende segmenten wordt de [!UICONTROL Profile Merge Rule] toegewezen die u hebt geselecteerd bij het maken van het model. De [!UICONTROL Profile Merge Rule] die u kiest is belangrijk om de volgende redenen:

* Hiermee wordt gedefinieerd met welke apparaten en/of geverifieerde profielen rekening moet worden gehouden wanneer het model de invloedrijke [!UICONTROL traits] analyseert, op het moment dat een gebruiker wordt ingedeeld in een voorspellende [!UICONTROL segment].
* Het bepaalt welke [!UICONTROL trait] typen (apparaatniveau of apparaatniveau) tijdens de modeltrainingsstap moeten worden gebruikt en als invloedrijk [!UICONTROL traits] moeten worden weergegeven. Voorspelend [!UICONTROL segments] zijn subsets van uw doelpubliek.
   * Als het doelpubliek een segment is, adviseren wij dat u het zelfde [!UICONTROL Profile Merge Rule] voor het model zoals aan uw doelpubliek wordt toegewezen, of [!UICONTROL Profile Merge Rule] selecteert die het profieltype van uw doelpubliek omvat.
   * Als het doelpubliek een [!UICONTROL trait] is, adviseren wij dat u [!UICONTROL Profile Merge Rule] selecteert die tot het zelfde type van gegevens kan toegang hebben zoals de eigenschap van het doelpubliek (of de gegevens van het apparatenprofiel of de gegevens van het dwars-apparatenprofiel).
* [!UICONTROL Profile Merge Rules] het gebruiken van de  [!UICONTROL Current Authenticated Profiles] en de  [!UICONTROL No Device Profile] opties worden slechts gesteund voor publieksclassificatie in real time. Voor meer informatie zie [Opties van de Regels van de Fusie van het profiel Gedefinieerd](../profile-merge-rules/merge-rule-definitions.md).

Als u een [!UICONTROL Profile Merge Rule] selecteert die zowel apparaatgegevens als apparaatgegevens gebruikt, maximaliseert u het aantal [!UICONTROL traits] dat kan worden gebruikt voor modeltraining en gebruikersclassificatie in het voorspellende [!UICONTROL segments].

## [!UICONTROL Role-Based Access Controls] {#rbac}

De eigenschappen en de segmenten die u voor persona&#39;s en publieksclassificatie kiest zijn onderworpen aan Audience Manager [Op rol-Gebaseerde Controles van de Toegang](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html).

Gebruikers van Audience Managers kunnen alleen sporen of segmenten voor personen en doelgroepen selecteren, waarvoor ze [machtiging hebben om](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html#wild-card-permissions) weer te geven.
