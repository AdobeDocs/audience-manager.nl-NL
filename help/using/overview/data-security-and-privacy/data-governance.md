---
description: In dit document wordt uitgelegd hoe klantdata in Audience Manager worden beheerd.
seo-description: TThis document explains how customer data is governed in Audience Manager.
seo-title: Data Governance
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, toestemming, verwarring, bestuur
title: Data Governance
feature: Data Governance & Privacy
exl-id: 52aeca00-73f2-4525-9e11-34a472ec45c6
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '454'
ht-degree: 94%

---

# Data Governance

## Overzicht {#overview}

Data Governance in Audience Manager verwijst naar de levenscyclus van uw klantdata in Audience Manager, en omvat [IP-adressen verzamelen en onzichtbaar maken](data-governance.md#collecting-ip-addresses), [Dataretentie](data-governance.md#data-retention) en [Grensoverschrijdende dataoverdrachten](data-governance.md#data-transfers).

## IP-adressen verzamelen en onzichtbaar maken {#collecting-ip-addresses}

Het [!DNL IP]-adres van een bezoeker van een klantwebsite wordt verzonden naar een Adobe [!DNL Data Processing Center] ([!DNL DPC]) waar het [!DNL IP]-adres mogelijk wordt opgeslagen. Afhankelijk van de netwerkconfiguratie voor de bezoeker hoeft het [!DNL IP]-adres niet per se het [!DNL IP]-adres van de computer van de bezoeker te zijn. Het [!DNL IP]-adres kan bijvoorbeeld het externe [!DNL IP]-adres van een NAT-firewall (Network Address Translation) zijn, een [!DNL HTTP]-proxy of een internetgateway.

**Methode voor IP-onzichtbaarmaking:** volgens de principes van “Privacy by Design” kunnen klanten in Adobe Audience Manager [!DNL IP]-onzichtbaarmaking inschakelen vanuit de gebruikersinterface, zowel wereldwijd voor alle geografische regio’s als voor specifieke landen. Wanneer u deze instelling inschakelt, wordt het laatste octet (het laatste gedeelte) van het [!DNL IP]-adres onmiddellijk verwijderd wanneer het [!DNL IP]-adres in Audience Manager wordt opgenomen. Audience Manager verwijdert dit deel van het [!DNL IP]-adres voordat het wordt verwerkt (nog vóór een eventuele geografische zoekopdracht of registratie van het [!DNL IP]-adres). Bijvoorbeeld:

* Voor: `255.255.255.255`
* Na: `255.255.255.0`

>[!NOTE]
>
>Zie [IP de Obfuscatie van het Adres](../../features/administration/ip-obfuscation.md) leren hoe u [!DNL IP] adresverwarring in de gebruikersinterface van de Audience Manager.

Bekijk de onderstaande video om te begrijpen hoe het onzichtbaar maken van [!DNL IP]-adressen in Audience Manager werkt.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geografische segmentatie:** als u onzichtbaarmaking van [!DNL IP]-adressen inschakelt, kunnen de resterende octetten van het [!DNL IP]-adres nog steeds worden gebruikt voor geosegmentatie en rapportage in Audience Manager. Als u onzichtbaarmaking van [!DNL IP]-adressen niet inschakelt, gebruikt Audience Manager het volledige [!DNL IP]-adres. U kunt de functie voor geografische segmentatie gebruiken waarmee u in beide gevallen een [!DNL IP]-locatie per geografische regio kunt identificeren, waarbij de precisie echter enigszins afneemt wanneer [!DNL IP]-onzichtbaarmaking wordt gebruikt. Het verkrijgen van informatie op plaatsniveau wordt waarschijnlijk sterk beïnvloed door onzichtbaarmaking van [!DNL IP]-adressen. Het verkrijgen van informatie op regionaal en nationaal niveau zal maar weinig worden beïnvloed. De data van geografische segmentatie zijn alleen granulair op het niveau van steden of postcodes, niet op individueel niveau. Lees meer over [geotargeting](../../features/traits/trait-geotarget-keys.md) en hoe u eigenschappen met geografische variabelen instelt.

## Dataretentie in Audience Manager {#data-retention}

Het toepassen van een geschikt, veilig en tijdig dataretentiebeleid is een belangrijk onderdeel van de naleving van de voorschriften voor dataprivacy. Audience Manager-klanten kunnen aangepaste retentieperioden instellen op eigenschappen en segmenten door de vereiste TTL (Time To Live) in te stellen. Zie [Veelgestelde vragen over dataretentie](../../faq/faq-privacy.md) voor meer details over retentieperioden.

## Grensoverschrijdende dataoverdrachten {#data-transfers}

Wanneer Audience Manager persoonlijke data van klanten over nationale grenzen overdraagt, gebeurt dit in overeenstemming met het toepasselijke recht. Ga naar het [Adobe Privacy Center](https://www.adobe.com/nl/privacy/eudatatransfers.html) voor meer informatie.
