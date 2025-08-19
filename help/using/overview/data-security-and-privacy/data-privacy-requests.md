---
description: In dit document worden de technische details van de naleving van Audience Manager Data Privacy-voorschriften besproken.
seo-description: This document covers the technicalities related to data privacy regulations compliance for Audience Manager.
seo-title: Data Privacy Requests
solution: Audience Manager
keywords: GDPR-gebruikersinterface, GDPR-API, CCPA, privacy
title: Data Privacy-aanvragen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
source-git-commit: 6b43885deddb0cdaeb3698051ea110f0a4eed44e
workflow-type: tm+mt
source-wordcount: '1324'
ht-degree: 42%

---

# Data Privacy-aanvragen {#data-privacy-requests}

## Overzicht {#overview}

Dit document verstrekt een overzicht van het beheren van individuele gegevensprivacy en opt-out verzoeken die u naar [!DNL Audience Manager] door [ Privacy Service UI ](https://privacyui.cloud.adobe.io/) en **[!DNL Privacy Service API]** kunt verzenden.

Met deze gereedschappen kunt u privacyverzoeken voor consumentengegevens verzenden die zijn ingediend onder [!DNL GDPR] en [!DNL CCPA] .

We adviseren u om voor het lezen van het artikel de [Verklarende woordenlijst GDPR (AVG)](../data-security-and-privacy/aam-gdpr-glossary.md) en de [Verklarende woordenlijst CCPA](aam-ccpa-glossary.md) door te nemen voor een beter begrip van de hier gebruikte terminologie.

U kunt op twee manieren individuele verzoeken verzenden om consumentengegevens vanuit [!DNL Audience Manager] te openen en te verwijderen:

* Via de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/). Zie de documentatie [hier](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Via de **[!DNL Privacy Service API]**. Zie hier de documentatie [&#128279;](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) en [!DNL API] verwijzing [&#128279;](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

Wanneer het verzenden van individuele verzoeken van de gegevensprivacy, kunt u om het even welke [!DNL Audience Manager] herkenningstekens (IDs) voorleggen, zoals die in de **[2&rbrace; sectie van de Herkenningstekens van Audience Manager wordt beschreven, samen met hun respectieve namespace IDs (gegevensbron IDs).](data-privacy-ids.md)**

De [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) ondersteunt twee typen aanvragen: aanvragen voor datatoegang en aanvragen voor dataverwijdering.

## Verzoeken om gegevenstoegang {#access-data}

U kunt individuele verzoeken van de gegevenstoegang door [ Privacy Service UI ](https://privacyui.cloud.adobe.io) verzenden (documentatie [ hier ](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) of door Privacy Service API te roepen (documentatie [ hier ](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) en [!DNL API] verwijzing [&#128279;](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

Met de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken met de [!UICONTROL Request Builder] of door een [!DNL JSON]-bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON]-bestand eruitziet, kunt u een [ voorbeeld-JSON downloaden](../data-security-and-privacy/assets/access_request.json).

We begrijpen dat u streeft naar de honorering van uw Data Privacy-aanvragen binnen de tijdsperiode die wettelijk is vastgesteld.

## Verzoeken om gegevens te verwijderen {#delete-data}

U kunt verzoeken van de gegevensschrapping door [ Privacy Service UI ](https://privacyui.cloud.adobe.io) (documentatie [ hier ](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) of door Privacy Service API te roepen (documentatie [ hier ](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) en [!DNL API] verwijzing [&#128279;](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

Met de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken met de [!UICONTROL Request Builder] of door een [!DNL JSON]-bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON]-bestand eruitziet, kunt u een [ voorbeeld-JSON downloaden](../data-security-and-privacy/assets/access_request.json).

Adobe begrijpt uw streven om binnen 30 dagen te voldoen aan de Data Privacy-aanvragen van uw consumenten. Daarom heeft [!DNL Adobe] zich ertoe verbonden uw verzoek om gegevens te verwijderen zo snel mogelijk te verwerken.

Als reactie op uw verzoeken om gegevens te verwijderen voor consumenten, verwijdert [!DNL Audience Manager] de kenmerken en segmenten die zijn gekoppeld aan de [!DNL Audience Manager] -id die in de aanvraag is opgenomen. Daarnaast worden de respectievelijke [!DNL Audience Manager] -id&#39;s voor de persoon die door [!DNL Audience Manager] is uitgekozen voor verdere gegevensverzameling, verwijderd en de respectievelijke id-toewijzingen.

Wanneer u gedeclareerde id&#39;s verzendt, zoals cross-device [!DNL CRM] id&#39;s of [!DNL cookie] id&#39;s, in privacyverzoeken voor gegevens, voert [!DNL Audience Manager] de vereiste verwijdering uit op alle gekoppelde apparaten (maximaal 100 apparaten per gedeclareerde id).

[!DNL Audience Manager] probeert activeringspartners op de hoogte te stellen van verwijderingsverzoeken door ze ongesegmenteerde informatie te sturen voor betrokkenen met gegevens die verwijdering van bepaalde gegevens vragen. Voor sommige activeringspartners geldt echter het volgende:

1. Kan geen ondersteuning bieden voor segmentaanvragen (of segment verwijderen) uit [!DNL Audience Manager] en/of
2. Kan geen updates ontvangen van [!DNL Audience Manager] met een frequentie van minder dan 30 dagen. In die gevallen kunnen [!DNL Audience Manager] -klanten geen verwijderingsaanvragen automatisch via [!DNL Audience Manager] naar activeringspartners verzenden.

In die gevallen kunt u geen verwijderingsverzoeken automatisch via [!DNL Audience Manager] naar activeringspartners verzenden.

Verwijs naar onze [ op apparaat-gebaseerde documentatie van de bestemmingslijst ](assets/AAM-Partners-October2019.xlsx) om te zien welke [!DNL Audience Manager] activeringspartners unsegment steunen.

## Uitschakelen van verzoeken {#opt-out-requests}

[!DNL Audience Manager] ondersteunt industriestandaarden op het gebied van opt-outbeheer. Lees verder voor volledige informatie over de typen opt-out die worden ondersteund door [!DNL Audience Manager] .

Terwijl de de gegevenstoegang en schrappingsverzoeken door [ Privacy Service ](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) worden behandeld, worden de opt-out verzoeken momenteel gesteund door [!DNL DCS API]. Lees verder om te zien hoe de opt-out [!DNL API] -aanroepen eruit moeten zien.

### Algemene opt-outaanvragen

De wereldwijde opt-out staat voor een opt-out voor [!DNL Audience Manager] en andere [!DNL Adobe Experience Cloud] -oplossingen voor alle merken. De onderstaande tabel geeft een overzicht van de methoden die worden gebruikt voor globale opt-out:

<table id="table_F1027B9633E948DCBB11C141B381682A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Opt-out voor </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Adobe Experience Cloud </p> </td> 
   <td colname="col2"> <p>De pagina <a href="https://www.adobe.com/nl/privacy/opt-out.html#customeruse" format="http" scope="external">Uw privacyopties</a> bevat 1-klikfuncties waarmee uw eindgebruikers de verzameling van hun data door de Adobe Experience Cloud-advertentieoplossingen (inclusief Audience Manager) kunnen beheren en uitschakelen. Zie met name de <a href="https://www.adobe.com/nl/privacy/opt-out.html#customeruse" format="http" scope="external">sectie voor zakelijke klanten</a> van de pagina voor privacyopties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Directe API-calls naar Audience Manager </p> </td> 
   <td colname="col2"> <p>Uw gebruikers kunnen zich afmelden voor dataverzameling door alle Audience Manager-merken door een call naar de onderstaande DCS-API inclusief de <a href="../../reference/ids-in-aam.md">Audience Manager-gebruikers-id</a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Daardoor zullen wij <code>demdex=NOTARGET</code>- en <code>dextp=NOTARGET</code>-cookies plaatsen voor de verzonden Audience Manager-gebruikers-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobiele apparaten </p> </td> 
   <td colname="col2"> <p>Zie de instellingen voor opt-out en privacy voor: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-apparaten </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-apparaten </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Uw eindgebruikers kunnen zich ook afmelden voor wereldwijde dataverzameling door websites te bezoeken van onze industriestandaardpartners.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Na de hierboven beschreven opt-outaanvragen:

* [!DNL Audience Manager] beëindigt alle gegevensverzameling, -segmentatie of -activering, zolang de gebruiker de cookies in de browser niet wist.
* Historische data worden na 120 dagen uit het gebruikersprofiel verwijderd.

### Opt-out op partnerniveau met gedeclareerde id-calls

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke [!DNL Audience Manager] partners te sluiten. U kunt op partnerniveau een verzoek indienen om te weigeren voor id&#39;s op andere apparaten, inclusief [!DNL CRM] ID&#39;s en gehashte e-mailadressen.

Na een opt-out op partnerniveau met een gedeclareerde id-call gebeurt het volgende:

* De [CRM-id](../../reference/ids-in-aam.md) wordt niet meer verzameld;
* De laatste apparaat-id ([unieke Audience Manager-gebruikers-id](../../reference/ids-in-aam.md)) die is gekoppeld aan de [CRM-id](../../reference/ids-in-aam.md) is afgemeld voor dataverzameling.
* [!DNL Audience Manager] beëindigt alle gegevensverzameling, segmentatie of activering die wordt uitgevoerd voor de [!DNL CRM] ID en de laatste apparaat-id die aan de [!DNL CRM] ID zijn gekoppeld;
* [!DNL Audience Manager] ontleedt de opted-out [!DNL CRM] ID en laatste apparatenidentiteitskaart van alle segmenten;
* [!UICONTROL Destination] -partners ontvangen de aanvraag voor het ongedaan maken van het segment voor de [!DNL CRM] ID en laatste apparaat-id. Desegmentatie werkt voor zowel [realtime](data-privacy-requests.md#aam-partners-with-unsegmentation)- als batchbestemmingen.
* Er worden geen historische data verwijderd.

Wanneer [!DNL Audience Manager] een partner-vlakke opt-out verzoek ontvangt, [!DNL JSON] door [!DNL DCS] is teruggekeerd bevat [ foutencode 171 ](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), met het bericht [!UICONTROL "Encountered opt out tag"], in plaats van [!DNL Audience Manager] gebruiker - identiteitskaart

U kunt een aanvraag voor opt-out van een gedeclareerde id aanvragen met de sleutelwaardeparen `d_cid` en `d_cid_ic`. De oude parameters zoals `d_dpid` en `d_dpuuid` werken nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

#### Uitschakelen met [!DNL CID] en [!DNL CID_IC]

Zie [URL-variabelen en syntaxis voor gedeclareerde id’s](../../features/declared-ids.md#variables-and-syntax) voor een beschrijving en syntaxis.

| Opt-out met | Codevoorbeeld |
|--- |--- |
| Een dataprovider-id en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Een integratiecode en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Meerdere `d_cid` en `d_cid_ic` sleutelwaardeparen. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out op partnerniveau met apparaat-id-calls

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke [!DNL Audience Manager] partners te sluiten. U kunt zich afmelden voor dataverzameling van een bepaalde apparaat-id voor een merk door de volgende calls uit te voeren naar de [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Opt-out met | Codevoorbeeld |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Een [!DNL Experience Cloud] id (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Lees meer over `uuid`, `mid` en `imsOrgId` in de [Index van id’s in Audience Manager](/help/using/reference/ids-in-aam.md).

Na een opt-out op partnerniveau met een apparaat-id-call gebeurt het volgende:

* De apparaat-id is uitgeschakeld voor dataverzameling.
* [!DNL Audience Manager] beëindigt alle gegevensinzameling, segmentatie of activering, voor de partner, die voor apparatenidentiteitskaart verdergaat
* [!DNL Audience Manager] maakt de apparaat-id los van alle segmenten.
* Bestemmingspartners ontvangen de desegmentatieaanvraag voor de apparaat-id. Desegmentatie werkt voor zowel [realtime](data-privacy-requests.md#aam-partners-with-unsegmentation)- als batchbestemmingen.
* Er worden geen historische data verwijderd.

## [!DNL Audience Manager] Partners met onsegmenteringsmogelijkheden {#aam-partners-with-unsegmentation}

Om u te helpen uw verzoeken van de privacy van consumentengegevens automatiseren, [!DNL Audience Manager] zal proberen om activeringspartners op de hoogte te brengen over schrappingsverzoeken van de Onderwerpen van Gegevens door hen te verzenden unsegment (of segment) informatie te verwijderen.

Voor een aantal van onze activeringspartners geldt echter het volgende:

1. Kan geen ondersteuning bieden voor ongesegmenteerde aanvragen van [!DNL Audience Manager] en/of
2. Kan geen updates ontvangen van [!DNL Audience Manager] vaker dan eenmaal in 30 dagen.

In die gevallen kunt u geen verwijderingsverzoeken automatisch via [!DNL Audience Manager] naar activeringspartners verzenden.

Raadpleeg de [ lijst van op apparaat-gebaseerde bestemmingen ](/help/using/features/destinations/device-based-destinations-list.md) om te zien welke [!DNL Audience Manager] activeringspartners unsegment steunen.

## Verzoeken om gegevenscorrectie {#correction}

Aangezien [!DNL Audience Manager] niet de bron van de gegevens is, is er een beperkte rol voor gegevenscorrectie in [!DNL Audience Manager]. De correctie kan betekenen dat de consument heeft verzocht om niet-gekwalificeerd te zijn voor een onjuiste [!UICONTROL trait]/ [!UICONTROL segment] of te zijn gekwalificeerd voor de gewenste [!UICONTROL trait]/ [!UICONTROL segment] .

[!DNL Audience Manager] de klanten kunnen verkiezen om de relevante signalen/traits/segmenten tegen gebruikersprofielen te vangen en deze informatie door [ off-line gegevensopname ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) naar [!DNL Audience Manager] te verzenden. Houd er rekening mee dat de gebruiker gekwalificeerd blijft voor het origineel [!UICONTROL trait] en [!UICONTROL segments] als deze hun gedrag herhalen.
