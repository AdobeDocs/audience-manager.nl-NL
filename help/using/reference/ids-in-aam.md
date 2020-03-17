---
description: Raadpleeg dit document voor de volledige lijst met Adobe Audience Manager-id's.
keywords: DPID; DPUUID; CID; UUID; uuid; uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid, uuid
seo-description: Raadpleeg dit document voor de volledige lijst met Adobe Audience Manager-id's.
seo-title: Index van id's in Audience Manager
solution: Audience Manager
title: Index van id's in Audience Manager
uuid: 292185ec-7c6a-414b-ab17-800c21cb1f01
translation-type: tm+mt
source-git-commit: f8916812a31513d3d8401a0598f37dae02a3fd02

---


# Index van id&#39;s in Audience Manager{#index-of-ids-in-audience-manager}

## Overzicht {#overview}

Audience Manager gebruikt meerdere id&#39;s om de gegevens te identificeren en te beheren die u ernaar verzendt. Raadpleeg dit artikel voor de volledige lijst met Adobe Audience Manager-id&#39;s, samen met voorbeelden van de voorvoegsels waarmee u deze kunt gebruiken.

## ID vooraf bepalen {#prefixing}

Terwijl u naar de meeste van deze IDs door hun standalone namen kunt verwijzen, moeten de meeste van hen met diverse prefixen worden gebruikt, wanneer het overgaan in gegevens door vraag DCS. Sommige van deze id&#39;s worden door Audience Manager gebruikt zonder aan gebruikers te worden blootgesteld, terwijl andere ook zichtbaar zijn in de gebruikersinterface (UI).

Om de prefixen te begrijpen die in de volgende voorbeelden worden gebruikt, zie [Gesteunde Attributen voor Vraag](../api/dcs-intro/dcs-api-reference/dcs-keys.md)DCS API.

## Lijst met id&#39;s voor Audience Manager {#id-list}

| ID | Naam en beschrijving | Gebruik en voorbeelden | UI-locatie |
|---|---|---|---|
| [!DNL AAM UUID] | Audience Manager Unique User ID. Een numerieke apparaat-id van 38 cijfers waarmee Audience Manager wordt geassocieerd aan elk apparaat waarmee het werkt. Denk aan deze id wanneer u een vermelding van unieke gebruikers ziet in de interface van Audience Manager. Audience Manager slaat deze id op als een cookie in het domein van `demdex.net` derden. | In [!DNL DCS] vraag, `uuid` wordt voorafgegaan door de `d_` prefix. <br>Voorbeeld: `d_uuid = 07955261652886032950143702505894272138` | Niet zichtbaar in de interface van Audience Manager. |
| [!DNL ImsOrgId] | Organisatie-id. Dit is de id waarmee een bedrijf wordt geconfronteerd wanneer het zich aanmeldt voor een Experience Cloud-account. | `5DC5123F5245B1D20A490D46@AdobeOrg` | Niet zichtbaar in de interface van Audience Manager. Als u wilt weten hoe u de organisatie-id van uw bedrijf kunt vinden, leest u [Zoeken naar uw organisatie-id](https://docs.adobe.com/content/help/en/core-services/interface/manage-users-and-products/organizations.html#concept_EA8AEE5B02CF46ACBDAD6A8508646255). |
| PID | Partner-id. De PID is de id van een bedrijf in Audience Manager. Audience Manager koppelt een koppeling [!DNL imsOrgId] aan een [!DNL PID]. | `1352` | Niet zichtbaar in de interface van Audience Manager. |
| [!DNL ECID], [!DNL MID] | Ervaar de cloud-id. De Experience Cloud-id ([!DNL ECID], verouderde afkortingen [!DNL MID] of [!DNL MCID]) wordt wiskundig afgeleid van uw organisatie-id en de unieke gebruikersnaam van Audience Manager. Zolang deze IDs constant blijft, is het produceren van het recht [!DNL ECID] voor een specifieke gebruiker eenvoudig een wiskundeprobleem. Met dezelfde organisatie-id en Audience Manager krijgt [!DNL UUID] u telkens dezelfde [!DNL ECID] waarde. Meer informatie over de ECID vindt u in de documentatie bij [Cookies en Experience Cloud ID](https://docs.adobe.com/content/help/en/id-service/using/intro/cookies.html#section-15f69c0bac394b4b9966a23fbc586d17) . | `mid = 08382830887934830189014177072406221371` | Niet zichtbaar in de interface van Audience Manager. |
| [!DNL SID] | Gebruikersnaam dienstreis. De eigenschap Trait ID identificeert op unieke wijze de kenmerken in de omgeving van Audience Manager. | In [!DNL DCS] vraag, `SID` wordt voorafgegaan door de `d_` prefix. <br>Voorbeeld `d_sid=289983`. | Aan elke eigenschap wordt een diensidentiteitskaart toegewezen, die in UI, op de pagina van [Randen](../features/traits/trait-details-page.md) zichtbaar is. |
| [!DNL SID] | Segment-id. Segment-id identificeert op unieke wijze segmenten in de omgeving van Audience Manager. | In [!DNL DCS] vraag, `SID` wordt voorafgegaan door de `d_` prefix. <br>Voorbeeld `d_sid=4798574`. | Een segment-id wordt toegewezen aan elk segment en zichtbaar in de UI op de pagina [Segmenten](../features/segments/segment-summary-view.md) . |
| [!DNL csegID] | Oudere segment-id. Deze identiteitskaart identificeert uniek segmenten in het milieu van de Manager van de Publiek. | `741232` | Een verouderde segment-id wordt toegewezen aan elk segment en is zichtbaar in de UI, op de pagina [Segmenten](../features/segments/segment-summary-view.md) . |
| [!DNL destID] | Doel-id. Identiteitskaart van de Bestemming identificeert uniek bestemmingen in het milieu van de Manager van de Publiek. Een identiteitskaart wordt toegewezen aan elke bestemming in UI. | `2523` | Een doel-id wordt toegewezen aan elk doel en zichtbaar in de gebruikersinterface op de pagina [Doelen](../features/destinations/destinations-home.md) . |
| [!DNL DPID] | Id van gegevensbron (wordt ook wel gegevensaanbieder-id genoemd). De gegevensbron-id is een naamruimte voor id&#39;s of kenmerken. Er wordt een id toegewezen aan elke gegevensbron (gegevensaanbieder) in de gebruikersinterface. | In [!DNL DCS] vraag, `dpid` wordt voorafgegaan door de `d_` prefix. <br>Voorbeeld: `d_dpid=39217`. | Een identiteitskaart van de Leverancier van Gegevens wordt toegewezen aan elke gegevensbron, en zichtbaar in UI, in de pagina van [Gegevensbronnen](../features/datasources-list-and-settings.md) . |
| [!DNL DPUUID] | Unieke gebruikersnaam van gegevensaanbieder (ook wel [!DNL CRM ID]). Een id van een derde. Dit is identiteitskaart waarmee u eind - gebruikers in uw eigen [!DNL CRM] systeem identificeert. U kunt synchroniseren [!DNL DPUUIDs] met Audience Manager [!DNL UUIDs] en u kunt synchroniseren [!DNL DPUUIDs] vanuit uw verschillende gegevensbronnen ([!DNL DPIDs]) tijdens het synchronisatieproces van de id. | In DCS vraag, `dpuuid` wordt voorafgegaan door de `d_` prefix. <br> Voorbeeld `d_dpuuid=2132-3423vn-343fds-3432r`. | Niet zichtbaar in de interface van Audience Manager. |
| [!DNL CRM ID] | Zie `DPUUID`. | Zie `DPUUID`. | Zie `DPUUID`. |
| [!DNL CID], [!DNL CID_IC] | Klantnummer, Code voor integratie van Klantnummer. De [!DNL CID] en [!DNL CID_IC] sleutel-waarde paren vervangen [!DNL DPID] en [!DNL DPUUID]. Zij verstrekken de zelfde functies zoals [!DNL DPID] en [!DNL DPUUID], maar zijn efficiënter omdat zij identiteitskaart van de gegevensleverancier en gebruiker - identiteitskaart (of integratiecode) in één enkel zeer belangrijk-waardepaar omvatten. | In vraag DCS, worden deze IDs voorafgegaan door de `d_` prefix. <br>Voorbeeld: `d_cid_ic=39217_myIntegrationCode`. | Zie `DPID` en `DPUUID`. |
| [!DNL DAID] | Advertising-id van apparaat. Een unieke id voor elk hardwareapparaat voor reclamedoeleinden. Meestal verstrekt door de fabrikant van het apparaat of het besturingssysteem. | Zie [Algemene apparaat-id&#39;s](#global-device-ids). |  |

## Algemene apparaat-id&#39;s {#global-device-ids}

Algemene apparaat-id&#39;s zijn apparaat-advertentie-id&#39;s die uniek zijn voor elk apparaat en die worden geleverd door de fabrikant van het apparaat of het besturingssysteem. In de onderstaande tabel wordt uitgelegd wat deze id&#39;s zijn en wat hun indeling is. Voor meer informatie over globale apparaat IDs en hoe te om hen in de Manager van de Publiek te gebruiken, lees [Globale Gegevensbronnen](/help/using/features/global-data-sources.md).

| ID | Algemene gegevensbron-id | Naam en beschrijving | Voorbeeld |
| --------------------- | ------ | ------------ | ---------------- |
| [!DNL IDFA] | 20915 | [!DNL Identifier for Advertisers] Id&#39;s zijn id&#39;s voor mobiele apparaten die worden geleverd door de fabrikant van het apparaat. Deze id&#39;s vertegenwoordigen apparaten die het iOS-besturingssysteem uitvoeren. | De opmaak bestaat strikt uit 32 hexadecimale hoofdletters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens.<br> Voorbeeld: `AEBE52E7-03EE-455A-B3C4-E57283966239`. |
| [!DNL GAID] | 20914 | [!DNL Google Advertising ID]s zijn id&#39;s voor mobiele apparaten die worden geleverd door fabrikanten van Android-apparaten. Deze id&#39;s vertegenwoordigen apparaten die het [!DNL Android] besturingssysteem uitvoeren. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `e4fe9bde-caa0-47b6-908d-ffba3fa184f2`. |
| [!DNL RIDA] | 121963 | [!DNL Roku IDs for Advertising] vertegenwoordigen [!DNL Roku] streamingapparaten. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `fcb2a29c-315a-5e6b-bcfd-d889ba19aada`. |
| [!DNL MAID] | 389146 | [!DNL Microsoft Advertising ID]s is apparaat-id&#39;s die per apparaat en per gebruiker worden gegenereerd. [!DNL Windows 10] | [!DNL MAID]s worden opgemaakt als alfanumerieke tekenreeksen. |
| [!DNL DUID] | 404660 | [!DNL Samsung DUID]s zijn apparaat-id&#39;s die door Samsung Smart TV&#39;s worden geleverd. | Samsung- [!DNL DUID]bestanden worden opgemaakt als alfanumerieke tekenreeksen. |
| [!DNL Amazon Fire TV Advertising ID] | 488258 | Apparaatid&#39;s die apparaten vertegenwoordigen waarop het [!DNL Fire OS] besturingssysteem wordt uitgevoerd. | De opmaak bestaat strikt uit 32 hexadecimale cijfers in kleine letters, weergegeven in vijf groepen en gescheiden door koppeltekens, in de vorm 8-4-4-4-12, voor een totaal van 36 tekens. <br>Voorbeeld: `df07c7dc-cea7-4a89-b328-810ff5acb15d` |

