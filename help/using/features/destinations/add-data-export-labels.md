---
description: De Etiketten van de Uitvoer van gegevens werken met de Controles van de Uitvoer u op een gegevensbron plaatst. De Etiketten van de Uitvoer van gegevens verhinderen u beperkte eigenschappen aan een segment toe te voegen en segmentgegevens naar een bestemming te verzenden. U kunt meerdere exportlabels instellen op een nieuw of bestaand cookie- of URL-doel.
seo-description: Data Export Labels work with the Export Controls you set on a data source. Data Export Labels prevent you from adding restricted traits to a segment and from sending segment data to a destination. You can set multiple export labels to a new or existing cookie or URL destination.
seo-title: Add Data Export Controls to a Destination
solution: Audience Manager
title: De Controles van de Uitvoer van Gegevens aan een Doel toevoegen
feature: Data Export Controls
exl-id: 12cfd2cc-b343-4dd1-a188-acbfc5cd25a2
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '221'
ht-degree: 2%

---

# Labels voor gegevensexport toevoegen aan een doel {#add-data-export-labels}

[!DNL Data Export Labels] werkt met de [!DNL Export Controls] die u op een gegevensbron instelt. [!DNL Data Export Labels] verhindert u beperkte eigenschappen aan een segment toe te voegen en segmentgegevens naar een bestemming te verzenden. U kunt meerdere exportlabels instellen op een nieuw of bestaand [!DNL cookie] - of [!DNL URL] -doel.

>[!NOTE]
>
>Om een uitvoeretiket toe te voegen, hebt u beheerdertoestemmingen *of* voldoende voorrechten nodig om een bestemming tot stand te brengen of uit te geven.

<!-- t_export_labels.xml -->

Exportlabels toevoegen aan een doel:

1. Klik op **[!UICONTROL Audience Data]** :

   * Voor nieuwe doelen: klik op **[!UICONTROL Create New Destination]** . Vul de sectie [!UICONTROL Basic Information] in voordat u een label voor het exporteren van gegevens selecteert. Zie [ een Bestemming van het Koekje ](../../features/destinations/create-cookie-destination.md) of [ creëren een Doel URL ](../../features/destinations/create-url-destination.md) voor informatie.
   * Voor bestaande doelen: gebruik het vak [!DNL Search] om het doel te zoeken of door de lijst te bladeren en op de doelnaam te klikken om het te openen.

1. Selecteer een [!DNL Data Export Label] . Laat de selectievakjes leeg als u geen exportbeperkingen wilt instellen. Exportlabels bevatten de volgende opties:

   * **[!UICONTROL This destination may enable a combination with personally identifiable information (PII)]**
   * **[!UICONTROL This destination may be used for on-site ad targeting]**
   * **[!UICONTROL This destination may be used for off-site ad targeting]**
   * **[!UICONTROL This destination may be used for on-site ad personalization]**

   >[!IMPORTANT]
   >
   >De beperkingen van de uitvoer zullen niet werken tenzij u a [ passende uitvoercontrole ](../../features/data-export-controls.md) op een gegevensbron plaatst.

1. Klik op **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Een databron maken](../../features/manage-datasources.md#create-data-source)
