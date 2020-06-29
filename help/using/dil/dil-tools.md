---
description: Beschrijft methodes in DIL.tools namespace. Deze hulpprogrammafuncties helpen u specifieke taken uit te voeren.
seo-description: Beschrijft methodes in DIL.tools namespace. Deze hulpprogrammafuncties helpen u specifieke taken uit te voeren.
seo-title: DIL-gereedschappen
solution: Audience Manager
title: DIL-gereedschappen
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '293'
ht-degree: 0%

---


# DIL-gereedschappen

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

In DIL worden zoekresultaten (namen en trefwoorden) geretourneerd die zijn gebruikt om uw site te bereiken. `getSearchReferrer` U kunt specifieke zoektermen doorgeven aan deze functie of de ondersteunde zoekfuncties ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google]en [!DNL Yahoo]) standaard laten doorzoeken `document.referrer` .

### Functiehandtekening

Handtekening functie: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Functieparameters

`getSearchReferrer` accepteert:

* *`{string}`*: *(Optioneel)* Een tekenreeks die de zoek-URL bevat (wordt gebruikt `document.referrer` als deze niet is gedefinieerd).
* *`{object}`*: *(Optioneel)* Een object met de configuratie voor de `hostPattern`, `queryParam`of `queryPattern`.

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
      <code>var&amp;nbsp;results&amp;nbsp;=&amp;nbsp;DIL.tools.getSearchReferrer();</code> 
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
   <td> <b>URL-hostnaam afstemmen met een aangepaste Regex</b></td> 
   <td> Geef een aangepaste regex door zodat deze overeenkomt met de hostnaam van de verwijzende URL. </td> 
   <td> 
  <code>
      var results = 
        DIL.tools.getSearchReferrer("https://www.ehow.com/
      search.aspx?q=adobe+rules",{ 
      &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
      &nbsp;&nbsp;&nbsp;queryParam:"p" 
      }); 
  </code>
  </td></tr> 
  <tr> 
   <td> <b>Zoekpatronen afstemmen met een aangepaste Regex</b> </td> 
   <td> Geef een aangepaste regex door om een aangepaste zoekopdracht uit te voeren. </td> 
   <td> 
    <code>
      var&nbsp;results&nbsp;= 
      DIL.tools.getSearchReferrer("https://www.ehow.com/search.aspx?q=adobe+rules,
      {
        &nbsp;&nbsp;&nbsp;hostPattern:/ehow\./, 
        &nbsp;&nbsp;&nbsp;search_pattern:/[&amp;\?]p=([^&amp;]+/ 
      });
    </code>
   </td> 
  </tr> 
 </tbody> 
</table>

## decomposeURI

Hiermee wordt een Uniform Resource Identifier ( [!DNL URI]) gedemonteerd in de bestanddelen ervan: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, en `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Handtekening functie: `DIL.tools.decomposeURI`

### Functieparameters

`decomposeURI` accepteert:

* *`uri {string}`*: *(Optioneel)* Een tekenreeks die de URI bevat. Wordt standaard ingesteld `document.location.href` als deze niet is opgegeven.

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

Handtekening functie: `DIL.tools.getMetaTags( 1 or more parameters)`

### Functieparameters

`getMetaTags` Accepteert een of meer naamparameters (type tekenreeks) waarnaar moet worden gezocht. Er wordt een object geretourneerd dat bestaat uit sleutelwaardeparen.

### Voorbeeldcode

<pre class="&ldquo;javascript&rdquo;"><code>
var dataLib = DIL.create({ 
     partner: '<i>partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>', '<i>keywords</i>',  '<i>description</i>'), 'c_').submit();
</code></pre>

<pre><code>
var dataLib = DIL.create({ 
     partner: <i>`partnerName'</i>, 
     containerNSID: <i>containerNSID</i> 
}); 

dataLib.api.signals(DIL.tools.getMetaTags('<i>application</i>','<i>keywords</i>', '<i>description</i>'), 'c_').submit();
</code></pre>
