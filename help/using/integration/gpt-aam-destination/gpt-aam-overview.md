---
description: Overzicht van hoe u Google Ad Manager kunt integreren met Google Publisher Tags (GPT).
seo-description: Overzicht van hoe u Google Ad Manager kunt integreren met Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Google Ad Manager integreren met Google Publisher Tags (GPT) in Adobe Audience Manager (AAM)
title: Google Ad Manager integreren met Google Publisher-tags (GPT)
feature: Third Party Integrations
translation-type: tm+mt
source-git-commit: e007279d81998031d2d61d0e68fe911813cadf8e
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Integrate [!DNL Google Ad Manager] (formerly DFP) using Google Publisher Tags (GPT)

De onderstaande artikelen bieden een overzicht van hoe u kunt integreren [!DNL Google Ad Manager] met Google Publisher Tags (GPT). U kunt een server-zijintegratie gebruiken, of u kunt opstelling GPT als bestemming om Audience Manager segmentgegevens naar te verzenden. [!DNL Google Ad Manager] U zult ook de noodzakelijke stappen leren om [!DNL Google Ad Manager] logboekdossiers voor rapportering in Audience Manager in te gaan.

* [Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager via Google Publisher-tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] of door een cliënt-kant of door een server-zijintegratie verzenden. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.

* [Een GPT-bestemming maken](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] een client-side (browser-side) integratie of een server-side integratie sturen. Als u kiest voor integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.

* [De GPT setTargeting API-call wijzigen](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Voeg een if-instructie toe om te controleren op cookies van Audience Managers voordat u de Google Publisher-tag .setTargeting-methode aanroept.

* [Audience Manager-code voor Google Publisher-tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt is een JavaScript-functie die Audience Manager cookie-gegevens leest en die informatie naar Google Publisher-tags verzendt.
