---
description: Recommendations en gebruik gevallen voor segment het opnieuw richten en gepersonaliseerde segmentkwalificatie met de het apparatengrafiek van de Verbinding van het Profiel.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Gebruiksscenario’s voor apparaatgrafieken van profielkoppelingen
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 7%

---

# Gebruiksscenario’s voor apparaatgrafieken van profielkoppelingen {#profile-link-device-graph-use-cases}

Recommendations en gebruik gevallen voor het opnieuw richten van segmenten en gepersonaliseerde segmentkwalificatie met de [!UICONTROL Profile Link Device Graph].

## Recommendations {#recommendations}

Neem de [!UICONTROL Profile Link] apparaatgrafiek voor campagnes die:

* Een hoog verificatieniveau hebben voor alle digitale eigenschappen. Een [grafiekoptie extern apparaat](merge-rule-definitions.md#device-options) als u een klein aantal geverifieerde gebruikers hebt.
* Noodzaak van nauwkeurige gerichtheid op bekende doelgroepen. De [!UICONTROL Profile Link Device Graph] wordt gebouwd gebruikend eerste-partij, voor authentiek verklaarde gegevens.
* Het bekende publiek van het doel over hun voor authentiek verklaarde en niet voor authentiek verklaarde staten in real time.

![](assets/merge-rule-triangle2.png)

## Toewijzing op meerdere apparaten {#cross-device-personalization}

Laten we zeggen dat John drie apparaten bezit die hij regelmatig gebruikt om te zoeken naar vakantiepakketten: zijn laptop ([!DNL Device 1]), zijn smartphone ([!DNL Device 2]) en zijn tablet ([!DNL Device 3]). John gebruikt echter zijn apparaten om te zoeken naar verschillende onderdelen van de pakketdeals:

* Hij gebruikt zijn laptop om naar vluchten te zoeken;
* Hij gebruikt zijn smartphone om hotels te zoeken.
* Hij gebruikt zijn tablet om naar rondleidingen te zoeken.

Zelfs als John niet op alle drie bovengenoemde apparaten voor authentiek wordt verklaard, door te gebruiken **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** regel, kan een vakantiepakketleverancier deze apparaten aan John voor authentiek verklaarde profiel associëren, veronderstellend dat hij de laatste persoon was om op alle drie apparaten voor authentiek te verklaren.

![last-device-graph](assets/last-device-graph.png)

Aangezien Audience Manager elk apparaatprofiel kwalificeert dat deelnam aan de profielsamenvoeging voor een segment, worden alle drie apparaatprofielen gesegmenteerd. De [!UICONTROL Profile Link Device Graph] staat Audience Manager toe om het gedrag over alle drie apparaten te bekijken en elk apparaat voor een segment te kwalificeren dat geen enkel apparatenprofiel voor zich kwalificeert.

Dit [!UICONTROL Profile Merge Rule] biedt marketers de mogelijkheid een consistente ervaring te bieden aan alle apparaten die eigendom zijn van één persoon, op basis van de gebruikersactiviteit in plaats van de afzonderlijke apparaatactiviteit.

![interdevice-personalisatie](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Gebruiksscenario’s voor grafiek van externe apparaten](external-graph-use-cases.md)
>* [Algemene gebruiksscenario’s voor regels voor profielsamenvoeging](merge-rule-targeting-options.md)
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

