---
description: Unsegmentation beschrijft processen die apparatenprofielen van segmenten onbruikbaar maken en verwijderen. De mogelijkheid om een apparaatprofiel uit een segment te verwijderen, is afhankelijk van de apparaatoptie die wordt gebruikt om een regel voor het samenvoegen van profielen te maken.
seo-description: Unsegmentation beschrijft processen die apparatenprofielen van segmenten onbruikbaar maken en verwijderen. De mogelijkheid om een apparaatprofiel uit een segment te verwijderen, is afhankelijk van de apparaatoptie die wordt gebruikt om een regel voor het samenvoegen van profielen te maken.
seo-title: Regels voor profielsamenvoeging en processen voor apparaatdesegmentatie
solution: Audience Manager
title: Regels voor profielsamenvoeging en processen voor apparaatdesegmentatie
uuid: b61c6de3-5fe4-4892-a05a-96a4cb35af34
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '503'
ht-degree: 6%

---


# Regels voor profielsamenvoeging en processen voor apparaatdesegmentatie {#profile-merge-rules-and-device-un-segmentation-processes}

Unsegmentation beschrijft processen die apparatenprofielen van segmenten onbruikbaar maken en verwijderen. Uw capaciteit om een apparatenprofiel uit een segment te verwijderen hangt van de apparatenoptie af die wordt gebruikt om tot [!UICONTROL Profile Merge Rule] te leiden.

## Beschikbare apparaatopties {#device-options}

Ter herinnering, [!UICONTROL Device Options] zijn beschikbaar in [!UICONTROL Profile Merge Rules Setup] sectie wanneer u [!UICONTROL Profile Merge Rule] creeert of uitgeeft.

## Optie voor huidige apparaatprofiel en segmentatie van apparaat {#current-device-profile-options}

**[!UICONTROL Device Profile]** is de standaardoptie van het apparatenprofiel voor een  [!UICONTROL Profile Merge Rule]. [!DNL Audience Manager] U kunt een apparaatprofiel uit een segment verwijderen wanneer u de  [!UICONTROL Profile Merge Rule] optie  **[!UICONTROL Device Profile]** gebruikt. Onder deze omstandigheden vindt ontsegmentatie plaats wanneer:

* Het apparaatprofiel is 120 dagen inactief. Tijdens het wekelijkse opschonen van gegevens worden inactieve apparaatprofielen uit de segmenten verwijderd.
* Het apparaat komt niet meer in aanmerking voor een segment omdat het door updates of wijzigingen in het apparaatprofiel wordt uitgesloten. Dit gebeurt wanneer de criteria van de segmentkwalificatie veranderen, of u past een [!DNL AND NOT] exploitant op een segmentregel toe, of [recency en frequentie](../segments/recency-and-frequency.md) voorwaarden specificeren die minder dan/gelijk aan montages gebruiken. Gebruiksgevallen worden beschreven in de [Onmiddellijke ondersteuning voor verschillende apparaten](instant-cross-device-suppression.md)-documentatie.

![alleen apparaat](assets/device-only.png)

## Geen apparaatoptie en apparaatsegmentatie {#no-device-option}

[!DNL Audience Manager] U kunt een apparaat-id uit een segment verwijderen wanneer u de  [!UICONTROL Profile Merge Rule] optie  **[!UICONTROL Current Authenticated Profiles]** +  **[!UICONTROL No Device Profile]** gebruikt. Onder deze omstandigheden vindt desegmentatie plaats wanneer de apparaat-id niet langer in aanmerking komt voor een segment omdat dit door updates of wijzigingen in het profiel voor alle apparaten wordt uitgesloten. Dit gebeurt wanneer de criteria van de segmentkwalificatie veranderen, of u past een [!UICONTROL AND NOT] exploitant op een segmentregel toe, of [recency en frequentie](../segments/recency-and-frequency.md) voorwaarden specificeren die minder dan/gelijk aan montages gebruiken. Gebruiksgevallen worden beschreven in de [Onmiddellijke ondersteuning voor verschillende apparaten](instant-cross-device-suppression.md)-documentatie.

![](assets/current-no-device.png)

## Grafiekopties apparaat en segmentatie van apparaat {#device-graph-options-unsegmentation}

[!DNL Audience Manager] U kunt meerdere apparaatprofielen uit een segment verwijderen wanneer u een grafiekoptie voor apparaten  [!UICONTROL Profile Merge Rule] gebruikt. De segmentatie gebeurt wanneer het samengevoegde profiel van het apparaat van de apparatengrafiek niet meer voor het segment kwalificeert omdat de updates of de veranderingen in dit samengevoegde profiel het van het segment diskwalificeren. Dit gebeurt wanneer de criteria van de segmentkwalificatie veranderen, of u past een [!UICONTROL AND NOT] exploitant op een segmentregel toe, of [recency en frequentie](../segments/recency-and-frequency.md) voorwaarden specificeren die minder dan/gelijk aan montages gebruiken. Gebruiksgevallen worden beschreven in de [Onmiddellijke ondersteuning voor verschillende apparaten](instant-cross-device-suppression.md)-documentatie.

>[!NOTE]
>
>**100 apparatengrens voor segmentbeoordeling en diskwalificatie**.
>Audience Manager voegt maximaal 100 apparaten samen bij het evalueren van segmenten met een profielsamenvoegregel die een apparaatgrafiek gebruikt. Audience Manager evalueert het huidige apparaat en tot 99 apparaten verbonden aan het huidige apparaat door [voor authentiek verklaard profiel](../../reference/visitor-authentication-states.md) (dwars-apparaat identiteitskaart). Als het unsegment signaal wordt uitgegeven, zullen het huidige apparaat en de extra apparaten uit het segment in de bestemming worden verwijderd.

![](assets/last-device-graph.png)

>[!MORELIKETHIS]
>
>* [Veelgestelde vragen over regels voor profielsamenvoeging en apparaatgrafieken](../../faq/faq-profile-merge.md)
>* [Onmiddellijke cross-device ondersteuning](instant-cross-device-suppression.md)

