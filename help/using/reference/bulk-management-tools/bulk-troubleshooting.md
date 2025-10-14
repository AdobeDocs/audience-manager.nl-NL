---
description: Wat te doen wanneer de aantekenvellen een fout terugkeren of uw bulkverzoek ontbreekt.
seo-description: What to do when the worksheets return an error or your bulk request fails.
seo-title: Troubleshooting Tips for Bulk Management Tools
solution: Audience Manager
title: Tips voor het oplossen van problemen voor Bulk Management Tools
uuid: 550908a1-e24e-4f31-954b-7132c0c8dc3e
feature: BAAAM
exl-id: 4f1c501c-2e28-4ce5-829f-4d81d10cdccd
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '410'
ht-degree: 0%

---

# Tips voor het oplossen van problemen voor Bulk Management Tools{#troubleshooting-tips-for-bulk-management-tools}

Wat te doen wanneer de aantekenvellen een fout terugkeren of uw bulkverzoek ontbreekt.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

<p>r_bulk_troubleshoot.xml </p>

 -->

>[!NOTE]
>
>[&#x200B; RBAC groepstoestemmingen &#x200B;](../../features/administration/administration-overview.md) die in [!DNL Audience Manager] worden toegewezen UI wordt geëerd in [!UICONTROL Bulk Management Tools].

Factoren zoals zwaar netwerkverkeer, servergebruik, en grote gegevensreeksen kunnen een bulkverzoek veroorzaken om of uit tijd te ontbreken. Als er een probleem is, stopt het werkblad met het schrijven van gegevens en wordt er een foutbericht weergegeven. Wanneer dit gebeurt, moet u:

* Lees het foutbericht.
* Los het probleem op.
* Verwijder alle rijen die al zijn bijgewerkt.
* Probeer het bulkverzoek opnieuw.

## Verificatiefouten, lange vertragingen of niet-responsief gedrag {#delays-behavior}

De volgende lijst maakt een lijst van sommige gemeenschappelijke problemen u wanneer het maken van bulkverzoeken met de aantekenvellen kunt ontmoeten. Probeer deze problemen op te lossen met de aanbevolen oplossingen. Als het probleem niet wordt opgelost met de aanbevolen oplossingen, slaat u uw werk op, start u de computer opnieuw op en probeert u het verzoek nogmaals zonder andere toepassingen te starten of ermee te werken.

<table id="table_AC6FB99402214A4EAC6E709465BB67AF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Probleem </th> 
   <th colname="col2" class="entry"> Oplossing </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <b> fout van de Authentificatie </b> </td> 
   <td colname="col2"> 
    <b> Update aan recentste versie van Microsoft Excel </b>: Wanneer een nieuwe versie van Microsoft Excel wordt vrijgegeven en u een oudere versie gebruikt, zou u een authentificatiefout in het Werkblad van het Beheer van het Bulk kunnen ontmoeten. Update naar de nieuwste versie van Microsoft Excel om de verificatiefout op te lossen.
</td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Lange vertragingen </b> </td> 
   <td colname="col2"> 
    <ul id="ul_AA6F414024B2475AB1C0B46DC3FF0B36"> 
     <li id="li_ECC83AC39D7142519AA9A223DB8FCF23"> <b> draai van verenigbaarheidswijze </b>: Controle als u andere aantekenvellen open op de verenigbaarheidswijze van Microsoft Excel hebt. In de compatibiliteitsmodus kunnen de runtimes toenemen. Sluit spreadsheets die geopend zijn in deze modus en probeer het bulkverzoek opnieuw. </li> 
     <li id="li_234BFCF563234DE198884F33AB75280D"> <b> middelen van het Systeem </b>: De beperkte systeemmiddelen dragen aan lange vertragingen bij. Sluit alle andere programma's voordat u een aanvraag bulksgewijs indient. </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <b> Geen reactie </b> </td> 
   <td colname="col2">Als u op een actieknop klikt en er gebeurt niets: 
    <ul id="ul_142E63CDD556414AB639E51734FEDBCF"> 
     <li id="li_DBB6C819603D46B5AECC9C854FDAFDF1">Zorg ervoor dat u de juiste kopteksten voor de selectieactie hebt. </li> 
     <li id="li_391C9031907A4085BDAD42054960045C">Zorg ervoor u het juiste aantekenvel voor de gekopieerde kopballen gebruikt. </li> 
     <li id="li_76A7241989204933858621FAAB5C3408">Controleer de positie van de gegevens die u in een bulkbewerking wilt gebruiken. Alle kopteksten beginnen in kolom A, rij 1. Alle gegevens worden in de corresponderende koppen opgenomen, beginnend in kolom A, rij 2 (direct onder de kopteksten). </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

## Foutberichten

Soms kunt u foutberichten ontvangen wanneer u bulksgewijs wijzigingen aanbrengt. Om het foutenbericht te interpreteren, zie [&#x200B; Gedefinieerde Codes van de Reactie &#x200B;](/help/using/api/rest-api-main/aam-api-getting-started.md) in onze API documentatie.
