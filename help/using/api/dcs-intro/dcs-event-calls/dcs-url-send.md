---
description: Begin hier voor informatie over het maken van /event vraag aan DCS. Deze sectie omvat informatie over vraagsyntaxis, parameters, het formatteren, en een verzoekvoorbeeld.
seo-description: Begin hier voor informatie over het maken van /event vraag aan DCS. Deze sectie omvat informatie over vraagsyntaxis, parameters, het formatteren, en een verzoekvoorbeeld.
seo-title: Gegevens verzenden naar de DCS
solution: Audience Manager
title: Gegevens verzenden naar de DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Gegevens verzenden naar de DCS {#send-data-to-the-dcs}

Begin hier voor informatie over het maken van `/event` vraag aan [!UICONTROL DCS]. Deze sectie omvat informatie over vraagsyntaxis, parameters, het formatteren, en een verzoekvoorbeeld.

>[!NOTE]
>
>In de code en voorbeelden staat *cursief* voor een variabele plaatsaanduiding. Vervang een reële waarde voor de tijdelijke aanduiding wanneer u gegevens naar de tijdelijke aanduiding verzendt [!UICONTROL DCS] met deze methode.

## Syntaxis bellen {#dcs-call-syntax}

Een basistekenreeks `URL` die gegevens naar de bron verzendt, [!UICONTROL DCS] gebruikt de hieronder getoonde syntaxis.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>U kunt gegevens ook naar de server verzenden [!UICONTROL DCS] met de `POST` methode. De vraagsyntaxis wordt beschreven in Methoden [](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md)DCS API.

## Beloproepparameters {#dcs-call-parameters}

De volgende lijst bepaalt de basiscomponenten van een eenvoudige [!UICONTROL DCS] vraag.

<table id="table_5F6A5B324EB848168543386516FBF384"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Component </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> domain alias.demdex.net</code> </p> </td> 
   <td colname="col2"> <p>Dit deel van de vraag bevat: </p> <p> 
     <ul id="ul_3EDA9C7BA6794D06BCB07A75A9BD2372"> 
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Uw domeinalias die is toegewezen door <span class="keyword"> Audience Manager</span> (bijvoorbeeld <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Het doeldomein, dat altijd is <code> demdex.net</code>. Zie het <a href="../../../reference/demdex-calls.md"> Begrip van Vraag aan het Domein</a>van de Index. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dit deel van de oproep: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identificeert de vraag als gebeurtenisvraag. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Definieert het begin van de URL-tekenreeks die de gegevens bevat die u naar de <span class="wintitle"> DCS</span>wilt verzenden. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Een unieke id in het sleutelwaardepaar. </p> <p>Deze sleutel-waarde paren gebruiken een specifiek voorvoegsel om het type van gegevens te identificeren u naar <span class="wintitle"> DCS</span>verzendt. Voor meer informatie, zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Gesteunde Attributen voor Vraag</a>DCS API. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Een waarde van de variabele die tot een reeks behoort die door een sleutel in het zeer belangrijk-waardepaar wordt bepaald. </p> <p>Bij het werken met waarden: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Tekenreeksgegevens tussen dubbele aanhalingstekens plaatsen (bijvoorbeeld <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">U kunt meerdere toetsen binnen op één waarde (bijvoorbeeld <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Zie het Opmaken van zeer belangrijke-waardeparen in Vraag <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"></a>DCS. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionele responsparameters. </p> <p> Geen van deze zijn vereist om gegevens naar <span class="wintitle"> DCS</span>te verzenden. Nochtans, als u <span class="wintitle"> DCS</span> een reactie wilt terugkeren, moet u <code> d_rtbd=json</code> in uw verzoek omvatten. </p> <p>Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ sleutel-waarde Gedefinieerde</a>paren. </p> </td> 
  </tr>
 </tbody>
</table>

## Voorbeeld van oproep {#dcs-sample-call}

Dit voorbeeld toont het fictieve bedrijf dat gegevens [!DNL Acme, Inc.] verzendt naar [!UICONTROL DCS] via een [!DNL HTTP] vraag. Merk op dat deze vraag de facultatieve parameters `d_dst=1`, `d_rtbd=json`, en `d_cb=callback`omvat. Deze wijzen erop dat [!DNL Acme] wil een [!DNL JSON] reactie van [!UICONTROL DCS] met een callback functie ontvangen. Onthoud, dit is slechts een voorbeeld. Knip en plak deze code niet.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Volgende stappen {#dcs-next-steps}

Nu je bekend bent met het verzenden van gegevens naar de [!UICONTROL DCS], is het tijd om te bekijken hoe je gegevens ervan kunt terugkrijgen en die informatie kan parseren. Zie Gegevens [ontvangen van DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Belangrijke paar uitgelegd](../../../reference/key-value-pairs-explained.md)

