---
description: Klik op bijhouden om de betrokkenheid van bezoekers tijdens uw campagne te meten, aangezien hierin op klikken gebaseerde activiteiten voor creatieve derden worden vastgelegd.
seo-description: Klik op bijhouden om de betrokkenheid van bezoekers tijdens uw campagne te meten, aangezien hierin op klikken gebaseerde activiteiten voor creatieve derden worden vastgelegd.
seo-title: Klikdata campagne vastleggen via pixelcalls
solution: Audience Manager
title: Klikdata campagne vastleggen via pixelcalls
uuid: 7c3797f7-9674-493d-972b-38be0584fede
feature: Integration with Campaign
translation-type: tm+mt
source-git-commit: 231d8e537cf5b4f29b1c4f284fe1b3ffe6d187a9
workflow-type: tm+mt
source-wordcount: '686'
ht-degree: 10%

---


# Klikdata campagne vastleggen via pixelcalls {#capturing-campaign-click-data-via-pixel-calls}

Klik op bijhouden om de betrokkenheid van bezoekers tijdens uw campagne te meten, aangezien hierin op klikken gebaseerde activiteiten voor creatieve derden worden vastgelegd. Vergelijkbaar met [impressions collection](/help/using/integration/media-data-integration/impression-data-pixels.md), wordt een gebeurtenisvraag verzonden naar [!DNL Audience Manager] de servers van de gegevensinzameling ([!DNL DCS]) voor verwerking. De bezoeker wordt dan omgeleid aan het voorgenomen Webadres.

>[!NOTE]
>
>Neem contact op met uw [!DNL Audience Manager] consultant of accountmanager voor de exacte [!DNL URL] die specifiek is voor het clientdomein.

## Vereisten

Klik volgende het volgen vraag vereist de volgende parameters:

* `d_event=click`: Een sleutel-waarde paar dat een gebeurtenisvraag als klikgebeurtenis identificeert.
* `d_rd=redirect URL`: Een sleutelwaardepaar dat een dubbel-gecodeerde omleiding bevat  [!DNL URL]. Als u een online het coderen hulpmiddel gebruikt, stel het koord door de codeermodule in werking, dan codeer opnieuw het resultaat, zodat omleiding werkt.

Daarnaast kan de aanroep sleutelwaardeparen bevatten die kunnen worden gebruikt voor vakkwalificatie of voor het verschaffen van gegevens en metagegevens voor andere rapporten.

## Voorbeeld aanvragen

```
https://client.demdex.net/event?d_event=click&d_creative=123&d_rd=http%3A%2F%2Fadobe.com%2Fcallback%3Fcreative%3D%25d_creative%25
```

## Antwoord

De reactie leidt de browser om naar de [!DNL URL] die in de `d_rd` parameter wordt gespecificeerd. De responstekenreeks kan waarden bevatten die worden gegenereerd door elk van de hieronder vermelde ondersteunde macro&#39;s.

Op basis van het bovenstaande voorbeeld wordt de browser omgeleid naar [!DNL URL]:

`https://adobe.com/callback?creative=123`

## Ondersteunde macro&#39;s

Klik op gebeurtenissen om de macro&#39;s in de volgende tabel te ondersteunen. Een macro is een kleine eenheid op zichzelf staande code die wordt geactiveerd wanneer de tag ad wordt geladen voor het bijhouden van campagnes en gebruikers. De macro&#39;s worden samen met het doel [!DNL URL] doorgegeven, mits deze met de volgende indeling worden gemarkeerd: `%macro%`. Sommige toetsen hebben geen macro&#39;s en accepteren in plaats daarvan een hard gecodeerde id-waarde. Toetsen die harde gecodeerde waarden accepteren, zijn vereist als u gegevens wilt analyseren in [Audience Optimization Reports](../../reporting/audience-optimization-reports/audience-optimization-reports.md).

<table id="table_6EB65C3B7D0E49C59AA6C932549E33FC"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Sleutel </th> 
   <th colname="col02" class="entry"> Macro </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> d_adgroup</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_adgroup%</code> </p> </td> 
   <td colname="col2"> <p>Numerieke id van advertentiegroep van de advertentieserver. </p> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col02"> <p>Geen macro. </p> <p>Accepteert een hard gecodeerde ID-waarde. </p> </td> 
   <td colname="col2"> <p>Advertiser-id.</p> <p>Een integratiecode voor de gegevensbron van uw adverteerder. Merk op dat dit niet met de gegevensbronnen van de Audience Manager verwant is.</p> <p> Vereist voor <span class="wintitle"> Audience Optimization</span> rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_bu%</code> </p> </td> 
   <td colname="col2"> <p>Numerieke id voor de bedrijfseenheid. </p> <p> Vereist voor <span class="wintitle"> Audience Optimization</span> rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_campaign%</code> </p> </td> 
   <td colname="col2"> <p>Numerieke campagne-id van de advertentieserver. </p> <p> Vereist voor <span class="wintitle"> Audience Optimization</span> rapporten. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_creative%</code> </p> </td> 
   <td colname="col2"> <p>Numerieke creatieve id van de advertentieserver. </p> <p>Vereist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_id%</code> </p> </td> 
   <td colname="col2"> <p>ID gegevensaanbieder. </p> <p>Wordt vaak gebruikt met <code> d_dpuuid</code> om een gegevensleverancier-id te koppelen aan een gebruikers-id. </p> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_dpuuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_dpuuid%</code> </p> </td> 
   <td colname="col2"> <p>De unieke gebruikersnaam die door de gegevensaanbieder is opgegeven. </p> <p>Wordt vaak gebruikt met <code> d_dpid</code> om een gebruikers-id te koppelen aan een gegevensaanbieder-id. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code> d_mid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_mid%</code> </p> </td> 
   <td colname="col2"> <p> <span class="keyword"></span> Experience Cloud ID (ECID). Zie <a href="https://docs.adobe.com/content/help/nl-NL/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies en de Experience Cloud-id</a> voor meer informatie over de ECID. </p> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_placement</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_placement%</code> </p> </td> 
   <td colname="col2"> <p>Numerieke plaatsing-id van de advertentieserver. </p> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_region</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_region%</code> </p> </td> 
   <td colname="col2"> <p>De numerieke regio-id voor de DCS-cluster die een aanvraag verzorgt. Voor meer informatie over DCS, zie <a href="../../reference/system-components/components-data-collection.md"> Componenten van de Inzameling van Gegevens</a>. </p> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> r_rand</code> </p> </td> 
   <td colname="col02"> <p> <code> %r_rand%</code> </p> </td> 
   <td colname="col2"> <p>Willekeurig nummer dat wordt gebruikt voor het busten van cache. </p> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_site</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_site%</code> </p> </td> 
   <td colname="col2"> <p>Numerieke site-id van de advertentieserver. </p> <p>Optioneel. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_src</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_src%</code> </p> </td> 
   <td colname="col2"> <p>DPID van de bron van waar de Audience Manager de meta-gegevens trekt. </p> <p>Vereist. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> d_uuid</code> </p> </td> 
   <td colname="col02"> <p> <code> %d_uuid%</code> </p> </td> 
   <td colname="col2"> <p>Geef de id van de bezoeker rechtstreeks op in de URL in plaats van te vertrouwen op het demdex-cookie. </p> <p>Optioneel. </p> </td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr}</code> </p> </td> 
   <td colname="col2"> <p>Gerelateerd aan de <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-invoegtoepassing voor IAB TCF.</a> </p><p><code>gdpr</code> 0 (GDPR is niet van toepassing) of 1 (GDPR is van toepassing).</p> <p>De standaardwaarde is 0.</p><p>Optioneel.</p></td> 
  </tr> 
   <tr> 
   <td colname="col1"> <p> <code>gdpr_consent</code> </p> </td> 
   <td colname="col02"> <p> <code>${gdpr_consent_XXXX}</code> </p> </td> 
   <td colname="col2"> <p>Gerelateerd aan de <a href="../../overview/data-security-and-privacy/aam-iab-plugin.md">Audience Manager-invoegtoepassing voor IAB TCF.</a></p><p> Als <code>gdpr=1</code>, dan <code>${gdpr_consent_XXXX}</code> wordt vervangen door <code>gdpr_consent</code> koord en verkoper identiteitskaart (zie <a href="https://github.com/InteractiveAdvertisingBureau/GDPR-Transparency-and-Consent-Framework/blob/master/TCFv2/IAB%20Tech%20Lab%20-%20Consent%20string%20and%20vendor%20list%20formats%20v2.md#about-the-transparency--consent-string-tc-string" format="http" scope="external"> IAB specificatie</a>).</p> <p>De standaardwaarde is 0.</p><p>Optioneel.</p></td> 
  </tr> 
 </tbody> 
</table>

## Voorbeeld van macro&#39;s

In dit voorbeeld ziet u hoe u de macro&#39;s creative, adgroup en placement doorgeeft. Het veronderstelt de waarden voor elke parameter in het non-redirect gedeelte van de klik-volgende vraag worden overgegaan.

<ul class="simplelist"> 
 <li> <code> creative=1235 </code> </li> 
 <li> <code> campaign=4709 </code> </li> 
 <li> <code> adgroup=3408 </code> </li> 
 <li> <code> placement=1001 </code> </li> 
 <li> <code> src=203 </code> </li> 
</ul>

## Verzoek

```
https://client.demdex.net/event?d_event=click&d_creative=1235&d_src=203&d_campaign=4709&d_adgroup=3408&d_placement=1001&
d_rd%3Dhttp%253A%252F%252Fadobe.com%252Fcallback%253Fcreative%253D%2525d_creative%2525%2526campaign%253D%2525d_campaign%2525%2526adgroup%253D%2525%0Ad_adgroup%2525%2526d_placement%253D%2525placement%2525%2526src%253D%2525d_src%2525
```

## Antwoord

Op basis van het bovenstaande voorbeeld wordt de browser omgeleid naar [!DNL URL]:

`https://adobe.com/callback?creative=1235&campaign=4709&adgroup=3408&placement=1001`

## Aanvullende functionaliteit - [!UICONTROL Audience Optimization Reports]

U kunt pixelvraag gebruiken om [Audience Optimization Rapporten](/help/using/reporting/audience-optimization-reports/audience-optimization-reports.md) aan te drijven. Zie [Overzicht en Toewijzingen voor de Dossiers van Meta-gegevens](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-file-overview.md) als u wenst om pixel te gebruiken om de rapporten aan te drijven.


>[!MORELIKETHIS]
>
>* [Gegevens- en metagegevensbestanden voor Audience Optimization-rapporten](../../reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md)

