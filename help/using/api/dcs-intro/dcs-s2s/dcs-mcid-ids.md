---
description: Gebruikers van id-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id's die nodig zijn om DCS API-aanroepen te maken.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Gebruikersnaam en regio's ophalen via de Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: e17eedfb94f2936c61298c44f3d556bae254b2a7
workflow-type: tm+mt
source-wordcount: '613'
ht-degree: 0%

---

# Gebruikersnaam en regio&#39;s ophalen via de Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Gebruikers van id-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id&#39;s die nodig zijn om [!DNL DCS] API-aanroepen uit te voeren.

## De gebruikersnaam ophalen van de ID Service Cookie {#get-user-ids-from-service-cookie}

De [&#x200B; Dienst van de Identiteit van Adobe Experience Platform &#x200B;](https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL) wijst bezoeker en gebied IDs aan gebruikers toe die naar uw website komen. Deze id&#39;s identificeren gebruikers op alle oplossingen in de [!DNL Experience Cloud] en zijn vereist als u [!DNL DCS] -aanroepen wilt uitvoeren.

* [!UICONTROL user ID] is vereist om gegevens aan een bepaalde bezoeker te identificeren en te koppelen.
* [!UICONTROL region ID] is vereist omdat het is gekoppeld aan een regionale servernaam, die u gegevens naar [!DNL DCS] moet verzenden. In [!DNL DCS] wordt informatie opgeslagen in datacenters die zich geografisch het dichtst bij sitebezoekers bevinden. Zie [&#x200B; DCS Gebied IDs, Locaties, en de Namen van de Gastheer &#x200B;](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

De de dienstklanten van identiteitskaart kunnen deze informatie uit het de dienstkoekje van identiteitskaart halen of door een functie te roepen. In de onderstaande tabel worden de taken of stappen beschreven die u moet uitvoeren om aan de slag te gaan.

De code in *cursief* vertegenwoordigt veranderlijke placeholder.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Taak </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Controleer uw <span class="keyword"> Experience Cloud </span> status </b> </p> </td> 
   <td colname="col2"> <p>U hebt een <span class="keyword"> Experience Cloud </span> rekening nodig om de dienst van identiteitskaart te gebruiken. Als u een <span class="keyword"> Experience Cloud </span> -account hebt, geweldig! </p> <p> Als u geen deel van <span class="keyword"> Experience Cloud </span> uitmaakt, dan onderteken omhoog. We zouden je graag hebben en er is altijd ruimte voor meer. Voor instructies op hoe te opstelling een rekening, zie <a href="https://experienceleague.adobe.com/nl/docs/core-services/interface/services/getting-started" format="https" scope="external"> Toelatend Uw oplossingen voor de kerndiensten </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> 2. Opstelling de <span class="keyword"> dienst van identiteitskaart </span> </b> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> dienst van identiteitskaart </span> bestaat uit de code van JavaScript die op elke pagina wordt gezet u voor gegevensinzameling wilt gebruiken. Zie de dienst van identiteitskaart <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html?lang=nl-NL" format="https" scope="external"> implementatiegidsen </a> voor meer informatie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> 3. Lees de <span class="keyword"> dienst van identiteitskaart </span> koekje </b> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> dienst van identiteitskaart </span> slaat de gebruiker en gebiedsidentiteitskaart in het koekje AMCV op. De volledige naam van de cookie is <code>AMCV_<i>###</i>@AdobeOrg</code> . De <code><i>###</i></code> -elementen zijn plaatsaanduidingen voor uw organisatie-id. Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=nl-NL" format="https" scope="external"> Koekjes en identiteitskaart van Experience Cloud </a> voor details. </p> <p>Parseer het cookie van AMCV voor deze sleutelwaardeparen: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Dit sleutel-waarde paar houdt <span class="keyword"> Experience Cloud </span> gebruiker - identiteitskaart </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Dit zeer belangrijk-waardepaar houdt gebiedsidentiteitskaart (soms genoemd een <span class="term"> plaatshint </span>) die met een regionale servernaam wordt geassocieerd. </li> 
     </ul> </p> <p>U kunt vraag aan <span class="wintitle"> DCS </span> maken zodra u gebruiker en gebied IDs hebt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b> 4. Haal <span class="keyword"> identiteitskaart van Experience Cloud </span> met getMarketingCloudVisitorID </b> terug </p> </td> 
   <td colname="col2"> <p><i> (Facultatief) </i> Deze functie keert <span class="keyword"> Experience Cloud </span> bezoeker identiteitskaart terug Het is ontworpen voor aangepaste oplossingen en specifieke gebruiksgevallen. Zie <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Werken met getMarketingCloudVisitorID </a> hieronder en de <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html?lang=nl-NL" format="https" scope="external"> verwante de dienstdocumentatie van identiteitskaart </a>. </p> <p>U hoeft dit niet te gebruiken als u de gebruikers- en locatie-id's uit het cookie van de ID-service ontvangt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Werken met `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Een andere manier om de bezoekersidentiteitskaart te krijgen is met de `getMarketingCloudVisitorID` functie. Wanneer deze functie wordt aangeroepen, wordt de [!DNL ID service] opgevraagd en wordt een id geretourneerd. `getMarketingCloudVisitorID` accepteert het optionele argument `callback` zoals getoond:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback-gebruik en doel {#callback-usage}

`callback` is optioneel. Deze functie werkt zonder deze, maar retourneert alleen een id wanneer een bezoeker een [!DNL Experience Cloud] cookie in zijn browser heeft. Als het bezoekerscookie ontbreekt of een bezoeker geen id heeft, retourneert de functie een leeg `()` -object. Dit kan zelfs gebeuren nadat de pagina is geladen en de bezoeker een nieuwe id ontvangt. Om dit te voorkomen, dwingt `callback` deze functie om op een bezoekersidentiteitskaart te controleren nadat de pagina laadt. Zonder `callback` retourneert de functie met de bezoeker-id geen id, zelfs niet als deze later naar de browser van de bezoeker is geschreven.

## Volgende stappen {#next-steps}

Zodra u de gebruikers- en regio-id hebt, kunt u beginnen met het verzenden en ontvangen van [!DNL DCS] -gegevens. Zie [&#x200B; het Maken van vraag DCS API &#x200B;](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
