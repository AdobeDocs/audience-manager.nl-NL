---
description: Beschrijft methodes in DIL.tools namespace. Deze hulpprogrammafuncties helpen u specifieke taken uit te voeren.
seo-description: Describes methods in the DIL.tools namespace. These utility functions help you perform specific tasks.
seo-title: DIL Tools
solution: Audience Manager
title: DIL-tools
uuid: 2bc62ce2-16bd-4e80-b493-c816ba643b59
feature: DIL Implementation
exl-id: 1f52eb95-8287-4dd0-b933-00de6926a797
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '355'
ht-degree: 1%

---

# DIL-tools

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangemoedigd om te evalueren [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun strategie voor het verzamelen van gegevens op lange termijn.
>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan.

Beschrijft methodes in `DIL.tools` naamruimte. Deze hulpprogrammafuncties helpen u specifieke taken uit te voeren.

<!-- 

c_dil_functions.xml

 -->

## getSearchReferrer

Retourneert de zoektermen die worden gebruikt om de huidige pagina te bereiken.

<!-- 

r_dil_get_search_referrer.xml

 -->

### Doel van `getSearchReferrer`

In DIL, `getSearchReferrer` retourneert zoekresultaten (namen en trefwoorden) die worden gebruikt om uw site te bereiken. U kunt specifieke zoektermen doorgeven aan deze functie of de functie laten zoeken in de ondersteunde zoekmachines ( [!DNL AOL], [!DNL Ask], [!DNL Bing], [!DNL Google], en [!DNL Yahoo]) tegen `document.referrer` standaard.

### Functiehandtekening

Handtekening functie: `DIL.tools.getSearchReferrer(uri, initConfig)`

### Functieparameters

`getSearchReferrer` accepteert:

* *`{string}`*: *(Optioneel)* Een tekenreeks met de zoek-URL (gebruikt `document.referrer` indien ongedefinieerd).
* *`{object}`*: *(Optioneel)* Een object dat de configuratie voor de `hostPattern`, `queryParam`, of `queryPattern`.

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
   <td> <b>URL-hostnaam afstemmen met een aangepaste Regex</b></td> 
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
   <td> <b>Zoekpatronen afstemmen met een aangepaste Regex</b> </td> 
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

Hiermee wordt een Uniform Resource Identifier gedemonteerd ( [!DNL URI]) in de bestanddelen ervan: `hash`, `host`, `href`, `pathname`, `protocol`, `search`, en `[!DNL uriParams]`.

<!-- 

r_dil_decompose.xml

 -->

Handtekening functie: `DIL.tools.decomposeURI`

### Functieparameters

`decomposeURI` accepteert:

* *`uri {string}`*: *(Optioneel)* Een tekenreeks die de URI bevat. Standaardwaarden: `document.location.href` indien niet opgegeven.

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
