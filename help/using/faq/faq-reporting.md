---
description: Algemene vragen en problemen in verband met rapportage.
seo-description: Algemene vragen en problemen in verband met rapportage.
seo-title: Veelgestelde vragen over rapportage
solution: Audience Manager
title: Veelgestelde vragen over rapportage
uuid: 78cd6c86-8a4a-4748-ab71-b6e8d6078c94
feature: Reporting Reference
exl-id: 1e6531b2-bb39-4056-9d5e-164f50955f99
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '704'
ht-degree: 99%

---

# Veelgestelde vragen over rapportage {#reporting-faq}

Algemene vragen en problemen in verband met rapportage.

<br>

<!-- 

faq_reports.xml

 -->

**Waarom geeft de [!UICONTROL Trait Graph] voor nieuwe, onboarded eigenschappen soms onverwacht lagere getallen of 0 weer?**

Soms geeft de [!UICONTROL Trait Graph] nadat u eigenschappen hebt geüpload, geen resultaten weer of lagere getallen dan u had verwacht. Dit gebeurt wanneer het datavolume dat we ontvangen, zo groot is dat de binnenkomende verwerkingstaak het opnemen van deze informatie pas kan beëindigen na de rapportagedeadline voor die dag.

Dit heeft tot gevolg dat deze data laat naar het rapportagesysteem worden verzonden en niet worden weergegeven in het rapportage-interval van één dag dat wordt gebruikt voor het uitzetten van de [!UICONTROL Trait Graph]-data. U kunt deze data echter bekijken in de rapportage-intervallen van 7, 14, 30 en 60 dagen in een [Trendrapport](../reporting/trend-reports.md#trend-report-overview) of [Algemeen rapport](../reporting/general-reports.md#general-reports-overview) op de volgende dag.

<br> 

**Sommige segmenten ontbreken in een [!UICONTROL Overlap]-rapport. Waar zijn ze?**

Om de hoeveelheid berekeningen te verminderen worden in deze rapporten statistisch onbelangrijke data uit de resultaten weggelaten. Uw segmenten ontbreken niet, maar ze worden verwijderd omdat ze geen betekenisvolle resultaten of nuttige groepen gebruikers opleveren om te targeten. Zie ook:

* [Rapporten en datasamplingmethodes](../reporting/report-sampling.md)
* [Unieke gebruikers tellen in overlaprapporten en algemene rapporten](../reporting/unique-user-counts.md).

<br> 

**Als ik een e-mailmarketingcampagne voer, hoe kan ik dan bepalen of omgeleide gebruikers naar mijn website komen vanuit die campagne of vanuit andere bronnen?**

Voeg een campagnespecifieke querytekenreeks toe aan de URL van het websitegedeelte dat u wilt controleren. Stel vervolgens een eigenschapregel in om deze variabele vast te leggen. Als uw URL bijvoorbeeld op deze manier langskomt in een campagne-id: `www.test123.com/electronics?campaign=123`, maak dan een eigenschapregel om deze data vast te leggen van de `h_referer`-variabele met een eigenschapregel die zoekt naar een kop als `h_referer = 'campaign=123'`).

<br> 

**Wat is het verschil tussen realtime-aantallen en totale aantallen van segmentpopulaties?**

* **Real time:** het aantal unieke gebruikers die deel uitmaken van het segment en tijdens een ingestelde periode actief zijn op uw eigenschappen (dat betekent dat [!DNL Audience Manager] activiteit voor die gebruiker voor deze specifieke periode moet hebben geregistreerd).

* **Totale segmentpopulatie:** een aggregatie van alle gebruikers die momenteel in dat segment zijn ondergebracht.

<!-- 

<p> <b>Why is data available for total fires for traits but not segments?</b> </p> 
<p>Total fires correspond to page loads. Total trait fires provide the number of times that specific trait has fired. This number will always be equal to, or greater than, your unique user count. By contrast, segments are audience profiles that represent groups of users. Segments don't correlate to page loads or views because they're tied to logic that classifies users based on rules, not individual traits. </p>

 -->

<br> 

**Ik heb een segment dat uit slechts één eigenschap bestaat. Wanneer ik de rapportagecijfers bekijk, komen de aantallen niet overeen. Hoe komt dat?**

Zie [Populatiedata van eigenschappen en segmenten in Segment Builder](../features/segments/segment-builder-data.md).

<br> 

<!-- 

<p> <b>Why would there be a difference between real-time segment population and the unique values?</b> </p> 
<p>Audience Manager uses different methodologies to count traits and segments. </p> 
<p>For traits, the uniques metric represents receipt of data collection. Every time a visitor realizes a particular trait, either in real-time via the DCS, or offline via Inbound, the uniques for that trait goes up by 1. </p> 
<p>For example, a trait uniques of 2,340 over the range of seven days means that 2,340 unique visitors realized that trait over the last seven days. </p> 
<p>Segments are counted differently because their primary purpose is to help you understand your audience better. Every time Audience Manager sees a visitor in real-time who is a member of a given segment, even if that segment isn’t being newly realized or re-realized on a request, the uniques for that segment goes up by 1. </p> 
<p>For example, a segment uniques of 5,000 over the range of seven days means that Audience Manager saw 5,000 unique users in real-time data-collection events over the last seven days who were members of that segment at the time that Audience Manager saw them, regardless of whether that was a new membership or a pre-existing one. </p>

 -->

**Ik ‘inbound’ een bestand en mijn ontvangstbewijs toont een groot aantal succesvol verwerkte records, maar de rapportage toont veel lagere aantallen. Waarom?**

Op de achtergrond worden onboarded data alleen verbonden met gebruikers die nog actief zijn in AAM (de gebruiker moet recente [!DNL DCS]-activiteit hebben gehad in de afgelopen 120 dagen). Als u dus data ‘onboardt’ voor gebruikers die in [!DNL Audience Manager] al zijn verlopen, vertelt [!UICONTROL Inbound] u mogelijk dat een bepaald aantal gebruikersrecords zijn onboarded, maar als deze gebruikers geen recente activiteit hebben vertoond, worden deze data verwijderd wanneer ze onze [!UICONTROL User Profile Store] bereiken en dat komt naar boven in de rapportage.

<br> 

**Waarom zijn de unieke eigenschappen voor mijn cross-device onboarded eigenschappen veel hoger dan het totale aantal onboarded records?**

Als u een bestand ‘onboardt’ voor een cross-device dataprovider op basis van de klant-id, voert Audience Manager een zoekactie uit om alle apparaat-id’s op te halen die zijn gekoppeld aan elk van de onboarded klant-id’s. Audience Manager wijst vervolgens de onboarded eigenschappen toe aan de apparaat-id die aan de klant-id is gekoppeld.

Stel dat u onboarded 100 records hebt. Aan elk van deze klant-id’s heeft AAM gemiddeld drie apparaat-id’s gekoppeld. Daardoor wordt de onboarded eigenschap toegewezen aan 300 apparaat-id’s.

Er zijn twee redenen waarom één cross-device klant-id kan worden gekoppeld aan meerdere apparaat-id’s:

* Gebruikers melden zich aan bij hetzelfde cross-device account vanaf meerdere computers/browsers.
* Gebruikers wissen hun cookies. Opmerking: “verlaten” cookies worden verwijderd na 120 dagen inactiviteit van de gebruiker.

<br> 

**Waarom zijn de [!UICONTROL Total Trait Realizations] voor mijn onboarded eigenschappen altijd 0?**

[!UICONTROL Total Trait Realizations] komt overeen met het aantal keren laden van pagina’s. [!UICONTROL Total Trait Realizations] geeft het aantal keren aan dat deze specifieke eigenschap in real time is geactiveerd. Dit aantal wordt alleen berekend voor op regels gebaseerde eigenschappen. Onboarded eigenschappen geven [!UICONTROL Total Trait Realizations] altijd weer als 0.

<br> 

**Ik heb een eigenschap gemaakt en de [!UICONTROL Trait Graph] toont een groter aantal [!UICONTROL Unique Trait Realizations] dan de [!UICONTROL Total Trait Population]. Is dit normaal?**

U ziet dit omdat de [!UICONTROL Unique Trait Realizations] realtimecijfers zijn, maar de rapportagetaken voor het berekenen van de [!UICONTROL Total Trait Population] worden niet in real time uitgevoerd. Het aantal [!UICONTROL Total Trait Population] moet binnen een paar dagen hoger zijn dan het aantal [!UICONTROL Unique Trait Realizations].
