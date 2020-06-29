---
description: De Etiketten van de Uitvoer van gegevens werken met de Controles van de Uitvoer u op een gegevensbron plaatst. De Etiketten van de Uitvoer van gegevens verhinderen u beperkte eigenschappen aan een segment toe te voegen en segmentgegevens naar een bestemming te verzenden. U kunt meerdere exportlabels instellen op een nieuw of bestaand cookie- of URL-doel.
seo-description: De Etiketten van de Uitvoer van gegevens werken met de Controles van de Uitvoer u op een gegevensbron plaatst. De Etiketten van de Uitvoer van gegevens verhinderen u beperkte eigenschappen aan een segment toe te voegen en segmentgegevens naar een bestemming te verzenden. U kunt meerdere exportlabels instellen op een nieuw of bestaand cookie- of URL-doel.
seo-title: De Controles van de Uitvoer van Gegevens aan een Bestemming toevoegen
solution: Audience Manager
title: De Controles van de Uitvoer van Gegevens aan een Bestemming toevoegen
feature: Data Export Controls
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '277'
ht-degree: 0%

---



# Labels voor gegevensexport toevoegen aan een doel {#add-data-export-labels}

[!DNL Data Export Labels] werken met de gegevensbron die [!DNL Export Controls] u instelt. [!DNL Data Export Labels] verhindert u beperkte eigenschappen aan een segment toe te voegen en segmentgegevens naar een bestemming te verzenden. U kunt meerdere exportlabels instellen op een nieuw of bestaand [!DNL cookie] of een [!DNL URL] doel.

>[!NOTE]
>
>Als u een exportlabel wilt toevoegen, hebt u beheerdersmachtigingen *of* voldoende rechten nodig om een doel te maken of te bewerken.

<!-- t_export_labels.xml -->

Exportlabels toevoegen aan een doel:

1. Klik op **[!UICONTROL Audience Data]**:
   * Voor nieuwe bestemmingen: Klik **[!UICONTROL Create New Destination]**. Vul de [!UICONTROL Basic Information] sectie in voordat u een label voor gegevensexport selecteert. Zie [Een doel](../../features/destinations/create-cookie-destination.md) voor cookies maken of [Een doel](../../features/destinations/create-url-destination.md) voor URL maken voor meer informatie.
   * Voor bestaande bestemmingen: Gebruik het [!DNL Search] vakje om uw bestemming te vinden of door de lijst te scrollen en op de bestemmingsnaam te klikken om het te openen.
1. Selecteer een [!DNL Data Export Label]. Laat de selectievakjes leeg als u geen exportbeperkingen wilt instellen. Exportlabels bevatten de volgende opties:
   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**
   >[!IMPORTANT]
   >
   >Exportbeperkingen werken alleen als u een [overeenkomend exportbesturingselement](../../features/data-export-controls.md) voor een gegevensbron instelt.
1. Klik op **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Een gegevensbron maken](../../features/manage-datasources.md#create-data-source)