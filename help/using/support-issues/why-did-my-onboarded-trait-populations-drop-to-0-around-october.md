---
description: Rond 14 oktober 2019 merkte ik op dat mijn populaties met geëngageerde kenmerken voor de grafiek van het Apparaat ID zijn gedaald tot 0, waar ze vroeger veel hoger waren.
seo-description: Rond 14 oktober 2019 merkte ik op dat mijn populaties met geëngageerde kenmerken voor de grafiek van het Apparaat ID zijn gedaald tot 0, waar ze vroeger veel hoger waren.
seo-title: Waarom zijn mijn populaties van onboded-trait gedaald tot 0 rond 15 oktober?
solution: Audience Manager
title: Waarom zijn mijn populaties van onboded-trait gedaald tot 0 rond 15 oktober?
feature: support
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '230'
ht-degree: 0%

---


# Waarom zijn mijn populaties van onboded-trait gedaald tot 0 rond 15 oktober? {#why-did-my-onboarded-trait-populations-drop-to-0-around-october}

## Vraag

Rond 14 oktober 2019 merkte ik op dat mijn populaties met geëngageerde kenmerken voor de grafiek van het Apparaat ID zijn gedaald tot 0, waar ze vroeger veel hoger waren. Waarom is dit gebeurd?

![Afbeelding van apparaat-id neerzetten](assets/device_id_populationdrop.png)

## Antwoord

Op 15 oktober, werd een update aan de functionaliteit van de Regel van de Samenvoeging van het Profiel van Audience Manager veranderd in waar de gegevens van Onboard van een identiteitskaart van CRM die aan een Gegevensbron van het Apparaat wordt geupload niet meer tegen apparatenids worden gerealiseerd.  Eerder realiseerde de Audience Manager zich tegen zowel dwars-Apparaat identiteitskaart (of identiteitskaart van CRM) als het kopiëren van die realisaties aan bijbehorende Audience Manager UUIDs (Apparaat IDs).  De wijziging is aangebracht om de aard van de gegevens over de eigenschap en de profielen die worden gerealiseerd, nauwkeuriger weer te geven.

Als u de karakteristieken wilt weergeven, selecteert u de optie &quot;Apparaatoverschrijdende id&quot; in de vervolgkeuzelijst rechtsboven in de weergave Trait.

![Weergaven per apparaat-id weergeven](assets/deviceid-crossdevice.png)