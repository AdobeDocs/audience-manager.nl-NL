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
source-git-commit: 8bee593d0359f87f030840f87d70025dd5ea33ed
workflow-type: tm+mt
source-wordcount: '1444'
ht-degree: 50%

---

# Data Privacy-aanvragen {#data-privacy-requests}

## Overzicht {#overview}

Dit document biedt een overzicht van het beheer van de privacy van individuele gegevens en verzoeken om te weigeren die u kunt verzenden naar [!DNL Audience Manager] via de [UI Privacy Service](https://privacyui.cloud.adobe.io/) en de **[!DNL Privacy Service API]**.

Met deze gereedschappen kunt u privacyverzoeken voor consumentengegevens verzenden die zijn ingediend in het kader van [!DNL GDPR] en [!DNL CCPA].

We adviseren u om voor het lezen van het artikel de [Verklarende woordenlijst GDPR (AVG)](../data-security-and-privacy/aam-gdpr-glossary.md) en de [Verklarende woordenlijst CCPA](aam-ccpa-glossary.md) door te nemen voor een beter begrip van de hier gebruikte terminologie.

U kunt individuele verzoeken indienen om tot consumentengegevens toegang te hebben en te schrappen van [!DNL Audience Manager]op twee manieren:

* Via de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/). Zie de documentatie [hier](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md).
* Via de **[!DNL Privacy Service API]**. Zie de documentatie [hier](https://docs.adobe.com/content/help/nl-NL/experience-platform/privacy/home.html#!api-specification/markdown/narrative/tutorials/privacy_service_tutorial/privacy_service_ui_tutorial.md) en de [!DNL API] referentie [hier](https://www.adobe.io/apis/experiencecloud/gdpr/api-reference.html#!acpdr/swagger-specs/privacy-service.yaml).

Wanneer u individuele privacyverzoeken voor gegevens verzendt, kunt u [!DNL Audience Manager] id&#39;s (id&#39;s), zoals beschreven in het dialoogvenster **[Audience Manager-id&#39;s](data-privacy-ids.md)** en de bijbehorende naamruimte-id&#39;s (gegevensbron-id&#39;s).

De [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en) ondersteunt twee typen aanvragen: aanvragen voor datatoegang en aanvragen voor dataverwijdering.

## Aanvragen voor datatoegang {#access-data}

U kunt verzoeken om individuele gegevenstoegang via [UI Privacy Service](https://privacyui.cloud.adobe.io) (documentatie) [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) of door de Privacy Service-API aan te roepen (documentatie [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) en [!DNL API] referentie [hier](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

Met de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken met de [!UICONTROL Request Builder] of door een [!DNL JSON]-bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON]-bestand eruitziet, kunt u een [ voorbeeld-JSON downloaden](../data-security-and-privacy/assets/access_request.json).

We begrijpen dat u streeft naar de honorering van uw Data Privacy-aanvragen binnen de tijdsperiode die wettelijk is vastgesteld.

## Aanvragen voor dataverwijdering  {#delete-data}

U kunt verzoeken om gegevensverwijdering verzenden via de [UI Privacy Service](https://privacyui.cloud.adobe.io) (documentatie) [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/ui/overview.html?lang=en) of door de Privacy Service-API aan te roepen (documentatie [hier](https://experienceleague.adobe.com/docs/experience-platform/privacy/api/overview.html?lang=en) en [!DNL API] referentie [hier](https://developer.adobe.com/experience-platform-apis/references/privacy-service/).

Met de [Privacy Service-gebruikersinterface](https://privacyui.cloud.adobe.io/) kunt u nieuwe taakaanvragen maken met de [!UICONTROL Request Builder] of door een [!DNL JSON]-bestand te uploaden.

Als u wilt zien hoe een geldig [!DNL JSON]-bestand eruitziet, kunt u een [ voorbeeld-JSON downloaden](../data-security-and-privacy/assets/access_request.json).

Adobe begrijpt uw streven om binnen 30 dagen te voldoen aan de Data Privacy-aanvragen van uw consumenten. Daarom [!DNL Adobe] heeft zich ertoe verbonden uw verzoek om gegevens te verwijderen zo snel mogelijk te verwerken.

In antwoord op uw verzoeken om gegevens van de consument te schrappen, [!DNL Audience Manager] schrapt eigenschappen en segmenten verbonden aan [!DNL Audience Manager] id is opgenomen in de aanvraag. Daarnaast worden de respectieve [!DNL Audience Manager] identificatiecodes voor de persoon die ervoor heeft gekozen niet langer gegevens te verzamelen door [!DNL Audience Manager] en de bijbehorende id-toewijzingen worden verwijderd.

Wanneer u gedeclareerde id&#39;s verzendt, zoals een ander apparaat [!DNL CRM] ID&#39;s of [!DNL cookie] ID&#39;s, in verzoeken om gegevensbescherming, [!DNL Audience Manager] zal de noodzakelijke schrapping op alle verbonden apparaten (tot 100 apparaten per verklaarde identiteitskaart) uitvoeren.

[!DNL Audience Manager] zal proberen om activeringspartners over verwijderingsaanvragen in te lichten door hun desegmentatiegegevens te sturen voor geregistreerde personen die de verwijdering van bepaalde data aanvragen. Voor sommige activeringspartners geldt echter het volgende:

1. Kan unsegment (of segment verwijderen verzoeken van niet steunen [!DNL Audience Manager] en/of
2. Kan geen updates ontvangen van [!DNL Audience Manager] met een frequentie van minder dan 30 dagen. In die gevallen [!DNL Audience Manager] klanten kunnen schrappingsverzoeken aan activeringspartners niet op een geautomatiseerde manier verzenden door [!DNL Audience Manager].

In deze gevallen kunt u geen geautomatiseerde verwijderingsaanvragen naar activeringspartners verzenden via [!DNL Audience Manager].

Raadpleeg onze [op apparaten gebaseerde documentatie van de lijst van bestemmingen](assets/AAM-Partners-October2019.xlsx) om te zien [!DNL Audience Manager] activeringspartners ondersteunen unsegment.

## Opt-outaanvragen {#opt-out-requests}

[!DNL Audience Manager] ondersteunt de normen die gelden voor de hele branche met betrekking tot opt-out-beheer. Lees verder voor volledige informatie over de typen opt-out die worden ondersteund door [!DNL Audience Manager].

Terwijl de verzoeken van de gegevenstoegang en van de schrapping door [Privacy Service](https://experienceleague.adobe.com/docs/experience-platform/privacy/home.html?lang=en), worden opt-outverzoeken momenteel ondersteund via de [!DNL DCS API]. Lees verder om te leren wat de opt-out is [!DNL API] de vraag zou moeten kijken als.

### Algemene opt-outaanvragen

De wereldwijde opt-out is een opt-out-optie [!DNL Audience Manager] en andere [!DNL Adobe Experience Cloud] oplossingen voor alle merken. De onderstaande tabel geeft een overzicht van de methoden die worden gebruikt voor globale opt-out:

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

* [!DNL Audience Manager] beëindigt alle dataverzameling, datasegmentatie of data-activering zolang de gebruiker de browsercookies niet wist.
* Historische data worden na 120 dagen uit het gebruikersprofiel verwijderd.

### Opt-out op partnerniveau met gedeclareerde id-calls

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke [!DNL Audience Manager] partners. U kunt partner-vlakke opt-outverzoeken voor dwars-apparaat IDs, met inbegrip van verzenden [!DNL CRM] Id&#39;s en gehashte e-mailadressen.

Na een opt-out op partnerniveau met een gedeclareerde id-call gebeurt het volgende:

* De [CRM-id](../../reference/ids-in-aam.md) wordt niet meer verzameld;
* De laatste apparaat-id ([unieke Audience Manager-gebruikers-id](../../reference/ids-in-aam.md)) die is gekoppeld aan de [CRM-id](../../reference/ids-in-aam.md) is afgemeld voor dataverzameling.
* [!DNL Audience Manager] zal alle gegevensverzameling, segmentatie of activering van de [!DNL CRM] ID en de laatste apparaat-id die aan de [!DNL CRM] ID;
* [!DNL Audience Manager] ontsegmenteert uit [!DNL CRM] ID en laatste apparaat-id uit alle segmenten;
* [!UICONTROL Destination] de partners ontvangen unsegment verzoek om [!DNL CRM] ID en laatste apparaat-id. Desegmentatie werkt voor zowel [realtime](data-privacy-requests.md#aam-partners-with-unsegmentation)- als batchbestemmingen.
* Er worden geen historische data verwijderd.

Wanneer [!DNL Audience Manager] ontvangt een opt-outverzoek op partnerniveau, de [!DNL JSON] geretourneerd door de [!DNL DCS] bevat de [foutcode 171](../../api/dcs-intro/dcs-api-reference/dcs-error-codes.md#opt-out-error-codes), met het bericht [!UICONTROL "Encountered opt out tag"]in plaats van de [!DNL Audience Manager] gebruikersnaam.

U kunt een aanvraag voor opt-out van een gedeclareerde id aanvragen met de sleutelwaardeparen `d_cid` en `d_cid_ic`. De oude parameters zoals `d_dpid` en `d_dpuuid` werken nog steeds, maar worden beschouwd als afgekeurd. Zie [CID vervangt DPID en DPUUID](../../reference/cid.md). In de voorbeelden geeft *cursief* een plaatsaanduiding voor variabelen aan.

#### Weigeren met [!DNL CID] en [!DNL CID_IC]

Zie [URL-variabelen en syntaxis voor gedeclareerde id’s](../../features/declared-ids.md#variables-and-syntax) voor een beschrijving en syntaxis.

| Opt-out met | Codevoorbeeld |
|--- |--- |
| Een dataprovider-id en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout.jpg?d_cid=123%01987...` |
| Een integratiecode en een gebruikers-id. | `https://yourcompany.demdex.net/demoptout?d_cid_ic=456%01321...` |
| Meerdere  `d_cid`  en  `d_cid_ic`  sleutelwaardeparen. | `https://yourcompany.demdex.net/demoptout?d_cid=123%01987&d_cid_ic=456%01321...` |

 

### Opt-out op partnerniveau met apparaat-id-calls

De partner-vlakke opt-out staat u toe om uw gebruikers van gegevensinzameling door specifieke [!DNL Audience Manager] partners. U kunt zich afmelden voor dataverzameling van een bepaalde apparaat-id voor een merk door de volgende calls uit te voeren naar de [DCS-API](../../api/dcs-intro/dcs-api-reference/dcs-api-reference-overview.md):

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

## [!DNL Audience Manager] Partners met onsegmenteringsmogelijkheden {#aam-partners-with-unsegmentation}

Om u te helpen uw verzoeken om privacy van consumentengegevens automatiseren, [!DNL Audience Manager] zal proberen om activeringspartners over schrappingsverzoeken van Subjects van Gegevens op de hoogte te brengen door hen unsegment (of segment) informatie te verzenden.

Voor een aantal van onze activeringspartners geldt echter het volgende:

1. Kan unsegment verzoeken van niet steunen [!DNL Audience Manager] en/of
2. Kan geen updates ontvangen van [!DNL Audience Manager] vaker dan eenmaal in 30 dagen.

In deze gevallen kunt u geen geautomatiseerde verwijderingsaanvragen naar activeringspartners verzenden via [!DNL Audience Manager].

Raadpleeg de [lijst van op apparaten gebaseerde bestemmingen](/help/using/features/destinations/device-based-destinations-list.md) om te zien [!DNL Audience Manager] activeringspartners ondersteunen unsegment.

## Aanvragen voor datacorrectie {#correction}

Aangezien [!DNL Audience Manager] is niet de bron van de gegevens, er is een beperkte rol voor gegevenscorrectie in [!DNL Audience Manager]. De correctie zou kunnen betekenen dat de consument heeft verzocht om hetzij van een onjuiste [!UICONTROL trait]/[!UICONTROL segment] of naar wens [!UICONTROL trait]/[!UICONTROL segment].

[!DNL Audience Manager] klanten kunnen de relevante signalen/eigenschappen/segmenten tegen gebruikersprofielen vastleggen en deze informatie via [offline gegevensinvoer](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) tot [!DNL Audience Manager]. De gebruiker blijft gekwalificeerd voor het origineel [!UICONTROL trait] en [!UICONTROL segments] als ze hun gedrag herhalen.
