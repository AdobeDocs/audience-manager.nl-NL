---
description: Met de API's voor DIL op instantieniveau kunt u programmatisch Audience Manager-objecten maken en ermee werken. De instantie-vlakke methodes verbeteren API functionaliteit die door de klasse-vlakke methodes wordt gevestigd.
keywords: kenmerken maken;kenmerk maken
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: DIL-methoden op instantieniveau
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '1153'
ht-degree: 2%

---

# DIL-methoden op instantieniveau{#instance-level-dil-methods}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
><br>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangeraden [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun strategie voor het verzamelen van gegevens op lange termijn.
><br>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan.

Instantieniveau [!UICONTROL DIL] Met API&#39;s kunt u programmatisch Audience Managers maken en bewerken. De instantie-vlakke methodes verbeteren API functionaliteit die door de klasse-vlakke methodes wordt gevestigd.

## Aan de slag met DIL-methoden op instantieniveau {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Wanneer u met de instantie werkt [!UICONTROL DIL] API&#39;s:

* De toegang vereist een partnernaam en container namespace identiteitskaart (NSID). Neem contact op met de accountmanager van de Audience Manager voor deze informatie.
* Een voorbeeld vervangen *cursief* tekst in de API documentatie met waarde, identiteitskaart, of andere variabele zoals vereist door de methode u met werkt.

<!-- 

c_instance_start.xml

 -->

## signalen {#signals}

Voegt klant en platform-vlakke afbeeldingen aan het vraagkoord van een hangende verzoek toe.

<!-- 

r_dil_signals.xml

 -->

**Functiehandtekening:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* U kunt andere API-aanroepen naar deze methode koppelen.
>* Als de Adobe Experience Cloud JavaScript-bibliotheek op de pagina staat, `submit()` wacht tot de cloud een cookie heeft ingesteld voordat een aanvraag wordt verzonden.

**Gereserveerde aanvraagsleutels**

De volgende aanvraagsleutels zijn gereserveerd en kunnen niet door deze methode worden beschreven:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `obj` | Object | Een object dat de sleutel-waardeparen voor platformafbeeldingen vertegenwoordigt. Parameter accepteert tekenreeksen en arrays als eigenschapswaarden in het object. |
| `prefix` | String | Optioneel. De tekenreekswaarde die aan elke objectsleutel voorafgaat (vervangt de oorspronkelijke sleutel). |
| `return` | DIL.api | Retourneert het API-object van de huidige DIL-instantie. |

**Antwoord**

Hiermee wordt het API-object van het huidige object geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
// Method 1 
var obj = { key1 : 1, key2 : 2 }; 
dataLib.api.signals(obj, 'c_').submit(); 
 
// Method 2 
dataLib.api.signals({c_zdid: 54321}).submit(); 
 
// Method 3 
// Will send 'c_key=a&c_key=2&c_key=3' to Audience Manager 
var obj = { key : ['a', 'b', 'c'] }; 
dataLib.api.signals(obj, 'c_').submit(); 
</code></pre>

## kenmerken {#traits}

Voegt SIDs aan het vraagkoord van een hangend verzoek toe.

<!-- 

r_dil_traits.xml

 -->

**Handtekening functie:** `traits:function (sids){}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `sids` | Array | Trait segment IDs in een serie. |

**Antwoord**

Hiermee wordt het API-object van het huidige object geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Voeg gegevens toe aan logbestanden in de aanvraag die in behandeling is.

<!-- 

r_dil_logs.xml

 -->

**Handtekening functie:** `logs: function {key1:value1, key2:value2}`

**Antwoord**

Hiermee wordt het API-object van het huidige object geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});
</code></pre>

## indienen {#submit}

Hiermee worden alle hangende gegevens naar de Audience Manager verzonden voor de [!UICONTROL DIL] -instantie.

<!-- 

r_dil_submit.xml

 -->

**Functiehandtekening:** `submit: function () {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen. Ook, [!UICONTROL DIL] gecodeerde gegevens worden naar een doelcookie geschreven. Spaties worden bijvoorbeeld gecodeerd als `%20` en puntkomma&#39;s als `%3B`.

**Antwoord**

Hiermee wordt het API-object van het huidige object geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([ 
<i>123,456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}).submit();
</code></pre>

## afterResult {#afterresult}

Een functie die na de standaardbestemmings het publiceren callback uitvoert.

<!-- 

r_dil_after_result.xml

 -->

**Functiehandtekening:** `afterResult: function (fn) {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `fn` | -functie | De functie die u wilt uitvoeren nadat JSON wordt verwerkt door de standaardcallback die bestemmings het publiceren behandelt. |

**Antwoord**

Hiermee wordt een API-object van het huidige object geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.signals({ 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
}).afterResult(function(json){ 
     //Do something with the JSON data returned from the server. 
}).submit();
</code></pre>

## clearData {#cleardata}

Wist alle gegevens in een aanvraag in behandeling.

<!-- 

r_dil_clear_data.xml

 -->

**Functiehandtekening:** `clearData: function () {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Antwoord**

Hiermee wordt het API-object van het huidige object geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs({ 
     file: 'dil.js' 
     message: 'This is the first request' 
}).signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
}); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Voegt aangepaste vraagparameters toe die niet uitdrukkelijk door de server van de gegevensinzameling aan een hangende verzoek worden bepaald.

<!-- 

r_dil_custom_query_params.xml

 -->

**Functiehandtekening:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Gereserveerde aanvraagsleutels**

De volgende aanvraagsleutels zijn gereserveerd en kunnen niet door deze methode worden beschreven:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Antwoord**

Retourneert het API-object van de huidige DIL-instantie.

**Voorbeeldcode**

<pre><code>
var partnerObject = DIL.create({ 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
}); 
partnerObject.api.customQueryParams({ 
     nid: 54231, 
     ntype: 'default' 
}); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Keert de waarde van container NSID voor terug [!UICONTROL DIL] -instantie. Nuttig voor foutopsporing en probleemoplossing.

<!-- 

r_dil_get_container_nsid.xml

 -->

**Functiehandtekening:** `dil.api.getContainerNSID: function () {}`

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Retourneert chronologisch gesorteerde gebeurtenisloggegevens als een array van tekenreeksen. Nuttig voor foutopsporing en probleemoplossing.

<!-- 

r_dil_get_event_log.xml

 -->

**Functiehandtekening:** `dil.api.getEventLog: function () {}`

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message: 'This is the first request' 
});.signals({ 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) { 
     alert(log.join('\n')); 
}else{ 
     alert('No log messages'); 
}
</code></pre>

## getPartner {#getpartner}

Retourneert de partnernaam voor een [!UICONTROL DIL] -instantie. Nuttig voor foutopsporing en probleemoplossing.

<!-- 

r_dil_get_partner.xml

 -->

**Functiehandtekening:** `dil.api.getPartner: function () {}`

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
}); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Retourneert de status van de huidige [!UICONTROL DIL] -instantie. Nuttig voor foutopsporing en probleemoplossing.

<!-- 

r_dil_get_state.xml

 -->

**Functiehandtekening:** `dil.api.getState: function () {}`

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs({ 
     file: 'dil.js', 
     message:'This is the first request' 
});.signals({ 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
});.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = { 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:{ 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: { 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          }, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     }, 
     destinationPublishingInfo: { 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          + containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     } 
} 
*/
</code></pre>

## idSync {#idsync}

Bestaat uit twee functies waarmee gegevenspartners gebruikers-id&#39;s tussen elkaar en Audience Manager kunnen uitwisselen en synchroniseren.

<!-- 

r_dil_idsync.xml

 -->

**Functiehandtekening:**

Werken met [!UICONTROL DIL] versies 2.10 en 3.1 of hoger.

<table id="table_ADC7501511914805A6A6B24B2DFEBA51"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Code </th> 
   <th colname="col2" class="entry"> Gebruikersnamen synchroniseren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.idSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Tussen verschillende gegevenspartners en Audience Manager. Bijvoorbeeld, zou partner x dit gebruiken om een gebruiker - identiteitskaart met partner y te synchroniseren en dan dat naar Audience Manager te verzenden. </p> <p> <p><b>Belangrijk:</b>  Deze methode is afgekeurd. Gebruik de <code> idSyncByURL </code> methode van de instantie Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Wanneer u de gebruikersnaam al kent en deze naar de Audience Manager wilt verzenden. </p> <p> <p><b>Belangrijk:</b>  Deze methode is afgekeurd. Gebruik de <code> idSyncByDataSource </code> methode van de instantie Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync Elements**

`idSync` kan bestaan uit:

<table id="table_5343BE784E694C67B09A0A8878CF8001"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Naam </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>ID gegevensaanbieder toegewezen door Audience Manager. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>De unieke id van de gegevensaanbieder voor de gebruiker. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Getal </td> 
   <td colname="col3"> <p><i>(Optioneel)</i> Hiermee stelt u de vervaltijd van het cookie in. Moet een geheel getal zijn. De standaardwaarde is 20160 minuten (14 dagen). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Doel-URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Macros**

`idSync` Hiermee worden de volgende macro&#39;s geaccepteerd:

* **`%TIMESTAMP%`:** Genereert een tijdstempel (in milliseconden). Wordt gebruikt voor het busten van cache.
* **`%DID%`:** Voegt de Audience Manager-id voor de gebruiker in.
* **`%HTTP_PROTO%`:** Hiermee wordt het paginaprotocol ingesteld ( `http` of `https`).

**Antwoord**

Beide functies retourneren `Successfully queued` indien succesvol. Ze retourneren een foutbericht als dat niet het geval is.

**Voorbeeldcode**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync({ 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync({ 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
});
</code></pre>

## resultaat {#result}

Voegt een callback (die JSON ontvangt) aan het hangende verzoek toe.

<!-- 

r_dil_result.xml

 -->

**Functiehandtekening:** `result: function (callback) {}`

Deze callback vervangt standaardcallback die bestemmings het publiceren behandelt.

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `callback` | -functie | JavaScript-functie die wordt uitgevoerd door de JSONP-callback. |

**Antwoord**

Hiermee wordt het API-object van het huidige object geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json){ 
     //Do something, possibly with the JSON data returned from the server. 
});.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` is een Booleaanse parameter die bepaalt hoe [!UICONTROL DIL] roept [!UICONTROL Data Collection Servers (DCS)] en Akamai.

<!-- 

dil-secure-data-collection.xml

 -->

* Wanneer `secureDataCollection= true` (standaard), [!UICONTROL DIL] maakt altijd veilige, HTTPS vraag.

* Wanneer `secureDataCollection= false`, [!UICONTROL DIL] voert HTTP- of HTTPS-aanroepen uit volgens het beveiligingsprotocol dat door de pagina is ingesteld.

>[!IMPORTANT]
>
>Set `secureDataCollection= false` als u bezoekerAPI.js en [!UICONTROL DIL] op dezelfde pagina. Zie het onderstaande codevoorbeeld.

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     secureDataCollection: false 
});
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` is een Booleaanse parameter true/false die bepaalt hoe de browser bronnen van andere domeinen opvraagt.

<!-- 

dil-use-cors-only.xml

 -->

**Overzicht**

`useCORSOnly` is standaard false. Onwaar betekent browser middelcontroles met CORS of JSONP kan uitvoeren. Maar [!UICONTROL DIL] probeert altijd om middelen met CORS eerst te verzoeken. Het keert aan JSONP op oudere browsers terug die geen CORS steunen. Als u browser moet dwingen om CORS slechts te gebruiken, zoals met plaatsen die hoge veiligheidseisen hebben, plaats `useCORSOnly:true`.

**Codevoorbeeld**

<pre><code class="js">
var dilInstance = DIL.create({ 
     ... 
     useCORSOnly: true 
});
</code></pre>

>[!IMPORTANT]
>
>* We raden u aan `useCORSOnly: true` alleen als u zeker weet dat bezoekers van uw site browsers hebben die deze functie ondersteunen.
>* Wanneer `useCORSOnly: true`, [!UICONTROL DIL] zal geen vraag van identiteitskaart van Internet Explorer versie 9 of ouder maken.
>

## useImageRequest {#useimagerequest}

Hiermee wijzigt u het aanvraagtype in de afbeelding `<img>` van script `<src>`.

<!-- 

r_dil_use_image_request.xml

 -->

**Functiehandtekening:** `useImageRequest: function () {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Antwoord**

Hiermee wordt een API-object van het huidige object geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre><code>
var dataLib = DIL.create({ 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
}); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Naamvereisten voor belangrijke variabelen](../features/traits/trait-key-name-requirements.md)
>* [Voorvoegselvereisten voor belangrijke variabelen](../features/traits/trait-variable-prefixes.md)
>* [Synchronisatiefuncties in de Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [DIL maken](../dil/dil-class-overview/dil-create.md#dil-create)
>* [Adobe Experience Platform Identity Service: UseCORSOnly](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [CORS-ondersteuning in de Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
