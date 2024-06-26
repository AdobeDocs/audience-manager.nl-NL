---
description: Met Destination Builder kunt u op cookies gebaseerde of DNL URL-doelen maken. U kunt geen server-aan-server (S2S) bestemmingen met de Bouwer van de Bestemming tot stand brengen, maar u kunt hun segmentafbeeldingen beheren. Neem contact op met uw consultant om een S2S-bestemming in te stellen. De Bouwer van de bestemming wordt gevestigd in de Gegevens van het Publiek > Doelen.
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Bestemmingsbuilder
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '270'
ht-degree: 2%

---

# Bestemmingsbuilder {#destination-builder}

[!UICONTROL Destination Builder] kunt u op cookies gebaseerde of [!DNL URL] bestemmingen. U kunt geen server-aan-server tot stand brengen ([!DNL S2S]) bestemmingen met [!UICONTROL Destination Builder], maar u kunt hun segmenttoewijzingen beheren. Neem contact op met uw consultant om een [!DNL S2S] bestemming. [!UICONTROL Destination Builder] bevindt zich in **[!UICONTROL Audience Data > Destinations]**.

## Instellingen van doelontwikkelaar {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] bestaat uit de volgende secties en instellingen:

| [!UICONTROL Destination Builder] Sectie | Doel |
|--- |--- |
| Basisinformatie | Wordt gebruikt om het doel een naam te geven, het te beschrijven en het doeltype te selecteren ([!DNL URL] of [!DNL cookie]), en platform (all, [!DNL Android], browser, of [!DNL iOS]). |
| Configuratie | Omvat besturingselementen voor: <br/><ul><li>Sleutelwaarde-gegevens doorgeven aan [!DNL URL] bestemmingen. U kunt gegevens verzenden als individuele of geserialiseerde sleutel-waardeparen. Zie voor meer informatie [Serienummering bestemming](../../features/destinations/key-value-pairs.md#destination-serialized) en [Standaard en seriële sleutelwaardeparen](../../features/destinations/key-value-pairs.md). </li><li>Elementen van een cookiebestemming, zoals de naam, het domein, de grootte, het vervalinterval, de gegevensindeling, enz.</li></ul> |
| Segmenttoewijzingen | Hiermee kunt u: <br/><ul><li>Zoek, voeg, en beheer segmenten toe verbonden aan alle bestemmingstypes. </li><li>Afleveringsprioriteiten instellen voor afzonderlijke segmenten (voor [!DNL cookie]alleen op segmenten gebaseerde segmenten).</li></ul> |

## Methoden voor gegevenslevering {#data-delivery-methods}

Gegevens naar een bestemming verzenden door deze door te geven via een [!DNL URL] tekenreeks, door naar een browser te schrijven [!DNL cookie]of via gegevensoverdracht van de ene naar de andere offlineserver.

* [!DNL URL] en op cookies gebaseerde doelen verzenden gegevens synchroon, terwijl een gebruiker actie onderneemt op een pagina.
* De server-aan-server gegevenstransmissie is asynchroon en kan voorkomen lang nadat een gebruiker de pagina heeft verlaten. Het leveringstype u selecteert hangt van uw bedrijfsvereisten af en hoe een bepaalde gegevenspartner gegevens wil, of kan, ontvangen.

Zie [Hoe te om een Type van Bestemming te kiezen](../../features/destinations/destinations.md) voor meer informatie .
