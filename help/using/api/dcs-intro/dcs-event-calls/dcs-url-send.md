---
description: Begin hier voor informatie over het maken van /event vraag aan DCS. Deze sectie omvat informatie over vraagsyntaxis, parameters, het formatteren, en een verzoekvoorbeeld.
seo-description: Begin hier voor informatie over het maken van /event vraag aan DCS. Deze sectie omvat informatie over vraagsyntaxis, parameters, het formatteren, en een verzoekvoorbeeld.
seo-title: Data verzenden naar de DCS
solution: Audience Manager
title: Data verzenden naar de DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '421'
ht-degree: 6%

---


# Data verzenden naar de DCS {#send-data-to-the-dcs}

Begin hier voor informatie over het maken van `/event` vraag aan [!DNL DCS]. Deze sectie omvat informatie over vraagsyntaxis, parameters, het formatteren, en een verzoekvoorbeeld.

>[!NOTE]
>
>In de code en de voorbeelden, *italics* vertegenwoordigt veranderlijke placeholder. Vervang een reële waarde voor de plaatsaanduiding wanneer u gegevens naar [!DNL DCS] met deze methode verzendt.

## Syntaxis {#dcs-call-syntax} aanroepen

Een basis `URL` koord dat gegevens naar [!DNL DCS] verzendt gebruikt de hieronder getoonde syntaxis.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>U kunt ook gegevens naar [!DNL DCS] verzenden door de methode `POST` te gebruiken. De vraagsyntaxis wordt beschreven in [DCS API Methods](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Parameters {#dcs-call-parameters} aanroepen

De volgende lijst bepaalt de basiscomponenten van een eenvoudige [!DNL DCS] vraag.

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
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Het bestemmingsdomein, dat altijd <code> demdex.net</code> is. Zie <a href="../../../reference/demdex-calls.md">Inzicht in calls naar het Demdex-domein</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dit deel van de oproep: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identificeert de vraag als gebeurtenisvraag. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Bepaalt het begin van het koord URL dat de gegevens bevat u naar <span class="wintitle"> DCS</span> wilt verzenden. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Een unieke id in het sleutelwaardepaar. </p> <p>Deze sleutel-waarde paren gebruiken een specifiek voorvoegsel om het type van gegevens te identificeren u naar <span class="wintitle"> DCS</span> verzendt. Voor meer informatie, zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Gesteunde Attributen voor Vraag DCS API</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Een waarde van de variabele die tot een reeks behoort die door een sleutel in het zeer belangrijk-waardepaar wordt bepaald. </p> <p>Bij het werken met waarden: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Tekenreeksgegevens tussen dubbele aanhalingstekens plaatsen (bijvoorbeeld <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">U kunt meerdere toetsen binnen op één waarde doorgeven (bijvoorbeeld <i><code>key</i>=<i>val1,val2,val3</i></code></i>). </li> 
     </ul> </p> <p>Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> het Opmaken van zeer belangrijke-waardeparen in Vraag DCS</a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionele responsparameters. </p> <p> Geen van deze zijn vereist om gegevens naar <span class="wintitle"> DCS</span> te verzenden. Nochtans, als u <span class="wintitle"> DCS</span> een reactie wilt terugkeren, moet u <code> d_rtbd=json</code> in uw verzoek omvatten. </p> <p>Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_ Key-Value Gedefinieerde paren</a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Voorbeeld van aanroep {#dcs-sample-call}

In dit voorbeeld wordt het fictieve bedrijf [!DNL Acme, Inc.] getoond dat gegevens via een [!DNL HTTP]-aanroep naar [!DNL DCS] verzendt. Merk op dat deze vraag de facultatieve parameters `d_dst=1`, `d_rtbd=json`, en `d_cb=callback` omvat. Deze wijzen erop dat [!DNL Acme] een [!DNL JSON] reactie van [!DNL DCS] met een callback functie wil ontvangen. Onthoud, dit is slechts een voorbeeld. Knip en plak deze code niet.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Volgende stappen {#dcs-next-steps}

Nu u vertrouwd bent met het verzenden van gegevens naar [!DNL DCS], is het tijd om te bekijken hoe te om gegevens terug van het terug te krijgen en die informatie te ontleden. Zie [Gegevens ontvangen van DCS](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md).

>[!MORELIKETHIS]
>
>* [Sleutelwaardeparen](../../../reference/key-value-pairs-explained.md)

