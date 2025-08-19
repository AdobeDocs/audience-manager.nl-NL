---
description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via een integratie op de client-side (browser-side) of via een integratie op de server. Als u kiest voor de integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Een GPT-doel maken
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '284'
ht-degree: 0%

---

# Een GPT-doel maken {#create-a-gpt-destination}

U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] verzenden via integratie op de client (browser-side) of via integratie op de server. Als u kiest voor de integratie op de client, moet u in Audience Manager een op cookies gebaseerd doel voor [!DNL Google Publisher Tags] maken.

## Doelen

In Audience Manager is een *`destination`* elk ander systeem (advertentieserver, [!DNL DSP], netwerk, enz.) waarmee u gegevens wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. Audience Manager-doelfuncties vindt u in *[!UICONTROL Audience Data]>[!UICONTROL Destinations]* . Klik op **[!UICONTROL Add New Destination]** en volg de onderstaande stappen om aan de slag te gaan.

## Basisinformatie

De sectie [!UICONTROL Basic Information] voltooien:

1. Geef het doel een naam.
1. Selecteer **[!UICONTROL "Cookie"]** in de vervolgkeuzelijst [!UICONTROL Type] .
1. Klik op **[!UICONTROL Next]** en ga naar de secties [!UICONTROL Configuration] en [!UICONTROL Segment Mappings] .

## Cookie-configuratie

Geef het volgende op om de sectie [!UICONTROL Configuration] te voltooien (andere velden zijn optioneel):

1. **Naam van het Koekje:** verstrek een korte, beschrijvende naam voor uw koekje.
1. **Formaat van Gegevens:** selecteer de **[!UICONTROL "Single Key"]** optie.
1. **Sleutel:** verstrek een zeer belangrijke naam.
1. **Serialize:** selecteer **[!UICONTROL Enable]** checkbox.
1. **Periodieke Scheidingsteken:** gebruik slechts een komma.

## Segmenttoewijzingen

Een segment toevoegen aan een cookiebestemming:

1. Segmenten zoeken: de sectie [!UICONTROL Segment Mappings] bevat twee zoekgereedschappen waarmee u segmenten kunt zoeken. Een segment zoeken:

   * Optie 1: typ een segmentnaam in het zoekveld. Het veld wordt automatisch bijgewerkt op basis van ingevoerde tekst. Klik op **[!UICONTROL Add]** als u het gewenste segment hebt gevonden.
   * Optie 2: klik op **[!UICONTROL Browse All Segments]** om een venster te openen waarin u naar segmenten kunt bladeren op naam of opslaglocatie. Klik op **[!UICONTROL Add Selected Segments]** als u klaar bent.

1. **voegt Toewijzingen toe:** in de afbeeldingen pop, ga segmentidentiteitskaart op het kaartingsgebied in en klik **[!UICONTROL Save]**.

1. Klik op **[!UICONTROL Done]**.
