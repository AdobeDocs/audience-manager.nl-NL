---
description: In dit document worden de technische details van de naleving van Audience Manager Data Privacy-voorschriften besproken.
seo-description: In dit document worden de technische details van de naleving van Audience Manager Data Privacy-voorschriften besproken.
seo-title: Data Privacy-aanvragen
solution: Audience Manager
keywords: GDPR-gebruikersinterface, GDPR-API, CCPA, privacy
title: Data Privacy-aanvragen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Beheer en privacy van gegevens
exl-id: a1fc9c21-3417-4899-a585-92ad2cb25362
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1486'
ht-degree: 57%

---

# Data Privacy-aanvragen {#data-privacy-requests}

## Overzicht {#overview}

Dit document biedt een overzicht van het beheer van individuele gegevensprivacy en opt-out verzoeken die u naar [!DNL Audience Manager] via [Privacy Service UI](https://privacyui.cloud.adobe.io/) en **[!DNL Privacy Service API]** kunt verzenden.

Met deze gereedschappen kunt u privacyverzoeken voor consumentengegevens verzenden die zijn ingediend onder [!DNL GDPR] en [!DNL CCPA].

We adviseren u om voor het lezen van het artikel de [Verklarende woordenlijst GDPR (AVG)](../data-security-and-privacy/aam-gdpr-glossary.md) en de [Verklarende woordenlijst CCPA](aam-ccpa-glossary.md) door te nemen voor een beter begrip van de hier gebruikte terminologie.

U kunt individuele verzoeken indienen om tot consumentengegevens van [!DNL Audience Manager] toegang te hebben en te schrappen, op twee manieren:

* Via de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/). Zie de documentatie [hier](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Via de **[!DNL Privacy Service API]**. Zie de documentatie [hier](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) en de [!DNL API] verwijzing [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Bij het verzenden van individuele verzoeken om gegevensprivacy kunt u om het even welke [!DNL Audience Manager] herkenningstekens (IDs) indienen, zoals die in **[Audience ManagerHerkenningstekens](data-privacy-ids.md)** sectie, samen met hun respectieve namespace IDs (gegevensbron IDs) worden beschreven.

De [Privacy Service](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html) ondersteunt twee typen aanvragen: aanvragen voor datatoegang en aanvragen voor dataverwijdering.

## Aanvragen voor datatoegang {#access-data}

U kunt individuele verzoeken om gegevenstoegang via [Privacy Service UI](https://privacyui.cloud.adobe.io) (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) of door de Privacy Service API (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) en [!DNL API] verwijzing [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)) te roepen verzenden.

Met de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken met de [!UICONTROL Request Builder] of door een [!DNL JSON]-bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON]-bestand eruitziet, kunt u een [ voorbeeld-JSON downloaden](../data-security-and-privacy/assets/access_request.json).

We begrijpen dat u streeft naar de honorering van uw Data Privacy-aanvragen binnen de tijdsperiode die wettelijk is vastgesteld.

## Aanvragen voor dataverwijdering {#delete-data}

U kunt verzoeken om gegevensverwijdering verzenden via de [Privacy Service-UI](https://privacyui.cloud.adobe.io) (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) of door de Privacy Service-API aan te roepen (documentatie [hier](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) en [!DNL API] referentie [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Met de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken met de [!UICONTROL Request Builder] of door een [!DNL JSON]-bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON]-bestand eruitziet, kunt u een [ voorbeeld-JSON downloaden](../data-security-and-privacy/assets/access_request.json).

Adobe begrijpt uw streven om binnen 30 dagen te voldoen aan de Data Privacy-aanvragen van uw consumenten. Om die reden, [!DNL Adobe] wordt geëngageerd om uw verzoek van de gegevensschrapping zo spoedig mogelijk te verwerken.

Als reactie op uw verzoeken om gegevens van de consument te schrappen, [!DNL Audience Manager] schrapt eigenschappen en segmenten verbonden aan [!DNL Audience Manager] herkenningsteken inbegrepen in het verzoek. Daarnaast worden de respectieve [!DNL Audience Manager]-id&#39;s voor de individu verwijderd uit verdere gegevensverzameling door [!DNL Audience Manager] en de respectievelijke id-toewijzingen verwijderd.

Wanneer u gedeclareerde id&#39;s verzendt, zoals [!DNL CRM]-id&#39;s of [!DNL cookie]-id&#39;s, in privacyverzoeken voor gegevens, voert [!DNL Audience Manager] de vereiste verwijdering uit op alle gekoppelde apparaten (maximaal 100 apparaten per gedeclareerde id).

[!DNL Audience Manager] zal proberen om activeringspartners over verwijderingsaanvragen in te lichten door hun desegmentatiegegevens te sturen voor geregistreerde personen die de verwijdering van bepaalde data aanvragen. Voor sommige activeringspartners geldt echter het volgende:

1. Kan segment-aanvragen (of segment-aanvragen verwijderen uit [!DNL Audience Manager] en/of niet ondersteunen
2. Kan geen updates ontvangen van [!DNL Audience Manager] met een frequentie van minder dan 30 dagen. In die gevallen kunnen [!DNL Audience Manager]-klanten geen verwijderingsverzoeken automatisch via [!DNL Audience Manager] naar activeringspartners verzenden.

In deze gevallen kunt u geen geautomatiseerde verwijderingsaanvragen naar activeringspartners verzenden via [!DNL Audience Manager].

Download ons [Partner Excel sheet](assets/AAM-Partners-October2019.xlsx) om te zien welke [!DNL Audience Manager] activeringspartners unsegment steunen.

## Opt-outaanvragen {#opt-out-requests}

[!DNL Audience Manager] ondersteunt de normen die gelden voor de hele branche met betrekking tot opt-out-beheer. Lees verder voor volledige informatie over de typen opt-out die worden ondersteund door [!DNL Audience Manager].

Terwijl de verzoeken van de gegevenstoegang en van de schrapping door [Privacy Service](https://www.adobe.io/apis/experienceplatform/home/services/privacy-service.html) worden behandeld, worden de opt-outverzoeken momenteel gesteund door [!DNL DCS API]. Lees verder om te leren hoe de opt-out [!DNL API] vraag zou moeten kijken als.

### Algemene opt-outaanvragen

De wereldwijde opt-out staat voor een opt-out voor alle merken in [!DNL Audience Manager] en andere [!DNL Adobe Experience Cloud] oplossingen. De onderstaande tabel geeft een overzicht van de methoden die worden gebruikt voor globale opt-out:

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
   <td colname="col2"> <p>De pagina <a href="https://www.adobe.com/nl/privacy/opt-out.html#customeruse" format="http" scope="external">Uw privacyopties</a> bevat 1-klikfuncties waarmee uw eindgebruikers de verzameling van hun data door de Adobe Experience Cloud-advertentieoplossingen (inclusief Audience Manager) kunnen beheren en uitschakelen. Zie met name de <a href="https://www.adobe.com/privacy/opt-out.html#customeruse" format="http" scope="external">sectie voor zakelijke klanten</a> van de pagina voor privacyopties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Directe API-calls naar Audience Manager </p> </td> 
   <td colname="col2"> <p>Uw gebruikers kunnen zich afmelden voor dataverzameling door alle Audience Manager-merken door een call naar de onderstaande DCS-API inclusief de <a href="../../reference/ids-in-aam.md">Audience Manager-gebruikers-id</a>: </p> <p> <code> curl -i "https://www.demdex.net/demoptout.jpg" --cookie "demdex=12345678901234567890123456789012345678;dextp=12;DST=12" </code> </p> <p>Daardoor zullen wij <code>demdex=NOTARGET</code>- en <code>dextp=NOTARGET</code>-cookies plaatsen voor de verzonden Audience Manager-gebruikers-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Mobiele apparaten </p> </td> 
   <td colname="col2"> <p>Zie de instellingen voor opt-out en privacy voor: </p> <p> 
     <ul id="ul_78042D6D302F4119A2439BF71F228288"> 
      <li id="li_5A0EDABDEF454FEEBBBFF4D68CC9A366"> <a href="https://docs.adobe.com/content/help/nl-NL/mobile-services/android/gdpr-privacy-android/privacy.html" format="https" scope="external"> Android-apparaten </a> </li> 
      <li id="li_690067D869B84A9598AA97388D56F1BE"> <a href="https://docs.adobe.com/content/help/nl-NL/mobile-services/ios/privacy-gdpr-ios/privacy.html" format="https" scope="external"> iOS-apparaten </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Uw eindgebruikers kunnen zich ook afmelden voor wereldwijde dataverzameling door websites te bezoeken van onze industriestandaardpartners.

* [The Digital Advertising Alliance (DAA)](https://optout.aboutads.info/?c=2#!/);
* [Network Advertising Initiative (NAI)](https://optout.networkadvertising.org/?c=1#!/).

Na de hierboven beschreven opt-outaanvragen:

* [!DNL Audience Manager] beëindigt alle dataverzameling, datasegmentatie of data-activering zolang de gebruiker de browsercookies niet wist.
* Historische data worden na 120 dagen uit het gebruikersprofiel verwijderd.

### Opt-out op partnerniveau met gedeclareerde id-calls

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke [!DNL Audience Manager] partners te sluiten. U kunt partner-vlakke opt-outverzoeken voor dwars-apparaat IDs, met inbegrip van [!DNL CRM] IDs en gehakt e-mailadressen verzenden.

Na een opt-out op partnerniveau met een gedeclareerde id-call gebeurt het volgende:

* De [CRM-id](../../reference/ids-in-aam.md) wordt niet meer verzameld;
* De laatste apparaat-id ([unieke Audience Manager-gebruikers-id](../../reference/ids-in-aam.md)) die is gekoppeld aan de [CRM-id](../../reference/ids-in-aam.md) is afgemeld voor dataverzameling.
* [!DNL Audience Manager] alle gegevensverzameling, segmentatie of activering van de  [!DNL CRM] id en de laatste apparaat-id die aan de  [!DNL CRM] id is gekoppeld, stopzetten;
* [!DNL Audience Manager] ontsegmenteert opted-out  [!DNL CRM] identiteitskaart en laatste apparatenidentiteitskaart van alle segmenten;
* [!UICONTROL Destination] de partners ontvangen unsegment verzoek om  [!DNL CRM] identiteitskaart en laatste apparatenidentiteitskaart Desegmentatie werkt voor zowel [realtime](data-privacy-requests.md#aam-partners-with-unsegmentation)- als batchbestemmingen.
* Er worden geen historische data verwijderd.

Wanneer [!DNL Audience Manager] een partner-vlakke opt-out verzoek ontvangt, [!DNL JSON] door [!DNL DCS] is teruggekeerd bevat [foutencode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), met het bericht [!UICONTROL "Encountered opt out tag"], in plaats van [!DNL Audience Manager] gebruiker - identiteitskaart

U kunt een aanvraag voor opt-out van een gedeclareerde id aanvragen met de sleutelwaardeparen `d_cid` en `d_cid_ic`. De oude parameters zoals `d_dpid` en `d_dpuuid` werken nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

#### Uitschakelen met [!DNL CID] en [!DNL CID_IC]

Zie [URL-variabelen en syntaxis voor gedeclareerde id’s](../../features/declared-ids.md#variables-and-syntax) voor een beschrijving en syntaxis.

| Opt-out met | Codevoorbeeld |
|--- |--- |
| Een dataprovider-id en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Een integratiecode en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Meerdere `d_cid`- en `d_cid_ic`-sleutelwaardeparen. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out op partnerniveau met apparaat-id-calls

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke [!DNL Audience Manager] partners te sluiten. U kunt zich afmelden voor dataverzameling van een bepaalde apparaat-id voor een merk door de volgende calls uit te voeren naar de [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Opt-out met | Codevoorbeeld |
|--- |--- |
| An [!DNL Audience Manager] [!DNL Unique User ID] (`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| An [!DNL Experience Cloud] ID (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Lees meer over `uuid`, `mid` en `imsOrgId` in de [Index van id’s in Audience Manager](/help/using/reference/ids-in-aam.md).

Na een opt-out op partnerniveau met een apparaat-id-call gebeurt het volgende:

* De apparaat-id is uitgeschakeld voor dataverzameling.
* [!DNL Audience Manager] beëindigt alle dataverzameling, -segmentatie of -activering voor de partner voor de apparaat-id.
* [!DNL Audience Manager] ontsegmenteert apparatenidentiteitskaart van alle segmenten;
* Bestemmingspartners ontvangen de desegmentatieaanvraag voor de apparaat-id. Desegmentatie werkt voor zowel [realtime](data-privacy-requests.md#aam-partners-with-unsegmentation)- als batchbestemmingen.
* Er worden geen historische data verwijderd.

## [!DNL Audience Manager] Partners met onsegmenteringsmogelijkheden  {#aam-partners-with-unsegmentation}

Om u te helpen uw verzoeken van de privacy van consumentengegevens automatiseren, [!DNL Audience Manager] zal proberen om activeringspartners over schrappingsverzoeken van de Onderwerpen van Gegevens op de hoogte te brengen door hen unsegment (of segment) informatie te verzenden.

Voor een aantal van onze activeringspartners geldt echter het volgende:

1. Kan unsegment verzoeken van [!DNL Audience Manager] en/of niet steunen
2. Kan updates niet vaker dan eenmaal in 30 dagen ontvangen van [!DNL Audience Manager].

In deze gevallen kunt u geen geautomatiseerde verwijderingsaanvragen naar activeringspartners verzenden via [!DNL Audience Manager].

Raadpleeg de [lijst van op apparaat-gebaseerde bestemmingen](/help/using/features/destinations/device-based-destinations-list.md) om te zien welke [!DNL Audience Manager] activeringspartners unsegment steunen.

## Aanvragen voor datacorrectie {#correction}

Aangezien [!DNL Audience Manager] niet de bron van de gegevens is, is er een beperkte rol voor gegevenscorrectie in [!DNL Audience Manager]. De correctie zou kunnen betekenen dat de consument heeft verzocht om ofwel te worden gediskwalificeerd van een onjuiste [!UICONTROL trait]/[!UICONTROL segment] of te worden gekwalificeerd naar de gewenste [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] klanten kunnen de relevante signalen/eigenschappen/segmenten tegen gebruikersprofielen vangen en deze informatie door  [off-line ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) gegevensopname verzenden  [!DNL Audience Manager]. Houd er rekening mee dat de gebruiker gekwalificeerd blijft voor het origineel [!UICONTROL trait] en [!UICONTROL segments] als deze hun gedrag herhalen.
