---
description: Met Audience Analytics kunt u Audience Manager-segmenten naar Analytics verzenden. Om deze eigenschap te gebruiken, creeert u een bestemming Analytics en kaartsegmenten aan het in Audience Manager.
seo-description: Audience Analytics lets you send Audience Manager segments to Analytics. To use this feature, you create an Analytics destination and map segments to it in Audience Manager.
seo-title: Configure an Analytics Destination
solution: Audience Manager
title: Een Analytics-bestemming configureren
feature: Adobe Analytics Integration
exl-id: f3ead057-04d1-40cd-8e3d-d0934d85cdb4
source-git-commit: ef8cca16c8c9478f8558c26bf6f3ae95cd72e7ac
workflow-type: tm+mt
source-wordcount: '888'
ht-degree: 1%

---

# Een Analytics-bestemming configureren

## Vereisten {#requirements}

Om een bestemming van de Analyse te vormen, moet uw gebruiker van de Audience Manager Admin toestemmingen hebben. Zie [Gebruikers maken](/help/using/features/administration/administration-overview.md#create-users) in de Beheerdershandleiding. Houd er rekening mee dat `CREATE_DESTINATIONS` [jokerteken, machtiging](/help/using/features/administration/administration-overview.md#wild-card-permissions) volstaat niet om analytische doelen te maken.
Voor verdere vereisten, zie Eerste vereisten in [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=nl-NL).

## Uw doel voor standaardanalyse en nieuwe analytische doelen

| Doeltype analyse | Beschrijving |
|---|---|
| Standaard | De naam van dit standaarddoel is &quot;Adobe Analytics&quot;, dat u kunt bewerken. Toegewezen rapportsuite-id&#39;s worden weergegeven in de mapopslag voor de kenmerken en segmenten van de Audience Manager. <br>  Audience Manager maakt automatisch één doel als uw account: <br>  <ul><li>Aan de in de [Audience Analytics](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/mc-audiences-aam.html?lang=nl-NL) documentatie.</li><li>A [rapportsuite](https://experienceleague.adobe.com/docs/analytics/admin/manage-report-suites/report-suites-admin.html?lang=nl-NL) in Analytics.</li></ul> |
| Nieuw | Ga naar Poortgegevens > Doelen > Nieuwe bestemming maken en volg de stappen voor elke hieronder beschreven sectie om nieuwe analytische doelen te maken. |

## Kwalificaties in het segment Audience Managers in Adobe Analytics {#segment-qualifications}

Wanneer het verzenden van segmentinformatie naar een bestemming van de Analyse, verzendt de Audience Manager slechts de segmenten die de bezoeker voor kwalificeerde. Als een bezoeker stopt met het in aanmerking komen voor een segment, is deze informatie _niet_ doorgestuurd naar Adobe Analytics.

Neem bijvoorbeeld de volgende segmentregels:

* Segment A: Trait 1 EN Trait 2
* Segment B: Trait 1 EN NOT Trait 2

In de rapporten van Analytics, kan een profiel voor beide segmenten worden getoond gekwalificeerd, alhoewel het ophield kwalificerend voor Segment B.

## Stap 1: Basisinformatie opgeven

Deze sectie bevat velden en opties waarmee het doelontwerpproces voor Analytics wordt gestart. Deze sectie voltooien:

1. Klikken **Basisinformatie** om de besturingselementen zichtbaar te maken.
2. Geef het doel een naam. Vermijd afkortingen en speciale tekens.
3. *(Optioneel)* Beschrijf de bestemming. Een beknopte beschrijving is een effectieve manier om meer informatie over een bestemming te definiëren of te verstrekken.
4. *(Optioneel)* In de **Platform** lijst, laat de standaardreeks aan **Alles**. Op dit moment doen deze opties niets. Ze zijn ontworpen om functies te ondersteunen die op een latere datum kunnen worden toegevoegd.
5. In de **Categorie** list, selecteer **Adobe Experience Cloud**.
6. In de **Type** list, selecteer **Adobe Analytics**.
7. Klikken **Opslaan** om naar de montages van de Configuratie te gaan of klik **Labels voor gegevensexport** om exportbesturingselementen toe te passen op de bestemming.

>[!NOTE]
>
>Voor een doel Analytics: **Bestemmingstoewijzing automatisch vullen** selectievakje en **Segment-id** Deze optie is standaard geselecteerd. U kunt deze instellingen niet wijzigen.

![basisinformatie](assets/basicinformation.png)

## Stap 2: Besturingselementen voor gegevensexport configureren

Deze sectie bevat opties die van toepassing zijn [Besturingselementen voor gegevensexport](/help/using/features/data-export-controls.md) naar een analysedoel. Sla deze stap over als u geen besturingselementen voor het exporteren van gegevens gebruikt. Deze sectie voltooien:

1. Klikken **Besturingselementen voor gegevensexport** om de besturingselementen zichtbaar te maken.
1. Selecteer een label dat overeenkomt met het besturingselement voor gegevensexport dat op het doel is toegepast (zie [Labels voor gegevensexport toevoegen aan een doel](/help/using/features/destinations/add-data-export-labels.md) ). Voor de bestemmingen van de Analyse, wordt het PII controlevakje geselecteerd door gebrek.
1. Klikken **Opslaan**.

![uitvoercontroles](assets/exportControls.png)

## Stap 3: Kaartrapportsets

De sectie van de Configuratie maakt een lijst van uw Reeksen van het Rapport van Analytics die voor server-kant het door:sturen zijn toegelaten. Als u veelvoudige bestemmingen van de Analyse hebt, zullen de rapportreeksen die aan deze bestemmingen worden toegewezen wederzijds exclusief zijn en door Audience Manager worden afgedwongen. Deze sectie voltooien:

1. Klikken **Configuratie** om de besturingselementen zichtbaar te maken.
1. Selecteer een (of meer) rapportsuites waarnaar u segmenten wilt verzenden.
1. Klikken **Opslaan**.

![reportsuites](assets/reportSuites.png)

## Stap 4: Segmenttoewijzingen

Deze sectie biedt opties waarmee u segmenten automatisch of handmatig kunt toewijzen.

| Toewijzingsoptie | Beschrijving |
|---|---|
| Automatisch alle huidige en toekomstige segmenten toewijzen | Deze functie is standaard geselecteerd en verzendt alle segmenten waarvoor een bezoeker per hit in aanmerking komt naar Analytics. <br>  Als een bezoeker tot meer dan 150 Audience Manager segmenten op één enkele klap behoort, slechts worden 150 onlangs gekwalificeerde segmenten verzonden naar Analytics, terwijl de resterende lijst wordt beknot. Een extra vlag wordt verzonden naar Analytics die erop wijst dat de segmentlijst werd beknot. Deze actie wordt weergegeven als &quot;Audience limit Rebbe&quot; in de dimensie Soorten publiek en &quot;1&quot; in de dimensie Soorten publiek-id. Zie de [Veelgestelde vragen](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/mc-audiences-faqs.html?lang=nl-NL) voor meer informatie. <br>  Deze optie beïnvloedt ook de beschikbaarheid van de bestemming in [Segment Builder](/help/using/features/segments/segment-builder.md). Als een segment bijvoorbeeld automatisch wordt toegewezen aan een bestemming Analytics, is dat doel niet beschikbaar voor selectie in het dialoogvenster [doeltoewijzingen](/help/using/features/segments/segment-builder.md#segment-builder-controls-destinations) sectie van Segment Builder. De bestemming Analytics verschijnt grijs-uit en toont &quot;Analytics&quot;in de kolom van het Type van browser van de Bestemming. |
| Segmenten handmatig toewijzen | Deze optie stelt onderzoek bloot en doorbladert controles die u laten kiezen welke segmenten u naar Analytics wilt verzenden. <br>  Een segment zoeken: <br>  <ol><li>Typ de segmentnaam of id in het zoekveld.</li><li>Klikken <b>Toevoegen.</b></li><li>Doorgaan met zoeken en segmenten toevoegen of klikken <b>Gereed</b>.</li></ol><br>  Een segment zoeken: <ol><li>Klikken <b>Bladeren door alle segmenten</b>. Hiermee wordt een lijst met beschikbare segmenten weergegeven.</li><li>Selecteer in de lijst het selectievakje van het segment dat u wilt gebruiken en klik op <b>Geselecteerde segmenten toevoegen</b>.</li><li>Klikken <b>Opslaan</b> in het venster Toewijzingen toevoegen. U kunt de toewijzingen, begin- of einddatum niet wijzigen tijdens de bètaversie.</li><li>Doorgaan en segmenten toevoegen of klikken <b>Gereed</b>.</li></ol> ![mapsegmenten](assets/mapSegments.png) |

## Volgende stappen

Nadat u een doel hebt gemaakt en opgeslagen, kunt u met die gegevens werken in Analytics. Het kan echter een paar uur duren voordat gegevens beschikbaar zijn in de geselecteerde rapportensuites. Zie [De gegevens van het publiek in Analytics gebruiken](https://experienceleague.adobe.com/docs/analytics/integration/audience-analytics/audience-analytics-workflow/use-audience-data-analytics.html?lang=nl-NL).
