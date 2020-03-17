---
description: De regionale DCS servergastheernaam wordt vereist om vraag aan DCS te maken. Dit komt doordat in de DCS informatie wordt opgeslagen in datacenters die geografisch dicht bij sitebezoekers liggen. Uw vragen zullen werken als u hen naar verkeerde DCS verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een DCS-aanvraag wilt maken, moet u de regio-id afstemmen op de corresponderende regionale hostnaam en de query met de juiste hostnaam configureren.
seo-description: De regionale DCS servergastheernaam wordt vereist om vraag aan DCS te maken. Dit komt doordat in de DCS informatie wordt opgeslagen in datacenters die geografisch dicht bij sitebezoekers liggen. Uw vragen zullen werken als u hen naar verkeerde DCS verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een DCS-aanvraag wilt maken, moet u de regio-id afstemmen op de corresponderende regionale hostnaam en de query met de juiste hostnaam configureren.
seo-title: Id's, locaties en hostnamen van DCS-regio's
solution: Audience Manager
title: Id's, locaties en hostnamen van DCS-regio's
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
translation-type: tm+mt
source-git-commit: 51a326d0ac02175e0e1452e0a00b4a3a415d88ff

---


# Id&#39;s, locaties en hostnamen van DCS-regio&#39;s {#dcs-region-ids-locations-and-host-names}

De regionale hostnaam van de [!UICONTROL DCS] server is vereist om oproepen te doen naar de [!UICONTROL DCS]. Dit komt omdat de [!UICONTROL DCS] informatie in gegevenscentra wordt opgeslagen die geografisch dicht bij plaatsbezoekers zijn. Uw vragen zullen werken als u hen naar het verkeerde [!UICONTROL DCS]verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een [!UICONTROL DCS] aanvraag wilt indienen, dient u de regio-id aan te passen aan de corresponderende regionale hostnaam en de query met de juiste hostnaam te vormen.

<table id="table_643212E4F9C64DFF9443904B01D89CB3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> DCS-regio-id (dcs_region) </th> 
   <th colname="col2" class="entry"> Regio (en locatie) </th> 
   <th colname="col3" class="entry"> Hostnaam </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>ID 3 </p> </td> 
   <td colname="col2"> <p>Zuidoost-Azië (Singapore) </p> </td> 
   <td colname="col3"> <p> <code> apse.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 4 </p> </td> 
   <td colname="col2"> <p>Zuid-Amerika (São Paulo, Brazilië) </p> </td> 
   <td colname="col3"> <p> <code> sae.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 6 </p> </td> 
   <td colname="col2"> <p>Europa (Dublin, Ierland) </p> </td> 
   <td colname="col3"> <p> <code> irl1.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 7 </p> </td> 
   <td colname="col2"> <p>US East (Virginia, VS) </p> </td> 
   <td colname="col3"> <p> <code> use.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 8 </p> </td> 
   <td colname="col2"> <p>Zuidelijke Stille Oceaan / Oceanië (Sydney, Australië) </p> </td> 
   <td colname="col3"> <p> <code> apse2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 9 </p> </td> 
   <td colname="col2"> <p>US West (Oregon, VS) </p> </td> 
   <td colname="col3"> <p> <code> usw2.demdex.net</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>ID 11 </p> </td> 
   <td colname="col2"> <p>Azië (Tokio, Japan) </p> </td> 
   <td colname="col3"> <p> <code> tyo3.demdex.net</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p>ID 12 </p> </td> 
   <td colname="col2"> <p>India </p> </td> 
   <td colname="col3"> <p> <code> ind1.demdex.net</code> </p> </td> 
  </tr> 
 </tbody> 
</table>

U kunt ook [!DNL API] methoden gebruiken om een lijst met beschikbare [!UICONTROL DCS] gebieden op te halen. Zie API-methoden voor [DCS-regio](../../../api/rest-api-main/aam-api-dcs-regions.md).