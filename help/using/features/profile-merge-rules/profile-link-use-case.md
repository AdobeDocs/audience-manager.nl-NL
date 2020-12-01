---
description: Recommendations en gebruik gevallen voor segment het opnieuw richten en gepersonaliseerde segmentkwalificatie met de het apparatengrafiek van de Verbinding van het Profiel.
seo-description: Recommendations en gebruik gevallen voor segment het opnieuw richten en gepersonaliseerde segmentkwalificatie met de het apparatengrafiek van de Verbinding van het Profiel.
seo-title: Gebruiksscenario’s voor apparaatgrafieken van profielkoppelingen
solution: Audience Manager
title: Gebruiksscenario’s voor apparaatgrafieken van profielkoppelingen
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '325'
ht-degree: 9%

---


# Gebruiksscenario’s voor apparaatgrafieken van profielkoppelingen {#profile-link-device-graph-use-cases}

Recommendations en gebruik gevallen voor segment het opnieuw richten en gepersonaliseerde segmentkwalificatie met [!UICONTROL Profile Link Device Graph].

## Recommendations {#recommendations}

Bekijk de [!UICONTROL Profile Link] apparaatgrafiek voor campagnes die:

* Een hoog verificatieniveau hebben voor alle digitale eigenschappen. Gebruik een [externe optie van de apparatengrafiek](merge-rule-definitions.md#device-options) als u een kleine hoeveelheid voor authentiek verklaarde gebruikers hebt.
* Noodzaak van nauwkeurige gerichtheid op bekende doelgroepen. [!UICONTROL Profile Link Device Graph] wordt gebouwd gebruikend eerste-partij, voor authentiek verklaarde gegevens.
* Het bekende publiek van het doel over hun voor authentiek verklaarde en niet voor authentiek verklaarde staten in real time.

![](assets/merge-rule-triangle2.png)

## Toewijzing voor verschillende apparaten {#cross-device-personalization}

Laten we zeggen dat John drie apparaten bezit die hij regelmatig gebruikt om te zoeken naar vakantiepakketten: zijn laptop ([!DNL Device 1]), zijn smartphone ([!DNL Device 2]), en zijn tablet ([!DNL Device 3]). John gebruikt echter zijn apparaten om te zoeken naar verschillende onderdelen van de pakketdeals:

* Hij gebruikt zijn laptop om naar vluchten te zoeken;
* Hij gebruikt zijn smartphone om hotels te zoeken.
* Hij gebruikt zijn tablet om naar rondleidingen te zoeken.

Zelfs als John niet op alle drie bovengenoemde apparaten voor authentiek wordt verklaard, door **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** regel te gebruiken, kan een leverancier van het vakantiepakket deze apparaten aan het voor authentiek verklaarde profiel van John associëren, veronderstellend dat hij de laatste persoon was om op alle drie apparaten voor authentiek te verklaren.

![last-device-graph](assets/last-device-graph.png)

Aangezien Audience Manager elk apparaatprofiel kwalificeert dat deelnam aan de profielsamenvoeging voor een segment, worden alle drie apparaatprofielen gesegmenteerd. Met [!UICONTROL Profile Link Device Graph] kan Audience Manager het gedrag op alle drie apparaten bekijken en elk apparaat kwalificeren voor een segment waarvoor geen enkel apparaatprofiel afzonderlijk in aanmerking komt.

Dit [!UICONTROL Profile Merge Rule] laat marketers toe om een verenigbare ervaring aan alle apparaten te leveren die door één persoon worden bezeten, die op de gebruikersactiviteit in plaats van de individuele apparatenactiviteit wordt gebaseerd.

![interdevice-personalisatie](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Gebruiksscenario’s voor grafiek van externe apparaten](external-graph-use-cases.md)
>* [Algemene gebruiksscenario’s voor regels voor profielsamenvoeging](merge-rule-targeting-options.md)
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

