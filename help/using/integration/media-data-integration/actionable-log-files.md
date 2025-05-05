---
description: Met uitvoerbare logbestanden kunt u mediasignalen vastleggen uit logbestanden van een server om kenmerken in Audience Manager te maken. Leg impressies, kliks en conversies van advertentieservers vast als kenmerken zonder dat u pixels hoeft toe te voegen.
keywords: actioneerbare stammen, alf, ALF
seo-description: Actionable Log Files allow you to capture media signals from ad server log files to create traits in Audience Manager. Capture impressions, clicks, and conversions from ad servers as traits without having to append pixels.
seo-title: Actionable Log Files
solution: Audience Manager
title: Actiegerichte logboekbestanden
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Log Files
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: b3f97cfbbd5167f03a6951fcc571368e4a0d15a4
workflow-type: tm+mt
source-wordcount: '1596'
ht-degree: 2%

---

# Actiegerichte logboekbestanden {#actionable-log-files}

[!UICONTROL Actionable Log Files] Hiermee kunt u mediagegevens vastleggen uit logbestanden van een advertentieserver en de gegevens gebruiken om eigenschappen in Audience Manager te maken. Leg impressies, klikken en conversies van advertentieservers vast als onderdelen zonder dat u deze hoeft toe te voegen [pixels](../../integration/media-data-integration/impression-data-pixels.md).

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, haakjes `[ ]` `( )`, enz.) in dit document de elementen en opties van de code aangeven. Zie [Stijlconventies voor code- en tekstelementen](../../reference/code-style-elements.md) voor meer informatie.

## Doel {#purpose}

[!UICONTROL Actionable Log Files] stroomlijnt de manier waarop u impressies vastlegt, klikt en conversies vanaf advertentieservers. Gebruik deze informatie voor gebruikerssegmentatie zonder handmatig media in pixels te moeten verzenden om campagnekenmerken naar te sturen [!DNL Audience Manager].

## Aan de slag {#getting-started}

Aan de slag met [!UICONTROL Actionable Log Files], moet u logboekgegevens invoeren in [!DNL Audience Manager]. Aan de slag met de volgende koppelingen:

* Voor [!UICONTROL Google Campaign Manager] logboeken, zie [Google Campagne Manager-gegevensbestanden importeren in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *en* contact opnemen met [!DNL Audience Manager] consultant.
* Voor [!UICONTROL Google Ad Manager] (voorheen Google DFP) logs, zie [Google Ad Manager-gegevensbestanden importeren in Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *en* contact opnemen met [!DNL Audience Manager] consultant.
* Zie voor andere aanmeldingen op de advertentieserver [Gegevens- en metagegevensbestanden](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *en* contact opnemen met [!DNL Audience Manager] consultant.

Als u al loggegevens importeert in [!DNL Audience Manager], vraag uw [!DNL Audience Manager] consultant of [Klantenservice](https://helpx.adobe.com/nl/contact/enterprise-support.ec.html) om [!UICONTROL Actionable Log Files] voor jou.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/nl/contact/enterprise-support.ec.html) to get started.

-->

## Werken met uitvoerbare logbestanden {#working-with-actionable-log-files}

Met [!UICONTROL Actionable Log Files], wordt de informatie van serverlogboeken voor advertenties vastgelegd in [!DNL Audience Manager] dezelfde manier waarop u gegevens vastlegt van realtime-websiteinteracties. [!DNL Audience Manager] verbindt met uw opslag van het het logboeklogboek van de advertentieserver, ontleedt de informatie van de logboeken, en verzendt de logboekgegevens als activeerbare signalen naar ons [Gegevensverzamelingsservers](../../reference/system-components/components-data-collection.md#dcs-pcs).

U moet nog opstelling op regel-gebaseerde eigenschappen om de handelingssignalen te vangen. Zie hoe te opstelling op regel-gebaseerde eigenschappen of in [Gebruikersinterface Audience Manager](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) of met onze [Bulkbeheertools](../../reference/bulk-management-tools/bulk-create.md). Omlaag schuiven naar de [Handbare signalen](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) voor een lijst van alle sleutels u in op regel-gebaseerde eigenschappen kunt gebruiken.

>[!IMPORTANT]
>
>We raden u aan om [!UICONTROL Actionable Log Files] *in plaats van*  [Pixelaanroepen](../../integration/media-data-integration/impression-data-pixels.md). We ontmoedigen het gebruik van beide opties, omdat dit leidt tot een toename van het aantal frequenties voor kenmerken.

## Handbare signalen {#actionable-signals}

Signalen zijn de [kleinste gegevenseenheden](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] kunt u adverteerders, bedrijfseenheden, creatieve en campagnewaarden vastleggen in imitatiegebeurtenissen, gebeurtenissen en conversiegebeurtenissen als signalen van serverlogboeken voor advertenties klikken.

>[!IMPORTANT]
>
>[!UICONTROL Actionable Log Files] worden ondersteund voor de volgende advertentieservers:
> <br>
>
> * [Google Campagne Manager](#dcm-logs-signals)
> * [Google Ad Manager](#ad-manager-logs-signals)
> * [Adobe Advertising Cloud, Flashtalk en Sizmek](#generic-logs-signals)


Herinner me, om deze informatie voor publieksverwezenlijking en segmentatie te gebruiken, moet u opstelling de op regel-gebaseerde trekken zelf.

### Handbare signalen uit Google Campagne Manager-logboeken {#dcm-logs-signals}

De tabel bevat de actiefsignalen van [!DNL Google Campaign Manager] logbestanden:

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
   <td colname="col3"> <p>Alleen beschikbaar voor conversiegebeurtenissen. </p> <p>Vertegenwoordigt numerieke id voor de omzettingsactiviteit in de Manager van de Campagne van Google. Dit veld verwijst naar de activiteit-id van Google Campagne Manager. </p> <p> <p>Tip: U kunt meerdere of specifieke conversieactiviteiten vastleggen vanuit Google Campagne Manager. Kenmerken maken met <code> d_conversion = activity ID</code> voor elke conversieactiviteit van Google Campaign Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Alleen beschikbaar voor conversiegebeurtenissen. </p> <p>Dit veld wordt toegewezen aan de conversie-id in Google Campaign Manager. Geeft de activiteit aan die voorafgaat aan de gebruikersconversie vanuit Google Campaign Manager. </p> <p>Accepteerde waarden zijn: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 1</code> voor conversies na klikken. </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 2</code> voor postimpressie. </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> 0</code> voor niet-gematchte omzettingen. De conversie kan niet worden gekoppeld aan een eerdere activiteit. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,2</code> </p> </td> 
  </tr>
   <tr> 
   <td colname="col1"> <p> <code>Event Time</code> </p> </td> 
   <td colname="col2"> <p><code>d_time</code> </p> </td> 
   <td colname="col3">Een UTC-datum en -tijd voor de impositie, klik of conversiegebeurtenis. Vertegenwoordigd in microseconden sinds 1970-01-01 00:00:00 UTC.</td> 
   <td colname="col4"> <p> <code>1570826763000</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser Group ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"><p>Een integratiecode voor de gegevensbron van uw adverteerder. Merk op dat dit niet met de gegevensbronnen van de Audience Manager verwant is.</p> <p>Dit veld wordt toegewezen aan de Advertiser Group ID uit Google Campaign Manager. </p> </td> 
   <td colname="col4"> <p> <code> 134243</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_bu</code> </p> </td> 
   <td colname="col3"> <p>Bedrijfs-eenheid-id. Dit veld wordt toegewezen aan de Advertiser-id van Google Campaign Manager. </p> </td> 
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
   <td colname="col3"> <p>De Creative ID van Google Campaign Manager. </p> </td> 
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
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> voor indrukken. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> voor klikken. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> voor omzettingen. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>De id van de gegevensbron die u gebruikt om gegevens van Google Campaign Manager vast te leggen. Zie <a href="../../features/manage-datasources.md#create-data-source"> Een gegevensbron maken</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

De in de tabel beschreven signalen worden vastgelegd in [!DNL Audience Manager] als een real-time `HTTP` vraag. De onderstaande voorbeeldaanroep bevat informatie over een conversiegebeurtenis van [!DNL Google Campaign Manager]. De vraag moet niet noodzakelijk omvatten *alles* de signalen in de voorbeeldvraag.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Voor een gemiddelde maat [!DNL Google Campaign Manager] het logboekdossier van 2 miljoen lijnen, om het even welke die eigenschappen van actionable signalen worden gecreeerd worden gerealiseerd binnen ongeveer één uur nadat wij de logboeken verwerken.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>De tijdstempel van de gebeurtenis die wordt opgegeven in het dialoogvenster [!DNL Google Campaign Manager] de logboeken worden nageleefd en worden doorgegeven aan de [!UICONTROL Data Collection Servers].
>
>* Als er geen tijdstempel beschikbaar is voor een gegevensrij in het dialoogvenster [!DNL Google Campaign Manager] logbestand, gebruiken we de tijd van `HTTP` aanroepen als tijdstempel voor de gebeurtenis.
>* Als de gegevens in de [!DNL Google Campaign Manager] het logboekdossier bevat misvormde timestamp, wij negeren de volledige rij.


<br>

### Handbare signalen van [!DNL Google Ad Manager] logs {#ad-manager-logs-signals}

De tabel bevat de actiefsignalen van [!DNL Google Ad Manager] logbestanden:


| Naam koptekst in logbestand | Signaal | Beschrijving |
|---------|----------|---------|
| `LineItemId` | `d_lineitem` | De numerieke id voor het geleverde regelitem Advertentiebeheer |
| `OrderId` | `d_orderid` | De numerieke id voor de volgorde van Advertentiebeheer waarin het geleverde regelitem en de creatieve functie zijn opgenomen. |
| `CreativeId` | `d_creative` | De numerieke id voor de geleverde advertentiemanager. |
| `-` | `d_event` | Geeft het gebeurtenistype aan. Audience Manager leest het gebeurtenistype van het AdManager logboekdossier - naam en zet het in een actionable signaal om. Accepteerde waarden zijn: <br> <ul><li>d_event = imp voor impressies.</li><li>d_event = click voor kliks.</li><li>d_event = conv voor conversies en activiteiten.</li></ul> |
| `-` | `d_src` | De id van de gegevensbron die u gebruikt om Advertentiebeheergegevens vast te leggen. Zie [Een gegevensbron maken](/help/using/features/manage-datasources.md). |

De signalen die in de lijst worden beschreven worden gevangen in Audience Manager als een vraag in real time van HTTP. De onderstaande voorbeeldaanroep bevat informatie over een conversiegebeurtenis van Google Ad Manager. De vraag moet niet noodzakelijk alle signalen in de voorbeeldvraag omvatten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_lineitem=112&d_orderid=22223&d_creative=3983524
```

>[!NOTE]
>
>De tijdstempel van de gebeurtenis die wordt opgegeven in het dialoogvenster [!DNL Google Ad Manager] de logboeken worden nageleefd en worden doorgegeven aan de [!UICONTROL Data Collection Servers].
>
>
>* Als er geen tijdstempel beschikbaar is voor een gegevensrij in het dialoogvenster [!DNL Google Ad Manager] logbestand, gebruiken we de tijd van `HTTP` aanroepen als tijdstempel voor de gebeurtenis.
>* Als de gegevens in de [!DNL Google Ad Manager] het logboekdossier bevat misvormde timestamp, wij negeren de volledige rij.


<br>

### Handelbare signalen van Adobe Advertising Cloud-, FlashTalk- en Sizmek- en serverlogboeken {#generic-logs-signals}

Eerst moet u uw aanmeldingen bij de advertentieserver deponeren in de Amazon S3-emmers. Hiervoor leest u [Gegevensbestanden voor Audience Optimization-rapporten en uitvoerbare logbestanden](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *en* contact opnemen met [!DNL Audience Manager] consultant. De tabel bevat een lijst met actiemogelijkheden van logbestanden van advertentieservers:

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
   <td colname="col3"> <p>Geeft aan of een conversie overeenkomt of niet. De volgende opties zijn beschikbaar: </p> <p> 
     <ul id="ul_2256294F1C6F448B9F269D00D4DFEE65"> 
      <li id="li_29D3FF8919B7404297E80BACA913117A"> <code> 0</code> Impressie </li> 
      <li id="li_B5250A63A2C1413FAF1FDC8272BFFB97"> <code> 1</code> Klik op </li> 
      <li id="li_81007A984F554932AC3354E41A42D57B"> <code> -1</code> Onbeheerd of onbekend </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> 0,1,-1</code> </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <code>Time-Stamp</code> </p> </td> 
   <td colname="col2"> <p> <code> d_time</code> </p> </td> 
   <td colname="col3"> <p> Een UTC-datum en -tijd voor de impositie, klik of conversiegebeurtenis. Gebruik de <code>yyyy-MM-dd HH:mm:ss</code> gebruiken. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Een integratiecode voor de gegevensbron van uw adverteerder. Dit veld heeft geen betrekking op <a href="../../features/datasources-list-and-settings.md">Gegevensbronnen van Audience Managers.</a></p></td> 
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
   <td colname="col3"> <p>De Creative ID uit het logbestand. </p> </td> 
   <td colname="col4"> <p> <code> 224221</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>Revenue</code> </p> </td> 
   <td colname="col2"> <p> <code> d_revenue</code> </p> </td> 
   <td colname="col3"> Aankoop of ander omrekeningsbedrag. Gegevenstype: Zweven. </td> 
   <td colname="col4"> <p> <code> 0.001</code> </p> </td> 
  </tr>
    <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_event</code> </p> </td> 
   <td colname="col3"> <p>Geeft het gebeurtenistype aan. Audience Manager leest het gebeurtenistype van het logboekdossier - naam en zet het in een actionable signaal om. Zie <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">naamconventies voor logbestanden</a>. </p> <p>Accepteerde waarden zijn: </p> <p> 
     <ul id="ul_58EB40E458844DA185ABAF160ADAF03E"> 
      <li id="li_71772CC106F74F4788E1784CC3D70BD3"> <code> d_event = imp</code> voor indrukken. </li> 
      <li id="li_33A629A32B87400F93269581154D566F"> <code> d_event = click</code> voor klikken. </li> 
      <li id="li_553B0C0F3D304193929230D54830EBCA"> <code> d_event = conv</code> voor omzettingen. </li> 
     </ul> </p> </td> 
   <td colname="col4"> <p> <code> imp, click, conv</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>-</code> </p> </td> 
   <td colname="col2"> <p> <code> d_src</code> </p> </td> 
   <td colname="col3"> <p>De id van de gegevensbron die u gebruikt om logboekgegevens vast te leggen. Zie <a href="../../features/manage-datasources.md#create-data-source"> Een gegevensbron maken</a>. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

De in de tabel beschreven signalen worden vastgelegd in [!DNL Audience Manager] als een real-time `HTTP` vraag. De vraag moet niet noodzakelijk omvatten *alles* de signalen in de voorbeeldvraag.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Werken met Handbare signalen in de gebruikersinterface van de Audience Manager {#actionable-signals-in-ui}

U kunt de inkomende actiefsignalen bekijken in de [Signalen zoeken](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) interface.

Ga naar **Poortgegevens** (1) > **Signalen** (2) > **Zoeken** (3) en selecteert u de **Werkbare logbestanden** (4).

![Handbare signalen in gebruikersinterface](/help/using/integration/assets/alf-in-signals.png)

Om op regel-gebaseerde eigenschappen tot stand te brengen die uw actionable signalen gebruiken, selecteer **Werkbare logbestanden** (1), selecteert u de actiefsignalen die u als gedragslijn wilt gebruiken (2) en drukt u op **Tekenreeks maken van geselecteerde signalen** (3)

![Kenmerken van signalen maken](/help/using/integration/assets/alf-create-trait.png)


## Gevallen gebruiken {#use-cases}

Eén voordeel van de implementatie [!UICONTROL Actionable Log Files] is de optie om toe te passen [recentie en frequentie](../../features/segments/recency-and-frequency.md) besturingselementen voor [op regels gebaseerde kenmerken](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) die actioneerbare signalen bevatten. Zo kunt u bijvoorbeeld het aantal keren dat een gebruiker een bepaald creatief programma ziet, in een mediacampagne beperken. Lezen [Onmiddellijke ondersteuning voor apparaten](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) om te leren hoe u dit kunt doen. Andere gebruiksgevallen zijn:

### Gebruikers opnieuw toewijzen

Ga gebruikers terug die creatieve 123 zagen maar niet klikte of omzet en hen creatieve 456 tonen. Doe dit:

1. Maak een eigenschap om gebruikers vast te leggen die de creatieve foto&#39;s hebben gezien. Laten we zeggen dat u het kenmerk noemt [!DNL Creative Trait 123]. Gebruik de regel Actief:

   `d_creative == 123 AND d_event == imp`

2. Maak een eigenschap om gebruikers vast te leggen die klikken of converteren. Laten we zeggen dat u deze naam geeft [!DNL Click and Converter]. Gebruik de regel Actief:

   `d_event == click OR d_event=conv`

3. Maak een segment om te vullen met gebruikers die creatieve 123 hebben gezien, maar niet hebben geklikt of geconverteerd. Naam geven [!DNL Retarget Users] en gebruik de segmentregel:

   `Creative Trait 123 AND NOT Click and Converter`

4. Het segment toewijzen [!DNL Retarget Users] naar een doel en doelgebruikers op de bestemming met creative 456.

### De activiteit van de Manager van de Campagne van Google van het gebruik de Vullight in de Rapporten van de Audience Optimization of in het Laboratorium van de Publiek

[Fullight-tags](https://support.google.com/dcm/partner/answer/4293719?hl=en) adverteerders in staat stellen de omzettingen van gebruikers bij te houden. Met [!UICONTROL Actionable Log Files], kunt u de [!DNL Google Campaign Manager] conversies in de [Audience Optimization-rapporten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) of in [Audience Lab](../../features/audience-lab/audience-lab.md):

1. Maak een kenmerk en gebruik de volgende regel voor het vastleggen van een conversie van de logboeken van de advertentieserver:

   `d_event == conv AND d_conversion == 123`

   Bij het maken van de eigenschap in de Audience Manager [!UICONTROL UI], selecteert u [!UICONTROL Conversion] als de [!UICONTROL Event Type].

2. Als u de eigenschap hebt gemaakt, wordt de conversie in het pop-upmenu [!UICONTROL Audience Optimization Reports] en in [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Google Campagne Manager-gegevensbestanden importeren in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
>* [Audience Optimization-rapporten](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

