---
description: Met Destination Builder kunt u op cookies gebaseerde of DNL URL-doelen maken. U kunt geen server-aan-server (S2S) bestemmingen met de Bouwer van de Bestemming tot stand brengen, maar u kunt hun segmentafbeeldingen beheren. Neem contact op met uw consultant om een S2S-bestemming in te stellen. De Bouwer van de bestemming wordt gevestigd in de Gegevens van het Publiek > Doelen.
seo-description: Met Destination Builder kunt u op cookies gebaseerde of DNL URL-doelen maken. U kunt geen server-aan-server (S2S) bestemmingen met de Bouwer van de Bestemming tot stand brengen, maar u kunt hun segmentafbeeldingen beheren. Neem contact op met uw consultant om een S2S-bestemming in te stellen. De Bouwer van de bestemming wordt gevestigd in de Gegevens van het Publiek > Doelen.
seo-title: Bestemmingsbouwer
solution: Audience Manager
title: Bestemmingsbouwer
translation-type: tm+mt
source-git-commit: 6f13bc32f00c81a67026bcedd72badbf536311e1

---


# Bestemmingsbouwer {#destination-builder}

[!UICONTROL Destination Builder] Hiermee kunt u op cookies gebaseerde of [!DNL URL] doelen maken. U kunt geen server-aan-server ([!DNL S2S]) bestemmingen met tot stand brengen [!UICONTROL Destination Builder], maar u kunt hun segmentafbeeldingen beheren. Neem contact op met uw consultant om een [!DNL S2S] bestemming in te stellen. [!UICONTROL Destination Builder] bevindt zich in **[!UICONTROL Audience Data > Destinations]**.

## Instellingen van doelontwikkelaar {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] bestaat uit de volgende secties en instellingen:

| [!UICONTROL Destination Builder] Sectie | Doel |
|--- |--- |
| Basisinformatie | Wordt gebruikt om het doel een naam te geven, het te beschrijven en het doeltype ([!DNL URL] of [!DNL cookie]) en platform (all, [!DNL Android], browser of [!DNL iOS]) te selecteren. |
| Configuratie | Omvat besturingselementen voor: <br/><ul><li>Het overgaan in zeer belangrijke-waardegegevens aan [!DNL URL] bestemmingen. U kunt gegevens verzenden als individuele of geserialiseerde sleutel-waardeparen. Voor details zie, [de Rangschikking](../../features/destinations/key-value-pairs.md#destination-serialized) van de Bestemming en [Standaard en Serie zeer belangrijke-waardeparen](../../features/destinations/key-value-pairs.md). </li><li>Elementen van een cookiebestemming, zoals de naam, het domein, de grootte, het vervalinterval, de gegevensindeling, enz.</li></ul> |
| Segmenttoewijzingen | Hiermee kunt u: <br/><ul><li>Zoek, voeg, en beheer segmenten toe verbonden aan alle bestemmingstypes. </li><li>Stel de leveringsprioriteiten voor afzonderlijke segmenten in (alleen voor [!DNL cookie]gebaseerde segmenten).</li></ul> |

## Methoden voor gegevenslevering {#data-delivery-methods}

Verzend informatie naar een bestemming door het binnen door een [!DNL URL] koord, door te schrijven aan browser [!DNL cookie], of door off-line server-aan-server gegevensoverdrachten over te gaan.

* [!DNL URL] en op cookies gebaseerde doelen verzenden gegevens synchroon, terwijl een gebruiker actie onderneemt op een pagina.
* De server-aan-server gegevenstransmissie is asynchroon en kan voorkomen lang nadat een gebruiker de pagina heeft verlaten. Het leveringstype u selecteert hangt van uw bedrijfsvereisten af en hoe een bepaalde gegevenspartner gegevens wil, of kan, ontvangen.

Zie [hoe te om een Type](../../features/destinations/destinations.md) van Bestemming voor meer informatie te kiezen.