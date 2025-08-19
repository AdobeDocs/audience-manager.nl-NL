---
description: Het uitgaande proces van de gegevensoverdracht in real time keert gebruikersgegevens als reeks voorwerpen JSON terug die binnen met een methode POST worden overgegaan.
seo-description: The outbound real-time data transfer process returns user data as a series of JSON objects passed in with a POST method.
seo-title: Real-Time Outbound Data Transfers
solution: Audience Manager
title: Uitgaande gegevensoverdrachten in real time
uuid: 1895e818-7ab8-4569-a920-4b0a4c8b83d2
feature: Outbound Data Transfers
exl-id: 12aee831-1a44-4cd6-aeba-7738a584dfe7
source-git-commit: 0245dd11de31c3139c5df5dc78100f0d3935aa2e
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 0%

---

# Uitgaande gegevensoverdrachten in real time {#real-time-outbound-data-transfers}

Het uitgaande real-time gegevensoverdrachtproces levert gebruikersgegevens als reeks [!DNL JSON] geformatteerde berichten aan een bestemmingsplatform.

<!-- c_outbound_json.xml -->

## Aanbevelingen

Om deze methode te gebruiken, moet het bestemmingsplatform aan de volgende vereisten voldoen:

* Het moet een eindpunt [!DNL URL] verstrekken dat kan schrapen om een hoog volume van berichten van Audience Manager te ontvangen;
* Gegevens in de [!DNL JSON] -indeling (`Content-type: application/json` ) moeten worden geaccepteerd.
* Beveiligde gegevensoverdracht `HTTPS` moet worden geaccepteerd. [!DNL Audience Manager] verzendt geen berichten via het onveilige `HTTP` -protocol.

## Frequentie

Deze methode van de gegevensoverdracht kan gegevens in bijna real time verzenden aangezien de gebruikers voor segmenten kwalificeren. In real time berichten worden slechts geleverd terwijl de gebruiker online en actief zichtbaar aan het netwerk van Audience Manager Edge is. Deze methode kan optioneel ook batches offline of aan boord genomen gegevens zo vaak verzenden als elke 24 uur.

## Batchoverdracht

Zowel worden de in real time als de partijoverdrachten verzonden naar het zelfde eindpunt en gebruiken het zelfde berichtformaat. Wanneer de partijoverdrachten worden toegelaten, zal het bestemmingsplatform een piek in berichtvolume zien terwijl de partijberichten worden geleverd. Veel van de segmentkwalificaties die door berichten in real time worden verzonden zullen in de partijberichten worden herhaald. De overdracht van partijen zal slechts de segmentkwalificaties (of niet-kwalificaties) omvatten die sinds de laatste partij werd geleverd zijn veranderd.

## Snelheidslimieten

Er zijn geen tariefgrenzen die op de productie van geleverde berichten worden geplaatst. Door tarieflimieten in te stellen kunnen gegevens verloren gaan.

## Vereiste reacties

Standaard moet de ontvangende server de `200 OK` -code retourneren om een geslaagde ontvangst aan te geven. Andere codes worden als mislukkingen geïnterpreteerd. Deze reactie wordt verwacht binnen 3000 milliseconden. Als reactie op een fout zal [!DNL Audience Manager] slechts één poging opnieuw proberen.

## Parameters

In de volgende tabel worden de elementen in het [!DNL JSON] -gegevensbestand gedefinieerd die u naar de bestemming verzendt.

<table id="table_68475F9D01ED4A44B5909234114AEDE2"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Datatype </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>ProcessTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>Tijdstip waarop het verzoek is uitgevoerd. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_DPID</i></code> </td> 
   <td colname="col2"> <p>Geheel </p> </td> 
   <td colname="col3"> <p>Een identiteitskaart die op het type van apparaat IDs wijst die binnen het bericht, in het bezit User.DataPartner_UID wordt bevat. </p> 
    <ul id="ul_159306B0CF304DE0B9A9836D41263E70"> 
     <li id="li_46F9F4F9DDC34AB683AE2DF0317FBCAC">Android-id's (GAID): <code> 20914</code> </li> 
     <li id="li_57DEB2A7B9024A94A0E302EEA967AB0B">iOS-id's (IDFA): <code> 20915</code> </li>
     <li>Web-/cookie-id's: varieert per doelplatform</li>
    </ul> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Client_ID</i></code> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Vertegenwoordigt de doelrekening in het bestemmingsplatform. Deze id is afkomstig van het doelplatform.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>AAM_Destination_ID</i></code> </td> 
   <td colname="col2"> <p>Geheel </p> </td> 
   <td colname="col3"> <p>De id van het Audience Manager-object 'destination'. Deze id is afkomstig uit Audience Manager.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User_count</i></code> </td> 
   <td colname="col2"> <p>Geheel </p> </td> 
   <td colname="col3"> <p>Het totale aantal gebruikers in de <code> POST</code> -aanvraag. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Users</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Een array van gebruikersobjecten. Door gebrek, zal elk bericht tussen 1 en 10 gebruikers bevatten, om de berichtgrootte optimaal te houden. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_UUID</i></code> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>De <span class="keyword"> Audience Manager </span> UUID. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.DataPartner_UUID</i></code> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>UUID van doelplatform of de algemene apparaat-id. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>User.AAM_Regions</i></code> </td> 
   <td colname="col2"> Array </td> 
   <td colname="col3"> De <span class="keyword"> Audience Manager </span> gebied identiteitskaart waar wij dit apparaat hebben gezien. Als het apparaat bijvoorbeeld enige activiteit had in Parijs (Europa), zou de regio-id <code> 6</code> zijn. Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> DCS Gebied IDs, Locaties, en de Namen van de Gastheer </a>. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segments</i></code> </td> 
   <td colname="col2"> <p>Array </p> </td> 
   <td colname="col3"> <p>Een array van segmentobjecten. Voor berichten in real time, bevat de serie alle segmenten de gebruiker tot behoort. Voor batchberichten bevat de array alleen segmentwijzigingen sinds de laatste batch.</p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Segment_ID</i></code> </td> 
   <td colname="col2"> <p>Geheel </p> </td> 
   <td colname="col3"> <p>De id voor het segment. In de meeste gevallen is dit de segment-id die door Audience Manager wordt gegenereerd (een geheel getal). In sommige gevallen, als het bestemmingsplatform toestaat, kunnen de klanten het segment herkenningsteken in het Audience Manager gebruikersinterface (open tekstgebied) bepalen, die dan in dit bezit zou weerspiegelen. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.Status</i></code> </td> 
   <td colname="col2"> <p>Geheel </p> </td> 
   <td colname="col3"> <p>Hiermee definieert u de status van een gebruiker in het segment. Accepteert de volgende waarden: </p> 
    <ul id="ul_42C4625E9543494586CF6D851A94E048"> 
     <li id="li_6F13809ECD78403FB3BDA626403E4B57"><code> 1</code>: Actief (standaard) </li> 
     <li id="li_10952C8DF7AF4593805FA29028257E38"><code> 0</code>: Niet actief, niet-gesegmenteerd of optioneel. </li> 
    </ul> <p>Gebruikers worden losgekoppeld wanneer ze: </p> 
    <ul id="ul_E17B080D8DF14D548E1142A9201C1C14"> 
     <li id="li_8352B919A87242E68716FB9EC0443407">Verwijderd uit een segment dat op de segmentregel wordt gebaseerd. </li> 
     <li id="li_83CFEAFE94C14A11AE198D56E80EBB8C">Verwijderd uit een segment dat op het <a href="../../../features/traits/segment-ttl-explained.md"> tijd-aan-levende interval van het segment </a> wordt gebaseerd. </li> 
     <li id="li_F48D1052BA2B45108225641292CC748D">Verplaatst naar een inactieve toestand als deze de afgelopen 120 dagen niet is waargenomen. </li>
     <li>Verwijderd vanwege een verzoek tot wijziging van de privacy (bijvoorbeeld <span class="keyword"> GDPR </span> )</li>
    </ul> <p>Alle partner IDs die aan <span class="keyword"> Audience Manager </span> identiteitskaart worden gesynchroniseerd zal de <code> "Status":"0"</code> vlag ontvangen wanneer een gebruiker wordt unsegmented. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"><code><i>Segment.DateTime</i></code> </td> 
   <td colname="col2"> <p>DateTime </p> </td> 
   <td colname="col3"> <p>De tijd toen de user-segment kwalificatie onlangs werd geverifieerd.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Beveiliging

U kunt uw uitgaande proces van de gegevensoverdracht in real time beveiligen door [ verzoeken van HTTP te ondertekenen ](../../../integration/receiving-audience-data/real-time-outbound-transfers/digitally-signed-http-requests.md) gebruikend privé sleutels of door [!DNL Audience Manager] te hebben voor authentiek verklaard door het [ OAuth 2.0 ](../../../integration/receiving-audience-data/real-time-outbound-transfers/oauth-in-outbound-transfers.md) protocol.

## Verzoek

Een verzoek in real time kan gelijkaardig aan het volgende kijken:

```js
{
"ProcessTime": "Wed Jul 27 16:17:42 UTC 2016",
"User_DPID": "12345",
"Client_ID": "74323",
"AAM_Destination_Id": "423",
"User_count": "2",
"Users": [{  
   "AAM_UUID": "19393572368547369350319949416899715727",
   "DataPartner_UUID": "4250948725049857",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "14356",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         },
         {
            "Segment_ID": "12176",
            "Status": "0",  
            "DateTime": "Wed Jul 27 16:17:22 UTC 2016"
         }
      ]
   },
   {
   "AAM_UUID": "0578240750487542456854736923319946899715232",
   "DataPartner_UUID": "848457757347734",
   "AAM_Regions": ["9"],
   "Segments": [{
            "Segment_ID": "10329",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
         },
         {
            "Segment_ID": "23954",
            "Status": "1",
            "DateTime": "Wed Jul 27 16:17:21 UTC 2016"
        }]
    }]
}
```
