---
description: Bekijk een lijst van uw momenteel gevormde gegevensbronnen, voeg nieuwe gegevensbronnen toe, en geef bestaande bronnen uit.
seo-description: View a list of your currently configured data sources, add new data sources, and edit existing sources.
seo-title: Data Sources List and Settings
solution: Audience Manager
title: Lijst met gegevensbronnen en instellingen
uuid: 280a6acd-fef0-4737-a96d-9e22fbc8bfaf
feature: Data Sources
exl-id: c561d51e-e1dc-413e-bf24-13f04f10abe6
source-git-commit: 2b7858ba9000f0e0a1310bf40cd33ce3b0b01de6
workflow-type: tm+mt
source-wordcount: '1070'
ht-degree: 0%

---

# [!UICONTROL Data Sources] Lijst en instellingen {#data-sources-list-and-settings}

Een lijst weergeven met de momenteel geconfigureerde bestanden [!UICONTROL data sources] , nieuwe [!UICONTROL data sources] toevoegen en bestaande [!UICONTROL data sources] bewerken.

U kunt [!UICONTROL data sources] ook beheren met [!DNL API] -methoden. Voor meer informatie, zie [ Gegevens Source API Methoden ](../api/rest-api-main/aam-api-data-sources.md).

## [!UICONTROL Data Sources] Lijstweergave {#list-view}

Het dashboard van [!UICONTROL Data Sources] is een gecentraliseerde werkruimte voor het beheer van gegevensbronnen.

Het [!UICONTROL Data Sources] dashboard ( **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** ) bevat functies en gereedschappen die u helpen:

* Bekijk al uw bestaande [!UICONTROL data sources] , inclusief de beschrijving, status van elke gegevensbron en of dit [!UICONTROL Inbound] , [!UICONTROL Outbound] , beide of een [!UICONTROL Shared Provider] is.
* Zoeken naar [!UICONTROL data sources] op naam.
* Maken, bewerken en verwijderen [!UICONTROL data sources] .

## [!DNL Data Source] Instellingen en menuopties {#settings-menu-options}

De instellingen in de verschillende secties van de beheerinterface van [!UICONTROL Data Source] identificeren uw [!DNL data source] , bepalen hoe het wordt gebruikt of gedeeld en laten u foutmeldingen voor de [!UICONTROL Onboarding Status Report] inschakelen.

## [!DNL Data Source] Details {#details}

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
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-type </span></b> </p> </td> 
   <td colname="col2"> <p> 
     <ul id="ul_8ADCD4C5CBE543BEAA8FFE0462B74198"> 
      <li id="li_1FC97E2B3E2A4289AFB4A3C2F8E84FEF"> <b><span class="uicontrol"> Koekje </span></b>: De koekjesidentiteitskaart die een apparaat identificeert. U selecteert deze optie wanneer uw gegevensbron een webbrowser is of wanneer u werkt met anonieme gegevens of gegevens die niet aan één persoon kunnen worden gekoppeld. </li> 
      <li id="li_4B2C9A7F2A5D49448E6D0A2B354D7EE7"> <b><span class="uicontrol"> Advertising-id van apparaat </span></b> : De id van het mobiele apparaat. Selecteer deze optie als uw gegevensbron een mobiel apparaat of een apparaat met internetverbinding is. </li> 
      <li id="li_063F1B263B3B4D69B8880F7ACCB82450"> <b><span class="uicontrol"> Cross-device </span></b> : Een door de klant opgegeven, geverifieerde id. Selecteer deze optie als u het volgende wilt maken: 
       <ul id="ul_D998B4081AD843C2B3B3E642DD011C1F"> 
        <li id="li_C9D2AF70603043D7BE9DF12FD494D7C7">Een gegevensbron voor meerdere apparaten en bouwen een <span class="wintitle"> Regel van de Fusie van het Profiel </span>. </li> 
        <li id="li_992BD05E2AFE454CAA4460DDEB2B839B">Een gegevensbron die verbindingen gebruikt die door een grafiek van het derdeapparaat worden verstrekt die met <span class="keyword"> Audience Manager </span> wordt geïntegreerd. </li> 
       </ul> </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Id-definitie </span></b> </p> </td> 
   <td colname="col2"> <p>De <b><span class="uicontrol"> opties van de Definitie van identiteitskaart </span></b> bepalen de verhouding een gegevensbron aan <span class="keyword"> Audience Manager </span> gebruiker - identiteitskaart (UUID) en bijbehorende apparaten verbonden door een grafiek van het derdeapparaat die met <span class="keyword"> Audience Manager </span> wordt geïntegreerd. U kunt onder andere de volgende opties kiezen: </p> <p> 
     <ul id="ul_718ADABF0C0C44E29643C85C69CE294F"> 
      <li id="li_19936095319446698E9A577385CD2A80"> <b><span class="uicontrol"> Persoon: </span></b> identiteitskaart die wordt gebruikt om één enkele persoon te bepalen. Deze id kan worden toegewezen aan meerdere <span class="keyword"> Audience Manager </span> -id's. </li> 
      <li id="li_3D939AFF34654D618A05D2603F34462D"> <b><span class="uicontrol"> Huishouden:</span></b> De id die wordt gebruikt om een groep personen te definiëren. Deze id kan aan meerdere Audience Manager-id's worden toegewezen. </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

## [!UICONTROL Data Export Controls] {#export-controls}

[ de Controles van de Uitvoer van Gegevens ](../features/data-export-controls.md) zijn facultatieve classificatieregels u op a [!UICONTROL data source] en [!UICONTROL destination] kunt toepassen. Hiermee voorkomt u dat u gegevens naar een [!UICONTROL destination] verzendt wanneer die handeling een schending van de privacy van gegevens of een gebruiksovereenkomst oplevert. Sla deze sectie over als u [!UICONTROL Data Export Controls] niet gebruikt.

>[!IMPORTANT]
>
>Exportbeperkingen werken alleen als u een overeenkomend exportlabel op een [!UICONTROL destination] instelt.

U kunt onder andere de volgende opties kiezen:

* **[!UICONTROL No Restriction]**
* **[!UICONTROL Cannot be tied to personally identifiable information]**
* **[!UICONTROL Cannot be used for on-site ad targeting]**
* **[!UICONTROL Cannot be used for off-site ad targeting]**
* **[!UICONTROL Cannot be used for on-site personalization]**

## [!UICONTROL Data Source] Instellingen {#data-source-settings}

[!UICONTROL Data Source Settings] bevat de hieronder vermelde besturingselementen en opties. Sommige van deze instellingen hebben extra subopties en menu-items die u kunt selecteren om een gegevensbron te wijzigen.

### [!UICONTROL Inbound Data Source] Instellingen

Schakel het selectievakje **[!UICONTROL Inbound]** in als uw gegevensbron is ontworpen voor het ontvangen van binnenkomende gegevens. Als u het selectievakje **[!UICONTROL Inbound]** selecteert, worden nog twee extra groepen besturingselementen weergegeven die hieronder worden beschreven.

>[!NOTE]
>
>Het selectievakje **[!UICONTROL Inbound]** is alleen bedoeld voor het weergeven of verbergen van de [!UICONTROL data source] -besturingselementen die hieronder worden beschreven. Het uitschakelen van de optie **[!UICONTROL Inbound]** heeft op geen enkele manier invloed op de gegevensinvoer. Uw geregistreerde gegevens worden verwerkt, ongeacht of deze optie is ingeschakeld.

<table id="table_B2825B7BE0DB4665B47C589A3787CD93"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Instelling </th> 
   <th colname="col2" class="entry"> Menuopties </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> ID-type </span></b> </p> </td> 
   <td colname="col2"> <p>Voor de optie <b><span class="uicontrol"> Binnenkomend </span></b> is een id-type vereist. U kunt onder andere de volgende opties kiezen: </p> <p> 
     <ul id="ul_3BC963CE378B4F6CB1861643A4541634"> 
      <li id="li_B86C5E7847424A2B9C094DF02741DDB8"> <b><span class="uicontrol"> Klantidentiteitskaart </span></b>: Identificeert binnenkomende gegevens met een klant identiteitskaart </li> 
      <li id="li_AD8E440436314902A794CDB11A3D657F"> <b><span class="uicontrol"> Audience Manager-id </span></b> : identificeert binnenkomende gegevens met een <span class="keyword"> Audience Manager </span> -id. </li> 
      <li id="li_B56608334DDA453B9E4E88E53DAF92FA"> <b><span class="uicontrol"> Experience Cloud-id </span></b> : identificeert binnenkomende gegevens met een <span class="keyword"> Experience Cloud </span> -id. Zie <a href="https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html?lang=nl-NL" format="https" scope="external"> Koekjes en identiteitskaart van Experience Cloud </a>. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Problemen met bestandsindeling oplossen </span></b> </p> </td> 
   <td colname="col2"> <p>Selecteer <b><span class="uicontrol"> Enable file error sampling </span></b> wanneer u problemen met binnenkomende dossierverwerking moet oplossen. Deze functie genereert een foutvoorbeeldrapport waarin u fouten in de bestandsindeling en de syntaxis ziet. </p> <p>Zie <a href="../reporting/onboarding-status-report.md#onboarding-status-about"> Statusrapport on boarding: Info </a> voor informatie over foutrapportage en foutsampling. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Overige [!UICONTROL Data Source] instellingen

<table id="table_82FEFA8DC8294FA18FB4C17F02DF5152"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Instelling </th> 
   <th colname="col2" class="entry"> Selecteren als </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Uitgaand </span></b> </p> </td> 
   <td colname="col2"> <p>Uw gegevensbron verzendt gegevens naar een bestemming. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Delen ingeschakeld </span></b> </p> </td> 
   <td colname="col2"> <p>Uw gegevensbron kan met andere partners worden gedeeld. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gebruiken als Voor authentiek verklaard Profiel </span></b> </p> </td> 
   <td colname="col2"> <p>De gegevensbron voor meerdere apparaten bevat een geverifieerde id. Een geverifieerde id wordt verzameld en gesynchroniseerd met een <span class="keyword"> Audience Manager </span> -id tijdens een verificatiegebeurtenis (een gebruiker meldt zich bijvoorbeeld on-site, in-app, enz.). De geverifieerde id kan worden gebruikt voor gegevens aan boord van andere bronnen die deze id opslaan. Het kan ook worden gebruikt om veelvoudige apparaat IDs in <span class="wintitle"> Verbinding van het Profiel </span> te verbinden. </p> <p>Met deze optie wordt een tekstveld weergegeven waarin u de naam van de gegevensbron kunt wijzigen in een alias. Als u een alias gebruikt, treedt deze nieuwe naam de gegevensbronnaam met voeten en verschijnt in de <span class="wintitle"> Voor authentiek verklaarde Opties van het Profiel </span> wanneer u <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> een regel van de Fusie van het Profiel </a> creeert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Als apparaatgrafiek gebruiken </span></b> </p> </td> 
   <td colname="col2"> <p>Maakt een gegevensbron als een apparaatgrafiek die u aan andere <span class="keyword"> Audience Manager </span> klanten kunt verstrekken. Alvorens u deze optie selecteert, vertel met uw <span class="keyword"> Audience Manager </span> consultant welke klanten deze <span class="wintitle"> Source van Gegevens </span> zouden moeten worden gedeeld met. Uw consultant zal deze bedrijven moeten voorzien via onze interne processen. </p> <p>Met deze optie wordt een tekstveld weergegeven waarin u de naam van de gegevensbron kunt wijzigen in een alias. Als u een alias gebruikt, treedt deze nieuwe naam de gegevensbronnaam met voeten en verschijnt in de <span class="wintitle"> Opties van het Apparaat </span> wanneer u <a href="../features/profile-merge-rules/merge-rules-start.md#create-profile-merge-rule"> een regel van de Fusie van het Profiel </a> creeert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gekoppelde gebruikers- of apparaatid's delen met specifieke Audience Manager-klanten </span></b> </p> </td> 
   <td colname="col2"> <p>De gegevensbron voor meerdere apparaten bevat id's uit een apparaatgrafiek. Een apparatengrafiek is een inzameling van IDs die aan één of meerdere <span class="keyword"> Audience Manager </span> IDs aan een cluster in kaart brengen. Deze cluster vertegenwoordigt doorgaans een persoon of een grotere groep huishoudens. Alleen beschikbaar voor accounts die zijn vermeld als 'Data Provider'. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Gekoppelde gebruikers- of apparaatid's delen op het Audience Manager-platform </span></b> </p> </td> 
   <td colname="col2"> <p>Uw gegevensbron bevat bezoeker of apparaat IDs die over andere <span class="keyword"> Experience Cloud </span> oplossingen kunnen worden gedeeld. </p> </td> 
  </tr>
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Bewaren van gegevens voor niet-actieve id's van klanten </span></b> </p> </td> 
   <td colname="col2"> <p>Hiermee kunt u de periode voor het bewaren van gegevens instellen voor inactieve id's van klanten. Dit bepaalt hoe lang Audience Manager de id's van de Klant in onze database bewaart nadat ze voor het laatst op het Audience Manager-platform zijn gezien.</p> <p>De standaardwaarde is 24 maanden (720 dagen). De minimumwaarde die u kunt instellen is 1 maand en de maximumwaarde is 5 jaar. We tellen alle maanden als 30 dagen.</p> <p>Audience Manager voert een proces uit dat inactieve klant-id's één keer per week verwijdert, in overeenstemming met de gegevensopslag die u hebt ingesteld voor niet-actieve klant-id's.</p> <p>Audience Manager voert een proces uit dat inactieve klant-id's één keer per week verwijdert, in overeenstemming met de gegevensopslag die u hebt ingesteld voor niet-actieve klant-id's.</p> <p><b> Nota </b>: Deze controle is beschikbaar slechts voor cross-device gegevensbronnen. Zie ook <a href="../features/profile-merge-rules/merge-rules-start.md#settings"> Een Source voor apparaatgegevens maken </a> .</p></td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unieke Trait Integration-codes </span></b> </p> </td> 
   <td colname="col2"> <p>U wilt afdwingen dat twee eigenschappen van dezelfde gegevensbron niet dezelfde integratiecode hebben. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b><span class="uicontrol"> Unieke segmentintegratiecodes </span></b> </p> </td> 
   <td colname="col2"> <p>U wilt afdwingen dat twee segmenten van dezelfde gegevensbron niet dezelfde integratiecode hebben. </p> </td> 
  </tr>
 </tbody>
</table>
