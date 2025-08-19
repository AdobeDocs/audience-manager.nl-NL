---
description: Voordat Audience Manager Audience Optimization for Publishers kan inschakelen, moet u ervoor zorgen dat aan alle voorwaarden in dit artikel wordt voldaan. Neem contact op met de klantenservice na het uitchecken van alle voorwaarden.
seo-description: Before Audience Manager can enable Audience Optimization for Publishers, you must ensure that all prerequisites outlined in this article are met. Contact Customer Care after checking off all prerequisites.
seo-title: Import Google Ad Manager Data Files Into Audience Manager
solution: Audience Manager
title: Google Ad Manager-gegevensbestanden importeren in Audience Manager
uuid: c685f34f-3e50-4c4b-99fa-d8bbafe0b268
feature: Audience Optimization Reports
exl-id: 62b72dd1-e664-4c6a-8c0a-f7a662d62a47
source-git-commit: 7147091e6c253e8124f5f21a2251c1a76ac9d808
workflow-type: tm+mt
source-wordcount: '511'
ht-degree: 0%

---

# Google Ad Manager (voorheen DFP)-gegevensbestanden importeren in Audience Manager{#import-dfp-data-files-into-audience-manager}

Voordat Audience Manager Audience Optimization for Publishers kan inschakelen, moet u ervoor zorgen dat aan alle voorwaarden in dit artikel wordt voldaan. Neem contact op met de klantenservice na het uitchecken van alle voorwaarden.

## Vereisten voor Google Ad Manager Logbestandsinname {#prereqs-dfp-ingestion}

Merk op dat het proces dat in deze sectie wordt beschreven *moet worden voltooid alvorens* u zich op de eerste vereisten voor login enablement beweegt.

Om [!DNL Google Ad Manager] (vroeger Google DFP) logboekdossiers in [!DNL Audience Manager] te gebruiken, moet u onze [ Unieke Gebruiker van Audience Manager - identiteitskaart (UUID) ](../../../reference/ids-in-aam.md) in de vraag van de ad markering eerst plaatsen. Op deze manier wordt onze id opgenomen in de logbestanden van [!DNL Google Ad Manager] en kunnen we id&#39;s afstemmen tussen [!DNL Google Ad Manager] en [!DNL Audience Manager] . Gebruik [!DNL Audience Manager] [!UICONTROL DIL] code of [!UICONTROL Audience Management Module] om de [!DNL Audience Manager] UUID in te stellen in een cookie van de eerste partij.

Hieronder wordt beschreven hoe u de id van [!DNL Audience Manager] instelt in de aanroep van de tag ad, zoals wordt uitgelegd in onze documentatie:

* [ via de Markering van de Uitgever van Google (GPT) ](../../../integration/gpt-aam-destination/gpt-aam-modify-api.md)
* [Via een Cookie-bestemming](../../../integration/gpt-aam-destination/gpt-aam-create-destination.md)

U moet de [!DNL Audience Manager] id zelf instellen en kunt met [!DNL Audience Manager] consulting werken om te controleren of alles werkt. U hebt de id van [!DNL Audience Manager] correct ingesteld als:

* `'aamid'` is de sleutel die als herkenningsteken wordt gebruikt.
* De waarde van identiteitskaart van de Gebruiker is correct geformatteerd als [!DNL Audience Manager] UUID, zoals die in onze [ Index van IDs in Audience Manager ](../../../reference/ids-in-aam.md) wordt beschreven.
* U hebt de [!DNL Audience Manager] UUID opgenomen in een gedefinieerd veld in uw [!DNL Google Ad Manager] -logbestanden (bijvoorbeeld CustomTargeting).

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
   <td colname="col2"> <p>Bevestig dat de vereiste stappen om <span class="keyword"> Audience Manager </span> UUID (hierboven geschetst) te plaatsen zijn voltooid alvorens aan Stap 2 over te gaan </p> </td> 
   <td colname="col3"> <p><span class="keyword"> Audience Manager </span> Klantenservice of advies </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 2 </p> </td> 
   <td colname="col2"> <p>Uw Google Ad Manager-beheerder maakt: </p> <p> 
     <ol id="ol_FCFA9B11CFF948A488DF9CB298FC04C4"> 
      <li id="li_BC946EDCC3324578AEB64EDDA55B5ACA">Een serviceaccount voor het invoeren van Google Ad Manager-logbestanden in <span class="keyword"> Audience Manager </span> . </li> 
      <li id="li_6B2FC7D73A3246419E55C004E17ACA25">Nieuwe referenties. <p>Opmerking: hiervoor is mogelijk een uniek e-mailadres nodig dat specifiek is voor dit project en dat wordt gebruikt bij de levering van toegang tot het Google Storage Bucket. </p> </li> 
      <li id="li_95444B9FD1B34659A9634814B262A681">Een persoonlijke sleutel (op JSON gebaseerde referentie) </li> 
     </ol> </p> </td> 
   <td colname="col3"> <p>Uw Google Ad Manager-beheerder </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p>Stap 3 </p> </td> 
   <td colname="col2"> <p>Uw Google Ad Manager-beheerder verleent API-toegang tot het serviceaccount. Met deze stap kunt u de afmetingen van de metagegevens (regelitems, bestellingen, creatieven) afbakenen. <p>Opmerking: gebruik de e-mailtoegang tot de serviceaccount die u in stap 2 hebt ingesteld om toegang tot de API te verlenen. </p> </p> </td> 
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
   <td colname="col2"> <p>Compileer de eerste vereisten en open een steunkaartje door de instructies te volgen die <a href="https://experienceleague.adobe.com/docs/customer-one/using/home.html?lang=nl-NL"> hier </a> worden gedetailleerd om van het proces van logboekopname af te schoppen. </p> </td> 
   <td colname="col3"> <p>U, of <span class="keyword"> Audience Manager </span> Consulting namens u </p> </td> 
  </tr> 
 </tbody> 
</table>
