---
description: Onmiddellijke onderdrukking van apparaten is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Met de functie Onmiddellijke ondersteuning voor apparaten kunt u uw gebruikers een consistente ervaring bieden op alle apparaten. Deze ervaring wordt mogelijk gemaakt door de real-time unsegment mogelijkheden in Audience Manager.
seo-description: Onmiddellijke onderdrukking van apparaten is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Met de functie Onmiddellijke ondersteuning voor apparaten kunt u uw gebruikers een consistente ervaring bieden op alle apparaten. Deze ervaring wordt mogelijk gemaakt door de real-time unsegment mogelijkheden in Audience Manager.
seo-title: Onmiddellijke cross-device ondersteuning
title: Onmiddellijke cross-device ondersteuning
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge Rules
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '829'
ht-degree: 1%

---


# Onmiddellijke cross-device ondersteuning {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Gebruik de [!UICONTROL Instant Cross-Device Suppression] mogelijkheid om uw gebruikers een consistente ervaring op verschillende apparaten te bieden. Deze ervaring wordt mogelijk gemaakt door de real-time unsegment mogelijkheden in Audience Manager.

## Overzicht {#overview}

[!UICONTROL Instant Cross-Device Suppression] levert twee belangrijke gebruiksgevallen: verbeterde gebruikerservaring en media-efficiëntie.

* **Een verbeterde gebruikerservaring**: Gebruikers die uw product of service al hebben aangeschaft, zien niet dezelfde creatieve producten als voor de aankoop. In plaats daarvan kun je berichten weergeven waarin producten of services worden aangeboden die je weet dat ze niet zijn aangeschaft.
* **Media-efficiëntie**: Optimaliseer uw campagneuitgaven door een globale frequentiegrens over alle [!DNL DSP]s toe te passen. De frequentieklep kan in real-time worden geactiveerd voor meerdere apparaten die tot een gebruiker behoren.

De technische details van unsegmentation in real time worden beschreven in lengte in de Regels van de Fusie van het [Profiel en de Processen](merge-rule-unsegment.md)van de Un-Segmentatie van het Apparaat. Lees verder voor de praktische implementatie van de hierboven beschreven gebruiksgevallen.

## Geen Target na conversie {#do-not-target-once}

Zorg ervoor dat gebruikers die al een product hebben geconverteerd (een product hebben aangeschaft, een abonnement hebben aangeschaft, enz.) zal niet het zelfde overseinen zien zoals vóór de omzetting. U kunt dit verkrijgen gebruikend de [!UICONTROL AND NOT] logica, als volgt.

1. Maak een segment met behulp van twee kenmerken en gebruik de [!UICONTROL AND NOT] logica, zoals in de onderstaande afbeelding wordt getoond. U moet een op regel-gebaseerd bezit gebruiken om de omzettingsgebeurtenis voor te bepalen unsegment dat in real time moet teweegbrengen. Lees meer over hoe te om op regel-gebaseerde eigenschappen [tot stand te](../traits/create-onboarded-rule-based-traits.md)brengen.
2. Wijs het segment aan om het even welk aantal server-aan-server bestemmingen in real time toe. Lees over hoe te om segmenten aan [server-aan-server bestemmingen](../destinations/add-edit-segments.md)toe te voegen.

Uw bezoekers komen in aanmerking voor het segment zolang zij niet hebben omgezet. Zodra zij voor de omzettingseigenschap in aanmerking komen, houden zij op de segmentregel te volgen en worden onmiddellijk verwijderd uit het segment.

![](assets/and_not_use_case.png)

## Geen Target na x-indrukking {#do-not-target-after-x}

U kunt ervoor zorgen dat u uw gebruikers niet met dezelfde creatieve instellingen overstroomt door de instellingen voor recentie en frequentie in te stellen. In dit scenario maakt u een segment met twee kenmerken, zoals wordt beschreven in de onderstaande stappen.

1. Maak een segment met behulp van twee kenmerken en gebruik de [!UICONTROL AND] logica, zoals in de onderstaande afbeelding wordt getoond. U moet een op regel-gebaseerde eigenschap gebruiken om de immexemplaar te bepalen voor unsegment dat in real time moet worden teweeggebracht. Lees meer over hoe te om op regel-gebaseerde eigenschappen [tot stand te](../traits/create-onboarded-rule-based-traits.md)brengen.
   >[!NOTE]
   >
   >U kunt eigenschappen gebruiken [!UICONTROL Actionable Log Files] of [!UICONTROL Pixel Calls] tot stand brengen die op gebruikersdrukken worden gebaseerd. Lees meer over [Actionable Log Files](../../integration/media-data-integration/actionable-log-files.md) en [Pixel Calls](../../integration/media-data-integration/impression-data-pixels.md).
2. Pas frequentiecontroles op de tweede eigenschap toe. Desgewenst kunt u ook de instellingen voor de frequentie toevoegen. Lees meer over [hoe u de instellingen voor recentie en frequentie](../segments/recency-and-frequency.md)kunt toepassen.
3. Wijs het segment aan om het even welk aantal server-aan-server bestemmingen in real time toe. Lees over hoe te om segmenten aan [server-aan-server bestemmingen](../destinations/add-edit-segments.md)toe te voegen.

In dit scenario worden gebruikers die meer dan drie indrukken hebben verzameld, uit dit segment verwijderd en wordt deze bepaalde creatieve expressie niet meer weergegeven.

![](assets/impressions_use_case.png)

## Belangrijke aspecten van notitie - Verwerking {#processing-notes}

Houd rekening met de volgende aspecten met betrekking tot verwerking:

* Voor het in real time unsegment vermogen om te werken, moet u de gewenste segmenten aan server-aan-server bestemmingen in kaart brengen in real time.
* Voor apparaten die met een [apparatengrafiek](profile-link-use-case.md#recommendations)worden verbonden, dwingen wij een vier-apparatengrens betreffende evaluatie en unsegmentation af. Deze beperking wordt beschreven in de Opties van de Grafiek van het [Apparaat en de Ontsegmentatie](merge-rule-unsegment.md#device-graph-options-unsegmentation)van het Apparaat. &#x200B;
* Het unsegment bevel zal in een partijdossier worden omvat, dat wordt verzonden naar bestemmingen om de 24 uur, voor veelvoudige apparaten die door de apparatengrafiek worden aangesloten.
* Het apparaat moet in real time (op de [Rand](../../reference/system-components/components-edge.md) worden gezien om segmentevaluatie in real time te veroorzaken. Voor kenmerken die een waarde hebben [!UICONTROL time-to-live (TTL)] wanneer aan de eigenschap [!DNL TTL] wordt voldaan, wordt het apparaat automatisch binnen 24 uur ontsegmenteerd via het batchbestand. &#x200B; Lees meer over hoe te om een Interval van de Vervalsing van het Beetje te [plaatsen](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Als u aan op regel-gebaseerde [!UICONTROL DCS API] eigenschappen op boord in real time gebruikt, kunt u unsegment met het gebruik van de [!UICONTROL AND NOT] logica teweegbrengen. Meer informatie over het [verzenden van gegevens naar de DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Belangrijke aspecten van notitie - Timing {#timing-notes}

Houd rekening met de volgende aspecten met betrekking tot timing:

* Een segment zal op de [Rand](../../reference/system-components/components-edge.md) voor de zelfde tijdspanne worden opgeslagen aangezien een apparatenprofiel op de [!UICONTROL Edge], namelijk 14 dagen sinds laatste real-time interactie wordt opgeslagen. Lees meer over gegevensbewaring in onze veelgestelde vragen over [gegevensbewaring](../../faq/faq-privacy.md#data-retention-faq).
* Het duurt ongeveer 24 uren voor de unsegment verrichting zich over [!DNL DCS] gebieden voortbrengt. Lees meer over onze [!DNL DCS] regio&#39;s [hier](../..//reference/system-components/components-data-collection.md) en [hier](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
