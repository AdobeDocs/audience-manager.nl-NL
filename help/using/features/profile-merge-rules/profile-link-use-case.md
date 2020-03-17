---
description: Aanbevelingen en gebruiksgevallen voor het opnieuw richten van segmenten en gepersonaliseerde segmentkwalificatie met de het apparatengrafiek van de Verbinding van het Profiel.
seo-description: Aanbevelingen en gebruiksgevallen voor het opnieuw richten van segmenten en gepersonaliseerde segmentkwalificatie met de het apparatengrafiek van de Verbinding van het Profiel.
seo-title: Gebruiksscenario's voor grafiekgebruik van profielkoppeling
solution: Audience Manager
title: Gebruiksscenario's voor grafiekgebruik van profielkoppeling
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Gebruiksscenario&#39;s voor grafiekgebruik van profielkoppeling {#profile-link-device-graph-use-cases}

Aanbevelingen en gebruiksgevallen voor segmentheroriëntering en gepersonaliseerde segmentkwalificatie met de [!UICONTROL Profile Link Device Graph]code.

## Aanbevelingen {#recommendations}

Bekijk de [!UICONTROL Profile Link] apparaatgrafiek voor campagnes die:

* Een hoog verificatieniveau hebben voor alle digitale eigenschappen. Gebruik een [externe grafiekoptie](merge-rule-definitions.md#device-options) voor apparaten als u een kleine hoeveelheid geverifieerde gebruikers hebt.
* Noodzaak van nauwkeurige gerichtheid op bekende doelgroepen. Het [!UICONTROL Profile Link Device Graph] is samengesteld met behulp van gegevens van de eerste partij die zijn geverifieerd.
* Het bekende publiek van het doel over hun voor authentiek verklaarde en niet voor authentiek verklaarde staten in real time.

![](assets/merge-rule-triangle2.png)

## Toewijzing op meerdere apparaten {#cross-device-personalization}

Laten we zeggen dat John drie apparaten bezit die hij regelmatig gebruikt om te zoeken naar vakantiepakketten: zijn laptop ([!DNL Device 1]), zijn smartphone ([!DNL Device 2]) en zijn tablet ([!DNL Device 3]). John gebruikt echter zijn apparaten om te zoeken naar verschillende onderdelen van de pakketdeals:

* Hij gebruikt zijn laptop om naar vluchten te zoeken;
* Hij gebruikt zijn smartphone om hotels te zoeken.
* Hij gebruikt zijn tablet om naar rondleidingen te zoeken.

Zelfs als John niet op alle drie bovengenoemde apparaten voor authentiek wordt verklaard, door **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** regel te gebruiken, kan een leverancier van het vakantiepakket deze apparaten aan John&#39;s voor authentiek verklaarde profiel associëren, veronderstellend dat hij de laatste persoon was om op alle drie apparaten voor authentiek te verklaren.

![last-device-graph](assets/last-device-graph.png)

Aangezien Audience Manager elk apparaatprofiel kwalificeert dat deelnam aan de profielsamenvoeging voor een segment, worden alle drie apparaatprofielen gesegmenteerd. Met [!UICONTROL Profile Link Device Graph] deze optie kan Audience Manager het gedrag op alle drie de apparaten bekijken en elk apparaat kwalificeren voor een segment waarvoor geen enkel apparaatprofiel afzonderlijk in aanmerking komt.

Dit [!UICONTROL Profile Merge Rule] laat marketers toe om een verenigbare ervaring aan alle apparaten te leveren die door één persoon worden bezeten, op de gebruikersactiviteit in plaats van de individuele apparatenactiviteit wordt gebaseerd.

![interdevice-personalisatie](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Gebruiksscenario&#39;s voor grafiek van externe apparaten](external-graph-use-cases.md)
>* [Algemene gebruiksscenario&#39;s voor regels voor het samenvoegen van profielen](merge-rule-targeting-options.md)
>* [Veelgestelde vragen over regels voor samenvoegen van profielen](../../faq/faq-profile-merge.md)

