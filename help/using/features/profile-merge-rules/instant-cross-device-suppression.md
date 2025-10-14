---
description: Onmiddellijke onderdrukking van apparaten is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Met de functie Onmiddellijke ondersteuning voor apparaten kunt u uw gebruikers een consistente ervaring bieden op alle apparaten. Deze ervaring wordt mogelijk gemaakt door de real-time functionaliteit voor het ongedaan maken van segmenten in Audience Manager.
seo-description: Instant Cross-Device Suppression is the ability to suppress users across multiple devices connected to them when a particular experience occurs on any of these devices. Use the Instant Cross-Device Suppression capability to deliver a consistent experience across devices to your users. This experience is made possible by the real-time unsegment capabilities in Audience Manager.
seo-title: Instant Cross-Device Suppression
title: Onmiddellijke ondersteuning voor apparaten
uuid: cb11b9cb-6d7d-4aa9-91b0-c2715857d821
feature: Profile Merge
exl-id: b9686210-e1aa-4f0a-a549-27d29c94e963
source-git-commit: 2643bebea8618124d5c96906e8dc89e21024d51a
workflow-type: tm+mt
source-wordcount: '778'
ht-degree: 0%

---

# Onmiddellijke ondersteuning voor apparaten {#instant-cross-device-suppression}

[!UICONTROL Instant Cross-Device Suppression] is de capaciteit om gebruikers over veelvoudige apparaten te onderdrukken die met hen worden verbonden wanneer een bepaalde ervaring op om het even welk van deze apparaten voorkomt. Met de [!UICONTROL Instant Cross-Device Suppression] -functie kunt u uw gebruikers een consistente ervaring bieden op verschillende apparaten. Deze ervaring wordt mogelijk gemaakt door de real-time functionaliteit voor het ongedaan maken van segmenten in Audience Manager.

## Overzicht {#overview}

[!UICONTROL Instant Cross-Device Suppression] biedt twee belangrijke gebruiksscenario&#39;s: verbeterde gebruikerservaring en media-efficiëntie.

* **een betere gebruikerservaring**: De gebruikers die reeds uw product of de dienst kochten zullen niet de zelfde creatieve personen zien zoals vóór de aankoop. In plaats daarvan kun je berichten weergeven waarin producten of services worden aangeboden die je weet dat ze niet zijn aangeschaft.
* **de efficiency van Media**: Optimaliseer uw campagneuitgaven door een globale frequentiekapitaal over alle [!DNL DSP] s toe te passen. De frequentieklep kan in real-time worden geactiveerd voor meerdere apparaten die tot een gebruiker behoren.

De technische details van de onsegmentatie in real time worden beschreven in lengte in [&#x200B; de Regels van de Fusie van het Profiel en de Processen van de Un-Segmentatie van het Apparaat &#x200B;](merge-rule-unsegment.md). Lees verder voor de praktische implementatie van de hierboven beschreven gebruiksgevallen.

## Niet activeren na conversie {#do-not-target-once}

Zorg ervoor dat gebruikers die al een product hebben geconverteerd (een product hebben aangeschaft, een abonnement hebben aangeschaft enz.), niet hetzelfde bericht zien als vóór de conversie. U kunt dit als volgt verkrijgen met de logica [!UICONTROL AND NOT] .

1. Maak een segment met behulp van twee kenmerken en gebruik de logica [!UICONTROL AND NOT] , zoals in de onderstaande afbeelding wordt getoond. U moet een op regel-gebaseerd bezit gebruiken om de omzettingsgebeurtenis voor te bepalen unsegment dat in real time moet teweegbrengen. Lees meer over hoe te [&#x200B; regel-gebaseerde eigenschappen &#x200B;](../traits/create-onboarded-rule-based-traits.md) tot stand brengen.
2. Wijs het segment aan om het even welk aantal server-aan-server bestemmingen in real time toe. Lees over hoe te om segmenten aan [&#x200B; server-aan-server bestemmingen &#x200B;](../destinations/add-edit-segments.md) toe te voegen.

Uw bezoekers komen in aanmerking voor het segment zolang zij niet hebben omgezet. Zodra zij voor de omzettingseigenschap in aanmerking komen, houden zij op de segmentregel te volgen en worden onmiddellijk verwijderd uit het segment.

![](assets/and_not_use_case.png)

## Niet gericht na x-indrukkingen {#do-not-target-after-x}

U kunt ervoor zorgen dat u uw gebruikers niet met dezelfde creatieve instellingen overstroomt door de instellingen voor recentie en frequentie in te stellen. In dit scenario maakt u een segment met twee kenmerken, zoals wordt beschreven in de onderstaande stappen.

1. Maak een segment met behulp van twee kenmerken en gebruik de logica [!UICONTROL AND] , zoals in de onderstaande afbeelding wordt getoond. U moet een op regel-gebaseerde eigenschap gebruiken om de immexemplaar te bepalen voor unsegment dat in real time moet worden teweeggebracht. Lees meer over hoe te [&#x200B; regel-gebaseerde eigenschappen &#x200B;](../traits/create-onboarded-rule-based-traits.md) tot stand brengen.
   >[!NOTE]
   >
   >U kunt [!UICONTROL Actionable Log Files] of [!UICONTROL Pixel Calls] gebruiken om kenmerken te maken op basis van gebruikersindrukkingen. Lees meer over [&#x200B; Acteerbare Dossiers van het Logboek &#x200B;](../../integration/media-data-integration/actionable-log-files.md) en [&#x200B; de Vraag van het Pixel &#x200B;](../../integration/media-data-integration/impression-data-pixels.md).
2. Pas frequentiecontroles op de tweede eigenschap toe. Desgewenst kunt u ook de instellingen voor de frequentie toevoegen. Lees meer over [&#x200B; hoe te om recentie en frequentiecontroles &#x200B;](../segments/recency-and-frequency.md) toe te passen.
3. Wijs het segment aan om het even welk aantal server-aan-server bestemmingen in real time toe. Lees over hoe te om segmenten aan [&#x200B; server-aan-server bestemmingen &#x200B;](../destinations/add-edit-segments.md) toe te voegen.

In dit scenario worden gebruikers die meer dan drie indrukken hebben verzameld, uit dit segment verwijderd en wordt deze bepaalde creatieve expressie niet meer weergegeven.

![](assets/impressions_use_case.png)

## Belangrijke aspecten van notitie - Verwerking {#processing-notes}

Houd rekening met de volgende aspecten met betrekking tot verwerking:

* Voor het in real time unsegment vermogen om te werken, moet u de gewenste segmenten aan server-aan-server bestemmingen in kaart brengen in real time.
* Voor apparaten die met een apparaat door a [&#x200B; apparatengrafiek &#x200B;](profile-link-use-case.md#recommendations) worden verbonden, dwingen wij een vier-apparatengrens betreffende evaluatie en unsegmentation af. Deze beperking wordt beschreven in [&#x200B; de Opties van de Grafiek van het Apparaat en de Ontsegmentatie van het Apparaat &#x200B;](merge-rule-unsegment.md#device-graph-options-unsegmentation). &#x200B;
* Het unsegment bevel zal in een partijdossier worden omvat, dat wordt verzonden naar bestemmingen om de 24 uur, voor veelvoudige apparaten die door de apparatengrafiek worden aangesloten.
* Het apparaat moet in real time (op [&#x200B; Edge &#x200B;](../../reference/system-components/components-edge.md) worden gezien om segmentevaluatie in real time te veroorzaken. Voor kenmerken met een [!UICONTROL time-to-live (TTL)] wanneer aan de eigenschap [!DNL TTL] wordt voldaan, wordt de segmentatie van het apparaat automatisch binnen 24 uur ongedaan gemaakt via het batchbestand. &#x200B; Lees meer over hoe te [&#x200B; plaatsen een Interval van de Vervalsing van het Beetje &#x200B;](../traits/create-onboarded-rule-based-traits.md#set-expiration-interval).
* Als u [!UICONTROL DCS API] aan op regel-gebaseerde eigenschappen in real time gebruikt op boord, kunt u unsegment met het gebruik van [!UICONTROL AND NOT] logica teweegbrengen. Lees meer over [&#x200B; verzendend gegevens naar DCS API &#x200B;](../../api/dcs-intro/dcs-event-calls/dcs-url-send.md). &#x200B;

## Belangrijke aspecten van notitie - Timing {#timing-notes}

Houd rekening met de volgende aspecten met betrekking tot timing:

* Een segment zal op [&#x200B; Edge &#x200B;](../../reference/system-components/components-edge.md) voor de zelfde tijdsperiode worden opgeslagen zoals een apparatenprofiel op [!UICONTROL Edge] wordt opgeslagen, namelijk 14 dagen sinds laatste interactie in real time. Lees meer over gegevensbehoud in onze [&#x200B; Veelgestelde Veelgestelde vragen van het Behoud van Gegevens &#x200B;](../../faq/faq-privacy.md#data-retention-faq).
* Het duurt ongeveer 24 uur voordat de bewerking zonder segment wordt doorlopen in [!DNL DCS] -gebieden. Lees meer over onze [!DNL DCS] gebieden [&#x200B; hier &#x200B;](../../reference/system-components/components-data-collection.md) en [&#x200B; hier &#x200B;](../../api/dcs-intro/dcs-api-reference/dcs-regions.md).
