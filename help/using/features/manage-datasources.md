---
description: Als u een nieuwe gegevensbron wilt maken, gaat u naar Poortgegevens > Gegevensbronnen > Nieuwe toevoegen en voert u de stappen voor elke hier beschreven sectie in. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.
keywords: gegevensbronnen;gegevensbron beheren;doelbeheergegevensbron
seo-description: To create a new data source, go to Audience Data > Data Sources > Add New and complete the steps for each section described here. Administrator permissions are required to create a data source.
seo-title: Create a Data Source
solution: Audience Manager
title: Gegevensbronnen beheren
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 6ec76227dd8c7581550c3d95e24fc5b6a4b01093
workflow-type: tm+mt
source-wordcount: '389'
ht-degree: 0%

---

# Beheren [!UICONTROL Data Sources] {#manage-data-sources}

## Een [!UICONTROL Data Source] {#create-data-source}

Een nieuwe [!UICONTROL data source], ga naar **[!UICONTROL Audience Data > Data Sources > Add New]** en voltooi de stappen voor elke hier beschreven sectie. Beheerdersmachtigingen zijn vereist voor het maken van een [!UICONTROL data source].

<!-- create-datasource.xml -->

>[!TIP]
>
>Zie [Instellingen gegevensbron en menuopties](../features/datasources-list-and-settings.md#settings-menu-options) voor beschrijvingen van deze verschillende besturingselementen.

## [!UICONTROL Data Source] Details {#details}

Als u het dialoogvenster [!UICONTROL Data Source Details] sectie:

1. Geef de naam [!UICONTROL data source].
1. *(Optioneel)* Beschrijf het [!UICONTROL data source]. Met een beknopte beschrijving kunt u de rol of het doel van het [!UICONTROL data source].
1. Een [!UICONTROL integration code]. In het algemeen [!UICONTROL integration codes] zijn optioneel. Deze zijn vereist wanneer u wilt:

   * [Een gegevensbron voor meerdere apparaten maken](../features/profile-merge-rules/merge-rules-start.md#create-data-source).
   * Gebruik de [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Werken met [Regels voor samenvoegen van profielen](../features/profile-merge-rules/merge-rules-start.md).

1. Kies een **[!UICONTROL ID Type]**. [!UICONTROL ID Type] opties zijn:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Vereist om een [!UICONTROL Profile Merge Rule]). Voor sommige klanten betekent deze selectie dat de **[!UICONTROL ID Definition]** opties.

   >[!NOTE]
   >
   >Voor elke organisatie die is ingericht voor Audience Manager en Experience Platform, zelfs als u geen segment hebt dat tussen de twee apps wordt gedeeld, wanneer u een gegevensbron voor meerdere apparaten maakt, een overeenkomstige [naamruimte identity](https://experienceleague.adobe.com/docs/experience-platform/identity/namespaces.html#manage-namespaces) wordt gemaakt in Experience Platform.

1. Kies een **[!UICONTROL ID Definition]** optie. De volgende opties zijn beschikbaar:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[Besturingselementen voor gegevensexport](../features/data-export-controls.md) zijn optionele classificatieregels die u kunt toepassen op een [!UICONTROL data source] en [!UICONTROL destination]. Ze verhinderen dat u gegevens naar een [!UICONTROL destination] wanneer die handeling een inbreuk vormt op een privacyovereenkomst of een gebruiksovereenkomst voor gegevens. Deze sectie overslaan als u deze niet gebruikt [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Instellingen {#settings}

Deze instellingen bepalen hoe een [!UICONTROL data source] wordt geïdentificeerd, gebruikt en gedeeld. U kunt foutrapportage ook inschakelen voor binnenkomende gegevensbestanden. Als u het dialoogvenster [!UICONTROL Data Source Settings] sectie:

1. Selecteer een [!UICONTROL Data Source Setting] selectievakje om een optie toe te passen op uw [!UICONTROL data source].
2. Klik op **[!UICONTROL Save]**.

## Een gegevensbron verwijderen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Een [!UICONTROL data source] die u niet meer nodig hebt.

>[!NOTE]
>
>Houd rekening met de volgende beperkingen:
>
>* U kunt geen [Actief publiek of Gegevensbron gesynchroniseerd gedrag](../features/traits/client-activity-synced-audience-traits.md).
>* Voor klanten die Adobe Analytics gebruiken: Audience Manager staat u niet toe gegevensbronnen te schrappen die automatisch van uw worden gecreeerd [!DNL Analytics] rapportsuites. Gebruik de [Kernservice](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) aan unmap deze gegevensbronnen.


1. Klik op **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Schakel het selectievakje naast een of meer gegevensbronnen in.
U kunt de [!UICONTROL Search] om de gewenste gegevensbronnen te zoeken als u een lange lijst hebt.
1. Klikken  ![](assets/icon_trash.png), bevestig vervolgens de verwijdering.


>[!MORELIKETHIS]
>
>* [Instellingen gegevensbron en menuopties](../features/datasources-list-and-settings.md#settings-menu-options)

