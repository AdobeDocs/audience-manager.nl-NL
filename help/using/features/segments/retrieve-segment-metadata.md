---
description: Wanneer de Audience Manager segmentinformatie naar een gegevenspartner verzendt, identificeert het deze voorwerpen met numerieke IDs. Als gegevenspartner, wanneer u deze informatie met uw klanten (of het werk met het zelf) deelt, verstrekken een daadwerkelijke naam en een beschrijving een betere ervaring voor klanten in rapporten, dashboards, of ander gebruikersinterface (UI). De partners van gegevens kunnen deze vriendschappelijke namen ter beschikking stellen aan hun klanten met of de hand of geautomatiseerde methodes die in deze sectie worden beschreven.
seo-description: Wanneer de Audience Manager segmentinformatie naar een gegevenspartner verzendt, identificeert het deze voorwerpen met numerieke IDs. Als gegevenspartner, wanneer u deze informatie met uw klanten (of het werk met het zelf) deelt, verstrekken een daadwerkelijke naam en een beschrijving een betere ervaring voor klanten in rapporten, dashboards, of ander gebruikersinterface (UI). De partners van gegevens kunnen deze vriendschappelijke namen ter beschikking stellen aan hun klanten met of de hand of geautomatiseerde methodes die in deze sectie worden beschreven.
seo-title: Segmentmetagegevens ophalen
solution: Audience Manager
title: Segmentmetagegevens ophalen
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '598'
ht-degree: 0%

---


# Segmentmetagegevens ophalen {#retrieving-segment-metadata}

Wanneer de Audience Manager segmentinformatie naar een gegevenspartner verzendt, identificeert het deze voorwerpen met numerieke IDs. Als gegevenspartner, wanneer u deze informatie met uw klanten (of het werk met het zelf) deelt, verstrekken een daadwerkelijke naam en een beschrijving een betere ervaring voor klanten in rapporten, dashboards, of andere gebruikersinterfaces ([!DNL UI]). De partners van gegevens kunnen deze vriendschappelijke namen ter beschikking stellen aan hun klanten met of de hand of geautomatiseerde methodes die in deze sectie worden beschreven.

## Handmatige methode {#manual-method}

Als gegevenspartner, wordt u waarschijnlijk gewend aan het krijgen van publieksmeta-gegevens van uw klanten door handprocessen. Dit kunnen bestanden zijn die zijn gekoppeld aan e-mailberichten of bestanden die klanten toevoegen via een [!DNL UI] bestand dat u voor dit doel hebt gemaakt en onderhouden. Deze processen werken, maar zijn vaak omslachtig, tijdrovend, en kunnen handwerk van de gegevensingang vereisen. Deze methodes worden vaak gebruikt om een integratie te helpen snel in werking te stellen, maar zij verstrekken niet de beste klantenervaring op de lange termijn. Als alternatief kunt u de metagegevens van segmenten automatisch ophalen [!DNL Audience Manager] [!DNL API] met de code.

## Geautomatiseerde methode {#automated-method}

[!DNL Audience Manager] verstrekt een reeks [REST APIs](../../api/rest-api-main/rest-api-main.md) die u segmentmeta-gegevens automatisch laten terugwinnen. Met [!DNL API], kunt u banen tot stand brengen die segmentmeta-gegevens met geplande intervallen of automatisch terugwinnen, wanneer u [!DNL Audience Manager] gegevens verwerkt en een nieuwe segmentidentiteitskaart vindt. Zie de onderstaande stappen voor meer informatie.

### Stap 1: De Audience Manager-API&#39;s bekijken

De sectie Aan de [slag met REST APIs](../../api/rest-api-main/aam-api-getting-started.md) bevat informatie over algemene vereisten, authentificatie, beschikbare methodes, enz. Dit is een goede plek om te beginnen als je nog niet met de [!DNL Audience Manager][!DNL API] eerder hebt gewerkt.

### Stap 2: OAuth2-toegangsreferenties aanvragen

U hebt een cliënt identiteitskaart en geheim nodig om [!DNL API] vraag te maken. Tijdens het integratieproces kunt u een client-id en een geheim opvragen bij uw integratiespecialist. U kunt ook een e-mailverzoek verzenden naar [!UICONTROL Audience Manager Customer Care] op [!DNL amsupport@adobe.com].

### Stap 3: Verzamel klant-specifieke informatie van elke geïntegreerde klant

Vraag het volgende van elke geïntegreerde klant:

* Gebruikersnaam: Dit is voor een beperkte gebruiker die read-only toestemmingen voor de bestemming verbonden aan een specifieke integratie heeft.
* Wachtwoord: Het gebruikerswachtwoord.
* Doel-id: Dit is identiteitskaart (een geheel) verbonden aan de bestemming die voor de specifieke server-aan-server integratie wordt gecreeerd.

### Stap 4: Segmentmetagegevens ophalen met een API-aanroep

Nadat u de vorige stappen hebt uitgevoerd, kunt u een `GET` methode gebruiken om segmentmetagegevens op te halen. Voor een steekproefverzoek en een reactie, zie de Toewijzingen van de Bestemming van de [Terugkeer](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Deze vraag keert segmentgegevens terug die als zeer belangrijk-waardeparen in een [!DNL JSON] voorwerp worden geformatteerd. Enkele belangrijke segmentkenmerken die in de reactie worden geretourneerd, worden in de volgende tabel weergegeven.

<table id="table_446384AE9A36408A9C570CB7DB72C3D6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> destinationMappingId</code> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> Audience Manager</span> segment-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementName</code> </p> </td> 
   <td colname="col2"> <p>De segmentnaam. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementDescription</code> </p> </td> 
   <td colname="col2"> <p>Een tekst die het segment kort beschrijft. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> elementStatus</code> </p> </td> 
   <td colname="col2"> <p>De huidige status van de segmenttoewijzing. Tot de statusopties voor geretourneerde meldingen behoren: </p> 
    <ul id="ul_BA3A1F5A773D4ECD9A1A3A1118BDDA8A"> 
     <li id="li_A12B858BD0AD4F35BCD50A4D113D86FF"> <code> active</code> </li> 
     <li id="li_98C04A861C2D4364B5FBD24498E8E9C5"> <code> inactive</code> </li> 
     <li id="li_1913A10948894FF3B507C0A3FE775CC1"> <code> deleted</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>