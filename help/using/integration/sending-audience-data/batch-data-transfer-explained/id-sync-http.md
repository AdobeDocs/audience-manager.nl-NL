---
description: Beschrijft de syntaxis en de parameters die in de aanvankelijke vraag van HTTP worden gebruikt om gebruikers IDs tussen een verkoper en een Audience Manager te synchroniseren. De synchronisatie van identiteitskaart kan beginnen nadat u uw gegevenstaxonomie naar Audience Manager verzendt.
seo-description: Beschrijft de syntaxis en de parameters die in de aanvankelijke vraag van HTTP worden gebruikt om gebruikers IDs tussen een verkoper en een Audience Manager te synchroniseren. De synchronisatie van identiteitskaart kan beginnen nadat u uw gegevenstaxonomie naar Audience Manager verzendt.
seo-title: ID-synchronisatie voor binnenkomende gegevensoverdrachten
solution: Audience Manager
title: ID-synchronisatie voor binnenkomende gegevensoverdrachten
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '480'
ht-degree: 3%

---


# ID-synchronisatie voor binnenkomende gegevensoverdrachten{#id-synchronization-for-inbound-data-transfers}

Describes the syntax and parameters used in the initial `HTTP` call to synchronize user IDs between a vendor and [!DNL Audience Manager]. ID synchronization can begin after you send your data taxonomy to [!DNL Audience Manager].

<!-- c_id_sync_in.xml -->

ID synchronization is the first step in the inbound, asynchronous data transfer process. In this step, [!DNL Audience Manager] and the vendor compare and match IDs for their respective site visitors. Zo kent een [!DNL Audience Manager] klant een gebruiker bijvoorbeeld op ID 123. Nochtans, kon uw gegevenspartner deze gebruiker met identiteitskaart 456 identificeren. Dankzij het synchronisatieproces kunnen [!DNL Audience Manager] en een leverancier van gegevens deze verschillende id&#39;s met elkaar combineren en gebruikers in hun respectieve systemen identificeren. Zodra volledig, [!DNL Audience Manager] en uw derdepartner overeenkomstige IDs voor elke unieke gebruiker zou moeten hebben die op onze netwerken wordt gezien.

U kunt de volgende methoden gebruiken om uw gegevens in te voeren [!DNL Audience Manager]:

* [HTTP-aanvraag voor synchronisatie van id](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Gebeurtenis gedeclareerde id](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID-synchronisatie uit een ingesloten e-mailafbeelding](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID-synchronisatieaanvraag `HTTP` {#id-sync-http}

In een uitwisseling van identiteitskaart, zou een behoorlijk geformatteerde [!DNL URL] koord als dit moeten kijken:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

De [!DNL URL] voor uw binnenkomende vraag van de synchronisatie van identiteitskaart zou variabelen moeten bevatten die in de lijst hieronder worden beschreven.

>[!NOTE]
>
>Vervang cursieve inhoud door werkelijke parameterwaarden.

<table id="table_EB9F4246E2A34ABB8ED06EA458EB186F"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Parameter </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2"> <p>Unieke id voor de inhoudsprovider (toegewezen door <span class="keyword"> Audience Manager</span>). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> <p>URL (Percent) Encoded representation of your Unique User ID. In addition to encoding reserved ASCII characters, any non-ASCII characters should be percent encoded based on the UTF-8 character encoding table. </p> <p>Zie de website <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL Encode/Decode Online</a> voor meer informatie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Een gecodeerde URL leidt om met de macro die binnen het wordt <code> ${DD_UUID}</code> ingebed. </p> <p>Opmerking:  Toegevoegd slechts wanneer de inhoudsleverancier de vraag in werking stelt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optioneel. Voeg deze parameter toe als u de Plug-in van de <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager voor IAB TCF gebruikt.</a></p> <p><code> gdpr</code> 0 (GDPR is niet van toepassing) of 1 (GDPR is van toepassing). </p> <p> <b>Opmerking:</b> Deze parameter kan alleen samen met <code>gdpr_consent</code>worden gebruikt.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optioneel. Voeg deze parameter toe als u de Plug-in van de <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager voor IAB TCF gebruikt.</a></p> <p><code>gdpr_consent</code> is de URL-veilige base64-gecodeerde GDPR toestemmingstekenreeks (zie <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-specificatie</a>). </p> <p> <b>Opmerking:</b> Deze parameter kan alleen samen met <code>gdpr</code>worden gebruikt.</p> </td> 
  </tr> 
 </tbody> 
</table>

## Gebeurtenis gedeclareerde id {#declared-id-event}

Zie [Opgegeven id&#39;s](../../../features/declared-ids.md)voor meer informatie.

## ID-synchronisatie uit een ingesloten e-mailafbeelding {#id-sync-email-image}

De indeling voor overeenkomende id&#39;s via een e-mailafbeelding is dezelfde als hierboven wordt weergegeven. Dit werkt echter alleen als afbeeldingen in een e-mailbericht zijn ingeschakeld. Dit kan de synchronisatie van id&#39;s via e-mail beïnvloeden, omdat de meeste e-mailsystemen afbeeldingen standaard uitschakelen.

>[!MORELIKETHIS]
>
>* [Componenten gegevensverzameling](../../../reference/system-components/components-data-collection.md)

