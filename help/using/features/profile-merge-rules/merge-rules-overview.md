---
description: Met de Regels van de Fusie van het Profiel krijgt u controle over de gegevensreeksen die voor segmentatie worden gebruikt en kan een persoon nauwkeurig over veelvoudige apparaten richten.
seo-description: Met de Regels van de Fusie van het Profiel krijgt u controle over de gegevensreeksen die voor segmentatie worden gebruikt en kan een persoon nauwkeurig over veelvoudige apparaten richten.
seo-title: Overzicht van regels voor samenvoegen van profielen
solution: Audience Manager
title: Overzicht van regels voor samenvoegen van profielen
uuid: 9e7988cc-9145-432b-840a-54fbd8657b3b
translation-type: tm+mt
source-git-commit: a077726fe4878aeb7722586654c27769e92e0665
workflow-type: tm+mt
source-wordcount: '362'
ht-degree: 0%

---


# [!UICONTROL Profile Merge Rules] Overzicht {#profile-merge-rules-overview}

Met [!UICONTROL Profile Merge Rules] u kunt bepalen welke gegevenssets worden gebruikt voor segmentatie en kunt u gebruikers nauwkeurig als doel instellen op meerdere apparaten.

>[!VIDEO](https://video.tv.adobe.com/v/28974)

## Gegevensverzameling en het richten met anonieme en voor authentiek verklaarde profielen {#data-collection-targeting}

Doorgaans is segmentering van het publiek en gericht afhankelijk van gegevens die zijn verzameld bij alle gebruikers op een apparaat. Gegevensverzameling en -gerichtheid op basis van apparaatgegevens heeft enkele nadelen. U kunt bijvoorbeeld geen onderscheid maken tussen meerdere gebruikers die een apparaat delen of gebruikers op meerdere apparaten nauwkeurig als doel instellen. Apparaatgecentreerde gegevensverzameling is niet langer voldoende voor digitale marketingcampagnes of het maken van apparaatspecifieke doelgroepen.

![](assets/unauthenticated2.png)

[!UICONTROL Profile Merge Rules] verandert fundamenteel hoe de gegevens en de segmentgebruikers voor het richten [!DNL Audience Manager] verzamelen. Hiermee kunt u werken met twee verschillende typen profielen, een apparaatprofiel en een [geverifieerd profiel](../../reference/visitor-authentication-states.md).

| Profieltype | Beschrijving |
|---|---|
| [!UICONTROL Device Profile] | Een id [!UICONTROL device profile] is gekoppeld aan een id voor een bepaald apparaat, zoals een [!UICONTROL cookie] id of een mobiele apparaat-id.<br><br> Het omvat:<ul><li>[!UICONTROL Rule-based traits] wordt gerealiseerd wanneer een gebruiker niet voor authentiek wordt verklaard.</li><li>[!UICONTROL Onboarded traits] gekoppeld aan een apparaat-id, zoals gegevens van [!UICONTROL cookie-based]derden.</li></ul> |
| [!UICONTROL Authenticated Profile] | Het [!UICONTROL authenticated profile] is gekoppeld aan een gebruikersnaam die wordt doorgegeven wanneer een persoon zich aanmeldt bij uw site.<br><br>Het omvat:<ul><li>[!UICONTROL Rule-based traits] verzameld over apparaten wanneer een gebruiker voor authentiek wordt verklaard.</li><li>[!UICONTROL Onboarded traits] in een offlinebestand dat aan dezelfde gebruiker-id is gekoppeld.</li></ul> |

Deze verschillende profielen bepalen de gegevens die u voor segmentatie kunt gebruiken. Met een [geverifieerd profiel](../../reference/visitor-authentication-states.md)kunt u bijvoorbeeld nauwkeurige gegevens maken [!UICONTROL segments] op basis van gegevens van meerdere apparaten voor één gebruiker. Dit betekent dat u klanten op meerdere apparaten een consistente merkervaring kunt bieden. [!DNL Audience Manager] Dit wordt bereikt door de toewijzing van de verschillende apparaten die een persoon voor zijn online activiteiten gebruikt, op te slaan in zijn [geverifieerde profiel](../../reference/visitor-authentication-states.md). Deze toewijzingen worden het [!UICONTROL Profile Link Device Graph]genoemd.

![](assets/authenticated2.png)

## Voordelen {#advantages}

Met [!UICONTROL Profile Merge Rules] u kunt:

* Target-gebruikers op basis van [geverifieerd profiel](../../reference/visitor-authentication-states.md), anonieme profielen of combinaties van beide.
* Target is een specifieke klant voor alle apparaten.
* Bouw een apparatengrafiek die op deterministische gegevens wordt gebaseerd.
* U kunt de gegevens in de bestanden nauwkeurig afstemmen op basis van verschillende profielen. [!UICONTROL segments]
* Verbeter extra inzicht in uw publiek.
