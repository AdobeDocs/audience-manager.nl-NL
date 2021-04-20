---
description: Overzicht van hoe u Google Ad Manager kunt integreren met Google Publisher Tags (GPT).
seo-description: Overzicht van hoe u Google Ad Manager kunt integreren met Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Google Ad Manager integreren met Google Publisher Tags (GPT) in Adobe Audience Manager (AAM)
title: Google Ad Manager integreren met Google Publisher-tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '246'
ht-degree: 6%

---

# [!DNL Google Ad Manager] (voorheen DFP) integreren met Google Publisher-tags (GPT)

De onderstaande artikelen bieden een overzicht van hoe u [!DNL Google Ad Manager] kunt integreren met Google Publisher Tags (GPT). U kunt een server-zijintegratie gebruiken, of u kunt opstelling GPT als bestemming om Audience Manager segmentgegevens naar [!DNL Google Ad Manager] te verzenden. U zult ook de noodzakelijke stappen leren om [!DNL Google Ad Manager] logboekdossiers voor rapportering in Audience Manager in te gaan.

* [Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager via Google Publisher-tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] verzenden via een client-kant of via een serverintegratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.

* [Een GPT-bestemming maken](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] verzenden via integratie op de client (browser-side) of via integratie op de server. Als u kiest voor integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.

* [De GPT setTargeting API-call wijzigen](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Voeg een if-instructie toe om te controleren op cookies van Audience Managers voordat u de Google Publisher-tag .setTargeting-methode aanroept.

* [Audience Manager-code voor Google Publisher-tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt is een JavaScript-functie die Audience Manager cookie-gegevens leest en die informatie naar Google Publisher-tags verzendt.
