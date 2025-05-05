---
description: Bekijk een lijst van uw momenteel gevormde gegevensbronnen, voeg nieuwe gegevensbronnen toe, en geef bestaande bronnen uit.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Lijst met databronnen en -instellingen
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1071'
ht-degree: 0%

---

# [!UICONTROL Data Sources] Lijst en instellingen {#data-sources-list-and-settings}

Een lijst weergeven met de momenteel geconfigureerde [!UICONTROL data sources], nieuwe toevoegen [!UICONTROL data sources]en bestaande [!UICONTROL data sources].

U kunt ook [!UICONTROL data sources] gebruiken [!DNL API] methoden. Zie voor meer informatie [API-methoden gegevensbron](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Lijstweergave {#list-view}

De [!UICONTROL Data Sources] dashboard is een gecentraliseerde werkruimte voor het beheer van gegevensbronnen.

De [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) bevat functies en gereedschappen die u helpen:

* Alle bestaande bekijken [!UICONTROL data sources], met inbegrip van de beschrijving van elke gegevensbron, de status en of deze [!UICONTROL Inbound], [!UICONTROL Outbound], zowel [!UICONTROL Shared Provider].
* Zoeken naar [!UICONTROL data sources] op naam.
* Maken, bewerken en verwijderen [!UICONTROL data sources].

## [!DNL Data Source] Instellingen en menuopties {#settings-menu-options}

De instellingen in de verschillende secties van het dialoogvenster [!UICONTROL Data Source] beheerinterface uw [!DNL data source], bepaalt u hoe het wordt gebruikt of gedeeld, en laat u foutenrapportering voor toelaten [!UICONTROL Onboarding Status Report].

## [!DNL Data Source] Details {#details}

Naast tekstvelden worden [!UICONTROL Data Source Details] bevat de onderstaande besturingselementen en opties.

<table id="table_BF73919473D74444B38939A36C2F7CDA"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Instelling </th> 
   <th colname="col2" class="entry"> Menuopties </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Type id</span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Cookie</span></b>: De cookie-id die een apparaat identificeert. U selecteert deze optie wanneer uw gegevensbron een webbrowser is of wanneer u werkt met anonieme gegevens of gegevens die niet aan één persoon kunnen worden gekoppeld. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Apparaatadvertentie-id</span></b>: De id van het mobiele apparaat. Selecteer deze optie als uw gegevensbron een mobiel apparaat of een apparaat met internetverbinding is. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Cross-device</span></b>: Een door de klant opgegeven, geverifieerde id. Selecteer deze optie als u het volgende wilt maken: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Een apparaatgegevensbron en een <span class="wintitle"> Regel voor samenvoegen van profiel</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Een gegevensbron die koppelingen gebruikt die worden geleverd door een apparaatgrafiek van een andere fabrikant die is geïntegreerd met <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-definitie</span></b> </p> </td> 
   <td colname="col2"> <p>De <b><span class="uicontrol"> ID-definitie</span></b> opties definiëren de relatie die een gegevensbron heeft met een <span class="keyword"> Audience Manager</span> gebruikers-id (UUID) en bijbehorende apparaten die zijn gekoppeld door een apparaatgrafiek van een andere fabrikant die is geïntegreerd met <span class="keyword"> Audience Manager</span>. De volgende opties zijn beschikbaar: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persoon:</span></b> De id die wordt gebruikt om één persoon te definiëren. Deze id kan worden toegewezen aan meerdere <span class="keyword"> Audience Manager</span> ID's. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Huishoudelijk:</span></b> De id die wordt gebruikt om een groep personen te definiëren. Deze id kan worden toegewezen aan meerdere Audience Manager-id's. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[Besturingselementen voor gegevensexport](../features/data-export-controls.md) zijn optionele classificatieregels die u kunt toepassen op een [!UICONTROL data source] en [!UICONTROL destination]. Ze verhinderen dat u gegevens naar een [!UICONTROL destination] wanneer die handeling een inbreuk vormt op een privacyovereenkomst of een gebruiksovereenkomst voor gegevens. Deze sectie overslaan als u deze niet gebruikt [!UICONTROL Data Export Controls].

>[!IMPORTANT]
>
>Exportbeperkingen werken alleen als u een overeenkomend exportlabel instelt op een [!UICONTROL destination].

De volgende opties zijn beschikbaar:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Instellingen {#data-source-settings}

De [!UICONTROL Data Source Settings] bevat de hieronder vermelde besturingselementen en opties. Sommige van deze instellingen hebben extra subopties en menu-items die u kunt selecteren om een gegevensbron te wijzigen.

### [!UICONTROL Inbound Data Source] Instellingen

Selecteer **[!UICONTROL Inbound]** Schakel het selectievakje in wanneer uw gegevensbron is ontworpen voor het ontvangen van binnenkomende gegevens. Het selecteren van **[!UICONTROL Inbound]** het controlevakje stelt 2 extra hieronder beschreven groepen controles bloot.

>[!NOTE]
>
>De **[!UICONTROL Inbound]** selectievakje is alleen bedoeld voor het weergeven of verbergen van [!UICONTROL data source] de hieronder beschreven besturingselementen. De optie Ongedaan maken **[!UICONTROL Inbound]** Deze optie heeft op geen enkele wijze invloed op de gegevensinvoer. Uw geregistreerde gegevens worden verwerkt, ongeacht of deze optie is ingeschakeld.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Instelling </th> 
   <th colname="col2" class="entry"> Menuopties </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Type id</span></b> </p> </td> 
   <td colname="col2"> <p>De <b><span class="uicontrol"> Binnenkomend</span></b> vereist een id-type. De volgende opties zijn beschikbaar: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Klant-id</span></b>: Identificeert binnenkomende gegevens met een klant identiteitskaart </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-id</span></b>: Identificeert binnenkomende gegevens met een <span class="keyword"> Audience Manager</span> ID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud-id</span></b>: Identificeert binnenkomende gegevens met een <span class="keyword"> Experience Cloud</span> ID. Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=nl-NL" format="https" scope="external"> Cookies en de Experience Cloud-id</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Problemen met bestandsindeling oplossen</span></b> </p> </td> 
   <td colname="col2"> <p>Selecteren <b><span class="uicontrol"> Sampling van bestandsfouten inschakelen</span></b> wanneer u problemen met binnenkomende dossierverwerking moet oplossen. Deze functie genereert een foutvoorbeeldrapport waarin u bestandsindelingen en syntaxisfouten kunt zien. </p> <p>Zie <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapport over status aan boord: Info</a> voor meer informatie over foutmeldingen en foutrapportage. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Overige [!UICONTROL Data Source] Instellingen

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Instelling </th> 
   <th colname="col2" class="entry"> Selecteren als </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Uitgaand</span></b> </p> </td> 
   <td colname="col2"> <p>Uw gegevensbron verzendt gegevens naar een bestemming. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Delen ingeschakeld</span></b> </p> </td> 
   <td colname="col2"> <p>Uw gegevensbron kan met andere partners worden gedeeld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als geverifieerd profiel gebruiken</span></b> </p> </td> 
   <td colname="col2"> <p>De gegevensbron voor meerdere apparaten bevat een geverifieerde id. Een geverifieerde id wordt verzameld en gesynchroniseerd met een <span class="keyword"> Audience Manager</span> ID tijdens een verificatiegebeurtenis (een gebruiker kan zich bijvoorbeeld on-site, in-app enz. aanmelden). De geverifieerde id kan worden gebruikt voor gegevens aan boord van andere bronnen die deze id opslaan. Het kan ook worden gebruikt om meerdere apparaat-id's te koppelen in <span class="wintitle"> Profielkoppeling</span>. </p> <p>Met deze optie wordt een tekstveld weergegeven waarin u de naam van de gegevensbron kunt wijzigen in een alias. Als u een alias gebruikt, overschrijft deze nieuwe naam de naam van de gegevensbron en wordt deze weergegeven in het dialoogvenster <span class="wintitle"> Opties voor geverifieerd profiel</span> wanneer u <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> Een regel voor het samenvoegen van profielen maken</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gebruiken als apparaatgrafiek</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee maakt u een gegevensbron als een apparaatgrafiek die u aan andere gebruikers kunt geven <span class="keyword"> Audience Manager</span> klanten. Voordat u deze optie selecteert, moet u eerst contact opnemen met uw <span class="keyword"> Audience Manager</span> consultant welke klanten dit <span class="wintitle"> Gegevensbron</span> moeten worden gedeeld met. Uw consultant zal deze bedrijven moeten voorzien via onze interne processen. </p> <p>Met deze optie wordt een tekstveld weergegeven waarin u de naam van de gegevensbron kunt wijzigen in een alias. Als u een alias gebruikt, overschrijft deze nieuwe naam de naam van de gegevensbron en wordt deze weergegeven in het dialoogvenster <span class="wintitle"> Apparaatopties</span> wanneer u <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> Een regel voor het samenvoegen van profielen maken</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gekoppelde gebruikers- of apparaatid's delen met specifieke klanten van Audience Managers</span></b> </p> </td> 
   <td colname="col2"> <p>De gegevensbron voor meerdere apparaten bevat id's uit een apparaatgrafiek. Een apparaatgrafiek is een verzameling id's die zijn toegewezen aan een of meer <span class="keyword"> Audience Manager</span> Id's naar een cluster. Deze cluster vertegenwoordigt doorgaans een persoon of een grotere groep huishoudens. Alleen beschikbaar voor accounts die zijn vermeld als 'Data Provider'. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gekoppelde bezoeker of apparaat-id's delen over het Platform Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Uw gegevensbron bevat bezoekers of apparaat-id's die kunnen worden gedeeld door andere <span class="keyword"> Experience Cloud</span> oplossingen. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bewaren van gegevens voor niet-actieve Customer ID's</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee kunt u de periode voor het bewaren van gegevens instellen voor inactieve id's van klanten. Dit bepaalt hoe lang de Audience Manager identiteitskaart van de Klant in ons gegevensbestand houdt nadat zij het laatst op het platform van de Audience Manager werden gezien.</p> <p>De standaardwaarde is 24 maanden (720 dagen). De minimumwaarde die u kunt instellen is 1 maand en de maximumwaarde is 5 jaar. We tellen alle maanden als 30 dagen.</p> <p>Audience Manager voert een proces uit dat inactieve identiteitskaart van de Klant één keer per week schrapt, overeenkomstig het gegevensbehoud u voor inactieve identiteitskaart van de Klant plaatst.</p> <p>Audience Manager voert een proces uit dat inactieve identiteitskaart van de Klant één keer per week schrapt, overeenkomstig het gegevensbehoud u voor inactieve identiteitskaart van de Klant plaatst.</p> <p><b>Opmerking</b>: Dit besturingselement is alleen beschikbaar voor apparaatgegevensbronnen. Zie ook: <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Een apparaatgegevensbron maken </a>.</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unieke codes voor integratie van sporen</span></b> </p> </td> 
   <td colname="col2"> <p>U wilt afdwingen dat twee eigenschappen van de zelfde gegevensbron niet de zelfde integratiecode hebben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unieke segmentintegratiecodes</span></b> </p> </td> 
   <td colname="col2"> <p>U wilt afdwingen dat twee segmenten van de zelfde gegevensbron niet de zelfde integratiecode hebben. </p> </td> 
  </tr>
 </tbody>
</table>
