---
description: Audience Manager ontvangt elke dag een enorme hoeveelheid gegevens. Dit beïnvloedt de hoeveelheid tijd het neemt om uw gegevens te verwerken en rapportresultaten te produceren. De inhoud in deze sectie beschrijft hoe deze tijdintervallen uw rekening van de Manager van de Publiek beïnvloeden. Ook, zijn de tijdkaders en de programma's die hier worden beschreven algemene slechts richtlijnen. Deze schema's vormen geen Service-Level Overeenkomsten (SLA's) of verbintenissen in verband met de levering van gegevens. Adobe behoudt zich het recht voor om de tijdsbestekken en -schema's op elk gewenst moment zonder voorafgaande kennisgeving te wijzigen.
seo-description: Audience Manager ontvangt elke dag een enorme hoeveelheid gegevens. Dit beïnvloedt de hoeveelheid tijd het neemt om uw gegevens te verwerken en rapportresultaten te produceren. De inhoud in deze sectie beschrijft hoe deze tijdintervallen uw rekening van de Manager van de Publiek beïnvloeden. Ook, zijn de tijdkaders en de programma's die hier worden beschreven algemene slechts richtlijnen. Deze schema's vormen geen Service-Level Overeenkomsten (SLA's) of verbintenissen in verband met de levering van gegevens. Adobe behoudt zich het recht voor om de tijdsbestekken en -schema's op elk gewenst moment zonder voorafgaande kennisgeving te wijzigen.
seo-title: Hoe de levering van gegevens en de tijden van de dossierverwerking rapporten beïnvloeden
solution: Audience Manager
title: Hoe de levering van gegevens en de tijden van de dossierverwerking rapporten beïnvloeden
uuid: 4b975512-f67e-4749-a7ef-168415597682
translation-type: tm+mt
source-git-commit: 6bdf79b17ec96ed0d54ed97ab5d69fadb68763b5

---


# Hoe de levering van gegevens en de tijden van de dossierverwerking rapporten beïnvloeden{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager ontvangt elke dag een enorme hoeveelheid gegevens. Dit beïnvloedt de hoeveelheid tijd het neemt om uw gegevens te verwerken en rapportresultaten te produceren. De inhoud in deze sectie beschrijft hoe deze tijdintervallen uw rekening van de Manager van de Publiek beïnvloeden. Ook, zijn de tijdkaders en de programma&#39;s die hier worden beschreven algemene slechts richtlijnen. Deze schema&#39;s vormen geen Service-Level Overeenkomsten (SLA&#39;s) of verbintenissen in verband met de levering van gegevens. Adobe behoudt zich het recht voor om de tijdsbestekken en -schema&#39;s op elk gewenst moment zonder voorafgaande kennisgeving te wijzigen.

## Meldingsnummers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

De volgende lijst maakt een lijst en beschrijft de tijdintervallen in onze algemene en real-time rapporten.


| Gegevenstype | Beschrijving |
|---|---|
| Real-time gegevens | Realtime cijfers voor vandaag zijn voor de uren 00:00 tot 23:59:59 UTC van gisteren. |
| Algemene rapportgegevens | De gegevens in de [algemene verslagen](../reporting/general-reports.md#general-reports-overview) zijn afhankelijk van de succesvolle voltooiing van andere arbeidsprocessen en van de hoeveelheid gegevens die voor een bepaalde dag zijn ontvangen. Meestal moeten de [!UICONTROL General Report] gegevens elke dag om 18.00 uur worden bijgewerkt. |

## Binnenkomende en Uitgaande Overdrachten van het Dossier {#inbound-outbound-file-transfers}

[!DNL Audience Manager] verwerkt en verzendt binnenkomende en uitgaande [!UICONTROL Server-to-Server (S2S)] dossieroverdrachten volgens de programma&#39;s die in deze sectie worden beschreven. Gezien deze programma&#39;s en de besnoeiingstijden, zou u discrepanties met nieuwe segmenten tussen real time en totale segmentaantallen kunnen zien.

| Bestandstype | Beschrijving |
|---|---|
| Binnenkomende bestandsinbraak (offlinegegevens) | Bestandsverwerking wordt tweemaal per dag uitgevoerd. Deze procedures nemen gegevens op en bereiden het voor levering voor. De leveringstijden van het dossier variëren omdat zij door de totale hoeveelheid klantengegevens worden beïnvloed die moet worden verwerkt. U kunt een maximale vertraging van 48 uur verwachten tussen het moment dat het bestand wordt geüpload in Audience Manager en het moment dat de gegevens beschikbaar zijn voor rapportage en activering. |
| Uitgaande (geëxporteerde) bestanden | Bestandsverwerking en -levering vinden eenmaal per dag plaats, om ongeveer 14:00 uur UTC. Houd er rekening mee dat de verwerking en levering worden beïnvloed door het totale aantal en de grootte van deze bestanden. In sommige gevallen kan de bestandsverwerking 24 uur vertraging oplopen. Als dit gebeurt, verzendt Audience Manager 2 bestanden voor een bepaalde dag in plaats van 1. Wij zullen onze klanten in het zeldzame geval op de hoogte brengen waar de Manager van de Publiek moet ophouden verwerkend een dossier. Gezien deze omstandigheden is het moeilijk om de leveringstermijnen voor uitgaande gegevens te ramen. Om te bepalen of u een volledige reeks dossiers hebt ontvangen, controleer timestamp en zoek om het even welke ontbrekende dagen. Dit is een UNIX UTC-tijdstempel van 13 cijfers waarmee de tijd wordt vastgelegd waarop het bestand is gemaakt. Zie [in real time Uitgaande gegevensoverdrachten](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Logbestanden van advertentieserver | De verwerking van het dossier wordt uitgevoerd in bijna echt - tijd om logboekdossierverslagen in te gaan aangezien de uurdossiers klaar zijn. Het proces om de bestanden voor te bereiden voor rapportage wordt eenmaal per dag uitgevoerd. De leveringstijden van het dossier variëren omdat zij door de totale hoeveelheid klantengegevens worden beïnvloed die moet worden verwerkt. U moet een maximale vertraging van 48 uur verwachten tussen het moment dat u het bestand uploadt naar Audience Manager en het moment dat de gegevens beschikbaar zijn voor rapportage en activering. |

>[!MORELIKETHIS]
>
>* [Binnenkomende Veelgestelde vragen over gegevensinvoer van klanten](../faq/faq-inbound-data-ingestion.md)

