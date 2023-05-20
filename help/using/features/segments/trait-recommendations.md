---
description: Met Trait Recommendations, wanneer u een segment in de Bouwer van het Segment bouwt of uitgeeft, krijgt u aanbevelingen op extra eigenschappen u kunt omvatten, die aan de eigenschappen in de segmentregel gelijkaardig zijn. Voeg de geadviseerde eigenschappen aan uw segment toe om uw doelpubliek te verhogen.
seo-description: Get live trait recommendations as you build your segments.
seo-title: Trait Recommendations
solution: Audience Manager
title: Trait Recommendations
feature: Segments
exl-id: 7ef862a9-7354-49fb-9af0-925d827a5165
source-git-commit: 432b12c4d4fb567d1a0bcaa9d12baaac5e3ae0f7
workflow-type: tm+mt
source-wordcount: '1562'
ht-degree: 8%

---

# Trait Recommendations

Krijg de levende aanbevelingen van het dienstreis aangezien u uw segmenten, van uw eigen eerstepartijeigenschappen bouwt, en [!UICONTROL Audience Marketplace] gegevensfeeds.

## Videodemonstratie

Begin met het bekijken van de [!UICONTROL Trait Recommendations] video hieronder, dan lees op voor meer informatie. De videodemonstratie laat u zien hoe u kunt werken met aanbevelingen van uw eigen eerderheidstolerantie en met aanbevelingen van trainingen [!UICONTROL Audience Marketplace] gegevensfeeds die *je bent al geabonneerd op*.

>[!VIDEO](https://video.tv.adobe.com/v/26228/)

In de volgende video wordt de workflow voor [!UICONTROL Marketplace Recommendations], die u tonen hoe te om eigenschappen aan uw segmenten toe te voegen die op aanbevelingen van gegevensvoer in worden gebaseerd [!UICONTROL Audience Marketplace]. Deze aanbevelingen zijn gebaseerd op gegevensfeeds die *je bent niet geabonneerd op*.

>[!VIDEO](https://video.tv.adobe.com/v/29363/)

## Overzicht

[!UICONTROL Trait Recommendations], aangedreven door [!DNL Adobe Sensei], brengt gegevenswetenschap in uw dagelijkse workflows van de Audience Manager.
Met [!UICONTROL Trait Recommendations], wanneer u een segment maakt of bewerkt in [Segment Builder](segment-builder.md), krijgt u aanbevelingen op extra eigenschappen u kunt omvatten, die aan de eigenschappen in de segmentregel gelijkaardig zijn.

De Audience Manager toont u de aanbevelingen van de eigenschap zowel van uw eerste partij, in **[!UICONTROL Recommendations]** en van **[!UICONTROL Audience Marketplace]** in de **[!UICONTROL Recommendations from Marketplace]** sectie.

Voeg de geadviseerde eigenschappen aan uw segment toe om uw doelpubliek te verhogen.

![Overzicht van Trait Recommendations](assets/trait-recommendations-overview-full.png)

**In een notendop:**

* Audience Manager toont de eigenschappen van de eerste partij in de [!UICONTROL Recommendations] sectie. De aanbevelingen van de Marketplace van openbare en privé voer u niet aan wordt geabonneerd zijn zichtbaar in [!UICONTROL Recommendations from Marketplace] sectie. Klik op de naam van de feed waarnaar u wilt gaan [!UICONTROL Audience Marketplace] en abonneren.
* De Audience Manager toont een maximum van vijftig eigenschappen gelijkend op in de segmentregel.
* U kunt de gegevensbronnen filteren waarvan u geen aanbevelingen wilt zien.
* Bij het berekenen van overeenkomsten houdt de Audience Manager rekening met [UUID&#39;s](../../reference/ids-in-aam.md) die in de laatste 30 dagen voor de eigenschap in aanmerking kwam.
* Als het foutbericht &quot;Geen vergelijkbare kenmerken gevonden. De eigenschap(pen) is mogelijk te nieuw.&quot;, wat betekent dat er in de laatste 30 dagen geen activiteit voor die eigenschap heeft plaatsgevonden, of dat de Audience Manager de aanbevelingen voor die eigenschap nog niet heeft bijgewerkt. Probeer het over 24 uur opnieuw.

## Gevallen gebruiken

Met [!UICONTROL Trait Recommendations], kunt u uw workflows verbeteren, afhankelijk van hoe u Audience Manager gebruikt:

* Als marketeer, kunt u snel publiek vinden in complementaire producten met behulp van gelijkaardige eigenschappen, zodat u uw bereik kunt verhogen.
* Als u Audience Manager als uitgever gebruikt, met [!UICONTROL Trait Recommendations], kunt u publieksgedrag begrijpen en betere segmenten voor advertentieverkoop of gebruikersverwerving bouwen.
* Als [!UICONTROL Audience Marketplace] koper, wil ik relevante gegevens van derden ontdekken zonder door een groot aantal feeds te bladeren.
* Als [!UICONTROL Audience Marketplace] gegevensaanbieder, wil ik kopers relevante gegevens aanbevelen zodat ik gebruik kan maken van optimale en relevante abonnementen.

## Verschillen tussen Trait Recommendations en Algorithmic Models

### Algorithmic Models

[!UICONTROL Algorithmic Models]Met worden niet alleen de meest invloedrijke eigenschappen gevonden, maar worden gebruikers ook geturfd op basis van deze eigenschappen en wordt aan elke gebruiker een afzonderlijke score toegewezen. Vervolgens maakt u algoritmische eigenschappen om uw gebruikers te targeten. Met nauwkeurigheid en bereikcontrole in de [!UICONTROL Trait Builder], kunt u opgeven welke gebruikers onder alle gebruikers met de invloedrijke eigenschappen u wilt richten.

[!UICONTROL Algorithmic Models]Met kunt u gebruikers op verschillende nauwkeurigheidsniveaus selecteren en in testen welke groep gebruikers het beste converteert.[!UICONTROL Audience Lab] Zie het gedetailleerde gebruiksscenario in [Modellen vergelijken in Audience Lab](../../features/audience-lab/audience-lab-use-cases.md#compare-models).

In [!UICONTROL Algorithmic Models]Het model wordt elke 8 dagen uitgevoerd en vernieuwt de gebruikers die zijn gekwalificeerd voor algoritmische kenmerken.

### Trait Recommendations

[!UICONTROL Trait Recommendations] is een snelle manier om inzicht te krijgen in andere eigenschappen die lijken op degene die u in een segment gebruikt.

U moet [!UICONTROL Trait Recommendations] wanneer:

* U hebt snelle inzichten nodig tijdens het bouwen van een segment;
* U gebruikt de segmenten voor korte campagnes of wanneer u snelle suppressie wilt toepassen op een converterende doelgroep;
* U probeert het bereik te maximaliseren.

## Workflow

Bij het maken of bewerken van een segment in [Segment Builder](segment-builder.md), kunt u eigenschappen onderzoeken gelijkend op de eigenschappen in de segmentregel. De [Segment Builder](segment-builder.md) de workflow lijkt sterk op die voor nieuwe en bestaande segmenten :

### Nieuwe segmenten

1. Ga naar **Poortgegevens > Segmenten** en klik op **Nieuwe toevoegen**.
1. In de **Treinen** drop-down doos, voeg minstens één eigenschap aan de segmentregel toe.
1. U kunt de door de eerste partij aanbevolen kenmerken en [!UICONTROL Audience Marketplace] aanbevelingen van kenmerken van feeds waarop u bent geabonneerd, in het gedeelte **[!UICONTROL Recommendations]** sectie. De **[!UICONTROL Recommendations from Marketplace]** in deze sectie ziet u aanbevelingen met betrekking tot kenmerken van feeds waarop u zich niet hebt geabonneerd. Al deze aanbevelingen zijn gelijkaardig aan de eigenschappen u aan de segmentregel toevoegde. Schuif omlaag om alle aanbevolen kenmerken weer te geven.
1. (Optioneel) Als u de aanbevolen eigenschappen van de eerste partij wilt uitsluiten van bepaalde gegevensbronnen, klikt u op de knop **X** symbool voor de gegevensbronnen die u wilt uitsluiten.

   >[!NOTE]
   >
   >De uitgesloten gegevensbronnen worden net boven de lijst met aanbevolen kenmerken weergegeven. Klikken **X** in het grijze vak om de uitsluitingen te verwijderen en de resultaten van de respectieve gegevensbronnen opnieuw te bekijken.
1. Als u aanbevolen kenmerken aan de segmentregel wilt toevoegen, klikt u op de knop **+** symbool.

>[!IMPORTANT]
>
>Bij toevoegen [!UICONTROL Marketplace] de eigenschappen aan een segment, worden de eigenschappen slechts gebruikt voor segmentschatting, tot u aan het overeenkomstige gegeven intekent. Traits die afkomstig zijn van gegevensfeeds waarop u zich niet hebt geabonneerd, worden gemarkeerd met een winkelwagentje in de lijst met handelsmerken. Klik op de naam van het kenmerk om naar de pagina met gegevensinvoer te gaan en u erop te abonneren.
>
>![marketplace-not-subscribed](assets/trait-recommendations-marketplace.png)
>
>U kunt een segment alleen met externe kenmerken opslaan nadat u zich aan de bijbehorende gegevensfeeds hebt geabonneerd.

### Bestaande segmenten

1. Ga naar **[!UICONTROL Audience Data]>[!UICONTROL Segments]** selecteert u het segment dat u wilt bewerken en klikt u op ![Bewerken](assets/edit-button.png).
1. Omlaag schuiven naar de [!UICONTROL Traits] vervolgkeuzelijst.
1. U kunt geadviseerde eigenschappen zien, die aan de eigenschappen reeds in de segmentregel gelijkaardig zijn. Schuif omlaag om alle aanbevolen kenmerken weer te geven.
1. (Optioneel) Klik op de knop **X** symbool voor de gegevensbronnen die u wilt uitsluiten.

   >[!NOTE]
   >
   >De uitgesloten gegevensbronnen worden net boven de lijst met aanbevolen kenmerken weergegeven. Klikken **X** in het grijze vak om de uitsluitingen te verwijderen en de resultaten van de respectieve gegevensbronnen opnieuw te bekijken.
1. Als u aanbevolen kenmerken aan de segmentregel wilt toevoegen, klikt u op de knop **+** symbool.

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

Als u op een eersteklas kenmerk klikt, wordt een pop-upvenster geopend, zoals in de onderstaande afbeelding wordt getoond. Als de geadviseerde eigenschappen geen deel van het segment uitmaken, kunt u hen aan het segment toevoegen door te drukken **+**.

![toe:voegen-aan-segment](assets/add_to_segments.png)

>[!TIP]
>
>De uitgesloten gegevensbronnen van de hoofdpagina worden overwogen terwijl het produceren van aanbevelingen binnen het pop-up venster van de eigenschapinformatie. En als u gegevensbronnen in deze weergave uitsluit, gelden de uitsluitingen voor de hoofdpagina.

>[!NOTE]
>
>Aanbevolen kenmerken kunnen de kenmerken van de eerste partij zijn of de eigenschappen van derden van gegevensfeeds waarop u zich hebt geabonneerd [!UICONTROL Audience Marketplace].

## Hoe het werkt

Voor het opstellen van aanbevelingen op het gebied van de eigenschap, berekent de Audience Manager het [Jaccard-gelijkenis](https://en.wikipedia.org/wiki/Jaccard_index) tussen de doelkenmerken en alle andere kenmerken waartoe uw account toegang heeft, inclusief gegevens van derden. Audience Manager geeft dan tot vijftig kenmerken weer die het hoogst op elkaar lijken.

## Gelijksoortige score volgen {#trait-similarity-score}

De Audience Manager berekent de [!UICONTROL Trait Similarity Score] tussen twee eigenschappen door de doorsnede en de vakbond te berekenen in termen van het aantal [!UICONTROL UUID]en verdeel de twee. Voor twee kenmerken A en B ziet de berekening er als volgt uit:

![jaccard-gelijkenis](assets/jaccard_similarity.png)

Zie ook de twee onderstaande voorbeelden.

### Voorbeeld 1 - Gelijksoortige score met laag bereik

Met twee kenmerken A en B heeft elk kenmerk een populatie van 1.000.000 [!UICONTROL UUID]s, 25.000 [!UICONTROL UUID]s waarvan beide kenmerken in aanmerking komen.
Met de bovenstaande formule resulteert dit in: 25,000 / 1,975,000 = 0,012. Dit is laag [!UICONTROL Trait Similarity Score]De twee kenmerken zijn echter zeer verschillend.

![trait-recommendations-low-overlap](assets/Trait-Recommendations-Low-overlap.png)

### Voorbeeld 2 - Score met gelijksoortige trajecten

Indien dezelfde kenmerken A en B 400.000 [!UICONTROL UUID]Aangezien beide kenmerken in aanmerking komen, [!UICONTROL Trait Similarity Score] is veel hoger: 400,000 / 1,600,000 = 0,25

![trait-recommendations-high-overlap](assets/Trait-Recommendations-High-overlap.png)

### Hoe te om de Score van de Gelijksheid van het Beetje te interpreteren

Gebruik de onderstaande tabel als een ruwe richtlijn voor de gelijkenis van de afbeelding. Deze gids is gebaseerd op de gelijkenisscores die in de meeste kenmerken zijn waargenomen.

| [!UICONTROL Trait Similarity Score] | Significantie |
|---------|----------|
| 0.1 en hoger | Hoge overeenkomst tussen kenmerken |
| 0.03 - 0.1 | Normale overeenkomst tussen kenmerken |
| 0.01 - 0.03 | Lage overeenkomst tussen kenmerken |
| 0 - 0.01 | Zeer lage overeenkomsten tussen eigenschappen |

## Rolgebaseerde toegangscontrole (RBAC)

Voor bedrijven die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) hebt u toestemming nodig om segmenten te maken en te bewerken om de aanbevolen kenmerken te kunnen zien. De aanbevelingen van de eigenschap die u ziet zijn slechts degenen van gegevensbronnen die u toegang tot via hebt [!UICONTROL RBAC].

>[!IMPORTANT]
>
>Toevoegen [!UICONTROL Marketplace Recommendations] aan een segment, moeten de gebruikers eerst aan de overeenkomstige gegevensvoer intekenen. Alleen gebruikers met beheerdersrechten kunnen zich abonneren op [!UICONTROL Audience Marketplace] gegevensfeeds.

Meer informatie over [!UICONTROL RBAC] besturingselementen [hier](../administration/administration-overview.md).

## Beperkingen

* Op dit moment worden mapkenmerken niet als aanbevolen kenmerken weergegeven in Audience Manager. Meer informatie over mapkenmerken [hier](../traits/manage-folder-traits.md).
* Bij het weergeven van Trait Recommendations houdt Audience Manager geen rekening met [!DNL Boolean] operatoren ([!DNL AND], [!DNL OR], [!DNL NOT]) in segmentregels.
