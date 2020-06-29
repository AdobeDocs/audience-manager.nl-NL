---
description: Veelgestelde vragen over de functie van het Laboratorium van de Publiek.
seo-description: Veelgestelde vragen over de functie van het Laboratorium van de Publiek.
seo-title: Veelgestelde vragen over publiek Lab
solution: Audience Manager
title: Veelgestelde vragen over publiek Lab
topic: DIL API
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '349'
ht-degree: 0%

---


# Veelgestelde vragen over publiek Lab{#audience-lab-faq}

Veelgestelde vragen over de functie van het Laboratorium van de Publiek.

<!-- 

audience-lab-faq.xml

 -->

<br> 

**Hebben de testsegmenten die in de testgroepen worden gecreeerd verschillende segment IDs? Hoe kan ik de id&#39;s toewijzen aan verschillende doelen?**

Ja, de testsegmenten hebben verschillende segment-id&#39;s. Voor bestemmingen met [!UICONTROL Auto-fill Destination Mapping] of segmenten die worden verzonden naar [!DNL Google], [!UICONTROL Audience Lab] zullen de toewijzingswaarden enkel als de bestemmingen normaal behandelen.

<br> 

**Kunnen dezelfde omzettingskenmerken aan meerdere testgroepen worden gekoppeld?**

Ja, dat is toegestaan. Denk aan een geval van één test die een mannelijk segment gebruikt verbonden aan conversie X en één test die een vrouwelijk segment verbonden aan conversie X gebruikt. Het maakt niet uit dat beide tests de omzettingen sturen omdat ze twee verschillende soorten publiek testen.

<br> 

**Stel dat een testgroep een geverifieerd profiel gebruikt voor de splitsing van het testsegment. Het geverifieerde profiel is gekoppeld aan UUID&#39;s van 4[Audience Managers](../reference/ids-in-aam.md). Wanneer de bezoeker een omzettingskenmerk van één van de vier UUIDs tentoonstelt,[!UICONTROL Audience Lab]telt dit als één of vier omzettingen?**

In dit geval telt [!UICONTROL Audience Lab] slechts één conversie.

<br> 

**Wat gebeurt er als de bezoeker van de bovenstaande zaak eerst de conversietekenmerken laat zien van een van de vier UUID&#39;s die aan hun geverifieerde profiel zijn gekoppeld en vervolgens ook de conversietekenmerken laat zien van twee andere UUID&#39;s die aan het geverifieerde profiel zijn gekoppeld? Telt dit geval als één of drie omzettingen?**

In dit geval, [!UICONTROL Audience Lab] telt drie omzettingen, één voor elk apparaat dat het authentificatietekenmerk heeft tentoongesteld.

<br> 

**Kan een gebruiker[!UICONTROL Segment: Read-Only]toegang hebben, maar ook toegang tot de creatie van het[!UICONTROL Audience Lab]testsegment?**

Zie [de Testgroep](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) van het Segment voor informatie over hoe te om [!UICONTROL Audience Lab] met [!UICONTROL RBAC] voorrechten te gebruiken.

**Kan ik gebruiken[!UICONTROL Audience Lab]in combinatie met[!UICONTROL Profile Link Device Graph]en externe apparaatgrafieken ([Adobe Experience Cloud Device Co-op](https://docs.adobe.com/content/help/en/device-co-op/using/home.html), Tapad Device Graph, Liveramp Device Graph)?**

Vooralsnog [!UICONTROL Audience Lab] kunnen segmentpopulaties alleen worden opgedeeld door de apparaten die zijn aangesloten op een gekwalificeerd apparaat wanneer u het [!UICONTROL Profile Link Device Graph]apparaat gebruikt. Wij werken aan het toevoegen van ondersteuning in [!UICONTROL Audience Lab] de andere apparaatgrafieken en zullen u laten weten wanneer wij dat doen.
