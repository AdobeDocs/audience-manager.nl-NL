---
description: Dit document behandelt de technische details met betrekking tot de naleving van de regels van de gegevensprivacy voor de Manager van het Publiek.
seo-description: Dit document behandelt de technische details met betrekking tot de naleving van de regels van de gegevensprivacy voor de Manager van het Publiek.
seo-title: Gegevensprivacyverzoeken
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Gegevensprivacyverzoeken
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Gegevensprivacyverzoeken {#data-privacy-requests}

## Overzicht {#overview}

Dit document biedt een overzicht van het beheer van de privacy van individuele gegevens en verzoeken om te weigeren die u naar Audience Manager kunt verzenden via de gebruikersinterface [van de](https://privacyui.cloud.adobe.io/) privacydienst en de **[!DNL Privacy Service API]** website.

Met deze gereedschappen kunt u privacyverzoeken voor consumentengegevens verzenden die zijn ingediend in het kader van de GDPR en de CCPA.

Alvorens dit artikel te lezen, adviseren wij het gaan door de Verklarende woordenlijst [van de](../data-security-and-privacy/aam-gdpr-glossary.md) GDPR en de Verklarende woordenlijst [van de](aam-ccpa-glossary.md)CCPA, om de hier gebruikte terminologie beter te begrijpen.

U kunt individuele verzoeken om tot consumentengegevens toegang te hebben en te schrappen van de Manager van het Publiek, op twee manieren voorleggen:

* Via de gebruikersinterface van de [privacyservice](https://privacyui.cloud.adobe.io/). Zie de documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Door de **[!DNL Privacy Service API]**. Zie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_api_tutorial.md) de documentatie en de API-referentie [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Wanneer het verzenden van individuele verzoeken van de gegevensprivacy, kunt u om het even welke herkenningstekens van de Manager van de Audience (IDs) voorleggen, zoals die in de sectie van de Herkenningstekens **[van de Manager van de](data-privacy-ids.md)**Audience, samen met hun respectieve namespace IDs (gegevensbron IDs) worden beschreven.

De [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) ondersteunt twee typen verzoeken: verzoeken om gegevenstoegang en gegevensverwijdering.

## Verzoeken om gegevenstoegang {#access-data}

U kunt individuele verzoeken van de gegevenstoegang door de Dienst UI [van de](https://privacyui.cloud.adobe.io/) Privacy (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) of door [!DNL Privacy Service API] (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) en [!DNL API] verwijzing [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)te roepen) verzenden.

Met de gebruikersinterface [van de](https://privacyui.cloud.adobe.io/) privacyservice kunt u nieuwe taakaanvragen maken door het bestand te gebruiken [!UICONTROL Request Builder] [!DNL JSON] of te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON] bestand eruitziet, kunt u een voorbeeld-JSON [](../data-security-and-privacy/assets/access_request.json)downloaden.

Wij begrijpen dat u zich ertoe verbindt uw verzoeken om privacy van gegevens binnen de in de wetgeving vastgestelde termijn in acht te nemen.

## Verzoeken om gegevens te verwijderen{#delete-data}

U kunt verzoeken om gegevensverwijdering verzenden via de gebruikersinterface [van de](https://privacyui.cloud.adobe.io/) privacyservice ( [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)documentatie) of door de [!DNL Privacy Service API] (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) en API-referentie [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)aan te roepen).

Met de gebruikersinterface [van de](https://privacyui.cloud.adobe.io/) privacyservice kunt u nieuwe taakaanvragen maken door het bestand te gebruiken [!UICONTROL Request Builder] [!DNL JSON] of te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON] bestand eruitziet, kunt u een voorbeeld-JSON [](../data-security-and-privacy/assets/access_request.json)downloaden.

Adobe begrijpt dat u binnen 30 dagen aan uw verzoeken om privacy van gegevens voldoet. Daarom zet Adobe zich ervoor in uw verzoek om gegevens te verwijderen zo snel mogelijk te verwerken.

In antwoord op uw verzoeken van de de gegevensschrapping van de consument, schrapt de Manager van de Publiek eigenschappen en segmenten verbonden aan het herkenningsteken van de Manager van de Publiek inbegrepen in het verzoek. Bovendien, zullen de respectieve herkenningstekens van de Manager van de Publiek voor het individu die uit verdere gegevensinzameling door de Manager van de Publiek wordt verkozen en de respectieve identiteitskaarten van identiteitskaart worden verwijderd.

Wanneer u gedeclareerde id&#39;s verzendt, zoals id&#39; [!DNL CRM] s van verschillende apparaten of cookie-id&#39;s, in privacyverzoeken voor gegevens, wordt de vereiste verwijdering uitgevoerd op alle gekoppelde apparaten (maximaal 100 apparaten per gedeclareerde id).

De Manager van het publiek zal proberen om activeringspartners over schrappingsverzoeken op de hoogte te brengen door hen te verzenden unsegment informatie voor de Onderwerpen van Gegevens die om schrapping van bepaalde gegevens verzoeken. Sommige activeringspartners:

1. Kan unsegment (of segment verwijderen) verzoeken van de Manager van het Publiek niet steunen en/of
2. Kan geen updates ontvangen van Audience Manager met een frequentie van minder dan 30 dagen. In die gevallen, kunnen de klanten van de Manager van de Publiek geen schrappingsverzoeken naar activeringspartners op een geautomatiseerde manier door de Manager van het Publiek verzenden.

In die gevallen, kunt u geen schrappingsverzoeken naar activeringspartners op een geautomatiseerde manier door de Manager van het Publiek verzenden.

Download ons blad [van Excel van de](assets/AAM-Partners-October2019.xlsx) Partner om te zien welke de activeringspartners van de Manager van de Audience unsegment steunen.

## Uitschakelen van verzoeken {#opt-out-requests}

De Manager van het publiek steunt industrie-brede normen met betrekking tot opt-outbeheer. Lees verder voor volledige informatie over de typen opt-out die door Audience Manager worden ondersteund.

Terwijl de verzoeken van de gegevenstoegang en van de schrapping door de Dienst [van de](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html)Privacy worden behandeld, opt-out verzoeken momenteel door DCS API worden gesteund. Lees verder om te leren hoe de opt-out API-aanroepen eruit moeten zien.

### Algemene verzoeken om te weigeren

De wereldwijde opt-out is een opt-out voor Audience Manager en andere Adobe Experience Cloud-oplossingen voor alle merken. In de onderstaande tabel worden de methoden weergegeven die worden gebruikt voor wereldwijde opt-out:

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
   <td colname="col2"> <p>De pagina <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> Uw privacy-keuzen </a> bevat 1-klik functies waarmee uw eindgebruikers gegevens kunnen verzamelen met de Adobe Experience Cloud-advertentieoplossingen (inclusief Audience Manager) en deze kunnen uitschakelen. Specifiek, zie de sectie van de <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external"> bedrijfsklant </a> van de pagina van de Keuzen van de Privacy. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Directe API-aanroepen naar Audience Manager </p> </td> 
   <td colname="col2"> <p>Uw gebruikers kunnen zich van gegevensinzameling door alle merken van de Manager van de Publiek door een vraag aan DCS hieronder API te maken en de Gebruiker van de Manager van de <a href="../../reference/ids-in-aam.md"> Publiek te omvatten - identiteitskaart </a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Dientengevolge, zullen wij plaatsen <code>demdex=NOTARGET</code> en <code>dextp=NOTARGET</code> koekjes voor de voorgelegde Gebruiker van de Manager van de Publiek - identiteitskaart </p> </td> 
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

* Audience Manager beëindigt alle gegevensverzameling, -segmentatie of -activering, zolang de gebruiker de cookies in de browser niet wist.
* Historische gegevens worden na 120 dagen uit het gebruikersprofiel verwijderd.

### Opt-out op partnerniveau met aangegeven id-aanroepen

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke partners van de Manager van het Publiek te sluiten. U kunt partner-vlakke opt-outverzoeken voor dwars-apparaat IDs, met inbegrip van CRM IDs en gehakt e-mailadressen verzenden.

Na een partner-vlakke opt-out met een verklaarde vraag van identiteitskaart:

* De [CRM-id](../../reference/ids-in-aam.md) wordt niet meer verzameld;
* De laatste apparaat-id (unieke gebruikersnaam[van](../../reference/ids-in-aam.md)Audience Manager) die is gekoppeld aan de [CRM-id](../../reference/ids-in-aam.md) , wordt niet meer verzameld.
* Audience Manager beëindigt alle gegevensverzameling, -segmentatie of -activering voor de CRM-id en de laatste apparaat-id die aan de CRM-id is gekoppeld;
* De Manager van het publiek ontsegmenteert opted-out identiteitskaart van CRM en laatste apparatenidentiteitskaart van alle segmenten;
* De partners van de bestemming ontvangen unsegment verzoek om identiteitskaart van CRM en laatste apparatenidentiteitskaart Unsegmentation werkt voor zowel [real time](data-privacy-requests.md#aam-partners-with-unsegmentation) als partijbestemmingen.
* Er worden geen historische gegevens verwijderd.

Wanneer de Manager van het Publiek een partner-vlakke opt-out verzoek ontvangt, bevat JSON die door DCS is teruggekeerd de [foutencode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), met het bericht [!UICONTROL "Encountered opt out tag"], in plaats van de gebruiker identiteitskaart van de Manager van de Publiek.

U kunt een gedeclareerde id-aanvraag voor een opt-out indienen met de paren `d_cid` en `d_cid_ic` sleutelwaarden. De oudere parameters werken `d_dpid` `d_dpuuid` nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

#### Uitschakelen met CID en CID_IC

Zie [URL-variabelen en syntaxis voor gedeclareerde id&#39;s voor een beschrijving en syntaxis](../../features/declared-ids.md#variables-and-syntax).

| Weigeren met | Codevoorbeeld |
|--- |--- |
| A data provider ID and user ID. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Een integratiecode en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Meerdere sleutelwaardeparen d_cid en d_cid_ic. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out op partnerniveau met id-aanroepen van apparaat

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke partners van de Manager van het Publiek te sluiten. U kunt zich afmelden voor gegevensverzameling op een bepaalde apparaat-id voor een merk door de volgende aanroepen uit te voeren naar de [DCS API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Weigeren met | Codevoorbeeld |
|--- |--- |
| Een unieke gebruikersnaam (`uuid`) voor Audience Manager. | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| An Experience Cloud ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Lees meer over `uuid`, `mid` en `imsOrgId` in de [Index van identiteitskaarts in de Manager](/help/using/reference/ids-in-aam.md)van de Publiek.

Na een partner-vlakke opt-out met een vraag van apparaatidentiteitskaart:

* De apparaat-id is uitgeschakeld voor gegevensverzameling.
* De Manager van het publiek zal alle gegevensinzameling, segmentatie of activering, voor de partner ophouden, die voor apparatenidentiteitskaart vooruitgaat.
* De Manager van de publiek maakt apparatenidentiteitskaart van alle segmenten los;
* De partners van de bestemming ontvangen unsegment verzoek om apparatenidentiteitskaart Unsegmentation werkt voor zowel [real time](data-privacy-requests.md#aam-partners-with-unsegmentation) als partijbestemmingen.
* Er worden geen historische gegevens verwijderd.

## De Partners van de Manager van het publiek met unsegmentation mogelijkheden {#aam-partners-with-unsegmentation}

Om u te helpen uw verzoeken van de privacy van consumentengegevens automatiseren, zal de Manager van de Publiek proberen om activeringspartners over schrappingsverzoeken van de Onderwerpen van Gegevens op de hoogte te brengen door hen te verzenden unsegment (of segment) informatie te verwijderen.

Enkele van onze activeringspartners:

1. Kan unsegment verzoeken van de Manager van het Publiek niet steunen en/of
2. Kan updates niet vaker dan eenmaal in 30 dagen ontvangen van Audience Manager.

In die gevallen, kunt u geen schrappingsverzoeken naar activeringspartners op een geautomatiseerde manier door de Manager van het Publiek verzenden.

Raadpleeg de [lijst van op apparaat-gebaseerde bestemmingen](/help/using/features/destinations/device-based-destinations-list.md) om te zien welke de activeringspartners van de Manager van de Audience unsegment steunen.

## Verzoeken om gegevenscorrectie {#correction}

Aangezien Audience Manager niet de bron van de gegevens is, is er een beperkte rol voor gegevenscorrectie in de Manager van het Publiek. De correctie zou kunnen betekenen dat de consument heeft verzocht om hetzij van een onjuist kenmerk/segment te worden uitgesloten, hetzij te worden gekwalificeerd tot het gewenste kenmerk/segment.

De Klanten van de Manager van het publiek kunnen verkiezen om de relevante signalen/traits/segmenten tegen gebruikersprofielen te vangen en deze informatie door [off-line gegevensopname](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) naar de Manager van het Publiek te verzenden. Houd er rekening mee dat de gebruiker gekwalificeerd blijft voor de oorspronkelijke kenmerken en segmenten als deze hun gedrag herhalen.
