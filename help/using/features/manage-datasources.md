---
description: Als u een nieuwe gegevensbron wilt maken, gaat u naar Poortgegevens > Gegevensbronnen > Nieuwe toevoegen en voert u de stappen voor elke sectie uit die hier wordt beschreven. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.
keywords: gegevensbronnen;gegevensbron beheren;doelbeheergegevensbron
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Gegevensbronnen beheren
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: e41dddd022b6fa02cab3e16bd21536d41584975f
workflow-type: tm+mt
source-wordcount: '372'
ht-degree: 0%

---

# [!UICONTROL Data Sources] beheren {#manage-data-sources}

## Een [!UICONTROL Data Source] maken {#create-data-source}

Als u een nieuwe [!UICONTROL data source] wilt maken, gaat u naar **[!UICONTROL Audience Data > Data Sources > Add New]** en voert u de stappen uit voor elke sectie die hier wordt beschreven. Beheerdersmachtigingen zijn vereist voor het maken van een [!UICONTROL data source] .

<!-- create-datasource.xml -->

>[!TIP]
>
>Zie {de Montages van Source van 0} Gegevens en de Opties van het Menu ](../features/datasources-list-and-settings.md#settings-menu-options) voor beschrijvingen van deze verschillende controles.[

## [!UICONTROL Data Source] Details {#details}

De sectie [!UICONTROL Data Source Details] voltooien:

1. Geef de [!UICONTROL data source] een naam.
1. *(Facultatief)* beschrijf [!UICONTROL data source]. Met een beknopte beschrijving kunt u de rol of het doel van de [!UICONTROL data source] definiëren.
1. Geef een [!UICONTROL integration code] op. Over het algemeen is [!UICONTROL integration codes] optioneel. Deze zijn vereist wanneer u wilt:

   * [ creeer een dwars-apparatengegevensbron ](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Gebruik de [ Dienst van de Identiteit van Adobe Experience Platform ](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Het werk met [ Regels van de Fusie van het Profiel ](../features/profile-merge-rules/merge-rules-start.md).

1. Kies een **[!UICONTROL ID Type]** . [!UICONTROL ID Type] -opties zijn:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Vereist om een [!UICONTROL Profile Merge Rule] te maken). Voor sommige klanten worden met deze selectie de **[!UICONTROL ID Definition]** -opties weergegeven.

   >[!NOTE]
   >
   >Voor elke organisatie die voor Audience Manager en Experience Platform provisioned is, zelfs als u geen segment het delen opstelling tussen twee apps hebt, wanneer u een dwars-apparatengegevensbron creeert, wordt een overeenkomstige [ identiteit namespace ](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) gecreeerd in Experience Platform.

1. Kies een optie **[!UICONTROL ID Definition]** . U kunt onder andere de volgende opties kiezen:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[ de Controles van de Uitvoer van Gegevens ](../features/data-export-controls.md) zijn facultatieve classificatieregels u op a [!UICONTROL data source] en [!UICONTROL destination] kunt toepassen. Hiermee voorkomt u dat u gegevens naar een [!UICONTROL destination] verzendt wanneer die handeling een schending van de privacy van gegevens of een gebruiksovereenkomst oplevert. Sla deze sectie over als u [!UICONTROL Data Export Controls] niet gebruikt.

## [!UICONTROL Data Source] Instellingen {#settings}

Deze instellingen bepalen hoe een [!UICONTROL data source] wordt geïdentificeerd, gebruikt en gedeeld. U kunt foutrapportage ook inschakelen voor binnenkomende gegevensbestanden. De sectie [!UICONTROL Data Source Settings] voltooien:

1. Schakel een selectievakje [!UICONTROL Data Source Setting] in om een optie toe te passen op de [!UICONTROL data source] .
2. Klik op **[!UICONTROL Save]**.

## Source voor gegevens verwijderen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Verwijder een [!UICONTROL data source] die u niet meer nodig hebt.

>[!NOTE]
>
>Houd rekening met de volgende beperkingen:
>
>* U kunt geen [ Actief Publiek of Gegevens Source Gesynchroniseerd Spoor ](../features/traits/client-activity-synced-audience-traits.md) schrappen.
>* Voor klanten die Adobe Analytics gebruiken: met Audience Manager kunt u geen gegevensbronnen verwijderen die automatisch zijn gemaakt op basis van uw [!DNL Analytics] -rapportsuite. Gebruik de [ Dienst van de Kern ](https://experienceleague.adobe.com/en/docs/core-services/interface/services/customer-attributes/attributes) om deze gegevensbronnen unmap.

1. Klik op **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]** .
1. Schakel het selectievakje naast een of meer gegevensbronnen in.
U kunt het vak [!UICONTROL Search] gebruiken om de gewenste gegevensbronnen te zoeken als u een lange lijst hebt.
1. Klik op ![](assets/icon_trash.png) en bevestig vervolgens de verwijdering.


>[!MORELIKETHIS]
>
>* [ de Montages van Source van Gegevens en de Opties van het Menu ](../features/datasources-list-and-settings.md#settings-menu-options)
