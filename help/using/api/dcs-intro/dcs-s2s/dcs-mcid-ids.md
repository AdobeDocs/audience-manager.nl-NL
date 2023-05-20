---
description: Gebruikers van id-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id's die nodig zijn om DCS API-aanroepen te maken.
seo-description: ID service customers should refer to this section for information on how to read the visitor cookie for the IDs required to make DCS API calls.
seo-title: Get User IDs and Regions Through the Adobe Experience Platform Identity Service
solution: Audience Manager
title: Gebruikers-id’s en -regio’s ontvangen via de Adobe Experience Platform Identity Service
uuid: 80de6cf2-5d9e-4ef8-a0f2-d53b5d574c89
feature: DCS
exl-id: 0b855237-ac14-4c0e-b831-221b9218840f
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '643'
ht-degree: 4%

---

# Gebruikers-id’s en -regio’s ontvangen via de Adobe Experience Platform Identity Service {#get-user-ids-and-regions-through-the-experience-cloud-id-service}

Klanten van ID-services moeten naar deze sectie verwijzen voor informatie over het lezen van het bezoekerscookie voor de id&#39;s die nodig zijn om [!DNL DCS] API-aanroepen.

## De gebruikersnaam ophalen van de ID Service Cookie {#get-user-ids-from-service-cookie}

De [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html) Hiermee worden gebruikers die naar uw website komen, toegewezen aan gebruikers van de gebruikers en regio-id&#39;s. Deze id&#39;s identificeren gebruikers op alle oplossingen in de [!DNL Experience Cloud] en zijn vereist als u wilt maken [!DNL DCS] oproepen.

* De [!UICONTROL user ID] is vereist om gegevens te identificeren en aan een bepaalde bezoeker te koppelen.
* De [!UICONTROL region ID] is vereist omdat deze gekoppeld is aan een regionale servernaam die u gegevens naar de [!DNL DCS]. De [!DNL DCS] slaat informatie in gegevenscentra op die geografisch dichtst bij bezoekers van de plaats zijn. Zie [Id&#39;s, locaties en hostnamen van DCS-regio&#39;s](../../../api/dcs-intro/dcs-api-reference/dcs-regions.md).

De de dienstklanten van identiteitskaart kunnen deze informatie uit het de dienstkoekje van identiteitskaart halen of door een functie te roepen. In de onderstaande tabel worden de taken of stappen beschreven die u moet uitvoeren om aan de slag te gaan.

Code in *cursief* vertegenwoordigt een variabele placeholder.

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
   <td colname="col2"> <p>U hebt een <span class="keyword"> Experience Cloud</span> account voor gebruik van de ID-service. Als u een <span class="keyword"> Experience Cloud</span> account, geweldig! </p> <p> Als u geen deel uitmaakt van de <span class="keyword"> Experience Cloud</span>en meld u vervolgens aan. We zouden je graag hebben en er is altijd ruimte voor meer. Voor instructies over het instellen van een account raadpleegt u <a href="https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services.html" format="https" scope="external"> Uw oplossingen inschakelen voor kernservices</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>2. Stel de <span class="keyword"> ID-service</span></b> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> ID-service</span> bestaat uit JavaScript-code die wordt geplaatst op elke pagina die u wilt gebruiken voor gegevensverzameling. Zie de id-service <a href="https://experienceleague.adobe.com/docs/id-service/using/implementation/implementation-guides.html" format="https" scope="external"> implementatiehulplijnen</a> voor meer informatie . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>3. Lees de <span class="keyword"> ID-service</span> koekje</b> </p> </td> 
   <td colname="col2"> <p>De <span class="keyword"> ID-service</span> slaat de gebruikers- en regio-id op in het AMCV-cookie. De volledige naam van de cookie is <code>AMCV_<i>###</i>@AdobeOrg</code>. De <code><i>###</i></code> elementen zijn plaatsaanduidingen voor uw organisatie-id. Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies en de Experience Cloud-id</a> voor meer informatie. </p> <p>Parseer het cookie van AMCV voor deze sleutelwaardeparen: </p> <p> 
     <ul id="ul_502ECFCDDD084D448B5EDC4E5C0909C1"> 
      <li id="li_662FFA36AC854E699D50A183B161D654"> <code>mid=<i>user ID</i></code>: Dit sleutelwaardepaar houdt het <span class="keyword"> Experience Cloud</span> gebruikersnaam. </li> 
      <li id="li_65422233187B4217B50DC52DBD58F404"> <code>aamlh=<i>region ID</i></code>: Dit sleutelwaardepaar houdt gebiedsidentiteitskaart (soms genoemd <span class="term"> locatiehint</span>) die is gekoppeld aan een regionale servernaam. </li> 
     </ul> </p> <p>U kunt oproepen aan <span class="wintitle"> DCS</span> als u de gebruikers- en regio-id's hebt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>4. De <span class="keyword"> Experience Cloud-id</span> met getMarketingCloudVisitorID</b> </p> </td> 
   <td colname="col2"> <p><i>(Optioneel)</i> Deze functie retourneert de <span class="keyword"> Experience Cloud</span> bezoeker-id. Het is ontworpen voor aangepaste oplossingen en specifieke gebruiksgevallen. Zie <a href="../../../api/dcs-intro/dcs-s2s/dcs-mcid-ids.md#working-with-getmarketingcloudvisitorid"> Werken met getMarketingCloudVisitorID</a> en de <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/getmcvid.html" format="https" scope="external"> gerelateerde documentatie over id-services</a>. </p> <p>U hoeft dit niet te gebruiken als u de gebruikers- en locatie-id's uit het cookie van de ID-service ontvangt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Werken met `getMarketingCloudVisitorID` {#working-with-getmarketingcloudvisitorid}

Een andere manier om de bezoekersidentiteitskaart te krijgen is met `getMarketingCloudVisitorID` functie. Wanneer deze functie wordt aangeroepen, wordt de [!DNL ID service] en retourneert een id. `getMarketingCloudVisitorID` accepteert de optionele `callback` argument zoals getoond:

`var analyticsID = visitor.getAnalyticsVisitorID(callback)`

### Callback-gebruik en doel {#callback-usage}

`callback` is optioneel. Deze functie werkt zonder deze, maar retourneert alleen een id wanneer een bezoeker een [!DNL Experience Cloud] cookie in hun browser. Als het bezoekerscookie ontbreekt of als een bezoeker geen id heeft, retourneert de functie een leeg cookie `()` object. Dit kan zelfs gebeuren nadat de pagina is geladen en de bezoeker een nieuwe id ontvangt. Om dit te voorkomen, `callback` forceert deze functie om op een bezoekersidentiteitskaart te controleren nadat de pagina laadt. Zonder `callback`, retourneert de functie met de bezoeker-id geen id, zelfs niet als deze later naar de browser van de bezoeker is geschreven.

## Volgende stappen {#next-steps}

Zodra u de gebruikers- en regio-id hebt, kunt u beginnen met verzenden en ontvangen [!DNL DCS] gegevens. Zie [DCS API-aanroepen maken](../../../api/dcs-intro/dcs-s2s/dcs-s2s-calls.md).
