---
description: Rond 14 oktober 2019 merkte ik dat mijn populaties met de eigenschap Onboarded voor de Device ID-grafiek zijn gedaald tot 0, terwijl ze daarvoor veel hoger waren.
seo-description: Around October 14th, 2019 I noticed that my onboarded trait populations for the Device ID graph have dropped to 0, where previously they were much higher.
seo-title: Why did my Onboarded trait populations drop to 0 around October 15th?
solution: Audience Manager
title: Waarom zijn mijn populaties met de eigenschap Onboarded rond 15 oktober tot 0 gedaald?
feature: Support
exl-id: e93cee15-7d05-4f81-8f14-a3e03f214542
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '195'
ht-degree: 100%

---

# Waarom zijn mijn populaties met de eigenschap Onboarded rond 15 oktober tot 0 gedaald? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Vraag

Rond 14 oktober 2019 merkte ik dat mijn populaties met de eigenschap Onboarded voor de Device ID-grafiek zijn gedaald tot 0, terwijl ze daarvoor veel hoger waren. Waarom is dit gebeurd?

![Afbeelding van Device ID neerzetten](assets/device_id_populationdrop.png)

## Antwoord

Op 15 oktober zorgde een update van de regel voor profielsamenvoeging in Audience Manager ervoor dat onboarded data niet meer werden gerealiseerd tegen apparaat-id’s als het ging om data op basis van een CRM-id die was geüpload naar een cross-device databron. Vroeger realiseerde Audience Manager tegen de cross-device id’s (of CRM-id) en kopieerde deze realisaties bovendien naar gekoppelde Audience Manager-UUID’s (apparaat-id’s). De wijziging is bedoeld om de aard van de eigenschapdata en de profielen die worden gerealiseerd nauwkeuriger weer te geven.

Als u de realisaties van de eigenschappen wilt weergeven, selecteert u de optie Cross-device id in de vervolgkeuzelijst rechtsboven in de weergave Eigenschap.

![Realisaties weergeven per cross-device id](assets/deviceid-crossdevice.png)
