---
description: Algemene vragen en problemen in verband met rapportage.
seo-description: Algemene vragen en problemen in verband met rapportage.
seo-title: Veelgestelde vragen over rapportage
solution: Audience Manager
title: Veelgestelde vragen over rapportage
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Veelgestelde vragen over rapportage{#reporting-faq}

Algemene vragen en problemen in verband met rapportage.

<br> 

<!-- 

faq_reports.xml

 -->

**Waarom geeft de eigenschap voor nieuwe onboded-eigenschappen[!UICONTROL Trait Graph]soms lagere getallen dan verwacht weer of 0?**

Soms geeft het programma, nadat u kenmerken hebt geüpload, [!UICONTROL Trait Graph] geen resultaten weer of geeft het lagere getallen dan u had verwacht. Dit gebeurt wanneer het volume van gegevens wij ontvangen zo groot is dat de binnenkomende verwerkingstaak niet kan beëindigen die deze informatie tot na de rapporteringsdeadline voor die dag inneemt.

Dit heeft tot gevolg dat deze gegevens te laat naar het rapportagesysteem worden verzonden en niet worden weergegeven in het rapportageinterval van één dag dat wordt gebruikt voor het tekenen van de [!UICONTROL Trait Graph]gegevens. Nochtans, kunt u deze gegevens in 7, 14, 30, en 60 dagrapportintervallen in een [Tendens](../reporting/trend-reports.md#trend-report-overview) of [Algemeen Rapport](../reporting/general-reports.md#general-reports-overview) op de volgende dag bekijken.

<br> 

**Sommige segmenten ontbreken in een[!UICONTROL Overlap]rapport. Waar zijn ze?**

Om de vraag naar berekeningen te verminderen, ontbreken deze rapporten statistisch onbelangrijke gegevens uit de resultaten. Uw segmenten ontbreken niet, ze worden gewoon verwijderd omdat ze geen betekenisvolle resultaten opleveren of nuttige groepen gebruikers waarop u zich kunt richten. Zie ook:

* [Rapporten en de Methodologieën van de Steekproef van Gegevens](../reporting/report-sampling.md)
* [Unieke gebruikers tellen in overlapping en algemene rapporten](../reporting/unique-user-counts.md).

<br> 

**Als ik een e-mailmarketingcampagne voer, hoe kan ik dan bepalen of omgeleide gebruikers naar mijn site komen vanuit die campagne of vanuit andere bronnen?**

Voeg een campagne-specifieke vraagkoord aan URL van de plaatssectie toe u wilt controleren. Stel vervolgens een taakregel in om deze variabele vast te leggen. Als uw URL bijvoorbeeld een campagne-id als deze doorgeeft, maakt u `www.test123.com/electronics?campaign=123`een regel voor het kenmerk om die gegevens van de `h_referer` variabele vast te leggen met een regel die naar een koptekst als `h_referer = 'campaign=123'`) zoekt.

<br> 

**Wat is het verschil tussen de aantallen in real time en de totale segmentpopulatie?**

* **In real time:** Het aantal unieke gebruikers die deel uitmaken van het segment en tijdens een ingestelde periode actief zijn op uw eigenschappen (d.w.z., [!DNL Audience Manager] moet activiteit voor die gebruiker voor de specifieke periode hebben geregistreerd).

* **Totale segmentpopulatie:** Een aggregatie van alle gebruikers die momenteel in dat segment zijn geclassificeerd.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Ik heb een segment dat uit slechts één eigenschap bestaat. Wanneer ik de metriek van de Rapportering bekijk, passen hun tellingen niet aan. Waarom is dat?**

Zie [Trait and Segment Population Data in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Ik binnenkomend een dossier en mijn Binnenkomend ontvangstbewijs toont een hoog aantal met succes verwerkte verslagen, maar het melden toont veel lagere aantallen. Waarom?**

Op de achtergrond, worden de geregistreerde gegevens verbonden slechts aan gebruikers die in AAM nog actief zijn (de gebruiker moet recente [!UICONTROL DCS] activiteit in de afgelopen 120 dagen hebben gehad). Daarom als u gegevens aan boord voor gebruikers hebt die reeds binnen zijn verlopen [!DNL Audience Manager], [!UICONTROL Inbound] zou u kunnen vertellen dat een bepaald aantal gebruikersverslagen werden geregistreerd, maar als deze gebruikers geen recente activiteit hebben gehad, worden deze gegevens gelaten vallen wanneer het ons bereikt [!UICONTROL User Profile Store] en het melden zal dat behandelen.

<br> 

**Waarom zijn de traditie-uniques voor mijn cross-device onboded traits veel hoger dan het totale aantal onboded records?**

Als u aan boord een dossier voor een dwars-apparatengegevensleverancier van klantenidentiteitskaart wordt gehouden, voert de Manager van de Publiek een raadpleging uit om alle apparaat IDs te krijgen die met elk van de geregistreerde klant IDs worden geassocieerd. Audience Manager wijst vervolgens de geregistreerde kenmerken toe aan de apparaat-id die aan de klant-id is gekoppeld.

Stel dat u 100 records hebt ingecheckt. Voor elk van deze klant IDs, gemiddeld, heeft AAM drie apparaat IDs geassocieerd. Dientengevolge, wordt het bezit dat werd ingezien toegewezen aan 300 apparaat IDs.

Er zijn twee redenen waarom één enkele dwars-apparatenklant ID met veelvoudige apparaat IDs kan worden geassocieerd:

* Gebruikers melden zich aan bij dezelfde apparaataccount vanaf meerdere computers/browsers.
* Gebruikers wissen hun cookies. Opmerking: &quot;Verlaten&quot; cookies worden verwijderd na 120 dagen inactiviteit van de gebruiker.

<br> 

**Waarom zijn[!UICONTROL Total Trait Realizations]mijn ongekende kenmerken altijd 0?**

[!UICONTROL Total Trait Realizations] komt overeen met het laden van pagina&#39;s. [!UICONTROL Total Trait Realizations] Geef het aantal keren op dat deze specifieke eigenschap in real-time heeft geactiveerd. Dit aantal wordt berekend voor regel-gebaseerde slechts eigenschappen. Aan boord genomen kenmerken worden altijd weergegeven [!UICONTROL Total Trait Realizations] als 0.

<br> 

**Ik creëerde een eigenschap en de[!UICONTROL Trait Graph]toont een groter aantal[!UICONTROL Unique Trait Realizations]dan de[!UICONTROL Total Trait Population]. Is dit normaal?**

Je ziet dit omdat het metriek in real time [!UICONTROL Unique Trait Realizations] zijn, maar de rapportbanen die we doen om de [!UICONTROL Total Trait Population] te berekenen zijn niet real time. De waarde [!UICONTROL Total Trait Population] [!UICONTROL Unique Trait Realizations] moet binnen een paar dagen groter zijn dan de waarde.
