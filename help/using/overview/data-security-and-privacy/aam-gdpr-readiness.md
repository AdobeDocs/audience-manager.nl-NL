---
description: Richtlijnen voor GDPR (AVG)-gereedheid voor Audience Manager-klanten
seo-description: Richtlijnen voor GDPR (AVG)-gereedheid voor Audience Manager-klanten
seo-title: Richtlijnen voor GDPR (AVG)-gereedheid voor Audience Manager-klanten
solution: Audience Manager
title: Richtlijnen voor GDPR (AVG)-gereedheid voor Audience Manager-klanten
feature: Data Governance & Privacy
exl-id: 353b9035-20f3-41ff-819c-71f161e6b1e1
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '478'
ht-degree: 99%

---

# Richtlijnen voor GDPR (AVG)-gereedheid voor Audience Manager-klanten (datacontrollers) {#gdpr-readiness-guidance}

Audience Manager adviseert proactief te zijn op de gebieden van data-governance en organisatorische gereedheid. Dit zal u helpen ervoor te zorgen dat uw consumentendata zijn georganiseerd voor processen in verband met toegangs- of verwijderingsaanvragen, dat uw teams klaar zijn om deze aanvragen te begeren, en dat uw klanten (geregistreerde personen) een positieve, gedifferentieerde ervaring met uw merk hebben.

Als uw dataprocessor kan Adobe geen juridisch advies geven over de GDPR (AVG)-vereisten en het proces voor het verkrijgen van toestemming van uw geregistreerde personen. Raadpleeg uw juridisch adviseur voor advies over naleving van GDPR (AVG) voor uw organisatie.

## Data Governance: Begin nu al met nadenken over de manier waarop uw consumentendata worden beheerd in uw Audience Manager-instantie

* Bekijk de verschillende klant-id’s die uw marketingteams gebruiken om gebruikers in Audience Manager te identificeren, samen met de databronnen waarin ze zijn opgeslagen. Dit zal het proces voor aanvragen (zoals verwijdering of toegang) stroomlijnen, aangezien bepaalde datatypen door uw teams worden gehasht voordat ze in Audience Manager worden opgenomen.
* Id’s van mobiele apparaten met IDFA/GAID worden gebruikt voor meerdere gebruiksscenario’s in Audience Manager. Als u Adobe Mobile SDK gebruikt, moet u de Experience Cloud ID (MID) samen met IDFA/GAID verzenden om ervoor te zorgen dat de GDPR (AVG)-reacties volledig zijn.
* Aangezien de definitie van persoonlijke data uitgebreider wordt, is het mogelijk dat IP-adressen in uw regio als persoonlijke data worden beschouwd. Neem proactief contact op met Adobe Consulting om de laatste octet onzichtbaar te maken.
* Stel een beleid en een proces op voor validatie/verificatie om de identiteit van een geregistreerde persoon te bevestigen wanneer deze een GDPR (AVG)-aanvraag indient.
* Overweeg het gebruik van [Besturingselementen voor data-export ](../../features/data-export-controls.md) om de activering van doelgroepen met persoonlijke data te blokkeren voor technologieën. Segmenten met data van derden moeten bijvoorbeeld niet worden gesyndiceerd met e-mailserviceproviders. Stel een [!UICONTROL Data Export Control] in om ervoor te zorgen dat niemand in uw organisatie deze data per ongeluk kan activeren.
* Begin met het gebruik van [Op rollen gebaseerd toegangsbeheer](../../features/administration/administration-overview.md) om ervoor te zorgen dat de juiste teams toegang hebben tot de beoogde data.
* Denk na over geschikte [retentieperioden](../../faq/faq-privacy.md#data-retention-faq) voor de data.
* Bekijk het privacybeleid, het beleid voor identiteitskoppeling en de wettelijke vereisten om te zien wanneer en waar het gepast is om identiteitsreeksen met elkaar te verbinden. Hanteer de [Regels voor profielsamenvoeging](../../features/profile-merge-rules/merge-rules-overview.md) van Audience Manager om op gepaste wijze te werk te gaan.

## Organisatie-gereedheid: een bedrijfsproces instellen

* Identificeer een proces voor het ontvangen en beantwoorden van aanvragen van geregistreerde personen. Overweeg een geautomatiseerde tool te maken voor het verzenden van aanvragen naar Audience Manager.
* Wijs een privacyaanspreekpunt aan binnen uw DMP-expertisecentrum. Verbind het privacyaanspreekpunt van uw organisatie met het productgebruiksteam van Audience Manager om inzicht te krijgen in hoe u de id-vereisten voor uw invoer kunt beheren.
* Voer een datacontrole uit voordat u data deelt met de geregistreerde persoon. Documenteer de stappen die u hebt geïmplementeerd, zodat u de verantwoordelijkheden kunt vaststellen.
