---
description: Als u een nieuwe gegevensbron wilt maken, gaat u naar Poortgegevens > Gegevensbronnen > Nieuwe toevoegen en voert u de stappen voor elke hier beschreven sectie in. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.
keywords: data sources;manage data source;audience manager data source
seo-description: Als u een nieuwe gegevensbron wilt maken, gaat u naar Poortgegevens > Gegevensbronnen > Nieuwe toevoegen en voert u de stappen voor elke hier beschreven sectie in. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.
seo-title: Een gegevensbron maken
solution: Audience Manager
title: Gegevensbronnen beheren
uuid: 4df65bcb-9ad9-4b72-a71e-8918b43d4850
translation-type: tm+mt
source-git-commit: 412972b9d9a633d09de411c46528b93c74a64e3f

---


# Gegevensbronnen beheren {#manage-data-sources}

## Een gegevensbron maken {#create-data-source}

Als u een nieuwe gegevensbron wilt maken, gaat u naar **[!UICONTROL Audience Data > Data Sources > Add New]** en voert u de stappen uit voor elke sectie die hier wordt beschreven. Beheerdersmachtigingen zijn vereist voor het maken van een gegevensbron.

<!-- create-datasource.xml -->

>[!TIP]
>
>Zie Instellingen [gegevensbron en Menuopties](../features/datasources-list-and-settings.md#settings-menu-options) voor beschrijvingen van deze verschillende besturingselementen.

## Gegevens gegevensbron {#details}

De [!UICONTROL Data Source Details] sectie voltooien:

1. Geef de gegevensbron een naam.
1. *(Optioneel)* Beschrijf de gegevensbron. Met een beknopte beschrijving kunt u de rol of het doel van de gegevensbron definiëren.
1. Geef een integratiecode op. Integratiecodes zijn over het algemeen optioneel. Deze zijn vereist wanneer u wilt:

   * [Maak een gegevensbron](../features/profile-merge-rules/merge-rules-start.md#create-data-source)voor alle apparaten.
   * Gebruik de [Adobe Experience Platform Identity Service](https://docs.adobe.com/content/help/en/id-service/using/home.html).
   * Werken met [Profielsamenvoegregels](../features/profile-merge-rules/merge-rules-start.md).

1. Kies een **[!UICONTROL ID Type]**. Opties voor id-type zijn:

   * **[!UICONTROL Cookie]**
   * **[!UICONTROL Device Advertising ID]**
   * **[!UICONTROL Cross-device]** (Vereist om een [!UICONTROL Profile Merge Rule]) te maken. Opmerking: voor sommige klanten worden met deze selectie de **[!UICONTROL ID Definition]** opties beschikbaar gemaakt.

1. Kies een **[!UICONTROL ID Definition]** optie. De volgende opties zijn beschikbaar:

   * **[!UICONTROL Person]**
   * **[!UICONTROL Household]**

## Besturingselementen voor gegevensexport {#export-controls}

[De Controles](../features/data-export-controls.md) van de Uitvoer van gegevens zijn facultatieve classificatieregels u op een gegevensbron en een bestemming kunt toepassen. Ze verhinderen dat u gegevens naar een bestemming verzendt wanneer die handeling een inbreuk vormt op de privacy van gegevens of een gebruiksovereenkomst. Sla deze sectie over als u deze niet gebruikt [!UICONTROL Data Export Controls].

## Instellingen gegevensbron {#settings}

Deze instellingen bepalen hoe een gegevensbron wordt geïdentificeerd, gebruikt en gedeeld. U kunt foutrapportage ook inschakelen voor binnenkomende gegevensbestanden. De [!UICONTROL Data Source Settings] sectie voltooien:

1. Schakel een [!UICONTROL Data Source Setting] selectievakje in om een optie op de gegevensbron toe te passen.
2. Klik op **[!UICONTROL Save]**.

>[!MORELIKETHIS]
>
>* [Instellingen gegevensbron en menuopties](../features/datasources-list-and-settings.md#settings-menu-options)


## Een gegevensbron verwijderen {#delete-data-source}

<!-- t_datasource_delete.xml -->

Verwijder een gegevensbron die u niet meer nodig hebt.

>[!NOTE]
>
>Houd rekening met de volgende beperkingen:
>
>* U kunt geen [Actief publiek of Gegevensbron Gesynchroniseerd Spoor](../features/traits/client-activity-synced-audience-traits.md)schrappen.
>* Voor klanten die Adobe Analytics gebruiken: De Manager van het publiek staat u niet toe om gegevensbronnen te schrappen die automatisch van uw [!DNL Analytics] rapportreeksen worden gecreeerd. Gebruik de [Dienst](https://docs.adobe.com/content/help/en/core-services/interface/about-core-services/core-services-landing.html) van de Kern om deze gegevensbronnen unmap.


1. Klik op **[!UICONTROL Audience Data]** > **[!UICONTROL Data Sources]**.
1. Schakel het selectievakje naast een of meer gegevensbronnen in.
U kunt het [!UICONTROL Search] vakje gebruiken om van de gewenste gegevensbronnen de plaats te bepalen als u een lange lijst hebt.
1. Klik ![](assets/icon_trash.png)en bevestig de verwijdering.