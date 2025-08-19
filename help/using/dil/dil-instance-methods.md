---
description: Met DIL API's op instantieniveau kunt u programmatisch Audience Manager-objecten maken en ermee werken. De instantie-vlakke methodes verbeteren API functionaliteit die door de klasse-vlakke methodes wordt gevestigd.
keywords: kenmerken maken;kenmerk maken
seo-description: The instance-level DIL APIs let you programmatically create and work with Audience Manager objects. The instance-level methods enhance API functionality established by the class-level methods.
seo-title: Instance-level DIL Methods
solution: Audience Manager
title: DIL-methoden op instantieniveau
uuid: aa5147bb-51d5-41d4-a78a-e550f7492056
feature: DIL Implementation
exl-id: 0342439d-708e-461c-b155-a3ee423f5437
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '1126'
ht-degree: 1%

---

# DIL-methoden op instantieniveau{#instance-level-dil-methods}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan moeten gebruiken.

Met de API&#39;s op instantieniveau [!UICONTROL DIL] kunt u programmatisch Audience Manager-objecten maken en ermee werken. De instantie-vlakke methodes verbeteren API functionaliteit die door de klasse-vlakke methodes wordt gevestigd.

## Aan de slag met DIL-methoden op instantieniveau {#get-started-dil-methods}

<!-- 

c_api_overview.xml

 -->

Wanneer u werkt met de API&#39;s op instantieniveau [!UICONTROL DIL] :

* De toegang vereist een partnernaam en container namespace identiteitskaart (NSID). Neem contact op met uw Audience Manager-accountmanager voor deze informatie.
* Vervang om het even welke steekproef *cursief* tekst in de API documentatie met waarde, identiteitskaart, of andere variabele zoals die door de methode wordt vereist u met werkt.

<!-- 

c_instance_start.xml

 -->

## signalen {#signals}

Voegt klant en platform-vlakke afbeeldingen aan het vraagkoord van een hangende verzoek toe.

<!-- 

r_dil_signals.xml

 -->

**de Handtekening van de Functie:** `signals: function ({key1:value1, key2:value2},prefix){}`

>[!NOTE]
>
>* U kunt andere API-aanroepen naar deze methode koppelen.
>* Als de Adobe Experience Cloud JavaScript-bibliotheek op de pagina staat, wacht `submit()` tot de cloud een cookie heeft ingesteld voordat een aanvraag wordt verzonden.

**Gereserveerde Sleutels van het Verzoek**

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

**Reactie**

Retourneert het API-object van de huidige [!UICONTROL DIL] -instantie.

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
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

**handtekening van de Functie:** `traits:function (sids){}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `sids` | Array | Trait segment IDs in een serie. |

**Reactie**

Retourneert het API-object van de huidige [!UICONTROL DIL] -instantie.

**Code van de Steekproef**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner name</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.traits(<i>[123, 456, 789]</i>); 
</code></pre>

## logs {#logs}

Voeg gegevens toe aan logbestanden in de aanvraag die in behandeling is.

<!-- 

r_dil_logs.xml

 -->

**handtekening van de Functie:** `logs: function {key1:value1, key2:value2}`

**Reactie**

Retourneert het API-object van de huidige [!UICONTROL DIL] -instantie.

**Code van de Steekproef**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);
</code></pre>

## indienen {#submit}

Hiermee worden alle gegevens die in behandeling zijn naar Audience Manager verzonden voor de instantie [!UICONTROL DIL] .

<!-- 

r_dil_submit.xml

 -->

**de Handtekening van de Functie:** `submit: function () {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen. Bovendien schrijft [!UICONTROL DIL] gecodeerde gegevens naar een doelcookie. Spaties worden bijvoorbeeld gecodeerd als `%20` en puntkomma&#39;s als `%3B` .

**Reactie**

Retourneert het API-object van de huidige [!UICONTROL DIL] -instantie.

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits(&lbrack; 
<i>123,456, 789</i>&rbrack;).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;).submit();
</code></pre>

## afterResult {#afterresult}

Een functie die na de standaardbestemmings het publiceren callback uitvoert.

<!-- 

r_dil_after_result.xml

 -->

**de Handtekening van de Functie:** `afterResult: function (fn) {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `fn` | Functie | De functie die u wilt uitvoeren nadat JSON wordt verwerkt door de standaardcallback die bestemmings het publiceren behandelt. |

**Reactie**

Retourneert een API-object van de huidige [!UICONTROL DIL] -instantie.

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.signals(&lbrace; 
     c_zdid: <i>54321</i> 
     d_dma: '<i>default</i>' 
&rbrace;).afterResult(function(json)&lbrace; 
     //Do something with the JSON data returned from the server. 
&rbrace;).submit();
</code></pre>

## clearData {#cleardata}

Wist alle gegevens in een aanvraag in behandeling.

<!-- 

r_dil_clear_data.xml

 -->

**de Handtekening van de Functie:** `clearData: function () {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Reactie**

Retourneert het API-object van de huidige [!UICONTROL DIL] -instantie.

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123,456, 789</i>]).logs(&lbrace; 
     file: 'dil.js' 
     message: 'This is the first request' 
&rbrace;).signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;); 
 
//Reset the pending data 
dataLib.clearData();
</code></pre>

## customQueryParams {#customqueryparams}

Voegt aangepaste vraagparameters toe die niet uitdrukkelijk door de server van de gegevensinzameling aan een hangende verzoek worden bepaald.

<!-- 

r_dil_custom_query_params.xml

 -->

**de Handtekening van de Functie:** `customQueryParams: function (obj) {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Gereserveerde Sleutels van het Verzoek**

De volgende aanvraagsleutels zijn gereserveerd en kunnen niet door deze methode worden beschreven:

* `sids`
* `pdata`
* `logdata`
* `callback`
* `postCallbackFn`
* `useImageRequest`

**Reactie**

Retourneert het API-object van de huidige DIL-instantie.

**Code van de Steekproef**

<pre><code>
var partnerObject = DIL.create(&lbrace; 
     partner: '<i>partner</i>', 
     containerNSID: <i>NSID</i> 
&rbrace;); 
partnerObject.api.customQueryParams(&lbrace; 
     nid: 54231, 
     ntype: 'default' 
&rbrace;); 
</code></pre>

## getContainerNSID {#getcontainernsid}

Retourneert de waarde van de container NSID voor de instantie [!UICONTROL DIL] . Nuttig voor foutopsporing en probleemoplossing.

<!-- 

r_dil_get_container_nsid.xml

 -->

**de Handtekening van de Functie:** `dil.api.getContainerNSID: function () {}`

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the container NSID 
var nsid = dataLib.api.getContainerNSID();
</code></pre>

## getEventLog {#geteventlog}

Retourneert chronologisch gesorteerde gebeurtenisloggegevens als een array van tekenreeksen. Nuttig voor foutopsporing en probleemoplossing.

<!-- 

r_dil_get_event_log.xml

 -->

**de Handtekening van de Functie:** `dil.api.getEventLog: function () {}`

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message: 'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c_zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
//Check log for messages 
var log = dataLib.api.getEventLog(); 
if (log && log.length) &lbrace; 
     alert(log.join('\n')); 
&rbrace;else&lbrace; 
     alert('No log messages'); 
&rbrace;
</code></pre>

## getPartner {#getpartner}

Retourneert de partnernaam voor een instantie [!UICONTROL DIL] . Nuttig voor foutopsporing en probleemoplossing.

<!-- 

r_dil_get_partner.xml

 -->

**de Handtekening van de Functie:** `dil.api.getPartner: function () {}`

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>' 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
//Verify the partner name 
var partner = dataLib.api.getPartner();
</code></pre>

## getState {#getstate}

Retourneert de status van de huidige [!UICONTROL DIL] -instantie. Nuttig voor foutopsporing en probleemoplossing.

<!-- 

r_dil_get_state.xml

 -->

**de Handtekening van de Functie:** `dil.api.getState: function () {}`

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).logs(&lbrace; 
     file: 'dil.js', 
     message:'This is the first request' 
&rbrace;);.signals(&lbrace; 
     c.zdid: <i>1111</i> 
     d_dma: '<i>default</i>' 
&rbrace;);.submit(); 
 
var state = dataLib.api.getState(); 
 
/*Object outline of state 
state = &lbrace; 
     pendingRequest: {<i>pending data for call to server</i>}, 
     otherRequestInfo:&lbrace; 
          firingQueue: [], 
          fired: [], 
          firing: false, 
          errored: [], 
          reservedKeys: &lbrace; 
               sids: true, 
               pdata: true, 
               logdata: true, 
               callback: true, 
               postCallbackFn: true, 
               useImageRequest: true, 
          &rbrace;, 
          firstRequestHasFired: false, 
          num_of_jsonp_responses: 0, 
          num_of_jsonp_errors: 0, 
          num_of_img_responses: 0, 
          num_of_img_errors: 0 
     &rbrace;, 
     destinationPublishingInfo: &lbrace; 
          THROTTLE_START: 3000, 
          throttleTimerSet: false, 
          id: ''destination_publishing_iframe_' + partner + '_' + containerNSID, 
          url: (constants.isHTTPS ? 'https://' : 'https://fast.') + partner + '.demdex.net/dest3.html?d_nsid=' 
          &#x200B;+ containerNSID + '#' + encodeURIComponent(document.location.href), 
               iframe: null, 
               iframeHasLoaded: false, 
               sendingMessages: false, 
               messages: [], 
               messageSendingInterval: constants.POST_MESSAGE_ENABLED ? 15: 100, 
               //Recommend 100ms for IE 6 & 7, 15ms for other browsers 
               jsonProcessed: [] 
     &rbrace; 
&rbrace; 
*/
</code></pre>

## idSync {#idsync}

Bestaat uit twee functies waarmee gegevenspartners gebruikers-id&#39;s onderling en in Audience Manager kunnen uitwisselen en synchroniseren.

<!-- 

r_dil_idsync.xml

 -->

**Handtekening van de Functie:**

Werkt met [!UICONTROL DIL] versies 2.10 en 3.1 of hoger.

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
   <td colname="col2"> <p>Tussen verschillende gegevenspartners en Audience Manager. Partner x zou dit bijvoorbeeld gebruiken om een gebruikers-id te synchroniseren met partner y en die vervolgens naar Audience Manager te verzenden. </p> <p> <p><b> Belangrijk:</b> Deze methode is afgekeurd. Gebruik de methode <code> idSyncByURL </code> van de instantie Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dil.Instance.api.aamIdSync(initConfig) </code> </td> 
   <td colname="col2"> <p>Wanneer u de gebruikersnaam al kent en deze naar Audience Manager wilt verzenden. </p> <p> <p><b> Belangrijk:</b> Deze methode is afgekeurd. Gebruik de methode <code> idSyncByDataSource </code> van de instantie Adobe Experience Platform Identity Service. </p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**idSync Elements**

`idSync` kan uit het volgende bestaan:

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
   <td colname="col3"> <p>ID gegevensaanbieder die door Audience Manager is toegewezen. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dpuuid </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>De unieke id van de gegevensaanbieder voor de gebruiker. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> minutesToLive </code> </td> 
   <td colname="col2"> Getal </td> 
   <td colname="col3"> <p><i> (Facultatief) </i> plaatst de koekjesvervaltijd. Moet een geheel getal zijn. De standaardwaarde is 20160 minuten (14 dagen). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> url </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Doel-URL. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Macro&#39;s**

`idSync` accepteert de volgende macro&#39;s:

* **`%TIMESTAMP%`:** produceert een timestamp (in milliseconden). Wordt gebruikt voor het busten van cache.
* **`%DID%`:** voegt de Audience Manager-id voor de gebruiker in.
* **`%HTTP_PROTO%`:** Hiermee stelt u het paginaprotocol in ( `http` of `https`).

**Reactie**

Beide functies retourneren `Successfully queued` als dit gelukt is. Ze retourneren een foutbericht als dat niet het geval is.

**Code van de Steekproef**

`dilInstance.api.idSync(initConfig)`

<pre><code class="js">
// Fires url with macros replaced 
dilInstance.api.idSync(&lbrace; 
 dpid: '23', // must be a string 
 url: '//su.addthis.com/red/usync?pid=16&puid=%DID%&url=%HTTP_PROTO%%3A%2F%2Fdpm.demdex.net 
%2Fibs%3Adpid%3D420%26dpuuid%3D%7B%7Buid%7D%7D', 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

`dilInstance.api.aamIdSync(initConfig)`

<pre><code class="js">
// Fires 'https:/https:' + '//dpm.demdex.net/ibs:dpid=&lt;dpid&gt;&dpuuid=&lt;dpuuid&gt;' 
dilInstance.api.aamIdSync(&lbrace; 
 dpid: '23', // must be a string 
 dpuuid: '98765', // must be a string 
 minutesToLive: 20160 // optional, defaults to 20160 minutes (14 days)  
&rbrace;);
</code></pre>

## resultaat {#result}

Voegt een callback (die JSON ontvangt) aan het hangende verzoek toe.

<!-- 

r_dil_result.xml

 -->

**de Handtekening van de Functie:** `result: function (callback) {}`

Deze callback vervangt standaardcallback die bestemmings het publiceren behandelt.

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `callback` | Functie | JavaScript functie uitgevoerd door JSONP callback. |

**Reactie**

Retourneert het API-object van de huidige [!UICONTROL DIL] -instantie.

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).result(function(json)&lbrace; 
     //Do something, possibly with the JSON data returned from the server. 
&rbrace;);.submit();
</code></pre>

## secureDataCollection {#securedatacollection}

`secureDataCollection` is een Booleaanse parameter die bepaalt hoe [!UICONTROL DIL] aanroepen naar de [!UICONTROL Data Collection Servers (DCS)] en Akamai uitvoert.

<!-- 

dil-secure-data-collection.xml

 -->

* Bij `secureDataCollection= true` (standaardwaarde) maakt [!UICONTROL DIL] altijd beveiligde HTTPS-aanroepen.

* Wanneer `secureDataCollection= false` , [!UICONTROL DIL] of HTTP of HTTPS vraag door het veiligheidsprotocol te volgen dat door de pagina wordt geplaatst.

>[!IMPORTANT]
>
>Stel `secureDataCollection= false` in als u bezoekerAPI.js en [!UICONTROL DIL] op dezelfde pagina gebruikt. Zie het onderstaande codevoorbeeld.

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     secureDataCollection: false 
&rbrace;);
</code></pre>

## useCORSOnly {#usecorsonly}

`useCORSOnly` is een Booleaanse parameter true/false die bepaalt hoe de browser bronnen van andere domeinen opvraagt.

<!-- 

dil-use-cors-only.xml

 -->

**Overzicht**

`useCORSOnly` is standaard false. Onwaar betekent browser middelcontroles met CORS of JSONP kan uitvoeren. [!UICONTROL DIL] probeert echter altijd eerst bronnen aan te vragen bij CORS. Het keert aan JSONP op oudere browsers terug die geen CORS steunen. Stel `useCORSOnly:true` in als u de browser wilt dwingen alleen CORS te gebruiken, bijvoorbeeld met sites die hoge beveiligingsvereisten hebben.

**Steekproef van de Code**

<pre><code class="js">
var dilInstance = DIL.create(&lbrace; 
     ... 
     useCORSOnly: true 
&rbrace;);
</code></pre>

>[!IMPORTANT]
>
>* We raden u aan `useCORSOnly: true` alleen in te stellen als u zeker weet dat bezoekers van de site browsers hebben die deze functie ondersteunen.
>* Als `useCORSOnly: true` , [!UICONTROL DIL] geen id-aanroepen uitvoert vanuit Internet Explorer versie 9 of ouder.
>

## useImageRequest {#useimagerequest}

Wijzigt het aanvraagtype in afbeelding `<img>` vanuit script `<src>` .

<!-- 

r_dil_use_image_request.xml

 -->

**de Handtekening van de Functie:** `useImageRequest: function () {}`

>[!NOTE]
>
>U kunt andere API-aanroepen naar deze methode koppelen.

**Reactie**

Retourneert een API-object van de huidige [!UICONTROL DIL] -instantie.

**Code van de Steekproef**

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner:'<i>partnerName</i>', 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 
 
dataLib.api.traits([<i>123, 456, 789</i>]).useImageRequest().submit();
</code></pre>

>[!MORELIKETHIS]
>
>* [Naamvereisten voor belangrijke variabelen](../features/traits/trait-key-name-requirements.md)
>* [Voorvoegselvereisten voor belangrijke variabelen](../features/traits/trait-variable-prefixes.md)
>* [ de Functies van de Synchronisatie in de Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/methods/idsync.html)
>* [DIL maken](../dil/dil-class-overview/dil-create.md#dil-create)
>* [ de Dienst van de Identiteit van Adobe Experience Platform: UseCORSOnly ](https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/use-cors-only.html)
>* [ steun CORS in de Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/reference/cors.html)
