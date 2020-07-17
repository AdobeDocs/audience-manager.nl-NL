---
description: Mapkenmerken maken, bewerken en verwijderen.
keywords: Folder Trait;Folder Traits;folder traits;folder trait
seo-description: Mapkenmerken maken, bewerken en verwijderen.
seo-title: Mapeigenschappen beheren
solution: Audience Manager
title: Mapeigenschappen beheren
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '366'
ht-degree: 9%

---


# Mapeigenschappen beheren {#manage-folder-traits}

Mapkenmerken maken, bewerken en verwijderen.

## Een maphandleiding maken {#create-folder-trait}

Er [!UICONTROL folder trait] wordt automatisch een map gemaakt wanneer u een nieuwe map maakt in uw taxonomie.

<!-- create-folder-trait.xml -->

1. Ga naar **[!UICONTROL Audience Data > Traits]** het dashboard **Traits** .
1. Houd de muisaanwijzer in het [!UICONTROL Trait Storage] venster boven:

   * Tekst Alle sporen om een nieuwe hoofdmap toe te voegen.
   * Een bestaande bovenliggende map om een nieuwe ondergeschikte map toe te voegen.

   ![](assets/folder_traits_create.PNG)

1. Klik op het pictogram + om de map te maken. U kunt maximaal 2.000 mappen maken in uw taxonomie. Raadpleeg de documentatie over [gebruikslimieten](../../features/administration/usage-limits.md) voor meer informatie.
1. Geef de map een naam en klik op **Opslaan**. Een map met de naam Electronics heeft bijvoorbeeld een mapkenmerk met de naam &#39;Electronics Folder Trait&#39;. U kunt de nieuwe mapkenmerken weergeven en selecteren op het dashboard met kenmerken.
1. Het nieuwe mapkenmerk wordt automatisch toegewezen aan de [!DNL Audience Manager] gegenereerde gegevensbron. Uw gebruikers met de juiste machtigingen [!UICONTROL Role-Based Access Control ([!DNL RBAC])] kunnen de gegevensbron wijzigen in de workflow voor het bewerken van de mapmap. Zie Een mapmap [bewerken](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Een mappenset bewerken {#edit-folder-trait}

Beschrijft hoe u een [!UICONTROL folder trait]document kunt uitgeven.

<!-- edit-folder-trait.xml -->

1. Houd de muisaanwijzer in het [!UICONTROL Traits] dashboard boven de **[!UICONTROL Actions]** kolom voor het mapkenmerk dat u wilt bewerken.
1. Klik op het potlood om de eigenschap te bewerken.

   ![](assets/folder_traits_edit_border.png)

1. Met de **[!UICONTROL Edit]** workflow kunt u de gegevensbron voor mapkenmerken wijzigen. Selecteer de gewenste gegevensbron en klik op **[!UICONTROL Save]**. De gegevensbronnen worden numeriek gesorteerd, door [!DNL DPID], in de drop-down doos.

   Als uw bedrijf gebruikt [!UICONTROL Role-Based Access Rights (RBAC)], hebt u of uw gebruikers [toegangstoestemmingen](../../features/traits/about-folder-traits.md#role-based-access-controls) aan de gegevensbronnen van de treksporen nodig.

>[!NOTE]
>
>U kunt de naam van een mapkenmerk niet rechtstreeks wijzigen. [Wijzig de naam van de bijbehorende opslagmap](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) om de mapkenmerken te wijzigen.

## Een mapmap verwijderen {#delete-folder-trait}

Verwijder een mapkenmerk door de opslagmap te verwijderen waartoe de eigenschap behoort.

<!-- delete-folder-trait.xml -->

1. **Poortgegevens > Vertrekken** om naar het dashboard **Traits** te navigeren.
1. Verwijder in het [!UICONTROL Trait Storage] venster een map door de muisaanwijzer op de map te plaatsen en op het X-pictogram te klikken.

   ![Stap resultaat](assets/folder_traits_create.PNG)

>[!NOTE]
>
>U kunt een mapkenmerk niet verwijderen als dit wordt gebruikt in een segmentexpressie. Navigeer naar de sectie van de [proefweergave](../../features/traits/trait-details-page.md) om te zien welke segmenten de omslageigenschap gebruiken. Klik vervolgens op de segmentnaam om de overzichtsweergave [van het](../../features/segments/segment-summary-view.md)segment te openen, zodat u kenmerken uit segmentexpressies kunt verwijderen.