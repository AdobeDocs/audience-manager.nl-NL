---
seo-title: Server-aan-Server DCS API Vraag maken
solution: Audience Manager
title: Server-aan-Server DCS API Vraag maken
uuid: bdfe3430-e27f-4a5c-88d9-ae164d28f601
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '344'
ht-degree: 0%

---


# Server-aan-Server DCS API Vraag maken {#making-server-to-server-dcs-api-calls}

De vraag vereist de gastheernaam van de regionale server DCS en gebruiker - identiteitskaart Als u niet over de vereiste gebruikers- en regio-id&#39;s beschikt, raadpleegt u [Gebruikersnamen en -gebieden ophalen uit een DCS-reactie](/help/using/api/dcs-intro/dcs-s2s/dcs-aam-ids.md) en/of [Experience Cloud](/help/using/api/dcs-intro/dcs-s2s/dcs-mcid-ids.md). Zodra u gebruiker en gebied IDs hebt, kunt u server-aan-server vraag aan DCS maken. Zie deze sectie voor syntaxis en voorbeelden.

>[!NOTE]
>
>In de code en voorbeelden staat *cursief* voor een variabele plaatsaanduiding. Vervang een reële waarde voor placeholder wanneer u server-aan-server vraag aan [!DNL DCS].

## De Syntaxis van de vraag en Voorbeeld {#call-syntax-example}

Een basisverzoek van server naar server dat gegevens naar de [!DNL DCS] syntaxis verzendt gebruikt hieronder wordt getoond die.

```js
"Host:domain_alias.demdex.net" "https://DCS_host_name.demdex.net/event?d_rtbd=json&d_jsonv=1&d_uuid=userID
```

Een steekproefvraag kijkt gelijkaardig aan het volgende voorbeeld.

```
"Host:foo.demdex.net" "https://usw2.demdex.net/event?d_rtbd=json&d_jsonv=1& d_uuid=123456789"`
```

## Beloproepparameters {#call-parameters}

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Uw domeinalias toegewezen door <span class="keyword"> Audience Manager</span> (bijvoorbeeld <i><code> my_domain.demdex.net</code></i>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Het doeldomein, dat altijd is <i><code> demdex.net</code></i>. Zie het <a href="../../../reference/demdex-calls.md"> Begrip van Vraag aan het Domein</a>van de Index. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> <i>DCS host name</i>.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>De http-headerhostparameter die de naam van de regionale <span class="wintitle"> DCS</span> -server weergeeft. De gastheernaam is gebonden aan een gebiedsidentiteitskaart, die is waarom u dit alvorens deze types van vraag nodig hebt te maken. Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-regions.md"> ID's, locaties en hostnamen van DCS-regio's</a>. </p> </td> 
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
   <td colname="col2"> <p>Dit is de unieke sleutel van identiteitskaart van de gebruiker die de waarde van de gebruiker van de <span class="keyword"> Audience Manager</span> in een zeer belangrijk-waardepaar houdt. </p> <p>Gebruik <code><i>d_uuid</i></code> als u de gebruikersnaam van de <span class="keyword"> Audience Manager</span> doorgeeft. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><code>d_mid=<i>Experience Cloud user ID</i></code> </p> </td> 
   <td colname="col2"> <p>Dit is de unieke sleutel van identiteitskaart van de gebruiker die de waarde van <span class="keyword"> Experience Cloud</span> gebruiker - identiteitskaart in een zeer belangrijk-waardepaar houdt. Zie ook <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#get-user-ids-from-service-cookie"> De gebruikersnaam ophalen uit de ID Service Cookie</a>. </p> <p>Gebruik deze optie <i><code> d_mid</code></i> als u een <span class="keyword"> Experience Cloud</span> -id doorgeeft die is vastgelegd via de <span class="keyword"> Experience Cloud</span> -id-service. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"><code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"><code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"><code>d_cb=<i>callback</i></code> </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionele responsparameters. </p> <p> Geen van deze zijn vereist om gegevens naar <span class="wintitle"> DCS</span>te verzenden. Nochtans, als u <span class="wintitle"> DCS</span> een reactie wilt terugkeren, moet u <i><code> d_rtbd=json</code></i> in uw verzoek omvatten. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Samplereactie {#sample-response}

Zie Gegevens [ontvangen van DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).
