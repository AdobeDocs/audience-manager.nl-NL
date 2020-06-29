---
description: Beschrijft de syntaxis en de parameters die in de aanvankelijke vraag van HTTP worden gebruikt om gebruiker IDs tussen Audience Manager en een derdegegevensleverancier te synchroniseren. Neem contact op met uw Adobe Audience Manager consultant voordat u de eerste id-synchronisatie gaat uitvoeren.
seo-description: Beschrijft de syntaxis en de parameters die in de aanvankelijke vraag van HTTP worden gebruikt om gebruiker IDs tussen Audience Manager en een derdegegevensleverancier te synchroniseren. Neem contact op met uw Adobe Audience Manager consultant voordat u de eerste id-synchronisatie gaat uitvoeren.
seo-title: De Synchronisatie van identiteitskaart voor Uitgaande Overdrachten van Gegevens
solution: Audience Manager
title: De Synchronisatie van identiteitskaart voor Uitgaande Overdrachten van Gegevens
uuid: f3849be8-1094-47db-9296-7482f020af18
feature: Outbound Data Transfers
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '376'
ht-degree: 3%

---


# De Synchronisatie van identiteitskaart voor Uitgaande Overdrachten van Gegevens{#id-synchronization-for-outbound-data-transfers}

Beschrijft de syntaxis en de parameters die in de aanvankelijke `HTTP` vraag worden gebruikt om gebruiker IDs tussen Audience Manager en een derdegegevensleverancier te synchroniseren. Neem contact op met uw Adobe Audience Manager consultant voordat u de eerste id-synchronisatie gaat uitvoeren.

<!-- c_id_sync_out.xml -->

## Doel van id-synchronisatie

De synchronisatie van identiteitskaart is de eerste stap in het uitgaande, asynchrone proces van de gegevensoverdracht. In deze stap vergelijkt [!DNL Audience Manager] en vergelijkt de leverancier ID&#39;s voor hun respectievelijke sitebezoekers. Zo kent een [!DNL Audience Manager] klant een gebruiker bijvoorbeeld op ID 123. Nochtans, kon uw gegevenspartner deze gebruiker met identiteitskaart 456 identificeren. Dankzij het synchronisatieproces kunnen [!DNL Audience Manager] en een leverancier van gegevens deze verschillende id&#39;s met elkaar combineren en gebruikers in hun respectieve systemen identificeren. Zodra volledig, [!DNL Audience Manager] en de derde gegevensleverancier overeenkomstige IDs voor elke unieke gebruiker zou moeten hebben die op onze netwerken wordt gezien.

## URL-syntaxis

In een uitwisseling van identiteitskaart, zou een behoorlijk geformatteerde [!DNL URL] koord als dit moeten kijken:

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
   <td colname="col2">Unieke id voor de gegevensaanbieder (toegewezen door <span class="keyword"> Audience Manager</span>). </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;VENDOR_UUID&gt;</i> </code> </td> 
   <td colname="col2"> Unieke gebruikersnaam. </td> 
  </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code> <i>&lt;REDIRECT_URL&gt;</i> </code> </td> 
   <td colname="col2">Een gecodeerde URL leidt om met de macro die binnen het wordt <code> ${DD_UUID}</code> ingebed. <p><b>Opmerking:</b> Wordt alleen toegevoegd wanneer de gegevensaanbieder de aanroep start. </p> </td> 
  </tr> 
    </tr> 
  <tr> 
   <td colname="col1"> <code> <i>gdpr = &lt;0|1&gt;</i> </code> </td> 
   <td colname="col2"> <p><code>gdpr</code> 0 (GDPR is niet van toepassing) of 1 (GDPR is van toepassing).</p><p><b>Opmerking:</b> <ul><li>De <code>gdpr</code> en <code>gdpr_consent</code> parameters worden geleidelijk ingevoerd in de synchronisatie-URL's van de id met activeringspartners. Zie Activeringspartners die IAB TCF in <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md#aam-activation-partners">Audience Manager stop-binnen voor IAB TCF steunen.</a></li><li>Deze parameter kan alleen samen met <code>gdpr_consent.</code></li></ul></p></td>
  </tr> 
    </tr> 
  <tr valign="top"> 
   <td colname="col1"> <code><i>gdpr_consent=&lt;ENCODED STRING&gt;</i> </code> </td> 
   <td colname="col2"><p><code>gdpr_consent</code> is de URL-veilige base64-gecodeerde GDPR toestemmingstekenreeks (zie <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/URL-based%20Consent%20Passing_%20Framework%20Guidance.md#specifications" format="http" scope="external"> IAB-specificatie</a>).</p><p><b>Opmerking:</b> Deze parameter kan alleen samen met <code>gdpr</code>worden gebruikt.</p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [API-methoden en code voor gegevensverzamelingsserver (DCS)](../../api/dcs-intro/dcs-event-calls/dcs-event-calls.md)
>* [Componenten gegevensverzameling](../../reference/system-components/components-data-collection.md)

