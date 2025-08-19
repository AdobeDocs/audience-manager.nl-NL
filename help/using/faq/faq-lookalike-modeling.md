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
source-wordcount: '420'
ht-degree: 0%

---

# Veelgestelde vragen over look-Alike Modeling

## Overzicht {#overview}

In dit artikel worden antwoorden gegeven op de meestgestelde vragen over [!UICONTROL Look-Alike Modeling] .

## Vragen {#questions}

**waarom ben ik een vlakke [!UICONTROL Accuracy & Reach] grafiek?**

Een vlakke [!UICONTROL Accuracy & Reach] grafiek betekent dat bijna elke gebruiker dezelfde score heeft ontvangen bij het model. Dit kan gebeuren wanneer u de eigenschap voor bezoekers van de site opneemt in de gegevensbronnen waarop u het model hebt uitgevoerd. Als u dit wilt voorkomen, verwijdert u de algemene eigenschap uit de modelinvoer tijdens de stap voor het maken van het model met behulp van het veld [!UICONTROL Exclusions] .

 

**waarom hebben sommige van mijn belangrijkste invloedrijke eigenschappen zeer kleine publiek?**

Het algoritme selecteert kenmerken die sterk gecorreleerd zijn met het basislijnkenmerk. Als een bepaalde eigenschap bijvoorbeeld 100% overlapt met de basislijneigenschap, heeft deze een zeer hoog gewicht, zelfs als het aantal gebruikers in die eigenschap klein is.

 

**waarom heeft mijn model niet in werking gesteld/opnieuw?**

Modellen die resultaten hebben opgeleverd, blijven alleen actief als u ten minste één actieve algoritmische eigenschap hebt gemaakt en deze aan een actief segment en een bestemming hebt toegewezen.

 

**waarom mijn model geen resultaten produceerde?**

Dit wordt doorgaans veroorzaakt door het feit dat de basispopulatie en de populatie in de geselecteerde gegevensbronnen elkaar niet significant overlappen.

 

**is er om het even welke aanbeveling op het basislijnspoor of segmentgrootte?**

Enkele duizenden gebruikers zouden genoeg moeten zijn om het model in werking te stellen, aangezien er aanzienlijke overlappingen zijn tussen de basispopulatie en de populatie in de geselecteerde gegevensbronnen. [!UICONTROL Look-Alike Modeling] levert nauwkeuriger resultaten op, hoe groter de basislijn.

 

**Welke derdegegevensbronnen zouden ik voor mijn model moeten kiezen?**

Gebruik gegevensbronnen die ten minste gedeeltelijk overlappen met uw basislijnkenmerk of -segment, maar zorg er tegelijkertijd voor dat extra gebruikers worden toegevoegd. U zou ook de kosten verbonden aan elke gegevensuitvoer moeten overwegen. De kosten- en prijsmodellen variëren per gegevensaanbieder in [!UICONTROL Audience Marketplace] .

 

**het kost om derdegegevens voor modellering te gebruiken?**

Dit hangt af van het prijsmodel van de geselecteerde gegevensinvoer. Sommige feeds maken modellering zonder kosten mogelijk, terwijl anderen u een vergoeding in rekening brengen. Zie [ het Factureren voor de Kopers van het voer van Gegevens ](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) voor details.

 

**hoeveel modellen/eigenschappen mag ik creëren?**

Op dit moment kunt u maximaal 20 algoritmische modellen en 50 algoritmische kenmerken maken.

 

**wat is verfrist frequentie van de modelopleiding en algoritmische het bezitspopulatie?**

Het model wordt om de 8 dagen opnieuw getraind, samen met het vernieuwen van de algoritmische populatie van de eigenschap.
