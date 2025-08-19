---
title: Een gegevensbron configureren voor gehashte e-mailworkflows
description: Leer hoe u een gegevensbron maakt voor het opslaan van gehashte e-mailberichten voor gehashte e-mailworkflows.
solution: Audience Manager
feature: Data Sources
exl-id: fb235dcb-e02f-41ac-ba3f-a1feb30b23dd
source-git-commit: d55dbc4f9630e3d22dfb988f6725f33993229c48
workflow-type: tm+mt
source-wordcount: '191'
ht-degree: 0%

---

# Een gegevensbron configureren voor gehashte e-mailworkflows

Voor workflows met onderbroken e-mail, zoals Op personen gebaseerde doelen, moet u een gegevensbron maken om de gehashte e-mailadressen op te slaan.

Voer de onderstaande stappen uit om een gegevensbron voor gehashte e-mails te maken en te configureren.

1. Meld u aan bij uw Audience Manager-account, ga naar **[!UICONTROL Audience Data]** -> **[!UICONTROL Data Sources]** en klik op **[!UICONTROL Add New]** .
1. Voer een **[!UICONTROL Name]** en **[!UICONTROL Description]** in voor de nieuwe gegevensbron.
1. Selecteer **[!UICONTROL ID Type]** in de vervolgkeuzelijst **[!UICONTROL Cross Device]** .
   {het beeld van 0} Audience Manager UI die de sectie van de gegevensbrondetails toont.![](../features/assets/create-hashed-email-data-source.png)
1. Selecteer in de sectie **[!UICONTROL Data Source Settings]** zowel de opties **[!UICONTROL Inbound]** als **[!UICONTROL Outbound]** en schakel de optie **[!UICONTROL Share associated cross-device IDs in people-based destinations]** in.
1. Gebruik het vervolgkeuzemenu om het label **[!UICONTROL Emails(SHA256, lowercased)]** voor deze gegevensbron te selecteren.

   >[!IMPORTANT]
   >
   >Met deze optie wordt alleen de gegevensbron gelabeld met gegevens die zijn gehasht met dat specifieke algoritme. Audience Manager hash de gegevens op dit moment niet. Controleer of de e-mailadressen die u wilt opslaan in deze gegevensbron al zijn gehasht met het algoritme [!DNL SHA256] . Anders kunt u deze niet gebruiken voor gehashte e-mailworkflows.

   {het beeld van 0} Audience Manager UI die de sectie van gegevensbronmontages toont.![](../features/assets/data-source-settings.png)
