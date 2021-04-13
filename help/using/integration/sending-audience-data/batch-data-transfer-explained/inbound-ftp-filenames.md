---
description: Beschrijft de vereiste gebieden, syntaxis, noemende overeenkomsten en dossiergrootte u moet volgen wanneer het verzenden van gegevens naar Audience Manager. Stel de namen en grootten van de bestanden in volgens deze specificaties wanneer u gegevens naar een FTP-map van een Audience Manager verzendt.
seo-description: Beschrijft de vereiste gebieden, syntaxis, noemende overeenkomsten en dossiergrootte u moet volgen wanneer het verzenden van gegevens naar Audience Manager. Stel de namen en grootten van de bestanden in volgens deze specificaties wanneer u gegevens naar een FTP-map van een Audience Manager verzendt.
seo-title: Vereisten voor naam en bestandsgrootte van binnenkomende FTP-databestanden
solution: Audience Manager
title: Vereisten voor naam en bestandsgrootte van binnenkomende FTP-databestanden
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Binnenkomende gegevensoverdrachten
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
translation-type: tm+mt
source-git-commit: 48b122a4184d1c0662b9de14e92f727caa4a9d74
workflow-type: tm+mt
source-wordcount: '1045'
ht-degree: 6%

---

# [!DNL FTP] Vereisten voor naam en bestandsgrootte voor binnenkomende gegevensbestanden  {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Beschrijft de vereiste gebieden, syntaxis, noemende overeenkomsten en dossiergrootte u moet volgen wanneer het verzenden van gegevens naar [!DNL Audience Manager]. Stel de namen en grootten van de bestanden in volgens deze specificaties wanneer u gegevens naar de map [!DNL FTP] van een Audience Manager verzendt.

>[!WARNING]
>
>Wij nemen geleidelijk de steun voor [!DNL FTP] configuraties uit. Terwijl de binnenkomende gegevensdossieropname nog in bestaande [!DNL FTP] integraties wordt gesteund, adviseren wij sterk gebruikend [!DNL Amazon S3] aan boord off-line gegevens voor nieuwe integratie. Zie [Vereisten voor naam en bestandsgrootte van binnenkomende Amazon S3-databestanden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) voor meer informatie.

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, haakjes `[ ]` `( )`, enz.) in dit document de elementen en opties van de code aangeven. Zie [Stijlconventies voor code- en tekstelementen](../../../reference/code-style-elements.md) voor meer informatie.

## Syntaxis bestandsnaam {#file-name-syntax}

[!DNL FTP] bestandsnamen bevatten de volgende vereiste en optionele elementen:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Voor andere toegelaten dossier - noem formaten, zie [Integraties van de Partner van de Douane](/help/using/integration/sending-audience-data/custom-partner-integrations.md).

>[!NOTE]
>
>[!DNL Audience Manager] alleen bestanden verwerkt  [!DNL ASCII] en  [!DNL UTF-8] gecodeerd.

### Elementen benoemen

De tabel definieert de elementen in de bestandsnaam [!DNL FTP].

<table id="table_1EA97D75004148CE85F702427DB7E97A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Bestandsnaamelement </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> ftp_dpm_</code> </p> </td> 
   <td colname="col2"> <p>Het pad naar en de naam van de FTP-map <span class="keyword"> Audience Manager</span>. Neem contact op met uw accountmanager voor de FTP-map en de referenties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Een id die <span class="keyword"> Audience Manager</span> vertelt als een gegevensdossier uw eigen gebruikers IDs, Android IDs, iOS IDs, of andere IDs bevat die tot <a href="/help/using/features/global-data-sources.md"> globale gegevensbronnen </a> behoren. Accepteert de volgende opties:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Identiteitskaart van de Gegevensbron (die ook als identiteitskaart van de Leverancier van Gegevens wordt bekend):</b> Dit is een unieke identiteitskaart die de Audience Manager aan een gegevensbron toewijst (verwijs naar de  <a href="/help/using/reference/ids-in-aam.md"> index van de Audience Manager van IDs  </a>). Gebruik deze toegewezen id in een bestandsnaam wanneer u gegevens verzendt die uw eigen gebruikers-id's bevatten. <code>...ftp_dpm_21_123456789.sync</code> vertelt <span class="keyword"> Audience Manager</span> aan boord gegevens aan IDs die tot gegevensbron 21 behoren. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android-id's (GAID):</b> gebruik ID 20914 in een gegevensbestandsnaam als deze Android-id's bevat. U moet het veld <code><i>_DPID_TARGET_DATA_OWNER</i></code> gebruiken wanneer u Android-id's gebruikt. <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> vertelt <span class="keyword"> Audience Manager</span> bijvoorbeeld dat het gegevensbestand alleen Android-id's bevat en dat de id's in aanmerking moeten komen voor de kenmerken die horen bij de <code><i>_DPID_TARGET_DATA_OWNER</i></code>-gegevensbron.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS-id's (IDFA):</b> Gebruik ID 20915 in een gegevensbestandsnaam als deze iOS-id's bevat. U moet het veld <code><i>_DPID_TARGET_DATA_OWNER</i></code> gebruiken wanneer u iOS-id's gebruikt. <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> vertelt <span class="keyword"> Audience Manager</span> bijvoorbeeld dat het gegevensbestand alleen iOS-id's bevat en dat de id's in aanmerking moeten komen voor de kenmerken van de <code><i>_DPID_TARGET_DATA_OWNER</i></code>-gegevensbron.</li>
     <li> <b>Id's die tot andere globale gegevensbronnen</b> behoren: U kunt Roku-id's voor advertentie (RIDA), Microsoft Advertising ID's (MAID) en andere id's aan boord nemen. Gebruik identiteitskaart die aan elke gegevensbron beantwoordt, zoals die in <a href="/help/using/features/global-data-sources.md"> globale gegevensbronnen artikel</a> wordt beschreven.</li> 
    </ul> <p> <p>Opmerking:  Gebruik geen ID-typen in uw gegevensbestanden. Als uw bestandsnaam bijvoorbeeld de Android-id bevat, plaats dan geen iOS-id's of uw eigen id's in het gegevensbestand. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Dit gebied vertelt Audience Manager welke gegevensbron aan boordgegevens aan. Dit veld is verplicht als u de DPID instelt op een Android-id of iOS-id of een andere id die bij globale gegevensbronnen hoort. Hierdoor kunnen <span class="keyword"> Audience Manager</span> de bestandsgegevens weer aan uw organisatie koppelen. </p> <p>Bijvoorbeeld: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> vertelt Audience Manager dat u klant-id's kwalificeert die tot gegevensbron 33 behoren voor kenmerken of signalen die tot gegevensbron 21 behoren. </li> 
     <li> <b>Android-id's (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> vertelt  <span class="keyword"> Audience </span> Managerdat het gegevensbestand alleen Android-id's bevat en dat de id's in aanmerking moeten komen voor de kenmerken van gegevensbron 21.</li> 
     <li> <b>iOS-id's (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> vertelt  <span class="keyword"> Audience </span> Managerdat het gegevensbestand alleen iOS-id's bevat en dat de id's in aanmerking moeten komen voor de kenmerken van gegevensbron 21.</li>
     <li> <b>Id's die tot andere globale gegevensbronnen</b> behoren:  <code>...ftp_dpm_121963_21_1234567890.sync</code> vertelt  <span class="keyword"> Audience </span> Managerest dat het gegevensbestand alleen Roku-id's bevat en de id's in aanmerking moeten komen voor de kenmerken van gegevensbron 21. Gebruik identiteitskaart die aan elke gegevensbron beantwoordt, zoals die in <a href="/help/using/features/global-data-sources.md"> globale gegevensbronnen artikel</a> wordt beschreven.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synchronisatieopties met: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normaal scenario wanneer de derdegegevensleveranciers eigenschappen op een per-gebruikersbasis verzenden om in het systeem van de Audience Manager worden toegevoegd of worden verwijderd. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Laat klanten en gegevensleveranciers een lijst van eigenschappen op een per-gebruikersbasis verzenden die alle bestaande eigenschappen van deze gebruiker voor een bepaalde gegevensbron in Audience Manager zou moeten beschrijven. U hoeft niet al uw gebruikers op te nemen in een overschrijvingsbestand. Neem alleen de gebruikers op die u wilt wijzigen. De sporen die niet aan de doelgegevensbron worden toegewezen zullen niet worden gewist. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Een geheel getal. Wordt gebruikt wanneer u grote bestanden in meerdere onderdelen splitst om de verwerkingstijd te verbeteren. Het nummer geeft aan welk deel van het oorspronkelijke bestand u wilt invoeren. </p> <p>Voor een efficiënte bestandsverwerking splitst u de gegevensbestanden zoals aangegeven: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Niet-gecomprimeerd: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Gecomprimeerd: 200-300 MB </li> 
    </ul> <p>Zie de eerste 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> voorbeelden van de dossiernaam</a> hieronder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Een tijdstempel van 10 cijfers (UTC UNIX) in seconden. Met de tijdstempel kunt u elke bestandsnaam uniek maken. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip is de toegestane compressie-indeling voor een FTP-bestandsnaam. Als u bestandscompressie gebruikt, moet u ervoor zorgen dat de bestandsnaam de juiste extensie heeft. </p> <p>Gecomprimeerde bestanden moeten 3 GB of kleiner zijn. Neem contact op met de klantenservice als uw bestanden groter zijn. Hoewel Audience Manager grote bestanden kan verwerken, kunnen we u helpen de bestanden te verkleinen en de gegevensoverdracht efficiënter te maken. Zie <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md">Bestandscompressie voor binnenkomende dataoverdrachtsbestanden</a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeelden van bestandsnaam {#file-name-examples}

In de volgende voorbeelden worden correct opgemaakte bestandsnamen weergegeven. De bestandsnamen kunnen er ongeveer hetzelfde uitzien.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[Download het voorbeeldbestand als u meer voorbeelden nodig hebt. ](assets/ftp_dpm_1234_1445374061.overwrite) Dit bestand wordt opgeslagen met de bestandsextensie `.overwrite`. Open het met een eenvoudige teksteditor.

## Geaccepteerde bestandsgrootten {#accepted-file-sizes}

Houd rekening met de onderstaande cijfers voor de snelste/vroegste verwerking van uw bestanden en voor beperkingen van de bestandsgrootte wanneer u gegevens naar een map [!DNL Audience Manager] / [!DNL FTP] verzendt.

<table id="table_59FCC63806684DF8BE54A1EAF224A234"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Bestandstype </th> 
   <th colname="col2" class="entry"> Optimale grootte </th> 
   <th colname="col3" class="entry"> Maximale grootte </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"><b>Gecomprimeerd</b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b>Niet gecomprimeerd</b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Amazon S3-naamvereisten voor binnenkomende databestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

