---
description: Beschrijft de gevolgen op gesegmenteerde gebruikers, gegevens, en bestemmingen wanneer u pauzeert of een actief segment schrapt gebruikend de Bouwer van het Segment.
seo-description: Describes the effects on segmented users, data, and destinations when you pause or delete an active segment using Segment Builder.
seo-title: Paused and Deleted Segments
solution: Audience Manager
title: Gepauzeerde en verwijderde segmenten
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
feature: Segments
exl-id: 994da89c-c9db-4cd5-b2bc-cfda231e5f2d
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '187'
ht-degree: 0%

---

# Gepauzeerde en verwijderde segmenten {#paused-and-deleted-segments}

Beschrijft de gevolgen op gesegmenteerde gebruikers, gegevens, en bestemmingen wanneer u pauzeert of een actief segment schrapt gebruikend [!UICONTROL Segment Builder].

## Toegang tot de besturingselementen Pauzeren en Verwijderen

Houd de muisaanwijzer boven een segmentnaam in de lijst met segmenten om de pictogrammen **[!UICONTROL pause]** en **[!UICONTROL delete]** weer te geven (in de kolom [!UICONTROL Actions] ). Deze functies zijn van invloed op segmenten zoals hieronder wordt beschreven.

## Functionaliteit gepauzeerd segment

Een gepauzeerd (gedeactiveerd) segment:

* Stopt het segmenteren van nieuwe, gekwalificeerde gebruikers.
* Hiermee behoudt u de segmentatiestatus/het lidmaatschap van een gebruiker (verwijdert een gebruiker niet uit het segment).
* Behoudt zich in de segmentlijst en kan opnieuw worden geactiveerd.
* Verzendt geen gegevens naar bijbehorende bestemmingen.
* Geeft gegevens in de beschikbare rapporten (tot en met de datum van deactivering).

## Verwijderde segmentfunctionaliteit

Een verwijderd segment:

* Stopt het segmenteren van nieuwe, gekwalificeerde gebruikers.
* Verwijdert gekwalificeerde gebruikers uit segmentlidmaatschap.
* Is verwijderd uit de segmentlijst.
* Kan niet verwijderen.
* Verzendt geen gegevens naar bijbehorende bestemmingen.
* Retourneert geen gegevens in de beschikbare rapporten.

>[!NOTE]
>
>U kunt segmenten ook pauzeren en verwijderen met de methode [!DNL API] . Voor meer informatie, zie [&#x200B; REST APIs &#x200B;](../../api/rest-api-main/rest-api-main.md).
