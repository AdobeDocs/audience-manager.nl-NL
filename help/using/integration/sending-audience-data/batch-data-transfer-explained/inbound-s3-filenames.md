---
description: Beschrijft de vereiste gebieden, syntaxis, noemende overeenkomsten en dossiergrootte u moet volgen wanneer het verzenden van gegevens naar Audience Manager. Stel de namen en grootten van uw bestanden in volgens deze specificaties wanneer u gegevens naar een Audience Manager / Amazon S3-map verzendt.
seo-description: Describes the required fields, syntax, naming conventions and file sizes you need to follow when sending data to Audience Manager. Set the names and sizes of your files according to these specifications when you send data to an Audience Manager / Amazon S3 directory.
seo-title: Amazon S3 Name and File Size Requirements for Inbound Data Files
solution: Audience Manager
title: Amazon S3-vereisten voor naam en bestandsgrootte voor binnenkomende gegevensbestanden
uuid: 3692a122-6ad5-468c-934e-53067bd8cf71
feature: Inbound Data Transfers
exl-id: 428acdb5-fff0-4b70-b15a-e384aed9cc2d
source-git-commit: a5506a315a98afdf31f8f52fac09b9179f388f30
workflow-type: tm+mt
source-wordcount: '1114'
ht-degree: 1%

---

# [!DNL Amazon S3] Vereisten voor naam en bestandsgrootte voor binnenkomende gegevensbestanden {#amazon-s-name-and-file-size-requirements-for-inbound-data-files}

Beschrijft de vereiste velden, syntaxis, naamgevingsconventies en bestandsgrootten die u moet volgen wanneer u gegevens naar [!DNL Audience Manager] verzendt. Stel de namen en grootten van de bestanden in volgens deze specificaties wanneer u gegevens naar een map [!DNL Audience Manager] / [!DNL Amazon S3] verzendt.

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, steunen `[ ]` `( )`, enz.) in dit document wijzen op codeelementen en opties. Zie [Stijlconventies voor code- en tekstelementen](../../../reference/code-style-elements.md) voor meer informatie.

## Syntaxis bestandsnaam {#file-name-syntax}

[!DNL S3] bestandsnamen bevatten de volgende vereiste en optionele elementen:

* **[!DNL S3]prefix:**   `s3n://AWS_directory/partner_name/date=yyyy-mm-dd/`

* **de naamelementen van het Dossier:**   `ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Voor andere toegelaten dossier - noem formaten, zie {de Integraties van de Partner van 0} Douane [.](/help/using/integration/sending-audience-data/custom-partner-integrations.md)

<!--
Removed  {importance="high"} for ExL
-->

>[!NOTE]
>
>[!DNL Audience Manager] verwerkt alleen [!DNL ASCII] - en [!DNL UTF-8] -gecodeerde bestanden.

### Naamelementen

De tabel definieert de elementen in een bestandsnaam van [!DNL S3] .

<table id="table_455D174BAB9B494D973DA1023F22B962"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Name Element </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <code> <i>AWS_directory</i> </code> </p> </td> 
   <td colname="col2"> <p>Het pad naar en de naam van uw Amazon S3-emmertje. Neem contact op met uw accountmanager voor uw S3-mapnaam, -pad en -referenties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>date=<i>yyyy-mm-dd</i></code> </p> </td> 
   <td colname="col2"> <p>Een tijdstempel (op basis van UTC-tijd) van wanneer u de bestanden naar uw S3-emmertje verzendt. </p> </td> 
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
   <td colname="col2"> <p>In dit veld wordt aan Audience Manager doorgegeven welke gegevensbron aan boord van gegevens moet worden geplaatst. Dit veld is verplicht als u de DPID instelt op een Android-id of een iOS-id of een andere id die bij globale gegevensbronnen hoort. Zo kan Audience Manager de bestandsgegevens weer koppelen aan uw organisatie. <br> Deze doelgegevensbron moet eigendom zijn van uw bedrijf. Voor de doeleinden van het delen van gegevens van de tweede partij, om gegevens in te voeren in een doelgegevensbron die tot een ander bedrijf behoort, moet u een toegangstoewijzing tussen uw bedrijf en de doelgegevensbron hebben. Neem contact op met uw Adobe-consultant of Klantenondersteuning om de toewijzing in te stellen.</p> <p><b> Belangrijke nota:</b> u <i> te hoeven niet </i> om een afbeelding voor bestaande gegevens te verzoeken delend verhoudingen (voor doelgegevensbronnen die tot andere bedrijven behoren waarin u gegevens voorafgaand aan 14 Maart, 2022) bezat. De toewijzing wordt ook niet vereist wanneer het aan boord gaan van gegevens in doelgegevensbronnen die tot uw PID behoren. </p> <p>Bijvoorbeeld: </p> 
    <ul> 
     <li> <code>...ftp_dpm_33_21_1234567890.sync</code> vertelt Audience Manager dat u klant-id's die tot gegevensbron 33 behoren, kwalificeert voor kenmerken of signalen die tot gegevensbron 21 behoren. </li> 
     <li> <b> Android IDs (GAID):</b> <code>...ftp_dpm_20914_21_1234567890.sync</code> vertelt <span class="keyword"> Audience Manager </span> dat het gegevensdossier Android IDs slechts bevat en IDs voor de eigenschappen zou moeten kwalificeren die tot gegevensbron 21 behoren.</li> 
     <li> <b> iOS IDs (IDFA):</b> <code>...ftp_dpm_20915_21_1234567890.sync</code> vertelt <span class="keyword"> Audience Manager </span> dat het gegevensdossier iOS IDs slechts bevat en IDs voor de eigenschappen zou moeten kwalificeren die tot gegevensbron 21 behoren.</li>
     <li> <b> IDs die tot andere globale gegevensbronnen </b> behoren: <code>...ftp_dpm_121963_21_1234567890.sync</code> vertelt <span class="keyword"> Audience Manager </span> dat het gegevensdossier slechts identiteitskaarts van Roku bevat en IDs voor de eigenschappen zou moeten kwalificeren die tot gegevensbron 21 behoren. Gebruik identiteitskaart die aan elke gegevensbron beantwoordt, zoals die in het <a href="/help/using/features/global-data-sources.md"> globale artikel van gegevensbronnen </a> wordt beschreven.</li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>partner_name</i> </code> </p> </td> 
   <td colname="col2"> <p>Het bedrijf of de organisatienaam u in <span class="keyword"> Audience Manager </span> gebruikt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Een tijdstempel van 10 cijfers (UTC UNIX) in seconden. Met de tijdstempel kunt u elke bestandsnaam uniek maken. </p> 
    <!-- 
     <p> <p>Note:  Audience Manager does not use the timestamp during processing of inbound files. The timestamp in the filename has been deprecated in Audience Manager but is still required for backwards compatibility. </p> </p> 
    --> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> (.sync|.overwrite)</code> </p> </td> 
   <td colname="col2"> <p>Synchronisatieopties met: </p> <p> 
     <ul id="ul_DAAF61EC636C4456BECDDC34C3F86E83"> 
      <li id="li_6EC6DE442B4546AA9F4F800D65C8A4EC"> <code> sync</code>: Normaal scenario wanneer externe gegevensproviders kenmerken per gebruiker verzenden die in het Audience Manager-systeem moeten worden toegevoegd of verwijderd. </li> 
      <li id="li_8FE8430C2C004F87835D55231A0D99C9"> <code> overwrite</code>: Laat gegevensleveranciers een lijst van eigenschappen op een per-gebruikersbasis verzenden die alle bestaande derdeeigenschappen van deze gebruiker voor deze gegevensleverancier in Audience Manager zou moeten beschrijven. U hoeft niet al uw gebruikers op te nemen in een overschrijvingsbestand. Neem alleen de gebruikers op die u wilt wijzigen. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i>]</code> </p> </td> 
   <td colname="col2"> <p>Een geheel getal. Wordt gebruikt wanneer u grote bestanden in meerdere onderdelen splitst om de verwerkingstijd te verbeteren. Het nummer geeft aan welk deel van het oorspronkelijke bestand u wilt invoeren. </p> <p>Voor een efficiënte bestandsverwerking splitst u de gegevensbestanden zoals aangegeven: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Niet-gecomprimeerd: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Gecomprimeerd: 200-300 MB </li> 
    </ul> <p>Zie de eerste 2 <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md#file-name-examples"> voorbeelden van bestandsnaam </a> hieronder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gebruik alleen gzip-compressie wanneer u bestanden naar Amazon S3 verzendt. Wanneer deze bestanden zijn gecomprimeerd, krijgen ze de extensie <code> .gz</code> . Gebruik geen .zip-compressie. </p> <p>Gecomprimeerde bestanden moeten 3 GB of kleiner zijn. Neem contact op met de klantenservice als uw bestanden groter zijn. Hoewel Audience Manager grote bestanden kan verwerken, kunnen we u misschien helpen uw bestanden kleiner te maken en gegevensoverdracht efficiënter te maken. Zie <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden </a> . </p> </td> 
  </tr> 
 </tbody> 
</table>

## Voorbeelden van bestandsnaam {#file-name-examples}

In de volgende voorbeelden worden correct opgemaakte bestandsnamen weergegeven. De bestandsnamen kunnen er ongeveer hetzelfde uitzien.

<ul class="simplelist"> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.1.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync.2.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.sync</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_567_1366545717.sync.gz</code> </li> 
 <li> <code> s3n://&lt;AWS_Bucket&gt;/&lt;partner_name&gt;/date=2016-05-09/ftp_dpm_478_1366545717.overwrite</code> </li> 
</ul>

U kunt [ downloaden ](assets/ftp_dpm_1234_1445374061.overwrite) het steekproefdossier als u extra voorbeelden wilt. Dit bestand is opgeslagen met de bestandsextensie `.overwrite` . Open het met een eenvoudige teksteditor.

## Geaccepteerde bestandsgrootten {#accepted-file-sizes}

Houd rekening met de onderstaande afbeeldingen voor de snelste/vroegste verwerking van uw bestanden en voor beperkingen van de bestandsgrootte wanneer u gegevens naar een map [!DNL Audience Manager] / [!DNL Amazon S3] verzendt.

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


>[!NOTE]
>
>Lege bestanden worden tijdens het proces voor gegevensvalidatie als ongeldig gemarkeerd en niet verwerkt.

## Limieten voor lijnlengte {#line-limits}

De binnenkomende gegevensdossiers hebben een lijnlengtelimiet van 102400 bytes. Lijnen die deze limiet overschrijden, worden van de overdracht uitgesloten.

>[!MORELIKETHIS]
>
>* [ de Vereisten van de Naam van FTP voor de Binnenkomende Dossiers van Gegevens ](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md)
