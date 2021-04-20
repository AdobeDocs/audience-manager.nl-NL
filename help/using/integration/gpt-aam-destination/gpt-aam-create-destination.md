---
description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via integratie op de client (browser) of via integratie op de server. Als u kiest voor integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.
seo-description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via integratie op de client (browser) of via integratie op de server. Als u kiest voor integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.
seo-title: Een GPT-bestemming maken
solution: Audience Manager
title: Een GPT-bestemming maken
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 7%

---

# Een GPT-bestemming maken {#create-a-gpt-destination}

U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] verzenden via integratie op de client (browser-side) of via integratie op de server. Als u kiest voor integratie op de client, moet u een doel op cookie maken voor [!DNL Google Publisher Tags] in Audience Manager.

## Bestemmingen 

In Audience Manager is een *`destination`* elk ander systeem (advertentieserver, [!DNL DSP], netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van de Audience Manager worden gevestigd in *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Klik **[!UICONTROL Add New Destination]** en volg de onderstaande stappen om aan de slag te gaan.

## Basisinformatie

De sectie [!UICONTROL Basic Information] voltooien:

1. Geef het doel een naam.
1. Selecteer **[!UICONTROL "Cookie"]** in de vervolgkeuzelijst [!UICONTROL Type].
1. Klik op **[!UICONTROL Next]** en ga naar de secties [!UICONTROL Configuration] en [!UICONTROL Segment Mappings].

## Cookie-configuratie

Geef het volgende op om de sectie [!UICONTROL Configuration] te voltooien (andere velden zijn optioneel):

1. **Naam cookie:** Geef een korte, beschrijvende naam op voor uw cookie.
1. **Gegevensindeling:** Selecteer de  **[!UICONTROL "Single Key"]** optie.
1. **Sleutel:** Geef een sleutelnaam op.
1. **Serienummering:** selecteer het  **[!UICONTROL Enable]** selectievakje.
1. **Seriescheidingsteken:Alleen een komma** gebruiken.

## Segmenttoewijzingen

Een segment toevoegen aan een cookiebestemming:

1. Segmenten zoeken: De sectie [!UICONTROL Segment Mappings] bevat twee zoekgereedschappen waarmee u segmenten kunt zoeken. Een segment zoeken:

   * Optie 1: Typ een segmentnaam in het zoekveld. Het veld wordt automatisch bijgewerkt op basis van ingevoerde tekst. Klik **[!UICONTROL Add]** zodra u het segment vindt u wilt gebruiken.
   * Optie 2: Klik **[!UICONTROL Browse All Segments]** om een venster te openen dat u voor segmenten door naam of opslagplaats laat doorbladeren. Klik **[!UICONTROL Add Selected Segments]** wanneer gereed.

1. **Toewijzingen toevoegen:** Voer in het pop-upmenu Toewijzingen de segment-id in het toewijzingsveld in en klik op  **[!UICONTROL Save]**.

1. Klik op **[!UICONTROL Done]**.
