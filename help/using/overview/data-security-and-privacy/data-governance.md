---
description: In dit document wordt uitgelegd hoe klantgegevens worden beheerd in Audience Manager.
seo-description: In dit document wordt uitgelegd hoe klantgegevens worden beheerd in Audience Manager.
seo-title: Gegevensbeheer
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent, obfuscation, governance
title: Gegevensbeheer
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# Gegevensbeheer

## Overzicht {#overview}

Gegevensbeheer in Audience Manager verwijst naar de levenscyclus van uw klantengegevens in de Manager van de Audience, en het omvat het [Verzamelen van en het Verduisteren van IP Adressen](data-governance.md#collecting-ip-addresses), het Behouden [van](data-governance.md#data-retention)Gegevens, en de [Grensoverschrijdende Overdrachten](data-governance.md#data-transfers)van Gegevens.

## Het verzamelen van IP Adressen en IP de Obfuscatie van het Adres {#collecting-ip-addresses}

Het [!DNL IP] adres van een bezoeker van de website van een klant wordt verzonden naar Adobe [!DNL Data Processing Center] ([!DNL DPC]) waar het [!DNL IP] adres kan worden opgeslagen. Afhankelijk van de netwerkconfiguratie voor de bezoeker, kan het [!DNL IP] adres niet noodzakelijk het [!DNL IP] adres van de computer van de bezoeker vertegenwoordigen. Bijvoorbeeld, zou het [!DNL IP] adres het externe [!DNL IP] adres van een firewall van het Adres van het Netwerk (NATIONAAL), [!DNL HTTP] volmacht, of de gateway van Internet kunnen zijn.

**IP Obfuscation Methodology:** Volgens de beginselen van &quot;Privacy door Ontwerp&quot; staat Adobe Audience Manager klanten toe om [!DNL IP] verwarring vanuit de gebruikersinterface mogelijk te maken, globaal voor alle geografische regio&#39;s of voor specifieke landen. Wanneer u deze het plaatsen toelaat, wordt het laatste octet (het laatste gedeelte) van het [!DNL IP] adres onmiddellijk verworpen wanneer het [!DNL IP] adres in de Manager van de Publiek wordt opgenomen. Audience Manager negeert dit deel van het [!DNL IP] adres voorafgaand aan verwerking (met inbegrip van vóór om het even welke facultatieve geografische raadpleging of registreren van het [!DNL IP] adres). Bijvoorbeeld:

* Voor: `255.255.255.255`
* Na: `255.255.255.0`

>[!NOTE]
>
>Zie [IP de Obfuscatie](../../features/administration/ip-obfuscation.md) van het Adres leren hoe te om [!DNL IP] adresverwarring in de Manager UI van de Publiek toe te laten.

Bekijk de video hieronder om te begrijpen hoe [!DNL IP] adresverwarring werkt in Audience Manager.

>[!VIDEO](https://video.tv.adobe.com/v/27218/)

**Geografische segmentatie:** Als u [!DNL IP] adresverwarring toelaat, kunnen de resterende octetten van het [!DNL IP] adres nog voor geo-segmentatie en rapportering in de Manager van het Publiek worden gebruikt. Als u [!DNL IP] adresverwarring niet toelaat, gebruikt de Manager van de Publiek het volledige [!DNL IP] adres. U kunt de functie Geografische segmentatie gebruiken waarmee u in beide gevallen een [!DNL IP] locatie per geografisch gebied kunt identificeren, maar waarbij de precisie enigszins afneemt wanneer [!DNL IP] verduistering wordt gebruikt. Het verkrijgen van informatie op het niveau van de stad zal waarschijnlijk aanzienlijk worden beïnvloed door de verduistering van het [!DNL IP] adres. Het verkrijgen van informatie op regionaal en nationaal niveau mag slechts een klein effect hebben. De geografische segmentatiegegevens worden alleen in korreligheid uitgedrukt op het niveau van de stad of de postcode, en niet op individueel niveau. Lees meer over [geotargeting](../../features/traits/trait-geotarget-keys.md) en hoe u eigenschappen met geografische variabelen instelt.

## Bewaring van gegevens in Audience Manager {#data-retention}

Het toepassen van een passend, veilig en tijdig beleid voor het bewaren van gegevens op uw gegevens is een belangrijk onderdeel van het naleven van de privacyregels voor gegevens. De Klanten van de Manager van het publiek hebben de capaciteit om de periodes van het douanebehoud op eigenschappen en segmenten te plaatsen door vereiste TTL (tijd te bepalen om te leven). Zie Veelgestelde vragen over [gegevensbewaring](../../faq/faq-privacy.md) voor meer informatie over bewaartermijnen.

## Grensoverschrijdende gegevensoverdracht {#data-transfers}

Wanneer Audience Manager persoonlijke gegevens van klanten over de nationale grenzen overdraagt, doet de Audience Manager dit in overeenstemming met het toepasselijke recht. Ga naar het [Adobe Privacy Center](https://www.adobe.com/privacy/eudatatransfers.html) voor meer informatie.