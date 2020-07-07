---
description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via integratie op de client (browser) of via integratie op de server. Als u kiest voor integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.
seo-description: U kunt gekwalificeerde segmenten naar Google Ad Manager verzenden via integratie op de client (browser) of via integratie op de server. Als u kiest voor integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.
seo-title: Een GPT-bestemming maken
solution: Audience Manager
title: Een GPT-bestemming maken
uuid: e3bbf327-a7e0-48da-bc84-8f531b7f6750
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '323'
ht-degree: 7%

---


# Een GPT-bestemming maken {#create-a-gpt-destination}

U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] een client-side (browser-side) integratie of een server-side integratie sturen. Als u de client-side integratie kiest, moet u een op cookies gebaseerde bestemming maken voor [!DNL Google Publisher Tags] in Audience Manager.

## Bestemmingen 

In Audience Manager, *`destination`* is een ander systeem (ad server, [!DNL DSP], en netwerk, enz.) waarmee u data wilt delen. [!UICONTROL Destination Builder] biedt de gereedschappen waarmee u deze processen voor gegevenslevering kunt maken en beheren. De bestemmingseigenschappen van de Audience Manager worden gevestigd in *[!UICONTROL Audience Data]>[!UICONTROL Destinations]*. Klik op de onderstaande stappen **[!UICONTROL Add New Destination]**en volg deze om aan de slag te gaan.

## Basisinformatie

De [!UICONTROL Basic Information] sectie voltooien:

1. Geef het doel een naam.
1. Selecteer een optie **[!UICONTROL "Cookie"]** in de [!UICONTROL Type] vervolgkeuzelijst.
1. Klik **[!UICONTROL Next]** en ga naar de [!UICONTROL Configuration] en [!UICONTROL Segment Mappings] secties.

## Cookie-configuratie

Geef het volgende op om de [!UICONTROL Configuration] sectie in te vullen (andere velden zijn optioneel):

1. **Naam cookie:** Geef een korte, beschrijvende naam op voor uw cookie.
1. **Gegevensindeling:** Selecteer de **[!UICONTROL "Single Key"]** optie.
1. **Sleutel:** Geef een sleutelnaam op.
1. **Serienummering:** Schakel het **[!UICONTROL Enable]** selectievakje in.
1. **Seriële scheidingsteken:** Gebruik alleen een komma.

## Segmenttoewijzingen

Een segment toevoegen aan een cookiebestemming:

1. Segmenten zoeken: De [!UICONTROL Segment Mappings] sectie bevat twee zoekgereedschappen waarmee u segmenten kunt zoeken. Een segment zoeken:

   * Optie 1: Typ een segmentnaam in het zoekveld. Het veld wordt automatisch bijgewerkt op basis van ingevoerde tekst. Klik **[!UICONTROL Add]** zodra u het segment vindt u wilt gebruiken.
   * Optie 2: Klik **[!UICONTROL Browse All Segments]** om een venster te openen waarin u naar segmenten kunt bladeren op naam of opslaglocatie. Klik **[!UICONTROL Add Selected Segments]** wanneer gereed.

1. **Toewijzingen toevoegen:** Voer in het pop-upmenu Toewijzingen de segment-id in het toewijzingsveld in en klik op **[!UICONTROL Save]**.

1. Klik op **[!UICONTROL Done]**.