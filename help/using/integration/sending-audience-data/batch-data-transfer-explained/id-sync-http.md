---
description: Beschrijft de syntaxis en de parameters die in de aanvankelijke vraag van HTTP worden gebruikt om gebruikers IDs tussen een verkoper en een Audience Manager te synchroniseren. De synchronisatie van identiteitskaart kan beginnen nadat u uw gegevenstaxonomie naar Audience Manager verzendt.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between a vendor and Audience Manager. ID synchronization can begin after you send your data taxonomy to Audience Manager.
seo-title: ID Synchronization for Inbound Data Transfers
solution: Audience Manager
title: Id-synchronisatie voor overdracht van binnenkomende data
uuid: 037e74a6-acfd-4cef-b693-16b7aaa8e976
feature: Inbound Data Transfers
exl-id: cd9be32f-f443-45bd-a906-ec4c8589f608
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '438'
ht-degree: 6%

---

# Id-synchronisatie voor overdracht van binnenkomende data {#id-synchronization-for-inbound-data-transfers}

Beschrijft de syntaxis en de parameters die in de aanvankelijke `HTTP` aanroep om gebruikers-id&#39;s te synchroniseren tussen een leverancier en [!DNL Audience Manager]. De synchronisatie van id kan beginnen nadat u uw gegevenstaxonomie naar verzendt [!DNL Audience Manager].

De synchronisatie van identiteitskaart is de eerste stap in het binnenkomende, asynchrone proces van de gegevensoverdracht. In deze stap [!DNL Audience Manager] en de verkoper vergelijkt en past IDs voor hun respectieve plaatsbezoekers aan. Een [!DNL Audience Manager] de klant kent mogelijk een gebruiker met ID 123. Nochtans, kon uw gegevenspartner deze gebruiker met identiteitskaart 456 identificeren. Het synchronisatieproces staat [!DNL Audience Manager] en een gegevensleverancier om deze verschillende id&#39;s met elkaar te combineren en gebruikers in hun respectieve systemen te identificeren. Na voltooiing, [!DNL Audience Manager] en uw derdepartner zou overeenkomstige IDs voor elke unieke gebruiker moeten hebben die op onze netwerken wordt gezien.

U kunt de volgende methoden gebruiken om uw gegevens in te voeren [!DNL Audience Manager]:

* [HTTP-aanvraag voor synchronisatie van id](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-http)
* [Gebeurtenis gedeclareerde id](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#declared-id-event)
* [ID-synchronisatie uit een ingesloten e-mailafbeelding](../../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-http.md#id-sync-email-image)

## ID-synchronisatie `HTTP` Verzoek {#id-sync-http}

In een ID-uitwisseling heeft de indeling [!DNL URL] string moet er als volgt uitzien:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

De [!DNL URL] voor uw binnenkomende vraag van de synchronisatie van identiteitskaart zou variabelen moeten bevatten die in de hieronder lijst worden beschreven.

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
   <td colname="col2"> <p>URL (percentage) gecodeerde representatie van je unieke gebruikersnaam. Naast het coderen van gereserveerde ASCII-tekens moeten niet-ASCII-tekens procentueel gecodeerd zijn op basis van de UTF-8-tabel voor tekencodering. </p> <p>Zie voor meer informatie de <a href="https://www.url-encode-decode.com" format="http" scope="external"> URL-codering/decodering online</a> website. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2"> <p>Een gecodeerde URL omleiden met de macro <code> ${DD_UUID}</code> ingesloten in het bestand. </p> <p>Opmerking: Toegevoegd slechts wanneer de inhoudsleverancier de vraag in werking stelt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optioneel. Voeg deze parameter toe als u de <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-plug-in voor IAB TCF.</a></p> <p><code> gdpr</code> 0 (GDPR is niet van toepassing) of 1 (GDPR is van toepassing). </p> <p> <b>Opmerking:</b> Deze parameter kan alleen samen met <code>gdpr_consent</code>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"> <p>Optioneel. Voeg deze parameter toe als u de <a href="../../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-plug-in voor IAB TCF.</a></p> <p><code>gdpr_consent</code> is de URL-veilige base64-gecodeerde GDPR toestemmingstekenreeks (zie <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-specificatie</a>). </p> <p> <b>Opmerking:</b> Deze parameter kan alleen samen met <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Declared ID] Gebeurtenis {#declared-id-event}

Zie voor meer informatie [Opgegeven id&#39;s](../../../features/declared-ids.md).

## ID-synchronisatie uit een ingesloten e-mailafbeelding {#id-sync-email-image}

De indeling voor overeenkomende id&#39;s via een e-mailafbeelding is dezelfde als hierboven wordt weergegeven. Dit werkt echter alleen als afbeeldingen in een e-mailbericht zijn ingeschakeld. Dit kan de synchronisatie van id&#39;s via e-mail beïnvloeden, omdat de meeste e-mailsystemen afbeeldingen standaard uitschakelen.

>[!MORELIKETHIS]
>
>* [Onderdelen voor dataverzameling](../../../reference/system-components/components-data-collection.md)

