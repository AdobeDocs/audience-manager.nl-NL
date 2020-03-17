---
description: Beschrijft de gevolgen op gesegmenteerde gebruikers, gegevens, en bestemmingen wanneer u pauzeert of een actief segment schrapt gebruikend de Bouwer van het Segment.
seo-description: Beschrijft de gevolgen op gesegmenteerde gebruikers, gegevens, en bestemmingen wanneer u pauzeert of een actief segment schrapt gebruikend de Bouwer van het Segment.
seo-title: Gepauzeerde en verwijderde segmenten
solution: Audience Manager
title: Gepauzeerde en verwijderde segmenten
uuid: 88efe4af-f9a4-4bce-920a-352bd4d505dd
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Gepauzeerde en verwijderde segmenten {#paused-and-deleted-segments}

Beschrijft de gevolgen op gesegmenteerde gebruikers, gegevens, en bestemmingen wanneer u pauzeert of een actief segment schrapt gebruikend [!UICONTROL Segment Builder].

## Toegang tot de besturingselementen Pauzeren en Verwijderen

Houd de muisaanwijzer boven een segmentnaam in de lijst met segmenten om de **[!UICONTROL pause]** pictogrammen en **[!UICONTROL delete]** pictogrammen (in de [!UICONTROL Actions] kolom) weer te geven. Deze functies zijn van invloed op segmenten zoals hieronder wordt beschreven.

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
>U kunt segmenten ook pauzeren en verwijderen met een [!DNL API] methode. Zie [REST API&#39;s](../../api/rest-api-main/rest-api-main.md)voor meer informatie.