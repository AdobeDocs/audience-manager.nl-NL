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
source-wordcount: '878'
ht-degree: 1%

---

# DIL, methode maken{#dil-create}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangemoedigd om te evalueren [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun strategie voor het verzamelen van gegevens op lange termijn.
>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan.

## DIL maken {#dil-create-new}

Creeert partner-specifiek [!UICONTROL DIL] -instantie.

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
   <td colname="col3"> <p>Met deze eigenschap wordt de container-id ingesteld die door <span class="keyword"> Audience Manager </span> voor ID-syncs. U kunt instellen <code> containerNSID </code> als u <span class="wintitle"> DIL </span> opgesteld over veelvoudige plaatsen. Elk van deze sites heeft een eigen container-id en id-syncs. Als u slechts 1 site hebt, is de container-id standaard 0 en hoeft u dit niet op de juiste wijze in te stellen. Neem contact op met uw consultant voor een lijst met uw sites en de bijbehorende container-id's. </p> <p>In de <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, de eigenschap <code> idSyncContainerID </code> komt overeen met <code> containerNSID </code> in <span class="wintitle"> DIL </span>. Let op het volgende als u werkt <span class="wintitle"> DIL </span> <i>en</i> de dienst van identiteitskaart over veelvoudige plaatsen: </p> <p> 
     <ul id="ul_FF17004C21FC408BB8C8CCE670E45F37"> 
      <li id="li_FFB23BB3CD224678B0A1CF3731F6A206">Stel voor elke site dezelfde container-id's in op <code> containerNSID </code> en <code> idSyncContainerID </code>. </li> 
      <li id="li_CC932D3A0D154F6C9566EF31260A14CF">Beide <span class="wintitle"> DIL </span> en de id-service probeert id-syncs naar ons iFrame voor gegevensverzameling te verzenden. De iFrame zorgt er echter voor dat <span class="wintitle"> DIL </span> geen id-sync starten. Zo voorkomt u dubbel werk. </li> 
      <li id="li_0A909AD26DE94EAA960DC1374C7AF89F">Alleen <span class="wintitle"> DIL </span> gegevens verzenden naar een <a href="../../features/destinations/destinations.md"> URL-doel </a>. </li> 
     </ul> </p> <p>Zie ook: <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncontainerid.html?lang=nl-NL" format="https" scope="external"> idSyncContainerID </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> declaredId </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> 
    <p> <code> declaredId </code> wordt gebruikt voor het passeren van: </p> 
    <ul id="ul_75E64D7DDBD14670BB0BC7819F72036C"> 
     <li id="li_43C7F0EAC5B24F07BBF4ADAB4B0142B7"> <code> dpid </code>: Identiteitskaart van de partner van Gegevens die aan u door wordt toegewezen <span class="keyword"> Audience Manager </span>. </li> 
     <li id="li_3BD52ADEA1E24B41B51AFA95D71DD1FC"> <code> dpuuid </code>: Je unieke id voor een gebruiker. </li> 
    </ul> <p> <p>Belangrijk: gebruik alleen niet-gecodeerde waarden voor uw id's. Bij codering worden dubbelgecodeerde id's gemaakt. </p> </p> <p> <p>Opmerking: als u de <a href="https://experienceleague.adobe.com/docs/id-service/using/home.html?lang=nl-NL" format="https" scope="external"> Adobe Experience Platform Identity Service </a>, klant-id's instellen met de <code> setCustomerIDs </code> methode in plaats van <span class="wintitle"> DIL </span>. Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=nl-NL" format="https" scope="external"> Klant-id's en verificatiestatus </a>. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> delayAllUntilWindowLoad </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Indien waar (true), worden alle aanvragen (IFRAME, gebeurtenisaanroepen, id-synchronisatie en bestemming) uitgesteld van uitvoering tot de <code> Page Load </code> gebeurtenis wordt geactiveerd. Standaard is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDeclaredUUIDCookie </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Standaard false, wat betekent <span class="keyword"> Audience Manager </span> plaatst een koekje in het domein van de partner (plaatst een eerste partijkoekje). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableDestinationPublishingIframe </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk: dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik de <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=nl-NL" format="https" scope="external"> function </a> in plaats daarvan in de Adobe Experience Platform Identity Service. </p> </p> <p> Indien <code> true </code>, zal IFRAME voor het publiceren van de bestemming niet aan de DOM- of branddoelen koppelen. Standaard is <code> false </code>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> disableIDSyncs </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk: dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik de <code> visitor.disableIdSyncs </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/disableidsync.html?lang=nl-NL" format="https" scope="external"> function </a> in plaats daarvan in de Adobe Experience Platform Identity Service. </p> </p> <p>Schakelt id-synchronisatie uit. U moet de syncs van identiteitskaart onbruikbaar maken wanneer het gebruiken van DIL v6.2+ en de Dienst van identiteitskaart van de Bezoeker. De <code> visitorService </code> Deze bewerking wordt uitgevoerd door een functie (zie de voorbeeldcode hieronder). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> enableErrorReporting </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Instellen op <code> true </code> om foutenrapportering voor allen toe te laten <span class="wintitle"> DIL </span> op de pagina. Werken met Boolean <code> true </code> alleen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> iframeAkamaiHTTPS </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> <p>Belangrijk: dit element is vervangen door <span class="wintitle"> DIL </span> versie 8.0 (uitgebracht in augustus 2018). Gebruik de <code> visitor.idSyncSSLUseAkamai </code> <a href="https://experienceleague.adobe.com/docs/id-service/using/id-service-api/configurations/idsyncssluseakamai.html?lang=nl-NL" format="https" scope="external"> function </a> in plaats daarvan in de Adobe Experience Platform Identity Service. </p> </p> <p> Hiermee wordt opgegeven of de doelpublicatiesjabloon Akamai moet gebruiken voor HTTPS-verbindingen. Toegelaten op een per-partnerbasis. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> mappings </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Koppelt de waarde van het ene sleutelwaardepaar aan een ander. Zie <a href="../../dil/dil-use-cases.md#map-key-values"> Sleutelwaarden toewijzen aan andere toetsen </a>. Uitgegeven met v2.4. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> namespace </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Vereist. </p> <p>De <code> namespace </code> sleutelwaardepaar bevat uw <span class="keyword"> Experience Cloud </span> Organisatie-id. Als u deze id niet hebt, kunt u deze vinden in het dialoogvenster <span class="wintitle"> Administratie </span> van de <span class="keyword"> Experience Cloud </span> dashboard. U hebt beheerdersmachtigingen nodig om dit dashboard weer te geven. Zie de <a href="../../faq/faq-features.md"> Veelgestelde vragen over productfuncties </a> en <a href="https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/faq.html?lang=nl-NL" format="https" scope="external"> Beheer - Gebruikersbeheer en veelgestelde vragen </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> partner </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Vereist. </p> <p> De naam van de partner zoals verstrekt door <span class="keyword"> Audience Manager </span>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> removeFinishedScriptsAndCallbacks </code> </p> </td> 
   <td colname="col2"> <p>Boolean </p> </td> 
   <td colname="col3"> <p> Hiermee verwijdert u scripts en callbacks. Standaard is <code> False </code>. Is van toepassing op de huidige <span class="wintitle"> DIL </span> alleen instantie. Uitgegeven met v3.3. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> uuidCookie </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Hiermee wordt een cookie ingesteld met de unieke gebruikers-id die wordt geretourneerd door <span class="keyword"> Audience Manager </span>. Zie <a href="../../dil/dil-class-overview/dil-create.md#uuidcookie-props"> uuidCookie-eigenschappen </a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> visitorService </code> </p> </td> 
   <td colname="col2"> <p>Object </p> </td> 
   <td colname="col3"> <p>Vereist met <span class="wintitle"> DIL </span> 6.2 of hoger. </p> <p> DIL is afhankelijk van de <code> setCustomerIDs </code> in de <span class="wintitle"> Adobe Experience Platform Identity Service </span> gedeclareerde id's doorgeven in <span class="keyword"> Audience Manager </span>. Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/reference/authenticated-state.html?lang=nl-NL" format="https" scope="external"> Klant-id's en verificatiestatus </a> voor meer informatie . </p> </td> 
  </tr> 
 </tbody> 
</table>

**Voorbeeldcode**

Een monster [!UICONTROL DIL] De vraag zou gelijkaardig aan het volgende kunnen kijken:

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

Als de reactie succesvol was, worden de [!UICONTROL DIL] -instantie. Een mislukte poging retourneert een foutobject (niet gegenereerd) als de code onjuist is geconfigureerd of als er een fout optreedt.

## uuidCookie-eigenschappen {#uuidcookie-props}

Definieert de eigenschappen die worden gebruikt door de `uuidCookie` variabele. Deze variabele maakt deel uit van de `DIL.create` methode.

`uuidCookie` heeft de volgende eigenschappen:

<!-- 

r_dil_uuid_cookie.xml

 -->

| Naam | Beschrijving |
|---|---|
| `name` | De cookienaam ( `aam_did` is standaard). |
| `days` | Het leven van het cookie (100 dagen is gebrek). |
| `path` | Cookie-pad, bijvoorbeeld `'/test'` ( `/` is standaard). |
| `domain` | Het domein waarin de cookie is ingesteld, bijvoorbeeld: `'adobe.com'` ( `'.'+document.domain` is standaard). |
| `secure` | Hiermee stelt u een markering in voor het verzenden van gegevens via alleen een HTTPS-verbinding. |

## eigenschappen van bezoekerService {#visitor-service-props}

Definieert de eigenschappen die worden gebruikt door de `visitorService` variabele. Deze variabele maakt deel uit van de `DIL.create` methode.

`visitorService` heeft de volgende eigenschappen:

| Naam | Type | Beschrijving |
|---|---|---|
| `namespace` | String | Vereist. Vertegenwoordigt de Experience Cloud Org-id. Dit is nodig voor de functionaliteit van de Experience Cloud Core-service. Dezelfde parameter die wordt gebruikt om de functie Bezoekersidentiteitskaart te instantiëren. |

**Codevoorbeeld:**

```
var vDil = DIL.create({ 
    partner: 'demofirst', 
    visitorService: { 
        namespace: "INSERT-EXPCLOUD-ORG-ID-HERE" 
    } 
});
```
