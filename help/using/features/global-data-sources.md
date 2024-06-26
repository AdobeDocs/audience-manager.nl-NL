---
description: Globale gegevensbronnen gebruiken om apparaat-advertentie-id's te importeren.
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: Algemene databronnen
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '448'
ht-degree: 3%

---

# Algemene databronnen {#global-data-sources}

## Overzicht

Algemene gegevensbronnen zijn toegankelijk voor alle klanten van de Audience Manager en bevatten id&#39;s voor apparaatreclame die worden gegenereerd door apparaatfabrikanten zoals [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku], en [!DNL Android] fabrikanten van apparaten. Deze id&#39;s worden door de fabrikanten beschikbaar gesteld voor reclamedoeleinden. Klanten van Audience Managers kunnen globale gegevensbronnen gebruiken om apparaat-id&#39;s te synchroniseren en gegevens die van die toewijzingen zijn afgehaald, te importeren of te exporteren.

In de volgende tabel worden de algemene gegevensbronnen beschreven die door Audience Manager worden ondersteund.

| Gegevensbron-id | Beschrijving |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** IDs vertegenwoordigt apparaten die in werking stellen [!DNL Android] besturingssysteem. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** IDs vertegenwoordigt apparaten die in werking stellen [!DNL iOS] besturingssysteem. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** ID&#39;s vertegenwoordigen [!DNL Roku] streaming apparaten. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** Id&#39;s vertegenwoordigen apparaten waarop de [!DNL Windows 10] besturingssysteem. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** ID&#39;s vertegenwoordigen [!DNL Samsung] slimme tv&#39;s. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** vertegenwoordigen apparaten die [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** vertegenwoordigen apparaten die [!DNL LG webOS] besturingssysteem. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** vertegenwoordigen apparaten waarop Vizio smart TV-besturingssystemen worden uitgevoerd. |

## Gegevens uit globale gegevensbronnen importeren

U kunt apparaat-id&#39;s uit algemene gegevensbronnen importeren via beide [realtime gegevensoverdracht](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) en [batchgegevensoverdracht](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md).

>[!IMPORTANT]
>
>Wanneer u gegevens naar de Audience Manager verzendt met een algemene apparaat-id, moet u ervoor zorgen dat u de bijbehorende gegevensbron voor de desbetreffende apparaat-id gebruikt. Voorbeeld: om gegevens te importeren voor [!DNL Apple IDFA], gebruikt u de gegevensbron-id 20915.

## Beperkingen

Op apparaten die [!DNL iOS] en [!DNL Android] besturingssystemen, kunnen alleen native toepassingen advertenties-id&#39;s voor apparaten ophalen en gebruiken ([!UICONTROL DAID]s). Webtoepassingen die in mobiele browsers worden uitgevoerd, hebben geen toegang tot advertentie-id&#39;s voor apparaten.

## Validatie van algemene apparaat-id

Audience Manager valideert de advertentie-id&#39;s van het apparaat ([!UICONTROL DAID]) die door klanten worden geïmporteerd op basis van hun indeling, om ervoor te zorgen dat ze overeenkomen met het standaardformaat dat door apparaatfabrikanten wordt beschreven. Zie [Index van id&#39;s in Audience Manager](../reference/ids-in-aam.md) voor een gedetailleerde toewijzing van apparaat advertentie-id&#39;s aan globale gegevensbronnen en de juiste indeling voor elke id. Zorg ervoor dat u apparaat-id&#39;s in de juiste indeling importeert op basis van het apparaattype. Audience Manager wijst apparaat-id&#39;s af die niet aan de juiste indeling voldoen en retourneert een foutbericht om aan te geven dat de id is afgewezen.

* Foutberichten voor batchgegevensoverdracht worden hier beschreven: [Voorwaarden en definities van het rapport betreffende de status van het aan boord nemen](../reporting/onboarding-status-report.md#report-terms-conditions).
* Het overseinen van de fout voor gegevensoverdrachten in real time wordt hier geschetst: [DCS-foutcodes, berichten en voorbeelden](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Expiratiebeleid voor apparaat-id

Audience Manager verwijdert automatisch id&#39;s voor apparaatreclame na 120 dagen inactiviteit, vergelijkbaar met [AAM UUID](../faq/faq-privacy.md)s.

## Nieuwe globale gegevensbronnen aanvragen

Om nieuwe globale gegevensbronnen te verzoeken om aan Audience Manager te worden toegevoegd, contacteer de Raadpleging van de Adobe of Adobe de Zorg van de Klant en verstrek gedetailleerde informatie over de vereiste gegevensbronnen:

* De naam van het gevraagde platform (bv. [!UICONTROL Apple IDFA]);
* De naam van het bedrijf/de organisatie die het platform beheert (bv. [!UICONTROL Apple Inc.]);
* Koppelingen naar de technische specificaties voor de naamruimte van de advertentie-id voor het apparaat (bv. [AdSupport-documentatie](https://developer.apple.com/documentation/adsupport)).
