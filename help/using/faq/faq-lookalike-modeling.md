---
description: Dankzij modellen die zijn afgestemd op look-Alike, kunt u nieuwe, unieke doelgroepen ontdekken via geautomatiseerde gegevensanalyse. In dit artikel worden antwoorden gegeven op de meest gestelde vragen.
seo-description: Look-Alike Modeling helps you discover new, unique audiences through automated data analysis. This article provides answers to the most frequently asked questions.
seo-title: Look-Alike Modeling FAQ
solution: Audience Manager
title: Veelgestelde vragen over look-Alike Modeling
feature: Algorithmic Models
exl-id: c6e92db0-129f-489e-8cf0-600e0e09698b
source-git-commit: 37823ae54e106e32aa195a6b69e0f1ebfc322f09
workflow-type: tm+mt
source-wordcount: '416'
ht-degree: 0%

---

# Veelgestelde vragen over look-Alike Modeling

## Overzicht {#overview}

In dit artikel worden antwoorden gegeven op de meest gestelde vragen over [!UICONTROL Look-Alike Modeling].

## Vragen {#questions}

**Waarom krijg ik een plat? [!UICONTROL Accuracy & Reach] grafiek?**

Een vlak [!UICONTROL Accuracy & Reach] de grafiek betekent dat bijna elke gebruiker de zelfde score door het model ontving. Dit kan gebeuren wanneer u de eigenschap voor sitebezoekers opneemt in de gegevensbronnen waarop u het model hebt uitgevoerd. Als u dit wilt voorkomen, verwijdert u het algemene kenmerk uit de modelinvoer tijdens de stap voor het maken van het model door het gereedschap [!UICONTROL Exclusions] veld.

 

**Waarom hebben sommige van mijn invloedrijke trekjes een zeer klein publiek?**

Het algoritme selecteert kenmerken die sterk gecorreleerd zijn met het basislijnkenmerk. Als een bepaalde eigenschap bijvoorbeeld 100% overlapt met de basislijneigenschap, heeft deze een zeer hoog gewicht, zelfs als het aantal gebruikers in die eigenschap klein is.

 

**Waarom is mijn model niet uitgevoerd/herhaald?**

Modellen die resultaten hebben opgeleverd, blijven alleen actief als u ten minste één actieve algoritmische eigenschap hebt gemaakt en deze aan een actief segment en een bestemming hebt toegewezen.

 

**Waarom heeft mijn model geen resultaten opgeleverd?**

Dit wordt doorgaans veroorzaakt door het feit dat de basispopulatie en de populatie in de geselecteerde gegevensbronnen elkaar niet significant overlappen.

 

**Is er een aanbeveling over het basislijnkenmerk of de segmentgrootte?**

Enkele duizenden gebruikers zouden genoeg moeten zijn om het model in werking te stellen, aangezien er aanzienlijke overlappingen zijn tussen de basispopulatie en de populatie in de geselecteerde gegevensbronnen. [!UICONTROL Look-Alike Modeling] geeft nauwkeuriger resultaten, hoe groter de basislijn.

 

**Welke gegevensbronnen van derden moet ik kiezen voor mijn model?**

Gebruik gegevensbronnen die ten minste gedeeltelijk overlappen met uw basislijnkenmerk of -segment, maar zorg er tegelijkertijd voor dat extra gebruikers worden toegevoegd. U zou ook de kosten verbonden aan elke gegevensuitvoer moeten overwegen. De kosten- en prijsmodellen verschillen per gegevensaanbieder in [!UICONTROL Audience Marketplace].

 

**Kosten het om derdegegevens voor modellering te gebruiken?**

Dit hangt af van het prijsmodel van de geselecteerde gegevensinvoer. Sommige feeds maken modellering zonder kosten mogelijk, terwijl anderen u een vergoeding in rekening brengen. Zie [Facturering voor kopers van gegevensfeed](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) voor meer informatie.

 

**Hoeveel modellen/eigenschappen mag ik maken?**

Op dit moment kunt u maximaal 20 algoritmische modellen en 50 algoritmische kenmerken maken.

 

**Wat is de vernieuwingsfrequentie van de modeltraining en algoritmische traitepopulatie?**

Het model wordt om de 8 dagen opnieuw getraind, samen met het vernieuwen van de algoritmische populatie van de eigenschap.
