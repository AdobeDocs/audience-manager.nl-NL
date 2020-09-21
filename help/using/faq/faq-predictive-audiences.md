---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-title: Veelgestelde vragen over Predictieve doelgroepen
solution: Audience Manager
title: Predictieve doelgroepen in Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 91ed0e755982375f41ed5eb484fa8e60bbe6f8e5
workflow-type: tm+mt
source-wordcount: '1024'
ht-degree: 64%

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

1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough user profiles. We recommend choosing your [!UICONTROL traits] or [!UICONTROL segments] so that each persona has at least a few hundred user profiles.
1. None of the selected persona [!UICONTROL traits] / [!UICONTROL segments] have enough data in their user profiles (not enough traits to analyze).
1. De doelgroepeigenschap/het doelgroepsegment had de afgelopen 30 dagen geen actieve of onboarded gebruikers.
1. Doelgroepgebruikers die de afgelopen 30 dagen actief of onboarded waren, hebben onvoldoende data in hun gebruikersprofielen (te weinig eigenschappen om te analyseren).
1. Het doelpubliekssegment gebruikt een andere segment [!UICONTROL Profile Merge Rule] dan het segment dat u voor het model hebt gekozen.
1. De gegevensbron van de kenmerken van het doelpubliek wordt mogelijk niet opgenomen in het model [!UICONTROL Profile Merge Rule] dat u hebt gekozen.

To produce relevant results, the [!UICONTROL Predictive Audiences] algorithm evaluates trait and segment realizations based on real-time user activity seen by the [!DNL DCS]. Als u nieuwe basiseigenschappen en -segmenten selecteert die nog niet genoeg gebruikers hebben, kan de algoritme een paar dagen nodig hebben om uw doelgroep te classificeren.

Volg voor optimale resultaten de voorgestelde richtlijnen van [Selectiecriteria voor persona&#39;s](../features/algorithmic-models/predictive-audiences.md#selection-personas) en [Selectiecriteria voor doelgroepen](../features/algorithmic-models/predictive-audiences.md#selection-audience).

 

**Waarom toont mijn model de[!UICONTROL Error]status?**

Het model kan niet worden uitgevoerd. In such cases, please reach out to your [!DNL Adobe] representative.

 

**Hoe kan ik de[!UICONTROL Profile Merge Rule]voor een[!UICONTROL Predictive Audiences][!UICONTROL segment]wijziging wijzigen?**

Maak een nieuw model door dezelfde personen en doelgroepen te selecteren als het vorige model. Wijs tijdens het maken van het model een andere waarde toe [!UICONTROL Profile Merge Rule].

>[!WARNING]
> Alternatief, kunt u de Bouwer [van het](../features/segments/segment-builder.md) Segment gebruiken om een [!UICONTROL segment] met een bestaande vooruitlopende situatie manueel tot stand te brengen [!UICONTROL trait] en het een [!UICONTROL Profile Merge Rule] van uw keus toe te wijzen.
> 
> Wij raden deze praktijk echter niet aan, aangezien voorspellend [!UICONTROL traits] automatisch de aard [!UICONTROL Profile Merge Rule] van het model erft waartoe ze behoren, en ze worden opgebouwd uit invloedrijke elementen [!UICONTROL traits] die voldoen aan het [!UICONTROL Profile Merge Rule] model.

 

**Wat[!UICONTROL Profile Merge Rule]moet ik kiezen?**

Wanneer u de optie [!UICONTROL Profile Merge Rule] voor uw model kiest, moet u de gebruiksaanwijzing zorgvuldig analyseren.

Stel dat uw doelpubliek een profiel [!UICONTROL segment] gebruikt dat is gebaseerd [!UICONTROL Profile Merge Rule] op geverifieerde profielen + [!DNL Device Graph] profielen en dat u hetzelfde selecteert [!UICONTROL Profile Merge Rule] voor voorspellend [!UICONTROL segments]. In dit geval [!UICONTROL traits] worden zowel het niveau van het apparaat als het niveau van het apparaat gebruikt bij de training van het model en bij de plaatsing van de gebruiker in een voorspellend element [!UICONTROL segment].

Als u echter een profiel selecteert dat alleen is gebaseerd op apparaatprofielen, [!UICONTROL Profile Merge Rule] wordt geen van uw apparaten beïnvloed en draagt dit niet bij aan de plaatsing van gebruikers in een voorspelbaar profiel [!UICONTROL traits] [!UICONTROL segment]. Dit kan een negatief effect hebben op de nauwkeurigheid en het bereik van het model.

Analyseer uw gebruiksgeval zorgvuldig en bepaal welke [!UICONTROL trait] types u het model van en welk type van gegevens wilt leren u het model voor classificatie wilt gebruiken.

**Kan het zijn dat een gebruiker uit de doelgroep die geen deel uitmaakt van een persona-eigenschap/segment niet is geclassificeerd?**

Ja, dat kan wanneer de gebruiker geen eigenschappen in zijn/haar profiel heeft. In dat geval krijgt de gebruiker een matchscore van 0 voor alle persona-eigenschappen/segmenten en wordt daarom niet in een van de voorspellende segmenten geclassificeerd.

 

**Kan een gebruiker die in één van de voorspellende segmenten is geclassificeerd, opnieuw worden geclassificeerd in een ander [!UICONTROL Predictive Audiences]-segment?**

Ja. Aangezien de algoritme dagelijks wordt getraind, past deze de wijzigingen voor alle persona’s aan in termen van eigenschapscores. Als een gebruiker die in een [!UICONTROL Predictive Audiences]-segment thuishoort, actief is, kunnen de wijzigingen in zijn of haar eigenschapscore de classificatie wijzigen op basis van de activiteit van de afgelopen 30 dagen.

 

**Kan ik voorspellende eigenschappen aan regelmatige segmenten toevoegen?**

Wanneer u een vooruitlopende eigenschap aan een normaal segment toevoegt, wordt het segment een vooruitstrevend segment. Alle gekoppelde profielen zijn daarom niet-gesegmenteerd. De voorspellende segmenten kunnen slechts naar bestemmingen in real time worden verzonden.

 

**Kan ik de eigenschappen zien op basis waarvan doelgroepclassificatie wordt uitgevoerd?**

Ja, u kunt alle invloedrijke eigenschappen voor alle basislijnen zien op de pagina met modelrapportage. Zie [Invloedrijke eigenschappen](../features/algorithmic-models/predictive-audiences-reporting.md#influential-traits).

 

**Wat gebeurt er met het model als ik een van de basislijneigenschappen of -segmenten bewerk?**

Het model evalueert de eigenschappen of segmenten eenmaal per dag. De dag na de update wordt de bijgewerkte classificatie weergegeven.

 

**Kan ik de databronnen selecteren waarvan het model leert?**

Nee, selectie van databronnen wordt niet ondersteund. De [!UICONTROL Predictive Audiences]-algoritme leert van al uw interne eigenschappen.