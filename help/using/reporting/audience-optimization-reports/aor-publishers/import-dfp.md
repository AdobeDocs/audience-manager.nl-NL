---
description: Voordat Audience Manager de optimalisatie van het publiek voor uitgevers kan inschakelen, moet u ervoor zorgen dat aan alle voorwaarden die in dit artikel worden beschreven, wordt voldaan. Neem contact op met de klantenservice nadat u alle voorwaarden hebt gecontroleerd.
seo-description: Voordat Audience Manager de optimalisatie van het publiek voor uitgevers kan inschakelen, moet u ervoor zorgen dat aan alle voorwaarden die in dit artikel worden beschreven, wordt voldaan. Neem contact op met de klantenservice nadat u alle voorwaarden hebt gecontroleerd.
seo-title: DFP-gegevensbestanden importeren in Auditions Manager
solution: Audience Manager
title: DFP-gegevensbestanden importeren in Auditions Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
translation-type: tm+mt
source-git-commit: 9f091fa765e937fb47b3328d8f5f2dab24a85040

---


# DFP-gegevensbestanden importeren in Auditions Manager{#import-dfp-data-files-into-audience-manager}

Voordat Audience Manager de optimalisatie van het publiek voor uitgevers kan inschakelen, moet u ervoor zorgen dat aan alle voorwaarden die in dit artikel worden beschreven, wordt voldaan. Neem contact op met de klantenservice nadat u alle voorwaarden hebt gecontroleerd.

## Vereisten voor DFP Log Ingestie {#prereqs-dfp-ingestion}

Merk op dat het proces in deze sectie wordt beschreven moet worden voltooid *alvorens* u zich op de eerste vereisten voor login enablement beweegt.

Als u DFP ( [!DNL DoubleClick For Publishers]) logbestanden in wilt gebruiken, moet u eerst onze unieke gebruikersnaam (UUID) [!DNL Audience Manager]voor [](../../../reference/ids-in-aam.md) Audience Manager instellen in het aanroepen van de tag ad. Hierdoor is onze id opgenomen in de DFP-logboeken en kunnen we id&#39;s afstemmen tussen DFP en [!DNL Audience Manager]. Gebruik [!DNL Audience Manager] de [!UICONTROL DIL] code of [!UICONTROL Audience Management Module] om de [!DNL Audience Manager] UUID in te stellen in een cookie van de eerste partij.

Hieronder wordt beschreven hoe u de [!DNL Audience Manager] id instelt in de aanroep van de tag ad, zoals wordt uitgelegd in de documentatie:

* [Via Google Publisher-tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Via een Cookie-bestemming](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

U moet de [!DNL Audience Manager] id zelf instellen en u kunt met [!DNL Audience Manager] advies werken om te controleren of alles werkt. U hebt de juiste [!DNL Audience Manager] id ingesteld als:

* `'aamid'` is de sleutel die als herkenningsteken wordt gebruikt.
* De waarde van de gebruikersnaam is correct opgemaakt als de [!DNL Audience Manager] UUID, zoals wordt beschreven in onze [index van id&#39;s in Audience Manager](../../../reference/ids-in-aam.md).
* U hebt de [!DNL Audience Manager] UUID opgenomen in een gedefinieerd veld in uw DFP-logbestanden (bijvoorbeeld CustomTargeting).

## Vereisten voor Ingestiemachtiging voor logbestanden {#prereqs-ingestion-enablement}

<table id="table_C980A9F9B0FB4157B4908A64768B1571"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Stap </th> 
   <th colname="col2" class="entry"> Details </th> 
   <th colname="col3" class="entry"> Eigenaar </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Stap 1 </p> </td> 
   <td colname="col2"> <p>Bevestig dat de vereiste stappen voor het instellen van de UUID voor <span class="keyword"> Audience Manager</span> (zie hierboven) zijn voltooid voordat u naar stap 2 gaat </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> Customer Care of Consulting </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 2 </p> </td> 
   <td colname="col2"> <p>Uw DFP-beheerder maakt: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Een serviceaccount voor het opnemen van DFP-logs in <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nieuwe referenties. <p>Opmerking:  Hiervoor is mogelijk een uniek e-mailadres nodig dat specifiek is voor dit project en dat wordt gebruikt bij het verlenen van toegang tot het Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Een persoonlijke sleutel (op JSON gebaseerde referentie) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Uw DFP-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 3 </p> </td> 
   <td colname="col2"> <p>Uw DFP-beheerder verleent API-toegang tot het serviceaccount. Met deze stap kunt u de afmetingen van de metagegevens (regelitems, bestellingen, creatieven) afbakenen. <p>Opmerking:  Gebruik de e-mailtoegang van de de dienstrekening die u opstelling in stap 2 om toestemming te verlenen om tot API toegang te hebben. </p> </p> </td> 
   <td colname="col3"> <p>Uw DFP-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 4 </p> </td> 
   <td colname="col2"> <p>Uw DFP-beheerder stelt toegang tot het Google Storage Bucket in. Onthoud: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Dit kan via een Google-groep worden gedaan. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Koppel het unieke e-mailadres dat aan de serviceaccount is toegewezen aan het opslagemmertje. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Uw DFP-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 5 </p> </td> 
   <td colname="col2"> <p>Uw DFP-beheerder biedt de DFP-netwerk-id. Dit staat ons toe om in identiteitskaart van het Netwerk over te gaan wanneer het maken van vraag aan API. </p> </td> 
   <td colname="col3"> <p>Uw DFP-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 6 </p> </td> 
   <td colname="col2"> <p>Compileer de voorwaarden in een e-mail naar de klantenservice van AAM (aamsupport@adobe.com) om het inlogproces af te breken. Ontwerp de e-mail gebruikend het malplaatje in de volgende sectie. </p> </td> 
   <td colname="col3"> <p>U, of de Manager <span class="keyword"></span> van het publiek die namens u raadpleegt </p> </td> 
  </tr> 
 </tbody> 
</table>

## E-mailsjabloon {#email-template}

Als u de logingestion-functie wilt voltooien, stuurt u ons een e-mail naar aamsupport@adobe.com. Gebruik de [bijgevoegde e-mailsjabloon](assets/enable_dfp_ingestion.txt).
