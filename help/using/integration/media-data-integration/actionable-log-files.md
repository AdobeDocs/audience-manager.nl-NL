---
description: Met uitvoerbare logbestanden kunt u mediasignalen vastleggen uit logbestanden van een server om kenmerken in Audience Manager te maken. Leg impressies, kliks en conversies van advertentieservers vast als kenmerken zonder dat u pixels hoeft toe te voegen.
keywords: actioneerbare stammen, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: Werkbare logbestanden
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1601'
ht-degree: 1%

---

# Werkbare logbestanden {#actionable-log-files}

Met [!UICONTROL Actionable Log Files] kunt u mediagegevens vastleggen uit logbestanden van advertenties en de gegevens gebruiken om kenmerken in Audience Manager te maken. Vang impressies, klikken, en omzettingen van advertentieservers als eigenschappen zonder het moeten [ pixel ](../../integration/media-data-integration/impression-data-pixels.md) toevoegen.

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, steunen `[ ]` `( )`, enz.) in dit document wijzen op codeelementen en opties. Zie [Stijlconventies voor code- en tekstelementen](../../reference/code-style-elements.md) voor meer informatie.

## Doel {#purpose}

[!UICONTROL Actionable Log Files] stroomlijnt de manier waarop u afbeeldingen vastlegt, klikt en conversies vanaf advertentieservers. Gebruik deze informatie voor gebruikerssegmentatie zonder dat u handmatig media in pixels hoeft te plaatsen om campagnerekenmerken naar [!DNL Audience Manager] te verzenden.

## Aan de slag {#getting-started}

Als u aan de slag wilt met [!UICONTROL Actionable Log Files] , moet u loggegevens importeren in [!DNL Audience Manager] . Aan de slag met de volgende koppelingen:

* Voor [!UICONTROL Google Campaign Manager] logboeken, zie [ de Dossiers van de Gegevens van de Manager van de Campagne van de Invoer Google in Audience Manager ](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *en* contact uw [!DNL Audience Manager] adviseur.
* Voor [!UICONTROL Google Ad Manager] (vroeger Google DFP) logboeken, zie [ de Dossiers van de Gegevens van Google en van de Manager van de Manager van de Invoer in Audience Manager ](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *en* contacteer uw [!DNL Audience Manager] consultant.
* Voor andere logboekregistraties van de advertentieserver, zie [ Gegevens en de Dossiers van Meta-gegevens ](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *en* contact uw [!DNL Audience Manager] adviseur.

Als u reeds logboekgegevens in [!DNL Audience Manager] invoert, vraag uw [!DNL Audience Manager] consultant of [ de Zorg van de Klant ](https://helpx.adobe.com/nl/contact/enterprise-support.ec.html) om [!UICONTROL Actionable Log Files] voor u toe te laten.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/nl/contact/enterprise-support.ec.html) to get started.

-->

## Werken met uitvoerbare logbestanden {#working-with-actionable-log-files}

Met [!UICONTROL Actionable Log Files] wordt de informatie van serverlogboeken voor advertenties in [!DNL Audience Manager] op dezelfde manier vastgelegd als gegevens van interacties van realtime websites. [!DNL Audience Manager] verbindt met uw opslag van het de serverlogboek van de advertentie, ontleedt de informatie van de logboeken, en verzendt de logboekgegevens als activeerbare signalen naar onze [ Servers van de Inzameling van Gegevens ](../../reference/system-components/components-data-collection.md#dcs-pcs).

U moet nog opstelling op regel-gebaseerde eigenschappen om de handelingssignalen te vangen. Zie hoe te opstelling op regel-gebaseerde eigenschappen of in het [ gebruikersinterface van Audience Manager ](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) of het gebruiken van onze [ BulkHulpmiddelen van het Beheer ](../../reference/bulk-management-tools/bulk-create.md). De rol neer aan de [ Acteerbare Signalen ](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) sectie voor een lijst van alle sleutels u in op regel-gebaseerde eigenschappen kunt gebruiken.

>[!IMPORTANT]
>
>Wij adviseren uitvoerend [!UICONTROL Actionable Log Files] *in plaats van* [ Vraag van het Pixel ](../../integration/media-data-integration/impression-data-pixels.md). We ontmoedigen het gebruik van beide opties, omdat dit leidt tot een toename van het aantal frequenties voor kenmerken.

## Handbare signalen {#actionable-signals}

De signalen zijn de [ kleinste gegevenseenheden ](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. Met [!UICONTROL Actionable Log Files] kunt u adverteerders, bedrijfseenheden, creatieve en campagnewaarden vastleggen in imitatiegebeurtenissen, gebeurtenissen en conversiegebeurtenissen als signalen van serverlogboeken voor advertenties.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] worden ondersteund voor de volgende advertentieservers:
>&#x200B;> <br>
>
> * [ de Manager van de Campagne van Google ](#dcm-logs-signals)
> * [ Google Advertentiemanager ](#ad-manager-logs-signals)
> * [ de Wolk van Adobe Advertising, Flashtalk, en Sizmek ](#generic-logs-signals)

Herinner me, om deze informatie voor publieksverwezenlijking en segmentatie te gebruiken, moet u opstelling de op regel-gebaseerde trekken zelf.

### Handbare signalen uit Google Campagne Manager-logboeken {#dcm-logs-signals}

De tabel bevat een lijst met actiemotionele signalen uit logbestanden van [!DNL Google Campaign Manager] :

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Naam koptekst in logbestand </th> 
   <th colname="col2" class="entry"> Signaal </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
   <th colname="col4" class="entry"> Voorbeeldwaarde </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Activity ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_conversion</code> </p> </td> 
   <td colname="col3"> <p>Alleen beschikbaar voor conversiegebeurtenissen. </p> <p>Vertegenwoordigt numerieke id voor de omzettingsactiviteit in de Manager van de Campagne van Google. Dit veld verwijst naar de activiteit-id van Google Campagne Manager. </p> <p> <p>Tip: u kunt meerdere of specifieke conversieactiviteiten vastleggen vanuit Google Campagne Manager. Maak kenmerken met <code> d_conversion = activity ID</code> voor elke conversieactiviteit in Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Alleen beschikbaar voor conversiegebeurtenissen. </p> <p>Dit veld wordt toegewezen aan de conversie-id in Google Campaign Manager. Geeft de activiteit aan die voorafgaat aan de gebruikersconversie vanuit Google Campaign Manager. </p> <p>Accepteerde waarden zijn: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> voor conversies na klikken. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> voor conversies na impressie. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> voor niet-overeenkomende conversies. De conversie kan niet worden gekoppeld aan een eerdere activiteit. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Een UTC-datum en -tijd voor de impositie, klik of conversiegebeurtenis. Vertegenwoordigde in microseconden sinds 1970-01-01 00 :00: 00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Een integratiecode voor de gegevensbron van uw adverteerder. Dit heeft geen betrekking op Audience Manager-gegevensbronnen.</p> <p>Dit veld wordt toegewezen aan de Advertiser Group ID uit Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Bedrijfs-eenheid-id. Dit veld wordt toegewezen aan de advertentie-id van Google Campagne Manager. </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>De campagne-id van Google Campaign Manager.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>De Creative-id van Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> De verkoop in USD, tot een macht van -6. Vermenigvuldig met 1.000.000 om als een dollarbedrag te zien.</td> 
   <td colname="col4"> <p> <code>10</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Geeft het gebeurtenistype aan. Audience Manager leest het gebeurtenistype uit de naam van het logbestand van Google Campaign Manager en zet het om in een actionable signaal. </p> <p>Accepteerde waarden zijn: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> voor afbeeldingen. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> voor klikken. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> voor conversies. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>De id van de gegevensbron die u gebruikt om gegevens van Google Campaign Manager vast te leggen. Zie <a href="../../features/manage-datasources.md#create-data-source"> Hoe te om een Gegevens Source </a> te creëren. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

De signalen die in de tabel worden beschreven, worden in [!DNL Audience Manager] vastgelegd als een realtime `HTTP` -aanroep. De onderstaande voorbeeldaanroep bevat informatie over een conversiegebeurtenis vanuit [!DNL Google Campaign Manager] . De vraag moet niet noodzakelijk *alle* de signalen in de voorbeeldvraag omvatten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Voor een logbestand met gemiddelde grootte van [!DNL Google Campaign Manager] van 2 miljoen regels worden alle kenmerken die zijn gemaakt op basis van actioneerbare signalen, uitgevoerd binnen ongeveer een uur nadat we de logbestanden hebben verwerkt.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>De tijdstempel van de gebeurtenis die in de logbestanden van [!DNL Google Campaign Manager] wordt opgegeven, wordt gerespecteerd en doorgegeven aan [!UICONTROL Data Collection Servers] .
>
>* Als er geen tijdstempel beschikbaar is voor een gegevensrij in het logbestand van [!DNL Google Campaign Manager] , gebruiken we de tijd van de aanroep van `HTTP` als tijdstempel voor de gebeurtenis.
>* Als de gegevensrij in het logbestand van [!DNL Google Campaign Manager] een verkeerd geformuleerde tijdstempel bevat, wordt de hele rij genegeerd.

<br>

### Handbare signalen van [!DNL Google Ad Manager] logs {#ad-manager-logs-signals}

De tabel bevat een lijst met actiemotionele signalen uit logbestanden van [!DNL Google Ad Manager] :


| Naam koptekst in logbestand | Signaal | Beschrijving |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | De numerieke id voor het geleverde regelitem Advertentiebeheer |
| `OrderId` | `d_orderid` | De numerieke id voor de volgorde van Advertentiebeheer waarin het geleverde regelitem en de creatieve functie zijn opgenomen. |
| `CreativeId` | `d_creative` | De numerieke id voor de geleverde advertentiemanager. |
| `-` | `d_event` | Geeft het gebeurtenistype aan. Audience Manager leest het gebeurtenistype uit de naam van het logbestand van AdvertentiManager en zet het om in een actionable signaal. Accepteerde waarden zijn: <br> <ul><li>d_event = imp voor impressies.</li><li>d_event = click voor kliks.</li><li>d_event = conv voor conversies en activiteiten.</li></ul> |
| `-` | `d_src` | De id van de gegevensbron die u gebruikt om Advertentiebeheergegevens vast te leggen. Zie [ hoe te om een Gegevens Source ](/help/using/features/manage-datasources.md) te creëren. |

De signalen die in de tabel worden beschreven, worden in Audience Manager vastgelegd als een realtime HTTP-aanroep. De onderstaande voorbeeldaanroep bevat informatie over een conversiegebeurtenis van Google Ad Manager. De vraag moet niet noodzakelijk alle signalen in de voorbeeldvraag omvatten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>De tijdstempel van de gebeurtenis die in de logbestanden van [!DNL Google Ad Manager] wordt opgegeven, wordt gerespecteerd en doorgegeven aan [!UICONTROL Data Collection Servers] .
>
>
>* Als er geen tijdstempel beschikbaar is voor een gegevensrij in het logbestand van [!DNL Google Ad Manager] , gebruiken we de tijd van de aanroep van `HTTP` als tijdstempel voor de gebeurtenis.
>* Als de gegevensrij in het logbestand van [!DNL Google Ad Manager] een verkeerd geformuleerde tijdstempel bevat, wordt de hele rij genegeerd.

<br>

### Handbare signalen van Adobe Advertising Cloud, Flash Talk en Sizmek en server logs {#generic-logs-signals}

Eerst moet u uw aanmeldingen bij de advertentieserver deponeren in de Amazon S3-emmers. Om dit te verwezenlijken, lees {de Dossiers van 0} Gegevens voor de Rapporten van Audience Optimization en de Geschikte Dossiers van het Logboek [&#128279;](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) en *contacteer uw* adviseur. [!DNL Audience Manager] De tabel bevat een lijst met actiemogelijkheden van logbestanden van advertentieservers:

<table id="table_A5A2A10D471C4C9D8DCD88F9C017040C"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Naam koptekst in logbestand </th> 
   <th colname="col2" class="entry"> Signaal </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
   <th colname="col4" class="entry"> Voorbeeldwaarde </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code>Event-Type</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Geeft aan of een conversie overeenkomt of niet. U kunt onder andere de volgende opties kiezen: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impressie </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Klik </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Niet toegewezen of onbekend </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Een UTC-datum en -tijd voor de impositie, klik of conversiegebeurtenis. Gebruik de <code>yyyy-MM-dd HH:mm:ss</code> -indeling. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Een integratiecode voor de gegevensbron van uw adverteerder. Merk op dat dit gebied niet met <a href="../../features/datasources-list-and-settings.md"> Audience Manager gegevensbronnen verwant is.</a></p></td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>BU-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Bedrijfs-eenheid-id.  </p> </td> 
   <td colname="col4"> <p> <code> 563332</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Campaign-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_campaign</code> </p> </td> 
   <td colname="col3"> <p>De campagne-id uit het logbestand.</p> </td> 
   <td colname="col4"> <p> <code> 7892520</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Creative-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_creative</code> </p> </td> 
   <td colname="col3"> <p>De Creative-id uit het logbestand. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Aankoop of ander omrekeningsbedrag. Gegevenstype: Zwevend. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Geeft het gebeurtenistype aan. Audience Manager leest het gebeurtenistype uit de naam van het logbestand en zet het om in een actionabel signaal. Zie <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions"> logboekdossiers noemend overeenkomsten </a>. </p> <p>Accepteerde waarden zijn: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> voor afbeeldingen. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> voor klikken. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> voor conversies. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>De id van de gegevensbron die u gebruikt om logboekgegevens vast te leggen. Zie <a href="../../features/manage-datasources.md#create-data-source"> Hoe te om een Gegevens Source </a> te creëren. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

De signalen die in de tabel worden beschreven, worden in [!DNL Audience Manager] vastgelegd als een realtime `HTTP` -aanroep. De vraag moet niet noodzakelijk *alle* de signalen in de voorbeeldvraag omvatten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Werken met Handbare signalen in de Audience Manager-gebruikersinterface {#actionable-signals-in-ui}

U kunt uw inkomende actionable signalen in het [ Signals Onderzoek ](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) interface bekijken.

Ga naar **Gegevens van het publiek** (1) > **Signalen** (2) > **Onderzoek** (3) en selecteer de **Actiebare filter van de Dossiers van het Logboek** (4).

![ Handelbare Signalen in UI ](/help/using/integration/assets/alf-in-signals.png)

Om op regel-gebaseerde treinen tot stand te brengen die uw actionable signalen gebruiken, de uitgezochte **Actiebare Dossiers van het Logboek** (1), selecteert de actioneerbare signalen die u als eigenlijke regels (2) wilt gebruiken, en drukt **tot Spoor van Geselecteerde Signalen** (3).

![ creeer eigenschappen van signalen ](/help/using/integration/assets/alf-create-trait.png)


## Gevallen gebruiken {#use-cases}

Één voordeel om [!UICONTROL Actionable Log Files] uit te voeren is de optie om [ recentie en frequentie ](../../features/segments/recency-and-frequency.md) controles op om het even welke [ op regel-gebaseerde eigenschappen ](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) toe te passen die actionable signalen bevatten. Zo kunt u bijvoorbeeld het aantal keren dat een gebruiker een bepaald creatief programma ziet, in een mediacampagne beperken. Lees [ Onmiddellijke Onderdrukking van dwars-Apparaat ](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) om te leren hoe te om dit te doen. Andere gebruiksgevallen zijn:

### Gebruikers opnieuw toewijzen

Ga gebruikers terug die creatieve 123 zagen maar niet klikte of omzet en hen creatieve 456 tonen. Doe dit:

1. Maak een eigenschap om gebruikers vast te leggen die de creatieve foto&#39;s hebben gezien. Laten we zeggen dat u de eigenschap [!DNL Creative Trait 123] noemt. Gebruik de regel Actief:

   `d_creative == 123 AND d_event == imp`

2. Maak een eigenschap om gebruikers vast te leggen die klikken of converteren. Laten we zeggen dat je deze [!DNL Click and Converter] noemt. Gebruik de regel Actief:

   `d_event == click OR d_event=conv`

3. Maak een segment om te vullen met gebruikers die creatieve 123 hebben gezien, maar niet hebben geklikt of geconverteerd. Noem het [!DNL Retarget Users] en gebruik de segmentregel:

   `Creative Trait 123 AND NOT Click and Converter`

4. Wijs het segment [!DNL Retarget Users] toe aan een doel en doelgebruikers in de bestemming met creatief 456.

### De activiteit van de Manager van de Campagne van Google van het gebruik de Vullight in de Rapporten van Audience Optimization of in het Laboratorium van het Publiek

[ de markeringen van de Vullingslicht ](https://support.google.com/dcm/partner/answer/4293719?hl=en) laten adverteerders toe om gebruikersomzettingen te volgen. Met [!UICONTROL Actionable Log Files], kunt u de [!DNL Google Campaign Manager] omzettingen in de [ Rapporten van Audience Optimization ](../../reporting/audience-optimization-reports/audience-optimization-reports.md) of in [ Laboratorium van de Publiek ](../../features/audience-lab/audience-lab.md) volgen:

1. Maak een kenmerk en gebruik de volgende regel voor het vastleggen van een conversie van de logboeken van de advertentieserver:

   `d_event == conv AND d_conversion == 123`

   Wanneer u de eigenschap maakt in de Audience Manager [!UICONTROL UI] , selecteert u [!UICONTROL Conversion] als de [!UICONTROL Event Type] .

2. Nadat u de eigenschap hebt gemaakt, wordt de conversie gerapporteerd in de [!UICONTROL Audience Optimization Reports] en in [!UICONTROL Audience Lab] .

>[!MORELIKETHIS]
>
>* [ de Dossiers van de Gegevens van de Manager van de Campagne van Google in Audience Manager ](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Audience Optimization-rapporten](../../reporting/audience-optimization-reports/audience-optimization-reports.md)
