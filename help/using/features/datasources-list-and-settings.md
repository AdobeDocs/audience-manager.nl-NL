---
description: Bekijk een lijst van uw momenteel gevormde gegevensbronnen, voeg nieuwe gegevensbronnen toe, en geef bestaande bronnen uit.
seo-description: Bekijk een lijst van uw momenteel gevormde gegevensbronnen, voeg nieuwe gegevensbronnen toe, en geef bestaande bronnen uit.
seo-title: Lijst met databronnen en -instellingen
solution: Audience Manager
title: Lijst met databronnen en -instellingen
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1118'
ht-degree: 1%

---


# [!UICONTROL Data Sources] Lijst en instellingen  {#data-sources-list-and-settings}

Bekijk een lijst van uw momenteel gevormde [!UICONTROL data sources], voeg nieuw [!UICONTROL data sources] toe, en geef bestaand [!UICONTROL data sources] uit.

U kunt [!UICONTROL data sources] ook beheren gebruikend [!DNL API] methodes. Zie [API-methoden voor gegevensbron](../api/rest-api-main/aam-api-data-sources.md) voor meer informatie.

## [!UICONTROL Data Sources] Lijstweergave  {#list-view}

Het [!UICONTROL Data Sources] dashboard is een gecentraliseerde werkruimte voor het beheer van gegevensbronnen.

Het [!UICONTROL Data Sources] dashboard (**[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**) bevat functies en gereedschappen die u helpen:

* Zie al uw bestaande [!UICONTROL data sources], met inbegrip van de beschrijving van elke gegevensbron, status, en of het [!UICONTROL Inbound], [!UICONTROL Outbound], allebei, of [!UICONTROL Shared Provider] is.
* [!UICONTROL data sources] op naam zoeken.
* [!UICONTROL data sources] maken, bewerken en verwijderen.

## [!DNL Data Source] Instellingen en menuopties  {#settings-menu-options}

De montages in de verschillende secties van [!UICONTROL Data Source] beheersinterface identificeren uw [!DNL data source], bepalen hoe het wordt gebruikt of gedeeld, en laten u foutenrapportering voor [!UICONTROL Onboarding Status Report] toelaten.

## [!DNL Data Source] Details  {#details}

Naast tekstvelden bevat de sectie [!UICONTROL Data Source Details] de onderstaande besturingselementen en opties.

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
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Koekje</span></b>: De cookie-id die een apparaat identificeert. U selecteert deze optie wanneer uw gegevensbron een webbrowser is of wanneer u werkt met anonieme gegevens of gegevens die niet aan één persoon kunnen worden gekoppeld. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Advertising-id</span></b> van apparaat: De id van het mobiele apparaat. Selecteer deze optie als uw gegevensbron een mobiel apparaat of een apparaat met internetverbinding is. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Kruisapparaat</span></b>: Een door de klant opgegeven, geverifieerde id. Selecteer deze optie als u het volgende wilt maken: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Een gegevensbron voor meerdere apparaten en bouw een <span class="wintitle"> Regel van de Fusie van het Profiel</span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Een gegevensbron die koppelingen gebruikt die worden geleverd door de <a href="https://docs.adobe.com/content/help/en/device-co-op/using/about/overview.html" format="https" scope="external"> Adobe Experience Cloud Device Co-op</a> of een andere apparaatgrafiek van derden die is geïntegreerd met <span class="keyword"> Audience Manager</span>. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-definitie</span></b> </p> </td> 
   <td colname="col2"> <p>Met de opties <b><span class="uicontrol"> ID Definition</span></b> wordt de relatie gedefinieerd die een gegevensbron heeft met een <span class="keyword"> Audience Manager</span> gebruikers-id (UUID) en de bijbehorende apparaten die zijn gekoppeld door de <span class="keyword"> Adobe Experience Cloud Device Co-op</span> of een andere apparaatgrafiek van derden die is geïntegreerd met <span class="keyword"> Audience Manager</span>. De volgende opties zijn beschikbaar: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persoon:</span></b> De id die wordt gebruikt om één persoon te definiëren. Deze id kan aan veelvoudige <span class="keyword"> Audience Manager</span> IDs worden in kaart gebracht. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Huishouden:</span></b> de id die wordt gebruikt om een groep personen te definiëren. Deze id kan worden toegewezen aan meerdere Audience Manager-id's. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[De Controles van de Uitvoer van gegevens ](../features/data-export-controls.md) zijn facultatieve classificatieregels u op een  [!UICONTROL data source] en  [!UICONTROL destination]. Ze verhinderen dat u gegevens naar een [!UICONTROL destination] verzendt wanneer die handeling een inbreuk vormt op een privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u [!UICONTROL Data Export Controls] niet gebruikt.

>[!IMPORTANT]
>
>Exportbeperkingen werken alleen als u een overeenkomend exportlabel instelt op een [!UICONTROL destination].

De volgende opties zijn beschikbaar:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Instellingen  {#data-source-settings}

De [!UICONTROL Data Source Settings] bevat de hieronder vermelde besturingselementen en opties. Sommige van deze instellingen hebben extra subopties en menu-items die u kunt selecteren om een gegevensbron te wijzigen.

### [!UICONTROL Inbound Data Source] Instellingen

Schakel het selectievakje **[!UICONTROL Inbound]** in als uw gegevensbron is ontworpen voor het ontvangen van binnenkomende gegevens. Als u het selectievakje **[!UICONTROL Inbound]** selecteert, worden nog twee extra groepen besturingselementen weergegeven die hieronder worden beschreven.

>[!NOTE]
>
>Het selectievakje **[!UICONTROL Inbound]** is alleen bedoeld om de hieronder beschreven besturingselementen [!UICONTROL data source] weer te geven of te verbergen. Het uitschakelen van de optie **[!UICONTROL Inbound]** heeft op geen enkele manier invloed op de gegevensinvoer. Uw geregistreerde gegevens worden verwerkt, ongeacht of deze optie is ingeschakeld.

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
   <td colname="col2"> <p>Voor de optie <b><span class="uicontrol"> Inbound</span></b> is een id-type vereist. De volgende opties zijn beschikbaar: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Klant-id</span></b>: Identificeert binnenkomende gegevens met een klant identiteitskaart </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-id</span></b>: Identificeert binnenkomende gegevens met een  <span class="keyword"> Publiek </span> ManagerID. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud-id</span></b>: Identificeert binnenkomende gegevens met een  <span class="keyword"> Experience </span> CloudID. Zie <a href="https://docs.adobe.com/content/help/nl-NL/id-service/using/intro/cookies.html" format="https" scope="external"> Koekjes en Experience Cloud ID</a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Problemen met bestandsindeling oplossen</span></b> </p> </td> 
   <td colname="col2"> <p>Selecteer <b><span class="uicontrol"> Enable file error sampling</span></b> wanneer u problemen met binnenkomende dossierverwerking moet oplossen. Deze functie genereert een foutvoorbeeldrapport waarin u bestandsindelingen en syntaxisfouten kunt zien. </p> <p>Zie <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Rapport over status aan boord: Info</a> voor informatie over fout het melden en fout bemonstering. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Overige instellingen [!UICONTROL Data Source]

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
   <td colname="col2"> <p>De gegevensbron voor meerdere apparaten bevat een geverifieerde id. Een geverifieerde id wordt verzameld en gesynchroniseerd met een <span class="keyword">-Audience Manager</span>-id tijdens een verificatiegebeurtenis (een gebruiker kan zich bijvoorbeeld on-site, in-app enz. aanmelden). De geverifieerde id kan worden gebruikt voor gegevens aan boord van andere bronnen die deze id opslaan. Het kan ook worden gebruikt om veelvoudige apparaat IDs in <span class="wintitle"> de Verbinding van het Profiel </span> te verbinden. </p> <p>Met deze optie wordt een tekstveld weergegeven waarin u de naam van de gegevensbron kunt wijzigen in een alias. Als u een alias gebruikt, treedt deze nieuwe naam de gegevensbronnaam met voeten en verschijnt in <span class="wintitle"> Voor authentiek verklaarde Opties van het Profiel </span> wanneer u <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> een regel van de Fusie van het Profiel </a> creeert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gebruiken als apparaatgrafiek</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee maakt u een gegevensbron als een apparaatgrafiek die u aan andere <span class="keyword"> Audience Managers</span>-klanten kunt geven. Voordat u deze optie selecteert, moet u met uw <span class="keyword"> Audience Manager</span> consultant aangeven met welke klanten deze <span class="wintitle"> Gegevensbron</span> moet worden gedeeld. Uw consultant zal deze bedrijven moeten voorzien via onze interne processen. </p> <p>Met deze optie wordt een tekstveld weergegeven waarin u de naam van de gegevensbron kunt wijzigen in een alias. Als u een alias gebruikt, treedt deze nieuwe naam de gegevensbronnaam met voeten en verschijnt in <span class="wintitle"> de Opties van het Apparaat </span> wanneer u <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> tot een regel van de Fusie van het Profiel</a> leidt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gekoppelde gebruikers- of apparaatid's delen met specifieke klanten van Audience Managers</span></b> </p> </td> 
   <td colname="col2"> <p>De gegevensbron voor meerdere apparaten bevat id's uit een apparaatgrafiek. Een apparatengrafiek is een inzameling van IDs die aan één of meerdere <span class="keyword"> Audience Manager</span> IDs aan een cluster in kaart brengen. Deze cluster vertegenwoordigt doorgaans een persoon of een grotere groep huishoudens. Alleen beschikbaar voor accounts die zijn vermeld als 'Data Provider'. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gekoppelde bezoeker of apparaat-id's delen over het Platform Audience Manager</span></b> </p> </td> 
   <td colname="col2"> <p>Uw gegevensbron bevat bezoeker of apparaat-id's die kunnen worden gedeeld door andere <span class="keyword"> Experience Cloud</span>-oplossingen. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bewaren van gegevens voor niet-actieve Customer ID's</span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee kunt u de periode voor het bewaren van gegevens instellen voor inactieve id's van klanten. Dit bepaalt hoe lang de Audience Manager identiteitskaart van de Klant in ons gegevensbestand houdt nadat zij het laatst op het platform van de Audience Manager werden gezien.</p> <p>De standaardwaarde is 24 maanden (720 dagen). De minimumwaarde die u kunt instellen is 1 maand en de maximumwaarde is 5 jaar. We tellen alle maanden als 30 dagen.</p> <p>Audience Manager voert een proces uit dat inactieve identiteitskaart van de Klant één keer per week schrapt, overeenkomstig het gegevensbehoud u voor inactieve identiteitskaart van de Klant plaatst.</p> <p>Audience Manager voert een proces uit dat inactieve identiteitskaart van de Klant één keer per week schrapt, overeenkomstig het gegevensbehoud u voor inactieve identiteitskaart van de Klant plaatst.</p> <p><b>Opmerking</b>: Dit besturingselement is alleen beschikbaar voor apparaatgegevensbronnen. Zie ook <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Een gegevensbron voor meerdere apparaten maken </a>.</p></td> 
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
