---
description: Beschrijft methodes in DIL.tools namespace. Deze hulpprogrammafuncties helpen u specifieke taken uit te voeren.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL Tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 0%

---

# DIL Tools

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [&#x200B; SDK van het Web van Experience Platform &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [&#x200B; SDK van het Web van Experience Platform &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan moeten gebruiken.

Beschrijft methodes in `DIL.tools` namespace. Deze hulpprogrammafuncties helpen u specifieke taken uit te voeren.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Retourneert de zoektermen die worden gebruikt om de huidige pagina te bereiken.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Doel van `getSearchReferrer`

In DIL retourneert `getSearchReferrer` zoekresultaten (namen en trefwoorden) die worden gebruikt om uw site te bereiken. U kunt specifieke zoektermen doorgeven aan deze functie of deze standaard laten zoeken in de ondersteunde zoekmachines ( [!DNL AOL] , [!DNL Ask] , [!DNL Bing] , [!DNL Google] en [!DNL Yahoo] ) op `document.referrer` .

### Functiehandtekening

Functiehandtekening: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Functieparameters

`getSearchReferrer` accepteert:

* *`{string}`*: *(Optioneel)* Een tekenreeks die de zoek-URL bevat (gebruikt `document.referrer` indien niet gedefinieerd).
* *`{object}`*: *(Facultatief)* Een voorwerp dat de configuratie voor `hostPattern` bevat, `queryParam`, of `queryPattern`.

En retourneert:

* `{object}` Een object dat geldige namen en trefwoorden bevat.

### Voorbeelden

<table id="table_D035276601EC428295E4D619F05BB8D0"> 
 <thead> 
  <tr> 
   <th> Zoektype </th> 
   <th> Beschrijving </th> 
   <th> Codevoorbeeld </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td> Standaardzoekopdracht</td> 
   <td> Retourneert zoektermen met trefwoorden die worden gebruikt door de zoekmachines AOL, Ask, Bing, Google en Yahoo. </td> 
   <td>
      <code>var&nbsp;results&nbsp;=&nbsp;DIL.tools.getSearchReferrer();</code> 
  </td>
  </tr> 
  <tr> 
   <td>Geef een aangepaste URL door</td> 
   <td>Retourneert de zoekverwijzer op basis van een aangepaste URL.</td> 
   <td> 
  <code>
        var&nbsp;results&nbsp;= 
        DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules");
  </code>
</td> 
  </tr> 
  <tr> 
   <td> <b> Gelijke Hostnaam URL met een Douane Regex </b></td> 
   <td> Geef een aangepaste regex door zodat deze overeenkomt met de hostnaam van de verwijzende URL. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",&lbrace; 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      &rbrace;); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b> Patronen van het Onderzoek van de Gelijke met een Douane Regex </b> </td> 
   <td> Geef een aangepaste regex door om een aangepaste zoekopdracht uit te voeren. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      &lbrace;
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      &rbrace;);
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Hiermee wordt een Uniform Resource Identifier ( [!DNL URI]) gedemonteerd in de bestanddelen: `hash`, `host`, `href`, `pathname`, `protocol`, `search` en `[!DNL uriParams]` .

<!-- 

r_dil_decompose.xml

 -->

Functiehandtekening: `DIL.tools.decomposeURI`

### Functieparameters

`decomposeURI` accepteert:

* *`uri {string}`*: *(Optioneel)* Een tekenreeks die de URI bevat. De standaardwaarde is `document.location.href` als deze niet is opgegeven.

En retourneert:

* *`{object}`*: Een object dat geldige namen en trefwoorden bevat.

### Voorbeeldcode


```javascript
var uriData = DIL.tools.decomposeURI('https://www.adobe.com/?arg1=123&arg2=456#am'); 
{ 
  hash : "#am", 
  host : "www.adobe.com", 
  hostname : "www.adobe.com", 
  href : "https://www.adobe.com/?arg1=123&arg2=456#am", 
  pathname : "", 
  protocol : "https:", 
  search : "?arg1=123&arg2=456", 
  uriParams : { 
    arg1 : "123", 
    arg2 : "456" 
  } 
}
```

## getMetaTags

Zoekt naar specifieke inhoud die in de metatags op een webpagina is gedefinieerd en retourneert die gegevens in een object.

<!-- 

r_dil_get_metatags.xml

 -->

### Functiehandtekening

Functiehandtekening: `DIL.tools.getMetaTags( 1 or more parameters)`

### Functieparameters

`getMetaTags` accepteert een of meer naamparameters (type tekenreeks) waarnaar moet worden gezocht. Er wordt een object geretourneerd dat bestaat uit sleutelwaardeparen.

### Voorbeeldcode

<pre class="javascript"><code>
var dataLib = DIL.create(&lbrace; 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create(&lbrace; 
     partner: <i>&grave;partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
&rbrace;); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
