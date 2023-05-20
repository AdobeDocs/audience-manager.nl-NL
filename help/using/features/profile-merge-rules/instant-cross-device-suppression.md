---
description: Onmiddellijke onderdrukking van apparaten is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Met de functie Onmiddellijke ondersteuning voor apparaten kunt u uw gebruikers een consistente ervaring bieden op alle apparaten. Deze ervaring wordt mogelijk gemaakt door de real-time unsegment mogelijkheden in Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Onmiddellijke cross-device ondersteuning
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '772'
ht-degree: 0%

---

# Onmiddellijke cross-device ondersteuning {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Gebruik de [!UICONTROL Instant Cross-Device Suppression] de mogelijkheid om uw gebruikers een consistente ervaring op verschillende apparaten te bieden. Deze ervaring wordt mogelijk gemaakt door de real-time unsegment mogelijkheden in Audience Manager.

## Overzicht {#overview}

[!UICONTROL Instant Cross-Device Suppression] levert twee belangrijke gebruiksgevallen: verbeterde gebruikerservaring en media-efficiëntie.

* **Verbeterde gebruikerservaring**: Gebruikers die uw product of service al hebben aangeschaft, zien niet dezelfde creatieve producten als voor de aankoop. In plaats daarvan kun je berichten weergeven waarin producten of services worden aangeboden die je weet dat ze niet zijn aangeschaft.
* **Media-efficiëntie**: Optimaliseer uw campagneuitgaven door een globale frequentiegrens over allen toe te passen [!DNL DSP]s. De frequentieklep kan in real-time worden geactiveerd voor meerdere apparaten die tot een gebruiker behoren.

De technische details van de realtime-ontsegmentatie worden uitvoerig beschreven in [Regels voor het samenvoegen van profielen en processen voor onsegmentering van apparaten](merge-rule-unsegment.md). Lees verder voor de praktische implementatie van de hierboven beschreven gebruiksgevallen.

## Niet activeren na conversie {#do-not-target-once}

Zorg ervoor dat gebruikers die al een product hebben geconverteerd (een product hebben aangeschaft, een abonnement hebben aangeschaft, enz.) zal niet het zelfde overseinen zien zoals vóór de omzetting. U kunt dit verkrijgen met de [!UICONTROL AND NOT] als volgt.

1. Maak een segment met behulp van twee kenmerken en gebruik de optie [!UICONTROL AND NOT] zoals weergegeven in de onderstaande afbeelding. U moet een op regel-gebaseerd bezit gebruiken om de omzettingsgebeurtenis voor te bepalen unsegment dat in real time moet teweegbrengen. Meer informatie over hoe [op regels gebaseerde kenmerken maken](../traits/create-onboarded-rule-based-traits.md).
2. Wijs het segment aan om het even welk aantal server-aan-server bestemmingen in real time toe. Lees meer over het toevoegen van segmenten aan [server-aan-server bestemmingen](../destinations/add-edit-segments.md).

Uw bezoekers komen in aanmerking voor het segment zolang zij niet hebben omgezet. Zodra zij voor de omzettingseigenschap in aanmerking komen, houden zij op de segmentregel te volgen en worden onmiddellijk verwijderd uit het segment.

![](assets/and_not_use_case.png)

## Niet activeren na x-indrukking {#do-not-target-after-x}

U kunt ervoor zorgen dat u uw gebruikers niet met dezelfde creatieve instellingen overstroomt door de instellingen voor recentie en frequentie in te stellen. In dit scenario maakt u een segment met twee kenmerken, zoals wordt beschreven in de onderstaande stappen.

1. Maak een segment met behulp van twee kenmerken en gebruik de optie [!UICONTROL AND] zoals weergegeven in de onderstaande afbeelding. U moet een op regel-gebaseerde eigenschap gebruiken om de immexemplaar te bepalen voor unsegment dat in real time moet worden teweeggebracht. Meer informatie over hoe [op regels gebaseerde kenmerken maken](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >U kunt [!UICONTROL Actionable Log Files] of [!UICONTROL Pixel Calls] om eigenschappen tot stand te brengen die op gebruikersdrukken worden gebaseerd. Meer informatie over [Werkbare logbestanden](../../integration/media-data-integration/actionable-log-files.md) en [Pixelaanroepen](../../integration/media-data-integration/impression-data-pixels.md).
2. Pas frequentiecontroles op de tweede eigenschap toe. Desgewenst kunt u ook de instellingen voor de frequentie toevoegen. Meer informatie over [hoe u recensie- en frequentiecontroles toepast](../segments/recency-and-frequency.md).
3. Wijs het segment aan om het even welk aantal server-aan-server bestemmingen in real time toe. Lees meer over het toevoegen van segmenten aan [server-aan-server bestemmingen](../destinations/add-edit-segments.md).

In dit scenario worden gebruikers die meer dan drie indrukken hebben verzameld, uit dit segment verwijderd en wordt deze bepaalde creatieve expressie niet meer weergegeven.

![](assets/impressions_use_case.png)

## Belangrijke aspecten van notitie - Verwerking {#processing-notes}

Houd rekening met de volgende aspecten met betrekking tot verwerking:

* Voor het in real time unsegment vermogen om te werken, moet u de gewenste segmenten aan server-aan-server bestemmingen in kaart brengen in real time.
* Voor apparaten die met een apparaat zijn verbonden door een [apparaatgrafiek](profile-link-use-case.md#recommendations)Wij handhaven een limiet van vier apparaten voor evaluatie en onsegmentering. Deze beperking wordt beschreven in [Grafiekopties apparaat en segmentatie apparaat](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* Het unsegment bevel zal in een partijdossier worden omvat, dat wordt verzonden naar bestemmingen om de 24 uur, voor veelvoudige apparaten die door de apparatengrafiek worden aangesloten.
* Het apparaat moet in real time (op [Rand](../../reference/system-components/components-edge.md) om segmentevaluatie in real time te veroorzaken. Voor kenmerken met een [!UICONTROL time-to-live (TTL)]  wanneer de eigenschap [!DNL TTL] is voldaan, wordt de segmentatie van het apparaat automatisch binnen 24 uur ongedaan gemaakt via het batchbestand. &#x200B; Meer informatie over hoe [Een interval voor verlopen van sporen instellen](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Als u het [!UICONTROL DCS API] aan op regel-gebaseerde eigenschappen op boord in real time, kunt u unsegment met het gebruik van activeren [!UICONTROL AND NOT] logica. Meer informatie over [gegevens verzenden naar de DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Belangrijke aspecten van notitie - Timing {#timing-notes}

Houd rekening met de volgende aspecten met betrekking tot timing:

* Een segment wordt opgeslagen op het tabblad [Rand](../../reference/system-components/components-edge.md) gedurende dezelfde periode als een apparaatprofiel wordt opgeslagen op de [!UICONTROL Edge], namelijk 14 dagen sinds laatste real-time interactie. Lees meer over het bewaren van gegevens in onze [Veelgestelde vragen over gegevensbewaring](../../faq/faq-privacy.md#data-retention-faq).
* Het vergt ongeveer 24 uren voor unsegment verrichting zich over te verspreiden [!DNL DCS] regio&#39;s. Meer informatie over onze [!DNL DCS] regio [hier](../../reference/system-components/components-data-collection.md) en [hier](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
