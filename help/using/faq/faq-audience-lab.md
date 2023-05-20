---
description: Veelgestelde vragen over het onderdeel Audience Lab.
seo-description: Frequently asked questions about the Audience Lab feature.
seo-title: Audience Lab FAQ
solution: Audience Manager
title: Veelgestelde vragen over Audience Lab
uuid: b1daf99d-af60-4f65-987d-794a6d45d566
feature: Audience Lab
exl-id: 25bdabb5-2ba8-45d2-81ca-05c0590d7d96
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 94%

---

# Veelgestelde vragen over Audience Lab{#audience-lab-faq}

Veelgestelde vragen over het onderdeel Audience Lab.

<br>

**Hebben de testsegmenten die in de testgroepen zijn gemaakt, verschillende segment-id’s? Hoe kan ik de id’s toewijzen aan verschillende bestemmingen?**

Ja, de testsegmenten hebben verschillende segment-id’s. Voor bestemmingen met [!UICONTROL Auto-fill Destination Mapping] of segmenten die worden verzonden naar [!DNL Google], zal [!UICONTROL Audience Lab] de toewijzingswaarden net zo behandelen als de bestemmingen normaal zouden doen.

<br>

**Kan dezelfde conversie-eigenschap aan meerdere testgroepen worden gekoppeld?**

Ja, dat is toegestaan. Denk aan een geval van één test die een mannelijk segment gebruikt dat is gekoppeld aan conversie X, en één test die een vrouwelijk segment gebruikt dat is gekoppeld aan conversie X.Het maakt niet uit dat beide tests conversies aansturen, omdat ze twee verschillende soorten doelgroepen testen.

<br>

**Stel dat een testgroep een geverifieerd profiel gebruikt voor de testsegmentsplitsing. Het geverifieerde profiel is gekoppeld aan vier [Audience Manager](../reference/ids-in-aam.md)-UUID’s. Wanneer de bezoeker een conversie-eigenschap van een van de vier UUID’s vertoont, telt [!UICONTROL Audience Lab] dit dan als één of vier conversies?**

In dit geval telt [!UICONTROL Audience Lab] slechts één conversie.

<br>

**Wat gebeurt er als de bezoeker in het bovenstaande scenario eerst de conversie-eigenschap vertoont van een van de vier UUID’s die aan zijn of haar geverifieerde profiel zijn gekoppeld, en vervolgens ook de conversie-eigenschap vertoont van twee andere UUID’s die aan het geverifieerde profiel zijn gekoppeld? Telt dit geval als één of drie conversies?**

In dit geval telt [!UICONTROL Audience Lab] drie conversies, één voor elk apparaat dat de verificatie-eigenschap heeft vertoond.

<br>

**Kan een gebruiker [!UICONTROL Segment: Read-Only] toegang hebben, maar ook toegang tot het maken van [!UICONTROL Audience Lab]-testsegmenten?**

Zie [Segmenttestgroep maken](../features/audience-lab/audience-lab-manage-test-groups.md#create-test-groups) voor informatie over het gebruik van [!UICONTROL Audience Lab] met [!UICONTROL RBAC]-rechten.

**Kan ik gebruiken [!UICONTROL Audience Lab] in samenhang met de [!UICONTROL Profile Link Device Graph] en externe apparaatgrafieken (Tapad Device Graph, Liveramp Device Graph)?**

Vooralsnog kunnen segmentpopulaties in [!UICONTROL Audience Lab] alleen worden opgedeeld volgens de apparaten die zijn aangesloten op een gekwalificeerd apparaat wanneer u [!UICONTROL Profile Link Device Graph] gebruikt. Wij werken aan het toevoegen van ondersteuning in [!UICONTROL Audience Lab] voor de andere apparaatgrafieken en zullen u laten weten wanneer dat is gebeurd.
