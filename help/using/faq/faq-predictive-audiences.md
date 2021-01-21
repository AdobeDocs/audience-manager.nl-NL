---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-title: Veelgestelde vragen over Predictieve doelgroepen
solution: Audience Manager
title: Predictieve doelgroepen in Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: c2c392b1201b5de08a3f4d58bbb7be5ef31545d0
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

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

1. Geen van de geselecteerde personen [!UICONTROL traits] / [!UICONTROL segments] heeft voldoende gebruikersprofielen. We raden u aan uw [!UICONTROL traits] of [!UICONTROL segments] te kiezen, zodat elke persoon ten minste een paar honderd gebruikersprofielen heeft.
1. Geen van de geselecteerde personen [!UICONTROL traits] / [!UICONTROL segments] hebben voldoende gegevens in hun gebruikersprofielen (niet genoeg kenmerken om te analyseren).
1. De eigenschap / het segment van het doelpubliek heeft geen actieve of onbeheerde gebruikers.
1. Doelgroepgebruikers die de afgelopen 30 dagen actief of onboarded waren, hebben onvoldoende data in hun gebruikersprofielen (te weinig eigenschappen om te analyseren).
1. Het doelpubliekssegment gebruikt een andere [!UICONTROL Profile Merge Rule] dan die u voor het model koos.
1. De gegevensbron van uw doelpubliekskenmerken worden mogelijk niet opgenomen in de [!UICONTROL Profile Merge Rule] die u voor het model hebt gekozen.

Volg voor optimale resultaten de voorgestelde richtlijnen van [Selectiecriteria voor persona&#39;s](../features/algorithmic-models/predictive-audiences.md#selection-personas) en [Selectiecriteria voor doelgroepen](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Waarom toont mijn model de  [!UICONTROL Error] status?**

Het model kan niet worden uitgevoerd. In dergelijke gevallen dient u contact op te nemen met uw [!DNL Adobe] vertegenwoordiger.

 

**Hoe kan ik het  [!UICONTROL Profile Merge Rule] voor een  [!UICONTROL Predictive Audiences] [!UICONTROL segment]veranderen?**

Maak een nieuw model door dezelfde personen en doelgroepen te selecteren als het vorige model. Wijs tijdens het maken van een model een andere [!UICONTROL Profile Merge Rule] toe.

>[!WARNING]
> U kunt [Segment Builder](../features/segments/segment-builder.md) ook gebruiken om handmatig een [!UICONTROL segment] met een bestaande voorspellende [!UICONTROL trait] te maken en deze [!UICONTROL Profile Merge Rule] van uw keuze toe te wijzen.
> 
> Wij raden deze praktijk echter niet aan, omdat voorspellende [!UICONTROL traits] automatisch de [!UICONTROL Profile Merge Rule] overerft van het model waartoe ze behoren, en deze worden gebouwd uit invloedrijke [!UICONTROL traits] die voldoen aan [!UICONTROL Profile Merge Rule] van het model.

 

**Wat  [!UICONTROL Profile Merge Rule] moet ik kiezen?**

Wanneer u de [!UICONTROL Profile Merge Rule] voor uw model kiest, moet u de gebruiksaanwijzing nauwkeurig analyseren.

Stel dat uw doelpubliek [!UICONTROL segment] een [!UICONTROL Profile Merge Rule] gebruikt op basis van geverifieerde profielen + [!DNL Device Graph] profielen en dat u dezelfde [!UICONTROL Profile Merge Rule] selecteert voor de voorspellende [!UICONTROL segments]. In dit geval worden zowel apparaatniveau als apparaatniveau [!UICONTROL traits] gebruikt bij het trainen van het model en bij het plaatsen van de gebruiker in een voorspellende [!UICONTROL segment].

Als u echter een [!UICONTROL Profile Merge Rule] selecteert die alleen op apparaatprofielen is gebaseerd, wordt geen van uw apparaten [!UICONTROL traits] beïnvloed en draagt dit niet bij aan de plaatsing van gebruikers in een voorspellende [!UICONTROL segment]. Dit kan een negatief effect hebben op de nauwkeurigheid en het bereik van het model.

Analyseer uw gebruiksgeval zorgvuldig en bepaal welke [!UICONTROL trait] types u het model van en welk type van gegevens wilt leren u het model voor classificatie wilt gebruiken.

**Kan het zijn dat een gebruiker uit de doelgroep die geen deel uitmaakt van een persona-eigenschap/segment niet is geclassificeerd?**

Ja, dat kan wanneer de gebruiker geen eigenschappen in zijn/haar profiel heeft. In dat geval krijgt de gebruiker een matchscore van 0 voor alle persona-eigenschappen/segmenten en wordt daarom niet in een van de voorspellende segmenten geclassificeerd.

 

**Kan een gebruiker die in één van de voorspellende segmenten is geclassificeerd, opnieuw worden geclassificeerd in een ander [!UICONTROL Predictive Audiences]-segment?**

Ja. Aangezien de algoritme dagelijks wordt getraind, past deze de wijzigingen voor alle persona’s aan in termen van eigenschapscores. Als een gebruiker die in een [!UICONTROL Predictive Audiences]-segment thuishoort, actief is, kunnen de wijzigingen in zijn of haar eigenschapscore de classificatie wijzigen op basis van de activiteit van de afgelopen 30 dagen.

 

**Kan ik de eigenschappen zien op basis waarvan doelgroepclassificatie wordt uitgevoerd?**

Ja, u kunt alle invloedrijke eigenschappen voor alle basislijnen zien op de pagina met modelrapportage. Zie [Invloedrijke eigenschappen](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Kan ik de tijd veranderen om te leven (TTL) voor voorspellende eigenschappen?**

De voorspellende eigenschap TTL wordt geplaatst aan 0 (leven) en kan niet worden veranderd. [!UICONTROL Predictive Audiences] gebruikers alleen van voorspellende segmenten kunnen losmaken wanneer zij in aanmerking komen voor het basissegment of wanneer zij worden geherclassificeerd naar een ander voorspellend segment.

Indien nodig, kunt u rond deze functionaliteit werken door een nieuw segment te creëren dat zowel een vooruitlopende eigenschap als een activiteiteneigenschap met gespecificeerde TTL bevat.

 


**Wat gebeurt er met het model als ik een van de basislijneigenschappen of -segmenten bewerk?**

Het model evalueert de eigenschappen of segmenten eenmaal per dag. De dag na de update wordt de bijgewerkte classificatie weergegeven.

 

**Kan ik de databronnen selecteren waarvan het model leert?**

Nee, selectie van databronnen wordt niet ondersteund. De [!UICONTROL Predictive Audiences]-algoritme leert van al uw interne eigenschappen.