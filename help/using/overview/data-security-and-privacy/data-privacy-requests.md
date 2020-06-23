---
description: In dit document worden de technische details besproken die verband houden met de naleving van de regelgeving inzake privacy van gegevens voor Audience Manager.
seo-description: In dit document worden de technische details besproken die verband houden met de naleving van de regelgeving inzake privacy van gegevens voor Audience Manager.
seo-title: Gegevensprivacyverzoeken
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Gegevensprivacyverzoeken
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 9a8c0650d3f00a95a8a1f05c248c21b420e727e0
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 0%

---


# Gegevensprivacyverzoeken {#data-privacy-requests}

## Overzicht {#overview}

Dit document biedt een overzicht van het beheer van de privacy van individuele gegevens en verzoeken om te weigeren die u kunt verzenden [!DNL Audience Manager] via de gebruikersinterface [van de](https://privacyui.cloud.adobe.io/) Privacy Service en de **[!DNL Privacy Service API]** gebruikersinterface.

Met deze gereedschappen kunt u privacyverzoeken voor consumentengegevens verzenden die onder [!DNL GDPR] en [!DNL CCPA].

Alvorens dit artikel te lezen, adviseren wij het gaan door de Verklarende woordenlijst [van de](../data-security-and-privacy/aam-gdpr-glossary.md) GDPR en de Verklarende woordenlijst [van de](aam-ccpa-glossary.md)CCPA, om de hier gebruikte terminologie beter te begrijpen.

U kunt individuele verzoeken om toegang tot en verwijdering van consumentengegevens op twee manieren verzenden [!DNL Audience Manager]:

* Via de [Privacy Service-interface](https://privacyui.cloud.adobe.io/). Zie de documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Door de **[!DNL Privacy Service API]**. Zie de documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) en de [!DNL API] verwijzing [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Wanneer u individuele verzoeken om gegevensprivacy verzendt, kunt u om het even welke [!DNL Audience Manager] herkenningstekens (IDs), zoals die in de sectie van Herkenningstekens **[van de](data-privacy-ids.md)**Audience Manager worden beschreven, samen met hun respectieve namespace IDs (gegevensbron IDs) voorleggen.

De [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) steunt twee soorten verzoeken: verzoeken om gegevenstoegang en gegevensverwijdering.

## Verzoeken om gegevenstoegang {#access-data}

U kunt individuele verzoeken van de gegevenstoegang door de [Privacy Service UI](https://privacyui.cloud.adobe.io/) (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) of door [!DNL Privacy Service API] (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) en [!DNL API] verwijzing [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)te roepen) verzenden.

Met de [Privacy Service-interface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken door de [!UICONTROL Request Builder] methode te gebruiken of door een [!DNL JSON] bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON] bestand eruitziet, kunt u een voorbeeld-JSON [](../data-security-and-privacy/assets/access_request.json)downloaden.

Wij begrijpen dat u zich ertoe verbindt uw verzoeken om privacy van gegevens binnen de in de wetgeving vastgestelde termijn in acht te nemen.

## Verzoeken om gegevens te verwijderen {#delete-data}

U kunt verzoeken om gegevensverwijdering verzenden via de [Privacy Service-interface](https://privacyui.cloud.adobe.io/) (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) of door de [!DNL Privacy Service API] (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) en [!DNL API] referentie [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) aan te roepen.

Met de [Privacy Service-interface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken door de [!UICONTROL Request Builder] methode te gebruiken of door een [!DNL JSON] bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON] bestand eruitziet, kunt u een voorbeeld-JSON [](../data-security-and-privacy/assets/access_request.json)downloaden.

Adobe begrijpt dat u binnen 30 dagen aan uw verzoeken om privacy van gegevens voldoet. Daarom [!DNL Adobe] wil ik graag uw verzoek om gegevens te verwijderen zo snel mogelijk verwerken.

In antwoord op uw verzoeken om gegevens van de consument te schrappen, [!DNL Audience Manager] schrapt eigenschappen en segmenten verbonden aan het [!DNL Audience Manager] herkenningsteken inbegrepen in het verzoek. Bovendien worden de respectieve [!DNL Audience Manager] id-identificatoren voor de persoon die door [!DNL Audience Manager] en door de respectievelijke id-toewijzingen uit verdere gegevensverzameling is gekozen, verwijderd.

Wanneer u gedeclareerde id&#39;s verzendt, zoals id&#39; [!DNL CRM] s van verschillende apparaten of id&#39; [!DNL cookie] s, in privacyverzoeken voor gegevens, [!DNL Audience Manager] wordt de vereiste verwijdering uitgevoerd op alle gekoppelde apparaten (maximaal 100 apparaten per gedeclareerde id).

[!DNL Audience Manager] zal proberen activeringspartners over schrappingsverzoeken op de hoogte te brengen door hen te verzenden unsegment informatie voor Subjects van Gegevens die om schrapping van bepaalde gegevens verzoeken. Sommige activeringspartners:

1. Kan segment-aanvragen (of segment-aanvragen verwijderen uit [!DNL Audience Manager] en/of niet ondersteunen
2. Kan geen updates ontvangen van [!DNL Audience Manager] met een frequentie van minder dan 30 dagen. In die gevallen, kunnen de [!DNL Audience Manager] klanten schrappingsverzoeken aan activeringspartners niet op een geautomatiseerde manier door verzenden [!DNL Audience Manager].

In die gevallen kunt u geen verwijderingsverzoeken automatisch naar activeringspartners verzenden [!DNL Audience Manager].

Download ons blad [van Excel van de](assets/AAM-Partners-October2019.xlsx) Partner om te zien welke [!DNL Audience Manager] activeringspartners unsegment steunen.

## Uitschakelen van verzoeken {#opt-out-requests}

[!DNL Audience Manager] ondersteunt normen voor het beheer van opt-out voor de hele branche. Lees verder voor volledige informatie over de typen opt-out die worden ondersteund door [!DNL Audience Manager].

Terwijl de verzoeken van de gegevenstoegang en van de schrapping door de [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)worden behandeld, worden de opt-outverzoeken momenteel gesteund door [!DNL DCS API]. Lees verder om te leren hoe de opt-out- [!DNL API] aanroepen eruit moeten zien.

### Algemene verzoeken om te weigeren

De wereldwijde opt-out is een opt-out voor alle merken [!DNL Audience Manager] en andere [!DNL Adobe Experience Cloud] oplossingen. De onderstaande tabel geeft een overzicht van de methoden die worden gebruikt voor wereldwijde opt-out:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Weigeren voor </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>De pagina <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Uw privacy-keuzen </a> bevat 1-klik functies waarmee uw eindgebruikers gegevens kunnen verzamelen met de Adobe Experience Cloud-advertentieoplossingen (waaronder Audience Manager) en deze kunnen uitschakelen. Specifiek, zie de sectie van de <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> bedrijfsklant </a> van de pagina van de Keuzen van de Privacy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Directe API-aanroepen naar Audience Manager </p> </td> 
   <td colname="col2"> <p>Uw gebruikers kunnen zich van gegevensinzameling door alle merken van de Audience Manager door een vraag aan DCS API hieronder te maken en de identiteitskaart van de Gebruiker van de <a href="../../reference/ids-in-aam.md"> Audience Manager te omvatten </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Daarom zullen we cookies instellen <code>demdex=NOTARGET</code> en <code>dextp=NOTARGET</code> opslaan voor de verzonden gebruikersnaam van de Audience Manager. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobiele apparaten </p> </td> 
   <td colname="col2"> <p>Zie de instellingen voor opt-out en privacy voor: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-apparaten </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-apparaten </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Uw eindgebruikers kunnen zich ook afmelden voor wereldwijde gegevensverzameling door de websites van onze partners in industriestandaarden te bezoeken.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Na de hierboven beschreven opt-out-verzoeken:

* [!DNL Audience Manager] stopt alle gegevensverzameling, segmentatie of activering, zolang de gebruiker de cookies in de browser niet wist.
* Historische gegevens worden na 120 dagen uit het gebruikersprofiel verwijderd.

### Opt-out op partnerniveau met aangegeven id-aanroepen

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke [!DNL Audience Manager] partners te sluiten. U kunt de partner-vlakke opt-outverzoeken voor dwars-apparaat IDs, met inbegrip van identiteitskaart&#39; [!DNL CRM] s en gehakt e-mailadressen verzenden.

Na een partner-vlakke opt-out met een verklaarde vraag van identiteitskaart:

* De [CRM-id](../../reference/ids-in-aam.md) wordt niet meer verzameld;
* De laatste apparaat-id (unieke gebruikersnaam[van](../../reference/ids-in-aam.md)Audience Manager) die is gekoppeld aan de [CRM-id](../../reference/ids-in-aam.md) , wordt niet meer verzameld.
* [!DNL Audience Manager] alle gegevensverzameling, segmentatie of activering van de [!DNL CRM] id en de laatste apparaat-id die aan de [!DNL CRM] id is gekoppeld, stopzetten;
* [!DNL Audience Manager] ontsegmenteert opted-out [!DNL CRM] identiteitskaart en laatste apparatenidentiteitskaart van alle segmenten;
* [!UICONTROL Destination] de partners ontvangen unsegment verzoek om identiteitskaart en [!DNL CRM] laatste apparatenidentiteitskaart Unsegmentation werkt voor zowel [real time](data-privacy-requests.md#aam-partners-with-unsegmentation) als partijbestemmingen.
* Er worden geen historische gegevens verwijderd.

Wanneer [!DNL Audience Manager] een partner-vlakke opt-out verzoek ontvangt, bevat [!DNL JSON] teruggekeerd door [!DNL DCS] de [foutencode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), met het bericht [!UICONTROL "Encountered opt out tag"], in plaats van [!DNL Audience Manager] gebruiker - identiteitskaart

U kunt een gedeclareerde id-aanvraag voor een opt-out indienen met de paren `d_cid` en `d_cid_ic` sleutelwaarden. De oudere parameters werken `d_dpid` `d_dpuuid` nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

#### Weigeren met [!DNL CID] en [!DNL CID_IC]

Zie [URL-variabelen en syntaxis voor gedeclareerde id&#39;s voor een beschrijving en syntaxis](../../features/declared-ids.md#variables-and-syntax).

| Weigeren met | Codevoorbeeld |
|--- |--- |
| A data provider ID and user ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Een integratiecode en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Meerdere `d_cid` en `d_cid_ic` sleutelwaardeparen. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out op partnerniveau met id-aanroepen van apparaat

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke [!DNL Audience Manager] partners te sluiten. U kunt zich afmelden voor gegevensverzameling op een bepaalde apparaat-id voor een merk door de volgende aanroepen uit te voeren naar de [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Weigeren met | Codevoorbeeld |
|--- |--- |
| An [!DNL Audience Manager] ( [!DNL Unique User ID]`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Een [!DNL Experience Cloud] id (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Lees meer over `uuid`, `mid` en `imsOrgId` in de [Index van IDs in Audience Manager](/help/using/reference/ids-in-aam.md).

Na een partner-vlakke opt-out met een vraag van apparaatidentiteitskaart:

* De apparaat-id is uitgeschakeld voor gegevensverzameling.
* [!DNL Audience Manager] zal alle gegevensinzameling, segmentatie of activering, voor de partner ophouden, die voor apparatenidentiteitskaart vooruitgaat.
* [!DNL Audience Manager] ontsegmenteert apparatenidentiteitskaart van alle segmenten;
* De partners van de bestemming ontvangen unsegment verzoek om apparatenidentiteitskaart Unsegmentation werkt voor zowel [real time](data-privacy-requests.md#aam-partners-with-unsegmentation) als partijbestemmingen.
* Er worden geen historische gegevens verwijderd.

## [!DNL Audience Manager] Partners met onsegmenteringsmogelijkheden {#aam-partners-with-unsegmentation}

Om u te helpen uw verzoeken van de privacy van consumentengegevens automatiseren, [!DNL Audience Manager] zal proberen om activeringspartners op de hoogte te brengen over schrappingsverzoeken van de Onderwerpen van Gegevens door hen te verzenden unsegment (of segment) informatie te verwijderen.

Enkele van onze activeringspartners:

1. Kan unsegment verzoeken van [!DNL Audience Manager] en/of niet steunen
2. Kan geen updates ontvangen van [!DNL Audience Manager] vaker dan eenmaal in 30 dagen.

In die gevallen kunt u geen verwijderingsverzoeken automatisch naar activeringspartners verzenden [!DNL Audience Manager].

Raadpleeg de [lijst van op apparaat-gebaseerde bestemmingen](/help/using/features/destinations/device-based-destinations-list.md) om te zien welke [!DNL Audience Manager] activeringspartners unsegment steunen.

## Verzoeken om gegevenscorrectie {#correction}

Aangezien [!DNL Audience Manager] dit niet de bron van de gegevens is, is er een beperkte rol voor gegevenscorrectie in [!DNL Audience Manager]. De correctie zou kunnen betekenen dat de consument heeft verzocht niet-gekwalificeerd te zijn voor een onjuiste [!UICONTROL trait]/[!UICONTROL segment] of gekwalificeerd te zijn voor de gewenste [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] klanten kunnen de relevante signalen/traits/segmenten tegen gebruikersprofielen vangen en deze informatie door [off-line gegevensopname](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) naar [!DNL Audience Manager]. verzenden De gebruiker blijft gekwalificeerd voor het origineel [!UICONTROL trait] en [!UICONTROL segments] als hij of zij zijn of haar gedrag herhaalt.
