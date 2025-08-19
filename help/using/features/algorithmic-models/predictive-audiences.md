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
source-wordcount: '1470'
ht-degree: 2%

---

# [!UICONTROL Predictive Audiences] Overzicht {#predictive-audiences}

Met [!UICONTROL Predictive Audiences] kunt u een onbekend publiek in realtime in verschillende personen classificeren met behulp van geavanceerde technieken voor gegevenswetenschap.

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

In een marketingcontext is een persoon een publiekssegment dat wordt gedefinieerd door bezoekers, gebruikers of potentiële kopers en dat een specifieke reeks kenmerken deelt, zoals demografie, bruisende gewoonten, winkelgeschiedenis, enz.

[!UICONTROL Predictive Audiences]-modellen gaan met dit concept een stap verder: hiermee kunt u de Audience Manager-mogelijkheden voor machine learning gebruiken om onbekende doelgroepen te classificeren als verschillende persona&#39;s. Audience Manager helpt u dit te bereiken door de neiging te berekenen van uw onbekende publiek van de eerste partij voor een reeks bekende publiek van de eerste partij.

Wanneer u een [!UICONTROL Predictive Audiences] -model maakt, kiest u eerst de basislijnkenmerken of -segmenten waarop het doelpubliek moet worden geclassificeerd. Met deze kenmerken of segmenten worden uw persona&#39;s gedefinieerd.

Tijdens de evaluatiefase maakt het model een nieuw [!UICONTROL Predictive Audiences] segment voor elk kenmerk of segment dat u als basislijn hebt gedefinieerd. De volgende keer dat Audience Manager een bezoeker van het doelpubliek ziet die niet voor een persoon is geclassificeerd (niet in aanmerking kwam voor een van uw basislijnkenmerken of -segmenten), bepaalt het [!UICONTROL Predictive Audiences] -model tot welke van de voorspellende segmenten de bezoeker moet behoren en voegt het de bezoeker toe aan dat segment.

U kunt de voorspellende segmenten die door het model worden gemaakt, identificeren op de pagina [!UICONTROL Segments] . Elk [!UICONTROL Predictive Audiences] -model heeft een eigen map onder de [!UICONTROL Predictive Audiences] -map en u kunt de segmenten van elk model bekijken door op de modelmap te klikken.

![ voorspellend-publiek-segmenten ](assets/predictive-audiences-segments.png)

## Gevallen gebruiken {#use-cases}

Voor een beter begrip van hoe en wanneer u [!UICONTROL Predictive Audiences] kunt gebruiken, zijn er enkele gebruiksgevallen die Audience Manager-klanten met deze functie kunnen oplossen.

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

## Hoe [!UICONTROL Predictive Audiences] modellen werken {#how-predictive-audiences-models-work}

Wanneer u een [!UICONTROL Predictive Audiences] -model maakt, doorloopt u drie stappen:

1. Eerst selecteert u minimaal twee kenmerken of twee segmenten die uw persona&#39;s definiëren.
1. Vervolgens kiest u een kenmerk of segment dat het doelpubliek definieert dat u wilt classificeren.
1. Tot slot kiest u een naam voor het model, een gegevensbron die de voorspellende segmenten zal opslaan, en [!UICONTROL Profile Merge Rule] voor het model.

### Selectiecriteria voor personeel {#selection-personas}

U kunt om het even welk van uw eerstepartijeigenschappen of segmenten kiezen om uw karakters te bepalen. Voor optimale resultaten is er echter een set aanbevolen aanbevolen procedures:

* Kies uw persona trekken of segmenten zodat elke persoon minstens een paar honderd [ apparaat IDs ](../../reference/ids-in-aam.md) heeft.
* Als uw sporen op [ dwars-apparaat IDs ](../../reference/ids-in-aam.md) gebaseerd zijn, kunt u hen in segmenten met [ de Regels van de Fusie van het Profiel ](../profile-merge-rules/merge-rules-overview.md) verpakken die [ apparaat IDs ](../../reference/ids-in-aam.md) gebruiken, zoals [!UICONTROL Device Graph]. Dit zal ervoor zorgen er genoeg [ apparaat IDs ](../../reference/ids-in-aam.md) zijn dat het algoritme van kan leren.
* Wij adviseren het kiezen van eigenschappen of eenvoudige segmenten voor uw persona&#39;s, die uit 1 tot 3 eigenschappen bestaan.
* Kies basislijnkenmerken of segmenten die elkaar minimaal overlappen.
* Zorg ervoor dat u granulaire kenmerken vastlegt over de digitale eigenschappen.

### Selectiecriteria voor doelgroep {#selection-audience}

Afhankelijk van uw gebruiksgeval, of u gebruikers in real time, in partij, of allebei wilt classificeren, kies een doelpubliek ([!UICONTROL trait] of [!UICONTROL segment]) dat een significante real-time en/of totale bevolking heeft. Net als een persoonlijke selectie raden we u aan dat uw doelpubliek [!UICONTROL trait] of [!UICONTROL segment] gebruikers met rijke profielen (rijke sets van [!UICONTROL traits] ) heeft.

Wanneer u het doelpubliek selecteert, analyseert u uw gebruiksscenario en bepaalt u welke typen id&#39;s u wilt classificeren: [!UICONTROL device IDs] of [!UICONTROL cross-device IDs] . De [!UICONTROL Profile Merge Rule] die u selecteert bij het maken van het model, definieert de gegevens die worden gebruikt om elke gebruiker in het voorspellende gedeelte van het formulier te plaatsen [!UICONTROL segments] .

We raden u aan een [!UICONTROL Profile Merge Rule] te kiezen met dezelfde configuratie als uw doelpubliek [!UICONTROL Profile Merge Rule] , of een  met het profieltype (apparaatprofiel of geverifieerd profiel) van uw doelpubliek.

### [!UICONTROL Predictive Audiences] Modeltrainingsfase {#model-training}

Voordat het algoritme je publiek van de eerste partij in de juiste persona&#39;s kan indelen, moet het zichzelf op de gegevens trainen.

Voor elke persoon die u definieert, analyseert het algoritme zijn respectieve publiek en evalueert het elke activiteit in real time en/of ongeboekt trait voor zijn gebruikers in de laatste 30 dagen.
Deze stap vindt om de 24 uur plaats om rekening te houden met wijzigingen in uw eerstepartijpubliek.

### [!UICONTROL Predictive Audiences] Modelindelingsfase {#model-classification}

Voor publieksclassificatie in real time en batch, controleert het model eerst of een gebruiker tot het doelpubliek behoort. Als de gebruiker voor het doelpubliek kwalificeert en niet tot om het even welke persona&#39;s behoort, wijst het model hen een persona kwalificatiescore toe.

Bij het evalueren van het publiek van de eerste partij en het toewijzen van scores, gebruikt het model de standaard **[!UICONTROL Profile Merge Rule]** die in uw account is gedefinieerd. Tot slot wordt de bezoeker geclassificeerd in de persoon waarvoor hij de hoogste score heeft ontvangen.

![ voorspellend-publiek-grafiek ](assets/predictive-audiences-graph.png)

## Overwegingen en beperkingen {#considerations}

>[!IMPORTANT]
> Lees deze sectie zorgvuldig door voordat u verdergaat met de implementatiefase.

Houd rekening met de volgende overwegingen en beperkingen wanneer u uw [!UICONTROL Predictive Audiences] -modellen configureert:

* U kunt maximaal 10 [!UICONTROL Predictive Audiences] modellen maken.
* Voor elk model kunt u maximaal 50 basiskenmerken/segmenten kiezen.
* Gegevens van derden en derden worden momenteel niet ondersteund in [!UICONTROL Predictive Audiences] .
* [!UICONTROL Predictive Audiences] voert publieksclassificatie uit op basis van uw eerste partijkenmerken, van al uw eerste-partijgegevensbronnen.
* Bij de evaluatie van segmenten voor [!UICONTROL Predictive Audiences] wordt de **[!UICONTROL Profile Merge Rule]** gebruikt die u kiest tijdens het maken van het model. Meer over [!UICONTROL Profile Merge Rules] leren zie de specifieke [ documentatie ](../profile-merge-rules/merge-rules-overview.md).
* Sommige kenmerken en segmenten worden niet ondersteund als basislijnen of doelgroepen. [!UICONTROL Predictive Audiences] -modellen worden niet opgeslagen wanneer u een van de volgende opties kiest als basislijn of doelpubliek:
   * voorspellende kenmerken en segmenten die met voorspellende kenmerken zijn gecreëerd;
   * [ Adobe Experience Platform ](../integration/../../integration/integration-aep/aam-aep-audience-sharing.md) trekken of segmenten;
   * Algoritmische kenmerken;
   * Tweede en derdekenmerken.
* [!UICONTROL Predictive Audience] [!UICONTROL segments] kan niet worden gebruikt in [!UICONTROL Audience Lab] .

## [!UICONTROL Data Export Controls] {#dec}

De voorspellende segmenten die door [!UICONTROL Predictive Audiences] modellen worden gecreeerd erven de [ Controles van de Uitvoer van Gegevens ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=nl-NL) van de volgende eerste gegevensbronnen van de partij:

1. De eerste gegevensbron die u kiest bij het bouwen van het model.
1. De gegevensbronnen van de eerste partij van uw doelpubliek. Met name de besturingselementen voor gegevensexport van de [!UICONTROL traits] of [!UICONTROL segments] die het doelpubliek vormen.
1. De [ Controles van de Uitvoer van Gegevens ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-export-controls.html?lang=nl-NL) van [!UICONTROL Profile Merge Rule] die u voor het model selecteerde.

De nieuwe voorspellende functies [!UICONTROL traits] en [!UICONTROL segments] hebben dezelfde privacybeperkingen als de samenvoeging van de hierboven beschreven gegevensbronnen van de eerste partij.

Traits die aanvullende beperkingen hebben die geen deel uitmaken van de privacybeperkingen voor segmenten van [!UICONTROL Predictive Audiences] , worden uitgesloten van de trainingsfase en worden niet beïnvloed door het model.

## [!UICONTROL Profile Merge Rules] {#pmr}

Aan alle voorspellende segmenten wordt de [!UICONTROL Profile Merge Rule] toegewezen die u hebt geselecteerd bij het maken van het model. De [!UICONTROL Profile Merge Rule] die u kiest, is om de volgende redenen belangrijk:

* Hiermee wordt gedefinieerd met welke apparaten en/of geverifieerde profielen rekening moet worden gehouden wanneer het model het invloedrijke [!UICONTROL traits] analyseert, op het moment dat een gebruiker in een voorspellend profiel wordt ingedeeld [!UICONTROL segment] .
* De klasse bepaalt welke [!UICONTROL trait] -typen (apparaatniveau of apparaatniveau) tijdens de modeltrainingsstap moeten worden gebruikt en als invloedrijk [!UICONTROL traits] moeten worden weergegeven. Predictief [!UICONTROL segments] zijn subsets van uw doelgroep.
   * Als het doelpubliek een segment is, raden we u aan om dezelfde [!UICONTROL Profile Merge Rule] voor het model te selecteren als het model dat aan uw doelpubliek is toegewezen, of een [!UICONTROL Profile Merge Rule] die het profieltype van uw doelpubliek bevat.
   * Als het doelpubliek een [!UICONTROL trait] is, raden we u aan een [!UICONTROL Profile Merge Rule] te selecteren die toegang kan krijgen tot hetzelfde type gegevens als de doeldoelgroep (apparaatprofielgegevens of apparaatprofielgegevens).
* [!UICONTROL Profile Merge Rules] het gebruik van de opties [!UICONTROL Current Authenticated Profiles] en [!UICONTROL No Device Profile] wordt alleen ondersteund voor publieksclassificatie in realtime. Voor meer informatie zie {de Opties van de Regels van de Fusie van het 0} Profiel bepaalde [.](../profile-merge-rules/merge-rule-definitions.md)

Als u een [!UICONTROL Profile Merge Rule] selecteert die zowel apparaatgegevens als apparaatgegevens gebruikt, maximaliseert u het aantal [!UICONTROL traits] dat kan worden gebruikt voor modeltraining en gebruikersclassificatie in de voorspellende [!UICONTROL segments] .

## [!UICONTROL Role-Based Access Controls] {#rbac}

De eigenschappen en de segmenten die u voor persona&#39;s en publieksclassificatie kiest zijn onderworpen aan Audience Manager [ Op rol-Gebaseerde Controles van de Toegang ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html?lang=nl-NL).

De gebruikers van Audience Manager kunnen slechts sporen of segmenten voor persona&#39;s en doelpubliek selecteren, dat zij [ toestemming hebben om ](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/administration/administration-overview.html?lang=nl-NL#wild-card-permissions) te bekijken.
