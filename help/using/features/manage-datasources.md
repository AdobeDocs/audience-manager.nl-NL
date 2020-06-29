---
description: Als u een nieuwe gegevensbron wilt maken, gaat u naar Poortgegevens > Gegevensbronnen > Nieuwe toevoegen en voert u de stappen voor elke hier beschreven sectie in. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.
keywords: data sources;manage data source;audience manager data source
seo-description: Als u een nieuwe gegevensbron wilt maken, gaat u naar Poortgegevens > Gegevensbronnen > Nieuwe toevoegen en voert u de stappen voor elke hier beschreven sectie in. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.
seo-title: Een gegevensbron maken
solution: Audience Manager
title: Gegevensbronnen beheren
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
feature: Data Sources
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '371'
ht-degree: 0%

---


# Beheren [!UICONTROL Data Sources] {#manage-data-sources}

## Een [!UICONTROL Data Source] {#create-data-source}

Als u een nieuwe sectie wilt maken, gaat u naar [!UICONTROL data source]**[!UICONTROL Audience Data > Data Sources > Add New]** en voert u de stappen uit voor elke sectie die hier wordt beschreven. Beheerdersmachtigingen zijn vereist voor het maken van een [!UICONTROL data source]account.

<!-- create-datasource.xml -->

>[!TIP]
>
>Zie Instellingen [gegevensbron en Menuopties](../features/datasources-list-and-settings.md#settings-menu-options) voor beschrijvingen van deze verschillende besturingselementen.

## [!UICONTROL Data Source] Details {#details}

De [!UICONTROL Data Source Details] sectie voltooien:

1. Geef de naam [!UICONTROL data source].
1. *(Optioneel)* Beschrijf de [!UICONTROL data source]. Met een beknopte beschrijving kunt u de rol of het doel van de [!UICONTROL data source]code definiëren.
1. Geef een [!UICONTROL integration code]wachtwoord op. Over het algemeen [!UICONTROL integration codes] zijn deze opties optioneel. Deze zijn vereist wanneer u wilt:

   * [Maak een gegevensbron](../features/profile-merge-rules/merge-rules-start.md#create-data-source)voor alle apparaten.
   * Gebruik de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
   * Werken met [Profielsamenvoegregels](../features/profile-merge-rules/merge-rules-start.md).

1. Kies een **[!UICONTROL ID Type]**. [!UICONTROL ID Type] opties zijn:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Vereist om een [!UICONTROL Profile Merge Rule]) te maken. Opmerking: voor sommige klanten worden met deze selectie de **[!UICONTROL ID Definition]** opties beschikbaar gemaakt.

1. Kies een **[!UICONTROL ID Definition]** optie. De volgende opties zijn beschikbaar:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## [!UICONTROL Data Export Controls] {#export-controls}

[De Controles](../features/data-export-controls.md) van de Uitvoer van gegevens zijn facultatieve classificatieregels u op een [!UICONTROL data source] en [!UICONTROL destination]. Ze verhinderen dat u gegevens naar een computer verzendt [!UICONTROL destination] wanneer die handeling een schending van een privacy-of gebruiksovereenkomst inhoudt. Sla deze sectie over als u deze niet gebruikt [!UICONTROL Data Export Controls].

## [!UICONTROL Data Source] Instellingen {#settings}

Deze instellingen bepalen hoe een [!UICONTROL data source] object wordt geïdentificeerd, gebruikt en gedeeld. U kunt foutrapportage ook inschakelen voor binnenkomende gegevensbestanden. De [!UICONTROL Data Source Settings] sectie voltooien:

1. Schakel een [!UICONTROL Data Source Setting] selectievakje in om een optie toe te passen op de [!UICONTROL data source]selectie.
2. Klik op **[!UICONTROL Save]**.

## Een gegevensbron verwijderen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Verwijder een [!UICONTROL data source] bestand dat u niet meer nodig hebt.

>[!NOTE]
>
>Houd rekening met de volgende beperkingen:
>
>* U kunt geen [Actief publiek of Gegevensbron Gesynchroniseerd Spoor](../features/traits/client-activity-synced-audience-traits.md)schrappen.
>* Voor klanten die Adobe Analytics gebruiken: Audience Manager staat u niet toe om gegevensbronnen te schrappen die automatisch van uw [!DNL Analytics] rapportreeksen worden gecreeerd. Gebruik de [Dienst](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) van de Kern om deze gegevensbronnen unmap.


1. Klik op **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Schakel het selectievakje naast een of meer gegevensbronnen in.
U kunt het [!UICONTROL Search] vakje gebruiken om van de gewenste gegevensbronnen de plaats te bepalen als u een lange lijst hebt.
1. Klik ![](assets/icon_trash.png)en bevestig de verwijdering.


>[!MORELIKETHIS]
>
>* [Instellingen gegevensbron en menuopties](../features/datasources-list-and-settings.md#settings-menu-options)