---
description: Aanbevelingen en gebruiksgevallen voor het opnieuw richten van segmenten en gepersonaliseerde segmentkwalificatie met de het apparatengrafiek van de Verbinding van het Profiel.
seo-description: Recommendations and use cases for segment retargeting and personalized segment qualification with the Profile Link device graph.
seo-title: Profile Link Device Graph Use Cases
solution: Audience Manager
title: Gebruiksscenario's voor grafiekgebruik van profielkoppeling
uuid: bd5567fd-fcd5-40ba-b6f1-035d2ddbcd3a
feature: Profile Merge
exl-id: 8712d02f-c431-4116-8807-41f9e2dda44c
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '302'
ht-degree: 3%

---

# Gebruiksscenario&#39;s voor grafiekgebruik van profielkoppeling {#profile-link-device-graph-use-cases}

Aanbevelingen en gebruiksgevallen voor het opnieuw toewijzen van segmenten en gepersonaliseerde segmentkwalificatie met de [!UICONTROL Profile Link Device Graph] .

## Aanbevelingen {#recommendations}

Bekijk de apparaatgrafiek van [!UICONTROL Profile Link] voor campagnes die:

* Een hoog verificatieniveau hebben voor alle digitale eigenschappen. Gebruik een [&#x200B; externe optie van de apparatengrafiek &#x200B;](merge-rule-definitions.md#device-options) als u een kleine hoeveelheid voor authentiek verklaarde gebruikers hebt.
* Noodzaak van nauwkeurige gerichtheid op bekende doelgroepen. [!UICONTROL Profile Link Device Graph] wordt gebouwd gebruikend eerste-partij, voor authentiek verklaarde gegevens.
* Het bekende publiek van het doel over hun voor authentiek verklaarde en niet voor authentiek verklaarde staten in real time.

![](assets/merge-rule-triangle2.png)

## Toewijzing op meerdere apparaten {#cross-device-personalization}

Laten wij zeggen John bezit drie apparaten die hij regelmatig gebruikt om naar vakantiepakketovereenkomsten te zoeken: zijn laptop ([!DNL Device 1]), zijn smartphone ([!DNL Device 2]), en zijn tablet ([!DNL Device 3]). John gebruikt echter zijn apparaten om te zoeken naar verschillende onderdelen van de pakketdeals:

* Hij gebruikt zijn laptop om naar vluchten te zoeken;
* Hij gebruikt zijn smartphone om hotels te zoeken.
* Hij gebruikt zijn tablet om naar rondleidingen te zoeken.

Zelfs als John niet voor authentiek wordt verklaard op alle drie bovengenoemde apparaten, door de **[!UICONTROL Last Authenticated Profiles]** + **[!UICONTROL Profile Link Device Graph]** regel te gebruiken, kan een vakantiepakketleverancier deze apparaten aan het voor authentiek verklaarde profiel van John associëren, veronderstellend dat hij de laatste persoon was om op alle drie apparaten voor authentiek te verklaren.

![&#x200B; last-apparaat-grafiek &#x200B;](assets/last-device-graph.png)

Aangezien Audience Manager elk apparaatprofiel kwalificeert dat deelnam aan de profielsamenvoeging voor een segment, worden alle drie apparaatprofielen gesegmenteerd. Met [!UICONTROL Profile Link Device Graph] kan Audience Manager het gedrag op alle drie apparaten bekijken en elk apparaat kwalificeren voor een segment waarvoor geen enkel apparaatprofiel afzonderlijk in aanmerking komt.

Hierdoor kunnen marketers alle apparaten die eigendom zijn van één persoon een consistente ervaring bieden op basis van de gebruikersactiviteit in plaats van de afzonderlijke apparaatactiviteit. [!UICONTROL Profile Merge Rule]

![&#x200B; dwars-apparaat-verpersoonlijking &#x200B;](assets/cross-device-personalization.png)

>[!MORELIKETHIS]
>
>* [Gebruiksscenario’s voor grafiek van externe apparaten](external-graph-use-cases.md)
>* [Algemene gebruiksscenario’s voor regels voor profielsamenvoeging](merge-rule-targeting-options.md)
>* [&#x200B; Veelgestelde vragen van de Regels van de Fusie van het Profiel &#x200B;](../../faq/faq-profile-merge.md)
