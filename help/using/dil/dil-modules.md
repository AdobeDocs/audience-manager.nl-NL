---
description: Beschrijft methodes in DIL.modules namespace. Deze modules laten u programmatically gegevens verzamelen en met de voorwerpen van de Audience Manager werken.
seo-description: Describes methods in the DIL.modules namespace. These modules let you programmatically collect data and work with Audience Manager objects.
seo-title: DIL Modules
solution: Audience Manager
title: DIL-modules
uuid: d4c0d8dd-79f8-448e-b17c-c935415dd449
feature: DIL Implementation
exl-id: 4685bcbb-a63b-4613-bc94-54de9881966e
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '771'
ht-degree: 1%

---

# DIL-modules{#dil-modules}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangemoedigd om te evalueren [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun strategie voor het verzamelen van gegevens op lange termijn.
>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan.

Beschrijft methodes in `DIL.modules` naamruimte. Deze modules laten u programmatically gegevens verzamelen en met de voorwerpen van de Audience Manager werken.

<!-- 

c_dil_mods.xml

 -->

## siteCatalyst.init {#sitecat-init}

Werken met [!UICONTROL DIL] naar verzenden [!DNL Analytics] tag-elementen (variabelen, props, eVars, enz.) naar Audience Manager. Retourneert gegevens in een door komma&#39;s gescheiden lijst. Beschikbaar in versie 2.6.

**Functiehandtekening:** `DIL.modules.siteCatalyst.init(siteCatalystReportingSuite, dilInstance, trackVars, options)`

>[!NOTE]
>
>U moet deze code op de pagina plaatsen *voor* de `s.t();` functie.

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
   <td colname="col3"> <p>Een array van tekenreeksen die een niet-opsomming bevat <span class="keyword"> Analyse </span> variabelen zoals <code> pageName </code>, <code> channel </code>, <code> campaign </code>, <code> product </code>, enz. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> iteratedNames </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Een array met objecten die zijn opgesomd <span class="keyword"> Analyse </span> variabelen zoals props en evars (bijvoorbeeld <code> prop1 </code>, <code> prop2 </code>, <code> evar3 </code>, <code> evar4 </code>). </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> maxIndex </code> </td> 
   <td colname="col2"> Geheel </td> 
   <td colname="col3"> <p>Geeft aan hoeveel herhaalde namen u wilt retourneren. Als u bijvoorbeeld twee voorvertoningen of gebeurtenissen wilt retourneren, stelt u <code> maxIndex:2 </code>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> siteCatalystReportingSuite </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Een object dat de <span class="keyword"> Analyse </span> object. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> dilInstance </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Een object dat <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> options </code> </td> 
   <td colname="col2"> Object </td> 
   <td colname="col3"> <p>Aanvullende opties: </p> 
    <ul id="ul_F4DFA5351BB5427B8CBF600A0A4A21A9"> 
     <li id="li_659ECE5E63834A21A2D9698A1444FCA6"> <p> <code> replaceContextDataPeriodsWith </code> </p> <p>Als u niets anders opgeeft, worden punten vervangen door het standaardonderstrepingsteken ( _ ). </p> <p>Bijvoorbeeld <code> s.contextData = {abc.def = '123'} </code>zou leiden tot <code> c_contextData_abc_def=123 </code> in de queryreeks voor gebeurtenisoproepen. </p> <p>Deze optie is alleen beschikbaar in <span class="wintitle"> DIL </span> versie 5.0 of hoger. </p> </li> 
     <li id="li_1C969DD8FC2F43A0A9281D9810A70C3A"> <p> <code> filterFromContextVariables </code> </p> <p>Bijvoorbeeld: <code> filterFromContextVariables: ['email', 'zip', 'accountNumber'] </code> resulteert in het filteren van de array van tekenreeksen uit de gegevensverzameling van contextgegevens. Deze optie sluit Persoonlijke identificeerbare informatie (PII) uit. </p> </li> 
    </ul> <p> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Gegevens vastgelegd door siteCatalyst.init**

Deze functie retourneert details over het volgende [!DNL Analytics] eigenschappen:

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

Deze code maakt een door komma&#39;s gescheiden lijst met [!DNL Analytics] gebeurtenissen (props, eVars, enz.) als er waarden voor bestaan.

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

Alle bewaakte [!DNL Analytics] gegevenspunten zonder de hierboven getoonde extra functie, aanhalen `siteCatalyst.init` op zich :

```
DIL.modules.siteCatalyst.init(s, scDil);
```

## GA.submitUniversalAnalytics {#ga-submit-universal-analytics}

De `GA.submitUniversalAnalytics();` function verzendt gegevens van Google [!DNL Universal Analytics] naar Audience Manager. Dit [!UICONTROL DIL] functie is ontworpen om te werken met `analytics.js`, de nieuwste codebibliotheek voor Google [!DNL Universal Analytics].

<!-- 

dil-google-universal-analytics.xml

 -->

>[!IMPORTANT]
>
>
>* [!DNL Audience Manager] heeft geen inzicht in of controle over de Google `analytics.js` codebibliotheek. Controleer of [!UICONTROL DIL] gegevensverzameling werkt nog steeds als of wanneer Google nieuwe versies van `analytics.js`.
>
>* U kunt niet `GA.submitUniversalAnalytics();` als u nog steeds werkt met code voor het bijhouden van analyses van Google (bijvoorbeeld `ga.js` of `dc.js`). Zie [GA.init](../dil/dil-modules.md#ga-init) in plaats daarvan.
>

**Functiehandtekening:** `DIL.modules.GA.submitUniversalAnalytics(gaObject, dilInstance, internalPropertyName);`

**Eigenschappen**

De `GA.submitUniversalAnalytics();` -functie accepteert de volgende eigenschappen.

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
   <td colname="col2"> <p>De algemene variabele voor uw instantie van <span class="keyword"> Google Analytics </span>. Dit is gewoonlijk <code> ga </code> standaard, tenzij u uw <span class="keyword"> Google Analytics </span> code. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> dilInstance </code> </p> </td> 
   <td colname="col2"> <p>De variabele die uw instantie van <span class="wintitle"> DIL </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> internalPropertyName </code> </p> </td> 
   <td colname="col2"> <p> <i>(Optioneel)</i> In de <code> analytics.js </code> bibliotheek, is het interne bezit de geminiatuurde variabele <code> 'b' </code>. Deze variabele houdt rekening met <span class="keyword"> Google Analytics </span> gegevens. </p> <p>Deze eigenschap is optioneel omdat u deze alleen hoeft in te stellen als Google de naam van de interne variabele wijzigt. Als deze geminificeerde variabele bijvoorbeeld is gewijzigd in <code> 'a' </code>, u wilt bellen <code> GA.submitUniversalAnalytics(); </code> als volgt: </p> <p> <code> DIL.modules.GAsubmitUniversalAnalytics(ga, DilInstance, 'a'); </code> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Voorbeeld**

Vergeet niet de [!DNL Google Analytics] `ga` object eerst, voordat wordt aangeroepen [!UICONTROL DIL] en `GA.submitUniversalAnalytics();`. Uw code kan er ongeveer als volgt uitzien:

```js
//Instantiate DIL 
var dilInstance = DIL.create({ 
     partner:"adobe" 
}); 
 
//Call the DIL Universal Analytics function 
DIL.modules.GA.submitUniversalAnalytics(ga, dilInstance);
```

## GA.init {#ga-init}

De `GA.init()` functie verzendt gegevens van de verouderde/vervangen versie van [!DNL Google Analytics] naar Audience Manager.

<!-- 

r_dil_ga_init.xml

 -->

>[!IMPORTANT]
>
>`GA.init()` werkt alleen met de code voor het bijhouden van analyses van Google. `ga.js` of `dc.js`. U kunt dit niet aanroepen [!UICONTROL DIL] functie als u `analytics.js`, de nieuwste codebibliotheek voor Google [!DNL Universal Analytics]. [!DNL Audience Manager] klanten die [!UICONTROL DIL] en [!DNL Universal Analytics] moet [GA.submitUniversalAnalytics](../dil/dil-modules.md#ga-submit-universal-analytics).

**Functiehandtekening:** `DIL.modules.GA.init(_gaq, dilInstance, trackVars);`

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `_gaq` | Array | Een array die GA-opdrachten bevat. |
| `dilInstance` | Object | Een object dat de instantie DIL bevat. |
| `trackVars` | Object | *(Optioneel)* Een object dat bestaat uit de `names` eigenschap. Deze eigenschap is een array van GA-opdrachtnamen die u wilt bijhouden. |

**Ondersteunde functieaanroepen GA**

Standaard, `GA.init` vangt gegevens van de volgende functies:

* `_setCustomVar`
* `_addItem`
* `_addTrans`
* `_setAccount`
* `_trackSocial`

**DIL maakt toetsen voor GA-gegevens**

Audience Manager accepteert gegevens in de vorm van sleutelwaardeparen, terwijl GA werkt met items in een array. Om met GA-gegevens te werken, [!UICONTROL DIL] maakt automatisch een sleutelwaardepaar en vormt zo een sleutel: `c_ <key name>`. Items in GA-arrays worden ook in een specifieke volgorde weergegeven. Dit betekent dat u alle parameters in die volgorde moet opgeven, zelfs als deze geen gegevens bevatten. [!UICONTROL DIL] kaarttoetsen voor de volgende GA-methoden:

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

Om alle bewaakte GA metriek zonder de extra hierboven getoonde functie te volgen, haal `GA.init` op zich :

`DIL.modules.GA.init(_gaq, dilInstance).submit();`

**Voorbeeld van gebeurtenisoproep**

De URL-gebeurtenisaanroep naar Audience Manager kan er als volgt uitzien:

`https://adobe.demdex.com/event?...c_accountId=UA-XXXXX-X&c_Section=Life%20%26%20Style &c_itemOrderId=1234&c_itemSku=DD44&c_itemName=T-Shirt&c_itemCategory=Olive%20Medium& c_itemPrice=11.99&c_itemQuantity=1`

>[!MORELIKETHIS]
>
>* [Google Analytics trackingcode](https://developers.google.com/analytics/devguides/collection/gajs/methods/)
>* [Volledige webupgrade: ga.js/dc.js naar analytics.js](https://developers.google.com/analytics/devguides/collection/upgrade)
>* [Analytics.js toevoegen aan uw site](https://developers.google.com/analytics/devguides/collection/analyticsjs/)
>* [Verwijzing naar ga-objectmethoden](https://developers.google.com/analytics/devguides/collection/analyticsjs/ga-object-methods-reference)
