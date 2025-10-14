---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Predictive Audiences FAQ
solution: Audience Manager
title: Veelgestelde vragen over Predictieve doelgroepen
feature: Algorithmic Models
exl-id: 21073970-8457-470b-89fc-724a118a18d2
source-git-commit: 03f039a1317576c7979a5cb4c3cffc543e3bd656
workflow-type: tm+mt
source-wordcount: '957'
ht-degree: 59%

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

 

**Wanneer kan ik de eerste resultaten van mijn model verwachten?**

[!UICONTROL Predictive Audiences]-modelresultaten zijn beschikbaar binnen 24 uur na het maken van het model, als het model succesvol wordt uitgevoerd.

Neem contact op met uw Adobe-vertegenwoordiger als het model niet binnen 24 uur resultaten oplevert.

 

**Waarom produceert mijn model geen resultaten of toont het een waarschuwingsstatus?**

Er kunnen diverse redenen zijn waarom [!UICONTROL Predictive Audiences]-modellen geen resultaten opleveren:

1. Geen van de geselecteerde personen [!UICONTROL traits] / [!UICONTROL segments] heeft voldoende gebruikersprofielen. We raden u aan om uw [!UICONTROL traits] of [!UICONTROL segments] zodanig te kiezen dat elke persoon ten minste een paar honderd gebruikersprofielen heeft.
1. Geen van de geselecteerde personen [!UICONTROL traits] / [!UICONTROL segments] heeft voldoende gegevens in hun gebruikersprofielen (niet genoeg kenmerken om te analyseren).
1. De eigenschap / het segment van het doelpubliek heeft geen actieve of onbeheerde gebruikers.
1. Doelgroepgebruikers die de afgelopen 30 dagen actief of onboarded waren, hebben onvoldoende data in hun gebruikersprofielen (te weinig eigenschappen om te analyseren).
1. Het doelpubliekssegment gebruikt een andere [!UICONTROL Profile Merge Rule] dan de doelpubliekssegment die u voor het model hebt gekozen.
1. De gegevensbron van de kenmerken van het doelpubliek wordt mogelijk niet opgenomen in de [!UICONTROL Profile Merge Rule] die u voor het model hebt gekozen.

Volg voor optimale resultaten de voorgestelde richtlijnen van [Selectiecriteria voor persona&#39;s](../features/algorithmic-models/predictive-audiences.md#selection-personas) en [Selectiecriteria voor doelgroepen](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**waarom is mijn model dat de [!UICONTROL Error] status toont?**

Het model kan niet worden uitgevoerd. In dergelijke gevallen kunt u contact opnemen met uw [!DNL Adobe] -vertegenwoordiger.

 

**hoe kan ik [!UICONTROL Profile Merge Rule] voor a [!UICONTROL Predictive Audiences] veranderen [!UICONTROL segment]?**

Maak een nieuw model door dezelfde personen en doelgroepen te selecteren als het vorige model. Wijs tijdens het maken van een model een andere [!UICONTROL Profile Merge Rule] toe.

>[!WARNING]
> Alternatief, kunt u [&#x200B; Bouwer van het Segment &#x200B;](../features/segments/segment-builder.md) gebruiken om a [!UICONTROL segment] met een bestaand vooruitlopend [!UICONTROL trait] manueel tot stand te brengen en het toe te wijzen a [!UICONTROL Profile Merge Rule] van uw keus.
> 
> We raden deze werkwijze echter niet aan, omdat voorspellende [!UICONTROL traits] automatisch de [!UICONTROL Profile Merge Rule] overerft van het model waartoe ze behoren en ze zijn gemaakt van invloedrijke [!UICONTROL traits] die voldoen aan de [!UICONTROL Profile Merge Rule] van het model.

 

**wat [!UICONTROL Profile Merge Rule] zou moeten kiezen?**

Wanneer u [!UICONTROL Profile Merge Rule] kiest voor uw model, moet u de gebruikte hoofdletters/kleine letters zorgvuldig analyseren.

Stel dat uw doelpubliek [!UICONTROL segment] een [!UICONTROL Profile Merge Rule] gebruikt op basis van geverifieerde profielen + [!DNL Device Graph] -profielen en dat u hetzelfde [!UICONTROL Profile Merge Rule] selecteert voor de voorspellende [!UICONTROL segments] . In dit geval worden zowel apparaatniveau als apparaatniveau [!UICONTROL traits] gebruikt bij het trainen van het model en bij het plaatsen van de gebruiker in een voorspellend [!UICONTROL segment] .

Als u echter een [!UICONTROL Profile Merge Rule] selecteert die alleen op apparaatprofielen is gebaseerd, wordt geen van uw apparaten [!UICONTROL traits] invloedrijk en dragen deze niet bij aan de plaatsing van gebruikers in een voorspellend profiel [!UICONTROL segment] . Dit kan een negatief effect hebben op de nauwkeurigheid en het bereik van het model.

Analyseer uw gebruikscase zorgvuldig en bepaal welke [!UICONTROL trait] types u van het model wilt leren van en welk type van gegevens u het model voor classificatie wilt gebruiken.

**Kan het zijn dat een gebruiker uit de doelgroep die geen deel uitmaakt van een persona-eigenschap/segment niet is geclassificeerd?**

Ja, dat kan wanneer de gebruiker geen eigenschappen in zijn/haar profiel heeft. In dat geval krijgt de gebruiker een matchscore van 0 voor alle persona-eigenschappen/segmenten en wordt daarom niet in een van de voorspellende segmenten geclassificeerd.

 

**Kan een gebruiker die in één van de voorspellende segmenten is geclassificeerd, opnieuw worden geclassificeerd in een ander [!UICONTROL Predictive Audiences]-segment?**

Ja. Aangezien de algoritme dagelijks wordt getraind, past deze de wijzigingen voor alle persona’s aan in termen van eigenschapscores. Als een gebruiker die in een [!UICONTROL Predictive Audiences]-segment thuishoort, actief is, kunnen de wijzigingen in zijn of haar eigenschapscore de classificatie wijzigen op basis van de activiteit van de afgelopen 30 dagen.

 

**Kan ik de eigenschappen zien op basis waarvan doelgroepclassificatie wordt uitgevoerd?**

Ja, u kunt alle invloedrijke eigenschappen voor alle basislijnen zien op de pagina met modelrapportage. Zie [Invloedrijke eigenschappen](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**kan ik de tijd veranderen om (TTL) voor vooruitlopende eigenschappen te leven?**

De voorspellende eigenschap TTL wordt geplaatst aan 0 (leven) en kan niet worden veranderd. [!UICONTROL Predictive Audiences] kan gebruikers alleen losmaken van voorspellende segmenten als ze in aanmerking komen voor het basissegment of als ze worden geherclassificeerd naar een ander voorspellend segment.

Indien nodig, kunt u rond deze functionaliteit werken door een nieuw segment te creëren dat zowel een vooruitlopende eigenschap als een activiteiteneigenschap met gespecificeerde TTL bevat.

 


**Wat gebeurt er met het model als ik een van de basislijneigenschappen of -segmenten bewerk?**

Het model evalueert de eigenschappen of segmenten eenmaal per dag. De dag na de update wordt de bijgewerkte classificatie weergegeven.

 

**Kan ik de databronnen selecteren waarvan het model leert?**

Nee, selectie van databronnen wordt niet ondersteund. De [!UICONTROL Predictive Audiences]-algoritme leert van al uw interne eigenschappen.
