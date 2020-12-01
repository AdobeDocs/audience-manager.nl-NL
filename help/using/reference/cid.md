---
description: Werk uw code bij om d_cid of d_cid_ic te gebruiken in plaats van d_dpid en d_dpuuid. De variabelen DPID en DPUUID blijven werken, maar u zou hen moeten overwegen verouderd. Dit omvat variabelen DPID en DPUUID zonder het d_ prefix.
seo-description: Werk uw code bij om d_cid of d_cid_ic te gebruiken in plaats van d_dpid en d_dpuuid. De variabelen DPID en DPUUID blijven werken, maar u zou hen moeten overwegen verouderd. Dit omvat variabelen DPID en DPUUID zonder het d_ prefix.
seo-title: CID vervangt DPID en DPUUID
solution: Audience Manager
title: CID vervangt DPID en DPUUID
uuid: 3641eac5-b19e-45d5-bc1c-35a23b4bab8c
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '666'
ht-degree: 2%

---


# CID vervangt DPID en DPUUID{#cid-replaces-dpid-and-dpuuid}

Werk uw code bij om `d_cid` of `d_cid_ic` in plaats van `d_dpid` en `d_dpuuid` te gebruiken. De variabelen DPID en DPUUID blijven werken, maar u zou hen moeten overwegen verouderd. Dit omvat variabelen DPID en DPUUID zonder `d_ prefix`.

## DPID en DPUUID: Een revisie {#dpid-dpuuid-review}

DPID en DPUUID zijn zeer belangrijk-waardeparen die een gegevensleverancier identiteitskaart en een gebruiker - identiteitskaart bevatten. Deze sleutelwaardeparen koppelen leverancier-id&#39;s aan gebruiker-id&#39;s. Zij verzenden in gegevens tijdens gebeurtenisvraag, voor binnenkomende synchronisatiegebeurtenissen, en voor de vraag van identiteitskaart. Zonder deze id&#39;s zouden [!DNL Audience Manager] en andere services of functies geen manier hebben om id&#39;s aan te passen en te synchroniseren. Deze variabelen worden soms uitgedrukt met of zonder het voorvoegsel `d_` zoals hieronder getoond. Opmerking: in de code geeft *italics* een tijdelijke aanduiding voor een variabele aan.

<table id="table_932B4416AE1E44E4A1E98D779D3B1ED5"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabele </th> 
   <th colname="col2" class="entry"> Syntaxis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Data Provider ID (DPID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_0567D39DCE784C20A81EC0845C7B1C6B"> 
     <li id="li_DDD8C18266314987A7C802918F4892A8"> <code>d_dpid=<i>data provider ID</i></code> </li> 
     <li id="li_80185558932E416698ABD71158303EA8"> <code>dpid=<i>data provider ID</i></code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Unieke gebruikersnaam gegevensaanbieder (DPUUID) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EA7F769523B142CE8FF5886E5CDFF2D9"> 
     <li id="li_C984E2FF0A83495880BB87C610FA3F79"> <code>d_dpuuid=<i>data provider unique user ID</i></code> </li> 
     <li id="li_DCFFAC995DCC49F489ACEFD97A06F877"> <code>dpuuid=<i>data provider unique user ID</i></code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Deze sleutelwaardeparen werken nog, maar zijn afgekeurd. Werk de code bij om CID of CID_IC te gebruiken.

## CID en CID_IC: Info {#cid-cidic-about}

De sleutel-waardeparen CID en CID_IC vervangen DPID en DPUUID. Zij verstrekken de zelfde functies zoals DPID en DPUUID, maar zijn efficiënter omdat zij gegevensleverancier identiteitskaart (of integratiecode) en gebruiker - identiteitskaart in één enkel zeer belangrijk-waardepaar omvatten. In elk zeer belangrijk-waardepaar:

* Het symbool = scheidt de sleutel van zijn verwante waarden.
* Het niet-afdrukbare ASCII-teken %01 scheidt de waarden.

`d_cid` en  `d_cid_ic` gebruik de hieronder getoonde syntaxis. Opmerking: in de code geeft *italics* een tijdelijke aanduiding voor een variabele aan.

<table id="table_0C8A4F8FDBC84416B4EB476F67BCFA8E"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Variabele </th> 
   <th colname="col2" class="entry"> Syntaxis </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Klant-id (CID) </p> </td> 
   <td colname="col2"> <p> <code>d_cid=<i>data provider ID</i>%01<i>user ID</i></code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Code voor integratie van klant-id (CID_IC) </p> </td> 
   <td colname="col2"> <p> <code>d_cid_ic=<i>integration code</i>%01<i>user ID</i></code> </p> <p> Een <span class="term"> integratiecode</span> is een afwisselende identiteitskaart u in plaats van identiteitskaart van de Gegevensbron kunt gebruiken, die door <span class="keyword"> Audience Manager</span> wordt toegewezen. Zie <a href="../features/manage-datasources.md#create-data-source"> Een gegevensbron maken</a> als u een integratiecode moet configureren. </p> </td> 
  </tr> 
 </tbody> 
</table>

Zie ook [URL-variabelen en syntaxis voor opgegeven id&#39;s](../features/declared-ids.md#variables-and-syntax).

>[!NOTE]
>
>U kunt integratiecodes voor uw eigen gegevensbronnen en voor globale [gedeelde gegevensbronnen](../features/datasources-list-and-settings.md#settings-menu-options) gebruiken, die u toegang tot hebt. U kunt bijvoorbeeld integratiecodes gebruiken wanneer u werkt met gegevensbronnen van mobiele id&#39;s. Gebruik de volgende integratiecodes, precies zoals hieronder gespecificeerd:

* **DSID_20914** voor GAID, die apparaten vertegenwoordigt die het Android werkende systeem in werking stellen.
* **DSID_20915** voor IDFA, die apparaten vertegenwoordigt die het iOS werkende systeem in werking stellen.

**Voorbeelden**

De volgende tabel bevat voorbeelden per gebeurtenistype.

<table id="table_097A58CCD6E64C4DB0652271A4F31AE8"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Type gebeurtenis </th> 
   <th colname="col2" class="entry"> Voorbeeld </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Gebeurtenis </p> </td> 
   <td colname="col2"> 
    <ul id="ul_6EAB4188C6954512A28D1A8328794BCB"> 
     <li id="li_344AAEF1622343489E2AD6E2929CEA98">Nieuw: <code> .../event?d_cid=123%01987...</code> </li> 
     <li id="li_B673C1BA5AD24C46AB8F8232EF89CE89">Vervangen: <code> .../event?d_dpid=123&amp;d_dpuuid=987...</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Binnenkomende synchronisatie (IBS) </p> </td> 
   <td colname="col2"> 
    <ul id="ul_78270745CBC2469B8CA9EDB7032B8F92"> 
     <li id="li_8C4620A04504442185F013F74E6B0647">Nieuw: <code> .../ibs:d_cid=123%01987...</code> </li> 
     <li id="li_2A8F761C76334C1BB097CF1A9D7E8429">Vervangen: <code> .../ibs:d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Audience Manager-UUID (ID) genereren </p> </td> 
   <td colname="col2"> 
    <ul id="ul_EAA764DCFF7244F69ABF67ACEE13E579"> 
     <li id="li_18467A531FAF454A881CBD157BBFD6D2">Nieuw: <code> .../id?d_cid=123%01987...</code> </li> 
     <li id="li_433C33F7BC284362AC7CC3C9DC0BF471">Vervangen: <code> .../id?d_dpid=123&amp;d_dpuuid=987</code> </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

Elke vraag kan veelvoudige `d_cid` en `d_cid_ic` zeer belangrijke waardeparen als dit ook omvatten:

```
...?d_cid=123%01456&d_cid=123%01789&d_cid_ic=543%01333...
```

## Belangrijke overwegingen voor ontwikkelingsteams {#dev-considerations}

<table id="table_5DD068FAE68A42CDB49B6C064706802A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> <p>Item </p> </th> 
   <th colname="col2" class="entry"> <p>Beschrijving </p> </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>URL-codering </p> </td> 
   <td colname="col2"> <p>Uw ontwikkelingsteams <i>moet</i> URL-codering toepassen op de volgende variabelen in het sleutelwaardepaar CID: </p> <p> 
     <ul id="ul_66DCB63C60914057B2BE21F49D9A36CA"> 
      <li id="li_6D82B4DB40BB4BB0B8FAF5841577FAAC"><code> user ID</code> <code> (dpuuid)</code> </li> 
      <li id="li_D2F94B07B0D84B09A5CDFA48518DDD62"><code> integration code</code> </li> 
     </ul> </p> <p> <p>Opmerking: U moet URL coderen de gebruiker - identiteitskaart en integratiecode <i>alvorens </i> hen in een koord aaneenschakelt. Dit komt doordat het ASCII-teken %01 dat de twee variabelen scheidt, niet in de URL-codering moet worden vastgelegd. </p> </p> <p>URL-codering zorgt ervoor dat uw gebruikers-id's en integratiecodes die gereserveerde of onveilige tekens bevatten, zoals, maar niet beperkt tot, + of =, correct naar onze servers worden verzonden. </p> <p>Gebruik de <a href="https://www.w3schools.com/tags/ref_urlencode.asp" format="https" scope="external"> ASCII-coderingstabel</a> ter referentie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Integratiecodes gebruiken voor algemene gedeelde gegevensbronnen </p> </td> 
   <td colname="col2"> <p>U kunt integratiecodes gebruiken voor uw eigen gegevensbronnen en voor globale <a href="../features/datasources-list-and-settings.md#settings-menu-options"> gedeelde gegevensbronnen</a>, die u toegang tot hebt. U kunt bijvoorbeeld integratiecodes gebruiken wanneer u werkt met gegevensbronnen van mobiele id's. Gebruik de volgende integratiecodes, precies zoals hieronder gespecificeerd: </p> <p> 
     <ul id="ul_B306EE96A3BD4CE982E113D5E23826CF"> 
      <li id="li_3340C7AFA9AB4105A2CCF3E476EC7552"> <b>DSID_20914</b> voor GAID, die apparaten vertegenwoordigt die het Android werkende systeem in werking stellen. </li> 
      <li id="li_779D9F08021043FCB233A0ABF5160C76"> <b>DSID_20915</b> voor IDFA, die apparaten vertegenwoordigt die het iOS werkende systeem in werking stellen. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

