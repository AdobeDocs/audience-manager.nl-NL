---
description: Met Trait Recommendations, wanneer u een segment in de Bouwer van het Segment bouwt of uitgeeft, krijgt u aanbevelingen op extra eigenschappen u kunt omvatten, die aan de eigenschappen in de segmentregel gelijkaardig zijn. Voeg de geadviseerde eigenschappen aan uw segment toe om uw doelpubliek te verhogen.
seo-description: Krijg levende trekaanbevelingen aangezien u uw segmenten bouwt.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1573'
ht-degree: 8%

---


# Trait Recommendations

Krijg de levende aanbevelingen van het dienstreis aangezien u uw segmenten, van uw eigen eerstepartijeigenschappen, en [!UICONTROL Audience Marketplace] gegevensvoer bouwt.

## Videodemonstratie

Bekijk eerst de [!UICONTROL Trait Recommendations] video hieronder en lees vervolgens verder voor meer informatie. De videodemonstratie toont u hoe te met aanbevelingen van uw eigen eerstepartijeigenschappen te werken, evenals traiteaanbevelingen van [!UICONTROL Audience Marketplace] gegevensvoer dat *u reeds aan* wordt geabonneerd.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

De volgende video schetst de werkstroom voor [!UICONTROL Marketplace Recommendations], die u toont hoe te om eigenschappen aan uw segmenten toe te voegen, die op aanbevelingen van gegevensvoer in [!UICONTROL Audience Marketplace] worden gebaseerd. Deze aanbevelingen zijn gebaseerd op gegevensvoer dat *u niet aan* wordt geabonneerd.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Overzicht

[!UICONTROL Trait Recommendations], aangedreven door  [!DNL Adobe Sensei], brengt gegevenswetenschap in uw dagelijkse werkstromen van de Audience Manager.
Met [!UICONTROL Trait Recommendations], wanneer u een segment in [de Bouwer van het Segment ](segment-builder.md) bouwt of uitgeeft, krijgt u aanbevelingen op extra eigenschappen u kunt omvatten, die aan de eigenschappen in de segmentregel gelijkaardig zijn.

De Audience Manager toont u trekaanbevelingen zowel van uw eerste-partijeigenschappen, in **[!UICONTROL Recommendations]** sectie, als van **[!UICONTROL Audience Marketplace]**, in **[!UICONTROL Recommendations from Marketplace]** sectie.

Voeg de geadviseerde eigenschappen aan uw segment toe om uw doelpubliek te verhogen.

![Overzicht van Trait Recommendations](assets/trait-recommendations-overview-full.png)

**In een notendop:**

* Audience Manager toont eerste partijeigenschappen in [!UICONTROL Recommendations] sectie. De aanbevelingen van de Marketplace van openbare en privé voer dat u niet aan wordt geabonneerd zijn zichtbaar in [!UICONTROL Recommendations from Marketplace] sectie. Klik op de naam van de feed om naar [!UICONTROL Audience Marketplace] te gaan en u te abonneren.
* De Audience Manager toont een maximum van vijftig eigenschappen gelijkend op in de segmentregel.
* U kunt de gegevensbronnen filteren waarvan u geen aanbevelingen wilt zien.
* Bij het berekenen van gelijkenissen, overweegt de Audience Manager [UUIDs](../../reference/ids-in-aam.md) die voor het dienteken tijdens de laatste 30 dagen kwalificeerden.
* Als het foutbericht &quot;Geen vergelijkbare kenmerken gevonden. De eigenschap(pen) is mogelijk te nieuw.&quot;, wat betekent dat er in de laatste 30 dagen geen activiteit voor die eigenschap heeft plaatsgevonden, of dat de Audience Manager de aanbevelingen voor die eigenschap nog niet heeft bijgewerkt. Probeer het over 24 uur opnieuw.

## Gevallen gebruiken

Met [!UICONTROL Trait Recommendations], kunt u uw werkschema&#39;s verbeteren, afhankelijk van hoe u Audience Manager gebruikt:

* Als marketeer, kunt u snel publiek vinden in complementaire producten met behulp van gelijkaardige eigenschappen, zodat u uw bereik kunt verhogen.
* Als u Audience Manager als uitgever, met [!UICONTROL Trait Recommendations] gebruikt, kunt u publieksgedrag begrijpen en betere segmenten voor advertentieverkoop of gebruikersverwerving bouwen.
* Als [!UICONTROL Audience Marketplace] gegevenskoper, wil ik relevante derdegegevens ontdekken zonder door een groot aantal feeds te doorbladeren.
* Als [!UICONTROL Audience Marketplace] gegevensleverancier, wil ik relevante gegevens aan kopers aanbevelen zodat ik van optimale en relevante abonnementen kan profiteren.

## Verschillen tussen Trait Recommendations en Algorithmic Models

### Algorithmic Models

[!UICONTROL Algorithmic Models]Met worden niet alleen de meest invloedrijke eigenschappen gevonden, maar worden gebruikers ook geturfd op basis van deze eigenschappen en wordt aan elke gebruiker een afzonderlijke score toegewezen. Vervolgens maakt u algoritmische eigenschappen om uw gebruikers te targeten. Met nauwkeurigheid en bereikcontroles in [!UICONTROL Trait Builder], kunt u specificeren welke gebruikers onder allen die de invloedrijke eigenschappen hebben u wilt richten.

[!UICONTROL Algorithmic Models]Met kunt u gebruikers op verschillende nauwkeurigheidsniveaus selecteren en in testen welke groep gebruikers het beste converteert.[!UICONTROL Audience Lab] Zie het gedetailleerde gebruiksscenario in [Modellen vergelijken in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models], loopt het model om acht dagen en verfrist de gebruikers die voor algoritmische eigenschappen worden gekwalificeerd.

### Trait Recommendations

[!UICONTROL Trait Recommendations] is een snelle manier om inzicht te krijgen in andere eigenschappen die lijken op degene die u in een segment gebruikt.

U moet [!UICONTROL Trait Recommendations] gebruiken wanneer:

* U hebt snelle inzichten nodig tijdens het bouwen van een segment;
* U gebruikt de segmenten voor korte campagnes of wanneer u snelle suppressie wilt toepassen op een converterende doelgroep;
* U probeert het bereik te maximaliseren.

## Workflow

Wanneer het bouwen van of het uitgeven van een segment in [de Bouwer van het Segment](segment-builder.md), kunt u eigenschappen gelijkend op de eigenschappen in de segmentregel onderzoeken. De [Segment Builder](segment-builder.md)-workflow lijkt sterk op die voor nieuwe en bestaande segmenten:

### Nieuwe segmenten

1. Ga naar **Gegevens van het publiek > Segmenten**, en klik **Nieuwe toevoegen**.
1. Voeg in de vervolgkeuzelijst **Traits** ten minste één eigenschap toe aan de segmentregel.
1. U kunt eerste-partij geadviseerde eigenschappen en [!UICONTROL Audience Marketplace] de aanbevelingen van het dienstreis van voer zien dat u aan, in **[!UICONTROL Recommendations]** sectie wordt geabonneerd. In de sectie **[!UICONTROL Recommendations from Marketplace]** ziet u aanbevelingen voor de eigenschap van feeds waarop u niet bent geabonneerd. Al deze aanbevelingen zijn gelijkaardig aan de eigenschappen u aan de segmentregel toevoegde. Schuif omlaag om alle aanbevolen kenmerken weer te geven.
1. (Optioneel) Als u aanbevolen eerstekenkenmerken van bepaalde gegevensbronnen wilt uitsluiten, klikt u op het symbool **X** voor de gegevensbronnen die u wilt uitsluiten.

   >[!NOTE]
   >
   >De uitgesloten gegevensbronnen worden net boven de lijst met aanbevolen kenmerken weergegeven. Klik **X** in het grijze vakje om de uitsluitingen te verwijderen en resultaten van de respectieve gegevensbronnen opnieuw te zien.
1. Om geadviseerde eigenschappen aan de segmentregel toe te voegen, klik **+** symbool.

>[!IMPORTANT]
>
>Wanneer u [!UICONTROL Marketplace] eigenschappen aan een segment toevoegt, worden de eigenschappen slechts gebruikt voor segmentschatting, tot u aan het overeenkomstige gegevensvoer intekent. Traits die afkomstig zijn van gegevensfeeds waarop u zich niet hebt geabonneerd, worden gemarkeerd met een winkelwagentje in de lijst met handelsmerken. Klik op de naam van het kenmerk om naar de pagina met gegevensinvoer te gaan en u erop te abonneren.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>U kunt een segment alleen met externe kenmerken opslaan nadat u zich aan de bijbehorende gegevensfeeds hebt geabonneerd.

### Bestaande segmenten

1. Ga naar **[!UICONTROL Audience Data]>[!UICONTROL Segments]**, selecteer het segment u wilt uitgeven en klik ![uitgeven](assets/edit-button.png).
1. Schuif omlaag naar de vervolgkeuzelijst [!UICONTROL Traits].
1. U kunt geadviseerde eigenschappen zien, die aan de eigenschappen reeds in de segmentregel gelijkaardig zijn. Schuif omlaag om alle aanbevolen kenmerken weer te geven.
1. (Optioneel) Als u aanbevolen kenmerken wilt uitsluiten van bepaalde gegevensbronnen, klikt u op het symbool **X** voor de gegevensbronnen die u wilt uitsluiten.

   >[!NOTE]
   >
   >De uitgesloten gegevensbronnen worden net boven de lijst met aanbevolen kenmerken weergegeven. Klik **X** in het grijze vakje om de uitsluitingen te verwijderen en resultaten van de respectieve gegevensbronnen opnieuw te zien.
1. Om geadviseerde eigenschappen aan de segmentregel toe te voegen, klik **+** symbool.

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
>De geadviseerde eigenschappen kunnen uw eerstepartijeigenschappen of derderderehandel van gegevensvoer zijn dat u in [!UICONTROL Audience Marketplace] wordt geabonneerd.

## Hoe het werkt

Voor het opstellen van aanbevelingen op het gebied van de eigenschap, berekent Audience Manager de [Jaccard gelijkenis](https://en.wikipedia.org/wiki/Jaccard_index) tussen de doeleigenschap en elke andere eigenschap waartoe uw account toegang heeft, met inbegrip van gegevens van derden. Audience Manager geeft dan tot vijftig kenmerken weer die het hoogst op elkaar lijken.

## Score voor gelijksoortige activiteit {#trait-similarity-score}

Audience Manager berekent de [!UICONTROL Trait Similarity Score] tussen twee eigenschappen door de doorsnede en de samenvoeging in termen van het aantal [!UICONTROL UUID]s te berekenen en dan twee te verdelen. Voor twee kenmerken A en B ziet de berekening er als volgt uit:

![jaccard-gelijkenis](assets/jaccard_similarity.png)

Zie ook de twee onderstaande voorbeelden.

### Voorbeeld 1 - Gelijksoortige score met laag bereik

Gezien twee eigenschappen A en B, laten wij zeggen elk van de eigenschappen een bevolking van 1.000.000 [!UICONTROL UUID]s heeft, waarvan 25.000 [!UICONTROL UUID]s voor beide eigenschappen in aanmerking komt.
Met de bovenstaande formule resulteert dit in: 25,000 / 1,975,000 = 0,012. Dit is een lage [!UICONTROL Trait Similarity Score], de twee eigenschappen zijn zeer verschillend.

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### Voorbeeld 2 - Score met gelijksoortige trajecten

Als dezelfde kenmerken A en B 400.000 [!UICONTROL UUID]s hadden die voor beide kenmerken in aanmerking kwamen, is [!UICONTROL Trait Similarity Score] veel hoger:
400,000 / 1,600,000 = 0,25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### Hoe te om de Score van de Gelijksheid van het Beetje te interpreteren

Gebruik de onderstaande tabel als een ruwe richtlijn voor de gelijkenis van de afbeelding. Deze gids is gebaseerd op de gelijkenisscores die in de meeste kenmerken zijn waargenomen.

| [!UICONTROL Trait Similarity Score] | Significantie |
---------|----------|
| 0.1 en hoger | Hoge overeenkomst tussen kenmerken |
| 0,03 - 0,1 | Normale overeenkomst tussen kenmerken |
| 0,01 - 0,03 | Lage overeenkomst tussen kenmerken |
| 0 - 0,01 | Zeer lage overeenkomsten tussen eigenschappen |

## Rolgebaseerde toegangscontrole (RBAC)

Voor bedrijven die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) gebruiken, moet u toestemming hebben om segmenten tot stand te brengen en uit te geven om geadviseerde eigenschappen te zien. De aanbevelingen van de eigenschap die u ziet zijn slechts degenen van gegevensbronnen die u toegang tot via [!UICONTROL RBAC] hebt.

>[!IMPORTANT]
>
>Als u [!UICONTROL Marketplace Recommendations] aan een segment wilt toevoegen, moeten gebruikers zich eerst abonneren op de corresponderende gegevensfeeds. Alleen gebruikers met beheerdersrechten kunnen zich abonneren op [!UICONTROL Audience Marketplace] gegevensfeeds.

Meer informatie over [!UICONTROL RBAC] besturingselementen [hier](../administration/administration-overview.md).

## Beperkingen

* Op dit moment worden mapkenmerken niet als aanbevolen kenmerken weergegeven in Audience Manager. Lees meer over omslageigenschappen [hier](../traits/manage-folder-traits.md).
* Bij het weergeven van Trait Recommendations houdt Audience Manager geen rekening met [!DNL Boolean]-operatoren ([!DNL AND], [!DNL OR], [!DNL NOT]) in segmentregels.
