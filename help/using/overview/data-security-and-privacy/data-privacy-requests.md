---
description: In dit document worden de technische details van de naleving van Audience Manager Data Privacy-voorschriften besproken.
seo-description: In dit document worden de technische details van de naleving van Audience Manager Data Privacy-voorschriften besproken.
seo-title: Data Privacy-aanvragen
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy
title: Data Privacy-aanvragen
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '1471'
ht-degree: 59%

---


# Data Privacy-aanvragen {#data-privacy-requests}

## Overzicht {#overview}

This document provides an overview of managing individual data privacy and opt-out requests that you can send to [!DNL Audience Manager] through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) and the **[!DNL Privacy Service API]**.

These tools allow you to send consumer data privacy requests made under [!DNL GDPR] and [!DNL CCPA].

We adviseren u om voor het lezen van het artikel de [Verklarende woordenlijst GDPR (AVG)](../data-security-and-privacy/aam-gdpr-glossary.md) en de [Verklarende woordenlijst CCPA](aam-ccpa-glossary.md) door te nemen voor een beter begrip van de hier gebruikte terminologie.

You can submit individual requests to access and delete consumer data from [!DNL Audience Manager], in two ways:

* Via de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/). Zie de documentatie [hier](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Via de **[!DNL Privacy Service API]**. See the documentation [here](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) and the [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

When sending individual data privacy requests, you can submit any [!DNL Audience Manager] identifiers (IDs), as described in the **[Audience Manager Identifiers](data-privacy-ids.md)**section, along with their respective namespace IDs (data source IDs).

De [Privacy Service](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html) ondersteunt twee typen aanvragen: aanvragen voor datatoegang en aanvragen voor dataverwijdering.

## Aanvragen voor datatoegang {#access-data}

U kunt individuele datatoegangsaanvragen verzenden via de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) (documentatie [hier](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) of door het oproepen van de [!DNL Privacy Service API] (documentatie [hier](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html) en [!DNL API]-referentie [hier ](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Met de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken met de [!UICONTROL Request Builder] of door een [!DNL JSON]-bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON]-bestand eruitziet, kunt u een [ voorbeeld-JSON downloaden](../data-security-and-privacy/assets/access_request.json).

We begrijpen dat u streeft naar de honorering van uw Data Privacy-aanvragen binnen de tijdsperiode die wettelijk is vastgesteld.

## Aanvragen voor dataverwijdering {#delete-data}

You can send data deletion requests through the [Privacy Service UI](https://privacyui.cloud.adobe.io/) (documentation [here](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md)) or by calling the [!DNL Privacy Service API] (documentation [here](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html) and [!DNL API] reference [here](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml)).

Met de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken met de [!UICONTROL Request Builder] of door een [!DNL JSON]-bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON]-bestand eruitziet, kunt u een [ voorbeeld-JSON downloaden](../data-security-and-privacy/assets/access_request.json).

Adobe begrijpt uw streven om binnen 30 dagen te voldoen aan de Data Privacy-aanvragen van uw consumenten. For that reason, [!DNL Adobe] is committed to processing your data deletion request as soon as possible.

In response to your consumer data deletion requests, [!DNL Audience Manager] deletes traits and segments associated with the [!DNL Audience Manager] identifier included in the request. Additionally, the respective [!DNL Audience Manager] identifiers for the individual opted out of further data collection by [!DNL Audience Manager] and the respective ID mappings will be removed.

When you send declared IDs, such as cross device [!DNL CRM] IDs or [!DNL cookie] IDs, in data privacy requests, [!DNL Audience Manager] will perform the necessary deletion on all the linked devices (up to 100 devices per declared ID).

[!DNL Audience Manager] zal proberen om activeringspartners over verwijderingsaanvragen in te lichten door hun desegmentatiegegevens te sturen voor geregistreerde personen die de verwijdering van bepaalde data aanvragen. Voor sommige activeringspartners geldt echter het volgende:

1. Cannot support unsegment (or remove segment) requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] with a frequency of less than 30 days. In those cases, [!DNL Audience Manager] customers are not able to send delete requests to activation partners in an automated way through [!DNL Audience Manager].

In deze gevallen kunt u geen geautomatiseerde verwijderingsaanvragen naar activeringspartners verzenden via [!DNL Audience Manager].

Download our [Partner Excel sheet](assets/AAM-Partners-October2019.xlsx) to see which [!DNL Audience Manager] activation partners support unsegment.

## Opt-outaanvragen {#opt-out-requests}

[!DNL Audience Manager] ondersteunt normen voor het beheer van opt-out voor de hele branche. Read on for complete information on the types of opt-out supported by [!DNL Audience Manager].

While data access and deletion requests are handled through the [Privacy Service](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html), opt-out requests are currently supported through the [!DNL DCS API]. Read on to learn what the opt-out [!DNL API] calls should look like.

### Algemene opt-outaanvragen

The global opt-out represents an opt-out across [!DNL Audience Manager] and other [!DNL Adobe Experience Cloud] solutions for all brands. De onderstaande tabel geeft een overzicht van de methoden die worden gebruikt voor globale opt-out:

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

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. You can send partner-level opt-out requests for cross-device IDs, including [!DNL CRM] IDs and hashed email addresses.

Na een opt-out op partnerniveau met een gedeclareerde id-call gebeurt het volgende:

* De [CRM-id](../../reference/ids-in-aam.md) wordt niet meer verzameld;
* De laatste apparaat-id ([unieke Audience Manager-gebruikers-id](../../reference/ids-in-aam.md)) die is gekoppeld aan de [CRM-id](../../reference/ids-in-aam.md) is afgemeld voor dataverzameling.
* [!DNL Audience Manager] alle gegevensverzameling, segmentatie of activering van de [!DNL CRM] id en de laatste apparaat-id die aan de [!DNL CRM] id is gekoppeld, stopzetten;
* [!DNL Audience Manager] ontsegmenteert opted-out [!DNL CRM] identiteitskaart en laatste apparatenidentiteitskaart van alle segmenten;
* [!UICONTROL Destination] de partners ontvangen unsegment verzoek om identiteitskaart en [!DNL CRM] laatste apparatenidentiteitskaart Desegmentatie werkt voor zowel [realtime](data-privacy-requests.md#aam-partners-with-unsegmentation)- als batchbestemmingen.
* Er worden geen historische data verwijderd.

When [!DNL Audience Manager] receives a partner-level opt-out request, the [!DNL JSON] returned by the [!DNL DCS] contains the [error code 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), with the message [!UICONTROL "Encountered opt out tag"], instead of the [!DNL Audience Manager] user ID.

U kunt een aanvraag voor opt-out van een gedeclareerde id aanvragen met de sleutelwaardeparen `d_cid` en `d_cid_ic`. De oude parameters zoals `d_dpid` en `d_dpuuid` werken nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

#### Weigeren met [!DNL CID] en [!DNL CID_IC]

Zie [URL-variabelen en syntaxis voor gedeclareerde id’s](../../features/declared-ids.md#variables-and-syntax) voor een beschrijving en syntaxis.

| Opt-out met | Codevoorbeeld |
|--- |--- |
| Een dataprovider-id en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Een integratiecode en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Meerdere `d_cid` en `d_cid_ic` sleutelwaardeparen. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out op partnerniveau met apparaat-id-calls

The partner-level opt-out allows you to opt-out your users from data collection by specific [!DNL Audience Manager] partners. U kunt zich afmelden voor dataverzameling van een bepaalde apparaat-id voor een merk door de volgende calls uit te voeren naar de [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

| Opt-out met | Codevoorbeeld |
|--- |--- |
| An [!DNL Audience Manager] ( [!DNL Unique User ID]`uuid`). | `https://yourcompany.demdex.net/demoptout.jpg?d_uuid=123` |
| Een [!DNL Experience Cloud] id (`mid`) | `https://yourcompany.demdex.net/demoptout.jpg?d_mid=123&d_orgid=IMSoRGid` |

Lees meer over `uuid`, `mid` en `imsOrgId` in de [Index van id’s in Audience Manager](/help/using/reference/ids-in-aam.md).

Na een opt-out op partnerniveau met een apparaat-id-call gebeurt het volgende:

* De apparaat-id is uitgeschakeld voor dataverzameling.
* [!DNL Audience Manager] beëindigt alle dataverzameling, -segmentatie of -activering voor de partner voor de apparaat-id.
* [!DNL Audience Manager] ontsegmenteert apparatenidentiteitskaart van alle segmenten;
* Bestemmingspartners ontvangen de desegmentatieaanvraag voor de apparaat-id. Desegmentatie werkt voor zowel [realtime](data-privacy-requests.md#aam-partners-with-unsegmentation)- als batchbestemmingen.
* Er worden geen historische data verwijderd.

## [!DNL Audience Manager] Partners met onsegmenteringsmogelijkheden {#aam-partners-with-unsegmentation}

In order to help you automate your consumer data privacy requests, [!DNL Audience Manager] will attempt to notify activation partners about deletion requests from Data Subjects by sending them unsegment (or remove segment) information.

Voor een aantal van onze activeringspartners geldt echter het volgende:

1. Cannot support unsegment requests from [!DNL Audience Manager] and/or
2. Are not able to receive updates from [!DNL Audience Manager] more frequently than once in 30 days.

In deze gevallen kunt u geen geautomatiseerde verwijderingsaanvragen naar activeringspartners verzenden via [!DNL Audience Manager].

Consult the [list of device-based destinations](/help/using/features/destinations/device-based-destinations-list.md) to see which [!DNL Audience Manager] activation partners support unsegment.

## Aanvragen voor datacorrectie {#correction}

Given that [!DNL Audience Manager] is not the source of the data, there is a limited role for data correction in [!DNL Audience Manager]. The correction could mean that the consumer has requested to either be disqualified from an incorrect [!UICONTROL trait]/[!UICONTROL segment] or qualified to the desired [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] klanten kunnen de relevante signalen/traits/segmenten tegen gebruikersprofielen vangen en deze informatie door [off-line gegevensopname](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) naar [!DNL Audience Manager]. verzenden Please note that the user will continue to get qualified to the original [!UICONTROL trait] and [!UICONTROL segments] if they repeat their behavior.
