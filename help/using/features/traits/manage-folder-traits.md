---
description: Mapkenmerken maken, bewerken en verwijderen.
keywords: Mappenmap;Maptraits;mapkenmerken;mapkenmerken
seo-description: Create, edit, and delete folder traits.
seo-title: Manage Folder Traits
solution: Audience Manager
title: Maptrajecten beheren
uuid: 287ac280-bd58-4985-85bd-b6501eb64b7f
feature: Traits
exl-id: fa7a8d2a-dacc-413e-89d6-d3b7ce7bbbe3
source-git-commit: f7a4478589f4af1d467f1045a97dbb7f5cd6f9e5
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 4%

---

# Maptrajecten beheren {#manage-folder-traits}

Mapkenmerken maken, bewerken en verwijderen.

## Een maphandleiding maken {#create-folder-trait}

Een [!UICONTROL folder trait] wordt automatisch gecreeerd wanneer u een nieuwe omslag in uw taxonomie creeert.

<!-- create-folder-trait.xml -->

1. Ga naar **[!UICONTROL Audience Data > Traits]** om aan het **&#x200B;**&#x200B;dashboard van Tonen &lbrace;te navigeren.
1. Houd de muisaanwijzer boven [!UICONTROL Trait Storage] in het venster:

   * Tekst Alle sporen om een nieuwe hoofdmap toe te voegen.
   * Een bestaande bovenliggende map om een nieuwe onderliggende map toe te voegen.

   ![](assets/folder_traits_create.PNG)

1. Klik op het pictogram + om de map te maken. U kunt maximaal 2000 mappen maken in uw taxonomie. Raadpleeg de documentatie over [gebruikslimieten](../../features/administration/usage-limits.md) voor meer informatie.
1. Noem de omslag en klik **sparen**. Een map met de naam Electronics heeft bijvoorbeeld een mapkenmerk met de naam &#39;Electronics Folder Trait&#39;. U kunt de nieuwe mapkenmerken weergeven en selecteren op het dashboard met kenmerken.
1. Het nieuwe mapkenmerk wordt automatisch toegewezen aan de [!DNL Audience Manager] gegenereerde gegevensbron. Uw gebruikers met de juiste [!UICONTROL Role-Based Access Control] ([!DNL RBAC] ) machtigingen kunnen de gegevensbron wijzigen in de workflow voor het bewerken van de mapmap. Zie [&#x200B; een Spoor van de Omslag &#x200B;](../../features/traits/manage-folder-traits.md#edit-folder-trait) uitgeven.

## Een mappenset bewerken {#edit-folder-trait}

Beschrijft hoe u een [!UICONTROL folder trait] kunt bewerken.

<!-- edit-folder-trait.xml -->

1. Houd de muisaanwijzer boven de kolom [!UICONTROL Traits] in het dashboard van **[!UICONTROL Actions]** voor de mapkenmerken die u wilt bewerken.
1. Klik op het potlood om de eigenschap te bewerken.

   ![](assets/folder_traits_edit_border.png)

1. Met de **[!UICONTROL Edit]** -workflow kunt u de gegevensbron voor mapkenmerken wijzigen. Selecteer de gewenste gegevensbron en klik op **[!UICONTROL Save]** . Gegevensbronnen worden numeriek gesorteerd op [!DNL DPID] in de vervolgkeuzelijst.

   Als uw bedrijf [!UICONTROL Role-Based Access Rights (RBAC)] gebruikt, hebt u of uw gebruikers [&#x200B; toegangstoestemmingen &#x200B;](../../features/traits/about-folder-traits.md#role-based-access-controls) nodig om gegevensbronnen te trekken.

>[!NOTE]
>
>U kunt de naam van een mapkenmerk niet rechtstreeks wijzigen. [&#x200B; noem zijn bijbehorende opslagomslag &#x200B;](../../features/traits/trait-storage.md#rename-delete-trait-storage-folder) anders om de naam van het omslagspoor te veranderen.

## Een mapmap verwijderen {#delete-folder-trait}

Verwijder een mapkenmerk door de opslagmap te verwijderen waartoe de eigenschap behoort.

<!-- delete-folder-trait.xml -->

1. **Gegevens van het publiek > Trekken** om aan het **&#x200B;**&#x200B;dashboard van Tonen &lbrace;te navigeren.
1. Verwijder in het [!UICONTROL Trait Storage] -venster een map door de muisaanwijzer boven de map te houden en op het X-pictogram te klikken.

   ![&#x200B; Resultaat van de Stap &#x200B;](assets/folder_traits_create.PNG)

>[!NOTE]
>
>U kunt een mapkenmerk niet verwijderen als dit wordt gebruikt in een segmentexpressie. Navigeer aan de [&#x200B; sectie van de trekmening &#x200B;](../../features/traits/trait-details-page.md) om te zien welke segmenten het omslagspoor gebruiken. Dan, klik op de segmentnaam om de [&#x200B; summiere mening van het segment &#x200B;](../../features/segments/segment-summary-view.md) te openen, die u toestaat om sporen uit segmentuitdrukkingen te verwijderen.
