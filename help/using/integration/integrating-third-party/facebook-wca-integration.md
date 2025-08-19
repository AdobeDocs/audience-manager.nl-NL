---
description: Deze pagina illustreert het proces van het maken van WCA-pixels (Custom Audiences) op de Facebook-website, waarmee u op het web gebaseerde Audience Manager-publiekssegmenten naar Facebook kunt sturen, zodat u deze online kunt plaatsen en doelgericht kunt gebruiken.
seo-description: This page illustrates the process of creating Facebook Website Custom Audiences (WCA) pixels for the purposes of sending web-based Audience Manager audience segments to Facebook, for online ad targeting with improved transparency.
seo-title: Facebook WCA Integration
solution: Audience Manager
title: Facebook WCA-integratie
feature: Third-party Integration
exl-id: edd06247-b46b-4851-ab71-8cc05a1d6d63
source-git-commit: 6dc931b88666515cf51ab89ce1a54bbcf9995679
workflow-type: tm+mt
source-wordcount: '808'
ht-degree: 1%

---

# [!DNL Facebook WCA] Integratie {#facebook-wca-integration}

Deze pagina illustreert het proces van het maken van [!DNL Facebook Website Custom Audiences] ([!DNL WCA] ) pixels voor het verzenden van op het web gebaseerde [!DNL Audience Manager] publiekssegmenten naar [!DNL Facebook] , voor online en doelgericht met verbeterde transparantie.

>[!IMPORTANT]
>
>Dit is geen productieve integratie tussen Audience Manager en Facebook.

## Overzicht {#overview}

[ Eigen publiek van de Website van Facebook (WCA) ](https://www.facebook.com/business/help/610516375684216?id=2469097953376494) staat u toe om een lijst van mensen tot stand te brengen die bepaalde pagina&#39;s hebben bezocht of bepaalde acties op uw website hebben genomen. [!DNL Audience Manager] schakelt activering in [!DNL WCA] using [!DNL URL] -doelen in, waarmee u een aangepaste op pixels gebaseerde integratie kunt configureren om een op het web gebaseerd publiek naar [!DNL Facebook] te sturen voor activering.

![Facebook WCA-integratie](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Dit vermogen vereist dat u het [!UICONTROL Website] publiek voor sociale platformoptie in [ bestemmingen URL ](/help/using/features/destinations/create-url-destination.md) selecteert. Sociale platforms vereisen dat de informatie van de verwijzer wordt ontmaskerd wanneer verzonden naar hun platform. Houd er rekening mee dat dit betekent dat het doelplatform/de doelpartner informatie kan zien in uw referentie [!DNL URL] .

## Vereisten {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] -segmenten, klaar om toe te wijzen aan uw nieuwe [!DNL Facebook] -doel. Hier is [ hoe te om een segment ](/help/using/features/segments/segment-builder.md) in [!DNL Audience Manager] UI tot stand te brengen.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versie 4.1.0 of hoger. Download de recentste versie **[hier ](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versie 9.0 of nieuwer, downloadbaar van **[hier ](https://github.com/Adobe-Marketing-Cloud/dil/releases)**. Alternatief, als u [ Server-zij door:sturen (SSF) ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/server-side-forwarding/ssf.html?lang=nl-NL) gebruikt om gegevens in [!DNL Audience Manager] in te voeren, moet u versie 2.12 van AppMeasurement of nieuwer gebruiken. Download [!DNL AppMeasurement] gebruikend de [ Manager van de Code van Analytics ](https://experienceleague.adobe.com/docs/analytics/admin/admin-tools/code-manager-admin.html?lang=nl-NL).

Wij adviseren dat u de bibliotheken in stappen 3 en 4 gebruikend [ de Markeringen van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/tags/home.html?lang=nl-NL) installeert of bevordert.

## Stap 1 - Maak een [!UICONTROL Facebook Destination] in [!DNL Audience Manager] {#step-1-create-facebook-destination}

Maak een nieuwe [!UICONTROL URL Destination] in [!DNL Audience Manager] en noem deze [!DNL Facebook Website Custom Audiences] . Gebruik de onderstaande instellingen bij het maken van het doel. U kunt ook naar [ verwijzen vormt een URL- Bestemming ](/help/using/features/destinations/create-url-destination.md) pagina.

### Basisinformatie

* **[!UICONTROL Category]**: Aangepast
* **[!UICONTROL Type]**: [!DNL URL]
* Schakel het selectievakje **[!UICONTROL Auto-fill Destination Mapping]** in en selecteer vervolgens **[!UICONTROL Segment ID]** .

### [!UICONTROL Data Export Labels]

Selecteer de optie **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]** .

>[!NOTE]
>
> Dit exportlabel voorkomt dat gegevens en gegevens van derden die zijn afgeleid van apparaatgrafieken, in de segmenten worden opgenomen.

### Configuratie

* **[!UICONTROL URL type]**: Selecteer **[!UICONTROL Website audience for social platforms]** . Als u deze optie [!UICONTROL URL Type] selecteert, worden de [!DNL Audience Manager] referentie [!DNL URL] -gegevens niet verborgen wanneer een [!DNL Facebook WCA] pixel wordt afgevuurd.
* **[!UICONTROL Serialize]**: Selecteer **[!UICONTROL Enable]** .
* Voer in het veld **[!UICONTROL Base URL]** en **[!UICONTROL Secure URL]** de [!DNL Facebook WCA] pixel in.
* **[!UICONTROL Delimiter]**: `,`

Base [!DNL URL] voorbeeld: `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Voorbeeld van pixel die van de pagina worden afgegaan. In dit voorbeeld wordt een gebruiker weergegeven die in aanmerking komt voor drie [!DNL Audience Manager] -segmenten, met de id&#39;s 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschrijving |
|---------|----------|
| `id` | Uw [!DNL Facebook] pixel-id, die u kunt vinden in de gebruikersinterface van [!DNL Facebook Ad Manager] wanneer u publiekspixels maakt. |
| `ev` | Gebeurtenis. Dit is een willekeurige waarde die in de gebruikersinterface van [!DNL Facebook Ad Manager] wordt weergegeven wanneer de pixel op de site wordt geactiveerd. Zie het [!UICONTROL Include] punt in [ Stap 3 ](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), voor meer informatie. |
| `cd[segID]` | Een aanvullende parameter die wordt gevuld in de gebruikersinterface van [!DNL Facebook Ad Manager] wanneer de pixel op de site wordt geactiveerd. `segID` is ook arbitrair. |
| `%ALIAS%` | Een [!DNL Audience Manager] macro, die dynamisch wordt vervangen door de [!DNL Audience Manager] [!UICONTROL segment] id&#39;s waarvoor de sitebezoeker in aanmerking komt, gescheiden door komma&#39;s, |

Uw [!UICONTROL URL destination] -configuratie moet er als volgt uitzien in de onderstaande afbeelding:

![ Configuratie van de Bestemming ](/help/using/integration/assets/facebook-wca.png)

Sla de [!UICONTROL destination] op. Dan, kunt u aan de **Mappings van het Segment** stap te werk gaan.

## Stap 2 - de Toewijzingen van het segment - de Segment van de kaart aan Bestemming {#step-2-segment-mappings}

In [ vorm URL bestemmings ](/help/using/features/destinations/create-url-destination.md) werkschema, kaart het toepasselijke segment aan uw onlangs gecreeerd [!UICONTROL destination]. De toewijzingswaarde wordt automatisch gevuld met de [!DNL Audience Manager] [!UICONTROL segment ID] .

Voer indien van toepassing een einddatum in, laat anders niets staan voor de einddatum.

## Stap 3 - Een [!UICONTROL Audience] binnen [!DNL Facebook Ads Manager] maken {#step-3-create-audience}

Zie [ een publiek van de Douane van de Website ](https://www.facebook.com/business/help/666509013483225) in de [!DNL Facebook] hulpdocumentatie creëren. Selecteer de opties voor [!UICONTROL Create Audience] in de onderstaande tabel:

| Item | Beschrijving |
|---------|----------|
| Websiteverkeer | Aangepaste combinatie |
| Inclusief | <ul><li>Selecteer **[!UICONTROL Event]** > Selecteren **[!UICONTROL Adobe-Audience-Manager-Segment]** . Dit was de waarde van de parameter `ev` in de voorbeeldpixel in stap 1. Als de pixel nog moet worden geactiveerd, wordt de optie **[!UICONTROL Event]** of **[!UICONTROL Adobe-Audience-Manager-Segment]** mogelijk niet weergegeven in de gebruikersinterface van [!DNL Facebook] .</li><li>Voeg een parameter toe: Selecteren `segID` .</li><li><p>Selecteer **bevat** exploitant.</p><p>Dit is belangrijk, aangezien bezoekers in aanmerking kunnen komen voor meerdere segmenten, kan de pixelparameter meerdere [!UICONTROL segment IDs] bevatten. Het gebruik van de gelijk (`=`) exploitant kan uw bezoekers voor het publiek niet kwalificeren, en u zult een lager volume waarnemen.</p></li><li>Voeg een waarde toe: voer de [!DNL Audience Manager] segment-id in.</li></ul> |
| Nieuwe voorwaarde toevoegen | Optionele instelling. |
| In de laatste | Optionele instelling. |
| Auditienaam | We raden u aan dezelfde segmentnaam van [!DNL Audience Manager] te gebruiken voor consistentie, tenzij u aanvullende voorwaarden toevoegt aan deze doelgroep. |

## Stap 4 - Wijs de [!UICONTROL Audience] toe aan een [!UICONTROL Campaign] in [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Nadat u de [!DNL Custom Audience] hebt gemaakt, wijst u deze toe aan een advertentiecampagne. Maak een nieuwe campagne of bewerk een bestaande campagne en u ziet dat het nieuwe publiek wordt vermeld in de gebruikersinterface van [!DNL Facebook] . Uw advertentiecampagne is gericht op gebruikers die de pixelbrand op hun browser hebben gezien toen ze uw site bezoeken, als [!DNL Audience Manager] deze in het segment opneemt.

## Samenvatting {#summary}

Nu u het [!DNL Audience Manager] -segment hebt toegewezen aan het [!DNL Facebook WCA] doel, wordt de [!DNL Audience Manager] -pixel selectief geactiveerd voor gebruikers van een bepaald segment met de respectievelijke segment-id in de pixel om de [!DNL Facebook WCA] -tekenreeks te vullen. [!DNL Facebook Audience] Dit leidt tot een geleidelijke verhoging van [!DNL Facebook Audience] hoe meer de markering aan het toepasselijke publiek op uw plaats in brand wordt gestoken.

>[!NOTE]
>
> Als een gebruiker buiten het [!DNL Audience Manager] -segment valt, is het momenteel niet mogelijk voor [!DNL Audience Manager] om [!DNL Facebook] op de hoogte te brengen om de gebruiker uit het [!DNL Custom Audience] -segment te verwijderen.
>
