---
description: Met de Regels van de Fusie van het Profiel krijgt u controle over de gegevensreeksen die voor segmentatie worden gebruikt en kan een persoon nauwkeurig over veelvoudige apparaten richten.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: Overzicht van regels voor samenvoegen van profielen
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '336'
ht-degree: 0%

---

# [!UICONTROL Profile Merge Rules] Overzicht {#profile-merge-rules-overview}

Met [!UICONTROL Profile Merge Rules] kunt u bepalen welke gegevenssets worden gebruikt voor segmentatie en kunt u gebruikers nauwkeurig als doel instellen op meerdere apparaten.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Gegevensverzameling en het richten met anonieme en voor authentiek verklaarde profielen {#data-collection-targeting}

Doorgaans is segmentering van het publiek en doelgericht afhankelijk van gegevens die zijn verzameld bij alle gebruikers op een apparaat. Gegevensverzameling en -gerichtheid op basis van apparaatgegevens heeft enkele nadelen. U kunt bijvoorbeeld geen onderscheid maken tussen meerdere gebruikers die een apparaat delen of gebruikers op meerdere apparaten nauwkeurig als doel instellen. Apparaatgecentreerde gegevensverzameling is niet langer voldoende voor digitale marketingcampagnes of het maken van doelgerichte toepassingen op verschillende apparaten.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] wijzigt fundamenteel de manier waarop [!DNL Audience Manager] gegevens en segmenten verzamelt die gebruikers als doelgroep kunnen gebruiken. Het laat u met 2 verschillende types van profielen werken, een apparatenprofiel en een [ voor authentiek verklaard profiel ](../../reference/visitor-authentication-states.md).

| Profieltype | Beschrijving |
|---|---|
| [!UICONTROL Device Profile] | Een [!UICONTROL device profile] is gekoppeld aan een id voor een bepaald apparaat, zoals een [!UICONTROL cookie] ID of een mobiele apparaat-id.<br><br> Het omvat:<ul><li>[!UICONTROL Rule-based traits] wordt uitgevoerd wanneer een gebruiker niet wordt geverifieerd.</li><li>[!UICONTROL Onboarded traits] gekoppeld aan een apparaat-id, zoals [!UICONTROL cookie-based] , gegevens van derden.</li></ul> |
| [!UICONTROL Authenticated Profile] | [!UICONTROL authenticated profile] is gekoppeld aan een gebruikersnaam die wordt doorgegeven wanneer een persoon zich aanmeldt bij uw site.<br><br> het omvat:<ul><li>[!UICONTROL Rule-based traits] wordt verzameld op verschillende apparaten wanneer een gebruiker wordt geverifieerd.</li><li>[!UICONTROL Onboarded traits] in een offlinebestand dat is gekoppeld aan dezelfde gebruiker-id.</li></ul> |

Deze verschillende profielen bepalen de gegevens die u voor segmentatie kunt gebruiken. Bijvoorbeeld, met een [ voor authentiek verklaard profiel ](../../reference/visitor-authentication-states.md), kunt u nauwkeurige [!UICONTROL segments] bouwen die op gegevens van veelvoudige apparaten voor één enkele gebruiker wordt gebaseerd. Dit betekent dat u klanten op meerdere apparaten een consistente merkervaring kunt bieden. [!DNL Audience Manager] bereikt dit door de afbeelding van de verschillende apparaten op te slaan een persoon voor hun online activiteiten aan hun [ voor authentiek verklaarde profiel ](../../reference/visitor-authentication-states.md) gebruikt. Deze toewijzingen worden de [!UICONTROL Profile Link Device Graph] genoemd.

![](assets/authenticated2.png)

## Voordelen {#advantages}

Met [!UICONTROL Profile Merge Rules] kunt u:

* De gebruikers van het doel die op [ worden gebaseerd voor authentiek verklaarde profiel ](../../reference/visitor-authentication-states.md), anonieme profielen, of combinaties van allebei.
* Richt een specifieke klant over hun apparaten.
* Bouw een apparatengrafiek die op deterministische gegevens wordt gebaseerd.
* Stel de gegevens in uw [!UICONTROL segments] nauwkeurig in op basis van verschillende profielen.
* Geniet van extra insight in je publiek.
