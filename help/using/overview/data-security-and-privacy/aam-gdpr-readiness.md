---
description: GDPR-gebruikershulp voor klanten van Audience Managers
seo-description: GDPR-gebruikershulp voor klanten van Audience Managers
seo-title: GDPR-gebruikershulp voor klanten van Audience Managers
solution: Audience Manager
title: GDPR-gebruikershulp voor klanten van Audience Managers
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '475'
ht-degree: 0%

---


# GDPR-richtlijnen voor gereedheid voor klanten van Audience Managers (gegevenscontrollers) {#gdpr-readiness-guidance}

Audience Manager beveelt aan proactief te zijn op het gebied van gegevensbeheer en organisatorische gereedheid. Dit zal u helpen ervoor zorgen dat uw consumentengegevens voor processen met betrekking tot toegang of schrappingsverzoeken worden georganiseerd, zullen uw teams worden toegelaten en gemachtigd om deze verzoeken te beheren, en uw consumenten (de Onderwerpen van Gegevens) zullen een positieve, onderscheiden ervaring met uw merk hebben.

Als uw gegevensprocessor kan Adobe geen juridisch advies geven over de GDPR-vereisten en het proces voor het verkrijgen van toestemming van de betrokkenen. Raadpleeg uw juridische adviseur voor advies over naleving van GDPR voor uw organisatie.

## Gegevensbeheer: Beginnen hoe uw consumentengegevens in uw Audience Manager-instantie worden beheerd

* Herzie diverse klant IDs uw marketing teams gebruiken om gebruikers in Audience Manager, samen met de gegevensbronnen te identificeren waarin zij worden opgeslagen. Dit zal het proces voor verzoeken (zoals schrapping of toegang) stroomlijnen aangezien bepaalde gegevenstypes door uw teams voorafgaand aan opname in Audience Manager zullen worden gehakt.
* IdFA/GAID mobiele apparaat-id&#39;s worden gebruikt voor meerdere gebruiksgevallen in Audience Manager. Als u Adobe Mobile SDK gebruikt, moet u de Experience Cloud-id (MID) samen met IDFA/GAID verzenden om te controleren of de GDPR-reacties zijn voltooid.
* Aangezien de definitie van persoonlijke gegevens expansiever wordt, IP kunnen de adressen als persoonlijke gegevens in uw regio worden beschouwd. Neem proactief contact op met Adobe Consulting om de laatste octet te verduisteren.
* Bepaal een bevestiging/authentificatiebeleid &amp; proces om de identiteit van een Onderwerp van Gegevens te bevestigen wanneer zij een verzoek GDPR indienen.
* Overweeg het gebruiken van de Controles [van de Uitvoer van](../../features/data-export-controls.md) Gegevens om publieksactivering aan technologieën te blokkeren die persoonlijke gegevens huishouden. Segmenten met gegevens van derden moeten bijvoorbeeld niet worden gesynchroniseerd met e-mailserviceproviders. Stel een optie in [!UICONTROL Data Export Control] om ervoor te zorgen dat niemand in uw organisatie deze gegevens per ongeluk kan activeren.
* Beginnen gebruikend [Rol Gebaseerde Controles](../../features/administration/administration-overview.md) van de Toegang om de juiste teams toegang tot voorgenomen gegevens te verzekeren.
* Overweeg de juiste [bewaartermijnen](../../faq/faq-privacy.md#data-retention-faq) voor de gegevens.
* Herziening van het beleid inzake identiteitsverbanden en privacy en wettelijke vereisten om te zien wanneer en waar het passend is om identiteitsreeksen te koppelen; gebruik correct via de Regels [van de Fusie van het](../../features/profile-merge-rules/merge-rules-overview.md)Profiel van de Audience Manager.

## Gereedheid van organisatie: Een bedrijfsproces instellen

* Identificeer een proces om te ontvangen/op de verzoeken van het Onderwerp van Gegevens te antwoorden. Overweeg een geautomatiseerd programma te maken voor het verzenden van aanvragen naar de Audience Manager.
* Wijs een privacy-aanspreekpunt aan binnen uw DMP-expertisecentrum. Verbind het privacy punt van uw organisatie van contact met uw team van het het productgebruik van de Audience Manager om te begrijpen hoe u uw vereisten van inputID zou kunnen beheren.
* Voer een gegevenscontrole uit alvorens met het Onderwerp van Gegevens te delen. Documenteer de stappen u opstelde, om u te helpen verantwoordingsplicht vestigen.
