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
source-git-commit: 4ea5ba4ebd8cd4c13c99c8272f4b5733ab5fa125
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 9%

---


# Mapeigenschappen beheren {#manage-folder-traits}

Mapkenmerken maken, bewerken en verwijderen.

## Een mappenset {#create-folder-trait} maken

Een [!UICONTROL folder trait] wordt automatisch gecreeerd wanneer u een nieuwe omslag in uw taxonomie creeert.

<!-- create-folder-trait.xml -->

1. Ga naar **[!UICONTROL Audience Data > Traits]** om naar **Traits** dashboard te navigeren.
1. Houd de aanwijzer boven in het venster [!UICONTROL Trait Storage]:

   * Tekst Alle sporen om een nieuwe hoofdmap toe te voegen.
   * Een bestaande bovenliggende map om een nieuwe ondergeschikte map toe te voegen.

   ![](assets/folder_traits_create.PNG)

1. Klik op het pictogram + om de map te maken. U kunt maximaal 2.000 mappen maken in uw taxonomie. Raadpleeg de documentatie over [gebruikslimieten](../../features/administration/usage-limits.md) voor meer informatie.
1. Geef de map een naam en klik op **Opslaan**. Een map met de naam Electronics heeft bijvoorbeeld een mapkenmerk met de naam &#39;Electronics Folder Trait&#39;. U kunt de nieuwe mapkenmerken weergeven en selecteren op het dashboard met kenmerken.
1. De nieuwe omslageigenschap wordt automatisch toegewezen aan [!DNL Audience Manager] geproduceerde gegevensbron. Uw gebruikers met de juiste [!UICONTROL Role-Based Access Control] ([!DNL RBAC]) machtigingen kunnen de gegevensbron wijzigen in de workflow voor het bewerken van de map. Zie [Een mapmap bewerken](../../features/traits/manage-folder-traits.md#edit-folder-trait).

## Een maptrack {#edit-folder-trait} bewerken

Beschrijft hoe u [!UICONTROL folder trait] kunt uitgeven.

<!-- edit-folder-trait.xml -->

1. Houd de muisaanwijzer in het dashboard [!UICONTROL Traits] boven de kolom **[!UICONTROL Actions]** voor het mapkenmerk dat u wilt bewerken.
1. Klik op het potlood om de eigenschap te bewerken.

   ![](assets/folder_traits_edit_border.png)

1. Met de **[!UICONTROL Edit]**-workflow kunt u de gegevensbron voor mapkenmerken wijzigen. Selecteer de gewenste gegevensbron en klik op **[!UICONTROL Save]**. Gegevensbronnen worden numeriek gesorteerd op [!DNL DPID] in de vervolgkeuzelijst.

   Als uw bedrijf [!UICONTROL Role-Based Access Rights (RBAC)] gebruikt, hebt u of uw gebruikers [toegangstoestemmingen](../../features/traits/about-folder-traits.md#role-based-access-controls) nodig om gegevensbronnen te karakteriseren.

>[!NOTE]
>
>U kunt de naam van een mapkenmerk niet rechtstreeks wijzigen. [Wijzig de naam van de bijbehorende ](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) opslagmap om de mapkenmerken te wijzigen.

## Een maptrack {#delete-folder-trait} verwijderen

Verwijder een mapkenmerk door de opslagmap te verwijderen waartoe de eigenschap behoort.

<!-- delete-folder-trait.xml -->

1. **Poortgegevens >** Traitstations om naar het  **** Traitsdashboard te navigeren.
1. Verwijder een map in het venster [!UICONTROL Trait Storage] door de muisaanwijzer op de map te plaatsen en op het X-pictogram te klikken.

   ![Stap resultaat](assets/folder_traits_create.PNG)

>[!NOTE]
>
>U kunt een mapkenmerk niet verwijderen als dit wordt gebruikt in een segmentexpressie. Navigeer naar de sectie [Trait view](../../features/traits/trait-details-page.md) om te zien welke segmenten het omslagspoor gebruiken. Dan, klik op de segmentnaam om [segment summiere mening](../../features/segments/segment-summary-view.md) te openen, die u toestaat om eigenschappen uit segmentuitdrukkingen te verwijderen.
