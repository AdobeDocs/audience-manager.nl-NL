---
description: Maakt een partnerspecifieke DIL-instantie.
seo-description: Maakt een partnerspecifieke DIL-instantie.
seo-title: DIL maken
solution: Audience Manager
title: DIL maken
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '837'
ht-degree: 0%

---


# DIL-methode maken{#dil-create}

## DIL maken {#dil-create-new}

Maakt een partnerspecifieke [!UICONTROL DIL] instantie.

**Functiehandtekening:** `DIL.create: function (initConfig) {}`

**initConfig Elements**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>De `visitorService` eigenschap is *altijd* vereist. Andere hier vermelde eigenschappen zijn optioneel, tenzij anders aangegeven.

`initConfig` aanvaardt de volgende elementen:

<table id="table_1334973505F54B238127FED9845B16C4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Naam </th> 
   <th colname="col2" class="entry"> Type </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> containerNSID </code> </p> </td> 
   <td colname="col2"> <p>Geheel </p> </td> 
   <td colname="col3"> <p>Met deze eigenschap wordt de container-id ingesteld die door <span class="keyword"> Audience Manager wordt gebruikt </span> voor ID-syncs. U zou plaatsen <code> containerNSID </code> als u <span class="wintitle"> DIL over veelvoudige plaatsen hebt </span> opgesteld. Elk van deze sites heeft een eigen container-id en id-syncs. Als u slechts 1 site hebt, is de container-id standaard 0 en hoeft u dit niet op de juiste wijze in te stellen. Neem contact op met uw consultant voor een lijst met uw sites en de bijbehorende container-id's. </p> <p>In de dienst van de Identiteit van het <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform </a>, beantwoordt het bezit <code> idSyncContainerID </code> aan <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Let op het volgende als u <span class="wintitle"> DIL </span> en de dienst van identiteitskaart over veelvoudige plaatsen gebruikt <i></i> : </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Stel voor elke site dezelfde container-id's in op <code> containerNSID </code> en <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Zowel <span class="wintitle"> DIL </span> als de ID-service proberen id-syncs naar ons iFrame voor gegevensverzameling te verzenden. De iFrame zorgt er echter voor dat <span class="wintitle"> DIL </span> geen id-synchronisatie start. Dit voorkomt dubbel werk. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Alleen <span class="wintitle"> DIL </span> verzendt gegevens naar een <a href="../../features/destinations/destinations.md"> URL-doel </a>. </li> 
     </ul> </p> <p>Zie ook <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncontainerid.html" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> 
    <draft-comment> 
     <p>Verzendt de <a href="../../features/declared-ids.md"> Gedeclareerde variabelen van identiteitskaart </a> op elke gebeurtenisvraag naar <span class="keyword"> Audience Manager </span>. </p> 
    </draft-comment> <p> <code> delcaredId </code> wordt gebruikt voor het passeren van: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Identiteitskaart van de partner van gegevens die aan u door <span class="keyword"> Audience Manager wordt toegewezen </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Je unieke id voor een gebruiker. </li> 
    </ul> <p> <p>Belangrijk:  Gebruik alleen niet-gecodeerde waarden voor uw id's. Bij codering worden dubbelgecodeerde id's gemaakt. </p> </p> <p> <p>Opmerking:  Als u de Dienst van de Identiteit van het <a href="https://docs.adobe.com/content/help/en/id-service/using/home.html" format="https" scope="external"> Adobe Experience Platform gebruikt </a>, plaats klant IDs met de <code> setCustomerIDs </code> methode in plaats van <span class="wintitle"> DIL </span>. See <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> Customer IDs and Authentication States </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Indien waar (true), worden alle aanvragen (IFRAME, gebeurtenisaanroepen, id-synchronisatie en doel) uitgesteld van uitvoering tot de <code> Page Load </code> gebeurtenis wordt geactiveerd. Standaard is dit <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Onwaar door gebrek, wat betekent <span class="keyword"> Audience Manager een koekje in het domein van de partner </span> plaatst (plaatst een eerste partijkoekje). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk:  Dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik in plaats hiervan de <code> visitor.disableIdSyncs </code> functie <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> in de Adobe Experience Platform Identity Service. </p> </p> <p> Indien <code> true </code>, zal niet de bestemmings het publiceren IFRAME aan DOM of brandbestemmingen vastmaken. Standaard is dit <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk:  Dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik in plaats hiervan de <code> visitor.disableIdSyncs </code> functie <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/disableidsync.html" format="https" scope="external"> </a> in de Adobe Experience Platform Identity Service. </p> </p> <p>Schakelt id-synchronisatie uit. U moet ID-syncs uitschakelen bij gebruik van DIL v6.2+ en de Bezoeker-id-service. Deze bewerking wordt uitgevoerd door de <code> visitorService </code> functie (zie de voorbeeldcode hieronder). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Ingesteld op <code> true </code> om foutrapportage voor alle <span class="wintitle"> DIL- </span> instanties op de pagina in te schakelen. Werkt <code> true </code> alleen met Boolean. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk:  Dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik in plaats hiervan de <code> visitor.idSyncSSLUseAkamai </code> functie <a href="https://docs.adobe.com/content/help/en/id-service/using/id-service-api/configurations/idsyncssluseakamai.html" format="https" scope="external"> </a> in de Adobe Experience Platform Identity Service. </p> </p> <p> Hiermee wordt opgegeven of de doelpublicatiesjabloon Akamai moet gebruiken voor HTTPS-verbindingen. Toegelaten op een per-partnerbasis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Koppelt de waarde van het ene sleutelwaardepaar aan een ander. Zie Sleutelwaarden toewijzen aan andere toetsen <a href="../../dil/dil-use-cases.md#map-key-values"> </a>. Uitgegeven met v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Vereist. </p> <p>Het <code> namespace </code> sleutelwaardepaar bevat uw <span class="keyword"> Experience Cloud- </span> organisatie-id. Als u deze id niet hebt, kunt u deze vinden in het gedeelte <span class="wintitle"> Beheer </span> van het <span class="keyword"> Experience Cloud- </span> dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Raadpleeg de veelgestelde vragen over <a href="../../faq/faq-features.md"> productfuncties en -functies </a> en <a href="https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/faq.html" format="https" scope="external"> Beheer - Gebruikersbeheer en veelgestelde vragen </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Vereist. </p> <p> De naam van de partner zoals verstrekt door <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Hiermee verwijdert u scripts en callbacks. Standaard is dit <code> False </code>. Is alleen van toepassing op de huidige <span class="wintitle"> DIL- </span> instantie. Uitgegeven met v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Stelt een cookie in met de unieke gebruikers-id die door de <span class="keyword"> Audience Manager wordt geretourneerd </span>. Zie <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uidCookie-eigenschappen </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Vereist met <span class="wintitle"> DIL </span> 6.2 of hoger. </p> <p> DIL vertrouwt op de functie in de Dienst van de Identiteit van het <code> setCustomerIDs </code> Adobe Experience Platform <span class="wintitle"> om gedeclareerde IDs tot </span> Audience Manager over te gaan <span class="keyword"> </span>. Raadpleeg <a href="https://docs.adobe.com/content/help/en/id-service/using/reference/authenticated-state.html" format="https" scope="external"> </a> Customer ID's en verificatiestatus voor meer informatie. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Voorbeeldcode**

Een steekproefvraag kon aan het volgende gelijkaardig kijken: [!UICONTROL DIL]

```js
var partnerObject1 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-ORGANIZATION-ID-HERE" 
  }, 
  containerNSID: 3, 
  uuidCookie:{ 
    name:'ad_uuid', 
    days:200, 
    path:'/test', 
    domain:'adobe.com', 
    secure:true 
  } 
}); 
 
var partnerObject2 = DIL.create({ 
  partner: "partner name", 
  visitorService:{ 
    namespace: "INSERT-MCORG-ID-HERE" 
  }, 
  containerNSID: 3 
}); 
```

Een geslaagde reactie retourneert de [!UICONTROL DIL] instantie. Een mislukte poging retourneert een foutobject (niet gegenereerd) als de code onjuist is geconfigureerd of als er een fout optreedt.

## uuidCookie-eigenschappen {#uuidcookie-props}

Definieert de eigenschappen die door de `uuidCookie` variabele worden gebruikt. Deze variabele maakt deel uit van de `DIL.create` methode.

`uuidCookie` heeft de volgende eigenschappen:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Naam | Beschrijving |
|---|---|
| `name` | De naam van het cookie ( `aam_did` is standaard). |
| `days` | Het leven van het cookie (100 dagen is gebrek). |
| `path` | Cookie-pad, bijvoorbeeld `'/test'` ( `/` is standaard). |
| `domain` | Het domein waarin de cookie wordt ingesteld, bijvoorbeeld `'adobe.com'` ( `'.'+document.domain` is standaard). |
| `secure` | Hiermee stelt u een markering in voor het verzenden van gegevens via alleen een HTTPS-verbinding. |

## eigenschappen van bezoekerService {#visitor-service-props}

Definieert de eigenschappen die door de `visitorService` variabele worden gebruikt. Deze variabele maakt deel uit van de `DIL.create` methode.

`visitorService` heeft de volgende eigenschappen:

| Naam | Type | Beschrijving |
|---|---|---|
| `namespace` | String | Vereist. Vertegenwoordigt de Experience Cloud Org ID. Dit is nodig voor de Experience Cloud Core Service-functionaliteit. Dezelfde parameter die wordt gebruikt om de functie Bezoekersidentiteitskaart te instantiëren. |

**Codevoorbeeld:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
