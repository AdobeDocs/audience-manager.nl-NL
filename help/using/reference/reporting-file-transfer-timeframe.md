---
description: Audience Manager ontvangt elke dag een enorme hoeveelheid gegevens. Dit beïnvloedt de hoeveelheid tijd het neemt om uw gegevens te verwerken en rapportresultaten te produceren. De inhoud in deze sectie beschrijft hoe deze tijdintervallen uw rekening van de Manager van de Publiek beïnvloeden. Ook, zijn de tijdkaders en de programma's die hier worden beschreven algemene slechts richtlijnen. Deze schema's vormen geen Service-Level Overeenkomsten (SLA's) of verbintenissen in verband met de levering van gegevens. Adobe behoudt zich het recht voor om de tijdsbestekken en -schema's op elk gewenst moment zonder voorafgaande kennisgeving te wijzigen.
seo-description: Audience Manager ontvangt elke dag een enorme hoeveelheid gegevens. Dit beïnvloedt de hoeveelheid tijd het neemt om uw gegevens te verwerken en rapportresultaten te produceren. De inhoud in deze sectie beschrijft hoe deze tijdintervallen uw rekening van de Manager van de Publiek beïnvloeden. Ook, zijn de tijdkaders en de programma's die hier worden beschreven algemene slechts richtlijnen. Deze schema's vormen geen Service-Level Overeenkomsten (SLA's) of verbintenissen in verband met de levering van gegevens. Adobe behoudt zich het recht voor om de tijdsbestekken en -schema's op elk gewenst moment zonder voorafgaande kennisgeving te wijzigen.
seo-title: Hoe de levering van gegevens en de tijden van de dossierverwerking rapporten beïnvloeden
solution: Audience Manager
title: Hoe de levering van gegevens en de tijden van de dossierverwerking rapporten beïnvloeden
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Hoe de levering van gegevens en de tijden van de dossierverwerking rapporten beïnvloeden{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager ontvangt elke dag een enorme hoeveelheid gegevens. Dit beïnvloedt de hoeveelheid tijd het neemt om uw gegevens te verwerken en rapportresultaten te produceren. De inhoud in deze sectie beschrijft hoe deze tijdintervallen uw rekening van de Manager van de Publiek beïnvloeden. Ook, zijn de tijdkaders en de programma&#39;s die hier worden beschreven algemene slechts richtlijnen. Deze schema&#39;s vormen geen Service-Level Overeenkomsten (SLA&#39;s) of verbintenissen in verband met de levering van gegevens. Adobe behoudt zich het recht voor om de tijdsbestekken en -schema&#39;s op elk gewenst moment zonder voorafgaande kennisgeving te wijzigen.

## Meldingsnummers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

De volgende lijst maakt een lijst en beschrijft de tijdintervallen in onze algemene en real-time rapporten.

<table id="table_73AF95DF5D3A423894486444505D816A"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Gegevenstype </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Real-time gegevens</b> </p> </td> 
   <td colname="col2"> <p> Realtime cijfers voor vandaag zijn voor de uren 00:00 tot 23:59:59 UTC van gisteren. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Algemene rapportgegevens</b> </p> </td> 
   <td colname="col2"> <p>De gegevens in de <a href="../reporting/general-reports.md#general-reports-overview"> algemene verslagen</a> zijn afhankelijk van de succesvolle voltooiing van andere arbeidsprocessen en van de hoeveelheid gegevens die voor een bepaalde dag zijn ontvangen. Meestal moeten de gegevens van het <span class="wintitle"> algemeen rapport</span> elke dag om 18:00 UTC worden bijgewerkt. </p> </td> 
  </tr> 
 </tbody> 
</table>

## Binnenkomende en Uitgaande Overdrachten van het Dossier {#inbound-outbound-file-transfers}

[!DNL Audience Manager] verwerkt en verzendt binnenkomende en uitgaande [!UICONTROL Server-to-Server (S2S)] dossieroverdrachten volgens de programma&#39;s die in deze sectie worden beschreven. Gezien deze programma&#39;s en de besnoeiingstijden, zou u discrepanties met nieuwe segmenten tussen real time en totale segmentaantallen kunnen zien.

<table id="table_303BEBA0756F46DDAA98D366A5304374"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Bestandstype </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>Binnenkomende bestandsinbraak (offlinegegevens)</b> </p> </td> 
   <td colname="col2"> <p>Bestandsverwerking wordt tweemaal per dag uitgevoerd. Deze procedures nemen gegevens op en bereiden het voor levering voor. </p> <p>De leveringstijden van het dossier variëren omdat zij door de totale hoeveelheid klantengegevens worden beïnvloed die moet worden verwerkt. U moet een maximale vertraging van 48 uur verwachten tussen het moment dat het bestand wordt geüpload in Audience Manager <span class="keyword"></span> en het moment dat de gegevens beschikbaar zijn voor rapportage en activering. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>Uitgaande (geëxporteerde) bestanden</b> </p> </td> 
   <td colname="col2"> <p>Bestandsverwerking en -levering vinden eenmaal per dag plaats, om ongeveer 14:00 uur UTC. Houd er rekening mee dat de verwerking en levering worden beïnvloed door het totale aantal en de grootte van deze bestanden. In sommige gevallen kan de bestandsverwerking 24 uur vertraging oplopen. Als dit gebeurt, verzendt <span class="keyword"> Audience Manager</span> twee bestanden voor een bepaalde dag in plaats van 1. Wij zullen onze klanten in het zeldzame geval op de hoogte brengen waar de Manager <span class="keyword"> van de</span> Publiek een dossier moet ophouden geheel te verwerken. Gezien deze omstandigheden is het moeilijk om de leveringstermijnen voor uitgaande gegevens te ramen. </p> <p>Om te bepalen of u een volledige reeks dossiers hebt ontvangen, controleer timestamp en zoek om het even welke ontbrekende dagen. Dit is een UNIX UTC-tijdstempel van 13 cijfers waarmee de tijd wordt vastgelegd waarop het bestand is gemaakt. Zie <a href="../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md"> in real time Uitgaande Overdrachten</a>van Gegevens. </p> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Binnenkomende Veelgestelde vragen over gegevensinvoer van klanten](../faq/faq-inbound-data-ingestion.md)

