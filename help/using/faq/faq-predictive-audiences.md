---
description: Met voorspellende doelgroepen kunt u een onbekend publiek in real-time in verschillende personen indelen met behulp van gegevenswetenschap.
seo-description: Met voorspellende doelgroepen kunt u een onbekend publiek in real-time in verschillende personen indelen met behulp van gegevenswetenschap.
seo-title: Veelgestelde vragen over voorspellende doelgroepen
solution: Audience Manager
title: Audience Manager voorspellend publiek
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 0%

---


# Veelgestelde vragen over voorspellende doelgroepen

Veelgestelde vragen over [!UICONTROL Predictive Audiences].

 

**Wanneer moet ik[!UICONTROL Predictive Audiences]in tegenstelling tot[!UICONTROL Look-alike modeling]gebruiken?**

[!UICONTROL Predictive Audiences] en andere gebruiksgevallen [!UICONTROL Look-alike modeling] te gebruiken. De belangrijkste verschillen tussen de twee algoritmen zijn:

1. [!UICONTROL Look-alike modeling] neemt een klein publiek als input en breidt het uit. [!UICONTROL Predictive Audiences] neemt een groot publiek als input, en verdeelt het in kleinere verschillende soorten publiek, die door uw persoonlijkheden worden bepaald.
1. Het aantal basissegmenten is verschillend voor elk algoritme. [!UICONTROL Predictive Audiences] vereist minstens twee basislijnen, terwijl [!UICONTROL Look-alike modeling] gebruikt hoogstens één basislijn.
1. [!UICONTROL Predictive Audiences] voert segment evaluatie in real time uit, terwijl [!UICONTROL Look-alike modeling] niet.

Op basis van uw gebruiksgeval moet u beslissen welk model voor u relevanter is.

Je kan denken aan het bouwen van een [!UICONTROL Predictive Audiences] model met een aantal basislijnen als het equivalent van het bouwen van hetzelfde aantal modellen van look-alike, alleen zonder de real-time evaluatie, en met een zeer grote kans om bezoekers te hebben die tot meerdere verschillende persona&#39;s behoren, in plaats van één verschillende persona.

 

**Hoeveel personen/modellen mag ik maken?**

U kunt maximaal 10 [!UICONTROL Predictive Audiences] modellen maken. Voor elk model, kunt u tot 50 basislijnkenmerken of segmenten bepalen.

 

**Hoe kan ik nieuwe segmenten van een[!UICONTROL Predictive Audiences]segment bouwen?**

Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** en klik op de **[!UICONTROL Predictive Audiences]** map. Zoek het gewenste segment, dupliceer het en bewerk het naar wens.

 

**Waarom zijn sommige van mijn bezoekers niet geclassificeerd?**

Momenteel werkt de publieksclassificatie alleen voor realtime kwalificaties, behalve voor geverifieerde gebruikers die zijn gedefinieerd als onderdeel van [!UICONTROL Profile Merge Rules].

Volledige ondersteuning voor gegevens aan boord wordt toegevoegd in een toekomstige update.

 

**Wanneer zie ik de eerste resultaten van mijn model?**

[!UICONTROL Predictive Audiences] modelresultaten zijn beschikbaar binnen 24 uur na het maken van het model als het model succesvol is uitgevoerd.

Neem contact op met uw Adobe-vertegenwoordiger als het model niet binnen 24 uur resultaten oplevert.

 

**Waarom produceert mijn model geen resultaten of toont de status van de Waarschuwing?**

[!UICONTROL Predictive Audiences] modellen kunnen om een aantal redenen geen resultaten opleveren:

1. Geen van de geselecteerde persoonlijke kenmerken/segmenten heeft voldoende gebruikersprofielen. We raden u aan uw kenmerken of segmenten te kiezen, zodat elke persoon minstens een paar honderd gebruikersprofielen heeft.
1. Geen van de geselecteerde persoonlijke kenmerken/segmenten hebben voldoende gegevens in hun gebruikersprofielen (onvoldoende kenmerken om te analyseren).
1. Het doelpubliek trait/segment had de afgelopen 30 dagen geen actieve of onbeheerde gebruikers.
1. Gebruikers van doelgroepen die de afgelopen 30 dagen actief of ingeschakeld waren, beschikken niet over voldoende gegevens in hun gebruikersprofielen (onvoldoende kenmerken om te analyseren).

Om relevante resultaten te produceren, evalueert het [!UICONTROL Predictive Audiences] algoritme eigenschap en segmentrealisaties die op gebruikersactiviteit in real time door DCS worden gezien. Als u nieuwe basiskenmerken en segmenten selecteert die nog niet genoeg gebruikers hebben, kan het algoritme een paar dagen duren om uw publiek te classificeren.

Voor optimale resultaten volgt u de voorgestelde richtlijnen uit de [selectiecriteria voor persoonlijke personen](../features/algorithmic-models/predictive-audiences.md#selection-personas) en de [selectiecriteria voor Target Audience](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Waarom toont mijn model de status van de Fout?**

Het model kan niet worden uitgevoerd. In dergelijke gevallen kunt u contact opnemen met uw vertegenwoordiger van Adobe.

 

**Hoe kan ik de Regel van de Fusie van het Profiel voor een Predictive segment van het publiek veranderen?**

Dupliceer het [!UICONTROL Predictive Audiences] segment en verander het [!UICONTROL Profile Merge Rule] voor het gedupliceerde segment.

 

**Kan een gebruiker van het doelpubliek die geen deel uitmaakt van enige persona eigenschap/segment niet worden geclassificeerd?**

Ja, voor het geval de gebruiker geen eigenschappen in zijn profiel heeft. In dat geval krijgt de gebruiker een overeenkomende score van 0 voor alle persona-kenmerken/-segmenten en wordt deze daarom niet in een van de voorspellende segmenten geclassificeerd.

 

**Kan een gebruiker die in één van de vooruitlopende segmenten werd geclassificeerd in een verschillend[!UICONTROL Predictive Audiences]segment worden geherclassificeerd?**

Ja. Aangezien het algoritme dagelijks wordt opgeleid, past het de veranderingen voor elk van de persona&#39;s op het gebied van het schatten van het bezit toe. Als een gebruiker die deel uitmaakt van een [!UICONTROL Predictive Audiences] segment actief is, kunnen de wijzigingen in de score voor het kenmerk de classificatie wijzigen op basis van de activiteit van de afgelopen 30 dagen.

 

**Kan ik de kenmerken zien waarmee publieksclassificatie wordt uitgevoerd?**

Ja, u kunt alle invloedrijke eigenschappen voor alle basislijnen in de modelrapporteringspagina zien. Zie [Influential Traits](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Wat gebeurt er met het model als ik een van de basislijnkenmerken of -segmenten bewerk?**

Het model evalueert de kenmerken of segmenten eenmaal per dag. De volgende dag na de update wordt de bijgewerkte classificatie weergegeven.

 

**Kan ik de gegevensbronnen selecteren waarvan het model zal leren?**

Nee, selectie van gegevensbronnen wordt niet ondersteund. Het [!UICONTROL Predictive Audiences] algoritme leert van al uw eerste partijeigenschappen.