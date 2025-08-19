---
description: Begin hier voor informatie over het maken van /event vraag aan DCS. Deze sectie omvat informatie over vraagsyntaxis, parameters, het formatteren, en een verzoekvoorbeeld.
seo-description: Start here for information about making /event calls to the DCS. This section includes information about call syntax, parameters, formatting, and a request example.
seo-title: Send Data to the DCS
solution: Audience Manager
title: Gegevens verzenden naar de DCS
uuid: 024e307d-bfcb-46cf-ac3a-fc71df0248fe
feature: DCS
exl-id: 8a6798c3-aafd-48c8-acd7-a0e29e04dc8e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '392'
ht-degree: 1%

---

# Gegevens verzenden naar de DCS {#send-data-to-the-dcs}

Begin hier voor informatie over het maken van `/event` vraag aan [!DNL DCS]. Deze sectie omvat informatie over vraagsyntaxis, parameters, het formatteren, en een verzoekvoorbeeld.

>[!NOTE]
>
>In de code en de voorbeelden, *cursief* vertegenwoordigt veranderlijke placeholder. Vervang een reële waarde voor de tijdelijke aanduiding wanneer u gegevens naar de [!DNL DCS] verzendt met deze methode.

## Syntaxis bellen {#dcs-call-syntax}

Een standaard `URL` -tekenreeks die gegevens naar [!DNL DCS] verzendt, gebruikt de onderstaande syntaxis.

```js
https://domain_alias.demdex.net/event?key1=val1&key2=val2&d_dst=1&d_rtbd=json&d_cb=callback
```

>[!NOTE]
>
>U kunt ook gegevens naar de [!DNL DCS] verzenden met de methode `POST` . De vraagsyntaxis wordt beschreven in [ DCS API Methoden ](../../../api/dcs-intro/dcs-api-reference/dcs-api-methods.md).

## Beloproepparameters {#dcs-call-parameters}

In de volgende tabel worden de basiscomponenten van een eenvoudige [!DNL DCS] -aanroep gedefinieerd.

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
      <li id="li_74624CA78D6F4536A8164AE1FA1DECB9">Uw domeinalias die door <span class="keyword"> Audience Manager </span> wordt toegewezen (b.v., <code> my_domain.demdex.net</code>). </li> 
      <li id="li_08ABE91CA247403AA480B3FB4BEF83BA">Het doeldomein, dat altijd <code> demdex.net</code> is. Zie <a href="../../../reference/demdex-calls.md"> Begrip Vraag aan het Domein van de Index </a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> /event?</code> </p> </td> 
   <td colname="col2"> <p>Dit deel van de oproep: </p> <p> 
     <ul id="ul_6332444A305A4F12A7CBE471CA508516"> 
      <li id="li_1C5C111B2B0E4621B3FC0C20D6516041">Identificeert de vraag als gebeurtenisvraag. </li> 
      <li id="li_DBCE9B1C70604A629ECD7AC0A9052198">Bepaalt het begin van het koord URL dat de gegevens bevat u naar <span class="wintitle"> DCS </span> wilt verzenden. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> key</code> </p> </td> 
   <td colname="col2"> <p>Een unieke id in het sleutelwaardepaar. </p> <p>Deze zeer belangrijk-waardeparen gebruiken een specifiek voorvoegsel om het type van gegevens te identificeren u naar <span class="wintitle"> DCS </span> verzendt. Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md"> Ondersteunde kenmerken voor DCS API-aanroepen </a> voor meer informatie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> val</code> </p> </td> 
   <td colname="col2"> <p>Een waarde van de variabele die tot een reeks behoort die door een sleutel in het zeer belangrijk-waardepaar wordt bepaald. </p> <p>Bij het werken met waarden: </p> <p> 
     <ul id="ul_624DC78759F74AD8920220058E54E083"> 
      <li id="li_091E5B4820EC4A93B775433E428E74AB">Tekenreeksgegevens tussen dubbele aanhalingstekens plaatsen (bijvoorbeeld <code> age="41 to 55"</code>). </li> 
      <li id="li_C558E3BA6EE34413BBBB962D4CD0D10E">U kunt meerdere toetsen binnen doorgeven op één waarde (bijvoorbeeld <i><code>key</i>=<i>val1,val2,val3</i></code></i> ). </li> 
     </ul> </p> <p>Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-key-format.md"> Formatterend zeer belangrijk-waardeparen in Vraag DCS </a>. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> 
     <ul id="ul_36E2C1A0538D4D2C94DFC1335720A524"> 
      <li id="li_8902EED431CE4F0189A94868FA52DB1F"> <code> d_dst=1</code> </li> 
      <li id="li_4B6B29499D444E31808DE0A9AA0442D0"> <code> d_rtbd=json</code> </li> 
      <li id="li_3430CD0438604B83BE6437E6EC480816"> <code>d_cb=<i>callback</i></code> </li>
     </ul> </p> </td> 
   <td colname="col2"> <p>Optionele responsparameters. </p> <p> Geen van deze zijn vereist om gegevens naar <span class="wintitle"> DCS </span> te verzenden. Als u echter wilt dat de <span class="wintitle"> DCS </span> een reactie retourneert, moet u <code> d_rtbd=json</code> in de aanvraag opnemen. </p> <p>Zie <a href="../../../api/dcs-intro/dcs-api-reference/dcs-keys.md#d-attributes"> d_sleutel-waarde Gedefinieerde paren </a>. </p> </td> 
  </tr>
 </tbody>
</table>

## Voorbeeld van oproep {#dcs-sample-call}

In dit voorbeeld wordt getoond hoe het fictieve bedrijf [!DNL Acme, Inc.] gegevens naar de [!DNL DCS] verzendt via een [!DNL HTTP] -aanroep. Deze aanroep bevat de optionele parameters `d_dst=1` , `d_rtbd=json` en `d_cb=callback` . Deze geven aan dat [!DNL Acme] een [!DNL JSON] reactie van de [!DNL DCS] wil ontvangen met een callback-functie. Onthoud, dit is slechts een voorbeeld. Knip en plak deze code niet.

```js
https://acme_aam_domain.demdex.net/event?videoTypeID=2&data=moarData&d_dst=1&d_rtbd=json&d_cb=acme_callback
```

## Volgende stappen {#dcs-next-steps}

Nu u bekend bent met het verzenden van gegevens naar de [!DNL DCS], is het tijd om te bekijken hoe u gegevens ervan kunt terugkrijgen en die informatie kunt parseren. Zie [ Gegevens van DCS ](../../../api/dcs-intro/dcs-event-calls/dcs-url-receive.md) ontvangen.

>[!MORELIKETHIS]
>
>* [Sleutelwaardeparen](../../../reference/key-value-pairs-explained.md)
