---
description: Veelgestelde vragen over het opnemen van offline data in Audience Manager.
keywords: ftp of s3;s3 of ftp
seo-description: Veelgestelde vragen over het opnemen van offline data in Audience Manager.
seo-title: Veelgestelde vragen over opname van binnenkomende klantdata
solution: Audience Manager
title: Veelgestelde vragen over opname van binnenkomende klantdata
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
feature: Offline gegevens aan boord
exl-id: 48eef5f1-0655-4dac-9ab4-74b11c705c13
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '1360'
ht-degree: 89%

---

# Veelgestelde vragen over opname van binnenkomende klantdata{#inbound-customer-data-ingestion-faq}

Veelgestelde vragen over het opnemen van offline data in Audience Manager.

 

**Kunt u het onboardingproces samenvatten?**

Het onboardingproces bestaat uit twee stappen die worden beschreven in [Overzicht van batchdata verzenden naar Audience Manager](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md):

* Stap 1: synchroniseer gebruikers-id’s;
* Stap 2: maak uw binnenkomende databestand en breng het over waarbij u zich houdt aan de vereisten van de bestandsindeling.

 

**Kunt u het implementatieproces samenvatten?**

We raden het volgende aan:

* Werk samen met uw dataprovider om het dagelijks binnenkomende databestand volgens de specificaties van Adobe in te delen. Zie de volgende documentatie voor vereisten voor bestandsnaamgeving en syntaxis:
   * [Naam- en contentvereisten voor id-synchronisatiebestanden](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md)
   * [Content van binnenkomende databestanden: syntaxis, ongeldige tekens, variabelen en voorbeelden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)
   * [Vereisten voor naam en bestandsgrootte van binnenkomende Amazon S3-databestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)
* Werk samen met uw [!DNL Adobe]-consultant om een testdatabestand naar [!DNL Adobe] te verzenden voor indelingverificatie.
* Werk samen met uw [!DNL Adobe]-consultant om een taxonomie te maken die geschikt is voor het interpreteren van de content van het databestand.
* Bevestig in de staging-/ontwikkelomgeving dat de id-synchronisatie is geconfigureerd om de bezoekers-id van de dataprovider correct op te halen en deze in real time naar de [!DNL Audience Manager]-servers over te brengen.
* Gebruik DIL/ID-synchronisatie voor productie. De synchronisatie van id’s is door uw Adobe-consultant al geconfigureerd als een module in de DIL-code.
* Breng productiedatabestanden over naar [!DNL Audience Manager]. Gezien de afhankelijkheden van id-synchronisatietoewijzingen is het misschien handig om de overdracht van data tot een week na productiecode-implementatie te starten, hoewel u de databestandsoverdracht kunt starten zodra de code in productie gaat.

 

**Welke FTP-modus moet ik gebruiken om gecomprimeerde of versleutelde bestanden over te brengen?**

Zie [Bestandscompressie voor binnenkomende dataoverdrachtsbestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

>[!WARNING]
>
>De ondersteuning voor FTP-configuraties wordt geleidelijk afgeschaft. Hoewel de opname van binnenkomende databestanden nog steeds wordt ondersteund in bestaande FTP-integraties, raden we sterk aan om Amazon S3 te gebruiken voor het onboarden van offline data voor nieuwe integraties. Zie [Vereisten voor naam en bestandsgrootte van binnenkomende Amazon S3-databestanden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) voor meer informatie.

 

**Kan ik een binnenkomend databestand ([!DNL .sync] - of [!DNL .overwrite] -bestand) uploaden alvorens code [!DNL Audience Manager] in productie te implementeren?**

Ja. Zolang u [!UICONTROL cross-device data source] gebruikt om de gegevens op te slaan van CRM die u uploadt, slaat de Audience Manager altijd de gegevens op. In feite, na de [!UICONTROL Profile Merge Rules] verhogingen die Audience Manager in oktober 2019 lanceerde die voor off-line-slechts gebruiksgevallen toestaan, kunt u gegevens uploaden en actie op gegevens zonder de code van de Audience Manager in productie in het geheel op te stellen. Zie:

* [Overzicht van de verbeteringen op het gebied van regels voor profielsamenvoeging](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* [!UICONTROL People-based Destinations] -  [Personalisatie op basis van gegevens die alleen offline beschikbaar zijn](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

<br>

<!---
* If the data provider is configured to use [Profile Link](../features/profile-merge-rules/merge-rules-overview.md) for cross-device targeting, the data available for targeting shortly after an ID sync identifies to the matching [!DNL Audience Manager] visitor ID.

* If the data provider is not configured to use the [!UICONTROL Profile Link] feature, [!DNL Audience Manager] processes only the data for visitor IDs in the inbound data file that have been previously synced/matched back to an [!DNL Audience Manager] visitor ID.

Consider the following use cases in which the data provider is not configured to use [!UICONTROL Profile Merge]:

<table id="table_1A367ED6D016428FB21B3F3BC261BA98"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Use Case </th> 
   <th colname="col2" class="entry"> Description </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Case 1</b> </p> </td> 
   <td colname="col2"> <p>On Monday, a visitor identified in the CRM database as visitor ABC logs in, which initiates a client-side ID sync. <span class="keyword"> Audience Manager</span> stores the mapping of visitor ABC to <span class="keyword"> Audience Manager</span> visitor 123. </p> <p>On Tuesday, the CRM database transfers a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager </span>server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> ABC "gender"="male","luxury_shopper"="yes"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> <p> 
     <ul id="ul_7616432BF9874E7D94F3101C71F73C81"> 
      <li id="li_DC4F5E63D8134A29B703BDF264F02F65">Recognizes visitor ABC from the stored ID sync mapping. </li> 
      <li id="li_62E085FC184D41C3863B1CE832F77946"> Associates the traits <code> male</code> and <code> luxury_shopper</code> with the visitor 123 profile. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 2</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the CRM database pushes a data file (<span class="filepath"> .sync</span>) to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes"</code> </li> 
     </ul> </p> <p> <span class="keyword"> Audience Manager</span> does not have a record of this visitor (or an associated visitor ID) so this record is not processed. </p> <p>On Tuesday, visitor DEF logs in. This action initiates the first client-side ID sync for that visitor. This action maps visitor DEF to <span class="keyword"> Audience Manager</span> ID 456. However, this visitor does not have CRM data associated with their profile. As a result, <span class="keyword"> Audience Manager</span> does not go back and reprocess old files. </p> <p>On Wednesday, the CRM database pushes another data file to the <span class="keyword"> Audience Manager</span> server with the following record: </p> <p> 
     <ul class="simplelist"> 
      <li><code> DEF "gender"="female","wine_enthusiast"="yes","dma"="paris"</code> </li> 
     </ul> </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_E853DA091D9042DAB19774383841D3A3"> 
     <li id="li_64D64A16E99E492BAAE1080867F854A9">Recognizes visitor DEF from the stored ID sync mapping. </li> 
     <li id="li_9CEE7A7B1A954FF6AEEBF8844074CFBB">Associates the traits <code> female</code>, <code> paris</code>, and <code> wine_enthusiast</code> with the visitor 456 profile. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Case 3</b> </p> </td> 
   <td colname="col2"> <p>On Monday, the <span class="keyword"> Audience Manager</span> server receives two files with the following records: </p> <p> <code> .sync</code> file containing: </p> <p> 
     <ul class="simplelist"> 
      <li><code> GHI 123456789</code> </li> 
     </ul> </p> <p> <code> .overwrite</code> file containing: </p> 
    <ul id="ul_084AE448C60447ACA9B1E0C30EAA3E3E"> 
     <li id="li_C68B7BBFE7CA4D22B606D939E32FF4FB"><code> GHI "gender"="male" "wine_enthusiast"="no"</code> </li> 
     <li id="li_FDBCAAFBD606477E8690EA80AD455A81"><code> JKL "gender"="female" "wine_enthusiast"="yes"</code> </li> 
    </ul> <p><span class="keyword"> Audience Manager</span> holds a mapped record of visitor JKL to ID 789, from a previous ID sync. </p> <p>In this case, <span class="keyword"> Audience Manager</span>: </p> 
    <ul id="ul_4D083CEA7F1B4F6BBBBB841C21293751"> 
     <li id="li_6DABD380311D49738DAD98F5E6DE45B8">Recognizes visitor JKL from the stored ID sync mapping. </li> 
     <li id="li_CCEF77240E5C4A03AAE347440D73F0BB">Associates the traits <code> female</code> and <code> wine_enthusiast</code> with visitor ID 789's profile. </li> 
     <li id="li_273F8FD7C6214488A26AAFFA6DE043E5">Ignores the trait association for visitor GHI, since its ID was only synced in the current batch. To associate traits with visitor GHI, you need to include them in future <code> .overwrite</code> files. </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

-->

**Hoe laat moet ik mijn bestand overbrengen?**

[!DNL Audience Manager] controleert en verwerkt bestanden meermalen op een dag. Upload uw data wanneer u klaar bent.

 

**Hoe lang duurt het voordat data uit een geüpload bestand beschikbaar zijn voor targeting?**

Data zijn na 48 uur beschikbaar voor targeting. Interpreteer de e-mail met de melding dat de data zijn geüpload, niet als een bevestiging dat de data beschikbaar zijn. Dit betekent alleen dat [!DNL Audience Manager] het bestand heeft opgehaald en de eerste verwerkingsstap heeft voltooid.

 

**Hoe vaak moet ik bestanden verzenden en moeten dit volledige of incrementele bestanden zijn?**

U kunt het beste eenmaal per dag een incrementeel bestand verzenden voor nieuwe bezoekers en voor bezoekers van wie de data zijn gewijzigd. Veel [!DNL Audience Manager]-klanten sturen één keer per maand een volledig bestand. Deze bestandsintervallen en incrementen zijn echter flexibel. U kunt data het best verzenden in stappen en op tijdstippen die voor u zinvol zijn.

 

**Hoe lang bewaart Audience Manager mijn bestanden op de server?**

FTP-bestanden worden verwijderd nadat ze zijn verwerkt. [!DNL S3]-bestanden worden na 30 dagen verwijderd. Bestanden die niet kunnen worden verwerkt vanwege de indeling, syntaxis of andere fouten, worden verwijderd. Zie ook [Veelgestelde vragen over privacy en dataretentie](../faq/faq-privacy.md).

 

**Wat is het verschil tussen volledige en incrementele bestanden?**

* **Volledig:** een volledig bestand overschrijft alle bestaande bezoekersprofielen en vervangt deze door de data in het bestand. Volledige bestanden zijn te herkennen aan de `.overwrite`-tag die aan de bestandsnaam wordt toegevoegd. U kunt een `.overwrite`-bestand gebruiken om bezoekerseigenschappen opnieuw in te stellen of om verouderde eigenschappen te verwijderen.

   >[!NOTE]
   >
   >De [!DNL .overwrite]-bestanden overschrijven alleen [!DNL Audience Manager]-profieldata die aan deze dataprovider zijn gekoppeld. Met andere woorden: alle [!DNL Audience Manager]-data die aan de bezoeker zijn gekoppeld, blijven intact nadat een [!DNL .overwrite]-bestand is verwerkt.

* **Incrementeel:** een incrementeel bestand voegt nieuwe data toe aan uw bestaande bezoekersprofielen. Incrementele bestanden zijn te herkennen aan de `.sync`-tag die aan de bestandsnaam wordt toegevoegd. Als u een incrementeel bestand verzendt, worden bestaande profielen niet gewist of overschreven.

De volgende gebruiksscenario’s tonen aan hoe deze bestandstypen van invloed zijn op opgeslagen bezoekersprofielen.

| Gebruiksscenario | Beschrijving |
|---|---|
| Incrementeel en volledig | <ul><li>Dag 1 `.sync` bestandscontent: `visitor123 = a,b,c`</li><li>Dag 2 `.overwrite` bestandscontent: `visitor123 = c,d,e`</li><li>Dag 3 bezoekersprofiel-id 123 content: `c,d,e`</li></ul> |
| Alleen incrementeel | <ul><li>Dag 1 `.sync` bestandscontent: `visitor123 = a,b,c`</li><li>Dag 2 `.sync` bestandscontent: `visitor123 = c,d,e`</li><li>Dag 3 bezoekersprofiel-id 123 content: `a,b,c,d,e`</li></ul> |

Zie voor meer informatie over volledige en incrementele bestandstypen:

* [Vereisten voor naam en bestandsgrootte van binnenkomende Amazon S3-data...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Wat gebeurt er als ik een bestand met id’s verzend voor bezoekers die nooit id-synchronisatie op de pagina hebben uitgevoerd?**

Tijdens de verwerking slaat [!DNL Audience Manager] deze record over en gaat naar de volgende. Als er een [DPID (Data Provider ID)](../reference/ids-in-aam.md) is ingesteld als cross-device DPID, worden data die zijn opgenomen vóór een id-synchronisatie, opgeslagen en zijn beschikbaar voor gebruik kort na de id-synchronisatie.

 

**Wat is het tijdstempel, waarvoor is het en kunt u een voorbeeld geven?**

Tijdstempels worden gebruikt voor vastleggen en bewaren. Ze worden vereist door de syntaxis die wordt gebruikt voor correct geformatteerde namen van binnenkomende bestanden. Zie:

* [Amazon S3-naamvereisten voor binnenkomende databestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**Wat is een  [!DNL Data Provider ID (DPID)] en hoe krijg ik het?**

Uw Adobe-consultant wijst een driecijferige of viercijferige [DPID (Data Provider ID)](../reference/ids-in-aam.md) toe aan uw specifieke databron. Deze id is uniek en verandert niet.

 

**Hoe groot kunnen de dagelijkse databestanden zijn?**

Zie [Bestandscompressie voor binnenkomende dataoverdrachtsbestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

 

**Biedt Audience Manager ondersteuning voor bestandscompressie?**

Ja, zie:

* [Bestandscompressie voor binnenkomende dataoverdrachtbestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Amazon S3-naamvereisten voor binnenkomende databestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

 

**De primaire sleutel in mijn databrondatabase is een e-mailadres. Wordt dat beschouwd als persoonlijk identificeerbare informatie?**

Ja. [!DNL Audience Manager] slaat geen e-mailadressen op in zijn database. Bezoekers moeten een willekeurig gegenereerde id of een eenrichtingsversie van het e-mailadres krijgen voordat ze id-synchronisaties starten.

 

**Is de content van het databestand hoofdlettergevoelig? Hoe zit het met de id-synchronisatie?**

Een databestand bestaat uit twee basisonderdelen: een [!UICONTROL User ID] (zie [!UICONTROL User ID] in [Definities van bestandsvariabelen](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)) en profieldata, meestal in de vorm van sleutelwaardeparen of codes. De [!UICONTROL User ID] is hoofdlettergevoelig. Doorgaans zijn profiel- of sleutelwaardedata niet hoofdlettergevoelig.

 

**Moet ik FTP of [!DNL Amazon S3] gebruiken om bestanden over te brengen?**

Als best practice adviseren wij [!DNL Amazon S3] omdat het proces eenvoudiger is. Met [!DNL Audience Manager] worden FTP-bestanden naar een willekeurige [!DNL S3]-locatie overgebracht, dus het proces is gestroomlijnder als u de bestanden zelf op [!DNL Amazon S3] neerzet. Bovendien gebruiken klanten die tegelijkertijd naar de FTP-server uploaden, dezelfde FTP-bandbreedte, zodat ze lagere uploadsnelheden kunnen verwachten. [!DNL Amazon S3] wordt ook gerepliceerd en gedistribueerd, zodat dit doorgaans veiliger en betrouwbaarder is dan een FTP-server. Zie [Informatie over Amazon S3](../reference/amazon-s3.md)voor meer informatie.

>[!WARNING]
>
>De ondersteuning voor FTP-configuraties wordt geleidelijk afgeschaft. Terwijl de binnenkomende gegevensdossieropname nog in bestaande integratie van FTP wordt gesteund, adviseren wij sterk gebruikend [!DNL Amazon S3] aan boord off-line gegevens voor nieuwe integratie. Zie [Vereisten voor naam en bestandsgrootte van binnenkomende Amazon S3-databestanden](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md) voor meer informatie.

 

**Hoe verwerkt Audience Manager binnenkomende bestanden?**

[!DNL Audience Manager] Gebruikt [!DNL Amazon Simple Queue Service (SQS)] voor verwerking van binnenkomende data. Dit werkt als volgt:

1. [!DNL Audience Manager]-klanten uploaden hun binnenkomende data naar een [!DNL Amazon S3]-bucket.
1. De data gaan naar de [!DNL Amazon SQS]-wachtrij en wachten op verwerking door [!DNL Audience Manager].
1. [!DNL Audience Manager] leest tot 119000 vermeldingen van de [!DNL Amazon SQS]-wachtrij en verdeelt die in maximaal drie batches. De bestanden in elke batch worden tegelijkertijd verwerkt.

 

**Ik moet meerdere bestanden tegelijk uploaden. Worden de bestanden gelijktijdig verwerkt?**

Dat hangt ervan af. [!DNL Audience Manager] leest tot 119000 vermeldingen van de [!DNL Amazon SQS]-wachtrij en verdeelt die in maximaal drie batches. Uw bestanden worden alleen tegelijkertijd verwerkt als ze in dezelfde batch terechtkomen. Vanwege de grote hoeveelheid data die dagelijks door [!DNL Audience Manager] worden opgenomen, kunnen we echter geen enkele volgorde voor bestandsverwerking garanderen.

>[!MORELIKETHIS]
>
>* [Beschrijving van batchdataoverdracht](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

