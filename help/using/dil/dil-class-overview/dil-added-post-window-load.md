---
description: Wordt gebruikt om DIL te laten weten dat het wordt geladen nadat het venster is geladen.
seo-description: Used to let DIL know that it is loaded after the window loads.
seo-title: isAddedPostWindowLoad
solution: Audience Manager
title: isAddedPostWindowLoad
uuid: 8cdeab00-6ce4-4f07-bb63-41425369a5b7
feature: DIL Implementation
exl-id: 955fe0f2-2a64-491f-9098-e5aabcc697db
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '98'
ht-degree: 0%

---


# isAddedPostWindowLoad{#isaddedpostwindowload}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [&#x200B; SDK van het Web van Experience Platform &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [&#x200B; SDK van het Web van Experience Platform &#x200B;](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan moeten gebruiken.

Wordt gebruikt om DIL te laten weten dat het wordt geladen nadat het venster is geladen.

**de Handtekening van de Functie:** `isAddedPostWindowLoad: function()`

<!--
r_dil_added_post_window_load.xml
-->

## Voorbeeldcode

```
DIL.isAddedPostWindowLoad();
```
