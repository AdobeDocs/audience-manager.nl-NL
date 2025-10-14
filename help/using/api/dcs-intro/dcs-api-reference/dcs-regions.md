---
description: De regionale DCS servergastheernaam wordt vereist om vraag aan DCS te maken. Dit komt doordat in de DCS informatie wordt opgeslagen in datacenters die geografisch dicht bij sitebezoekers liggen. Uw vragen zullen werken als u hen naar verkeerde DCS verzendt, maar deze vraag is inefficiënt en kan de reactie vertragen. Als u een DCS-aanvraag wilt maken, moet u de regio-id afstemmen op de corresponderende regionale hostnaam en de query met de juiste hostnaam configureren.
seo-description: The regional DCS server host name is required to make calls to the DCS. This is because the DCS stores information in data centers that are geographically close to site visitors. Your queries will work if you send them to the wrong DCS, but these calls are inefficient and can delay the response. To make a DCS request, match the region ID to its corresponding regional host name and form your query with the proper host name.
seo-title: DCS Region IDs, Locations, and Host Names
solution: Audience Manager
title: Id's, locaties en hostnamen van DCS-regio's
uuid: ad150ffe-4583-472b-ac8b-fb900a7966e4
feature: DCS
exl-id: 9b12946c-89f1-4f6f-adb9-961e15a0b816
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '234'
ht-degree: 0%

---

# Id&#39;s, locaties en hostnamen van DCS-regio&#39;s {#dcs-region-ids-locations-and-host-names}

De regionale hostnaam van de [!DNL DCS] -server is vereist voor het aanroepen van de [!DNL DCS] . Dit komt omdat de [!DNL DCS] informatie opslaat in gegevenscentra die geografisch dicht bij bezoekers van de site staan. Uw query&#39;s werken als u ze naar de verkeerde [!DNL DCS] stuurt, maar deze aanroepen zijn inefficiënt en kunnen de reactie vertragen. Als u een [!DNL DCS] -aanvraag wilt indienen, dient u de regio-id aan te passen aan de corresponderende regionale hostnaam en de query met de juiste hostnaam te vormen.

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

U kunt ook [!DNL API] -methoden gebruiken om een lijst met de beschikbare [!DNL DCS] -gebieden op te halen. Zie [&#x200B; DCS Gebied API Methoden &#x200B;](../../../api/rest-api-main/aam-api-dcs-regions.md).
