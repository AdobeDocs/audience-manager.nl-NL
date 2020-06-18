---
description: Beschrijft de vereiste gebieden, syntaxis, noemende overeenkomsten en dossiergrootte u moet volgen wanneer het verzenden van gegevens naar Audience Manager. Stel de namen en grootten van de bestanden in volgens deze specificaties wanneer u gegevens naar een FTP-map van een Audience Manager verzendt.
seo-description: Beschrijft de vereiste gebieden, syntaxis, noemende overeenkomsten en dossiergrootte u moet volgen wanneer het verzenden van gegevens naar Audience Manager. Stel de namen en grootten van de bestanden in volgens deze specificaties wanneer u gegevens naar een FTP-map van een Audience Manager verzendt.
seo-title: Vereisten voor FTP-naam en bestandsgrootte voor binnenkomende gegevensbestanden
solution: Audience Manager
title: Vereisten voor FTP-naam en bestandsgrootte voor binnenkomende gegevensbestanden
uuid: 49eaafac-5cb0-482f-872a-84c056016bdb
translation-type: tm+mt
source-git-commit: 50c5b654d962649c98f1c740cd17967e70b957bc
workflow-type: tm+mt
source-wordcount: '899'
ht-degree: 2%

---


# Vereisten voor FTP-naam en bestandsgrootte voor binnenkomende gegevensbestanden{#ftp-name-and-file-size-requirements-for-inbound-data-files}

Beschrijft de vereiste gebieden, syntaxis, noemende overeenkomsten en dossiergrootte u moet volgen wanneer het verzenden van gegevens naar Audience Manager. Stel de namen en grootten van de bestanden in op basis van deze specificaties wanneer u gegevens naar een [!DNL FTP] map Audience Manager verzendt.

>[!WARNING]
>
>Wij nemen geleidelijk de steun voor [!DNL FTP] configuraties af. Terwijl de binnenkomende gegevensdossieropname nog in bestaande [!DNL FTP] integratie wordt gesteund, adviseren wij sterk gebruikend [!DNL Amazon S3] aan boord off-line gegevens voor nieuwe integratie. Zie [Amazon S3 Name and File Size Requirements for Inbound Data Files](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) voor meer informatie.

>[!NOTE]
>
>De tekststijlen (`monospaced text`, *cursief*, haakjes `[ ]` `( )`, enz.) in dit document de elementen en opties van de code aangeven. Zie [Stijlconventies voor code- en tekstelementen](../../../reference/code-style-elements.md) voor meer informatie.

## Syntaxis bestandsnaam {#file-name-syntax}

[!DNL FTP] bestandsnamen bevatten de volgende vereiste en optionele elementen:

`ftp_dpm_DPID[_DPID_TARGET_DATA_OWNER]_TIMESTAMP(.sync|.overwrite)[.SPLIT_NUMBER][.gz]`

Voor andere toegelaten dossiernaamformaten, zie de Integraties [van de Partner van de](/help/using/integration/sending-audience-data/custom-partner-integrations.md)Douane.

>[!NOTE] {Important=&quot;high&quot;}
>
>[!DNL Audience Manager] alleen bestanden verwerkt [!DNL ASCII] en [!DNL UTF-8] gecodeerd.

### Elementen benoemen

De tabel definieert de elementen in een [!DNL FTP] bestandsnaam.

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
   <td colname="col2"> <p>Het pad naar en de naam van de FTP-map van de <span class="keyword"> Audience Manager</span> . Neem contact op met uw accountmanager voor de FTP-map en de referenties. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>DPID</i> </code> </p> </td> 
   <td colname="col2"> <p>Een id die de <span class="keyword"> Audience Manager</span> vertelt of een gegevensbestand uw eigen gebruikers-id's of Android- of iOS-id's bevat. Accepteert de volgende opties: </p> 
    <ul id="ul_818EB3EB2E5543F0B048BCEBB6699562"> 
     <li id="li_ED6B13CB49794F6BA3DB6D807F788BAF"> <b>Id van gegevenspartner:</b> Dit is een unieke ID-Audience Manager die aan uw bedrijf of organisatie wordt toegewezen. Gebruik deze toegewezen id in een bestandsnaam wanneer u gegevens verzendt die uw eigen gebruikers-id's bevatten. Bijvoorbeeld, <code>...ftp_dpm_21_123456789.sync</code> vertelt <span class="keyword"> Audience Manager</span> dat een partner met identiteitskaart 21 het dossier verzond en het bevat gebruiker IDs die door die partner wordt toegewezen. </li> 
     <li id="li_1955911BA11F4F458227B77F383F25A3"> <b>Android-id's (GAID):</b> Gebruik ID 20914 in een gegevensbestandsnaam als deze Android-id bevat. Geeft bijvoorbeeld aan <code>...ftp_dpm_20914_123456789.sync</code> de <span class="keyword"> Audience Manager</span> dat het gegevensbestand alleen Android-id's bevat. </li> 
     <li id="li_54E7734C121646AF82095806DD1AED61"> <b>iOS-id's (IDFA):</b> Gebruik ID 20915 in een gegevensbestandsnaam als deze iOS-id's bevat. Geeft bijvoorbeeld aan <code>...ftp_dpm_20915_123456789.sync</code> de <span class="keyword"> Audience Manager</span> dat het gegevensbestand alleen iOS-id's bevat. </li> 
    </ul> <p> <p>Opmerking:  Gebruik geen ID-typen in uw gegevensbestanden. Als uw bestandsnaam bijvoorbeeld de Android-id bevat, plaats dan geen iOS-id's of uw eigen id's in het gegevensbestand. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>_DPID_TARGET_DATA_OWNER</i> </code> </p> </td> 
   <td colname="col2"> <p>Een tijdelijke aanduiding voor een id. U kunt de DPID bijvoorbeeld instellen op de <span class="keyword"> Audience Manager</span> -id als u een gegevensbron-id of een Android- of iOS-id instelt. Hierdoor kan de <span class="keyword"> Audience Manager</span> de bestandsgegevens weer aan uw organisatie koppelen. </p> <p>Bijvoorbeeld: </p> 
    <ul id="ul_55EBBCB11F2B4A858AEFBFA1CD99E286"> 
     <li id="li_3404428F4E3D49A5AB6EDF56310D923F"> <code>...ftp_dpm_33_21_1234567890.sync</code> toont een partner met identiteitskaart 21 in gegevens van een gegevensbron heeft verzonden die identiteitskaart 33 gebruikt. </li> 
     <li id="li_CF8D5AF678764E9984A088FD5D7BBFB6"> <code>...ftp_dpm_20914_21_1234567890.sync</code> toont een partner met id 21 gegevens heeft verzonden die Android-id's bevatten. </li> 
     <li id="li_3D73168391D7443BADDF27153090274D"> <code>...ftp_dpm_20915_21_1234567890.sync</code> toont een partner met ID 21 gegevens heeft verzonden die iOS IDs bevatten. </li> 
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
   <td colname="col1"> <p> <code>[<i>SPLIT_NUMBER</i></code>] </p> </td> 
   <td colname="col2"> <p>Een geheel getal. Wordt gebruikt wanneer u grote bestanden in meerdere onderdelen splitst om de verwerkingstijd te verbeteren. Het nummer geeft aan welk deel van het oorspronkelijke bestand u wilt invoeren. </p> <p>Voor een efficiënte bestandsverwerking splitst u de gegevensbestanden zoals aangegeven: </p> 
    <ul id="ul_E9446C5CA42649658093904D49D4369C"> 
     <li id="li_B275708DFE3F49E29EFAE6B838429E39">Niet-gecomprimeerd: 1 GB </li> 
     <li id="li_A9638EB46ED14E0680B6575D5457E32F">Gecomprimeerd: 200-300 MB </li> 
    </ul> <p>Zie de eerste twee <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-ftp-filenames.md#file-name-examples"> voorbeelden</a> van bestandsnaam hieronder. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> <i>TIMESTAMP</i> </code> </p> </td> 
   <td colname="col2"> <p>Een tijdstempel van 10 cijfers (UTC UNIX) in seconden. Met de tijdstempel kunt u elke bestandsnaam uniek maken. </p> 
    <draft-comment> 
     <p> <p>Opmerking:  Audience Manager gebruikt de tijdstempel niet tijdens het verwerken van binnenkomende bestanden. Het tijdstempel in de bestandsnaam is afgekeurd in de Audience Manager, maar is nog steeds vereist voor achterwaartse compatibiliteit. </p> </p> 
    </draft-comment> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <code> [.gz]</code> </p> </td> 
   <td colname="col2"> <p>Gzip is de toegestane compressie-indeling voor een FTP-bestandsnaam. Als u bestandscompressie gebruikt, moet u ervoor zorgen dat de bestandsnaam de juiste extensie heeft. </p> <p>Gecomprimeerde bestanden moeten 3 GB of kleiner zijn. Neem contact op met de klantenservice als uw bestanden groter zijn. Hoewel Audience Manager grote bestanden kan verwerken, kunnen we u helpen de bestanden te verkleinen en de gegevensoverdracht efficiënter te maken. Zie <a href="../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md"> Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden</a> . </p> </td> 
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

[Download](assets/ftp_dpm_1234_1445374061.overwrite) het voorbeeldbestand als u meer voorbeelden nodig hebt. Dit bestand wordt opgeslagen met de `.overwrite` bestandsextensie. Open het met een eenvoudige teksteditor.

## Geaccepteerde bestandsgrootten {#accepted-file-sizes}

Houd rekening met de onderstaande cijfers voor de snelste/vroegste verwerking van uw bestanden en voor beperkingen van de bestandsgrootte wanneer u gegevens naar een [!DNL Audience Manager] / [!DNL FTP] directory verzendt.

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
>* [Amazon S3-naamvereisten voor binnenkomende gegevensbestanden](../../../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

