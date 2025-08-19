---
description: Unsegmentation beschrijft processen die apparatenprofielen van segmenten onbruikbaar maken en verwijderen. De mogelijkheid om een apparaatprofiel uit een segment te verwijderen, is afhankelijk van de apparaatoptie die wordt gebruikt om een regel voor het samenvoegen van profielen te maken.
seo-description: Unsegmentation describes processes that disqualify and remove device profiles from segments. Your ability to remove a device profile from a segment depends on the device option used to create a Profile Merge Rule.
seo-title: Profile Merge Rules and Device Un-Segmentation Processes
solution: Audience Manager
title: Regels voor het samenvoegen van profielen en processen voor onsegmentering van apparaten
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge
exl-id: ff3da607-5c25-45b2-ac27-071c22d518a0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '467'
ht-degree: 2%

---

# Regels voor het samenvoegen van profielen en processen voor onsegmentering van apparaten {#profile-merge-rules-and-device-un-segmentation-processes}

Unsegmentation beschrijft processen die apparatenprofielen van segmenten onbruikbaar maken en verwijderen. De mogelijkheid om een apparaatprofiel uit een segment te verwijderen, is afhankelijk van de apparaatoptie die wordt gebruikt om een [!UICONTROL Profile Merge Rule] -profiel te maken.

## Beschikbare apparaatopties {#device-options}

Ter herinnering: [!UICONTROL Device Options] is beschikbaar in de [!UICONTROL Profile Merge Rules Setup] -sectie wanneer u een [!UICONTROL Profile Merge Rule] maakt of bewerkt.

## Optie voor huidige apparaatprofiel en segmentatie van apparaat {#current-device-profile-options}

**[!UICONTROL Device Profile]** is de standaardoptie voor apparaatprofielen voor een [!UICONTROL Profile Merge Rule] . [!DNL Audience Manager] kan een apparaatprofiel uit een segment verwijderen wanneer uw [!UICONTROL Profile Merge Rule] de optie **[!UICONTROL Device Profile]** gebruikt. Onder deze omstandigheden vindt ontsegmentatie plaats wanneer:

* Het apparaatprofiel is al 120 dagen inactief. Tijdens het wekelijkse opschonen van gegevens worden inactieve apparaatprofielen uit de segmenten verwijderd.
* Het apparaat komt niet meer in aanmerking voor een segment omdat het door updates of wijzigingen in het apparaatprofiel wordt uitgesloten. Dit gebeurt wanneer de criteria van de segmentkwalificatie veranderen, of u past een [!DNL AND NOT] exploitant op een segmentregel toe, of specificeert [ recentie en frequentie ](../segments/recency-and-frequency.md) voorwaarden die minder dan/gelijk aan montages gebruiken. De gevallen van het gebruik worden beschreven in de [ Onmiddellijke documentatie van de Onderdrukking van het Apparaat 1&rbrace;.](instant-cross-device-suppression.md)

![ apparaat-slechts ](assets/device-only.png)

## Geen apparaatoptie en apparaatontsegmentatie {#no-device-option}

[!DNL Audience Manager] kan een apparaat-id uit een segment verwijderen wanneer uw [!UICONTROL Profile Merge Rule] de optie **[!UICONTROL Current Authenticated Profiles]** + **[!UICONTROL No Device Profile]** gebruikt. Onder deze omstandigheden vindt desegmentatie plaats wanneer de apparaat-id niet langer in aanmerking komt voor een segment omdat dit door updates of wijzigingen in het profiel voor alle apparaten wordt uitgesloten. Dit gebeurt wanneer de criteria van de segmentkwalificatie veranderen, of u past een [!UICONTROL AND NOT] exploitant op een segmentregel toe, of specificeert [ recentie en frequentie ](../segments/recency-and-frequency.md) voorwaarden die minder dan/gelijk aan montages gebruiken. De gevallen van het gebruik worden beschreven in de [ Onmiddellijke documentatie van de Onderdrukking van het Apparaat 1&rbrace;.](instant-cross-device-suppression.md)

![](assets/current-no-device.png)

## Grafiekopties apparaat en segmentatie van apparaat {#device-graph-options-unsegmentation}

[!DNL Audience Manager] kan meerdere apparaatprofielen uit een segment verwijderen wanneer uw [!UICONTROL Profile Merge Rule] een optie voor apparaatgrafieken gebruikt. De segmentatie gebeurt wanneer het samengevoegde profiel van het apparaat van de apparatengrafiek niet meer voor het segment kwalificeert omdat de updates of de veranderingen in dit samengevoegde profiel het van het segment diskwalificeren. Dit gebeurt wanneer de criteria van de segmentkwalificatie veranderen, of u past een [!UICONTROL AND NOT] exploitant op een segmentregel toe, of specificeert [ recentie en frequentie ](../segments/recency-and-frequency.md) voorwaarden die minder dan/gelijk aan montages gebruiken. De gevallen van het gebruik worden beschreven in de [ Onmiddellijke documentatie van de Onderdrukking van het Apparaat 1&rbrace;.](instant-cross-device-suppression.md)

>[!NOTE]
>
>**100 apparatengrens voor segmentevaluatie en diskwalificatie**.
>&#x200B;>Audience Manager voegt maximaal 100 apparaten samen bij het evalueren van segmenten met een profielsamenvoegregel die een apparaatgrafiek gebruikt. Audience Manager evalueert het huidige apparaat en tot 99 apparaten verbonden aan het huidige apparaat door een [ voor authentiek verklaard profiel ](../../reference/visitor-authentication-states.md) (dwars-apparaat identiteitskaart). Als het unsegment signaal wordt uitgegeven, zullen het huidige apparaat en de extra apparaten uit het segment in de bestemming worden verwijderd.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken](../../faq/faq-profile-merge.md)
>* [Onmiddellijke cross-device ondersteuning](instant-cross-device-suppression.md)
