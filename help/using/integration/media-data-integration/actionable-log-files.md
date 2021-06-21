---
description: Met uitvoerbare logbestanden kunt u mediasignalen vastleggen uit logbestanden van een server om kenmerken in Audience Manager te maken. Leg impressies, kliks en conversies van advertentieservers vast als kenmerken zonder dat u pixels hoeft toe te voegen.
keywords: actioneerbare stammen, alf, ALF
seo-description: Met uitvoerbare logbestanden kunt u mediasignalen vastleggen uit logbestanden van een server om kenmerken in Audience Manager te maken. Leg impressies, kliks en conversies van advertentieservers vast als kenmerken zonder dat u pixels hoeft toe te voegen.
seo-title: Actiegerichte logboekbestanden
solution: Audience Manager
title: Actiegerichte logboekbestanden
uuid: 4c47615f-ed47-41ba-8694-1d7de4f55d62
feature: Logbestanden
exl-id: bd499931-4e02-4f64-82ba-46ef7c4ffd3c
source-git-commit: 7c46a246233c3519049197bac824f0ee0db29754
workflow-type: tm+mt
source-wordcount: '1611'
ht-degree: 2%

---

# Actiegerichte logboekbestanden {#actionable-log-files}

[!UICONTROL Actionable Log Files] Hiermee kunt u mediagegevens vastleggen uit logbestanden van een advertentieserver en de gegevens gebruiken om eigenschappen in Audience Manager te maken. Leg impressies, kliks en conversies van advertentieservers vast als onderdelen zonder dat u [pixels](../../integration/media-data-integration/impression-data-pixels.md) hoeft toe te voegen.

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, haakjes `[ ]` `( )`, enz.) in dit document de elementen en opties van de code aangeven. Zie [Stijlconventies voor code- en tekstelementen](../../reference/code-style-elements.md) voor meer informatie.

## Doel {#purpose}

[!UICONTROL Actionable Log Files] stroomlijnt de manier waarop u impressies vastlegt, klikt en conversies vanaf advertentieservers. Gebruik deze informatie voor gebruikerssegmentatie zonder het moeten media manueel pixel om campagneattributen naar [!DNL Audience Manager] te verzenden.

## Aan de slag {#getting-started}

Als u aan de slag wilt gaan met [!UICONTROL Actionable Log Files], moet u loggegevens importeren in [!DNL Audience Manager]. Aan de slag met de volgende koppelingen:

* Zie [!UICONTROL Google Campaign Manager] Logboeken [Gegevensbestanden van Google Campagne Manager importeren in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md) *en* Neem contact op met uw [!DNL Audience Manager]-consultant.
* Voor [!UICONTROL Google Ad Manager] (voorheen Google DFP)-logbestanden raadpleegt u [Gegevensbestanden van Google Ad Manager importeren in Audience Manager](/help/using/reporting/audience-optimization-reports/aor-publishers/import-dfp.md) *en* neem contact op met uw [!DNL Audience Manager]-consultant.
* Zie [Gegevens- en metagegevensbestanden](/help/using/reporting/audience-optimization-reports/metadata-files-intro/metadata-files-intro.md) *en* voor andere aanmeldingen op de advertentieserver.[!DNL Audience Manager]

Als u al loggegevens importeert in [!DNL Audience Manager], vraagt u uw [!DNL Audience Manager]-consultant of [Klantenservice](https://helpx.adobe.com/nl/contact/enterprise-support.ec.html) om [!UICONTROL Actionable Log Files] voor u in te schakelen.

<!--

>[!IMPORTANT]
>
> At the end of 2019, [!UICONTROL Actionable Log Files] began to expand availability to new ad servers. Ask your [!DNL Audience Manager] consultant or [Customer Care](https://helpx.adobe.com/contact/enterprise-support.ec.html) to get started.

-->

## Werken met uitvoerbare logbestanden {#working-with-actionable-log-files}

Met [!UICONTROL Actionable Log Files] wordt de informatie van serverlogboeken van de advertentie in [!DNL Audience Manager] de zelfde manier gevangen dat u gegevens van websiteinteractie in real time zou vangen. [!DNL Audience Manager] verbindt met uw opslag van het het logboeklogboek van de advertentieserver, ontleedt de informatie van de logboeken, en verzendt de logboekgegevens als activeerbare signalen naar onze Servers [ van de ](../../reference/system-components/components-data-collection.md#dcs-pcs)Inzameling van Gegevens.

U moet nog opstelling op regel-gebaseerde eigenschappen om de handelingssignalen te vangen. Zie hoe u op regels gebaseerde eigenschappen kunt instellen in de [gebruikersinterface voor Audience Managers](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) of met onze [Bulk Management Tools](../../reference/bulk-management-tools/bulk-create.md). Schuif omlaag naar de sectie [Handbare signalen](../../integration/media-data-integration/actionable-log-files.md#actionable-signals) voor een lijst van alle sleutels u in op regel-gebaseerde eigenschappen kunt gebruiken.

>[!IMPORTANT]
>
>We raden u aan [!UICONTROL Actionable Log Files] *in plaats van* [Pixelaanroepen](../../integration/media-data-integration/impression-data-pixels.md) te implementeren. We ontmoedigen het gebruik van beide opties, omdat dit leidt tot een toename van het aantal frequenties voor kenmerken.

## Handbare signalen {#actionable-signals}

Signalen zijn de [kleinste gegevenseenheden](../../reference/signal-trait-segment.md) in [!DNL Audience Manager]. [!UICONTROL Actionable Log Files] kunt u adverteerders, bedrijfseenheden, creatieve en campagnewaarden vastleggen in imitatiegebeurtenissen, gebeurtenissen en conversiegebeurtenissen als signalen van serverlogboeken voor advertenties klikken.

Herinner me, om deze informatie voor publieksverwezenlijking en segmentatie te gebruiken, moet u opstelling de op regel-gebaseerde trekken zelf.

### Handbare signalen van Google Campagne Manager-logbestanden {#dcm-logs-signals}

De tabel bevat een lijst met actiemotionele signalen van [!DNL Google Campaign Manager] logbestanden:

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
   <td colname="col3"> <p>Alleen beschikbaar voor conversiegebeurtenissen. </p> <p>Vertegenwoordigt de numerieke id voor de conversieactiviteit in Google Campaign Manager. Dit veld verwijst naar de activiteit-id van Google Campaign Manager. </p> <p> <p>Tip: U kunt meerdere of specifieke conversieactiviteiten vastleggen via Google Campagne Manager. Maak kenmerken met <code> d_conversion = activity ID</code> voor elke conversieactiviteit van Google Campagne Manager. </p> </p> </td> 
   <td colname="col4"> <p> <code> 24122</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Conversion ID</code> </p> </td> 
   <td colname="col2"> <p> <code>d_conversionType</code> </p> </td> 
   <td colname="col3"> <p>Alleen beschikbaar voor conversiegebeurtenissen. </p> <p>Dit veld verwijst naar de conversie-id in Google Campagne Manager. Geeft de activiteit aan die voorafgaat aan de gebruikersconversie vanuit Google Campaign Manager. </p> <p>Accepteerde waarden zijn: </p> <p> 
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
   <td colname="col3"><p>Een integratiecode voor de gegevensbron van uw adverteerder. Merk op dat dit niet met de gegevensbronnen van de Audience Manager verwant is.</p> <p>Dit veld verwijst naar de groep-id Advertiser van Google Campaign Manager. </p> </td> 
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
   <td colname="col3"> <p>Geeft het gebeurtenistype aan. Audience Manager leest het gebeurtenistype uit de naam van het logbestand van Google Campagne Manager en zet het om in een actionabel signaal. </p> <p>Accepteerde waarden zijn: </p> <p> 
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
   <td colname="col3"> <p>De id van de gegevensbron die u gebruikt om gegevens van Google Campaign Manager vast te leggen. Zie <a href="../../features/manage-datasources.md#create-data-source"> Hoe te om een Gegevensbron</a> tot stand te brengen. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

De signalen die in de lijst worden beschreven worden gevangen in [!DNL Audience Manager] als een vraag in real time `HTTP`. De onderstaande voorbeeldaanroep bevat informatie over een conversiegebeurtenis van [!DNL Google Campaign Manager]. De vraag moet niet noodzakelijk *all* de signalen in de voorbeeldvraag omvatten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_event=conv&d_conversion=24122&d_conversionType=2&d_bu=3983524&d_campaign=7321391&d_adsrc=11111&d_creative=123456
```

Voor een gemiddeld-gerangschikt [!DNL Google Campaign Manager] logboekdossier van 2 miljoen lijnen, worden om het even welke die eigenschappen van actionable signalen worden gecreeerd gerealiseerd binnen ongeveer één uur nadat wij de logboeken verwerken.

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>De tijdstempel van de gebeurtenis die in de logboeken [!DNL Google Campaign Manager] wordt opgegeven, wordt gerespecteerd en doorgegeven aan [!UICONTROL Data Collection Servers].
>
>* Als een timestamp niet beschikbaar voor een gegevensrij in het [!DNL Google Campaign Manager] logboekdossier is, gebruiken wij de tijd van `HTTP` vraag als gebeurtenistimestamp.
>* Als de gegevensrij in het [!DNL Google Campaign Manager] logboekdossier een misvormd timestamp bevat, negeren wij de volledige rij.


<br>

### Handbare signalen van [!DNL Google Ad Manager] logboeken {#ad-manager-logs-signals}

De tabel bevat een lijst met actiemotionele signalen van [!DNL Google Ad Manager] logbestanden:


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
>De tijdstempel van de gebeurtenis die in de logboeken [!DNL Google Ad Manager] wordt opgegeven, wordt gerespecteerd en doorgegeven aan [!UICONTROL Data Collection Servers].
>
>* Als een timestamp niet beschikbaar voor een gegevensrij in het [!DNL Google Ad Manager] logboekdossier is, gebruiken wij de tijd van `HTTP` vraag als gebeurtenistimestamp.
>* Als de gegevensrij in het [!DNL Google Ad Manager] logboekdossier een misvormd timestamp bevat, negeren wij de volledige rij.


<br> 

### Handbare signalen van generieke en serverlogboeken {#generic-logs-signals}

Eerst moet u uw aanmeldingen bij de advertentieserver deponeren in de Amazon S3-emmers. Hiervoor leest u [Gegevensbestanden voor Audience Optimization-rapporten en ActionScript-bestanden](/help/using/reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md) *en* om contact op te nemen met uw [!DNL Audience Manager]-consultant. De lijst maakt een lijst van de actionable signalen van generische logboekdossiers:

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
   <td colname="col3"> <p> Een UTC-datum en -tijd voor de impositie, klik of conversiegebeurtenis. Gebruik de indeling <code>yyyy-MM-dd HH:mm:ss</code>. </p></td> 
   <td colname="col4"> <p> <code>2019-03-26 11:23:10</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>Advertiser-ID</code> </p> </td> 
   <td colname="col2"> <p> <code> d_adsrc</code> </p> </td> 
   <td colname="col3"> <p>Een integratiecode voor de gegevensbron van uw adverteerder. Merk op dat dit gebied niet met <a href="../../features/datasources-list-and-settings.md">gegevensbronnen van de Audience Manager verwant is.</a></p></td> 
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
   <td colname="col3"> <p>Geeft het gebeurtenistype aan. Audience Manager leest het gebeurtenistype van het logboekdossier - naam en zet het in een actionable signaal om. Zie <a href="../../reporting/audience-optimization-reports/metadata-files-intro/datafiles-intro.md#naming-conventions">conventies voor het benoemen van logbestanden</a>. </p> <p>Accepteerde waarden zijn: </p> <p> 
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
   <td colname="col3"> <p>De id van de gegevensbron die u gebruikt om logboekgegevens vast te leggen. Zie <a href="../../features/manage-datasources.md#create-data-source"> Hoe te om een Gegevensbron</a> tot stand te brengen. </p> </td> 
   <td colname="col4"> <p> <code> 743</code> </p> </td> 
  </tr>
 </tbody>
</table>

De signalen die in de lijst worden beschreven worden gevangen in [!DNL Audience Manager] als een vraag in real time `HTTP`. De vraag moet niet noodzakelijk *all* de signalen in de voorbeeldvraag omvatten.

```
https://yourcompany.demdex.net?d_src=743&d_uuid=07955261652886032950143702505894272138&d_time=1504536233&d_activity=1234&d_creative=24122&d_placemebt=3442&d_bu=3983524&d_campaign=7321391&d_adsrc=11111
```

## Werken met uitvoerbare signalen in de gebruikersinterface {#actionable-signals-in-ui} van de Audience Manager

U kunt uw inkomende actionable signalen in [Signals Onderzoek](/help/using/features/data-explorer/data-explorer-signals-search/data-explorer-signals-search.md) interface bekijken.

Ga naar **Poortgegevens** (1) > **Signalen** (2) > **Zoeken** (3) en selecteer **Geschikte logbestanden** (4) filter.

![Handbare signalen in gebruikersinterface](/help/using/integration/assets/alf-in-signals.png)

Om op regel-gebaseerde eigenschappen tot stand te brengen die uw actionable signalen gebruiken, selecteer **Acteerbare Dossiers van het Logboek** (1), selecteer de actionable signalen die u als eigenlijke regels (2) wilt gebruiken, en druk **Tand van Geselecteerde Signalen creëren** (3).

![Kenmerken van signalen maken](/help/using/integration/assets/alf-create-trait.png)


## Gevallen {#use-cases} gebruiken

Één voordeel van het uitvoeren van [!UICONTROL Actionable Log Files] is de optie om [recency en frequentie](../../features/segments/recency-and-frequency.md) controles op om het even welke [op regel-gebaseerde eigenschappen ](../../features/traits/create-onboarded-rule-based-traits.md#create-rules-based-or-onboarded-traits) toe te passen die actionable signalen bevatten. Zo kunt u bijvoorbeeld het aantal keren dat een gebruiker een bepaald creatief programma ziet, in een mediacampagne beperken. Lees [Onmiddellijke ondersteuning voor verschillende apparaten](/help/using/features/profile-merge-rules/instant-cross-device-suppression.md) om te leren hoe u dit kunt doen. Andere gebruiksgevallen zijn:

### Gebruikers opnieuw toewijzen

Ga gebruikers terug die creatieve 123 zagen maar niet klikte of omzet en hen creatieve 456 tonen. Doe dit:

1. Maak een eigenschap om gebruikers vast te leggen die de creatieve foto&#39;s hebben gezien. Laten we zeggen dat u de eigenschap [!DNL Creative Trait 123] noemt. Gebruik de regel Actief:

   `d_creative == 123 AND d_event == imp`

2. Maak een eigenschap om gebruikers vast te leggen die klikken of converteren. Laten we zeggen dat u deze [!DNL Click and Converter] noemt. Gebruik de regel Actief:

   `d_event == click OR d_event=conv`

3. Maak een segment om te vullen met gebruikers die creatieve 123 hebben gezien, maar niet hebben geklikt of geconverteerd. Noem het [!DNL Retarget Users] en gebruik de segmentregel:

   `Creative Trait 123 AND NOT Click and Converter`

4. Wijs het segment [!DNL Retarget Users] aan een bestemming en doelgebruikers in de bestemming met creatief 456 toe.

### De Google Campagne Manager van de Vullight Activiteit in de Rapporten van de Audience Optimization of in het Laboratorium van de Publiek gebruiken

[Gelabelde ](https://support.google.com/dcm/partner/answer/4293719?hl=en) adverteerders laten zien hoe ze de omzettingen van gebruikers kunnen volgen. Met [!UICONTROL Actionable Log Files], kunt u [!DNL Google Campaign Manager] omzettingen in [Audience Optimization Rapporten](../../reporting/audience-optimization-reports/audience-optimization-reports.md) of in [Laboratorium van het publiek ](../../features/audience-lab/audience-lab.md) volgen:

1. Maak een kenmerk en gebruik de volgende regel voor het vastleggen van een conversie van de logboeken van de advertentieserver:

   `d_event == conv AND d_conversion == 123`

   Wanneer u het kenmerk in de Audience Manager [!UICONTROL UI] maakt, selecteert u [!UICONTROL Conversion] als [!UICONTROL Event Type].

2. Als u de eigenschap hebt gemaakt, wordt de conversie gerapporteerd in de [!UICONTROL Audience Optimization Reports] en in [!UICONTROL Audience Lab].

>[!MORELIKETHIS]
>
>* [Google Campagne Manager-gegevensbestanden importeren in Audience Manager](../../reporting/audience-optimization-reports/aor-advertisers/import-dcm.md)
* [Audience Optimization-rapporten](../../reporting/audience-optimization-reports/audience-optimization-reports.md)

