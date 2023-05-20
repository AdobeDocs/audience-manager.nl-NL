---
description: De Etiketten van de Uitvoer van gegevens werken met de Controles van de Uitvoer u op een gegevensbron plaatst. De Etiketten van de Uitvoer van gegevens verhinderen u beperkte eigenschappen aan een segment toe te voegen en segmentgegevens naar een bestemming te verzenden. U kunt meerdere exportlabels instellen op een nieuw of bestaand cookie- of URL-doel.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: Besturingselementen voor data-export aan een bestemming toevoegen
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 5%

---

# Labels voor gegevensexport toevoegen aan een doel {#add-data-export-labels}

[!DNL Data Export Labels] met de [!DNL Export Controls] u plaatst op een gegevensbron. [!DNL Data Export Labels] verhindert u beperkte eigenschappen aan een segment toe te voegen en segmentgegevens naar een bestemming te verzenden. U kunt meerdere exportlabels instellen op een nieuw of bestaand [!DNL cookie] of [!DNL URL] bestemming.

>[!NOTE]
>
>Als u een exportlabel wilt toevoegen, hebt u beheerdersmachtigingen nodig *of* voldoende rechten om een doel te maken of te bewerken.

<!-- t_export_labels.xml -->

Exportlabels toevoegen aan een doel:

1. Klik op **[!UICONTROL Audience Data]**:
   * Voor nieuwe bestemmingen: Klikken **[!UICONTROL Create New Destination]**. Voltooi de [!UICONTROL Basic Information] voordat u een exportlabel voor gegevens selecteert. Zie [Een doel voor cookies maken](../../features/destinations/create-cookie-destination.md) of [Een URL-doel maken](../../features/destinations/create-url-destination.md) ter informatie.
   * Voor bestaande bestemmingen: Gebruik de [!DNL Search] om uw bestemming te zoeken of door de lijst te scrollen en op de bestemmingsnaam te klikken om het te openen.
1. Selecteer een [!DNL Data Export Label]. Laat de selectievakjes leeg als u geen exportbeperkingen wilt instellen. Exportlabels bevatten de volgende opties:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >Exportbeperkingen werken alleen als u een [overeenkomende exportcontrole](../../features/data-export-controls.md) op een gegevensbron.
1. Klik op **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Een databron maken](../../features/manage-datasources.md#create-data-source)

