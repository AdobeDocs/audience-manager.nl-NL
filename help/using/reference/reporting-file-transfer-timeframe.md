---
description: Audience Manager ontvangt elke dag een enorme hoeveelheid gegevens. Dit beïnvloedt de hoeveelheid tijd het neemt om uw gegevens te verwerken en rapportresultaten te produceren. De inhoud in deze sectie beschrijft hoe deze tijdintervallen uw rekening van de Audience Manager beïnvloeden. Ook, zijn de tijdkaders en de programma's die hier worden beschreven algemene slechts richtlijnen. Deze schema's vormen geen Service-Level Overeenkomsten (SLA's) of verbintenissen in verband met de levering van gegevens. Adobe behoudt zich het recht voor om de termijnen en schema's te allen tijde zonder voorafgaande kennisgeving te wijzigen.
seo-description: Audience Manager receives a tremendous amount of data every day. This affects the amount of time it takes to process your data and generate report results. The content in this section describes how these time intervals affect your Audience Manager account. Also, the time frames and schedules described here are general guidelines only. These schedules do not constitute Service-Level Agreements (SLAs) or commitments related to data delivery. Adobe reserves the right to change the time frames and schedules at any time without notice.
seo-title: How Data Delivery and File Processing Times Affect Reports
solution: Audience Manager
title: Hoe de tijdsduur van datalevering en bestandsverwerking rapporten beïnvloedt
uuid: 4b975512-f67e-4749-a7ef-168415597682
feature: Reference
exl-id: d13102c3-fd1b-4c31-8003-9fdc0df36838
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '596'
ht-degree: 4%

---

# Hoe de tijdsduur van datalevering en bestandsverwerking rapporten beïnvloedt{#how-data-delivery-and-file-processing-times-affect-reports}

Audience Manager ontvangt elke dag een enorme hoeveelheid gegevens. Dit beïnvloedt de hoeveelheid tijd het neemt om uw gegevens te verwerken en rapportresultaten te produceren. De inhoud in deze sectie beschrijft hoe deze tijdintervallen uw rekening van de Audience Manager beïnvloeden. Ook, zijn de tijdkaders en de programma&#39;s die hier worden beschreven algemene slechts richtlijnen. Deze schema&#39;s vormen geen Service-Level Overeenkomsten (SLA&#39;s) of verbintenissen in verband met de levering van gegevens. Adobe behoudt zich het recht voor om de termijnen en schema&#39;s te allen tijde zonder voorafgaande kennisgeving te wijzigen.

## Meldingsnummers {#reporting-numbers}

<!-- 

c_reporting_file_transfer_timeframe.xml

 -->

De volgende lijst maakt een lijst en beschrijft de tijdintervallen in onze algemene en real-time rapporten.


| Datatype | Beschrijving |
|---|---|
| Real-time gegevens | Realtime cijfers voor vandaag zijn voor de uren 00:00 tot 23:59:59 UTC van gisteren. |
| Algemene rapportgegevens | De gegevens in de [Algemene rapporten](../reporting/general-reports.md#general-reports-overview) is afhankelijk van de succesvolle voltooiing van andere arbeidsprocessen en van de hoeveelheid gegevens die voor een bepaalde dag zijn ontvangen. Meestal [!UICONTROL General Report] gegevens moeten elke dag om 18.00 uur worden bijgewerkt. |

## Binnenkomende en Uitgaande Overdrachten van het Dossier {#inbound-outbound-file-transfers}

[!DNL Audience Manager] processen en verzenden binnenkomend en uitgaand [!UICONTROL Server-to-Server (S2S)] bestandsoverdrachten volgens de in deze sectie beschreven schema&#39;s. Gezien deze programma&#39;s en de besnoeiingstijden, zou u discrepanties met nieuwe segmenten tussen real time en totale segmentaantallen kunnen zien.

| Bestandstype | Beschrijving |
|---|---|
| Binnenkomende bestandsinbraak (offlinegegevens) | Bestandsverwerking wordt tweemaal per dag uitgevoerd. Deze procedures nemen gegevens op en bereiden het voor levering voor. De leveringstijden van het dossier variëren omdat zij door de totale hoeveelheid klantengegevens worden beïnvloed die moet worden verwerkt. U moet een maximale vertraging van 48 uur verwachten tussen het moment dat het bestand in de Audience Manager wordt geüpload en het moment dat de gegevens beschikbaar zijn voor rapportage en activering. |
| Uitgaande (geëxporteerde) bestanden | Bestandsverwerking en -levering vinden eenmaal per dag plaats, om ongeveer 14:00 uur UTC. Houd er rekening mee dat de verwerking en levering worden beïnvloed door het totale aantal en de grootte van deze bestanden. In sommige gevallen kan de bestandsverwerking 24 uur vertraging oplopen. Wanneer dit gebeurt, zal de Audience Manager 2 dossiers voor een bepaalde dag in plaats van 1 verzenden. Wij zullen onze klanten in het zeldzame geval op de hoogte brengen waar de Audience Manager moet ophouden met het verwerken van een dossier. Gezien deze omstandigheden is het moeilijk om de leveringstermijnen voor uitgaande gegevens te ramen. Om te bepalen of u een volledige reeks dossiers hebt ontvangen, controleer timestamp en zoek om het even welke ontbrekende dagen. Dit is een UNIX UTC-tijdstempel van 13 cijfers waarmee de tijd wordt vastgelegd waarop het bestand is gemaakt. Zie [Uitgaande gegevensoverdrachten in real time](../integration/receiving-audience-data/real-time-outbound-transfers/real-time-outbound-transfers.md). |
| Logbestanden van advertentieserver | De verwerking van het dossier wordt uitgevoerd in bijna echt - tijd om logboekdossierverslagen in te gaan aangezien de uurdossiers klaar zijn. Het proces om de bestanden voor te bereiden voor rapportage wordt eenmaal per dag uitgevoerd. De leveringstijden van het dossier variëren omdat zij door de totale hoeveelheid klantengegevens worden beïnvloed die moet worden verwerkt. U moet een maximale vertraging van 48 uur verwachten tussen het moment dat u het bestand uploadt naar de Audience Manager en het moment dat de gegevens beschikbaar zijn voor rapportage en activering. |

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over opname van binnenkomende klantdata](../faq/faq-inbound-data-ingestion.md)

