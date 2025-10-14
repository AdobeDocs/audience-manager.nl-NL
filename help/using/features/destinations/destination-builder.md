---
description: Met Destination Builder kunt u op cookies gebaseerde of DNL URL-doelen maken. U kunt geen server-aan-server (S2S) bestemmingen met de Bouwer van de Bestemming tot stand brengen, maar u kunt hun segmentafbeeldingen beheren. Neem contact op met uw consultant om een S2S-bestemming in te stellen. De Bouwer van de bestemming wordt gevestigd in de Gegevens van het Publiek > Doelen.
seo-description: Destination Builder lets you create cookie-based or DNL URL destinations. You cannot create server-to-server (S2S) destinations with Destination Builder, but you can manage their segment mappings. Contact your consultant to set up a S2S destination. Destination Builder is located in Audience Data > Destinations.
seo-title: Destination Builder
solution: Audience Manager
title: Bestemmingsbouwer
feature: Destination Basics
exl-id: 0923bea3-fb23-45c0-bbb7-5a74f46bf45b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '268'
ht-degree: 0%

---

# Bestemmingsbouwer {#destination-builder}

Met [!UICONTROL Destination Builder] kunt u op cookies gebaseerde of [!DNL URL] doelen maken. U kunt geen server-aan-server ([!DNL S2S]) bestemmingen met [!UICONTROL Destination Builder] tot stand brengen, maar u kunt hun segmentafbeeldingen beheren. Neem contact op met uw consultant om een [!DNL S2S] -bestemming in te stellen. [!UICONTROL Destination Builder] bevindt zich in **[!UICONTROL Audience Data > Destinations]** .

## Instellingen van doelontwikkelaar {#destination-builder-settings}

<!-- destination-builder.xml -->

[!UICONTROL Destination Builder] bestaat uit de volgende secties en instellingen:

| [!UICONTROL Destination Builder] Sectie | Doel |
|--- |--- |
| Basisinformatie | Wordt gebruikt om het doel een naam te geven, het te beschrijven en het doeltype ([!DNL URL] of [!DNL cookie] ) en platform (all, [!DNL Android] , browser of [!DNL iOS]) te selecteren. |
| Configuratie | Bevat besturingselementen voor: <br/><ul><li>Het overgaan in zeer belangrijke-waardegegevens aan [!DNL URL] bestemmingen. U kunt gegevens verzenden als individuele of geserialiseerde sleutel-waardeparen. Voor details zie, [&#x200B; Serienummering van de Bestemming &#x200B;](../../features/destinations/key-value-pairs.md#destination-serialized) en [&#x200B; Standaard en Serie zeer belangrijke - waardeparen &#x200B;](../../features/destinations/key-value-pairs.md). </li><li>Elementen van een cookiebestemming, zoals de naam, het domein, de grootte, het vervalinterval, de gegevensindeling, enz.</li></ul> |
| Segmenttoewijzingen | Hier volgt u: <br/><ul><li>Zoek, voeg, en beheer segmenten toe verbonden aan alle bestemmingstypes. </li><li>Geef leveringsprioriteiten op voor afzonderlijke segmenten (alleen voor op [!DNL cookie] gebaseerde segmenten).</li></ul> |

## Methoden voor gegevenslevering {#data-delivery-methods}

Verzend informatie naar een doel door deze door te geven via een [!DNL URL] -tekenreeks, door naar een browser [!DNL cookie] te schrijven of door gegevens over te dragen van de ene naar de andere offlineserver.

* [!DNL URL] en op cookies gebaseerde doelen verzenden gegevens synchroon, terwijl een gebruiker actie onderneemt op een pagina.
* De server-aan-server gegevenstransmissie is asynchroon en kan voorkomen lang nadat een gebruiker de pagina heeft verlaten. Het leveringstype u selecteert hangt van uw bedrijfsvereisten af en hoe een bepaalde gegevenspartner gegevens wil, of kan, ontvangen.

Zie [&#x200B; hoe te om een Type van Bestemming &#x200B;](../../features/destinations/destinations.md) voor meer informatie te kiezen.
