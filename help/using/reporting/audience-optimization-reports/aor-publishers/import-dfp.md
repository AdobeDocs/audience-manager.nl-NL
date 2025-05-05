---
description: Voordat Audience Manager Audience Optimization voor uitgevers kan inschakelen, moet u ervoor zorgen dat aan alle voorwaarden die in dit artikel worden beschreven, wordt voldaan. Neem contact op met de klantenservice nadat u alle voorwaarden hebt gecontroleerd.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Google Ad Manager-gegevensbestanden importeren in Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '508'
ht-degree: 0%

---

# Google Ad Manager (voorheen DFP)-gegevensbestanden importeren in Audience Manager{#import-dfp-data-files-into-audience-manager}

Voordat Audience Manager Audience Optimization voor uitgevers kan inschakelen, moet u ervoor zorgen dat aan alle voorwaarden die in dit artikel worden beschreven, wordt voldaan. Neem contact op met de klantenservice nadat u alle voorwaarden hebt gecontroleerd.

## Vereisten voor Google Ad Manager Logbestandsinname {#prereqs-dfp-ingestion}

Het in deze sectie beschreven proces moet worden voltooid. *voor* u zich op de eerste vereisten voor logboekopname enablement beweegt.

Voor gebruik [!DNL Google Ad Manager] (voorheen Google DFP) logbestanden in [!DNL Audience Manager], moet u eerst onze [Unieke gebruikersnaam van Audience Manager (UUID)](../../../reference/ids-in-aam.md) in de aanroep van de tag ad. Op deze manier wordt onze id opgenomen in de [!DNL Google Ad Manager] logbestanden en we kunnen id&#39;s afstemmen tussen [!DNL Google Ad Manager] en [!DNL Audience Manager]. Gebruiken [!DNL Audience Manager] [!UICONTROL DIL] code of de [!UICONTROL Audience Management Module] om de [!DNL Audience Manager] UUID in een cookie van de eerste partij.

Hieronder wordt beschreven hoe u de [!DNL Audience Manager] Id in de aanroep van de advertentietag, zoals wordt uitgelegd in onze documentatie:

* [Via Google Publisher-tag (GPT)](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Via een Cookie-bestemming](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

U moet de [!DNL Audience Manager] Id zelf, en kan werken met [!DNL Audience Manager] raadplegen om te controleren of alles werkt. U hebt de opdracht [!DNL Audience Manager] ID correct als:

* `'aamid'` is de sleutel die als herkenningsteken wordt gebruikt.
* De waarde van de gebruikersnaam is correct opgemaakt als de [!DNL Audience Manager] UUID, zoals beschreven in onze [Index van id&#39;s in Audience Manager](../../../reference/ids-in-aam.md).
* U hebt de [!DNL Audience Manager] UUID in een gedefinieerd veld in uw [!DNL Google Ad Manager] logbestanden (bijvoorbeeld CustomTargeting).

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
   <td colname="col2"> <p>Bevestig dat de vereiste stappen om de <span class="keyword"> Audience Manager</span> UUID (hierboven beschreven) is voltooid voordat u naar stap 2 gaat </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager</span> Klantenservice of advies </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 2 </p> </td> 
   <td colname="col2"> <p>Uw Google Ad Manager-beheerder maakt: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Een serviceaccount voor het opnemen van Google Ad Manager-aanmeldingen bij <span class="keyword"> Audience Manager</span>. </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nieuwe referenties. <p>Opmerking: Dit kan een uniek e-mailadres vereisen specifiek voor dit project en zal worden gebruikt wanneer levering toegang tot het Emmertje van de Opslag van Google. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Een persoonlijke sleutel (op JSON gebaseerde referentie) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Uw Google Ad Manager-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 3 </p> </td> 
   <td colname="col2"> <p>Uw Google Ad Manager-beheerder verleent API-toegang tot het serviceaccount. Met deze stap kunt u de afmetingen van de metagegevens (regelitems, bestellingen, creatieven) afbakenen. <p>Opmerking: Gebruik de e-mailtoegang van de de dienstrekening die u opstelling in stap 2 om toestemming te verlenen om tot API toegang te hebben. </p> </p> </td> 
   <td colname="col3"> <p>Uw Google Ad Manager-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 4 </p> </td> 
   <td colname="col2"> <p>Uw Google Ad Manager-beheerder stelt toegang tot het Google Storage Bucket in. Onthoud: </p> <p> 
     <ul id="ul_3E8DCC73454243D998BD9024D0966A4E"> 
      <li id="li_3691DBD28006412288458175F75873C6">Dit kan via een Google-groep worden gedaan. </li> 
      <li id="li_4774806B263245CEAAAB89BD2AA7F23F">Koppel het unieke e-mailadres dat aan de serviceaccount is toegewezen aan het opslagemmertje. </li> 
     </ul> </p> </td> 
   <td colname="col3"> <p>Uw Google Ad Manager-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 5 </p> </td> 
   <td colname="col2"> <p>Uw Google Ad Manager-beheerder geeft de Google Ad Manager Network ID. Dit staat ons toe om in identiteitskaart van het Netwerk over te gaan wanneer het maken van vraag aan API. </p> </td> 
   <td colname="col3"> <p>Uw Google Ad Manager-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 6 </p> </td> 
   <td colname="col2"> <p>Compileer de eerste vereisten en open een steunkaartje door de gedetailleerde instructies te volgen <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html?lang=nl-NL">hier</a> om het inlogproces af te remmen. </p> </td> 
   <td colname="col3"> <p>U, of <span class="keyword"> Audience Manager</span> Namens u raadplegen </p> </td> 
  </tr> 
 </tbody> 
</table>
