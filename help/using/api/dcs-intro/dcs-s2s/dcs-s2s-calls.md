---
seo-title: Server-naar-server DCS-API-calls uitvoeren
solution: Audience Manager
title: Server-naar-server DCS-API-calls uitvoeren
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
feature: DCS
description: De syntaxis van de vraag, voorbeeld, en parameters wanneer het maken van server-aan-server DCS API vraag
translation-type: tm+mt
source-git-commit: 4dbe9a838470d1fe54538df12605a0e0aa1e0510
workflow-type: tm+mt
source-wordcount: '356'
ht-degree: 6%

---


# Server-naar-server DCS-API-calls uitvoeren {#making-server-to-server-dcs-api-calls}

De vraag vereist de gastheernaam van de regionale server DCS en gebruiker - identiteitskaart Zie [Gebruikersnamen en -gebieden ophalen uit een DCS-respons](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) en/of [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md) als u niet over de vereiste gebruikers- en regio-id&#39;s beschikt. Zodra u gebruiker en gebied IDs hebt, kunt u server-aan-server vraag aan DCS maken. Zie deze sectie voor syntaxis en voorbeelden.

>[!NOTE]
>
>In de code en de voorbeelden, *italics* vertegenwoordigt veranderlijke placeholder. Vervang een reële waarde voor de plaatsaanduiding wanneer u server-naar-server aanroept aan [!DNL DCS].

## De Syntaxis van de vraag en Voorbeeld {#call-syntax-example}

Een basisverzoek van server naar server dat gegevens naar [!DNL DCS] verzendt gebruikt de hieronder getoonde syntaxis.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Een steekproefvraag kijkt gelijkaardig aan het volgende voorbeeld.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Parameters {#call-parameters} aanroepen

<table id="table_3AF4466009B64F0C9CBE7904A4096E0C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> <i>domain alias</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Dit deel van de vraag bevat: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Uw domeinalias die is toegewezen door <span class="keyword"> Audience Manager</span> (bijvoorbeeld <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Het bestemmingsdomein, dat altijd <i><code> demdex.net</code></i> is. Zie <a href="../../../reference/demdex-calls.md">Inzicht in calls naar het Demdex-domein</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>De http-headerhostparameter die de naam van de regionale <span class="wintitle"> DCS</span>-server weergeeft. De gastheernaam is gebonden aan een gebiedsidentiteitskaart, die is waarom u dit alvorens deze types van vraag nodig hebt te maken. Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> DCS Gebied IDs, Locaties, en de Namen van de Gastheer</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dit deel van de oproep: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identificeert de vraag als gebeurtenisvraag. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definieert het begin van de URL-tekenreeks die de gegevens bevat die u naar de DCS wilt verzenden. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_uuid= <i>Audience Manager user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dit is de unieke sleutel van gebruikersidentiteitskaart die <span class="keyword"> Audience Manager</span> gebruiker - identiteitskaart in een zeer belangrijk-waardepaar houdt. </p> <p>Gebruik <code><i>d_uuid</i></code> als u in <span class="keyword"> Audience Manager</span> gebruiker - identiteitskaart overgaat </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dit is de unieke sleutel van gebruikersidentiteitskaart die <span class="keyword"> Experience Cloud </span> gebruikersidentiteitskaart in een zeer belangrijk-waardepaar houdt. Zie ook <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> Krijg de Gebruiker - identiteitskaart van de Koekje van de Dienst van identiteitskaart</a>. </p> <p>Gebruik <i><code> d_mid</code></i> als u een <span class="keyword"> Experience Cloud</span> ID doorgeeft die van de <span class="keyword"> Experience Cloud</span> dienst van identiteitskaart wordt gevangen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionele responsparameters. </p> <p> Geen van deze zijn vereist om gegevens naar <span class="wintitle"> DCS</span> te verzenden. Nochtans, als u <span class="wintitle"> DCS</span> een reactie wilt terugkeren, moet u <i><code> d_rtbd=json</code></i> in uw verzoek omvatten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Samplereactie {#sample-response}

Zie [Gegevens ontvangen van DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
