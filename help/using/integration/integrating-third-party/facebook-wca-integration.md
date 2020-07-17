---
description: Deze pagina illustreert het proces van het maken van WCA-pixels (Custom Audiences) op de Facebook-website, zodat webdoelsegmenten voor Audience Managers naar Facebook kunnen worden gestuurd, zodat ze online en doelgericht kunnen worden gemaakt.
seo-description: Deze pagina illustreert het proces van het maken van WCA-pixels (Custom Audiences) op de Facebook-website, zodat webdoelsegmenten voor Audience Managers naar Facebook kunnen worden gestuurd, zodat ze online en doelgericht kunnen worden gemaakt.
seo-title: Facebook WCA-integratie
solution: Audience Manager
title: Facebook WCA-integratie
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '862'
ht-degree: 5%

---


# [!DNL Facebook WCA] Integratie {#facebook-wca-integration}

Deze pagina illustreert het proces van het maken van [!DNL Facebook Website Custom Audiences] ([!DNL WCA]) pixels met het oog op het verzenden van [!DNL Audience Manager] publiekssegmenten op het web naar [!DNL Facebook], voor onlinedoeleinden en het maken van doeldocumenten met verbeterde transparantie.

## Overzicht {#overview}

[Met Facebook Website Custom Audiences (WCA)](https://www.facebook.com/business/help/449542958510885) kunt u een lijst maken met personen die bepaalde pagina&#39;s hebben bezocht of bepaalde handelingen op uw website hebben uitgevoerd. [!DNL Audience Manager] laat activering in het [!DNL WCA] gebruiken van [!DNL URL] bestemmingen toe, waarmee u een op pixel-gebaseerde integratie kunt vormen om web-based publiek naar [!DNL Facebook] voor het richten te verzenden.

![Facebook WCA-integratie](/help/using/integration/assets/facebook-wca-integration.png)

>[!IMPORTANT]
>
> Deze mogelijkheid vereist dat u het [!UICONTROL Website] publiek voor sociale platforms selecteert in [URL-doelen](/help/using/features/destinations/create-url-destination.md). Sociale platforms vereisen dat de informatie van de verwijzer wordt ontmaskerd wanneer verzonden naar hun platform. Houd er rekening mee dat dit betekent dat het doelplatform/de doelpartner informatie in uw referentie kan zien [!DNL URL].

## Vereisten {#prerequisites}

1. [!DNL Facebook Ad Account]
2. [!DNL Audience Manager] segmenten, klaar om toe te wijzen aan uw nieuwe [!DNL Facebook] bestemming. Hier is [hoe te om een segment](/help/using/features/segments/segment-builder.md) in [!DNL Audience Manager] UI tot stand te brengen.
3. [!DNL Adobe Experience Platform Identity Service] ([!DNL ECID]) Versie 4.1.0 of hoger. Download de nieuwste versie **[hier](https://github.com/Adobe-Marketing-Cloud/id-service/releases)**.
4. [!DNL Audience Manager Data Integration Library] ([!DNL DIL]) versie 9.0 of hoger, **[hier](https://github.com/Adobe-Marketing-Cloud/dil/releases)**te downloaden. U kunt ook[Server-Side Forwarding (SSF)](https://docs.adobe.com/content/help/en/analytics/admin/admin-tools/server-side-forwarding/ssf.html)gebruiken om gegevens te importeren naar[!DNL Audience Manager]AppMeasurement versie 2.12 of hoger. Download[!DNL AppMeasurement]using the[Analytics Code Manager](https://docs.adobe.com/content/help/nl-NL/analytics/admin/admin-tools/code-manager-admin.html).

We raden u aan de bibliotheken in stap 3 en 4 te installeren of bij te werken met [Adobe Experience Platform Launch](https://docs.adobelaunch.com/) of [Adobe Dynamic Tag Management](https://docs.adobe.com/content/help/nl-NL/dtm/using/dtm-home.html).

## Stap 1 - een [!UICONTROL Facebook Destination] in maken [!DNL Audience Manager] {#step-1-create-facebook-destination}

Maak een nieuwe [!UICONTROL URL Destination] in [!DNL Audience Manager] en noem deze [!DNL Facebook Website Custom Audiences]. Gebruik de onderstaande instellingen bij het maken van het doel. U kunt ook naar de pagina [Een URL-doel](/help/using/features/destinations/create-url-destination.md) configureren verwijzen.

### Basisinformatie

* **[!UICONTROL Category]**: Aangepast
* **[!UICONTROL Type]**: [!DNL URL]
* Selecteer het **[!UICONTROL Auto-fill Destination Mapping]** selectievakje en selecteer vervolgens **[!UICONTROL Segment ID]**.

### [!UICONTROL Data Export Labels]

Selecteer de optie **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**.

>[!NOTE]
>
> Dit exportlabel voorkomt dat gegevens en gegevens van derden die zijn afgeleid van apparaatgrafieken, in de segmenten worden opgenomen.

### Configuratie

* **[!UICONTROL URL type]**: Selecteer **[!UICONTROL Website audience for social platforms]**. Als u deze [!UICONTROL URL Type] optie selecteert, worden de gegevens van de [!DNL Audience Manager] referenties niet verborgen wanneer u een [!DNL URL] [!DNL Facebook WCA] pixel afvaagt.
* **[!UICONTROL Serialize]**: Selecteer **[!UICONTROL Enable]**.
* Voer in het **[!UICONTROL Base URL]** veld en het **[!UICONTROL Secure URL]** veld de [!DNL Facebook WCA] pixel in.
* **[!UICONTROL Delimiter]**: `,`

Basisvoorbeeld [!DNL URL] : `https://www.facebook.com/tr/?id=XXXXXXXXX&ev=Adobe-Audience-Manager-Segment&cd[segID]=%ALIAS%&noscript=1`

Voorbeeld van pixel die van de pagina worden afgegaan. In dit voorbeeld wordt een gebruiker weergegeven die in aanmerking komt voor drie [!DNL Audience Manager] segmenten, met de id&#39;s 3401321, 2993399, 3263410:

`https://www.facebook.com/tr/?id=6876666666662303&ev=Adobe-Audience-Manager-Segment&cd[segID]=3401321,2993399,3263410&noscript=1`

| Parameter | Beschrijving |
---------|----------|
| `id` | Uw [!DNL Facebook] pixel-id, die u kunt vinden in de [!DNL Facebook Ad Manager] gebruikersinterface wanneer u publiekspixels maakt. |
| `ev` | Event.     Dit is een willekeurige waarde die in de [!DNL Facebook Ad Manager] gebruikersinterface wordt weergegeven wanneer de pixel op de site wordt geactiveerd. Zie het [!UICONTROL Include] punt in [Stap 3](/help/using/integration/integrating-third-party/facebook-wca-integration.md#step-3-create-audience), voor meer informatie. |
| `cd[segID]` | Een extra parameter die wordt gevuld in de [!DNL Facebook Ad Manager] gebruikersinterface zodra de pixel op de site wordt geactiveerd. `segID` is ook arbitrair. |
| `%ALIAS%` | Een [!DNL Audience Manager] macro, die dynamisch wordt vervangen door de [!DNL Audience Manager] [!UICONTROL segment] id&#39;s waarvoor de bezoeker van de site in aanmerking komt, afgebakend door komma&#39;s, |

Uw [!UICONTROL URL destination] configuratie zou als in het hieronder beeld moeten kijken:

![Doelconfiguratie](/help/using/integration/assets/facebook-wca.png)

Sla het bestand op [!UICONTROL destination]. Vervolgens kunt u doorgaan naar de stap **Segmenttoewijzingen** .

## Stap 2 - de Toewijzingen van het segment - de Segment van de kaart aan Bestemming {#step-2-segment-mappings}

In het [Configure URL bestemmingswerkschema](/help/using/features/destinations/create-url-destination.md) , kaart het toepasselijke segment aan uw onlangs gecreeerd [!UICONTROL destination]. De toewijzingswaarde wordt automatisch ingevuld met de [!DNL Audience Manager] code [!UICONTROL segment ID].

Voer indien van toepassing een einddatum in, laat anders niets staan voor de einddatum.

## Stap 3 - Een [!UICONTROL Audience] element maken binnen [!DNL Facebook Ads Manager] {#step-3-create-audience}

Zie [Een aangepast publiek](https://www.facebook.com/business/help/666509013483225) voor de website maken in de [!DNL Facebook] Help-documentatie. Selecteer de [!UICONTROL Create Audience] opties in de onderstaande tabel:

| Item | Beschrijving |
---------|----------|
| Websiteverkeer | Aangepaste combinatie |
| Inclusief | <ul><li>Selecteer **[!UICONTROL Event]** > Selecteren **[!UICONTROL Adobe-Audience-Manager-Segment]**. Dit was de waarde van de `ev` parameter in de voorbeeldpixel in stap 1. Als de pixel nog moet worden geactiveerd, wordt de **[!UICONTROL Event]** optie wel of **[!UICONTROL Adobe-Audience-Manager-Segment]** niet weergegeven in de [!DNL Facebook] gebruikersinterface.</li><li>Een parameter toevoegen: Selecteer `segID`.</li><li><p>Selecteer de operator **contains** .</p><p>Dit is belangrijk, aangezien bezoekers in aanmerking kunnen komen voor meerdere segmenten, kan de pixelparameter meerdere [!UICONTROL segment IDs] elementen bevatten. Het gebruik van de operator equals (`=`) kwalificeert uw bezoekers mogelijk niet voor het publiek en u ziet een lager volume.</p></li><li>Voeg een waarde toe: Voer de [!DNL Audience Manager] segment-id in.</li></ul> |
| Nieuwe voorwaarde toevoegen | Optionele instelling. |
| In de laatste | Optionele instelling. |
| Auditienaam | Wij adviseren u de zelfde [!DNL Audience Manager] segmentnaam voor consistentie gebruikt, tenzij u extra voorwaarden aan dit Publiek toevoegt. |

## Stap 4 - Wijs het [!UICONTROL Audience] aan [!UICONTROL Campaign] binnen toe [!DNL Facebook Ads Manager] {#step-4-assign-audience-to-campaign}

Nadat u de animatie hebt gemaakt, wijst u deze toe aan een advertentiecampagne. [!DNL Custom Audience] Maak een nieuwe campagne of bewerk een bestaande campagne en u ziet dat het nieuwe publiek wordt vermeld in de [!DNL Facebook] gebruikersinterface. Uw advertentiecampagne richt zich op gebruikers die de pixelbrand op hun browser hebben gezien toen het bezoeken van uw plaats, als hen in het segment [!DNL Audience Manager] omvat.

## Samenvatting {#summary}

Nu u uw [!DNL Audience Manager] segment aan de [!DNL Facebook WCA] bestemming hebt toegewezen, [!DNL Audience Manager] zal selectief de [!DNL Facebook WCA] pixel aan gebruikers van een bepaald segment met respectieve segmentidentiteitskaart in het pixel in brand steken om [!DNL Facebook Audience]te bevolken. Dit leidt tot een geleidelijke verhoging van [!DNL Facebook Audience] hoe meer de markering aan het toepasselijke publiek op uw plaats in brand wordt gestoken.

>[!NOTE]
>
> Als een gebruiker uit het [!DNL Audience Manager] segment valt, is er momenteel geen manier voor [!DNL Audience Manager] om de gebruiker [!DNL Facebook] te informeren om uit het [!DNL Custom Audience].

