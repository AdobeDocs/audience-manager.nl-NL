---
description: Basisinformatie over CDF-bestanden (Customer Data Feed) en instructies over hoe u aan de slag kunt gaan. Begin hier als u in het ontvangen van CDF- dossiers geinteresseerd bent of enkel meer informatie wilt.
keywords: gegevens van tweede partij;gegevens van tweede partij;gegevens van tweede partij;gegevens van tweede partij
seo-description: Basic information about Customer Data Feed (CDF) files and instructions on how to get started. Start here if you're interested in receiving CDF files or just want more information.
seo-title: Customer Data Feeds
solution: Audience Manager
title: Klantdatafeeds
uuid: a5de1630-2c7a-4862-9ba0-f8343cdd2782
feature: Customer Data Feeds
exl-id: 118c4225-3b57-4a02-ae05-2fcbf3e5d743
source-git-commit: 89137248aa47573f5b65e387a152f651419da827
workflow-type: tm+mt
source-wordcount: '1989'
ht-degree: 1%

---

# [!UICONTROL Customer Data Feeds] {#customer-data-feeds}

Basisinformatie over [!UICONTROL Customer Data Feed] ([!UICONTROL CDF]) en instructies over hoe u aan de slag kunt gaan. Begin hier als je interesse hebt in [!UICONTROL CDF] of meer informatie.

## Bestandsinhoud en doel {#file-contents-purpose}

Een [!UICONTROL CDF]-bestand bevat dezelfde data die een [!DNL Audience Manager]-gebeurteniscall (`/event`) naar onze servers verzendt. Dit omvat gegevens zoals gebruikers-id&#39;s, [!UICONTROL trait IDs], [!UICONTROL segment IDs]en alle andere parameters die door een gebeurtenisaanroep worden vastgelegd. Intern [!DNL Audience Manager] systemen verwerken gebeurtenisgegevens in een [!UICONTROL CDF] bestand met inhoud die is ingedeeld in velden die in een ingestelde volgorde worden weergegeven. [!DNL Audience Manager] pogingen om te genereren [!UICONTROL CDF] bestanden per uur worden opgeslagen en opgeslagen in een beveiligd, klantspecifiek emmertje op een [!DNL Amazon S3] server. We bieden deze bestanden zodat u kunt werken met [!DNL Audience Manager] gegevens buiten de grenzen die door onze gebruikersinterface worden opgelegd.

>[!IMPORTANT]
>
>Houd rekening met de volgende beperkingen wanneer u werkt met CDF-bestanden:
>
>* Voordat u CDF-bestandslevering instelt, moet u ervoor zorgen dat u over de juiste machtigingen van externe gegevensleveranciers beschikt voor het exporteren van externe traits. Audience Manager ondersteunt momenteel geen functionaliteit in de gebruikersinterface om CDF-toestemming voor het exporteren van bestanden van gegevensleveranciers van derden te vragen. Neem daarom een onafhankelijk contact op met deze leveranciers.
>* U mag het niet gebruiken [!UICONTROL CDF] bestanden als een proxy om het paginaverkeer te controleren, discrepanties tussen rapporten of facturering op elkaar af te stemmen, enz.


## Aan de slag {#getting-started}

Er is geen zelfbedieningsproces om te beginnen [!UICONTROL CDF] bestandslevering. Neem contact op met uw [!DNL Audience Manager] consultant of klantenservice om aan de slag te gaan. Tijdens de implementatie [!DNL Audience Manager] vertegenwoordiger:

* Stel uw [!DNL Amazon S3] opslagemmer.
* Alleen-lezen opgeven [!DNL S3] verificatiereferenties naar het opslagemmertje voor bestanden. U kunt geen mappen en bestanden zien of openen die bij andere klanten horen.

Bestandsmeldingen en [!UICONTROL CDF] bestanden worden weergegeven in uw [!DNL S3] emmertje als ze klaar zijn om te downloaden. U bent verantwoordelijk voor het controleren en downloaden van bestanden van uw toegewezen [!DNL S3] directory. Zie [Voortgangsmeldingen voor klantdatafeedbestanden](#cdf-file-processing-notifications).

## Volgende stappen {#next-steps}

De onderstaande secties en de [Veelgestelde vragen over de gegevensfeed van de klant](../faq/faq-cdf.md) kan u helpen vertrouwd met deze dienst worden.

## [!UICONTROL Customer Data Feed] Gedefinieerde inhoud {#cdf-defined}

Hiermee worden de gegevenselementen en arrays in een [!UICONTROL CDF] bestand, op volgorde van weergave. Definities omvatten gegevenstypen, maar deze informatie maakt geen deel uit van een [!UICONTROL CDF] bestand.

>[!IMPORTANT]
>
>Gebeurtenispixels worden standaard uitgesloten in CDF-configuraties. Zorg ervoor dat u in uw verzoek aan de klantenzorg specificeert als u gebeurtenispixel om in uw CDF- dossiers wilt worden omvat. Elke gebeurtenispixel wordt als een unieke rij in uw CDF-bestanden gevuld.

## Definities {#definitions}

A [!UICONTROL CDF] bevat enkele of alle velden die hieronder worden gedefinieerd. Voor informatie over interne bestandsorganisatie raadpleegt u [Bestandsstructuur voor klantgegevens](#cdf-file-structure).

<table id="table_46BC897A30C2469AB5911F5B85A3FAA7"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Veld </th> 
   <th colname="col2" class="entry"> Datatype </th> 
   <th colname="col3" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><code> Event Time</code> </p> </td> 
   <td colname="col2"> <p>Tijdstempel </p> </td> 
   <td colname="col3"> <p>De tijd dat een CDF-bestand is verwerkt door de <span class="wintitle"> Gegevensverzamelingsservers</span> (DCS). De tijdstempel gebruikt de <i>jjjj-mm-dd hh:mm:ss</i> en wordt ingesteld in de tijdzone UTC. </p> <p> <p>Opmerking: De tijd van de gebeurtenis <i>is niet</i>: <p> 
       <ul id="ul_41ABC813FAAC4659AC8DA13F4A6DD7EB"> 
        <li id="li_0192D253EA4C49C4BF2E8BA62CEE028E">De tijd van de paginagebeurtenis of de gebeurtenisvraag zelf, hoewel het aan die tijden kan dicht zijn. </li> 
        <li id="li_271DF14395BC495FBF17186588A554A8">Heeft betrekking op het DCS-uur in de bestandsnaam. Zie ook: <a href="#different-processing-times"> Tijdstippen en tijden van bestandsinhoud voor klantgegevens</a>. </li> 
       </ul> </p> </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Device</code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Dit is het <span class="wintitle"> Unieke gebruikersnaam</span> (UUID). Dit is een apparaat-id van 38 cijfers voor uw sitebezoeker. Zie ook: <a href="../reference/ids-in-aam.md"> Index van id's in Audience Manager</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Container ID</code> </p> </td> 
   <td colname="col2"> <p>Numeriek </p> </td> 
   <td colname="col3"> <p>De id van de container die de syncs van id's activeert. Dit veld wordt alleen gevuld als u de container-id instelt in het dialoogvenster <i>d_nsid</i> in uw site-implementatie. Anders wordt de standaardwaarde 0 niet opgenomen in CDF-bestanden. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Traits</code> </p> </td> 
   <td colname="col2"> <p>Numerieke array </p> </td> 
   <td colname="col3"> <p>Een array met referentie-id's die alle kenmerken bevat die een bezoeker heeft gerealiseerd (gekwalificeerd voor) in de gebeurtenisaanroep. </p> <p>De array kan kenmerken bevatten waarvoor de bezoeker eerder had gekwalificeerd en waarvoor ze via deze gebeurtenisaanroep opnieuw in aanmerking kwamen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Realized Segments</code> </p> </td> 
   <td colname="col2"> <p>Numerieke array </p> </td> 
   <td colname="col3"> <p>Een array van segment-id's die alle segmenten bevat die een bezoeker heeft gerealiseerd (gekwalificeerd voor) in de gebeurtenisaanroep. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Request Parameters</code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Een tekenreeks die alle parameters vastlegt (variabelen, id's, sleutelwaardeparen, id's voor apparaatreclame, enz.) overgegaan binnen de gebeurtenisvraag. </p> <p>Verkort voorbeeld: </p> <p> <code> d_rtbd:json,c_contextData.a.CarrierName:mobile,c_contextData.a.adid:92D56353-49C5-431E-B474-FC528D585810,c_contextData.a,RunMode:Application,c_contextData.a.DaysSinceLastUpgrade:61,d_cid_ic:xid%01EACB6E40-AC65-4012-9FE9-ABD59965E9C4%011,c_contextData.a.PrevSessionLength:583</code> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> Referer Data Type</code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>De niet-gecodeerde URL van de verwijzende pagina (indien aanwezig). </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> IP Data Type</code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>Het IP-adres van de bezoeker die is vastgelegd in de gebeurtenisaanroep. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> MCDevice </code> </p> </td> 
   <td colname="col2"> <p>String </p> </td> 
   <td colname="col3"> <p>De <span class="keyword"> Experience Cloud</span> Id (MID) die is toegewezen aan de sitebezoeker. Zie ook: <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies en de Adobe Experience Platform Identity Service</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Segments</code> </p> </td> 
   <td colname="col2"> <p>Numerieke array </p> </td> 
   <td colname="col3"> <p>Een array van segment-id's die eerder gerealiseerde segmenten en nieuwe segmenten bevat waarvoor de bezoeker in aanmerking komt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><code> All Traits</code> </p> </td> 
   <td colname="col2"> <p>Numerieke array </p> </td> 
   <td colname="col3"> <p>Een array met ID's van het eerste en het derde kenmerk die eerder gerealiseerde kenmerken en nieuwe kenmerken bevat waarvoor de bezoeker zich heeft gekwalificeerd sinds de laatste gegenereerde gegevensfeed. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Bestandsstructuur {#cdf-file-structure}

Hiermee geeft u de gegevensstructuur van een [!UICONTROL CDF] bestand. Dit omvat gegevensreeksen, gebiedsscheidingen en scheidingstekens, een kaart van het gegevensdossier, en steekproefdossier.

## Id&#39;s en volgorde van gegevensvelden {#identifiers-and-sequence}

[!UICONTROL CDF] bestanden bevatten geen gelabelde kolommen of veldkoppen. In plaats daarvan [!UICONTROL CDF] bestand definieert velden en arrays met niet-afdrukbare [!DNL ASCII] tekens. Ook de [!UICONTROL CDF] elk veld en elke array wordt in een bepaalde volgorde weergegeven. Als u de veld-id&#39;s en de volgorde begrijpt, kunt u het bestand op de juiste wijze parseren.

<table id="table_D2C8786DF7CE47E5ADB8930EC825F8F6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> CDF-bestandselement </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Veldscheidingstekens en scheidingstekens </p> </td> 
   <td colname="col2"> <p>Deze niet-afdrukbare tekens definiëren de elementen en structuur van het CDF-bestand: </p> <p> 
     <ul id="ul_056A9B90AC88405CBB5F81A56CD6E4C9"> 
      <li id="li_B9DA15DCB6A445D781B8753C1C4262B0">Ctrl + a (ASCII) <code> 001</code> of <code> ^A</code>) worden gegevens in afzonderlijke velden gescheiden met een niet-afdrukbare ruimte-indicator. </li> 
      <li id="li_E68D0CC065B34AC9AF91F166CAA2A67C">Ctrl + b (ASCII) <code> 002</code> of <code> ^B</code>) scheidt gegevens en array- en request-parameters. </li> 
      <li id="li_6C32D927FEF04CDE9887374E8C2688E7">Ctrl + c (ASCII) <code> 003</code> of <code> ^C</code>) definieert sleutelwaardeparen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Veldvolgorde </p> </td> 
   <td colname="col2"> <p> <p>Belangrijk: <span class="keyword"> Audience Manager</span> behoudt zich het recht voor om nieuwe velden toe te voegen aan het einde van het CDF-bestand in toekomstige versies. Dit betekent het technische ontwerp van uw dossier het ontleden systeem niet een vast aantal kolommen zou moeten veronderstellen (hoewel het een vaste orde voor bestaande kolommen kan veronderstellen).</p> </p> <p>De gegevens in uw CDF-bestand worden weergegeven in de onderstaande volgorde. /N kan in plaats van om het even welk van deze gebieden verschijnen, wijzend op een ongeldige waarde.</p> <p> 
     <ol id="ol_1FDF4A7F089448ED8A724378C23009C8"> 
      <li id="li_CB97D90B54EB4F95861583D4A5F660C7">Gebeurtenistijd </li> 
      <li id="li_C44E8CCB1A964B7A941FD772FB8A7608">Apparaat </li> 
      <li id="li_F8AE0D4CA19D411686A240FE06F56147">Container-id </li> 
      <li id="li_660D17989BE54610A01229C47894E8A9">Realistische kenmerken </li> 
      <li id="li_1591180564374204852785C6FFCA4F74">Geregistreerde segmenten </li> 
      <li id="li_FE38DA4969EE4E19B39124E77E2EA5F9">Parameters aanvragen </li> 
      <li id="li_9AC25DA883214FBC902D7CE9DACFAE28">Verwijzing </li> 
      <li id="li_BA05F1C33B5B4625B450425FF1911B30">IP-adres </li> 
      <li id="li_08E632FB135F42B5830D5CBFE6EE6BE8">Experience Cloud Device ID (of MID). Zie ook: <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html" format="https" scope="external"> Cookies en de Adobe Experience Platform Identity Service</a> </li> 
      <li id="li_7A05AF4790A1425A90D019681DF4A595">Alle segmenten </li> 
      <li id="li_1B5A6F076A354BA0A931CB260E6D2675">Alle sporen </li> 
     </ol> </p> <p>Zie voor veldbeschrijvingen <a href="#cdf-defined"> Inhoud van feed-gegevens van klant gedefinieerd</a>. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL CDF] Bestandstoewijzing {#cdf-file-map}

[!UICONTROL CDF] bestandsgegevens worden weergegeven in de volgorde hieronder.

![](assets/sequence-map.png)

## Arrays identificeren

Arrays in een [!UICONTROL CDF] het dossier begint en beëindigt met `Ctrl + a` veldscheidingsteken. Hierdoor lijkt het eerste element in een array op een zelfstandig gegevensveld. De gerealiseerde [!UICONTROL traits] array begint met `^A1234`. Arrayscheidingsteken en id `^B5678` volgt deze vermelding. Als gevolg hiervan zou u geneigd kunnen zijn te denken dat het eerste element in gerealiseerde [!UICONTROL traits] array is ID 5678 (omdat deze begint met `^B`). Dit is niet het geval, en daarom moet u met de opeenvolging en de structuur van een gegevensdossier vertrouwd zijn. Hoewel het eerste element in de [!UICONTROL trait] array (of een van de andere arrays in een [!UICONTROL CDF] bestand) begint met `^A`De volgorde van weergave of positie in het bestand definieert het begin van een array. En het eerste element in een array wordt altijd gescheiden van het vorige item door `^A`.

## Monster [!UICONTROL CDF] Bestand {#sample-file}

Een monster [!UICONTROL CDF] kan er als volgt uitzien. In dit voorbeeld zijn regeleinden ingevoegd om deze aan te passen aan de pagina.

![](assets/CDF-sample.png)

## [!UICONTROL Customer Data Feed] Naamgevingsconventies voor bestanden {#cdf-naming-conventions}

In de onderstaande secties worden de elementen in uw [!UICONTROL CDF] bestandsnaam.

## [!UICONTROL CDF] Bestandsnaam: Syntaxis en voorbeeld {#cdf-file-name}

Een standaard [!UICONTROL CDF] de bestandsnaam bevat de onderstaande elementen. Opmerking: *cursief* Hiermee wordt een tijdelijke aanduiding voor een variabele aangegeven:

### Syntaxis

```
s3://aam-cdf/YOUR-S3-BUCKET-NAME/day=yyyy-mm-dd/hour=hh/AAM-CDF_PARTNER-ID_FILE-SEQUENCE_0.gz
```

### Voorbeeld

```
s3://aam-cdf/dataCompany/day=2017-09-14/hour=17/AAM_CDF_1234_0_0_0.gz
```

In uw [!DNL S3] opslagemmer, de dossiers worden gesorteerd in stijgende orde door identiteitskaart van de Partner ([!UICONTROL PID]), dag en uur.

## [!UICONTROL CDF] Bestandsnaamelementen gedefinieerd {#cdf-file-name-elements}

In de volgende tabel worden de elementen in een [!UICONTROL CDF] bestandsnaam.

<table id="table_4AC4F90C1C7D43E2A93CB3B6908D7E94"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Bestandsnaamelement </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> s3://aam-cdf/</code> </p> </td> 
   <td colname="col2"> <p>Dit is het standaard, basisopslagemmertje voor uw CDF-bestand op een Amazon S3-server. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>your S3 bucket name</i> </code> </p> </td> 
   <td colname="col2"> <p>De naam van het read-only, S3 emmertje dat uw CDF dossiers houdt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>day=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>De datum waarop het bestand is verwerkt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>hour=<i>hh</i></code> </p> </td> 
   <td colname="col2"> <p>Een tijdwaarde uitgedrukt in notatie van 24 uur en ingesteld in de tijdzone UTC. Zie ook: <a href="#different-processing-times"> Tijdstippen en tijden van bestandsinhoud voor klantgegevens</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner ID</i> </code> </p> </td> 
   <td colname="col2"> <p>Je partner-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>File Sequence</i>_0</code> </p> </td> 
   <td colname="col2"> <p>Waarden die de bestandsreeks identificeren. De reeks wordt als volgt verhoogd: 0_0_0, 0_1_0, 0_2_0....1_0_0</p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> .gz</code> </p> </td> 
   <td colname="col2"> <p>Een gzip-bestandsextensie. CDF-bestanden worden gecomprimeerd met gzip. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Meldingen voor bestandsverwerking {#cdf-file-processing-notifications}

[!DNL Audience Manager] schrijft een `.info` bestand naar uw [!DNL S3] directory om u te laten weten wanneer uw [!UICONTROL Customer Data File] ([!UICONTROL CDF]) is klaar om te worden gedownload. De `.info` bestand bevat ook [!DNL JSON] opgemaakte metagegevens over de inhoud van uw [!UICONTROL CDF] bestanden. Controleer deze sectie voor informatie over de syntaxis en de gebieden die door dit berichtdossier worden gebruikt.

## Voorbeeldgegevensbestand {#sample-info-file}

Elk `.info` bestand bevat een `Files` en `Totals` sectie. De `Files` -sectie bevat een array die specifieke meetgegevens bevat voor elk uurbestand. De `Totals` sectie bevat cijfers die zijn geaggregeerd voor al uw [!UICONTROL CDF] bestanden voor een bepaalde dag. De inhoud van uw `.info` kan er ongeveer als volgt uitzien.

```js
{
    "Files": [
        {
            "FileByteSize": 2709730,
            "FileChecksumMD5": "a9ea418e79511642cff11c2a898037dc-1",
            "FileName": "AAM_CDF_1109_000000_0.gz",
            "FileSequenceNumber": 1
        },
        {
            "FileByteSize": 2783351,
            "FileChecksumMD5": "7b469485d60274b6991acd0817855840-3",
            "FileName": "AAM_CDF_1109_000001_0.gz",
            "FileSequenceNumber": 2
        }
    ],
    "Totals": {
        "Day": "2017-09-26",
        "Hour": "18",
        "TotalByteSize": 150092997,
        "TotalNumberFiles": 2
    }
}
```

## Gedefinieerde gegevensbestandsvelden {#info-file-fields-defined}

In de volgende tabellen worden de elementen in een [!UICONTROL CDF] `.info` bestand.

### Bestandsobject

<table id="table_582101B414864DA991CE813A7937ECC6"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Veld </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Files</code> </p> </td> 
   <td colname="col2"> <p>Start de array die metagegevens over uw CDF-bestanden bevat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileByteSize</code> </p> </td> 
   <td colname="col2"> <p>Bestandsgrootte in bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileChecksumMD5</code> </p> </td> 
   <td colname="col2"> <p>De Amazon S3 ETag. Het nummer na het koppelteken geeft het aantal onderdelen weer dat wordt gebruikt om het bestand te maken tijdens het uploaden van meerdere onderdelen. De <code> ETag</code> is niet gelijk aan de MD5-controlesom van het bestand. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileName</code> </p> </td> 
   <td colname="col2"> <p>De bestandsnaam. Zie <a href="#cdf-naming-conventions"> Naamgevingsconventies voor bestanden met namen van klantgegevens</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> FileSequenceNumber</code> </p> </td> 
   <td colname="col2"> <p>Een indexnummer voor elk bestand. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Totalen, object

<table id="table_44F0B2D229E84A5DB3041760B1A50858"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Veld </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> Totals</code> </p> </td> 
   <td colname="col2"> <p>Start het object dat samengevoegde gegevens over al uw CDF-bestanden bevat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Day</code> </p> </td> 
   <td colname="col2"> <p>De dag waarvoor de gegevens beschikbaar zijn. Gebruiksmiddelen <i>jjjj-mm-dd</i> gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> Hour</code> </p> </td> 
   <td colname="col2"> <p>Het uur waarvoor gegevens beschikbaar zijn. Gebruikt een 24-uursnotatie in UTC-tijdzone. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalByteSize</code> </p> </td> 
   <td colname="col2"> <p>De totale grootte van al uw CDF-bestanden voor die datum in bytes. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> TotalNumberFiles</code> </p> </td> 
   <td colname="col2"> <p>Het totale aantal bestanden dat naar uw S3-map is geüpload. </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Customer Data Feed] Tijdstippen voor bestandsnaam en bestandsinhoud verschillen {#different-processing-times}

Uw [!UICONTROL CDF] bevat tijdstempels in de bestandsnaam en de bestandsinhoud. Deze tijdstempels registreren verschillende gebeurtenisprocessen voor hetzelfde [!UICONTROL CDF] bestand. Het is niet ongebruikelijk om verschillende tijdstempels in de naam en inhoud van het zelfde dossier te zien. Als u een goed begrip van elk tijdstempel hebt, voorkomt u vaak voorkomende fouten wanneer u met deze gegevens werkt of probeert deze op tijd te sorteren.

## Locatie [!UICONTROL CDF] Tijdstempels voor bestand {#locating-timestamps}

[!UICONTROL CDF] in bestanden wordt de tijd op twee verschillende locaties vastgelegd.

![](assets/cdf-timestamp.png)

## Het verschil tussen tijdstempels begrijpen {#understanding-timestamps}

De volgende tabel bevat aanvullende informatie over uw [!UICONTROL CDF] bestandstijdstempels samen met informatie over het juiste gebruik ervan.

| Locatie tijdstempel | Beschrijving |
|--- |--- |
| Bestandsnaam | Het tijdstempel in uw [!DNL CDF] bestandsnaam markeert de tijd waarop [!DNL Audience Manager] begon uw bestand voor levering voor te bereiden. Deze tijdstempel wordt ingesteld in het dialoogvenster [!DNL UTC] tijdzone. Het gebruikt de `hour=` parameter, met tijd die als 2-cijferig uur in 24-uursnotatie wordt geformatteerd. Deze tijd kan anders zijn dan de tijd van de gebeurtenis die in de bestandsinhoud is opgenomen. Wanneer u werkt met [!DNL CDF] soms zult u merken dat uw [!DNL S3] emmertje is een bepaald uur leeg. Onder &quot;lege emmer&quot; wordt verstaan:<ul><li>Er zijn geen gegevens voor dat specifieke uur. </li><li> Onze servers zijn zwaar belast en kunnen geen dossiers voor een bepaald uur verwerken. Wanneer de server omhoog vangt, zet het de dossiers die in een vroegere dossiers van het tijdemmertje in een emmer met een recentere tijdwaarde zouden moeten zijn gegaan. Bijvoorbeeld, zult u dit zien wanneer een dossier dat in het uur 17 emmertje zou moeten geweest in het uur 18 emmer verschijnen (met `hour=18` in de bestandsnaam). In dit geval is de server waarschijnlijk begonnen met het verwerken van uw bestand in uur 17, maar kon het bestand niet binnen dat tijdsinterval voltooien. In plaats daarvan wordt het bestand naar het volgende uurtje geduwd.</li></ul><br>**Belangrijk**: Gebruik geen tijdstempel voor de bestandsnaam om gebeurtenissen te groeperen. Als u wilt groeperen in tijd, gebruikt u `EventTime` tijdstempel in de bestandsinhoud. |
| Bestandsinhoud | Het tijdstempel in uw [!DNL CDF] bestandsinhoud geeft de tijd aan [!DNL Data Collection Servers] is begonnen met het verwerken van het bestand. Deze tijdstempel wordt ingesteld in het dialoogvenster [!DNL UTC] tijdzone. Het gebruikt de `EventTime` veld, met tijd opgemaakt als *`yyyy-mm-dd hh:mm:ss`*. Deze tijd ligt dicht bij de werkelijke tijd van de gebeurtenis op de pagina, maar kan verschillen van de tijdindicator in de bestandsnaam. <br> **Tip**: In tegenstelling tot `hour=` tijdstempel in de bestandsnaam, kunt u `EventTime` om gegevens op tijd te groeperen. |

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over klantdatafeeds](../faq/faq-cdf.md)

