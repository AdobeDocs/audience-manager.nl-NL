---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-title: Veelgestelde vragen over Predictieve doelgroepen
solution: Audience Manager
title: Predictieve doelgroepen in Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '773'
ht-degree: 100%

---


# Veelgestelde vragen over Predictieve doelgroepen

Veelgestelde vragen over [!UICONTROL Predictive Audiences].

 

**Wanneer moet ik [!UICONTROL Predictive Audiences] gebruiken, in tegenstelling tot [!UICONTROL Look-alike modeling]?**

[!UICONTROL Predictive Audiences] en [!UICONTROL Look-alike modeling] zijn geschikt voor verschillende gebruiksscenario’s. De belangrijkste verschillen tussen de twee algoritmes zijn:

1. [!UICONTROL Look-alike modeling] gebruikt een kleine doelgroep als invoer en breidt deze uit. [!UICONTROL Predictive Audiences] gebruikt een grote doelgroep als invoer en verdeelt deze in kleinere, verschillende doelgroepen, gedefinieerd door uw persona&#39;s.
1. Het aantal basissegmenten is verschillend voor beide algoritmes. [!UICONTROL Predictive Audiences] vereist minstens twee basislijnen, terwijl [!UICONTROL Look-alike modeling] hoogstens één basislijn gebruikt.
1. [!UICONTROL Predictive Audiences] voert segmentevaluatie in real time uit, [!UICONTROL Look-alike modeling] niet.

Op basis van uw gebruiksscenario moet u bepalen welk model voor u relevanter is.

Denk bijvoorbeeld aan het maken van een [!UICONTROL Predictive Audiences]-model met een aantal basislijnen als het equivalent van het bouwen van hetzelfde aantal look-alike modellen, maar dan zonder de realtime-evaluatie, en met een heel grote kans op bezoekers van verschillende persona&#39;s, in plaats van één afzonderlijke persona.

 

**Hoeveel persona&#39;s/modellen mag ik maken?**

U kunt maximaal tien [!UICONTROL Predictive Audiences]-modellen maken. Voor elk model kunt u maximaal 50 basislijneigenschappen of -segmenten definiëren.

 

**Hoe kan ik nieuwe segmenten maken van een [!UICONTROL Predictive Audiences]-segment?**

Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Segments]** en klik op de map **[!UICONTROL Predictive Audiences]**. Zoek het gewenste segment, dupliceer het en bewerk het naar wens.

 

**Waarom zijn sommige van mijn onboarded bezoekers niet geclassificeerd?**

Momenteel werkt doelgroepclassificatie alleen voor realtimekwalificaties, behalve voor geverifieerde gebruikers die zijn gedefinieerd als onderdeel van [!UICONTROL Profile Merge Rules].

Volledige ondersteuning voor onboarded data wordt in een toekomstige update toegevoegd.

 

**Wanneer kan ik de eerste resultaten van mijn model verwachten?**

[!UICONTROL Predictive Audiences]-modelresultaten zijn beschikbaar binnen 24 uur na het maken van het model, als het model succesvol wordt uitgevoerd.

Neem contact op met uw Adobe-vertegenwoordiger als het model niet binnen 24 uur resultaten oplevert.

 

**Waarom produceert mijn model geen resultaten of toont het een waarschuwingsstatus?**

Er kunnen diverse redenen zijn waarom [!UICONTROL Predictive Audiences]-modellen geen resultaten opleveren:

1. Geen van de geselecteerde personakenmerken/segmenten heeft voldoende gebruikersprofielen. We raden u aan uw eigenschappen of segmenten zo te kiezen dat elke persona minstens een paar honderd gebruikersprofielen heeft.
1. Geen van de geselecteerde personakenmerken/segmenten heeft voldoende data in hun gebruikersprofielen (te weinig eigenschappen om te analyseren).
1. De doelgroepeigenschap/het doelgroepsegment had de afgelopen 30 dagen geen actieve of onboarded gebruikers.
1. Doelgroepgebruikers die de afgelopen 30 dagen actief of onboarded waren, hebben onvoldoende data in hun gebruikersprofielen (te weinig eigenschappen om te analyseren).

Voor het produceren van relevante resultaten evalueert de [!UICONTROL Predictive Audiences]-algoritme eigenschap- en segmentrealisaties op basis van realtime-gebruikersactiviteit die door de DCS wordt gedetecteerd. Als u nieuwe basiseigenschappen en -segmenten selecteert die nog niet genoeg gebruikers hebben, kan de algoritme een paar dagen nodig hebben om uw doelgroep te classificeren.

Volg voor optimale resultaten de voorgestelde richtlijnen van [Selectiecriteria voor persona&#39;s](../features/algorithmic-models/predictive-audiences.md#selection-personas) en [Selectiecriteria voor doelgroepen](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Waarom toont mijn model de foutstatus?**

Het model kan niet worden uitgevoerd. In dergelijke gevallen kunt u contact opnemen met uw Adobe-vertegenwoordiger.

 

**Hoe kan ik de regel voor profielsamenvoeging wijzigen voor een Predictieve doelgroepen-segment?**

Dupliceer het [!UICONTROL Predictive Audiences]-segment en wijzig de [!UICONTROL Profile Merge Rule] voor het gedupliceerde segment.

 

**Kan het zijn dat een gebruiker uit de doelgroep die geen deel uitmaakt van een persona-eigenschap/segment niet is geclassificeerd?**

Ja, dat kan wanneer de gebruiker geen eigenschappen in zijn/haar profiel heeft. In dat geval krijgt de gebruiker een matchscore van 0 voor alle persona-eigenschappen/segmenten en wordt daarom niet in een van de voorspellende segmenten geclassificeerd.

 

**Kan een gebruiker die in één van de voorspellende segmenten is geclassificeerd, opnieuw worden geclassificeerd in een ander [!UICONTROL Predictive Audiences]-segment?**

Ja. Aangezien de algoritme dagelijks wordt getraind, past deze de wijzigingen voor alle persona’s aan in termen van eigenschapscores. Als een gebruiker die in een [!UICONTROL Predictive Audiences]-segment thuishoort, actief is, kunnen de wijzigingen in zijn of haar eigenschapscore de classificatie wijzigen op basis van de activiteit van de afgelopen 30 dagen.

 

**Kan ik de eigenschappen zien op basis waarvan doelgroepclassificatie wordt uitgevoerd?**

Ja, u kunt alle invloedrijke eigenschappen voor alle basislijnen zien op de pagina met modelrapportage. Zie [Invloedrijke eigenschappen](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Wat gebeurt er met het model als ik een van de basislijneigenschappen of -segmenten bewerk?**

Het model evalueert de eigenschappen of segmenten eenmaal per dag. De dag na de update wordt de bijgewerkte classificatie weergegeven.

 

**Kan ik de databronnen selecteren waarvan het model leert?**

Nee, selectie van databronnen wordt niet ondersteund. De [!UICONTROL Predictive Audiences]-algoritme leert van al uw interne eigenschappen.