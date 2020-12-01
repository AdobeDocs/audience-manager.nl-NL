---
description: De regionale DCS servergastheernaam wordt vereist om vraag aan DCS te maken. Dit komt doordat in de DCS informatie wordt opgeslagen in datacenters die geografisch dicht bij sitebezoekers liggen. Uw vragen zullen werken als u hen naar verkeerde DCS verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een DCS-aanvraag wilt maken, moet u de regio-id afstemmen op de corresponderende regionale hostnaam en de query met de juiste hostnaam configureren.
seo-description: De regionale DCS servergastheernaam wordt vereist om vraag aan DCS te maken. Dit komt doordat in de DCS informatie wordt opgeslagen in datacenters die geografisch dicht bij sitebezoekers liggen. Uw vragen zullen werken als u hen naar verkeerde DCS verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een DCS-aanvraag wilt maken, moet u de regio-id afstemmen op de corresponderende regionale hostnaam en de query met de juiste hostnaam configureren.
seo-title: Id’s, locaties en hostnamen van DCS-regio’s
solution: Audience Manager
title: Id’s, locaties en hostnamen van DCS-regio’s
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '311'
ht-degree: 6%

---


# Id’s, locaties en hostnamen van DCS-regio’s {#dcs-region-ids-locations-and-host-names}

De regionale [!DNL DCS] naam van de servergastheer wordt vereist om vraag aan [!DNL DCS] te maken. Dit komt omdat de [!DNL DCS] informatie opslaat in gegevenscentra die geografisch dicht bij bezoekers van de site zijn. Uw vragen zullen werken als u hen naar verkeerd [!DNL DCS] verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een [!DNL DCS]-verzoek wilt indienen, past u de regio-id aan de corresponderende regionale hostnaam aan en vormt u de query met de juiste hostnaam.

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

U kunt [!DNL API] methodes ook gebruiken om een lijst van de beschikbare [!DNL DCS] gebieden te krijgen. Zie [DCS Region API Methods](../../../api/rest-api-main/aam-api-dcs-regions.md).