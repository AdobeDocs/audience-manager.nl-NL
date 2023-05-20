---
description: Met de Regels van de Fusie van het Profiel krijgt u controle over de gegevensreeksen die voor segmentatie worden gebruikt en kan een persoon nauwkeurig over veelvoudige apparaten richten.
seo-description: With Profile Merge Rules you get control over the data sets used for segmentation and can target a person accurately across multiple devices.
seo-title: Profile Merge Rules Overview
solution: Audience Manager
title: Overzicht van de regels voor profielsamenvoeging
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
feature: Profile Merge
exl-id: 5d1f5bea-0fca-4684-a2b4-585d9e38d9ef
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '335'
ht-degree: 1%

---

# [!UICONTROL Profile Merge Rules] Overzicht {#profile-merge-rules-overview}

Met [!UICONTROL Profile Merge Rules] U kunt bepalen welke gegevenssets worden gebruikt voor segmentatie en u kunt gebruikers nauwkeurig als doel instellen op meerdere apparaten.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Gegevensverzameling en het richten met anonieme en voor authentiek verklaarde profielen {#data-collection-targeting}

Doorgaans is segmentering van het publiek en doelgericht afhankelijk van gegevens die zijn verzameld bij alle gebruikers op een apparaat. Gegevensverzameling en -gerichtheid op basis van apparaatgegevens heeft enkele nadelen. U kunt bijvoorbeeld geen onderscheid maken tussen meerdere gebruikers die een apparaat delen of gebruikers op meerdere apparaten nauwkeurig als doel instellen. Apparaatgecentreerde gegevensverzameling is niet langer voldoende voor digitale marketingcampagnes of het maken van doelgerichte toepassingen op verschillende apparaten.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] fundamenteel verandert hoe [!DNL Audience Manager] verzamelt gegevens en segmentgebruikers voor doelframes. Hiermee kunt u werken met twee verschillende typen profielen, een apparaatprofiel en een [geverifieerd profiel](../../reference/visitor-authentication-states.md).

| Profieltype | Beschrijving |
|---|---|
| [!UICONTROL Device Profile] | A [!UICONTROL device profile] is gekoppeld aan een id voor een bepaald apparaat, zoals een [!UICONTROL cookie] ID of mobiele apparaat-id.<br><br> Het omvat:<ul><li>[!UICONTROL Rule-based traits] wordt gerealiseerd wanneer een gebruiker niet voor authentiek wordt verklaard.</li><li>[!UICONTROL Onboarded traits] gekoppeld aan een apparaat-id, zoals [!UICONTROL cookie-based], gegevens van derden.</li></ul> |
| [!UICONTROL Authenticated Profile] | De [!UICONTROL authenticated profile] is gekoppeld aan een gebruikersnaam die wordt doorgegeven wanneer een persoon zich aanmeldt bij uw site.<br><br>Het omvat:<ul><li>[!UICONTROL Rule-based traits] verzameld over apparaten wanneer een gebruiker voor authentiek wordt verklaard.</li><li>[!UICONTROL Onboarded traits] in een offlinebestand dat aan dezelfde gebruiker-id is gekoppeld.</li></ul> |

Deze verschillende profielen bepalen de gegevens die u voor segmentatie kunt gebruiken. Met bijvoorbeeld een [geverifieerd profiel](../../reference/visitor-authentication-states.md)kunt u nauwkeurige [!UICONTROL segments] gebaseerd op gegevens van meerdere apparaten voor één gebruiker. Dit betekent dat u klanten op meerdere apparaten een consistente merkervaring kunt bieden. [!DNL Audience Manager] Dit wordt bereikt door het in kaart brengen van de verschillende apparaten die een persoon voor zijn online activiteiten gebruikt aan hun [geverifieerd profiel](../../reference/visitor-authentication-states.md). Deze toewijzingen worden de [!UICONTROL Profile Link Device Graph].

![](assets/authenticated2.png)

## Voordelen {#advantages}

Met [!UICONTROL Profile Merge Rules] u kunt:

* Doelgebruikers gebaseerd op [geverifieerd profiel](../../reference/visitor-authentication-states.md), anonieme profielen of combinaties van beide.
* Richt een specifieke klant over hun apparaten.
* Bouw een apparatengrafiek die op deterministische gegevens wordt gebaseerd.
* De gegevens in uw [!UICONTROL segments] op basis van verschillende profielen.
* Verbeter extra inzicht in uw publiek.
