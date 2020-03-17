---
description: Veelgestelde vragen over het plaatsen van offlinegegevens in de Manager van het Publiek.
keywords: ftp or s3;s3 or ftp
seo-description: Veelgestelde vragen over het plaatsen van offlinegegevens in de Manager van het Publiek.
seo-title: Binnenkomende Veelgestelde vragen over gegevensinvoer van klanten
solution: Audience Manager
title: Binnenkomende Veelgestelde vragen over gegevensinvoer van klanten
uuid: 491e9ec1-4731-46a8-86e7-d8c613e6cedc
translation-type: tm+mt
source-git-commit: 6b9afa7c53f5bc2738f185440160f62a87e0bda1

---


# Binnenkomende Veelgestelde vragen over gegevensinvoer van klanten{#inbound-customer-data-ingestion-faq}

Veelgestelde vragen over het plaatsen van offlinegegevens in de Manager van het Publiek.

<br> 

<!-- 

c_inbound_crm_data_ingestion.xml

 -->

**Kunt u het instapproces samenvatten?**

Het instapproces bestaat uit twee kerncomponenten die worden beschreven in het beschreven [](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)batchgegevensoverdrachtproces. Deze omvatten:

* ID-synchronisatie
* Binnenkomend gegevensbestand ( [!DNL .sync] bestand of [!DNL .overwrite] bestand)

<!-- 

Removed the Data Translation File bullet from the list above.

 -->

Hieronder volgt een lijst met vragen en antwoorden die u na het bekijken van de documentatie nuttig kunt vinden.

>[!NOTE]
>
>De voorbeelden in deze sectie worden vereenvoudigd of verkort voor beknoptheid en demonstratie. Raadpleeg de documentatie bij Binnenkomende gegevensinsluiting voor gedetailleerde specificaties over bestandsindelingen en syntaxis.

<br> 

**Kunt u het implementatieproces samenvatten?**

We raden het volgende aan:

* Werk met uw gegevensleverancier om het dagelijkse binnenkomende gegevensbestand volgens [!DNL Adobe] specificaties te formatteren.
* Breng een bestand met testgegevens over naar [!DNL Adobe] voor formaatcontrole.
* Werk samen met uw [!DNL Adobe] consultant om een taxonomie te maken die geschikt is voor het interpreteren van de inhoud van het gegevensbestand.
* Bevestig in de testomgeving/ontwikkelomgeving dat de id-synchronisatie is geconfigureerd om de bezoeker-id van de gegevensaanbieder correct op te halen en deze in realtime naar de [!DNL Audience Manager] servers over te brengen.
* DIL/ID-synchronisatie gebruiken voor productie. De synchronisatie van de id wordt al geconfigureerd als een module in de DIL-code door uw Adobe-consultant.
* Productiegegevensbestanden overbrengen naar [!DNL Audience Manager]. Gezien de gebiedsdelen op de afbeeldingen van de synchronisatie van identiteitskaart, zou het zinvol kunnen zijn beginnen gegevens over te brengen tot één week na productie-code plaatsing, hoewel u kunt beginnen de gegevensdossiers over te brengen zodra de code in productie gaat.

<br> 

**Welke FTP-modus moet ik gebruiken om gecomprimeerde of gecodeerde bestanden over te brengen?**

Zie [Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Kan ik een binnenkomend databestand (bestand[!DNL .sync]of[!DNL .overwrite]) uploaden alvorens code[!DNL Audience Manager]in productie te implementeren?**

Ja. Zolang u een dwars-apparatengegevensbron gebruikt om de gegevens op te slaan van CRM die u uploadt, slaat de Manager van de Publiek altijd de gegevens op. In feite, na de verbeteringen van de Regels van de Fusie van het Profiel die de Manager van de Publiek in Oktober 2019 lanceerde die voor off-line-slechts gebruiksgevallen toestaan, kunt u en actie op gegevens uploaden zonder de code van de Manager van de Publiek in productie bij allen op te stellen. Zie:

* [Overzicht van verbeteringen in regels voor het samenvoegen van profielen](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/overview-of-profile-merge-rule-enhancements.html)
* Op mensen gebaseerde Doelen - [Personalisering die op off-line-slechts Gegevens wordt gebaseerd](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/destinations/people-based/implementation-guide/people-based-destinations-workflow-offline.html)

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

[!DNL Audience Manager] controleert en verwerkt dossiers veelvoudige tijden door de dag. Upload uw gegevens wanneer u klaar bent.

<br> 

**Hoe lang duurt het voordat gegevens uit een geüpload bestand beschikbaar zijn voor de doelversie?**

Er zijn gegevens beschikbaar voor doelgericht gebruik na 48 uur. U moet de e-mail met de melding dat de gegevens zijn geüpload, ook niet interpreteren als een instructie dat de gegevens beschikbaar zijn. Dit betekent alleen dat het bestand [!DNL Audience Manager] is opgehaald en de eerste verwerkingsstap is voltooid.

<br> 

**Hoe vaak moet ik bestanden verzenden en moeten deze volledige of incrementele bestanden zijn?**

U kunt het beste één keer per dag een incrementeel bestand verzenden voor nieuwe bezoekers en voor bezoekers wier gegevens zijn gewijzigd. Veel [!DNL Audience Manager] klanten sturen één keer per maand een volledig bestand. Deze bestandsintervallen en -toenamen zijn echter flexibel. U moet gegevens in stappen verzenden en op momenten die voor u zinvol zijn.

<br> 

**Hoe lang houdt Audience Manager mijn bestanden op de server?**

FTP-bestanden worden verwijderd nadat ze zijn verwerkt. [!DNL S3] bestanden worden na 30 dagen verwijderd. Bestanden die niet kunnen worden verwerkt vanwege een indeling, syntaxis of andere fout, worden verwijderd. Zie ook de veelgestelde vragen over [privacy en gegevensbewaring](../faq/faq-privacy.md).

<br> 

**Wat is het verschil tussen volledige en incrementele bestanden?**

* **Volledig:** Een volledig bestand overschrijft alle bestaande bezoekersprofielen en vervangt deze door de gegevens in het bestand. Alle bestanden worden geïdentificeerd met de `.overwrite` tag die aan de bestandsnaam wordt toegevoegd. U kunt een `.overwrite` bestand gebruiken om de eigenschappen van de bezoeker opnieuw in te stellen of verouderde, verouderde kenmerken te verwijderen.

   >[!NOTE]
   >
   >De [!DNL .overwrite] bestanden overschrijven alleen de [!DNL Audience Manager] profielgegevens die aan deze gegevensaanbieder zijn gekoppeld. Met andere woorden, alle [!DNL Adobe Analytics] gegevens die aan de bezoeker zijn gekoppeld, blijven intact nadat een [!DNL .overwrite] bestand is verwerkt.

* **Incrementeel:** Een incrementeel bestand voegt nieuwe gegevens toe aan uw bestaande bezoekersprofielen. Incrementele bestanden worden aangeduid met de `.sync` tag die aan de bestandsnaam wordt toegevoegd. Als u een incrementeel bestand verzendt, worden bestaande profielen niet gewist of overschreven.

De volgende gebruiksgevallen tonen aan hoe deze bestandstypen van invloed zijn op opgeslagen bezoekersprofielen.

<table id="table_CE43B49508384ABF8B25FA8A8FFE5362"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Hoofdletters gebruiken </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Incrementeel en volledig</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_E89301D815174D45B9B238F2CDE6CCC6"> 
      <li id="li_FA841FEEC0534AD59D1AB61DD5B9DEC4">Dag 1 <code> .sync</code> bestandsinhoud: <code> visitor123 = a,b,c</code> </li> 
      <li id="li_0E1A57B04D26481C8C41EBA63ACBEFE0">Dag 2 <code> .overwrite</code> bestandsinhoud: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_497A5604AD9A49A2ADE548C7CE158F0E"> ID 123 van bezoekersprofiel van dag 3 bevat <code> c,d,e </code> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Alleen incrementeel</b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8271C9796BD040E4B8DC64DCE4FE2AD3"> 
      <li id="li_347959BDE83549F794E6661C95097891">Dag 1 <code> .sync</code> bestandsinhoud: <code> visitor123 = a,b,c </code> </li> 
      <li id="li_B25D96526DE94171A3A5DC8DB7A19415">Dag 2 <code> .sync</code> bestandsinhoud: <code> visitor123 = c,d,e</code> </li> 
      <li id="li_6E17809D49C74F4991B0B445469055E6">ID 123 van bezoekersprofiel van dag 3 bevat <code> a,b,c,d,e</code> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

Zie voor meer informatie over volledige en incrementele bestandstypen:

* [Vereisten voor naam en bestandsgrootte van Amazon S3 voor binnenkomende gegevens...](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)

<br> 

**Wat gebeurt er als ik een bestand met id&#39;s verzend voor bezoekers die de id-synchronisatie op de pagina nog niet hebben uitgevoerd?**

Tijdens de verwerking slaat [!DNL Audience Manager] u gewoon die record over en gaat u naar de volgende record. Als een DPID (Data Provider ID) is ingesteld als een DPID voor alle apparaten, worden gegevens die worden ingevoerd voordat een ID-synchronisatie wordt opgeslagen, kort nadat de ID-synchronisatie is uitgevoerd, opgeslagen en beschikbaar voor gebruik.

<br> 

**Wat is het tijdstempel, waarvoor is het en kunt u een voorbeeld geven?**

Tijdstempels worden gebruikt voor loggen en vastleggen. Deze worden vereist door de syntaxis die wordt gebruikt voor een inbound-bestandsnaam met de juiste indeling. Zie:

* [Amazon S3-naamvereisten voor binnenkomende gegevensbestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**Wat is een identiteitskaart van de Leverancier van Gegevens (DPID) en hoe krijg ik het?**

Uw Adobe-consultant wijst een DPID van drie of vier cijfers toe aan uw specifieke gegevensbron. Deze id is uniek en verandert niet.

<br> 

**Hoe groot kunnen de dagelijkse gegevensbestanden zijn?**

Zie [Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md).

<br> 

**Biedt Audience Manager ondersteuning voor bestandscompressie?**

Ja, zie:

* [Bestandscompressie voor binnenkomende gegevensoverdrachtbestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-compression.md)
* [Amazon S3-naamvereisten voor binnenkomende gegevensbestanden](../integration/sending-audience-data/batch-data-transfer-explained/inbound-s3-filenames.md)


<br> 

**De primaire sleutel in mijn gegevensbrongegevensbestand is een e-mailadres. Wordt dat beschouwd als persoonlijk identificeerbare informatie?**

Ja. [!DNL Audience Manager] e-mailadressen worden niet opgeslagen in onze database. Bezoekers moeten een willekeurige id of een gehashte versie van het e-mailadres krijgen voordat ze ID-syncs starten.

<br> 

**Is de inhoud van het gegevensbestand case-sensitive? Hoe zit het met de id-synchronisatie?**

Een gegevensbestand bestaat uit twee basiscomponenten: Een gebruiker-id (zie Gebruiker - identiteitskaart in Gedefinieerde [de Variabelen van het](/help/using/integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md#file-variables-defined)Dossier) en profielgegevens, gewoonlijk in de vorm van zeer belangrijke paren of codes. De gebruikersnaam is hoofdlettergevoelig. Doorgaans zijn profiel- of sleutelwaardegegevens niet hoofdlettergevoelig.

<br> 

**Moet ik FTP gebruiken of bestanden[!DNL Amazon S3]overbrengen?**

Als beste praktijken, adviseren wij [!DNL Amazon S3] omdat het proces eenvoudiger is. [!DNL Audience Manager] Hiermee worden FTP-bestanden naar [!DNL S3] elke gewenste locatie overgebracht. Het proces wordt dus gestroomlijnd als u de bestanden op [!DNL Amazon S3] uzelf neerzet. Bovendien delen klanten die tegelijkertijd uploaden naar FTP de FTP-bandbreedte, zodat ze lagere uploadsnelheden moeten verwachten. [!DNL Amazon S3] wordt ook gerepliceerd en gedistribueerd, zodat deze doorgaans veiliger en betrouwbaarder is dan een FTP-server. Zie [Informatie over Amazon S3](../reference/amazon-s3.md)voor meer informatie.

<br> 

**Hoe verwerkt de Manager van de Publiek binnenkomende dossiers?**

[!DNL Audience Manager] gebruik [!DNL Amazon Simple Queue Service (SQS)] voor binnenkomende gegevensverwerking. Dit werkt als volgt:

1. [!DNL Audience Manager] klanten uploaden hun binnenkomende gegevens naar een [!DNL Amazon S3] emmer.

2. De gegevens gaan in de [!DNL Amazon SQS] wachtrij en wachten op verwerking door [!DNL Audience Manager].

3. [!DNL Audience Manager] leest tot 119000 ingangen van de [!DNL Amazon SQS] rij en verdeelt hen in maximaal 3 partijen. Bestanden in elke batch worden tegelijkertijd verwerkt.

<br> 

**Ik moet meerdere bestanden tegelijk uploaden. Zullen de bestanden gelijktijdig worden verwerkt?**

Het hangt ervan af. [!DNL Audience Manager] leest tot 119000 ingangen van de [!DNL Amazon SQS] rij en verdeelt hen in maximaal 3 partijen. Uw bestanden worden alleen tegelijkertijd verwerkt als ze in dezelfde batch terechtkomen. Vanwege de grote hoeveelheid gegevens die dagelijks [!DNL Audience Manager] worden ingevoerd, kunnen we echter geen enkele volgorde voor bestandsverwerking garanderen.

>[!MORELIKETHIS]
>
>* [Batchgegevensoverdrachtproces beschreven](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)

