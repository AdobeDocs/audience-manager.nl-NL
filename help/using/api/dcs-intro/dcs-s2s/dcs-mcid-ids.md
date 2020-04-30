---
description: Gebruikers van id-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id's die nodig zijn om DCS API-aanroepen te maken.
seo-description: Gebruikers van id-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id's die nodig zijn om DCS API-aanroepen te maken.
seo-title: Gebruik de identiteitsservice van het Adobe Experience Platform voor gebruikers-id's en -regio's
solution: Audience Manager
title: Gebruik de identiteitsservice van het Adobe Experience Platform voor gebruikers-id's en -regio's
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Gebruik de identiteitsservice van het Adobe Experience Platform voor gebruikers-id&#39;s en -regio&#39;s {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

De de dienstklanten van identiteitskaart zouden naar deze sectie voor informatie over moeten verwijzen hoe te om het bezoekerskoekje voor IDs te lezen die wordt vereist om [!UICONTROL DCS] API vraag te maken.

## De gebruikersnaam ophalen van de ID Service Cookie {#get-user-ids-from-service-cookie}

De identiteitsservice [van het](https://docs.adobe.com/content/help/en/id-service/using/home.html) Adobe Experience Platform wijst gebruikers- en regio-id&#39;s toe aan gebruikers die naar uw website komen. Deze IDs identificeert gebruikers over alle oplossingen in het [!DNL Experience Cloud] en zij worden vereist als u [!UICONTROL DCS] vraag wilt maken.

* De gegevens [!UICONTROL user ID] zijn vereist om gegevens te identificeren en aan een bepaalde bezoeker te koppelen.
* Dit [!UICONTROL region ID] [!UICONTROL DCS]is vereist omdat het is gekoppeld aan een regionale servernaam, die u gegevens naar de server moet verzenden. De [!UICONTROL DCS] opslaginformatie in gegevenscentra die geografisch het dichtst bij plaatsbezoekers zijn. Zie [DCS-regio-id&#39;s, -locaties en -hostnamen](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

De de dienstklanten van identiteitskaart kunnen deze informatie uit het de dienstkoekje van identiteitskaart halen of door een functie te roepen. In de onderstaande tabel worden de taken of stappen beschreven die u moet uitvoeren om aan de slag te gaan.

De code in *cursief* staat voor een variabele plaatsaanduiding.

<table id="table_660EBE1C24DD4FBE9DCE5191836C9135"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Taak </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>1. Controleer de status van uw <span class="keyword"> Experience Cloud</span></b> </p> </td> 
   <td colname="col2"> <p>U hebt een <span class="keyword"> Experience Cloud</span> -account nodig om de id-service te kunnen gebruiken. Als u een <span class="keyword"> Experience Cloud</span> -account hebt, geweldig! </p> <p> Als u geen deel uitmaakt van de <span class="keyword"> Experience Cloud</span>, meldt u zich aan. We zouden je graag hebben en er is altijd ruimte voor meer. Zie <a href="https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Uw oplossingen inschakelen voor kernservices</a>voor instructies over het instellen van een account. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. De <span class="keyword"> id-service instellen</span></b> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> id-service</span> bestaat uit JavaScript-code die wordt geplaatst op elke pagina die u voor gegevensverzameling wilt gebruiken. Raadpleeg de handleidingen bij <a href="https://docs.adobe.com/content/help/en/id-service/using/implementation/implementation-guides.html" format="https" scope="external"></a> de implementatie van de id-service voor meer informatie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Het cookie van de <span class="keyword"> id-service</span> lezen</b> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> -id-service</span> slaat de gebruikers- en regio-id op in het AMCV-cookie. De volledige naam van de cookie is <code>AMCV_<i>###</i>@AdobeOrg</code>. De <code><i>###</i></code> elementen zijn plaatsaanduidingen voor uw organisatie-id. Raadpleeg <a href="https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies en de Experience Cloud-id</a> voor meer informatie. </p> <p>Parseer het cookie van AMCV voor deze sleutelwaardeparen: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Dit sleutelwaardepaar bevat de gebruikers-id van de <span class="keyword"> Experience Cloud</span> . </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Dit zeer belangrijk-waardepaar houdt gebiedsidentiteitskaart (soms genoemd een <span class="term"> plaatswenk</span>) die met een regionale servernaam wordt geassocieerd. </li> 
     </ul> </p> <p>U kunt vraag aan <span class="wintitle"> DCS</span> maken zodra u de gebruiker en gebiedsidentiteitskaart hebt </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. De <span class="keyword"> Experience Cloud-id</span> ophalen met getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Optioneel)</i> Deze functie retourneert de <span class="keyword"> Experience Cloud</span> -bezoeker-id. Het is ontworpen voor aangepaste oplossingen en specifieke gebruiksgevallen. Zie <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Werken met getMarketingCloudVisitorID</a> hieronder en de <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> gerelateerde documentatie</a>van de id-service. </p> <p>U hoeft dit niet te gebruiken als u de gebruikers- en locatie-id's uit het cookie van de ID-service ontvangt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Werken met `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Een andere manier om bezoekersidentiteitskaart te krijgen is met de `getMarketingCloudVisitorID` functie. Als deze functie wordt aangeroepen, wordt de id opgehaald [!DNL ID service] en geretourneerd. `getMarketingCloudVisitorID` Accepteert het optionele `callback` argument zoals getoond:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback-gebruik en doel {#callback-usage}

`callback` is optioneel. Deze functie werkt zonder deze, maar retourneert alleen een id wanneer een bezoeker een [!DNL Experience Cloud] cookie in zijn browser heeft. Als het bezoekerscookie ontbreekt of een bezoeker geen id heeft, retourneert de functie een leeg `()` object. Dit kan zelfs gebeuren nadat de pagina is geladen en de bezoeker een nieuwe id ontvangt. Om dit te voorkomen, `callback` dwingt u deze functie om te controleren op een bezoeker-id nadat de pagina is geladen. Zonder `callback`, zal de functie van bezoekersidentiteitskaart geen identiteitskaart terugkeren zelfs als het aan browser van de bezoeker later wordt geschreven.

## Volgende stappen {#next-steps}

Zodra u de gebruikers- en regio-id hebt, kunt u beginnen met het verzenden en ontvangen van [!UICONTROL DCS] gegevens. Zie [DCS API-aanroepen](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md)maken.