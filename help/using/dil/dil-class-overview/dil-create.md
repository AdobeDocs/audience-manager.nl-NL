---
description: Maakt een partnerspecifieke DIL-instantie.
seo-description: Creates a partner-specific DIL instance.
seo-title: DIL create
solution: Audience Manager
title: DIL maken
uuid: 6e054600-703c-4a97-af2a-8207c50013db
feature: DIL Implementation
exl-id: 0bef149c-4458-43d6-affe-6d79fe1fca46
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '820'
ht-degree: 0%

---

# DIL-methode maken{#dil-create}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan moeten gebruiken.

## DIL maken {#dil-create-new}

Maakt een partnerspecifieke [!UICONTROL DIL] -instantie.

**de Handtekening van de Functie:** `DIL.create: function (initConfig) {}`

**initConfig Elementen**

<!-- 

r_dil_create.xml

 -->

>[!IMPORTANT]
>
>Het `visitorService` bezit is *altijd* vereist. Andere hier vermelde eigenschappen zijn optioneel, tenzij anders aangegeven.

`initConfig` accepteert de volgende elementen:

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
   <td colname="col3"> <p>Deze eigenschap stelt de container-id in die door <span class="keyword"> Audience Manager </span> wordt gebruikt voor id-syncs. U stelt <code> containerNSID </code> in als u <span class="wintitle"> DIL </span> hebt geïmplementeerd voor meerdere sites. Elk van deze sites heeft een eigen container-id en id-syncs. Als u slechts 1 site hebt, is de container-id standaard 0 en hoeft u dit niet op de juiste wijze in te stellen. Neem contact op met uw consultant voor een lijst met uw sites en de bijbehorende container-id's. </p> <p>In de <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL" format="https" scope="external"> Adobe Experience Platform Identity Service </a> komt de eigenschap <code> idSyncContainerID </code> overeen met <code> containerNSID </code> in <span class="wintitle"> DIL </span> . Neem nota van het volgende als u <span class="wintitle"> DIL </span> <i> en </i> de dienst van identiteitskaart over veelvoudige plaatsen gebruikt: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Stel voor elke site dezelfde container-id's in op <code> containerNSID </code> en <code> idSyncContainerID </code> . </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Zowel <span class="wintitle"> DIL </span> als de id-service proberen id-syncs naar ons iFrame voor gegevensverzameling te verzenden. De iFrame zorgt er echter voor dat <span class="wintitle"> DIL </span> geen id-sync start. Zo voorkomt u dubbel werk. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Alleen <span class="wintitle"> DIL </span> verzendt gegevens naar een <a href="../../features/destinations/destinations.md"> URL-doel </a> . </li> 
     </ul> </p> <p>Zie ook <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=nl-NL" format="https" scope="external"> idSyncContainerID </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> wordt gebruikt om de volgende twee waarden door te geven: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: ID van gegevenspartner die aan u is toegewezen door <span class="keyword"> Audience Manager </span> . </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Uw unieke id voor een gebruiker. </li> 
    </ul> <p> <p>Belangrijk: gebruik alleen niet-gecodeerde waarden voor uw id's. Bij codering worden dubbelgecodeerde id's gemaakt. </p> </p> <p> <p>Opmerking: als u de <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL" format="https" scope="external"> Adobe Experience Platform Identity Service </a> gebruikt, stelt u de id's van de klant in met de methode <code> setCustomerIDs </code> in plaats van met <span class="wintitle"> DIL </span> . Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=nl-NL" format="https" scope="external"> Klantnamen en verificatiestatus </a> . </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Indien waar (true), worden alle aanvragen (IFRAME, gebeurtenisaanroepen, id-synchronisatie en doel) uitgesteld van uitvoering tot de gebeurtenis <code> Page Load </code> wordt geactiveerd. De standaardwaarde is <code> false </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Standaard false, wat betekent dat <span class="keyword"> Audience Manager </span> een cookie in het domein van de partner instelt (een cookie van de eerste partij instelt). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk: dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik in plaats hiervan de <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=nl-NL" format="https" scope="external"> function </a> in de Adobe Experience Platform Identity Service. </p> </p> <p> Indien <code> true </code> , wordt de IFRAME voor het publiceren van de bestemming niet gekoppeld aan de DOM- of branddoelen. De standaardwaarde is <code> false </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk: dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik in plaats hiervan de <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=nl-NL" format="https" scope="external"> function </a> in de Adobe Experience Platform Identity Service. </p> </p> <p>Schakelt id-synchronisatie uit. U moet ID-syncs uitschakelen bij gebruik van DIL v6.2+ en de Bezoeker-id-service. Deze bewerking wordt uitgevoerd door de functie <code> visitorService </code> (zie de voorbeeldcode hieronder). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Stel in op <code> true </code> om foutmeldingen in te schakelen voor alle <span class="wintitle"> DIL </span> -instanties op de pagina. Werkt alleen met Boolean <code> true </code> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk: dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik in plaats hiervan de <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=nl-NL" format="https" scope="external"> function </a> in de Adobe Experience Platform Identity Service. </p> </p> <p> Hiermee wordt opgegeven of de doelpublicatiesjabloon Akamai moet gebruiken voor HTTPS-verbindingen. Toegelaten op een per-partnerbasis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Koppelt de waarde van het ene sleutelwaardepaar aan een ander. Zie <a href="../../dil/dil-use-cases.md#map-key-values"> Toetswaarden toewijzen aan andere toetsen </a> . Uitgegeven met v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Vereist. </p> <p>Het sleutelwaardepaar <code> namespace </code> bevat uw <span class="keyword"> Experience Cloud </span> -organisatie-id. Als u deze id niet hebt, kunt u deze vinden in de sectie <span class="wintitle"> Beheer </span> van het <span class="keyword"> Experience Cloud </span> -dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie <a href="../../faq/faq-features.md"> Veelgestelde vragen over productfuncties en -functies </a> en <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=nl-NL" format="https" scope="external"> Beheer - Gebruikersbeheer en Veelgestelde vragen </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Vereist. </p> <p> De partnernaam zoals opgegeven door <span class="keyword"> Audience Manager </span> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Hiermee verwijdert u scripts en callbacks. De standaardwaarde is <code> False </code> . Is alleen van toepassing op de huidige <span class="wintitle"> DIL </span> -instantie. Uitgegeven met v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Stelt een cookie in met de unieke gebruikersnaam die door <span class="keyword"> Audience Manager </span> wordt geretourneerd. Zie <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie-eigenschappen </a> . </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Vereist met <span class="wintitle"> DIL </span> 6.2 of hoger. </p> <p> DIL vertrouwt op de <code> setCustomerIDs </code> functie in de <span class="wintitle"> Adobe Experience Platform Identity Service </span> om gedeclareerde id's door te geven aan <span class="keyword"> Audience Manager </span> . Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=nl-NL" format="https" scope="external"> Klantnamen en verificatiestatus </a> voor meer informatie. </p> </td> 
  </tr> 
 </tbody> 
</table>

**Code van de Steekproef**

Een voorbeeldaanroep [!UICONTROL DIL] kan er ongeveer als volgt uitzien:

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

Een geslaagde reactie retourneert de instantie [!UICONTROL DIL] . Een mislukte poging retourneert een foutobject (niet gegenereerd) als de code onjuist is geconfigureerd of als er een fout optreedt.

## uuidCookie-eigenschappen {#uuidcookie-props}

Definieert de eigenschappen die door de variabele `uuidCookie` worden gebruikt. Deze variabele maakt deel uit van de methode `DIL.create` .

`uuidCookie` heeft de volgende eigenschappen:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Naam | Beschrijving |
|---|---|
| `name` | De naam van het cookie ( `aam_did` is standaard). |
| `days` | Het leven van het cookie (100 dagen is gebrek). |
| `path` | Cookie-pad, bijvoorbeeld `'/test'` ( `/` is standaard). |
| `domain` | Het domein waarin de cookie wordt ingesteld, bijvoorbeeld `'adobe.com'` ( `'.'+document.domain` is default). |
| `secure` | Hiermee stelt u een markering in voor het verzenden van gegevens via alleen een HTTPS-verbinding. |

## eigenschappen van bezoekerService {#visitor-service-props}

Definieert de eigenschappen die door de variabele `visitorService` worden gebruikt. Deze variabele maakt deel uit van de methode `DIL.create` .

`visitorService` heeft de volgende eigenschappen:

| Naam | Type | Beschrijving |
|---|---|---|
| `namespace` | String | Vereist. Vertegenwoordigt de Experience Cloud Org ID. Dit is nodig voor de Experience Cloud Core Service-functionaliteit. Dezelfde parameter die wordt gebruikt om de functie Bezoekersidentiteitskaart te instantiëren. |

**Steekproef van de Code:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
