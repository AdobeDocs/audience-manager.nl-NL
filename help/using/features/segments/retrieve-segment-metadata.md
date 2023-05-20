---
description: Wanneer de Audience Manager segmentinformatie naar een gegevenspartner verzendt, identificeert het deze voorwerpen met numerieke IDs. Als gegevenspartner, wanneer u deze informatie met uw klanten (of het werk met het zelf) deelt, verstrekken een daadwerkelijke naam en een beschrijving een betere ervaring voor klanten in rapporten, dashboards, of ander gebruikersinterface (UI). De partners van gegevens kunnen deze vriendschappelijke namen ter beschikking stellen aan hun klanten met of de hand of geautomatiseerde methodes die in deze sectie worden beschreven.
seo-description: When Audience Manager sends segment information to a data partner, it identifies these objects with numeric IDs. As a data partner, when you share this information with your customers (or work with it yourself), an actual name and description provide a better experience for customers in reports, dashboards, or other user interfaces (UI). Data partners can make these friendly names available to their customers with either the manual or automated methods described in this section.
seo-title: Retrieving Segment Metadata
solution: Audience Manager
title: Metadata van segmenten ophalen
uuid: 719e2c41-8788-4e8a-967a-e367421f9f84
feature: Segments
exl-id: 64922cf8-f7bf-4e33-871f-d33626b06360
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '520'
ht-degree: 1%

---

# Metadata van segmenten ophalen {#retrieving-segment-metadata}

Wanneer de Audience Manager segmentinformatie naar een gegevenspartner verzendt, identificeert het deze voorwerpen met numerieke IDs. Als gegevenspartner, wanneer u deze informatie met uw klanten (of het werk met het zelf) deelt, verstrekken een daadwerkelijke naam en een beschrijving een betere ervaring voor klanten in rapporten, dashboards, of andere gebruikersinterfaces ([!DNL UI]). De partners van gegevens kunnen deze vriendschappelijke namen ter beschikking stellen aan hun klanten met of de hand of geautomatiseerde methodes die in deze sectie worden beschreven.

## Handmatige methode {#manual-method}

Als gegevenspartner, wordt u waarschijnlijk gewend aan het krijgen van publieksmeta-gegevens van uw klanten door handprocessen. Dit kunnen bestanden zijn die zijn gekoppeld aan e-mailberichten of die afkomstig zijn van klanten die deze gegevens via een [!DNL UI] u hebt voor dit doel gebouwd en onderhouden. Deze processen werken, maar zijn vaak omslachtig, tijdrovend, en kunnen handwerk van de gegevensingang vereisen. Deze methodes worden vaak gebruikt om een integratie te helpen snel in werking te stellen, maar zij verstrekken niet de beste klantenervaring op de lange termijn. Als alternatief kunt u de [!DNL Audience Manager] [!DNL API] om automatisch segmentmetagegevens op te halen.

## Geautomatiseerde methode {#automated-method}

[!DNL Audience Manager] verstrekt een reeks van [REST API&#39;s](../../api/rest-api-main/rest-api-main.md) Hiermee kunt u automatisch segmentmetagegevens ophalen. Met de [!DNL API], kunt u banen creëren die segmentmeta-gegevens met geplande intervallen of automatisch terugwinnen wanneer u verwerkt [!DNL Audience Manager] gegevens en zoek een nieuwe segment-id. Zie de onderstaande stappen voor meer informatie.

### Stap 1: De Audience Manager-API&#39;s bekijken

De [Aan de slag met REST API&#39;s](../../api/rest-api-main/aam-api-getting-started.md) Deze sectie bevat informatie over algemene vereisten, authenticatie, beschikbare methoden, enz. Dit is een goede plek om te beginnen als je niet met de [!DNL Audience Manager] [!DNL API] voor.

### Stap 2: OAuth2-toegangsreferenties aanvragen

U hebt een client-id en een geheim nodig om [!DNL API] oproepen. Tijdens het integratieproces kunt u een client-id en een geheim opvragen bij uw integratiespecialist. U kunt ook een e-mailverzoek verzenden naar [!UICONTROL Audience Manager Customer Care] om [!DNL amsupport@adobe.com].

### Stap 3: Verzamel klant-specifieke informatie van elke geïntegreerde klant

Vraag het volgende van elke geïntegreerde klant:

* Gebruikersnaam: Dit is voor een beperkte gebruiker die read-only toestemmingen voor de bestemming verbonden aan een specifieke integratie heeft.
* Wachtwoord: Het gebruikerswachtwoord.
* Doel-id: Dit is identiteitskaart (een geheel) verbonden aan de bestemming die voor de specifieke server-aan-server integratie wordt gecreeerd.

### Stap 4: Segmentmetagegevens ophalen met een API-aanroep

Nadat u de vorige stappen hebt uitgevoerd, kunt u een `GET` methode om segmentmeta-gegevens terug te winnen. Voor een voorbeeldverzoek en een reactie raadpleegt u [Toewijzingen retourbestemming](../../api/rest-api-main/aam-api-destinations/aam-api-retrieve-destinations.md#return-dest-mappings). Deze vraag keert segmentgegevens terug die als zeer belangrijk-waardeparen in a worden geformatteerd [!DNL JSON] object. Enkele belangrijke segmentkenmerken die in de reactie worden geretourneerd, worden in de volgende tabel weergegeven.

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
