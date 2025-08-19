---
description: Beschrijft de vereiste gebieden, syntaxis, noemende overeenkomsten en dossiergrootte u moet volgen wanneer het verzenden van gegevens naar Audience Manager. Stel de namen en grootten van uw bestanden in op basis van deze specificaties wanneer u gegevens naar een Audience Manager FTP-map verzendt.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager FTP directory.
seo-title: FTP Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Vereisten voor FTP-naam en bestandsgrootte voor binnenkomende gegevensbestanden
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
feature: Inbound Data Transfers
exl-id: 9c889214-7075-4392-9ed5-f07b91e7b50a
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 3%

---

# [!DNL FTP] Vereisten voor naam en bestandsgrootte voor binnenkomende gegevensbestanden {#ftp-name-and-file-size-requirements-for-inbound-data-files}

Beschrijft de vereiste velden, syntaxis, naamgevingsconventies en bestandsgrootten die u moet volgen wanneer u gegevens naar [!DNL Audience Manager] verzendt. Stel de namen en formaten van uw bestanden in volgens deze specificaties wanneer u gegevens naar een Audience Manager [!DNL FTP] -map verzendt.

>[!WARNING]
>
>De ondersteuning voor [!DNL FTP] -configuraties wordt geleidelijk afgeschaft. Hoewel de binnenkomende gegevensbestandsinvoer nog steeds wordt ondersteund in bestaande [!DNL FTP] -integraties, raden we u ten zeerste aan om [!DNL Amazon S3] te gebruiken om offlinegegevens voor nieuwe integraties aan boord te nemen. Zie [Vereisten voor naam en bestandsgrootte van binnenkomende Amazon S3-databestanden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) voor meer informatie.

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, steunen `[ ]` `( )`, enz.) in dit document wijzen op codeelementen en opties. Zie [Stijlconventies voor code- en tekstelementen](../../../reference/code-style-elements.md) voor meer informatie.

## Syntaxis bestandsnaam {#file-name-syntax}

[!DNL FTP] bestandsnamen bevatten de volgende vereiste en optionele elementen:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Voor andere toegelaten dossier - noem formaten, zie {de Integraties van de Partner van 0} Douane [.](/help/using/integration/sending-audience-data/custom-partner-integrations.md)

>[!NOTE]
>
>[!DNL Audience Manager] verwerkt alleen [!DNL ASCII] - en [!DNL UTF-8] -gecodeerde bestanden.

### Elementen benoemen

De tabel definieert de elementen in een bestandsnaam van [!DNL FTP] .

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
   <td colname="col2"> <p>Het pad naar en de naam van de <span class="keyword"> Audience Manager </span> FTP-map. Neem contact op met uw accountmanager voor de FTP-map en de referenties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Een lD die <span class="keyword"> Audience Manager </span> vertelt als een gegevensdossier uw eigen gebruiker IDs, Android IDs, iOS IDs, of andere IDs bevat die tot <a href="/help/using/features/global-data-sources.md"> globale gegevensbronnen </a> behoren. Accepteert de volgende opties:</p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b> identiteitskaart van Source van Gegevens (die ook als identiteitskaart van de Leverancier van Gegevens wordt bekend):</b> dit is een unieke identiteitskaart die Audience Manager aan een gegevensbron toewijst (verwijs naar de Audience Manager <a href="/help/using/reference/ids-in-aam.md"> index van IDs </a>). Gebruik deze toegewezen id in een bestandsnaam wanneer u gegevens verzendt die uw eigen gebruikers-id's bevatten. Bijvoorbeeld, vertelt <code>...ftp_dpm_21_123456789.sync</code> <span class="keyword"> Audience Manager </span> aan binnenbordgegevens aan IDs die tot gegevensbron 21 behoren. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b> Android IDs (GAID):</b> identiteitskaart 20914 van het Gebruik in een naam van het gegevensdossier als het Android IDs bevat. U moet het veld <code><i>_DPID_TARGET_DATA_OWNER</i></code> gebruiken wanneer u Android-id's gebruikt. <code>...ftp_dpm_20914_DPID_TARGET_DATA_OWNER_123456789.sync</code> vertelt <span class="keyword"> Audience Manager </span> bijvoorbeeld dat het gegevensbestand alleen Android-id's bevat en dat de id's in aanmerking moeten komen voor de kenmerken die bij de <code><i>_DPID_TARGET_DATA_OWNER</i></code> -gegevensbron horen.</li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b> iOS IDs (IDFA):</b> identiteitskaart 20915 van het Gebruik in een naam van het gegevensdossier als het iOS IDs bevat. U moet het veld <code><i>_DPID_TARGET_DATA_OWNER</i></code> gebruiken wanneer u iOS-id's gebruikt. <code>...ftp_dpm_20915_DPID_TARGET_DATA_OWNER_123456789.sync</code> vertelt <span class="keyword"> Audience Manager </span> bijvoorbeeld dat het gegevensbestand alleen iOS-id's bevat en dat de id's in aanmerking moeten komen voor de kenmerken die bij de <code><i>_DPID_TARGET_DATA_OWNER</i></code> -gegevensbron horen.</li>
     <li> <b> IDs die tot andere globale gegevensbronnen </b> behoren: U kunt aan boord Roku IDs voor Advertising (RIDA), Microsoft Advertising IDs (MAID), en andere IDs. Gebruik identiteitskaart die aan elke gegevensbron beantwoordt, zoals die in het <a href="/help/using/features/global-data-sources.md"> globale artikel van gegevensbronnen </a> wordt beschreven.</li> 
    </ul> <p> <p>Opmerking: gebruik geen ID-typen in uw gegevensbestanden. Als uw bestandsnaam bijvoorbeeld de Android-id bevat, plaats dan geen iOS-id of uw eigen id in het gegevensbestand. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>In dit veld wordt aan Audience Manager doorgegeven welke gegevensbron aan boord van gegevens moet worden geplaatst. Dit veld is verplicht als u de DPID instelt op een Android-id of een iOS-id of een andere id die bij globale gegevensbronnen hoort. Dit laat <span class="keyword"> Audience Manager </span> de dossiergegevens terug naar uw organisatie verbinden. <br> Deze doelgegevensbron moet eigendom zijn van uw bedrijf. Voor de doeleinden van het delen van gegevens van de tweede partij, om gegevens in te voeren in een doelgegevensbron die tot een ander bedrijf behoort, moet u een toegangstoewijzing tussen uw bedrijf en de doelgegevensbron hebben. Neem contact op met uw Adobe-consultant of Klantenondersteuning om de toewijzing in te stellen.</p><p><b> Belangrijke nota:</b> u <i> te hoeven niet </i> om een afbeelding voor bestaande gegevens te verzoeken delend verhoudingen (voor doelgegevensbronnen die tot andere bedrijven behoren waarin u gegevens voorafgaand aan 14 Maart, 2022) bezat. De toewijzing wordt ook niet vereist wanneer het aan boord gaan van gegevens in doelgegevensbronnen die tot uw PID behoren. </p> <p>Bijvoorbeeld: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> vertelt Audience Manager dat u klant-id's die tot gegevensbron 33 behoren, kwalificeert voor kenmerken of signalen die tot gegevensbron 21 behoren. </li> 
     <li> <b> Android IDs (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> vertelt <span class="keyword"> Audience Manager </span> dat het gegevensdossier Android IDs slechts bevat en IDs voor de eigenschappen zou moeten kwalificeren die tot gegevensbron 21 behoren.</li> 
     <li> <b> iOS IDs (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> vertelt <span class="keyword"> Audience Manager </span> dat het gegevensdossier iOS IDs slechts bevat en IDs voor de eigenschappen zou moeten kwalificeren die tot gegevensbron 21 behoren.</li>
     <li> <b> IDs die tot andere globale gegevensbronnen </b> behoren: <code>...ftp_dpm_121963_21_1234567890.sync</code> vertelt <span class="keyword"> Audience Manager </span> dat het gegevensdossier slechts identiteitskaarts van Roku bevat en IDs voor de eigenschappen zou moeten kwalificeren die tot gegevensbron 21 behoren. Gebruik identiteitskaart die aan elke gegevensbron beantwoordt, zoals die in het <a href="/help/using/features/global-data-sources.md"> globale artikel van gegevensbronnen </a> wordt beschreven.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync |.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synchronisatieopties met: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normaal scenario wanneer externe gegevensproviders kenmerken per gebruiker verzenden die in het Audience Manager-systeem moeten worden toegevoegd of verwijderd. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Hiermee kunnen klanten en gegevensleveranciers een lijst met kenmerken per gebruiker verzenden die alle bestaande kenmerken van deze gebruiker voor een bepaalde gegevensbron in Audience Manager moet overschrijven. U hoeft niet al uw gebruikers op te nemen in een overschrijvingsbestand. Neem alleen de gebruikers op die u wilt wijzigen. De sporen die niet aan de doelgegevensbron worden toegewezen zullen niet worden gewist. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Een geheel getal. Wordt gebruikt wanneer u grote bestanden in meerdere onderdelen splitst om de verwerkingstijd te verbeteren. Het nummer geeft aan welk deel van het oorspronkelijke bestand u wilt invoeren. </p> <p>Voor een efficiënte bestandsverwerking splitst u de gegevensbestanden zoals aangegeven: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Niet-gecomprimeerd: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Gecomprimeerd: 200-300 MB </li> 
    </ul> <p>Zie de eerste 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> voorbeelden van bestandsnaam </a> hieronder. </p> </td> 
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
   <td colname="col2"> <p>Gzip is de toegestane compressie-indeling voor een FTP-bestandsnaam. Als u bestandscompressie gebruikt, moet u ervoor zorgen dat de bestandsnaam de juiste extensie heeft. </p> <p>Gecomprimeerde bestanden moeten 3 GB of kleiner zijn. Neem contact op met de klantenservice als uw bestanden groter zijn. Hoewel Audience Manager grote bestanden kan verwerken, kunnen we u misschien helpen uw bestanden kleiner te maken en gegevensoverdracht efficiënter te maken. Zie <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden </a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeelden van bestandsnamen {#file-name-examples}

In de volgende voorbeelden worden correct opgemaakte bestandsnamen weergegeven. De bestandsnamen kunnen er ongeveer hetzelfde uitzien.

<ul class="simplelist"> 
 <li> <code> ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

[ Download ](assets/ftp_dpm_1234_1445374061.overwrite) het steekproefdossier als u extra voorbeelden nodig hebt. Dit bestand wordt opgeslagen met de bestandsextensie `.overwrite` . Open het met een eenvoudige teksteditor.

## Geaccepteerde bestandsgrootten {#accepted-file-sizes}

Houd rekening met de onderstaande afbeeldingen voor de snelste/vroegste verwerking van uw bestanden en voor beperkingen van de bestandsgrootte wanneer u gegevens naar een map [!DNL Audience Manager] / [!DNL FTP] verzendt.

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
   <td colname="col1"><b> Gecomprimeerde </b> </td> 
   <td colname="col2"> <p>200-300 MB </p> </td> 
   <td colname="col3"> <p>3 GB </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"><b> niet samengeperst </b> </td> 
   <td colname="col2"> <p>1 GB </p> </td> 
   <td colname="col3"> <p>5 GB </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Amazon S3-naamvereisten voor binnenkomende databestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
