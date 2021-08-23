---
description: Als u een nieuwe gegevensbron wilt maken, gaat u naar Poortgegevens > Gegevensbronnen > Nieuwe toevoegen en voert u de stappen voor elke hier beschreven sectie in. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.
keywords: gegevensbronnen;gegevensbron beheren;doelbeheergegevensbron
seo-description: Als u een nieuwe gegevensbron wilt maken, gaat u naar Poortgegevens > Gegevensbronnen > Nieuwe toevoegen en voert u de stappen voor elke hier beschreven sectie in. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.
seo-title: Een databron maken
solution: Audience Manager
title: Gegevensbronnen beheren
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Databronnen
exl-id: 1c20988e-4a09-4d56-b454-d48b75eed1ce
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '378'
ht-degree: 2%

---

# [!UICONTROL Data Sources] beheren {#manage-data-sources}

## Een [!UICONTROL Data Source] maken {#create-data-source}

Als u een nieuwe [!UICONTROL data source] wilt maken, gaat u naar **[!UICONTROL Audience Data > Data Sources > Add New]** en voert u de stappen uit voor elke sectie die hier wordt beschreven. Beheerdersmachtigingen zijn vereist om een [!UICONTROL data source] te maken.

<!-- create-datasource.xml -->

>[!TIP]
>
>Zie [Instellingen gegevensbron en menuopties](../features/datasources-list-and-settings.md#settings-menu-options) voor beschrijvingen van deze verschillende besturingselementen.

## [!UICONTROL Data Source] Details {#details}

De sectie [!UICONTROL Data Source Details] voltooien:

1. Geef de [!UICONTROL data source] een naam.
1. *(Optioneel)* Beschrijf de  [!UICONTROL data source]code. Een beknopte beschrijving helpt u de rol of het doel van [!UICONTROL data source] bepalen.
1. Geef een [!UICONTROL integration code] op. In het algemeen is [!UICONTROL integration codes] optioneel. Deze zijn vereist wanneer u wilt:

   * [Maak een gegevensbron](../features/profile-merge-rules/merge-rules-start.md#create-data-source) voor alle apparaten.
   * Gebruik [Adobe Experience Platform Identity Service](https://experienceleague.adobe.com/docs/id-service/using/home.html).
   * Werken met [Regels voor het samenvoegen van profielen](../features/profile-merge-rules/merge-rules-start.md).

1. Kies een **[!UICONTROL ID Type]**. [!UICONTROL ID Type] opties zijn:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Vereist om een  [!UICONTROL Profile Merge Rule]) te maken. Voor sommige klanten worden met deze selectie de opties **[!UICONTROL ID Definition]** weergegeven.

1. Kies een optie **[!UICONTROL ID Definition]**. De volgende opties zijn beschikbaar:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[De Controles van de Uitvoer van gegevens ](../features/data-export-controls.md) zijn facultatieve classificatieregels u op een  [!UICONTROL data source] en  [!UICONTROL destination]. Ze verhinderen dat u gegevens naar een [!UICONTROL destination] verzendt wanneer die handeling een inbreuk vormt op een privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u [!UICONTROL Data Export Controls] niet gebruikt.

## [!UICONTROL Data Source] Instellingen {#settings}

Deze instellingen bepalen hoe een [!UICONTROL data source] wordt geïdentificeerd, gebruikt en gedeeld. U kunt foutrapportage ook inschakelen voor binnenkomende gegevensbestanden. De sectie [!UICONTROL Data Source Settings] voltooien:

1. Schakel een selectievakje [!UICONTROL Data Source Setting] in om een optie toe te passen op uw [!UICONTROL data source].
2. Klik op **[!UICONTROL Save]**.

## Een gegevensbron verwijderen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Verwijder een [!UICONTROL data source] die u niet meer nodig hebt.

>[!NOTE]
>
>Houd rekening met de volgende beperkingen:
>
>* U kunt geen [Actieve Audience of Gegevensbron Gesynchroniseerd Spoor](../features/traits/client-activity-synced-audience-traits.md) schrappen.
>* Voor klanten die Adobe Analytics gebruiken: Audience Manager staat u niet toe om gegevensbronnen te schrappen die automatisch van uw [!DNL Analytics] rapportreeksen worden gecreeerd. Gebruik [Core Service](https://experienceleague.adobe.com/docs/core-services/interface/about-core-services/core-services-landing.html) om deze gegevensbronnen uit de kaart te halen.


1. Klik op **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Schakel het selectievakje naast een of meer gegevensbronnen in.
U kunt het vakje [!UICONTROL Search] gebruiken om van de gewenste gegevensbronnen de plaats te bepalen als u een lange lijst hebt.
1. Klik ![](assets/icon_trash.png), dan bevestig de schrapping.


>[!MORELIKETHIS]
>
>* [Instellingen gegevensbron en menuopties](../features/datasources-list-and-settings.md#settings-menu-options)

