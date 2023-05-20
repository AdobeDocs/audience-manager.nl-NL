---
description: Raadpleeg dit document voor de volledige lijst met Adobe Audience Manager-id's.
keywords: DPID; DPUUID; CID; UUID; uuuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuuid, uuid, uuid
seo-description: Refer to this document for the complete list of Adobe Audience Manager IDs.
seo-title: Index of IDs in Audience Manager
solution: Audience Manager
title: Index van id’s in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
feature: Reference
exl-id: 1caf3c6a-ebfd-49f1-9ebd-d4604474c070
source-git-commit: e408c118870fb331c40758be8a7e6b38690aeb5f
workflow-type: tm+mt
source-wordcount: '994'
ht-degree: 3%

---

# Index van id&#39;s in [!DNL Audience Manager] {#index-of-ids-in-audience-manager}

## Overzicht {#overview}

[!DNL Audience Manager] gebruikt meerdere id&#39;s om de gegevens te identificeren en te beheren die u ernaar verzendt. Raadpleeg dit artikel voor de volledige lijst met [!DNL Audience Manager] Id&#39;s, samen met voorbeelden van de voorvoegsels waarmee u ze moet gebruiken.

## ID vooraf bepalen {#prefixing}

Terwijl u naar de meeste van deze IDs door hun standalone namen kunt verwijzen, zijn de meeste van hen bedoeld om met diverse prefixen worden gebruikt, wanneer het overgaan in gegevens door [!DNL DCS] oproepen. Sommige van deze id&#39;s worden gebruikt door [!DNL Audience Manager] zonder aan gebruikers te worden blootgesteld, terwijl anderen ook in het gebruikersinterface (UI) zichtbaar zijn.

Als u de voorvoegsels wilt begrijpen die in de volgende voorbeelden worden gebruikt, raadpleegt u [Ondersteunde kenmerken voor DCS API-aanroepen](../api/dcs-intro/dcs-api-reference/dcs-keys.md).

## [!DNL Audience Manager] Lijst met id&#39;s {#id-list}

| ID | Naam en beschrijving | Gebruik en voorbeelden | Locatie gebruikersinterface |
|---|---|---|---|
| [!DNL AAM UUID] | [!DNL Adobe Audience Manager Unique User ID], ook bekend als [!UICONTROL Device ID]. Een numerieke, 38-cijferige apparaat-id die [!DNL Audience Manager] koppelen aan elk apparaat waarmee het communiceert. Denk aan deze id wanneer u een vermelding van unieke gebruikers ziet in het deelvenster [!DNL Audience Manager] UI. Audience Manager slaat deze id op als een [!DNL cookie] in de `demdex.net` Domein van derden. | In [!DNL DCS] oproepen, `uuid` wordt voorafgegaan door de `d_` voorvoegsel. <br>Voorbeeld: `d_uuid = 07955261652886032950143702505894272138` | U kunt filteren [!DNL traits] door [!UICONTROL Device ID] wanneer u [Modellen met veel vormgeving](../features/algorithmic-models/create-model.md), en [bouwsegmenten](../features/segments/segment-builder.md). U kunt resultaten ook filteren op [!UICONTROL Device ID] bij uitvoering [Algemene verslagen over reizen](../reporting/general-reports.md) en [Trend Reports for Traits](../reporting/trend-reports.md). |
| [!DNL ImsOrgId] | [!DNL Organization ID]. Dit is de id waarmee een bedrijf wordt uitgerust wanneer het zich aanmeldt voor een [!DNL Experience Cloud] account. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Niet zichtbaar in het dialoogvenster [!DNL Audience Manager] gebruikersinterface. Om te leren hoe u uw bedrijf kunt vinden [!DNL Organization ID], lezen [Zoek uw organisatie-id](https://experienceleague.adobe.com/docs/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| [!DNL PID] | [!DNL Partner ID]. De [!DNL PID] is de id van een bedrijf in [!DNL Audience Manager]. Audience Manager associeert en [!DNL imsOrgId] een [!DNL PID]. | `1352` | Niet zichtbaar in het dialoogvenster [!DNL Audience Manager] gebruikersinterface. |
| [!DNL ECID], [!DNL MID] | [!DNL Experience Cloud] ID. De [!DNL Experience Cloud] ID ([!DNL ECID], oude afkortingen [!DNL MID] of [!DNL MCID]) is wiskundig afgeleid van uw [!DNL Organization ID] en de [!DNL Audience Manager] [!UICONTROL Unique User ID]. Zolang deze id&#39;s constant blijven, wordt het recht gegenereerd [!DNL ECID] voor een specifieke gebruiker is gewoon een wiskundeprobleem. Met dezelfde [!DNL Organization ID] en [!DNL Audience Manager] [!DNL UUID] dezelfde [!DNL ECID] waarde elke keer. U kunt meer lezen over de [!DNL ECID] in de [Cookies en Experience Cloud-id](https://experienceleague.adobe.com/docs/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) documentatie. | `mid = 08382830887934830189014177072406221371` | Niet zichtbaar in het dialoogvenster [!DNL Audience Manager] gebruikersinterface. |
| [!DNL SID] | [!UICONTROL Trait ID]. De [!UICONTROL Trait ID] uniek identificeert [!DNL traits] in de [!DNL Audience Manager] milieu. | In [!DNL DCS] oproepen, `SID` wordt voorafgegaan door de `d_` voorvoegsel. <br>Voorbeeld `d_sid=289983`. | A [!UICONTROL Trait ID] wordt toegewezen aan elk [!DNL trait]en zichtbaar zijn in de gebruikersinterface, in de [Treinen](../features/traits/trait-details-page.md) pagina. |
| [!DNL SID] | [!UICONTROL Segment ID]. De [!UICONTROL Segment ID] uniek identificeert [!DNL segments] in de [!DNL Audience Manager] milieu. | In [!DNL DCS] oproepen, `SID` wordt voorafgegaan door de `d_` voorvoegsel. <br>Voorbeeld `d_sid=4798574`. | A [!UICONTROL Segment ID] wordt toegewezen aan elk [!DNL segment]en zichtbaar zijn in de gebruikersinterface, in de [Segmenten](../features/segments/segment-summary-view.md) pagina. |
| [!DNL csegID] | [!DNL Legacy Segment ID]. Deze id identificeert op unieke wijze segmenten in de [!DNL Audience Manager] milieu. | `741232` | A [!UICONTROL Legacy Segment ID] wordt toegewezen aan elk segment, en zichtbaar in het gebruikersinterface, in [Segmenten](../features/segments/segment-summary-view.md) pagina. |
| [!DNL destID] | [!UICONTROL Destination ID]. De [!UICONTROL Destination ID] uniek identificeert [!DNL destinations] in de [!DNL Audience Manager] milieu. Aan elke id wordt een id toegewezen [!DNL destination] in de gebruikersinterface. | `2523` | A [!UICONTROL Destination ID] wordt toegewezen aan elk [!DNL destination]en zichtbaar zijn in de gebruikersinterface, in de [Doelen](../features/destinations/destinations-home.md) pagina. |
| [!DNL DPID] | [!UICONTROL Data Source ID] (ook aangeduid als [!UICONTROL Data Provider ID]). De [!UICONTROL Data Source ID] is een naamruimte voor id&#39;s of [!DNL traits]. Aan elke id wordt een id toegewezen [!DNL data source] (gegevensaanbieder) in de gebruikersinterface. | In [!DNL DCS] oproepen, `dpid` wordt voorafgegaan door de `d_` voorvoegsel. <br>Voorbeeld: `d_dpid=39217`. | A [!UICONTROL Data Provider ID] wordt toegewezen aan elk [!DNL data source]en zichtbaar zijn in de gebruikersinterface, in de [Gegevensbronnen](../features/datasources-list-and-settings.md) pagina. |
| [!DNL DPUUID] | [!UICONTROL Data Provider Unique User ID], ook aangeduid als [!DNL CRM ID] of [!UICONTROL Cross-Device ID]. Een id van een derde. Dit is de id waarmee u eindgebruikers in uw eigen identiteit kunt identificeren [!DNL CRM] systeem. U kunt synchroniseren [!DNL DPUUIDs] with [!DNL Audience Manager] [!DNL UUIDs] en u kunt synchroniseren [!DNL DPUUIDs] van uw [!UICONTROL Data Sources] ([!DNL DPIDs]) in het synchronisatieproces van de id. | In [!DNL DCS] oproepen; `dpuuid` wordt voorafgegaan door de `d_` voorvoegsel. <br> Voorbeeld `d_dpuuid=2132-3423vn-343fds-3432r`. | U kunt filteren [!DNL traits] door [!UICONTROL Cross-Device ID] wanneer u [Modellen met veel vormgeving](../features/algorithmic-models/create-model.md), en [bouwsegmenten](../features/segments/segment-builder.md). U kunt resultaten ook filteren op [!UICONTROL Cross-Device ID] bij uitvoering [Algemene verslagen over reizen](../reporting/general-reports.md) en [Trend Reports for Traits](../reporting/trend-reports.md). |
| [!DNL CRM ID] | Zie `DPUUID`. | Zie `DPUUID`. | Zie `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | [!UICONTROL Customer ID], [!UICONTROL Customer ID Integration Code]. De [!DNL CID] en [!DNL CID_IC] sleutelwaardeparen vervangen [!DNL DPID] en [!DNL DPUUID]. Zij leveren dezelfde functies als de [!DNL DPID] en [!DNL DPUUID], maar zijn efficiënter omdat zij gegevensleverancier ID en gebruiker - identiteitskaart (of integratiecode) in één enkel zeer belangrijk-waardepaar omvatten. | In [!DNL DCS] vraag, wordt deze IDs voorafgegaan door `d_` voorvoegsel. <br>Voorbeeld: `d_cid_ic=39217_myIntegrationCode`. | Zie `DPID` en `DPUUID`. |
| [!DNL DAID] | [!UICONTROL Device Advertising ID]. Een unieke id voor elk hardwareapparaat voor reclamedoeleinden. Meestal verstrekt door de fabrikant van het apparaat of het besturingssysteem. | Zie [Algemene apparaat-id&#39;s](#global-device-ids). |  |

## [!DNL Global Device IDs] {#global-device-ids}

Algemene apparaat-id&#39;s zijn apparaat-advertentie-id&#39;s die uniek zijn voor elk apparaat en die worden geleverd door de fabrikant van het apparaat of het besturingssysteem. In de onderstaande tabel wordt uitgelegd wat deze id&#39;s zijn en wat hun indeling is. Voor meer informatie over algemene apparaat-id&#39;s en hoe u deze kunt gebruiken in [!DNL Audience Manager], lezen [Algemene gegevensbronnen](/help/using/features/global-data-sources.md).

| ID | [!DNL Global Data Source ID] | Naam en beschrijving | Voorbeeld |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Id&#39;s zijn id&#39;s voor mobiele apparaten die worden geleverd door de fabrikant van het apparaat. Deze id&#39;s vertegenwoordigen apparaten die de [!DNL iOS] besturingssysteem. | De opmaak bestaat strikt uit 32 hexadecimale hoofdletters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens.<br> Voorbeeld: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s zijn id&#39;s voor mobiele apparaten die worden geleverd door fabrikanten van Android-apparaten. Deze id&#39;s vertegenwoordigen apparaten die de [!DNL Android] besturingssysteem. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] vertegenwoordigen [!DNL Roku] streaming apparaten. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s zijn apparaat-id&#39;s die zijn gegenereerd door [!DNL Windows 10] per apparaat, per gebruiker. | [!DNL MAID]s worden opgemaakt als alfanumerieke tekenreeksen. |
| [!DNL TIFA] | 963906 | [!DNL Samsung Tizen IDs for Advertising] zijn apparaat-id&#39;s die worden geleverd door [!DNL Samsung] Slimme tv&#39;s. | [!DNL Samsung] [!DNL TIFA] Id&#39;s worden opgemaakt als alfanumerieke tekenreeksen. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Apparaatid&#39;s die apparaten vertegenwoordigen waarop het [!DNL Fire OS] besturingssysteem. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |
| [!DNL LGUDID] | 1171485 | Apparaatid&#39;s die apparaten vertegenwoordigen waarop het [!DNL LG webOS] besturingssysteem. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `095f142a-ace8-ac5d-b86a-92c8be18b197` |
| [!DNL Vizio IFA] | 1171489 | Apparaatid&#39;s die apparaten vertegenwoordigen waarop het besturingssysteem Vizio smart TV wordt uitgevoerd. | [!DNL Vizio IFA] Id&#39;s worden opgemaakt als alfanumerieke tekenreeksen. <br>Voorbeeld: `7XCBNROQJQPYW`. |
