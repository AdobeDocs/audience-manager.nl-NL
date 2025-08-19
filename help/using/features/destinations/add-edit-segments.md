---
description: De Etiketten van de Uitvoer van gegevens werken met de Controles van de Uitvoer u op een gegevensbron plaatst. De Etiketten van de Uitvoer van gegevens verhinderen u beperkte eigenschappen aan een segment toe te voegen en segmentgegevens naar een bestemming te verzenden. U kunt meerdere exportlabels instellen op een nieuw of bestaand cookie- of URL-doel.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add or Edit Segments for Server-to-Server Destinations
solution: Audience Manager
title: Segmenten voor server-naar-server doelen toevoegen of bewerken
feature: Destination Basics
exl-id: 20124779-e14b-4d17-be4b-9f17ee0dc19e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '202'
ht-degree: 0%

---

# Segmenten voor server-naar-server doelen toevoegen of bewerken {#add-edit-segments}

U kunt segmenten voor een server-aan-server ([!DNL S2S]) bestemming slechts toevoegen of uitgeven. U kunt geen [!DNL S2S] doelen maken met [[!UICONTROL Destination Builder]](/help/using/features/destinations/destination-builder.md) . Neem contact op met uw consultant om [!DNL S2S] -doelen in te stellen. Volg deze instructies om segmenten voor een [!DNL S2S] -doel toe te voegen of te bewerken.

<!-- destination-s2s-edit.xml -->

U kunt als volgt segmenttoewijzingen voor een [!DNL S2S] -doel toevoegen of bewerken:

1. Ga naar **[!UICONTROL Audience Data > Destinations]** . Selecteer **Geïntegreerde Platforms > Op apparaat-Gebaseerde** en vind de [!DNL S2S] bestemming u met wilt werken.
2. Klik in de kolom [!UICONTROL Action] op het potloodpictogram om het doel te bewerken.
   * Typ in het vak **[!UICONTROL Search and Add Segments]** de naam van een segment of klik op **[!UICONTROL Browse All Segments]** om door een lijst met beschikbare segmenten te bladeren.
   * Klik op **[!UICONTROL Add Selected Segments]** wanneer u het gewenste segment vindt. Als u een segment toevoegt, wordt het venster [!UICONTROL Edit Mapping] geopend.
   * In [!UICONTROL Edit Mapping]:
      * **[!UICONTROL Mappings]**: Plaats een waarde voor het [ zeer belangrijk-waardepaar ](../../features/destinations/key-value-pairs.md) dat door deze bestemming wordt gebruikt.
      * **[!UICONTROL Start Date]** en **[!UICONTROL End Date]**: kies een begin- en einddatum voor het doel. Als de einddatum leeg is, verloopt de bestemming nooit.
3. Klik op **[!UICONTROL Save]** en vervolgens op **[!UICONTROL Done]** .
