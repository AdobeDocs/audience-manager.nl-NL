---
description: Met de opties voor samenvoegregels kunt u het type gegevens bepalen dat Audience Manager gebruikt voor segmentatie. Een samenvoegregel kan apparaatprofielen bevatten die zijn toegewezen door de apparaatgrafiek van de Verbinding van het Profiel en/of andere, apparaatgrafiekproviders van derden die zijn geïntegreerd met Audience Manager. U kunt maximaal vier regels voor het samenvoegen van profielen maken.
seo-description: The merge rule options let you control the type of data Audience Manager uses for segmentation. A merge rule can include device profiles mapped by the Profile Link device graph and/or other, third-party device graph providers who are integrated with Audience Manager. You can create a maximum of 4 Profile Merge Rules.
seo-title: Profile Merge Rule Options Defined
solution: Audience Manager
title: Definities van opties voor regels voor profielsamenvoeging.
uuid: 225eeaf7-45e9-4f21-9360-d80a9f90520c
feature: Profile Merge
exl-id: 682d2540-c764-4f5a-a946-5d0e18c66c00
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '789'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] Gedefinieerde opties {#profile-merge-rule-options-defined}

De [!UICONTROL profile merge rule] Met opties kunt u het type gegevens bepalen [!DNL Audience Manager] gebruikt voor segmentatie. A [!UICONTROL profile merge rule] kan apparaatprofielen bevatten die zijn toegewezen door de [!UICONTROL Profile Link] apparaatgrafiek en/of andere, externe apparaatgrafiekproviders die zijn geïntegreerd met [!DNL Audience Manager]. U kunt maximaal 4 [!UICONTROL Profile Merge Rules]. Het vierde [!UICONTROL Profile Merge Rule] uitsluitend beschikbaar is voor klanten die de [!UICONTROL People-Based Destinations] invoegtoepassing.

U maakt een [!UICONTROL Profile Merge Rule] door een keuze te maken uit de hieronder beschreven opties, in [!UICONTROL Profile Merge Rule Setup].

![profile-merge-rule-setup](assets/profile-merge-rule-setup.png)

## [!UICONTROL Profile Merge Rule] Overzicht van opties {#overview}

[!UICONTROL Profile Merge Rules] een aantal regelcombinaties mogelijk te maken, elk gericht op specifieke gebruiksgevallen. Zie de tabel hieronder voor meer informatie over het gebruik van elke regelcombinatie.

| [!UICONTROL Cross-Device Option] | [!UICONTROL Device Option] | Beschikbaarheid | Type evaluatie | [!UICONTROL Audience Lab] Ondersteuning | Gevallen gebruiken |
| ------------------------------ | --------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------- | ----| -------------------- |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL Device Profile] | Alle klanten | Realtime en batch | Ja | [Apparaatgericht](merge-rule-targeting-options.md#device-personalization) |
| [!UICONTROL No Cross-Device Profile] | [!UICONTROL External Device Graph] | Alle klanten | Realtime en batch | Nee | [Uitgebreide doelapparaten](external-graph-use-cases.md#audience-expansion) |
| [!UICONTROL Current Authenticated Profiles] | [!UICONTROL No Device Profile] | Alle klanten | Alleen in realtime | Nee | [Gedeelde apparaatdoelen](merge-rule-targeting-options.md#target-shared-devices) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Device Profile] | Alle klanten | Realtime en batch | Ja | [Online/offline gericht](merge-rule-targeting-options.md#device-household-targeting) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL Profile Link Device Graph] | Alle klanten | Realtime en batch | Ja | [Toewijzing op meerdere apparaten](profile-link-use-case.md#cross-device-personalization) |
| [!UICONTROL Last Authenticated Profiles] | [!UICONTROL External Device Graph] | Alle klanten | Realtime en batch | Nee | [Geavanceerde interDevice-doelen](external-graph-use-cases.md#advanced-graph-expansion) |
| [!UICONTROL All Cross-Device Profiles] | N.v.t. | Exclusief voor [Bestemmingen op basis van personen](../destinations/people-based-destinations-overview.md) klanten | Alleen batch | Nee | [Doelen voor op mensen gebaseerde bestemmingen](merge-rule-targeting-options.md#all-cross-device) |

## [!UICONTROL Profile Merge Rule] [!UICONTROL Segment] Evaluatie {#segment-evaluation}

Afhankelijk van uw [!UICONTROL Profile Merge Rules] configuratie, [!DNL Audience Manager] kan [!UICONTROL segment] evaluatie in real time, in partij, of allebei.

* In real time [!UICONTROL segment] de evaluatie vereist [!DNL DCS] om bezoekers in real-time toegang te geven tot uw digitale eigenschappen, zodat ze in aanmerking komen voor de [!UICONTROL segment].
* Batch [!UICONTROL segment] evaluatie wordt uitgevoerd op basis van eerder gekwalificeerd [!UICONTROL traits].
* [!UICONTROL Profile Merge Rules] die zowel realtime als batch ondersteunen [!UICONTROL segment] de evaluatie combineert de activiteit van de bezoeker in real time met eerder gekwalificeerd [!UICONTROL traits].

## [!UICONTROL Profile Merge Rules] Rapportageachterstand {#reporting-latency}

In real time [!UICONTROL segment] de evaluatie weerspiegelt onmiddellijk de [!UICONTROL Profile Merge Rules] rapporten.

Batch [!UICONTROL segment] de evaluatie kan tot 24 uur duren om in de [Rapporten met regels voor samenvoegen van profielen](profile-link-metrics.md).

## [!UICONTROL Cross-Device Options] {#auth-options}

De [!UICONTROL Cross-Device Options] Hiermee kunt u geverifieerde en niet-geverifieerde gebruikers selecteren en hun apparaatprofiel gebruiken voor segmentatie. Met deze opties kunt u specifieke gebruikers op een gedeeld apparaat identificeren en bereiken. Voor meer informatie over anonieme en voor authentiek verklaarde gebruikers, zie [Verificatiestatus bezoeker in Audience Manager](../../reference/visitor-authentication-states.md).

<table id="table_4CE2DD312F54480E96BEAF72800789FB"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Optie voor meerdere apparaten </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geen profiel voor meerdere apparaten</span></b> </p> </td> 
   <td colname="col2"> <p>Tellen <span class="keyword"> Audience Manager</span> geen gegevens gebruiken die zijn verzameld bij geverifieerde gebruikers. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Huidige geverifieerde profielen</span></b> </p> </td> 
   <td colname="col2"> <p>Tellen <span class="keyword"> Audience Manager</span> om gegevens naar het geverifieerde profiel te lezen en te schrijven als een bezoeker zich bij uw site heeft aangemeld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Laatst geverifieerde profielen</span></b> </p> </td> 
   <td colname="col2"> <p>Tellen <span class="keyword"> Audience Manager</span> om gegevens te lezen van het geverifieerde profiel van de gebruiker die zich het laatst op het apparaat heeft aangemeld. </p> <p>Wanneer geselecteerd, <span class="keyword"> Audience Manager</span> schrijft geen nieuwe gegevens over de eigenschap naar het geverifieerde profiel als de gebruiker anoniem is. Bij verificatie worden nieuwe doelgegevens naar het geverifieerde profiel van de gebruiker geschreven. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Alle profielen voor meerdere apparaten</span></b> </p> </td> 
   <td colname="col2"> <p>Vertelt Audience Manager om gegevens van alle cross-device profielen, ongeacht de authentificatiestatus te lezen. Deze optie is alleen beschikbaar voor klanten van Audience Managers die de invoegtoepassing voor op mensen gebaseerde doelen hebben aangeschaft.</p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL Cross-Device Profile Options] {#profile-options}

De [!UICONTROL Cross-Device Profile Options] bevat uw [!UICONTROL cross-device data sources]. Deze opties gebruiken de namen die u hebt opgegeven toen u een [!UICONTROL cross-device] [!UICONTROL data source] (zie [Een apparaatgegevensbron maken](merge-rules-start.md#create-data-source)). U kunt maximaal 3 selecteren [!UICONTROL cross-device data sources] gebruiken met elke profielregel. De [!UICONTROL Authenticated Profile Options] zijn beschikbaar wanneer u **[!UICONTROL Current Authenticated Profiles]** of **[!UICONTROL Last Authenticated Profiles]**.

## [!UICONTROL Device Options] {#device-options}

De [!UICONTROL Device Options] Hiermee kunt u het type *`device profile`* gebruikt door een [!UICONTROL Profile Merge Rule]. Een apparaatprofiel is gemaakt van [!UICONTROL traits] verzameld bij anonieme browseractiviteiten. Ten minste [!UICONTROL profile merge rule] bevat een [!UICONTROL authenticated option] en [!UICONTROL device option].

<table id="table_D373FB787D1A4E3485C02C4A76F03395"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Apparaatoptie </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Geen apparaatprofiel</span></b> </p> </td> 
   <td colname="col2"> <p>Tellen <span class="keyword"> Audience Manager</span> de kenmerken in het anonieme profiel niet gebruiken voor segmentatie. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Apparaatprofiel</span></b> </p> </td> 
   <td colname="col2"> <p>Tellen <span class="keyword"> Audience Manager</span> om het anonieme apparatenprofiel voor segmentatie te gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Apparaatgrafiek profielkoppeling</span></b> </p> </td> 
   <td colname="col2"> <p>Tellen <span class="keyword"> Audience Manager</span> om de profielen van het huidige apparaat en tot 100 andere apparaten te lezen die de gebruiker van authentiek heeft verklaard. Deze apparaatgrafiek is gebaseerd op uw eigen gegevens van de eerste partij <span class="keyword"> Audience Manager</span>. Dit is ideaal voor klanten die een hoog verificatieniveau hebben voor hun digitale eigenschappen. De <span class="wintitle"> Profielkoppeling</span> apparaatgrafiek wordt in real-time bijgewerkt. Deze optie is beschikbaar wanneer u <b><span class="uicontrol"> Huidig geverifieerd profiel</span></b> of <b><span class="uicontrol"> Laatst geverifieerd profiel</span></b>. Als u deze optie gebruikt, kunt u slechts één geverifieerd profiel kiezen (<span class="keyword"> Audience Manager</span> worden de andere automatisch uitgegrijsd). Zie ook: <a href="profile-link-use-case.md"> Gebruiksscenario's voor grafiekgebruik van profielkoppeling</a>. </p> </td>
  </tr>

<tr> 
   <td colname="col1"> <p><b>Grafiekopties van externe apparaten</b> (Persoon en huishouden) </p> </td>
   <td colname="col2"> <p>Met deze opties kunt u fusieregels samenstellen op basis van apparaatgrafiektechnologie die door een externe leverancier wordt geleverd. Een apparaatgrafiek van derden biedt de volgende mogelijkheden: </p> <p> 
     <ul id="ul_5BA0D940BA15484FADF134A5A73815D5"> 
      <li id="li_389ACEBBF79A47499B6119B0F9CB3B5D"> Probabilistische en/of deterministische gegevens. </li> 
      <li id="li_E8606D3871A145A68E87BDC3554AC4EF">Gegevens per persoon of per huishouden. </li> 
     </ul> </p> <p>Als u deze opties wilt gebruiken, moet u een klant zijn van een apparaatgrafiek die al is geïntegreerd met <span class="keyword"> Audience Manager</span>. Neem contact op met uw accountmanager voor meer informatie of om aan de slag te gaan. </p> </td>
  </tr>
 </tbody>
</table>

## [!UICONTROL External Merge Policies] {#external-merge-policies}

De segmenten van het publiek die automatisch van andere werden gecreeerd [!DNL Experience Cloud] oplossingen, gebaseerd op fusieregels die buiten [!DNL Audience Manager], gemarkeerd zijn als een [!UICONTROL External Merge Policy]. Zie bijvoorbeeld [Publiek delen tussen Audience Manager en Adobe Experience Platform](../../integration/integration-aep/aam-aep-audience-sharing.md).

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

