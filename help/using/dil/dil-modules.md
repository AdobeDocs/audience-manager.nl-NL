---
description: Beschrijft methodes in DIL.modules namespace. Deze modules laten u programmatically gegevens verzamelen en met de voorwerpen van de Audience Manager werken.
seo-description: Beschrijft methodes in DIL.modules namespace. Deze modules laten u programmatically gegevens verzamelen en met de voorwerpen van de Audience Manager werken.
seo-title: DIL-modules
solution: Audience Manager
title: DIL-modules
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL-implementatie
translation-type: tm+mt
source-git-commit: 65598677498ede26e4961cd4849c9b655dac38dc
workflow-type: tm+mt
source-wordcount: '716'
ht-degree: 1%

---


# DIL-modules{#dil-modules}

Beschrijft methodes in `DIL.modules` namespace. Deze modules laten u programmatically gegevens verzamelen en met de voorwerpen van de Audience Manager werken.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Werkt met [!UICONTROL DIL] om [!DNL Analytics] markeringselementen (variabelen, steunen, eVars, enz.) te verzenden naar Audience Manager. Retourneert gegevens in een door komma&#39;s gescheiden lijst. Beschikbaar in versie 2.6.

**Functiehandtekening:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>U moet deze code op de pagina *vóór* de functie `s.t();` plaatsen.

<!-- 

r_dil_sc_init.xml

 -->

**Parameters**

<table id="table_A8CF8D298D944A608E2F49719F2732A1"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Namen </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr valign="top"> 
   <td colname="col1"> <code> names </code> </td> 
   <td colname="col2"> String </td> 
   <td colname="col3"> <p>Een array van tekenreeksen die niet-opgesomde <span class="keyword"> Analytics </span> variabelen zoals <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, enz. bevat. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Een array van objecten die opgesomde <span class="keyword"> Analytics </span>-variabelen zoals props en evars bevat (bijvoorbeeld <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Geheel </td> 
   <td colname="col3"> <p>Geeft aan hoeveel herhaalde namen u wilt retourneren. Stel <code> maxIndex:2 </code> in als u bijvoorbeeld twee voorvertoningen of gebeurtenissen wilt retourneren. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Een object dat het object <span class="keyword"> Analytics </span> vertegenwoordigt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Een object dat <span class="wintitle"> DIL </span> vertegenwoordigt. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Aanvullende opties: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Als u niets anders opgeeft, worden punten vervangen door het standaardonderstrepingsteken ( _ ). </p> <p><code> s.contextData = {abc.def = '123'} </code>resulteert bijvoorbeeld in <code> c_contextData_abc_def=123 </code> in de queryreeks voor de gebeurtenisaanroep. </p> <p>Deze optie is alleen beschikbaar in <span class="wintitle"> DIL </span> versie 5.0 of hoger. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p><code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> resulteert bijvoorbeeld in het filteren van de array van tekenreeksen uit de gegevensverzameling van contextgegevens. Deze optie sluit Persoonlijke identificeerbare informatie (PII) uit. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Gegevens vastgelegd door siteCatalyst.init**

Deze functie retourneert details over de volgende [!DNL Analytics] eigenschappen:

* `pageName`
* `channel`
* `campaign`
* `products`
* `events`
* `eVar` (1 - 250)
* `prop` (1 - 75)
* `pe`
* `pev1`
* `pev2`
* `pev3`

**Voorbeeldcode**

Deze code maakt een door komma&#39;s gescheiden lijst van gebeurtenissen [!DNL Analytics] (eigenschappen, eVars, enz.) als er waarden voor bestaan.

```
// Get the Site Catalyst object instance: 
var s = s_gi(s_account); 
  
// Instantiate DIL code: 
var scDil = DIL.create({ 
        partner: 'adobe', 
        containerNSID: 5 
}); 
 
// Use the module: 
DIL.modules.siteCatalyst.init(s, scDil, { 
        //Specify the Site Catalyst variables you want to capture: 
        names: ['pageName', 'channel', 'campaign'], 
        //Use this to create iterated variable names: 
        iteratedNames: [{ 
               name: 'eVar', 
               maxIndex: 75 
        }, { 
               name: 'prop', 
               maxIndex: 75 
        }] 
});
```

Als u alle gecontroleerde [!DNL Analytics] gegevenspunten wilt bijhouden zonder de extra functie die hierboven is weergegeven, roept u `siteCatalyst.init` als volgt aan:

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

De functie `GA.submitUniversalAnalytics();` verzendt gegevens van [!DNL Universal Analytics] van Google naar Audience Manager. Deze [!UICONTROL DIL] functie is ontworpen om met `analytics.js` te werken, die de recentste codebibliotheek voor Google [!DNL Universal Analytics] is.

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] heeft geen inzicht in of controle over de Google- `analytics.js` codebibliotheek. Controleer of [!UICONTROL DIL] gegevensverzameling nog steeds werkt als of wanneer Google nieuwe versies van `analytics.js` publiceert.
   >
   >
* U kunt `GA.submitUniversalAnalytics();` niet gebruiken als u nog steeds werkt met de oudere code voor het bijhouden van analysemogelijkheden van Google (bijvoorbeeld `ga.js` of `dc.js`). Zie [GA.init](../dil/dil-modules.md#ga-init) in plaats daarvan.

>



**Functiehandtekening:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Eigenschappen**

De functie `GA.submitUniversalAnalytics();` accepteert de volgende eigenschappen.

<table id="table_8E0C1E4B17D541259E72B88F02BE4503"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Eigenschap </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> gaObject </code> </p> </td> 
   <td colname="col2"> <p>De algemene variabele voor uw instantie van <span class="keyword"> Google Analytics </span>. Dit is gewoonlijk <code> ga </code> door gebrek, tenzij u uw <span class="keyword"> Google Analytics code </span> hebt aangepast. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>De variabele die uw instantie van <span class="wintitle"> DIL </span> vertegenwoordigt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Optioneel)</i> In de  <code> analytics.js </code> bibliotheek is de interne eigenschap de geminificeerde variabele  <code> 'b' </code>. Deze variabele bevat <span class="keyword"> Google Analytics </span> gegevens. </p> <p>Deze eigenschap is optioneel omdat u deze alleen hoeft in te stellen als Google de naam van de interne variabele wijzigt. Bijvoorbeeld, als deze geminificeerde variabele in <code> 'a' </code> veranderde, zou u <code> GA.submitUniversalAnalytics(); </code> als dit roepen: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Voorbeeld**

Denk eraan om het [!DNL Google Analytics] `ga` voorwerp eerst te bepalen, alvorens [!UICONTROL DIL] en `GA.submitUniversalAnalytics();` te roepen. Uw code kan er ongeveer als volgt uitzien:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

De functie `GA.init()` verzendt gegevens van verouderde/vervangen versie van [!DNL Google Analytics] naar Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` werkt alleen met Google&#39;s oudere code voor het bijhouden van analysemogelijkheden,  `ga.js` of  `dc.js`. U kunt deze [!UICONTROL DIL] functie niet aanroepen als u `analytics.js`, de recentste codebibliotheek voor Google [!DNL Universal Analytics] gebruikt. [!DNL Audience Manager] klanten die gebruikmaken  [!UICONTROL DIL] en  [!DNL Universal Analytics] moeten  [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics) raadplegen.

**Functiehandtekening:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `_gaq` | Array | Een array die GA-opdrachten bevat. |
| `dilInstance` | Object | Een object dat de instantie DIL bevat. |
| `trackVars` | Object | *(Optioneel)* Een object dat bestaat uit de  `names` eigenschap. Deze eigenschap is een array van GA-opdrachtnamen die u wilt bijhouden. |

**Ondersteunde functieaanroepen GA**

Standaard legt `GA.init` gegevens van de volgende functies vast:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL maakt toetsen voor GA-gegevens**

Audience Manager accepteert gegevens in de vorm van sleutelwaardeparen, terwijl GA werkt met items in een array. Als u met GA-gegevens wilt werken, maakt [!UICONTROL DIL] automatisch een sleutelwaardepaar en vormt dit een soort sleutel: `c_ <key name>`. Items in GA-arrays worden ook in een specifieke volgorde weergegeven. Dit betekent dat u alle parameters in die volgorde moet opgeven, zelfs als deze geen gegevens bevatten. [!UICONTROL DIL] kaarttoetsen voor de volgende GA-methoden:

```js
// Tracking Social Interactions 
_gaq.push(['_trackSocial', 
    'facebook',                        // c_socialNetwork 
    'like',                            // c_socialAction 
    'https://www.adobe.com/cool.php',   // c_socialTarget 
    '/cool.php'                        // c_socialPagePath 
]);  
 
// Tracking a Transaction 
_gaq.push(['_addTrans', 
   '1234',           // c_transOrderId 
   'Womens Apparel', // c_transAfflication 
   '28.28',          // c_transTotal 
   '1.29',           // c_tranTax 
   '15.00',          // c_transShipping 
   'San Jose',       // c_transCity 
   'California',     // c_transState 
   'USA'             // c_transCountry 
]); 
 
// Tracking an item 
_gaq.push(['_addItem', 
   '1234',           // c_itemOrderId=1234 
   'DD44',           // c_itemSku 
   'T-Shirt',        // c_itemName 
   'Olive Medium',   // c_itemCategory 
   '11.99',          // c_itemPrice 
   '1'               // c_itenQuantity 
]);
```

**Voorbeeldcode**

```js
// DIL JavaScript library needs to be loaded and executed here 
var dilInstance = DIL.create({ 
    partner : "adobe" 
}); 
 
// Assume ga.js has not loaded 
var _gaq = _gaq || []; 
_gaq.push( 
  ['_setAccount', 'UA-XXXXX-X'], 
  ['_setDomainName', 'example.com'], 
  ['_setCustomVar', 1, 'Section', 'Life & Style', 3], 
  ['_trackPageview'] 
); 
_gaq.push([ 
  '_addItem', 
  '1234',         // order ID - necessary to associate item with transaction 
  'DD44',         // SKU/code - required 
  'T-Shirt',      // product name - necessary to associate revenue with product 
  'Olive Medium', // category or variation 
  '11.99',        // unit price - required 
  '1'             // quantity - required 
]); 
```

Als u alle bewaakte GA-meetgegevens wilt bijhouden zonder de hierboven weergegeven extra functie, roept u `GA.init` als volgt aan:

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Voorbeeld van gebeurtenisoproep**

De URL-gebeurtenisaanroep naar Audience Manager kan er als volgt uitzien:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics trackingcode](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Volledige webupgrade: ga.js/dc.js to analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Analytics.js toevoegen aan uw site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Verwijzing naar ga-objectmethoden](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)

