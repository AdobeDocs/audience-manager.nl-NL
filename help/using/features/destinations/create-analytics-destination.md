---
description: Analytics van het publiek laat u de segmenten van de Manager van de Publiek naar Analytics verzenden. Om deze eigenschap te gebruiken, creeert u een bestemming van Analytics en kaartsegmenten aan het in de Manager van het Publiek.
seo-description: Analytics van het publiek laat u de segmenten van de Manager van de Publiek naar Analytics verzenden. Om deze eigenschap te gebruiken, creeert u een bestemming van Analytics en kaartsegmenten aan het in de Manager van het Publiek.
seo-title: Een analysedoel configureren
solution: Audience Manager
title: Een analysedoel configureren
translation-type: tm+mt
source-git-commit: fa39d070be9ec9f07e9da31de3efd151dd2c6cf1

---


# Een analysedoel configureren

## Vereisten {#requirements}

Om een bestemming van de Analyse te vormen, moet uw gebruiker van de Manager van de Publiek Admin toestemmingen hebben. Zie Gebruikers [](/help/using/features/administration/administration-overview.md#create-users) maken in de handleiding voor beheer. Merk op dat het hebben van de `CREATE_DESTINATIONS` vervangingstoestemming [](/help/using/features/administration/administration-overview.md#wild-card-permissions) niet volstaat om de bestemmingen van Analytics tot stand te brengen.
Voor verdere vereisten, zie Eerste vereisten in de Analytics van het [publiek](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/).

## Uw doel voor standaardanalyse en nieuwe analytische doelen

| Doeltype analyse | Beschrijving |
|---|---|
| Standaard | De naam van dit standaarddoel is &quot;Adobe Analytics&quot;, dat u kunt bewerken. Toegewezen rapportsuite-id&#39;s worden weergegeven in de mapopslag voor de kenmerken en segmenten van Audience Manager. <br>  Auditiebeheer maakt automatisch één doel als uw account: <br>  <ul><li>Voldeed aan de vereisten die zijn beschreven in de documentatie van [Audience Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/) .</li><li>Een [rapportsuite](https://marketing.adobe.com/resources/help/en_US/sc/implement/ref-reports-report-suites.html) in Analytics.</li><li>[Wijst een rapportsuite toe aan een organisatie](https://marketing.adobe.com/resources/help/en_US/mcloud/report-suite-mapping.html).</li></ul> |
| Nieuw | Ga naar Poortgegevens > Doelen > Nieuwe bestemming maken en volg de stappen voor elke hieronder beschreven sectie om nieuwe analytische doelen te maken. |

## Stap 1: Basisinformatie opgeven

Deze sectie bevat velden en opties waarmee het doelontwerpproces voor Analytics wordt gestart. Deze sectie voltooien:

1. Klik op **Basisinformatie** om de besturingselementen beschikbaar te maken.
2. Geef het doel een naam. Vermijd afkortingen en speciale tekens.
3. *(Optioneel)* Beschrijf de bestemming. Een beknopte beschrijving is een effectieve manier om meer informatie over een bestemming te definiëren of te verstrekken.
4. *(Optioneel)* Laat in de lijst **Platform** de standaardwaarde **Alles** staan. Op dit moment doen deze opties niets. Ze zijn ontworpen om functies te ondersteunen die op een latere datum kunnen worden toegevoegd.
5. Selecteer in de lijst **Categorie** de optie **Adobe Experience Cloud**.
6. Selecteer **Adobe Analytics in de lijst** Type ****.
7. Klik **sparen** om naar de montages van de Configuratie te gaan of de Etiketten **van de Uitvoer van** Gegevens te klikken om de uitvoercontroles op de bestemming toe te passen.

>[!NOTE]
>
>Voor een bestemming Analytics, worden de **Auto-Vulling de controledoos van de Toewijzing** van de Bestemming en de optie van identiteitskaart **van het** Segment geselecteerd door gebrek. U kunt deze instellingen niet wijzigen.

![basisinformatie](assets/basicinformation.png)

## Stap 2: Besturingselementen voor gegevensexport configureren

Deze sectie bevat opties die de Controles [van de Uitvoer van](/help/using/features/data-export-controls.md) Gegevens op een bestemming Analytics toepassen. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klik de Controles **van de Uitvoer van** Gegevens om de controles bloot te stellen.
1. Selecteer een label dat overeenkomt met het besturingselement voor gegevensexport dat op de bestemming wordt toegepast (zie Labels voor gegevensexport [toevoegen aan een doel](/help/using/features/destinations/add-data-export-labels.md) ). Voor de bestemmingen van de Analyse, wordt het PII controlevakje geselecteerd door gebrek.
1. Klik op **Opslaan**.

![uitvoercontroles](assets/exportControls.png)

## Stap 3: Kaartrapportsets

De sectie van de Configuratie maakt een lijst van uw Reeksen van het Rapport van Analytics die voor server-kant het door:sturen zijn toegelaten. Als u veelvoudige bestemmingen van de Analyse hebt, zullen de rapportreeksen die aan deze bestemmingen worden toegewezen wederzijds exclusief zijn en door de Manager van het Publiek worden afgedwongen. Deze sectie voltooien:

1. Klik **Configuratie** om de controles bloot te stellen.
1. Selecteer een (of meer) rapportsuites waarnaar u segmenten wilt verzenden.
1. Klik op **Opslaan**.

![reportsuites](assets/reportSuites.png)

## Stap 4: Segmenttoewijzingen

Deze sectie biedt opties waarmee u segmenten automatisch of handmatig kunt toewijzen.

| Toewijzingsoptie | Beschrijving |
|---|---|
| Automatisch alle huidige en toekomstige segmenten toewijzen | Deze functie is standaard geselecteerd en verzendt alle segmenten waarvoor een bezoeker per hit in aanmerking komt naar Analytics. <br>  Als een bezoeker tot meer dan 150 segmenten van de Manager van de Publiek op één enkele klap behoort, slechts worden 150 onlangs gekwalificeerde segmenten verzonden naar Analytics, terwijl de resterende lijst wordt beknot. Een extra vlag wordt verzonden naar Analytics die erop wijst dat de segmentlijst werd beknot. Deze actie wordt weergegeven als &quot;Audience limit Rebbe&quot; in de dimensie Soorten publiek en &quot;1&quot; in de dimensie Soorten publiek-id. Raadpleeg de [veelgestelde vragen](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/mc-audiences-faqs.html) voor meer informatie. <br>  Ook, beïnvloedt deze optie bestemmingsbeschikbaarheid in de Bouwer van het [Segment](/help/using/features/segments/segment-builder.md). Bijvoorbeeld, als een segment automatisch aan een bestemming van Analytics in kaart wordt gebracht, is die bestemming niet beschikbaar voor selectie in de sectie van [bestemmingstoewijzingen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) van de Bouwer van het Segment. De bestemming Analytics verschijnt grijs-uit en toont &quot;Analytics&quot;in de kolom van het Type van browser van de Bestemming. |
| Segmenten handmatig toewijzen | Deze optie stelt onderzoek bloot en doorbladert controles die u laten kiezen welke segmenten u naar Analytics wilt verzenden. <br>  Een segment zoeken: <br>  <ol><li>Typ de segmentnaam of id in het zoekveld.</li><li>Klik op <b>Toevoegen.</b></li><li>Ga door met zoeken en voeg segmenten toe of klik op <b>Gereed</b>.</li></ol><br>  Een segment zoeken: <ol><li>Klik op <b>Bladeren in alle segmenten</b>. Hiermee wordt een lijst met beschikbare segmenten weergegeven.</li><li>Selecteer in de lijst het selectievakje van het segment dat u wilt gebruiken en klik op Geselecteerde segmenten <b></b>toevoegen.</li><li>Klik op <b>Opslaan</b> in het venster Toewijzingen toevoegen. U kunt de toewijzingen, begin- of einddatum niet wijzigen tijdens de bètaversie.</li><li>Ga door en voeg segmenten toe of klik op <b>Gereed</b>.</li></ol> ![mapsegmenten](assets/mapSegments.png) |

## Volgende stappen

Nadat u een doel hebt gemaakt en opgeslagen, kunt u met die gegevens werken in Analytics. Het kan echter een paar uur duren voordat gegevens beschikbaar zijn in de geselecteerde rapportensuites. Zie De gegevens van het publiek [gebruiken in Analytics](https://marketing.adobe.com/resources/help/en_US/analytics/audiences/use-audience-data-analytics.html).
