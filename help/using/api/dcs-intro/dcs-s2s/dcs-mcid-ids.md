---
description: Gebruikers van id-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id's die nodig zijn om DCS API-aanroepen te maken.
seo-description: Gebruikers van id-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id's die nodig zijn om DCS API-aanroepen te maken.
seo-title: Gebruikers-id’s en -regio’s ontvangen via de Adobe Experience Platform Identity Service
solution: Audience Manager
title: Gebruikers-id’s en -regio’s ontvangen via de Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '682'
ht-degree: 6%

---

# Gebruikers-id’s en -regio’s ontvangen via de Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Klanten van id-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id&#39;s die nodig zijn om [!DNL DCS] API-aanroepen uit te voeren.

## De gebruikersnaam ophalen van de ID Service Cookie {#get-user-ids-from-service-cookie}

Met de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) worden gebruikers die naar uw website komen, een bezoeker- en regio-id toegewezen. Deze IDs identificeert gebruikers over alle oplossingen in [!DNL Experience Cloud] en zij worden vereist als u [!DNL DCS] vraag wilt maken.

* [!UICONTROL user ID] is vereist om gegevens aan een bepaalde bezoeker te identificeren en te associëren.
* De [!UICONTROL region ID] is vereist omdat deze is gekoppeld aan een regionale servernaam, die u gegevens naar [!DNL DCS] moet verzenden. [!DNL DCS] slaat informatie in gegevenscentra op die geografisch dichtst bij bezoekers van de plaats zijn. Zie [DCS-regio-id&#39;s, -locaties en hostnamen](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

De de dienstklanten van identiteitskaart kunnen deze informatie uit het de dienstkoekje van identiteitskaart halen of door een functie te roepen. In de onderstaande tabel worden de taken of stappen beschreven die u moet uitvoeren om aan de slag te gaan.

De code in *italics* vertegenwoordigt veranderlijke placeholder.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Taak </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Controleer uw <span class="keyword"> Experience Cloud</span> status</b> </p> </td> 
   <td colname="col2"> <p>U hebt een <span class="keyword"> Experience Cloud</span> rekening nodig om de dienst van identiteitskaart te gebruiken. Als u een <span class="keyword"> Experience Cloud</span> account hebt, geweldig! </p> <p> Als u geen deel van <span class="keyword"> Experience Cloud</span> uitmaakt, dan onderteken omhoog. We zouden je graag hebben en er is altijd ruimte voor meer. Zie <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Uw oplossingen inschakelen voor kernservices</a> voor instructies voor het instellen van een account. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. De <span class="keyword"> ID-service</span></b> instellen </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> ID-service</span> bestaat uit JavaScript-code die wordt geplaatst op elke pagina die u voor gegevensverzameling wilt gebruiken. Raadpleeg de implementatiehandleidingen</a> voor de id-service voor meer informatie.<a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> </a></p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lees de <span class="keyword"> ID service</span> cookie</b> </p> </td> 
   <td colname="col2"> <p>In de <span class="keyword"> ID-service</span> worden de gebruikers- en regio-id opgeslagen in het AMCV-cookie. De volledige naam van het cookie is <code>AMCV_<i>###</i>@AdobeOrg</code>. De <code><i>###</i></code> elementen zijn placeholders voor uw organisatie ID. Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies en Experience Cloud ID</a> voor meer informatie. </p> <p>Parseer het cookie van AMCV voor deze sleutelwaardeparen: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Dit sleutelwaardepaar bevat de  <span class="keyword"> Experience </span> Clouduser-id. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Dit zeer belangrijk-waardepaar houdt gebiedsidentiteitskaart (soms genoemd een  <span class="term"> plaatswenk</span>) die met een regionale servernaam wordt geassocieerd. </li> 
     </ul> </p> <p>U kunt vraag aan <span class="wintitle"> DCS</span> maken zodra u gebruiker en gebied IDs hebt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. De <span class="keyword"> Experience Cloud-id</span> ophalen met getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Optioneel)</i> Deze functie retourneert de  <span class="keyword"> Experience </span> Cloudbezoeker-id. Het is ontworpen voor aangepaste oplossingen en specifieke gebruiksgevallen. Zie <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Werken met getMarketingCloudVisitorID</a> hieronder en de <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> gerelateerde ID-servicedocumentatie</a>. </p> <p>U hoeft dit niet te gebruiken als u de gebruikers- en locatie-id's uit het cookie van de ID-service ontvangt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Werken met `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Een andere manier om bezoekersidentiteitskaart te krijgen is met de functie `getMarketingCloudVisitorID`. Wanneer opgeroepen, vraagt deze functie [!DNL ID service] en keert een identiteitskaart terug `getMarketingCloudVisitorID` Accepteert het optionele  `callback` argument zoals getoond:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback-gebruik en doel {#callback-usage}

`callback` is optioneel. Deze functie werkt zonder deze, maar retourneert alleen een id wanneer een bezoeker een cookie [!DNL Experience Cloud] in zijn browser heeft. Als het bezoekerscookie ontbreekt of een bezoeker geen id heeft, retourneert de functie een leeg `()`-object. Dit kan zelfs gebeuren nadat de pagina is geladen en de bezoeker een nieuwe id ontvangt. Om dit te voorkomen, dwingt `callback` deze functie om op bezoekersidentiteitskaart te controleren nadat de pagina laadt. Zonder `callback` retourneert de functie van de bezoeker-id geen id, zelfs niet als deze later naar de browser van de bezoeker is geschreven.

## Volgende stappen {#next-steps}

Zodra u de gebruiker en gebiedsidentiteitskaart hebt, kunt u beginnen te verzenden en [!DNL DCS] gegevens te ontvangen. Zie [DCS API-aanroepen maken](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
