---
description: Onmiddellijke onderdrukking van apparaten is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Met de functie Onmiddellijke ondersteuning voor apparaten kunt u uw gebruikers een consistente ervaring bieden op alle apparaten. Deze ervaring wordt mogelijk gemaakt door de real-time unsegment mogelijkheden in Audience Manager.
seo-description: Onmiddellijke onderdrukking van apparaten is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Met de functie Onmiddellijke ondersteuning voor apparaten kunt u uw gebruikers een consistente ervaring bieden op alle apparaten. Deze ervaring wordt mogelijk gemaakt door de real-time unsegment mogelijkheden in Audience Manager.
seo-title: Onmiddellijke cross-device ondersteuning
title: Onmiddellijke cross-device ondersteuning
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profielsamenvoeging
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '831'
ht-degree: 1%

---

# Onmiddellijke cross-device ondersteuning {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Met de [!UICONTROL Instant Cross-Device Suppression]-functie kunt u uw gebruikers een consistente ervaring bieden op verschillende apparaten. Deze ervaring wordt mogelijk gemaakt door de real-time unsegment mogelijkheden in Audience Manager.

## Overzicht {#overview}

[!UICONTROL Instant Cross-Device Suppression] levert twee belangrijke gebruiksgevallen: verbeterde gebruikerservaring en media-efficiëntie.

* **Een verbeterde gebruikerservaring**: Gebruikers die uw product of service al hebben aangeschaft, zien niet dezelfde creatieve producten als voor de aankoop. In plaats daarvan kun je berichten weergeven waarin producten of services worden aangeboden die je weet dat ze niet zijn aangeschaft.
* **Media-efficiëntie**: Optimaliseer uw campagneuitgaven door een globale frequentiegrens over alle  [!DNL DSP]s toe te passen. De frequentieklep kan in real-time worden geactiveerd voor meerdere apparaten die tot een gebruiker behoren.

De technische details van de onsegmentatie in real time worden beschreven in lengte in [de Regels van de Fusie van het Profiel en de Processen van de Un-Segmentatie van het Apparaat ](merge-rule-unsegment.md). Lees verder voor de praktische implementatie van de hierboven beschreven gebruiksgevallen.

## Niet richten na omgezette {#do-not-target-once}

Zorg ervoor dat gebruikers die al een product hebben geconverteerd (een product hebben aangeschaft, een abonnement hebben aangeschaft, enz.) zal niet het zelfde overseinen zien zoals vóór de omzetting. U kunt dit verkrijgen door de logica [!UICONTROL AND NOT] als volgt te gebruiken.

1. Maak een segment met behulp van twee kenmerken en gebruik de logica [!UICONTROL AND NOT], zoals in de onderstaande afbeelding wordt getoond. U moet een op regel-gebaseerd bezit gebruiken om de omzettingsgebeurtenis voor te bepalen unsegment dat in real time moet teweegbrengen. Lees meer over hoe te [regel-gebaseerde eigenschappen tot stand brengen](../traits/create-onboarded-rule-based-traits.md).
2. Wijs het segment aan om het even welk aantal server-aan-server bestemmingen in real time toe. Lees over hoe te om segmenten aan [server-aan-server bestemmingen ](../destinations/add-edit-segments.md) toe te voegen.

Uw bezoekers komen in aanmerking voor het segment zolang zij niet hebben omgezet. Zodra zij voor de omzettingseigenschap in aanmerking komen, houden zij op de segmentregel te volgen en worden onmiddellijk verwijderd uit het segment.

![](assets/and_not_use_case.png)

## Niet gericht na x-impressies {#do-not-target-after-x}

U kunt ervoor zorgen dat u uw gebruikers niet met dezelfde creatieve instellingen overstroomt door de instellingen voor recentie en frequentie in te stellen. In dit scenario maakt u een segment met twee kenmerken, zoals wordt beschreven in de onderstaande stappen.

1. Maak een segment met behulp van twee kenmerken en gebruik de logica [!UICONTROL AND], zoals in de onderstaande afbeelding wordt getoond. U moet een op regel-gebaseerde eigenschap gebruiken om de immexemplaar te bepalen voor unsegment dat in real time moet worden teweeggebracht. Lees meer over hoe te [regel-gebaseerde eigenschappen tot stand brengen](../traits/create-onboarded-rule-based-traits.md).
   >[!NOTE]
   >
   >U kunt [!UICONTROL Actionable Log Files] of [!UICONTROL Pixel Calls] gebruiken om eigenschappen tot stand te brengen die op gebruikersindrukkingen worden gebaseerd. Lees meer over [Handbare logbestanden](../../integration/media-data-integration/actionable-log-files.md) en [Pixelaanroepen](../../integration/media-data-integration/impression-data-pixels.md).
2. Pas frequentiecontroles op de tweede eigenschap toe. Desgewenst kunt u ook de instellingen voor de frequentie toevoegen. Lees meer over [hoe te om recentie en frequentiecontroles toe te passen](../segments/recency-and-frequency.md).
3. Wijs het segment aan om het even welk aantal server-aan-server bestemmingen in real time toe. Lees over hoe te om segmenten aan [server-aan-server bestemmingen ](../destinations/add-edit-segments.md) toe te voegen.

In dit scenario worden gebruikers die meer dan drie indrukken hebben verzameld, uit dit segment verwijderd en wordt deze bepaalde creatieve expressie niet meer weergegeven.

![](assets/impressions_use_case.png)

## Belangrijke aspecten van notitie - verwerking {#processing-notes}

Houd rekening met de volgende aspecten met betrekking tot verwerking:

* Voor het in real time unsegment vermogen om te werken, moet u de gewenste segmenten aan server-aan-server bestemmingen in kaart brengen in real time.
* Voor apparaten die met een [apparatengrafiek](profile-link-use-case.md#recommendations) worden aangesloten, dwingen wij een vier-apparatengrens betreffende evaluatie en unsegmentation af. Deze beperking wordt beschreven in [Apparaatgrafiekopties en Apparaatontsegmentatie](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* Het unsegment bevel zal in een partijdossier worden omvat, dat wordt verzonden naar bestemmingen om de 24 uur, voor veelvoudige apparaten die door de apparatengrafiek worden aangesloten.
* Het apparaat moet in real time (op [Edge](../../reference/system-components/components-edge.md) worden gezien om segmentevaluatie in real time te veroorzaken. Voor kenmerken met een [!UICONTROL time-to-live (TTL)] wanneer aan de eigenschap [!DNL TTL] wordt voldaan, wordt de segmentatie van het apparaat automatisch binnen 24 uur ongedaan gemaakt via het batchbestand. &#x200B; Lees meer over hoe te [Plaats een Interval van de Vervalsing van het Beetje ](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Als u [!UICONTROL DCS API] aan op regel-gebaseerde eigenschappen in real time gebruikt, kunt u unsegment met het gebruik van [!UICONTROL AND NOT] logica teweegbrengen. Lees meer over [het verzenden van gegevens naar DCS API](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Belangrijke aspecten van notitie - Timing {#timing-notes}

Houd rekening met de volgende aspecten met betrekking tot timing:

* Een segment wordt op de [Edge](../../reference/system-components/components-edge.md) opgeslagen gedurende dezelfde periode als een apparaatprofiel op [!UICONTROL Edge] wordt opgeslagen, namelijk 14 dagen sinds laatste real-time interactie. Lees meer over gegevensbewaring in onze [Veelgestelde vragen over gegevensbewaring](../../faq/faq-privacy.md#data-retention-faq).
* Het duurt ongeveer 24 uren voor de unsegment verrichting zich over [!DNL DCS] gebieden verspreidt. Lees meer over onze [!DNL DCS] gebieden [hier](../..//reference/system-components/components-data-collection.md) en [hier](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
