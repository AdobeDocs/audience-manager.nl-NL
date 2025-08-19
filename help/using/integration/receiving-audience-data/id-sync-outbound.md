---
description: Beschrijft de syntaxis en de parameters die in de aanvankelijke vraag van HTTP worden gebruikt om gebruiker IDs tussen Audience Manager en een derdegegevensleverancier te synchroniseren. Neem contact op met uw Adobe Audience Manager-consultant voordat u de eerste id synchroniseert.
seo-description: Describes the syntax and parameters used in the initial HTTP call to synchronize user IDs between Audience Manager and a third-party data provider. Contact your Adobe Audience Manager consultant before attempting your first ID synchronization.
seo-title: ID Synchronization for Outbound Data Transfers
solution: Audience Manager
title: De Synchronisatie van identiteitskaart voor Uitgaande Overdrachten van Gegevens
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
exl-id: 02cca19a-eebf-43b2-b034-24f072fe2efb
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '327'
ht-degree: 1%

---

# De Synchronisatie van identiteitskaart voor Uitgaande Overdrachten van Gegevens{#id-synchronization-for-outbound-data-transfers}

Beschrijft de syntaxis en de parameters die in de aanvankelijke `HTTP` vraag worden gebruikt om gebruiker IDs tussen Audience Manager en een derdegegevensleverancier te synchroniseren. Neem contact op met uw Adobe Audience Manager-consultant voordat u de eerste id synchroniseert.

<!-- c_id_sync_out.xml -->

## Doel van id-synchronisatie

De synchronisatie van identiteitskaart is de eerste stap in het uitgaande, asynchrone proces van de gegevensoverdracht. In deze stap vergelijken [!DNL Audience Manager] en de leverancier ID&#39;s voor hun respectievelijke sitebezoekers en komen deze overeen. Een klant van [!DNL Audience Manager] kent bijvoorbeeld een gebruiker op ID 123. Nochtans, kon uw gegevenspartner deze gebruiker met identiteitskaart 456 identificeren. Dankzij het synchronisatieproces kunnen [!DNL Audience Manager] en een leverancier van gegevens deze verschillende id&#39;s met elkaar combineren en gebruikers in hun respectieve systemen identificeren. Zodra volledig, [!DNL Audience Manager] en de derdegegevensleverancier overeenkomstige IDs voor elke unieke gebruiker zou moeten hebben die op onze netwerken wordt gezien.

## URL-syntaxis

In een ID-uitwisseling moet een correct opgemaakte [!DNL URL] -tekenreeks er als volgt uitzien:

```
https://dpm.demdex.net/ibs:dpid=<VENDOR_ID>&dpuuid=<VENDOR_UUID>&redir=<REDIRECT_URL>
```

## URL-parameters

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
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_ID&gt;</i> </code> </td> 
   <td colname="col2">Unieke identiteitskaart voor de gegevensleverancier (die door <span class="keyword"> Audience Manager </span> wordt toegewezen). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Unieke gebruikersnaam. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Een gecodeerde URL leidt omleiding met de daarin ingesloten macro <code> ${DD_UUID}</code> . <p><b> Nota:</b> voegde slechts toe wanneer de gegevensleverancier de vraag in werking stelt. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 0 (GDPR is niet van toepassing) of 1 (GDPR is van toepassing).</p><p><b> Nota:</b> <ul><li>De parameters <code>gdpr</code> en <code>gdpr_consent</code> worden geleidelijk ingevoerd in id sync URLs met activeringspartners. Zie de partners van de Activering die IAB TCF in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners"> insteekmodule-binnen van Audience Manager voor IAB TCF steunen.</a></li><li>Deze parameter kan alleen samen met <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> is het URL-veilige base64-gecodeerde GDPR toestemmingskoord (zie <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB specificatie </a>).</p><p><b> Nota:</b> Deze parameter kan slechts samen met <code>gdpr</code> worden gebruikt.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [ de Server van de Inzameling van Gegevens (DCS) API Methoden en Code ](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Onderdelen voor dataverzameling](../../reference/system-components/components-data-collection.md)
