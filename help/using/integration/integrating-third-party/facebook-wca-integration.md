---
description: Deze pagina illustreert het proces van het creëren van de pixel van de Douane van de Auditie van de Website van Facebook (WCA) voor het verzenden van web-based Audience Manager publiekssegmenten naar Facebook, voor online en gericht met betere transparantie.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA-integratie
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: b0521682c6332d23e55d769e7421680337670fa4
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# [!DNL Facebook WCA] Integratie {#facebook-wca-integration}

Deze pagina illustreert het proces voor het maken van [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) voor het verzenden van webgebaseerde [!DNL Audience Manager] doelsegmenten naar [!DNL Facebook], voor een betere transparantie bij het online en doelgericht gebruik.

## Overzicht {#overview}

[Aangepast publiek voor facebook-website (WCA)](https://www.facebook.com/business/help/449542958510885) Hiermee kunt u een lijst maken met personen die bepaalde pagina&#39;s hebben bezocht of bepaalde handelingen op uw website hebben uitgevoerd. [!DNL Audience Manager] activering in [!DNL WCA] gebruiken [!DNL URL] doelen, waarmee u een aangepaste op pixels gebaseerde integratie kunt configureren om een op het web gebaseerd publiek te sturen naar [!DNL Facebook] voor doelwitten.

![Facebook WCA-integratie](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Voor deze functie moet u de optie [!UICONTROL Website] publiek voor sociale platforms, optie in [URL-doelen](/help/using/features/destinations/create-url-destination.md). Sociale platforms vereisen dat de informatie van de verwijzer wordt ontmaskerd wanneer verzonden naar hun platform. Houd er rekening mee dat dit betekent dat het doelplatform/de doelpartner informatie in uw referentie kan zien [!DNL URL].

## Vereisten {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmenten, klaar om toe te wijzen aan uw nieuwe [!DNL Facebook] bestemming. Hier [hoe te om een segment tot stand te brengen](/help/using/features/segments/segment-builder.md) in de [!DNL Audience Manager] UI.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versie 4.1.0 of hoger. Download de nieuwste versie **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versie 9.0 of hoger, downloadbaar vanaf **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Als u [Server-Side Forwarding (SSF)](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html) om gegevens te importeren in [!DNL Audience Manager], moet u AppMeasurement versie 2.12 of hoger gebruiken. Downloaden [!DNL AppMeasurement] met de [Analysebeheer](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html).

U wordt aangeraden de bibliotheken in stap 3 en 4 te installeren of bij te werken met [Adobe Experience Platform-tags](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html).

## Stap 1 - een [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Een nieuwe [!UICONTROL URL Destination] in [!DNL Audience Manager] en noem deze [!DNL Facebook Website Custom Audiences]. Gebruik de onderstaande instellingen bij het maken van het doel. U kunt ook verwijzen naar de [Een URL-doel configureren](/help/using/features/destinations/create-url-destination.md) pagina.

### Basisinformatie

* **[!UICONTROL Category]**: Aangepast
* **[!UICONTROL Type]**: [!DNL URL]
* Selecteer **[!UICONTROL Auto-fill Destination Mapping]** selectievakje en selecteer vervolgens **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selecteer de optie **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Dit exportlabel voorkomt dat gegevens en gegevens van derden die zijn afgeleid van apparaatgrafieken, in de segmenten worden opgenomen.

### Configuratie

* **[!UICONTROL URL type]**: Selecteren **[!UICONTROL Website audience for social platforms]**. Selecteer deze [!UICONTROL URL Type] optie, [!DNL Audience Manager] verbergt de verwijzende persoon niet [!DNL URL] informatie bij het afvuren van een [!DNL Facebook WCA] pixel.
* **[!UICONTROL Serialize]**: Selecteren **[!UICONTROL Enable]**.
* In de **[!UICONTROL Base URL]** en **[!UICONTROL Secure URL]** veld, voert u de [!DNL Facebook WCA] pixel.
* **[!UICONTROL Delimiter]**: `,`

Basis [!DNL URL] voorbeeld: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Voorbeeld van pixel die van de pagina worden afgegaan. In dit voorbeeld wordt een gebruiker getoond die in aanmerking komt voor drie [!DNL Audience Manager] segmenten, met de ID&#39;s 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschrijving |
|---------|----------|
| `id` | Uw [!DNL Facebook] pixel ID, die u in kunt vinden [!DNL Facebook Ad Manager] gebruikersinterface bij het maken van publiekspixels. |
| `ev` | Event.     Dit is een willekeurige waarde die wordt weergegeven in het dialoogvenster [!DNL Facebook Ad Manager] gebruikersinterface wanneer de pixel op de site wordt geactiveerd. Zie de [!UICONTROL Include] item in [Stap 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience)voor meer informatie. |
| `cd[segID]` | Een extra parameter, die binnen zal beginnen te bevolken binnen [!DNL Facebook Ad Manager] gebruikersinterface wanneer de pixel op de site wordt geactiveerd. `segID` is ook arbitrair. |
| `%ALIAS%` | An [!DNL Audience Manager] macro, die dynamisch wordt vervangen door de [!DNL Audience Manager] [!UICONTROL segment] ID&#39;s waarvoor de sitebezoeker in aanmerking komt, gescheiden door komma&#39;s, |

Uw [!UICONTROL URL destination] De configuratie zou als in het hieronder beeld moeten kijken:

![Doelconfiguratie](/help/using/integration/assets/facebook-wca.png)

Sla de [!UICONTROL destination]. Vervolgens kunt u doorgaan naar de **Segmenttoewijzingen** stap.

## Stap 2 - de Toewijzingen van het segment - de Segment van de kaart aan Bestemming {#step-2-segment-mappings}

In de [URL-doel configureren](/help/using/features/destinations/create-url-destination.md) werkschema, kaart het toepasselijke segment aan uw nieuw gecreeerd [!UICONTROL destination]. Merk op dat de toewijzingswaarde automatisch wordt gevuld met de [!DNL Audience Manager] [!UICONTROL segment ID].

Voer indien van toepassing een einddatum in, laat anders niets staan voor de einddatum.

## Stap 3 - Een [!UICONTROL Audience] binnen [!DNL Facebook Ads Manager] {#step-3-create-audience}

Zie [Aangepast publiek voor website maken](https://www.facebook.com/business/help/666509013483225) in de [!DNL Facebook] Help documentatie. Selecteer [!UICONTROL Create Audience] opties in de onderstaande tabel:

| Item | Beschrijving |
|---------|----------|
| Websiteverkeer | Aangepaste combinatie |
| Inclusief | <ul><li>Selecteren **[!UICONTROL Event]** > Selecteren **[!UICONTROL Adobe-Audience-Manager-Segment]**. Dit was de waarde van de `ev` in de voorbeeldpixel in stap 1. Als de pixel nog moet worden geactiveerd, **[!UICONTROL Event]** of **[!UICONTROL Adobe-Audience-Manager-Segment]** mag niet worden weergegeven in het [!DNL Facebook] gebruikersinterface.</li><li>Een parameter toevoegen: Selecteren `segID`.</li><li><p>Selecteer **contains** operator.</p><p>Dit is belangrijk, aangezien bezoekers in aanmerking kunnen komen voor meerdere segmenten, er meerdere [!UICONTROL segment IDs] in de parameter pixel. De equals gebruiken (`=`) niet in aanmerking komen voor het publiek en u ziet een lager volume.</p></li><li>Voeg een waarde toe: Voer de [!DNL Audience Manager] segment-id.</li></ul> |
| Nieuwe voorwaarde toevoegen | Optionele instelling. |
| In de laatste | Optionele instelling. |
| Auditienaam | We raden u aan hetzelfde te gebruiken [!DNL Audience Manager] segmentnaam voor consistentie, tenzij u extra voorwaarden aan dit publiek toevoegt. |

## Stap 4 - Wijs de [!UICONTROL Audience] een [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Nadat u de [!DNL Custom Audience], wijst u deze toe aan een advertentiecampagne. Maak een nieuwe campagne of bewerk een bestaande campagne. Uw nieuwe publiek wordt vermeld in het dialoogvenster [!DNL Facebook] gebruikersinterface. Uw advertentiecampagne is gericht op gebruikers die de pixelbrand op hun browser hebben gezien toen ze uw site bezoeken, als [!DNL Audience Manager] neemt hen in het segment op.

## Samenvatting {#summary}

Nu hebt u uw [!DNL Audience Manager] naar het segment [!DNL Facebook WCA] bestemming, [!DNL Audience Manager] zal selectief de [!DNL Facebook WCA] pixel aan gebruikers van een bepaald segment met respectieve segment ID in het pixel om het te bevolken [!DNL Facebook Audience]. Dit leidt tot een geleidelijke toename van de [!DNL Facebook Audience] hoe meer de tag wordt geactiveerd voor het toepasselijke publiek op uw site.

>[!NOTE]
>
> Als een gebruiker buiten de [!DNL Audience Manager] segment, is er momenteel geen manier voor [!DNL Audience Manager] om [!DNL Facebook] om de gebruiker uit de [!DNL Custom Audience].
