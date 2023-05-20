---
description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via integratie op de client (browser) of via integratie op de server. Als u kiest voor de integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.
seo-description: You can send qualified segments to Google Ad Manager through a client-side (browser-side) integration, or a server-side integration. If you choose the client-side integration, you must create a cookie-based destination for Google Publisher Tags in Audience Manager.
seo-title: Create a GPT Destination
solution: Audience Manager
title: Een GPT-bestemming maken
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third-party Integration
exl-id: 26373826-de06-49e5-82fd-bb6588a73fb9
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '282'
ht-degree: 6%

---

# Een GPT-bestemming maken {#create-a-gpt-destination}

U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] via een clientintegratie (browser-side) of een serverintegratie. Als u kiest voor de integratie op de client, moet u een doel op cookie maken voor [!DNL Google Publisher Tags] in de Audience Manager.

## Bestemmingen 

In de Audience Manager *`destination`* is een ander systeem (advertentieserver), [!DNL DSP], en netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van de Audience Manager worden gevestigd in *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Klik op **[!UICONTROL Add New Destination]** en volgt u de onderstaande stappen.

## Basisinformatie

Als u het dialoogvenster [!UICONTROL Basic Information] sectie:

1. Geef het doel een naam.
1. Selecteren **[!UICONTROL "Cookie"]** van de [!UICONTROL Type] vervolgkeuzelijst.
1. Klikken **[!UICONTROL Next]** en gaat u verder naar de [!UICONTROL Configuration] en [!UICONTROL Segment Mappings] secties.

## Cookie-configuratie

Geef het volgende op om de [!UICONTROL Configuration] sectie (andere velden zijn optioneel):

1. **Naam cookie:** Geef een korte, beschrijvende naam op voor uw cookie.
1. **Gegevensindeling:** Selecteer **[!UICONTROL "Single Key"]** optie.
1. **Sleutel:** Geef een sleutelnaam op.
1. **Serienummering:** Selecteer **[!UICONTROL Enable]** selectievakje.
1. **Seriële scheidingsteken:** Gebruik alleen een komma.

## Segmenttoewijzingen

Een segment toevoegen aan een cookiebestemming:

1. Segmenten zoeken: De [!UICONTROL Segment Mappings] de sectie verstrekt twee onderzoekshulpmiddelen helpen van segmenten de plaats bepalen. Een segment zoeken:

   * Optie 1: Typ een segmentnaam in het zoekveld. Het veld wordt automatisch bijgewerkt op basis van ingevoerde tekst. Klikken **[!UICONTROL Add]** wanneer u het segment vindt u wilt gebruiken.
   * Optie 2: Klikken **[!UICONTROL Browse All Segments]** om een venster te openen dat u naar segmenten op naam of opslagplaats laat doorbladeren. Klikken **[!UICONTROL Add Selected Segments]** wanneer gereed.

1. **Toewijzingen toevoegen:** Voer in het pop-upmenu Toewijzingen de segment-id in het toewijzingsveld in en klik op **[!UICONTROL Save]**.

1. Klik op **[!UICONTROL Done]**.
