---
description: Raadpleeg dit document voor de volledige lijst met Adobe Audience Manager-id's.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Raadpleeg dit document voor de volledige lijst met Adobe Audience Manager-id's.
seo-title: Index van id's in Audience Manager
solution: Audience Manager
title: Index van id's in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: reference
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '944'
ht-degree: 0%

---


# Index van id&#39;s in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Overzicht {#overview}

[!DNL Audience Manager] gebruikt meerdere id&#39;s om de gegevens te identificeren en te beheren die u ernaar verzendt. Raadpleeg dit artikel voor de volledige lijst met [!DNL Audience Manager] id&#39;s, samen met voorbeelden van de voorvoegsels waarmee u deze kunt gebruiken.

## ID vooraf bepalen {#prefixing}

Terwijl u naar de meeste van deze IDs door hun standalone namen kunt verwijzen, moeten de meesten van hen met diverse prefixen worden gebruikt, wanneer het overgaan in gegevens door [!DNL DCS] vraag. Sommige van deze id&#39;s worden gebruikt door [!DNL Audience Manager] en worden niet aan gebruikers weergegeven, terwijl andere ook zichtbaar zijn in de gebruikersinterface (UI).

Om de prefixen te begrijpen die in de volgende voorbeelden worden gebruikt, zie [Gesteunde Attributen voor Vraag](../api/dcs-intro/dcs-api-reference/dcs-keys.md)DCS API.

## [!DNL Audience Manager] Lijst met id&#39;s {#id-list}

| ID | Naam en beschrijving | Gebruik en voorbeelden | Locatie gebruikersinterface |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], ook bekend als [!UICONTROL Device ID]. Een numerieke, 38-cijferige apparaat-id die [!DNL Audience Manager] aan elk apparaat wordt gekoppeld waarmee het werkt. Denk aan deze id wanneer u een vermelding van unieke gebruikers in de [!DNL Audience Manager] gebruikersinterface ziet. Audience Manager slaat deze id als een [!DNL cookie] bestand op in het domein van `demdex.net` derden. | In [!DNL DCS] vraag, `uuid` wordt voorafgegaan door de `d_` prefix. <br>Voorbeeld: `d_uuid = 07955261652886032950143702505894272138` | U kunt filteren [!DNL traits] door [!UICONTROL Device ID] wanneer het creëren van [blik-Vergelijkbare Modellen](../features/algorithmic-models/create-model.md), en het [bouwen van segmenten](../features/segments/segment-builder.md). U kunt resultaten door ook filtreren [!UICONTROL Device ID] wanneer het runnen van [Algemene Rapporten voor Tanden](../reporting/general-reports.md) en de Rapporten van de [Trend voor Tanden](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Dit is de id waarmee een bedrijf wordt geconfronteerd wanneer het zich aanmeldt voor een [!DNL Experience Cloud] account. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Niet zichtbaar in de [!DNL Audience Manager] gebruikersinterface. Als u wilt weten hoe u de bedrijfsnaam kunt vinden [!DNL Organization ID], leest u [Zoeken naar uw organisatie-id](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. Het [!DNL PID] is de id van een bedrijf in [!DNL Audience Manager]. Audience Manager associeert een [!DNL imsOrgId] aan een [!DNL PID]. | `1352` | Niet zichtbaar in de [!DNL Audience Manager] gebruikersinterface. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. De [!DNL Experience Cloud] id ([!DNL ECID], verouderde afkortingen [!DNL MID] of [!DNL MCID]) wordt wiskundig afgeleid van uw [!DNL Organization ID] en de [!DNL Audience Manager] [!UICONTROL Unique User ID]. Zolang deze IDs constant blijft, is het produceren van het recht [!DNL ECID] voor een specifieke gebruiker eenvoudig een wiskundeprobleem. Met dezelfde [!DNL Organization ID] waarde krijgt [!DNL Audience Manager] u telkens dezelfde [!DNL UUID] [!DNL ECID] waarde. U kunt meer informatie lezen over de inhoud [!DNL ECID] in de documentatie bij [Cookies en Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Niet zichtbaar in de [!DNL Audience Manager] gebruikersinterface. |
| [!DNL SID] | [!UICONTROL Trait ID]. De [!UICONTROL Trait ID] unieke identificatie [!DNL traits] in de [!DNL Audience Manager] omgeving. | In [!DNL DCS] vraag, `SID` wordt voorafgegaan door de `d_` prefix. <br>Voorbeeld `d_sid=289983`. | Aan elke sectie [!UICONTROL Trait ID] wordt een status toegewezen [!DNL trait]die zichtbaar is in de gebruikersinterface, op de pagina [Traits](../features/traits/trait-details-page.md) . |
| [!DNL SID] | [!UICONTROL Segment ID]. De [!UICONTROL Segment ID] unieke identificatie [!DNL segments] in de [!DNL Audience Manager] omgeving. | In [!DNL DCS] vraag, `SID` wordt voorafgegaan door de `d_` prefix. <br>Voorbeeld `d_sid=4798574`. | Een [!UICONTROL Segment ID] wordt toegewezen aan elk [!DNL segment], en zichtbaar in het gebruikersinterface, op de pagina van [Segmenten](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Deze id identificeert op unieke wijze segmenten in de [!DNL Audience Manager] omgeving. | `741232` | Een [!UICONTROL Legacy Segment ID] wordt toegewezen aan elk segment, en zichtbaar in het gebruikersinterface, op de pagina van [Segmenten](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | [!UICONTROL Destination ID]. De [!UICONTROL Destination ID] unieke identificatie [!DNL destinations] in de [!DNL Audience Manager] omgeving. Aan elke id wordt een id toegewezen [!DNL destination] in de gebruikersinterface. | `2523` | Een [!UICONTROL Destination ID] wordt toegewezen aan elk [!DNL destination], en zichtbaar in het gebruikersinterface, op de pagina van [Doelen](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | [!UICONTROL Data Source ID] (ook wel [!UICONTROL Data Provider ID]) genoemd. Dit [!UICONTROL Data Source ID] is een naamruimte voor id&#39;s of [!DNL traits]. Er wordt een id toegewezen aan elke [!DNL data source] (gegevensaanbieder) in de gebruikersinterface. | In [!DNL DCS] vraag, `dpid` wordt voorafgegaan door de `d_` prefix. <br>Voorbeeld: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] wordt toegewezen aan elk [!DNL data source], en zichtbaar in het gebruikersinterface, in de pagina van [Gegevensbronnen](../features/datasources-list-and-settings.md) . |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], ook wel [!DNL CRM ID] of [!UICONTROL Cross-Device ID]genoemd. Een id van een derde. Dit is identiteitskaart waarmee u eind - gebruikers in uw eigen [!DNL CRM] systeem identificeert. U kunt synchroniseren [!DNL DPUUIDs] met [!DNL Audience Manager] en u kunt [!DNL UUIDs] vanuit uw andere [!DNL DPUUIDs] ( [!UICONTROL Data Sources][!DNL DPIDs]) id synchroniseren. | In [!DNL DCS] vraag, `dpuuid` wordt voorafgegaan door de `d_` prefix. <br> Voorbeeld `d_dpuuid=2132-3423vn-343fds-3432r`. | U kunt filteren [!DNL traits] door [!UICONTROL Cross-Device ID] wanneer het creëren van [blik-Vergelijkbare Modellen](../features/algorithmic-models/create-model.md), en het [bouwen van segmenten](../features/segments/segment-builder.md). U kunt resultaten door ook filtreren [!UICONTROL Cross-Device ID] wanneer het runnen van [Algemene Rapporten voor Tanden](../reporting/general-reports.md) en de Rapporten van de [Trend voor Tanden](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Zie `DPUUID`. | Zie `DPUUID`. | Zie `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. De [!DNL CID] en [!DNL CID_IC] sleutel-waarde paren vervangen [!DNL DPID] en [!DNL DPUUID]. Zij verstrekken de zelfde functies zoals [!DNL DPID] en [!DNL DPUUID], maar zijn efficiënter omdat zij identiteitskaart van de gegevensleverancier en gebruiker - identiteitskaart (of integratiecode) in één enkel zeer belangrijk-waardepaar omvatten. | In [!DNL DCS] vraag, worden deze IDs voorafgegaan door de `d_` prefix. <br>Voorbeeld: `d_cid_ic=39217_myIntegrationCode`. | Zie `DPID` en `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Een unieke id voor elk hardwareapparaat voor reclamedoeleinden. Meestal verstrekt door de fabrikant van het apparaat of het besturingssysteem. | Zie [Algemene apparaat-id&#39;s](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Algemene apparaat-id&#39;s zijn apparaat-advertentie-id&#39;s die uniek zijn voor elk apparaat en die worden geleverd door de fabrikant van het apparaat of het besturingssysteem. In de onderstaande tabel wordt uitgelegd wat deze id&#39;s zijn en wat hun indeling is. Voor meer informatie over globale apparaat IDs en hoe te om hen in te gebruiken, lees [!DNL Audience Manager]Globale Gegevensbronnen [](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Naam en beschrijving | Voorbeeld |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Id&#39;s zijn id&#39;s voor mobiele apparaten die worden geleverd door de fabrikant van het apparaat. Deze id&#39;s vertegenwoordigen apparaten die het [!DNL iOS] besturingssysteem uitvoeren. | De opmaak bestaat strikt uit 32 hexadecimale hoofdletters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens.<br> Voorbeeld: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s zijn id&#39;s voor mobiele apparaten die worden geleverd door fabrikanten van Android-apparaten. Deze id&#39;s vertegenwoordigen apparaten die het [!DNL Android] besturingssysteem uitvoeren. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] vertegenwoordigen [!DNL Roku] streamingapparaten. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s is apparaat-id&#39;s die per apparaat en per gebruiker worden gegenereerd. [!DNL Windows 10] | [!DNL MAID]s worden opgemaakt als alfanumerieke tekenreeksen. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s zijn apparaat-id&#39;s die worden geleverd door [!DNL Samsung] slimme tv&#39;s. | [!DNL Samsung] [!DNL DUID]s worden opgemaakt als alfanumerieke tekenreeksen. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Apparaatid&#39;s die apparaten vertegenwoordigen waarop het [!DNL Fire OS] besturingssysteem wordt uitgevoerd. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |