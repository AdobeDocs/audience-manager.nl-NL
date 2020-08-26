---
description: Globale gegevensbronnen gebruiken om apparaat-advertentie-id's te importeren.
seo-description: Globale gegevensbronnen gebruiken om apparaat-advertentie-id's te importeren.
seo-title: Algemene databronnen
solution: Audience Manager
title: Algemene databronnen
feature: Data Sources
translation-type: tm+mt
source-git-commit: b8b848ad04d1ec07c12e57d94e4f3c6e672dc102
workflow-type: tm+mt
source-wordcount: '444'
ht-degree: 3%

---


# Algemene databronnen {#global-data-sources}

## Overzicht

Algemene gegevensbronnen zijn toegankelijk voor alle klanten van de Audience Manager en bevatten id&#39;s voor apparaatreclame die worden gegenereerd door apparaatfabrikanten zoals [!DNL Apple], [!DNL Samsung], [!DNL Microsoft], [!DNL Roku]en [!DNL Android] apparaatfabrikanten. Deze id&#39;s worden door de fabrikanten beschikbaar gesteld voor reclamedoeleinden. Klanten van Audience Managers kunnen globale gegevensbronnen gebruiken om apparaat-id&#39;s te synchroniseren en gegevens die van die toewijzingen zijn afgehaald, te importeren of te exporteren.

In de volgende tabel worden de algemene gegevensbronnen beschreven die door Audience Manager worden ondersteund.

| Gegevensbron-id | Beschrijving |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** Id&#39;s zijn apparaten die het [!DNL Android] besturingssysteem uitvoeren. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** Id&#39;s zijn apparaten die het [!DNL iOS] besturingssysteem uitvoeren. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** ID&#39;s vertegenwoordigen [!DNL Roku] streamingapparaten. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** Id&#39;s zijn apparaten waarop het [!DNL Windows 10] besturingssysteem wordt uitgevoerd. |
| 404660 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** ID&#39;s zijn [!DNL Samsung] slimme tv&#39;s. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** vertegenwoordigen apparaten die [!DNL Amazon Fire OS] |

## Gegevens uit globale gegevensbronnen importeren

U kunt apparaat-id&#39;s van globale gegevensbronnen importeren via gegevensoverdracht [in](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) realtime en gegevensoverdracht [in](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md)batch.

>[!IMPORTANT]
>
>Wanneer u gegevens naar de Audience Manager verzendt met een algemene apparaat-id, moet u ervoor zorgen dat u de bijbehorende gegevensbron voor de desbetreffende apparaat-id gebruikt. Voorbeeld: Gebruik de gegevensbron-id 20915 om gegevens te importeren voor [!DNL Apple IDFA].

## Beperkingen

Op apparaten met [!DNL iOS] en [!DNL Android] besturingssystemen kunnen alleen native toepassingen adverteren-id&#39;s ([!UICONTROL DAID]s) voor apparaten ophalen en gebruiken. Webtoepassingen die in mobiele browsers worden uitgevoerd, hebben geen toegang tot advertentie-id&#39;s voor apparaten.

## Validatie van algemene apparaat-id

Audience Manager valideert de door klanten geïmporteerde advertentie-id&#39;s ([!UICONTROL DAID]) voor het apparaat op basis van hun indeling, zodat deze overeenkomen met de standaardindeling die door apparaatfabrikanten wordt beschreven. Zie [Index van IDs in Audience Manager](../reference/ids-in-aam.md) voor een gedetailleerde afbeelding van apparaat reclame IDs aan globale gegevensbronnen en het juiste formaat voor elke identiteitskaart Zorg ervoor dat u apparaat-id&#39;s in de juiste indeling importeert op basis van het apparaattype. Audience Manager wijst apparaat-id&#39;s af die niet aan de juiste indeling voldoen en retourneert een foutbericht om aan te geven dat de id is afgewezen.

* Foutberichten voor batchgegevensoverdracht worden hier beschreven: [Voorwaarden en definities](../reporting/onboarding-status-report.md#report-terms-conditions)van statusrapport bij instapweigering.
* Het overseinen van de fout voor gegevensoverdrachten in real time wordt hier geschetst: [DCS-foutcodes, -berichten en -voorbeelden](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Expiratiebeleid voor apparaat-id

Audience Manager verwijdert automatisch id&#39;s voor apparaatreclame na 120 dagen inactiviteit, vergelijkbaar met [AAM](../faq/faq-privacy.md)UUID&#39;s.

## Nieuwe globale gegevensbronnen aanvragen

Om nieuwe globale gegevensbronnen te verzoeken om aan Audience Manager te worden toegevoegd, contacteer de Raadpleging van de Adobe of Adobe de Zorg van de Klant en verstrek gedetailleerde informatie over de vereiste gegevensbronnen:

* de naam van het gevraagde platform (bv. [!UICONTROL Apple IDFA]);
* de naam van de onderneming/organisatie die het platform beheert (bv. [!UICONTROL Apple Inc.]);
* Koppelingen naar de technische specificaties voor de naamruimte van advertentie-id voor het apparaat (bijvoorbeeld [AdSupport-documentatie](https://developer.apple.com/documentation/adsupport)).