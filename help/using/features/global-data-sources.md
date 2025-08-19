---
description: Globale gegevensbronnen gebruiken om id's voor apparaatreclame te importeren.
seo-description: Use Global Data Sources to import device advertising IDs.
seo-title: Global Data Sources
solution: Audience Manager
title: Algemene gegevensbronnen
feature: Data Sources
exl-id: ef137f89-1e1a-4cc0-8864-8a84162581c1
source-git-commit: 77daa5bd6545914f65e3e0f19b12c750535244e8
workflow-type: tm+mt
source-wordcount: '447'
ht-degree: 2%

---

# Algemene gegevensbronnen {#global-data-sources}

## Overzicht

Algemene gegevensbronnen zijn toegankelijk voor alle Audience Manager-klanten en bevatten apparaatadvertentie-id&#39;s die zijn gegenereerd door apparaatfabrikanten zoals [!DNL Apple] , [!DNL Samsung] , [!DNL Microsoft] , [!DNL Roku] en [!DNL Android] . Deze id&#39;s worden door de fabrikanten beschikbaar gesteld voor reclamedoeleinden. Audience Manager-klanten kunnen globale gegevensbronnen gebruiken om apparaat-id&#39;s te synchroniseren en gegevens die van deze toewijzingen zijn afgehaald, te importeren of te exporteren.

In de volgende tabel worden de algemene gegevensbronnen beschreven die door Audience Manager worden ondersteund.

| Source-id voor gegevens | Beschrijving |
|---|---|
| 20914 | **[!DNL Google Advertising ID]** - **[!DNL GAID]** ID&#39;s zijn apparaten die het [!DNL Android] -besturingssysteem uitvoeren. |
| 20915 | **[!DNL Apple ID For Advertising]** - **[!DNL IDFA]** ID&#39;s zijn apparaten die het [!DNL iOS] -besturingssysteem uitvoeren. |
| 121963 | **[!DNL Roku ID for Advertising]** - **[!DNL RIDA]** ID&#39;s vertegenwoordigen [!DNL Roku] streamingapparaten. |
| 389146 | **[!DNL Microsoft Advertising ID]** - **[!DNL MAID]** ID&#39;s vertegenwoordigen apparaten waarop het [!DNL Windows 10] -besturingssysteem wordt uitgevoerd. |
| 963906 | **[!DNL Samsung Tizen IDs for Advertising]** - **[!DNL TIFA]** ID&#39;s vertegenwoordigen [!DNL Samsung] slimme tv&#39;s. |
| 488258 | **[!DNL Amazon Fire TV Advertising IDs]** vertegenwoordigen apparaten die worden uitgevoerd [!DNL Amazon Fire OS] |
| 1171485 | **[!DNL LG webOS TV ID]** - **[!DNL LGUDID]** vertegenwoordigt apparaten waarop het [!DNL LG webOS] -besturingssysteem wordt uitgevoerd. |
| 1171489 | **[!DNL Vizio ID for Advertising]** - **[!DNL IFA]** vertegenwoordigt apparaten waarop Vizio Smart TV-besturingssystemen worden uitgevoerd. |

## Gegevens uit globale gegevensbronnen importeren

U kunt apparaat IDs van globale gegevensbronnen door zowel [ gegevensoverdracht in real time ](../integration/sending-audience-data/real-time-data-integration/real-time-data-transfer.md) als [ partij gegevensoverdracht ](../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-explained.md) invoeren.

>[!IMPORTANT]
>
>Wanneer u gegevens naar Audience Manager verzendt met een algemene apparaat-id, moet u de bijbehorende gegevensbron voor de desbetreffende apparaat-id gebruiken. Voorbeeld: gebruik de gegevensbron-id 20915 om gegevens te importeren voor [!DNL Apple IDFA] .

## Beperkingen

Op apparaten die [!DNL iOS] en [!DNL Android] in werking stellen, slechts kunnen de inheemse toepassingen apparaat reclame IDs ([!UICONTROL DAID] s) terugwinnen en gebruiken. Webtoepassingen die in mobiele browsers worden uitgevoerd, hebben geen toegang tot advertentie-id&#39;s voor apparaten.

## Validatie van algemene apparaat-id

Audience Manager valideert de apparaat advertentie-id&#39;s ([!UICONTROL DAID]) die door klanten zijn geïmporteerd, op basis van hun indeling, om ervoor te zorgen dat deze overeenkomen met de standaardindeling die door apparaatfabrikanten wordt beschreven. Zie [ Index van IDs in Audience Manager ](../reference/ids-in-aam.md) voor een gedetailleerde afbeelding van apparaat reclame IDs aan globale gegevensbronnen en het juiste formaat voor elke identiteitskaart. Zorg ervoor dat u apparaat-id&#39;s in de juiste indeling importeert op basis van het apparaattype. Audience Manager wijst apparaat-id&#39;s die niet aan de juiste indeling voldoen af en retourneert een foutbericht om aan te geven dat de id is afgewezen.

* Het overseinen van de fout voor de overdrachten van partijgegevens wordt hier geschetst: [ Aan boord de Termen en Definities van het Rapport van de Status ](../reporting/onboarding-status-report.md#report-terms-conditions).
* Het overseinen van de fout voor gegevensoverdrachten in real time wordt hier geschetst: [ Codes van de Fout DCS, Berichten, en Voorbeelden ](../api/dcs-intro/dcs-api-reference/dcs-error-codes.md).

## Expiratiebeleid voor apparaat-id

Audience Manager verwerpt automatisch apparaat reclame IDs na 120 dagen van inactiviteit, gelijkend op [ AAM UUID ](../faq/faq-privacy.md) s.

## Nieuwe globale gegevensbronnen aanvragen

Neem contact op met de klantenservice van Adobe Consulting of Adobe om nieuwe wereldwijde gegevensbronnen aan Audience Manager toe te voegen en geef gedetailleerde informatie over de vereiste gegevensbronnen:

* de naam van het gevraagde platform (bv. [!UICONTROL Apple IDFA]);
* de naam van het bedrijf/de organisatie die het platform beheert (bijvoorbeeld [!UICONTROL Apple Inc.]);
* Verbindingen met de technische specificaties voor het apparaat reclame ID namespace (b.v., [ Documentatie AdSupport ](https://developer.apple.com/documentation/adsupport)).
