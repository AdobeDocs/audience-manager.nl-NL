---
description: GDPR-gebruikershulp voor Audience Manager-klanten
seo-description: GDPR-gebruikershulp voor Audience Manager-klanten
seo-title: GDPR-gebruikershulp voor Audience Manager-klanten
solution: Audience Manager
title: GDPR-gebruikershulp voor Audience Manager-klanten
translation-type: tm+mt
source-git-commit: caa5207bc2955ee18b40d6a51613340001cbd92f

---


# GDPR-gebruikershulp voor klanten van Audience Manager (gegevenscontrollers) {#gdpr-readiness-guidance}

De Manager van het publiek adviseert proactief op de gebieden van gegevensbestuur en organisatorische bereidheid te zijn. Dit zal u helpen ervoor zorgen dat uw consumentengegevens voor processen met betrekking tot toegang of schrappingsverzoeken worden georganiseerd, zullen uw teams worden toegelaten en gemachtigd om deze verzoeken te beheren, en uw consumenten (de Onderwerpen van Gegevens) zullen een positieve, onderscheiden ervaring met uw merk hebben.

Als uw gegevensprocessor kan Adobe geen juridisch advies geven over de GDPR-vereisten en het proces voor het verkrijgen van toestemming van de betrokkenen. Raadpleeg uw juridische adviseur voor advies over naleving van GDPR voor uw organisatie.

## Gegevensbeheer: Beginnen met hoe uw consumentengegevens in uw instantie Audience Manager worden beheerd

* Herzie diverse klant IDs uw marketing teams gebruiken om gebruikers in de Manager van het Publiek, samen met de gegevensbronnen te identificeren waarin zij worden opgeslagen. Dit zal het proces voor verzoeken (zoals schrapping of toegang) stroomlijnen aangezien bepaalde gegevenstypes door uw teams voorafgaand aan opname in de Manager van de Publiek zullen worden gehakt.
* ID&#39;s van mobiele apparaten met IDFA/GAID worden gebruikt voor meerdere gebruiksgevallen in Audience Manager. Als u Adobe Mobile SDK gebruikt, moet u de Experience Cloud-id (MID) samen met IDFA/GAID indienen om ervoor te zorgen dat de GDPR-reacties volledig zijn.
* Aangezien de definitie van persoonlijke gegevens expansiever wordt, IP kunnen de adressen als persoonlijke gegevens in uw regio worden beschouwd. Neem proactief contact op met Adobe Consulting om de laatste octet te verduisteren.
* Bepaal een bevestiging/authentificatiebeleid &amp; proces om de identiteit van een Onderwerp van Gegevens te bevestigen wanneer zij een verzoek GDPR indienen.
* Overweeg het gebruiken van de Controles [van de Uitvoer van](../../features/data-export-controls.md) Gegevens om publieksactivering aan technologieën te blokkeren die persoonlijke gegevens huishouden. Segmenten met gegevens van derden moeten bijvoorbeeld niet worden gesynchroniseerd met e-mailserviceproviders. Stel een optie in [!UICONTROL Data Export Control] om ervoor te zorgen dat niemand in uw organisatie deze gegevens per ongeluk kan activeren.
* Beginnen gebruikend [Rol Gebaseerde Controles](../../features/administration/administration-overview.md) van de Toegang om de juiste teams toegang tot voorgenomen gegevens te verzekeren.
* Overweeg de juiste [bewaartermijnen](../../faq/faq-privacy.md#data-retention-faq) voor de gegevens.
* Herziening van het beleid inzake identiteitsverbanden en privacy en wettelijke vereisten om te zien wanneer en waar het passend is om identiteitsreeksen te koppelen; op de juiste wijze gebruiken via de [regels](../../features/profile-merge-rules/merge-rules-overview.md)voor het samenvoegen van profielen van Audience Manager.

## Gereedheid van organisatie: Een bedrijfsproces instellen

* Identificeer een proces om te ontvangen/op de verzoeken van het Onderwerp van Gegevens te antwoorden. Overweeg een geautomatiseerd programma te maken voor het verzenden van aanvragen naar Audience Manager.
* Wijs een privacy-aanspreekpunt aan binnen uw DMP-expertisecentrum. Sluit het privacypunt van uw organisatie aan op het productgebruiksteam van Audience Manager om te begrijpen hoe u de vereisten voor uw invoer-id kunt beheren.
* Voer een gegevenscontrole uit alvorens met het Onderwerp van Gegevens te delen. Documenteer de stappen u opstelde, om u te helpen verantwoordingsplicht vestigen.
