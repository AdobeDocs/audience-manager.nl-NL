---
description: Dankzij modellen die zijn afgestemd op look-Alike, kunt u nieuwe, unieke doelgroepen ontdekken via geautomatiseerde gegevensanalyse. In dit artikel worden antwoorden gegeven op de meest gestelde vragen.
seo-description: Dankzij modellen die zijn afgestemd op look-Alike, kunt u nieuwe, unieke doelgroepen ontdekken via geautomatiseerde gegevensanalyse. In dit artikel worden antwoorden gegeven op de meest gestelde vragen.
seo-title: Veelgestelde vragen over look-Alike Modeling
solution: Audience Manager
title: Veelgestelde vragen over look-Alike Modeling
feature: Algorithmic Models
source-git-commit: cf9368d4690b61066646054543cc60d390eea021
workflow-type: tm+mt
source-wordcount: '443'
ht-degree: 0%

---

# Veelgestelde vragen over look-Alike Modeling

## Overzicht {#overview}

In dit artikel worden antwoorden gegeven op de meestgestelde vragen over [!UICONTROL Look-Alike Modeling].

## Vragen {#questions}

**Waarom krijg ik een platte  [!UICONTROL Accuracy & Reach] grafiek?**

Een vlakke [!UICONTROL Accuracy & Reach] grafiek betekent dat bijna elke gebruiker de zelfde score door het model ontving. Dit kan gebeuren wanneer u de eigenschap voor sitebezoekers opneemt in de gegevensbronnen waarop u het model hebt uitgevoerd. Om dit te vermijden, verwijder het generische bezit uit de modelinput tijdens de stap van de modelverwezenlijking, door het [!UICONTROL Exclusions] gebied te gebruiken.

 

**Waarom hebben sommige van mijn invloedrijke trekjes een zeer klein publiek?**

Het algoritme selecteert kenmerken die sterk gecorreleerd zijn met het basislijnkenmerk. Als een bepaalde eigenschap bijvoorbeeld 100% overlapt met de basislijneigenschap, heeft deze een zeer hoog gewicht, zelfs als het aantal gebruikers in die eigenschap klein is.

 

**Waarom is mijn model niet uitgevoerd/herhaald?**

Modellen die resultaten hebben opgeleverd, blijven alleen actief als u ten minste één actieve algoritmische eigenschap hebt gemaakt en deze aan een actief segment en een bestemming hebt toegewezen.

 

**Waarom heeft mijn model geen resultaten opgeleverd?**

Dit wordt doorgaans veroorzaakt door het feit dat de basispopulatie en de populatie in de geselecteerde gegevensbronnen elkaar niet significant overlappen.

 

**Is er een aanbeveling over het basislijnkenmerk of de segmentgrootte?**

Enkele duizenden gebruikers zouden genoeg moeten zijn om het model in werking te stellen, aangezien er aanzienlijke overlappingen zijn tussen de basispopulatie en de populatie in de geselecteerde gegevensbronnen. [!UICONTROL Look-Alike Modeling] geeft nauwkeuriger resultaten, hoe groter de basislijn.

 

**Welke gegevensbronnen van derden moet ik kiezen voor mijn model?**

Gebruik gegevensbronnen die ten minste gedeeltelijk overlappen met uw basislijnkenmerk of -segment, maar zorg er tegelijkertijd voor dat extra gebruikers worden toegevoegd. U zou ook de kosten verbonden aan elke gegevensuitvoer moeten overwegen. De kosten en prijsmodellen variëren tussen gegevensleveranciers in [!UICONTROL Audience Marketplace].

 

**Kosten het om derdegegevens voor modellering te gebruiken?**

Dit hangt af van het prijsmodel van de geselecteerde gegevensinvoer. Sommige feeds maken modellering zonder kosten mogelijk, terwijl anderen u een vergoeding in rekening brengen. Zie [Facturering voor de Kopers van de Invoer van Gegevens](../features/audience-marketplace/marketplace-data-buyers/marketplace-buyer-billing.md) voor details.

 

**Hoeveel modellen/eigenschappen mag ik maken?**

Op dit moment kunt u maximaal 20 algoritmische modellen en 50 algoritmische kenmerken maken.

 

**Wat is de vernieuwingsfrequentie van de modeltraining en algoritmische traitepopulatie?**

Het model wordt om de 8 dagen opnieuw getraind, samen met het vernieuwen van de algoritmische populatie van de eigenschap.