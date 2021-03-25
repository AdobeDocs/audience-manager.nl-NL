---
description: Raadpleeg dit document voor de volledige lijst met Adobe Audience Manager-id's.
keywords: DPID; DPUUID; CID; UUID; uuuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid, uuid
seo-description: Raadpleeg dit document voor de volledige lijst met Adobe Audience Manager-id's.
seo-title: Index van id’s in Audience Manager
solution: Audience Manager
title: Index van id’s in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: referentie
translation-type: tm+mt
source-git-commit: 5abb131966e0b27e6c628ff992c4c30b89f65ae9
workflow-type: tm+mt
source-wordcount: '965'
ht-degree: 3%

---


# Index van id&#39;s in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Overzicht {#overview}

[!DNL Audience Manager] gebruikt meerdere id&#39;s om de gegevens te identificeren en te beheren die u ernaar verzendt. Raadpleeg dit artikel voor de volledige lijst met [!DNL Audience Manager] id&#39;s, samen met voorbeelden van de voorvoegsels waarmee u deze kunt gebruiken.

## Id-voorvoegsel {#prefixing}

Terwijl u naar de meeste van deze IDs door hun standalone namen kunt verwijzen, moeten de meesten van hen met diverse prefixen worden gebruikt, wanneer het overgaan in gegevens door [!DNL DCS] vraag. Sommige van deze id&#39;s worden door [!DNL Audience Manager] gebruikt zonder aan gebruikers te worden blootgesteld, terwijl andere ook zichtbaar zijn in de gebruikersinterface (UI).

Om de prefixen te begrijpen die in de volgende voorbeelden worden gebruikt, zie [Gesteunde Attributen voor Vraag DCS API](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Lijst met id&#39;s  {#id-list}

| ID | Naam en beschrijving | Gebruik en voorbeelden | Locatie gebruikersinterface |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], ook bekend als  [!UICONTROL Device ID]. Een numerieke apparaat-id van 38 cijfers waarmee [!DNL Audience Manager] is gekoppeld aan elk apparaat waarmee het werkt. Denk aan deze id wanneer u een vermelding van unieke gebruikers ziet in de interface [!DNL Audience Manager]. Audience Manager slaat deze id op als een [!DNL cookie] in het `demdex.net` domein van derden. | In [!DNL DCS] vraag, wordt `uuid` voorafgegaan door `d_` prefix. <br>Voorbeeld: `d_uuid = 07955261652886032950143702505894272138` | U kunt [!DNL traits] door [!UICONTROL Device ID] filtreren wanneer het creëren van [look-Alike Modellen](../features/algorithmic-models/create-model.md), en [bouwsegmenten](../features/segments/segment-builder.md). U kunt resultaten door [!UICONTROL Device ID] ook filtreren wanneer het lopen [Algemene Rapporten voor Tanden](../reporting/general-reports.md) en [Tendrapporten voor Tanden](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Dit is de id die een bedrijf bij het aanmelden voor een [!DNL Experience Cloud]-account krijgt. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Niet zichtbaar in [!DNL Audience Manager] gebruikersinterface. Lees [Zoek uw organisatie-id](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255) voor meer informatie over hoe u [!DNL Organization ID] van uw bedrijf kunt vinden. |
| [!DNL PID] | [!DNL Partner ID]. De [!DNL PID] is een bedrijfs-id in [!DNL Audience Manager]. Audience Manager koppelt een [!DNL imsOrgId] aan een [!DNL PID]. | `1352` | Niet zichtbaar in [!DNL Audience Manager] gebruikersinterface. |
| [!DNL ECID],  [!DNL MID] | [!DNL Experience Cloud] ID. De [!DNL Experience Cloud]-id ([!DNL ECID], verouderde afkortingen [!DNL MID] of [!DNL MCID]) wordt wiskundig afgeleid van uw [!DNL Organization ID] en [!DNL Audience Manager] [!UICONTROL Unique User ID]. Zolang deze id&#39;s constant blijven, is het genereren van de juiste [!DNL ECID] voor een specifieke gebruiker gewoon een wiskundig probleem. Met dezelfde [!DNL Organization ID] en [!DNL Audience Manager] [!DNL UUID] krijgt u telkens dezelfde [!DNL ECID]-waarde. U kunt meer over [!DNL ECID] in [Cookies en Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) documentatie lezen. | `mid = 08382830887934830189014177072406221371` | Niet zichtbaar in [!DNL Audience Manager] gebruikersinterface. |
| [!DNL SID] | [!UICONTROL Trait ID]. [!UICONTROL Trait ID] identificeert [!DNL traits] uniek in [!DNL Audience Manager] milieu. | In [!DNL DCS] vraag, wordt `SID` voorafgegaan door `d_` prefix. <br>Voorbeeld `d_sid=289983`. | Een [!UICONTROL Trait ID] wordt toegewezen aan elke [!DNL trait], en zichtbaar in het gebruikersinterface, op [Traits](../features/traits/trait-details-page.md) pagina. |
| [!DNL SID] | [!UICONTROL Segment ID]. [!UICONTROL Segment ID] identificeert [!DNL segments] uniek in [!DNL Audience Manager] milieu. | In [!DNL DCS] vraag, wordt `SID` voorafgegaan door `d_` prefix. <br>Voorbeeld `d_sid=4798574`. | Een [!UICONTROL Segment ID] wordt toegewezen aan elke [!DNL segment], en zichtbaar in het gebruikersinterface, op [de pagina van Segmenten](../features/segments/segment-summary-view.md). |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Deze id identificeert op unieke wijze segmenten in de [!DNL Audience Manager]-omgeving. | `741232` | Een [!UICONTROL Legacy Segment ID] wordt toegewezen aan elk segment, en zichtbaar in het gebruikersinterface, in [Segmenten](../features/segments/segment-summary-view.md) pagina. |
| [!DNL destID] | [!UICONTROL Destination ID]. [!UICONTROL Destination ID] identificeert [!DNL destinations] uniek in [!DNL Audience Manager] milieu. Een id wordt toegewezen aan elke [!DNL destination] in de gebruikersinterface. | `2523` | Een [!UICONTROL Destination ID] wordt toegewezen aan elke [!DNL destination], en zichtbaar in het gebruikersinterface, op [Doelen](../features/destinations/destinations-home.md) pagina. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (ook wel  [!UICONTROL Data Provider ID]) genoemd. De [!UICONTROL Data Source ID] is een naamruimte voor id&#39;s of [!DNL traits]. Er wordt een id toegewezen aan elke [!DNL data source] (gegevensaanbieder) in de gebruikersinterface. | In [!DNL DCS] vraag, wordt `dpid` voorafgegaan door `d_` prefix. <br>Voorbeeld: `d_dpid=39217`. | Een [!UICONTROL Data Provider ID] wordt toegewezen aan elke [!DNL data source], en zichtbaar in het gebruikersinterface, in [Gegevensbronnen](../features/datasources-list-and-settings.md) pagina. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], ook wel  [!DNL CRM ID] of  [!UICONTROL Cross-Device ID]. Een id van een derde. Dit is identiteitskaart waardoor u eind - gebruikers in uw eigen [!DNL CRM] systeem identificeert. U kunt [!DNL DPUUIDs] met [!DNL Audience Manager] [!DNL UUIDs] synchroniseren en u kunt [!DNL DPUUIDs] van uw verschillende [!UICONTROL Data Sources] ([!DNL DPIDs]) in het proces van de synchronisatie van identiteitskaart synchroniseren. | In [!DNL DCS] vraag, wordt `dpuuid` voorafgegaan door `d_` prefix. <br> Voorbeeld `d_dpuuid=2132-3423vn-343fds-3432r`. | U kunt [!DNL traits] door [!UICONTROL Cross-Device ID] filtreren wanneer het creëren van [look-Alike Modellen](../features/algorithmic-models/create-model.md), en [bouwsegmenten](../features/segments/segment-builder.md). U kunt resultaten door [!UICONTROL Cross-Device ID] ook filtreren wanneer het lopen [Algemene Rapporten voor Tanden](../reporting/general-reports.md) en [Tendrapporten voor Tanden](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Zie `DPUUID`. | Zie `DPUUID`. | Zie `DPUUID`. |
| [!DNL CID],  [!DNL CID_IC] | [!UICONTROL Customer ID],  [!UICONTROL Customer ID Integration Code]. De sleutel-waardeparen [!DNL CID] en [!DNL CID_IC] vervangen [!DNL DPID] en [!DNL DPUUID]. Zij verstrekken de zelfde functies zoals [!DNL DPID] en [!DNL DPUUID], maar zijn efficiënter omdat zij gegevensleverancier identiteitskaart en gebruiker - identiteitskaart (of integratiecode) in één enkel zeer belangrijk-waardepaar omvatten. | In [!DNL DCS] vraag, worden deze IDs voorafgegaan door `d_` prefix. <br>Voorbeeld: `d_cid_ic=39217_myIntegrationCode`. | Zie `DPID` en `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Een unieke id voor elk hardwareapparaat voor reclamedoeleinden. Meestal verstrekt door de fabrikant van het apparaat of het besturingssysteem. | Zie [Algemene apparaat-id&#39;s](#global-device-ids). |  |

<!--

Commenting out the table style. Fixed layout works better than auto layout for the index of IDs.

{style="table-layout:auto"}

-->

## [!DNL Global Device IDs] {#global-device-ids}

Algemene apparaat-id&#39;s zijn apparaat-advertentie-id&#39;s die uniek zijn voor elk apparaat en die worden geleverd door de fabrikant van het apparaat of het besturingssysteem. In de onderstaande tabel wordt uitgelegd wat deze id&#39;s zijn en wat hun indeling is. Voor meer informatie over globale apparaat IDs en hoe te om hen in [!DNL Audience Manager] te gebruiken, lees [Globale Gegevensbronnen](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Naam en beschrijving | Voorbeeld |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Id&#39;s zijn id&#39;s voor mobiele apparaten die worden geleverd door de fabrikant van het apparaat. Deze id&#39;s vertegenwoordigen apparaten die het besturingssysteem [!DNL iOS] uitvoeren. | De opmaak bestaat strikt uit 32 hexadecimale hoofdletters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens.<br> Voorbeeld: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s zijn id&#39;s voor mobiele apparaten die worden geleverd door fabrikanten van Android-apparaten. Deze id&#39;s vertegenwoordigen apparaten die het besturingssysteem [!DNL Android] uitvoeren. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] vertegenwoordigen  [!DNL Roku] streamingapparaten. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s is apparaat-id&#39;s die per apparaat en per gebruiker  [!DNL Windows 10] worden gegenereerd. | [!DNL MAID]s worden opgemaakt als alfanumerieke tekenreeksen. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] zijn apparaat-id&#39;s die door  [!DNL Samsung] slimme tv&#39;s worden geleverd. | [!DNL Samsung] [!DNL TIFA] Id&#39;s worden opgemaakt als alfanumerieke tekenreeksen. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Apparaatid&#39;s die apparaten vertegenwoordigen waarop het [!DNL Fire OS] besturingssysteem wordt uitgevoerd. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |