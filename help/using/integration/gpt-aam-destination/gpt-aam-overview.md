---
description: Overzicht van hoe u Google Ad Manager kunt integreren met behulp van Google Publisher Tags (GPT).
seo-description: Overview of how to integrate Google Ad Manager using Google Publisher Tags (GPT) in Adobe Audience Manager (AAM).
seo-title: Integrate Google Ad Manager using Google Publisher Tags (GPT)in Adobe Audience Manager (AAM)
title: Google Ad Manager integreren met Google Publisher-tags (GPT)
feature: Third-party Integration
exl-id: d383cb8a-ef41-4ce6-9e31-6145797a89fa
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '212'
ht-degree: 8%

---

# Integreren [!DNL Google Ad Manager] (voorheen DFP) met Google Publisher-tags (GPT)

De onderstaande artikelen bieden een overzicht van de wijze waarop [!DNL Google Ad Manager] Google Publisher-tags (GPT) gebruiken. U kunt een server-zijintegratie gebruiken, of u kunt opstelling GPT als bestemming om de gegevens van het de segmentsegment van de Audience Manager naar te verzenden [!DNL Google Ad Manager]. U leert ook de benodigde stappen voor het invoegen [!DNL Google Ad Manager] logbestanden voor rapportage in Audience Manager.

* [Vereisten en methoden voor het verzenden van segmenten naar Google Ad Manager met behulp van Google Publisher-tags (GPT)](/help/using/integration/gpt-aam-destination/gpt-aam-requirements.md)

   U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] hetzij via een client-side of via een server-side integratie. Vereisten en gerelateerde informatie over beide methoden worden hieronder vermeld.

* [Een GPT-bestemming maken](/help/using/integration/gpt-aam-destination/gpt-aam-create-destination.md)

   U kunt gekwalificeerde segmenten naar [!DNL Google Ad Manager] via een clientintegratie (browser-side) of een serverintegratie. Als u kiest voor de integratie op de client, moet u een op cookies gebaseerde bestemming maken voor Google Publisher-tags in Audience Manager.

* [De GPT setTargeting API-call wijzigen](/help/using/integration/gpt-aam-destination/gpt-aam-modify-api.md)

   Voeg een if-instructie toe om te controleren op cookies van de Audience Manager voordat u de methode Google Publisher Tag.setTargeting aanroept.

* [Audience Manager-code voor Google Publisher-tags](/help/using/integration/gpt-aam-destination/gpt-aam-aamgpt-code.md)

   AamGpt is een JavaScript-functie die Audience Manager cookie-gegevens leest en die informatie naar Google Publisher Tags verzendt.
