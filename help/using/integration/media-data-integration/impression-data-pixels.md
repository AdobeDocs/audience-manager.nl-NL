---
description: Één benadering voor het verzenden van media gegevens naar Audience Manager gebruikt en servermacro's om campagnerekenmerken naar Audience Manager te verzenden.
seo-description: Één benadering voor het verzenden van media gegevens naar Audience Manager gebruikt en servermacro's om campagnerekenmerken naar Audience Manager te verzenden.
seo-title: Campagne-impressiedata vastleggen via pixelcalls
solution: Audience Manager
title: Campagne-impressiedata vastleggen via pixelcalls
uuid: 6ac44100-4c55-4992-8835-0d578bb4e5c2
feature: Adobe Campaign Integration
exl-id: 04e6f1e5-5075-4221-a310-deb3717458ad
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '738'
ht-degree: 20%

---

# Campagne-impressiedata vastleggen via pixelcalls{#capturing-campaign-impression-data-via-pixel-calls}

Één benadering voor het verzenden van media gegevens naar Audience Manager gebruikt en servermacro&#39;s om campagnerekenmerken naar Audience Manager te verzenden.

Deze methodologie wordt vaak bedoeld als &quot;het blokkeren van creatief.&quot; Die gegevenspunten worden dynamisch ingevoegd in de [!DNL Audience Manager] pixelcode door de externe macro&#39;s en servermacro&#39;s, die worden gebruikt om alle indrukken in kaart te brengen en te melden en op de belangrijkste rapporteringsattributen van de campagne worden gebaseerd. De geaggregeerde gegevens bieden een uniforme weergave van de campagneprestaties, helpen u aangepaste conversiepaden te identificeren en helpen klanten de volgorde van ad-servergebeurtenissen die tot conversies leiden, te verbeteren.

## Syntaxis gebeurtenisaanroep

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, haakjes `[ ]` `( )`, enz.) geven code-elementen en -opties aan. Zie [Stijlconventies voor code- en tekstelementen](../../reference/code-style-elements.md) voor meer informatie.

De gebeurtenisaanroep verzamelt impressie- en conversiedata en verzendt deze naar de [!DNL Audience Manager][-dataverzamelingsservers ](/help/using/reference/system-components/components-data-collection.md) ([!DNL DCS]). Dit proces baseert zich op advertentieservers van derden die de aanvraag in de advertentie plaatsen om te bepalen welke content in de code wordt opgenomen. De advertentieservers van derden (bijvoorbeeld [!DNL DFA]) kunnen deze code in elke advertentie-impressie plaatsen. Bovendien gebruikt een advertentievraag geen [!DNL JavaScript] en past deze geen framebustertechnieken toe om toegang te krijgen tot uitgeversdata buiten de advertentietag.

Gebeurtenisaanroepen bestaan uit sleutel-waardeparen die de volgende syntaxis gebruiken:

```
http://clientname.demdex.net/event?d_event=imp&d_src=datasource_id&d_site=siteID&d_creative=<i>creative_id</i>&d_adgroup=<i>adgroup_id</i>&d_placement=<i>placement_id</i>&d_campaign=<i>campaign_id</i>[&d_cid=(GAID|IDFA)%01 DPUUID]&d_bust=cache buster value
```

In het sleutelwaardepaar, is de waardevariabele identiteitskaart of macro die door de advertentieserver wordt opgenomen. Wanneer de tag ad wordt geladen, wordt `%macro%` vervangen door de vereiste corresponderende waarden. Deze vraag keert geen reactie terug.

## Ondersteunde sleutelwaardeparen {#supported-key-value-pairs}

Aanroepen van indrukwekkende gebeurtenissen accepteren gegevens die in sleutelwaardeparen worden gevormd. In de volgende tabel vindt u een overzicht en beschrijving van de toetsen die worden gebruikt om deze variabelen vast te houden. Veel van deze zijn vereist als u gegevens in [Audience Optimization Rapporten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) wilt vangen en analyseren.

<table id="table_F068C4D49F7D4775924D3CA712BF15BA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sleutel </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <code> d_adgroup </code> </td> 
   <td colname="col2"> <p>Numerieke id van advertentiegroep van de advertentieserver. </p> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_adsrc </code> </td> 
   <td colname="col2"> <p>Gegevensbron-id of integratiecode voor uw adverteerder. </p> <p>Vereist voor <span class="wintitle"> Audience Optimization </span> rapporten. </p> <p>Optioneel.</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_bu </code> </td> 
   <td colname="col2"> <p>Gegevensbron-id of integratiecode voor uw bedrijfseenheid. </p> <p>Vereist voor <span class="wintitle"> Audience Optimization </span> rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bust </code> </p> </td> 
   <td colname="col2"> <p>Waarde voor opbouwen van cache. <span class="keyword"> Audience Manager verzendt  </span> automatisch cache-control headers die door de meeste browsers en proxy's worden ondersteund. Als u extra cache-busting wilt uitvoeren, neemt u deze parameter op in een gebeurtenisaanroep, gevolgd door een willekeurige tekenreeks. </p> <p> Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_campaign </code> </td> 
   <td colname="col2"> <p>Numerieke campagne-id van de advertentieserver. </p> <p>Vereist voor <span class="wintitle"> Audience Optimization </span> rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_cid </code> </td> 
   <td colname="col2"> <p>In deze context instantieert <code> d_cid </code> een sleutelwaardepaar waarmee u een mobiel apparaattype aan een unieke gebruikersnaam (DPUUID) kunt koppelen. Een vaste id bepaalt het type mobiel apparaat. De waarde, de gebruikers-id, kan variëren. Scheid het sleutel-waardepaar met <code> %01 </code>, wat een niet-druk controlekarakter is. Deze parameter accepteert de volgende toetsen: </p> 
    <ul id="ul_4D5D696D10B34615867AF3B64A938878"> 
     <li id="li_A4BD4B0C8C9443BF99075CDFACC013F6">20914: Identificeert een Android-apparaat (GAID). <code> d_cid = 20914 %01 1234 </code> zegt bijvoorbeeld dat gebruiker 1234 is gekoppeld aan een Android-apparaat. </li> 
     <li id="li_F83D7B3EC4D24D0187BFE639E2812B36">20915: Identificeert een iOS-apparaat (IDFA). <code> d_cid = 20915 %01 5678 </code> zegt bijvoorbeeld dat gebruiker 5678 is gekoppeld aan een iOS-apparaat. </li> 
    </ul> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_creative </code> </td> 
   <td colname="col2"> <p>Numerieke creatieve id van de advertentieserver. </p> <p>Vereist voor <span class="wintitle"> Audience Optimization </span> rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_event=imp </code> </td> 
   <td colname="col2"> <p>Hiermee wordt een gebeurtenisaanroep geïdentificeerd als een weergavegebeurtenis. </p> <p>Vereist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_placement </code> </td> 
   <td colname="col2"> <p>Numerieke plaatsing-id van de advertentieserver. </p> <p> Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_site </code> </td> 
   <td colname="col2"> <p>Numerieke site-id van de advertentieserver. </p> <p>Vereist voor <span class="wintitle"> Audience Optimization </span> rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <code> d_src </code> </td> 
   <td colname="col2"> <p>Gegevensbron-id of integratiecode van het platform dat de metagegevens levert (bijvoorbeeld DFA, Atlas, GBM, Media Math, enz.). </p> <p>Vereist voor <span class="wintitle"> Audience Optimization </span> rapporten. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <code>gdpr</code>  </td> 
   <td colname="col2"> <p>Gerelateerd aan de <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-invoegtoepassing voor IAB TCF.</a></p> <p><code>gdpr</code> 0 (GDPR is niet van toepassing) of 1 (GDPR is van toepassing).</p> <p>De standaardwaarde is 0.</p><p>Optioneel.</p><p>Als <code>gdpr=1</code>, dan zou de <code>gdpr_consent</code> parameter de de toestemmingsparameter moeten bevatten IAB TC om de gegevens met succes te verwerken. Anders worden alle gegevens verwijderd.</p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <code>gdpr_consent</code> </td> 
   <td colname="col2"> <p>Gerelateerd aan de <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-invoegtoepassing voor IAB TCF.</a></p><p> Als <code>gdpr=1</code>, dan <code>${gdpr_consent_XXXX}</code> wordt vervangen door <code>gdpr_consent</code> koord en verkoper identiteitskaart (zie <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB specificatie</a>).</p> <p>De standaardwaarde is 0.</p><p>Optioneel.</p></td> 
  </tr> 
 </tbody> 
</table>

>[!NOTE]
>
>Neem contact op met uw Adobe Audience Manager-consultant of accountmanager voor de exacte URL die specifiek is voor het clientdomein.

## Aanvullende functionaliteit - [!DNL Audience Optimization Reports] {#additional-functionality-aor}

U kunt pixelvraag gebruiken om [Audience Optimization Rapporten](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md) aan te drijven. Zie [Overzicht en Toewijzingen voor de Dossiers van Meta-gegevens](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) als u wenst om pixel te gebruiken om de rapporten aan te drijven.

>[!MORELIKETHIS]
>
>* [Gegevens- en metagegevensbestanden voor Audience Optimization-rapporten](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

