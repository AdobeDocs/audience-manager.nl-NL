---
description: Beschrijft de syntaxis en de parameters die in de aanvankelijke vraag van HTTP worden gebruikt om gebruiker IDs tussen Audience Manager en een derdegegevensleverancier te synchroniseren. Neem contact op met uw Adobe Audience Manager-consultant voordat u de eerste id synchroniseert.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: Id-synchronisatie voor overdracht van uitgaande data
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 10%

---

# Id-synchronisatie voor overdracht van uitgaande data{#id-synchronization-for-outbound-data-transfers}

Beschrijft de syntaxis en de parameters die in de aanvankelijke `HTTP` oproep om gebruikers-id&#39;s te synchroniseren tussen Audience Manager en een externe gegevensaanbieder. Neem contact op met uw Adobe Audience Manager-consultant voordat u de eerste id synchroniseert.

<!-- c_id_sync_out.xml -->

## Doel van id-synchronisatie

De synchronisatie van identiteitskaart is de eerste stap in het uitgaande, asynchrone proces van de gegevensoverdracht. In deze stap [!DNL Audience Manager] en de verkoper vergelijkt en past IDs voor hun respectieve plaatsbezoekers aan. Een [!DNL Audience Manager] de klant kent mogelijk een gebruiker met ID 123. Nochtans, kon uw gegevenspartner deze gebruiker met identiteitskaart 456 identificeren. Het synchronisatieproces staat [!DNL Audience Manager] en een gegevensleverancier om deze verschillende id&#39;s met elkaar te combineren en gebruikers in hun respectieve systemen te identificeren. Na voltooiing, [!DNL Audience Manager] en de derde gegevensleverancier zou overeenkomstige IDs voor elke unieke gebruiker moeten hebben die op onze netwerken wordt gezien.

## URL-syntaxis

In een ID-uitwisseling heeft de indeling [!DNL URL] string moet er als volgt uitzien:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-parameters

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
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">Unieke id voor de gegevensaanbieder (toegewezen door <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Unieke gebruikersnaam. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Een gecodeerde URL omleiden met de macro <code> ${DD_UUID}</code> ingesloten in het bestand. <p><b>Opmerking:</b> Wordt alleen toegevoegd wanneer de gegevensaanbieder de aanroep start. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 0 (GDPR is niet van toepassing) of 1 (GDPR is van toepassing).</p><p><b>Opmerking:</b> <ul><li>De <code>gdpr</code> en <code>gdpr_consent</code> Parameters worden geleidelijk ingevoerd in id sync URLs met activeringspartners. Zie Activeringspartners die IAB TCF in steunen <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager-plug-in voor IAB TCF.</a></li><li>Deze parameter kan alleen samen met <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> is de URL-veilige base64-gecodeerde GDPR toestemmingstekenreeks (zie <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-specificatie</a>).</p><p><b>Opmerking:</b> Deze parameter kan alleen samen met <code>gdpr</code>.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [API-methoden en -code van Data Collection Server (DCS) ](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Onderdelen voor dataverzameling](../../reference/system-components/components-data-collection.md)

