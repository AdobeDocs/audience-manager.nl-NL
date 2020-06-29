---
description: Met de Aanbevelingen van het Aanzicht, wanneer u een segment in de Bouwer van het Segment bouwt of uitgeeft, krijgt u aanbevelingen op extra eigenschappen u kunt omvatten, die aan de eigenschappen in de segmentregel gelijkaardig zijn. Voeg de geadviseerde eigenschappen aan uw segment toe om uw doelpubliek te verhogen.
seo-description: Krijg levende trekaanbevelingen aangezien u uw segmenten bouwt.
seo-title: Aanbevolen stappen
solution: Audience Manager
title: Aanbevolen stappen
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 0%

---


# Aanbevolen stappen

Krijg de levende aanbevelingen van het dienstreis aangezien u uw segmenten, van uw eigen eerstepartijeigenschappen, en [!UICONTROL Audience Marketplace] gegevensvoer bouwt.

## Videodemonstratie

Bekijk eerst de onderstaande [!UICONTROL Trait Recommendations] video en lees vervolgens de video voor meer informatie. De videodemonstratie laat u zien hoe u met aanbevelingen van uw eigen eerderedienaarseigenschappen werkt, evenals aanbevelingen van de eigenschap van [!UICONTROL Audience Marketplace] gegevensvoer die *u reeds aan* wordt geabonneerd.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

In de volgende video wordt een overzicht gegeven van de workflow voor [!UICONTROL Marketplace Recommendations], waarin u kunt zien hoe u kenmerken aan uw segmenten kunt toevoegen op basis van aanbevelingen van gegevensfeeds in [!UICONTROL Audience Marketplace]. Deze aanbevelingen zijn gebaseerd op gegevensvoer waarop *u niet bent geabonneerd*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Overzicht

[!UICONTROL Trait Recommendations], aangedreven door [!DNL Adobe Sensei], brengt gegevenswetenschap in uw dagelijkse werkstromen van de Audience Manager.
Met [!UICONTROL Trait Recommendations], wanneer u bouwt of een segment in de Bouwer [van het](segment-builder.md)Segment uitgeeft, krijgt u aanbevelingen op extra eigenschappen u kunt omvatten, die aan de eigenschappen in de segmentregel gelijkaardig zijn.

De Audience Manager toont u de aanbevelingen van de eigenschap van zowel uw eerste partij, in de **[!UICONTROL Recommendations]** sectie, als van **[!UICONTROL Audience Marketplace]**, in de **[!UICONTROL Recommendations from Marketplace]** sectie.

Voeg de geadviseerde eigenschappen aan uw segment toe om uw doelpubliek te verhogen.

![Overzicht van reisaanbevelingen](assets/trait-recommendations-overview-full.png)

**In een notendop:**

* In de [!UICONTROL Recommendations] sectie ziet u de eigenschappen van de eerste partij. De aanbevelingen van de Marketplace van openbare en privé voer u niet aan wordt geabonneerd zijn zichtbaar in de [!UICONTROL Recommendations from Marketplace] sectie. Klik op de naam van de feed waarnaar u wilt gaan [!UICONTROL Audience Marketplace] en zich wilt abonneren.
* De Audience Manager toont een maximum van vijftig eigenschappen gelijkend op in de segmentregel.
* U kunt de gegevensbronnen filteren waarvan u geen aanbevelingen wilt zien.
* Bij het berekenen van gelijkenissen, beschouwt Audience Manager [UUIDs](../../reference/ids-in-aam.md) die voor het bezit in de afgelopen 30 dagen in aanmerking kwamen.
* Als het foutbericht &quot;Geen vergelijkbare kenmerken gevonden. De eigenschap(pen) is mogelijk te nieuw.&quot;, wat betekent dat er in de laatste 30 dagen geen activiteit voor die eigenschap heeft plaatsgevonden, of dat de Audience Manager de aanbevelingen voor die eigenschap nog niet heeft bijgewerkt. Probeer het over 24 uur opnieuw.

## Gevallen gebruiken

Met [!UICONTROL Trait Recommendations], kunt u uw werkschema&#39;s verbeteren, afhankelijk van hoe u Audience Manager gebruikt:

* Als marketeer, kunt u snel publiek vinden in complementaire producten met behulp van gelijkaardige eigenschappen, zodat u uw bereik kunt verhogen.
* Als u Audience Manager als uitgever gebruikt, met [!UICONTROL Trait Recommendations], kunt u publieksgedrag begrijpen en betere segmenten voor advertentieverkoop of gebruikersverwerving bouwen.
* Als [!UICONTROL Audience Marketplace] gegevenskoper wil ik relevante gegevens van derden ontdekken zonder door een groot aantal feeds te bladeren.
* Als [!UICONTROL Audience Marketplace] gegevensaanbieder wil ik kopers relevante gegevens aanbevelen zodat ik gebruik kan maken van optimale en relevante abonnementen.

## Verschillen tussen Trait Recommendations en Algorithmic Models

### Algorithmic Models

[!UICONTROL Algorithmic Models] niet alleen de meest invloedrijke kenmerken worden gevonden , maar ook gebruikers worden op basis van deze kenmerken gescand en aan iedere gebruiker wordt een individuele score toegekend . Vervolgens maakt u algoritmische kenmerken om uw gebruikers als doel in te stellen. Met nauwkeurigheid en bereikbesturingselementen in de [!UICONTROL Trait Builder]handleiding kunt u opgeven welke gebruikers u wilt gebruiken onder alle gebruikers die de invloedrijke kenmerken hebben waarop u zich wilt richten.

[!UICONTROL Algorithmic Models] Hiermee kunt u gebruikers op verschillende nauwkeurigheidsniveaus selecteren en testen [!UICONTROL Audience Lab] welke gebruikersgroep het beste converteert. Zie het gedetailleerde gebruiksgeval in [Compare Modellen in het Laboratorium](../../features/audience-lab/audience-lab-use-cases.md#compare-models)van de Publiek.

In [!UICONTROL Algorithmic Models], loopt het model om acht dagen en verfrist de gebruikers die voor algoritmische eigenschappen worden gekwalificeerd.

### Aanbevolen stappen

[!UICONTROL Trait Recommendations] Dit is een snelle manier om inzicht te krijgen in andere eigenschappen die vergelijkbaar zijn met de eigenschappen die u in een segment gebruikt.

U dient te gebruiken [!UICONTROL Trait Recommendations] wanneer:

* U hebt snelle inzichten nodig terwijl het bouwen van een segment;
* U gebruikt de segmenten voor korte campagnes of wanneer u publiek snel wilt onderdrukken die omzet;
* U probeert het bereik te maximaliseren.

## Workflow

Wanneer het bouwen van of het uitgeven van een segment in de Bouwer [van het](segment-builder.md)Segment, kunt u eigenschappen gelijkend op de eigenschappen in de segmentregel onderzoeken. De workflow [Segment Builder](segment-builder.md) lijkt sterk op die voor nieuwe en bestaande segmenten:

### Nieuwe segmenten

1. Ga naar **Poortgegevens > Segmenten** en klik op **Nieuwe** toevoegen.
1. In de drop-down doos van **Tanden** , voeg minstens één eigenschap aan de segmentregel toe.
1. U kunt de door de eerste partij aanbevolen eigenschappen en aanbevelingen voor [!UICONTROL Audience Marketplace] kenmerken van feeds bekijken waarop u bent geabonneerd, in de **[!UICONTROL Recommendations]** sectie. In de **[!UICONTROL Recommendations from Marketplace]** sectie ziet u aanbevelingen met kenmerken van feeds waarop u zich niet hebt geabonneerd. Al deze aanbevelingen zijn gelijkaardig aan de eigenschappen u aan de segmentregel toevoegde. Schuif omlaag om alle aanbevolen kenmerken weer te geven.
1. (Optioneel) Als u aanbevolen eerdereportretten wilt uitsluiten van bepaalde gegevensbronnen, klikt u op het **X** -symbool voor de gegevensbronnen die u wilt uitsluiten.

   >[!NOTE]
   >
   >De uitgesloten gegevensbronnen worden net boven de lijst met aanbevolen kenmerken weergegeven. Klik op **X** in het grijze vak om de uitsluitingen te verwijderen en de resultaten van de respectievelijke gegevensbronnen weer te zien.
1. Klik op het symbool **+** om aanbevolen kenmerken aan de segmentregel toe te voegen.

>[!IMPORTANT]
>
>Wanneer het toevoegen van [!UICONTROL Marketplace] eigenschappen aan een segment, worden de eigenschappen slechts gebruikt voor segmentschatting, tot u aan het overeenkomstige gegevensvoer intekent. Traits die afkomstig zijn van gegevensfeeds waarop u zich niet hebt geabonneerd, worden gemarkeerd met een winkelwagentje in de lijst met handelsmerken. Klik op de naam van het kenmerk om naar de pagina met gegevensinvoer te gaan en u erop te abonneren.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>U kunt een segment alleen met externe kenmerken opslaan nadat u zich aan de bijbehorende gegevensfeeds hebt geabonneerd.

### Bestaande segmenten

1. Ga naar **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, selecteer het segment u wilt uitgeven en klik![uitgeven](assets/edit-button.png).
1. Blader omlaag naar het [!UICONTROL Traits] vervolgkeuzemenu.
1. U kunt geadviseerde eigenschappen zien, die aan de eigenschappen reeds in de segmentregel gelijkaardig zijn. Schuif omlaag om alle aanbevolen kenmerken weer te geven.
1. (Optioneel) Als u aanbevolen kenmerken wilt uitsluiten van bepaalde gegevensbronnen, klikt u op het **X** -symbool voor de gegevensbronnen die u wilt uitsluiten.

   >[!NOTE]
   >
   >De uitgesloten gegevensbronnen worden net boven de lijst met aanbevolen kenmerken weergegeven. Klik op **X** in het grijze vak om de uitsluitingen te verwijderen en de resultaten van de respectievelijke gegevensbronnen weer te zien.
1. Klik op het symbool **+** om aanbevolen kenmerken aan de segmentregel toe te voegen.

Wanneer u een segment maakt of bewerkt en een kenmerk aan de segmentregel toevoegt, ziet u een maximum van vijftig aanbevolen kenmerken, vergelijkbaar met de eigenschap die u hebt toegevoegd. Als de segmentregel meer dan één eigenschap bevat, gebruikt de Audience Manager een ronde robinmethode om de beste gelijke voor elk bezit te tonen, dan de tweede-beste gelijke voor elk bezit, etc., voor de grootste vijftig eigenschappen door populatie, in de segmentregel.

![Drie basiskenmerken](assets/three-base-traits.png)

Bijvoorbeeld, wanneer er drie eigenschappen in de segmentregel zijn, zoals hieronder getoond, zijn de geadviseerde eigenschappen:

1. Beste overeenkomst voor kenmerk 3 (de eigenschap met de grootste populatie);
1. Beste overeenkomst voor kenmerk 1;
1. Beste overeenkomst voor kenmerk 2;
1. Tweede beste overeenkomst voor kenmerk 3;
1. De op één na beste overeenkomst voor eigenschap 1, etc. tot u aan vijftig eigenschappen krijgt.

Om aanbevelingen voor een specifiek bezit te krijgen, kunt u op de eigenschappen in de segmentregel (1) of in de geadviseerde mening van het Dienstverband (2) klikken.

![base-traits-example](assets/three-base-traits-numbered.png)

Als u op een eersteklas kenmerk klikt, wordt een pop-upvenster geopend, zoals in de onderstaande afbeelding wordt getoond. Als de geadviseerde eigenschappen geen deel van het segment uitmaken, kunt u hen aan het segment toevoegen door **+** te drukken.

![toe:voegen-aan-segment](assets/add_to_segments.png)

>[!TIP]
>
>De uitgesloten gegevensbronnen van de hoofdpagina worden overwogen terwijl het produceren van aanbevelingen binnen het pop-up venster van de eigenschapinformatie. En als u gegevensbronnen in deze weergave uitsluit, gelden de uitsluitingen voor de hoofdpagina.

>[!NOTE]
>
>Aanbevolen kenmerken kunnen de kenmerken van de eerste partij zijn of de eigenschappen van derden van gegevensfeeds waarop u zich hebt geabonneerd [!UICONTROL Audience Marketplace].

## Hoe het werkt

Voor het opstellen van aanbevelingen op het gebied van de eigenschap, berekent de Audience Manager de [Jaccard gelijkenis](https://en.wikipedia.org/wiki/Jaccard_index) tussen de doeleigenschap en elke andere eigenschap waartoe uw account toegang heeft, met inbegrip van gegevens van derden. Audience Manager geeft dan tot vijftig kenmerken weer die het hoogst op elkaar lijken.

## Gelijksoortige score volgen {#trait-similarity-score}

De Audience Manager berekent de [!UICONTROL Trait Similarity Score] tussen twee eigenschappen door de intersection en union te berekenen in termen van het aantal [!UICONTROL UUID]s en dan de twee te verdelen. Voor twee kenmerken A en B ziet de berekening er als volgt uit:

![jaccard-gelijkenis](assets/jaccard_similarity.png)

Zie ook de twee onderstaande voorbeelden.

### Voorbeeld 1 - Gelijksoortige score met laag bereik

Met twee kenmerken A en B heeft elk kenmerk een populatie van 1.000.000 [!UICONTROL UUID]s, waarvan 25.000 in aanmerking [!UICONTROL UUID]komen voor beide kenmerken.
Met de bovenstaande formule resulteert dit in: 25,000 / 1,975,000 = 0,012. Dit is een lage waarde [!UICONTROL Trait Similarity Score], de twee kenmerken zijn zeer verschillend.

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### Voorbeeld 2 - Score met gelijksoortige trajecten

Als dezelfde kenmerken A en B 400.000 [!UICONTROL UUID]s hadden die voor beide kenmerken in aanmerking kwamen, [!UICONTROL Trait Similarity Score] is het veel hoger:
400,000 / 1,600,000 = 0,25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### Hoe te om de Score van de Gelijksheid van het Beetje te interpreteren

Gebruik de onderstaande tabel als een ruwe richtlijn voor de gelijkenis van de afbeelding. Deze gids is gebaseerd op de gelijkenisscores die in de meeste kenmerken zijn waargenomen.

| [!UICONTROL Trait Similarity Score] | Significantie |
---------|----------|
| 0.1 en hoger | Hoge overeenkomst tussen kenmerken |
| 0.03 - 0.1 | Normale overeenkomst tussen kenmerken |
| 0.01 - 0.03 | Lage overeenkomst tussen kenmerken |
| 0 - 0.01 | Zeer lage overeenkomsten tussen eigenschappen |

## Rolgebaseerde toegangscontrole (RBAC)

Voor bedrijven die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) gebruiken, moet u toestemming hebben om segmenten tot stand te brengen en uit te geven om geadviseerde eigenschappen te zien. De aanbevelingen van de eigenschap die u ziet zijn slechts degenen van gegevensbronnen die u toegang tot via hebt [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Gebruikers moeten zich eerst abonneren op de overeenkomstige gegevensfeeds om [!UICONTROL Marketplace Recommendations] aan een segment toe te voegen. Alleen gebruikers met beheerdersrechten kunnen zich abonneren op [!UICONTROL Audience Marketplace] gegevensfeeds.

Lees meer over [!UICONTROL RBAC] besturingselementen [hier](../administration/administration-overview.md).

## Beperkingen

* Op dit moment worden mapkenmerken niet als aanbevolen kenmerken weergegeven in Audience Manager. Lees [hier](../traits/manage-folder-traits.md)meer over mapkenmerken.
* Bij het tonen van de Aanbevelingen van het Spoor, houdt de Audience Manager geen rekening met [!DNL Boolean] exploitanten ([!DNL AND], [!DNL OR], [!DNL NOT]) in segmentregels.
