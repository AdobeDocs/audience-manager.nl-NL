---
description: Met Audience Analytics kunt u Audience Manager-segmenten naar Analytics verzenden. Als u deze functie wilt gebruiken, maakt u een bestemming Analytics en kent u er segmenten aan toe in Audience Manager.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Een analysedoel configureren
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '866'
ht-degree: 0%

---

# Een analysedoel configureren

## Vereisten {#requirements}

Uw Audience Manager-gebruiker moet beheerdersrechten hebben om een analysedoel te configureren. Zie [ tot Gebruikers ](/help/using/features/administration/administration-overview.md#create-users) in de Gids van het Beleid leiden. Merk op dat het hebben van `CREATE_DESTINATIONS` [ vervangingstoestemming ](/help/using/features/administration/administration-overview.md#wild-card-permissions) niet volstaat om de bestemmingen van Analytics tot stand te brengen.
Voor verdere vereisten, zie Eerste vereisten in [ Audience Analytics ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html).

## Uw doel voor standaardanalyse en nieuwe analytische doelen

| Doeltype analyse | Beschrijving |
|---|---|
| Standaard | De naam van dit standaarddoel is &quot;Adobe Analytics&quot;, dat u kunt bewerken. ID&#39;s van de toegewezen rapportsuite worden weergegeven in de mapopslag voor uw Audience Manager-kenmerken en -segmenten. <br>  Audience Manager maakt automatisch één doel als uw account: <br>  <ul><li>Voldeed aan de vereisten die in [ worden beschreven Audience Analytics ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html) documentatie.</li><li>A [ rapportreeks ](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html) in Analytics.</li></ul> |
| Nieuw | Ga naar Poortgegevens > Doelen > Nieuwe bestemming maken en volg de stappen voor elke hieronder beschreven sectie om nieuwe analytische doelen te maken. |

## Audience Manager-segmentkwalificaties in Adobe Analytics {#segment-qualifications}

Wanneer het verzenden van segmentinformatie naar een bestemming van de Analyse, verzendt Audience Manager slechts de segmenten die de bezoeker voor kwalificeerde. Als een bezoeker ophoudt kwalificerend voor een segment, wordt deze informatie _niet_ door:sturen aan Adobe Analytics.

Neem bijvoorbeeld de volgende segmentregels:

* Segment A: Trait 1 EN Trait 2
* Segment B: Trait 1 EN NOT Trait 2

In de rapporten van de Analyse, kan een profiel voor beide segmenten worden getoond gekwalificeerd, alhoewel het ophield kwalificerend voor Segment B.

## Stap 1: Basisinformatie verstrekken

Deze sectie bevat velden en opties waarmee het doelontwerpproces voor Analytics wordt gestart. Deze sectie voltooien:

1. Klik **BasisInformatie** om de controles bloot te stellen.
2. Geef het doel een naam. Vermijd afkortingen en speciale tekens.
3. *(Facultatief)* beschrijf de bestemming. Een beknopte beschrijving is een effectieve manier om meer informatie over een bestemming te definiëren of te verstrekken.
4. *(Facultatief)* in de **Platform** lijst, verlaat het gebrek dat aan **wordt geplaatst allen**. Op dit moment doen deze opties niets. Ze zijn ontworpen om functies te ondersteunen die op een latere datum kunnen worden toegevoegd.
5. In de **lijst van de Categorie**, uitgezochte **Adobe Experience Cloud**.
6. In de **lijst van het Type**, uitgezochte **Adobe Analytics**.
7. Klik **sparen** om naar de montages van de Configuratie te gaan of **de Etiketten van de Uitvoer van Gegevens** te klikken om de uitvoercontroles op de bestemming toe te passen.

>[!NOTE]
>
>Voor een bestemming van de Analyse, wordt de **auto-Vul het Toewijzen van de Bestemming** controledoos en **Identiteitskaart van het Segment** optie geselecteerd door gebrek. U kunt deze instellingen niet wijzigen.

![ basisinformatie ](assets/basicinformation.png)

## Stap 2: De Controles van de Uitvoer van Gegevens vormen

Deze sectie bevat opties die [ de Controles van de Uitvoer van Gegevens ](/help/using/features/data-export-controls.md) op een bestemming van Analytics toepassen. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klik **de Controles van de Uitvoer van Gegevens** om de controles bloot te stellen.
1. Selecteer een etiket dat aan de controle beantwoordt van de gegevensuitvoer die op de bestemming wordt toegepast (zie [ de Etiketten van de Uitvoer van Gegevens aan een Bestemming ](/help/using/features/destinations/add-data-export-labels.md) toevoegen). Voor de bestemmingen van de Analyse, wordt het PII controlevakje geselecteerd door gebrek.
1. Klik **sparen**.

![ exportcontroles ](assets/exportControls.png)

## Stap 3: Kaartrapportsets

De sectie van de Configuratie maakt een lijst van uw Reeksen van het Rapport van Analytics die voor server-kant het door:sturen zijn toegelaten. Als u veelvoudige bestemmingen van de Analyse hebt, zullen de rapportreeksen die aan deze bestemmingen worden toegewezen wederzijds exclusief zijn en door Audience Manager worden afgedwongen. Deze sectie voltooien:

1. Klik **Configuratie** om de controles bloot te stellen.
1. Selecteer een (of meer) rapportsuites waarnaar u segmenten wilt verzenden.
1. Klik **sparen**.

![ rapportsuites ](assets/reportSuites.png)

## Stap 4: Segmenttoewijzingen

Deze sectie biedt opties waarmee u segmenten automatisch of handmatig kunt toewijzen.

| Toewijzingsoptie | Beschrijving |
|---|---|
| Automatisch alle huidige en toekomstige segmenten toewijzen | Deze functie is standaard geselecteerd en verzendt alle segmenten waarvoor een bezoeker per hit in aanmerking komt naar Analytics. <br>  Als een bezoeker tot meer dan 150 segmenten van Audience Manager op één enkele klap behoort, slechts worden 150 onlangs gekwalificeerde segmenten verzonden naar Analytics, terwijl de resterende lijst wordt beknot. Een extra vlag wordt verzonden naar Analytics die erop wijst dat de segmentlijst werd beknot. Deze actie wordt weergegeven als &quot;Audience limit Rebbe&quot; in de dimensie Soorten publiek en &quot;1&quot; in de dimensie Soorten publiek-id. Zie [ Veelgestelde vragen ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html) voor details. <br>  Ook, beïnvloedt deze optie bestemmingsbeschikbaarheid in [ de Bouwer van het Segment ](/help/using/features/segments/segment-builder.md). Bijvoorbeeld, als een segment automatisch aan een bestemming van Analytics in kaart wordt gebracht, is die bestemming niet beschikbaar voor selectie in de [ sectie van bestemmingstoewijzingen ](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) van de Bouwer van het Segment. De bestemming Analytics verschijnt grijs-uit en toont &quot;Analytics&quot;in de kolom van het Type van browser van de Bestemming. |
| Segmenten handmatig toewijzen | Deze optie stelt onderzoek bloot en doorbladert controles die u laten kiezen welke segmenten u naar Analytics wilt verzenden. <br>  U kunt als volgt naar een segment zoeken: <br>  <ol><li>Typ de segmentnaam of id in het zoekveld.</li><li>Klik <b> toevoegen.</b></li><li>Ga verder om segmenten te zoeken en toe te voegen of <b> Gedaan </b> te klikken.</li></ol><br>  Een segment zoeken: <ol><li>Klik <b> doorbladeren alle segmenten </b>. Hiermee wordt een lijst met beschikbare segmenten weergegeven.</li><li>Van de lijst, selecteer de controledoos van het segment u wilt gebruiken en <b> klikken voegt geselecteerde segmenten </b> toe.</li><li>Klik <b> sparen </b> in Add venster van Toewijzingen. U kunt de toewijzingen, begin- of einddatum niet wijzigen tijdens de bètaversie.</li><li>Ga verder en voeg segmenten toe of klik <b> Gereed </b>.</li></ol> ![ mapsegments ](assets/mapSegments.png) |

## Volgende stappen

Nadat u een doel hebt gemaakt en opgeslagen, kunt u met die gegevens werken in Analytics. Het kan echter een paar uur duren voordat gegevens beschikbaar zijn in de geselecteerde rapportensuites. Zie [ de Gegevens van het Publiek in Analytics ](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html) gebruiken.
