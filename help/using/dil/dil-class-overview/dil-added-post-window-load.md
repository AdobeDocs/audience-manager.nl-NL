---
description: Gebruikt om DIL te laten weten dat het wordt geladen nadat het venster wordt geladen.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
><br><br>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangeraden [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun strategie voor het verzamelen van gegevens op lange termijn.
><br><br>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan.

Gebruikt om DIL te laten weten dat het wordt geladen nadat het venster wordt geladen.

**Functiehandtekening:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## Voorbeeldcode

```
DIL.isAddedPostWindowLoad();
```
