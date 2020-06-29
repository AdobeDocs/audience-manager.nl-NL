---
description: 'Mensen-Gebaseerde Doelen introduceren het begrip van Aandeelbare Publiek aan Audience Manager. Deze metrisch helpt u begrijpen hoeveel van de gehakte e-mailadressen Audience Manager met het bestemmingsplatform kan delen. '
seo-description: 'Mensen-Gebaseerde Doelen introduceren het begrip van Aandeelbare Publiek aan Audience Manager. Deze metrisch helpt u begrijpen hoeveel van de gehakte e-mailadressen Audience Manager met het bestemmingsplatform kan delen. '
seo-title: Aandeelbaar publiek
solution: Audience Manager
title: Aandeelbaar publiek
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '523'
ht-degree: 0%

---


# Aandeelbaar publiek {#shareable-audiences}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

[!DNL People-Based Destinations] het begrip Audience Manager [!DNL Shareable Audiences] te brengen. Deze metrisch helpt u begrijpen hoeveel van de gehakte e-mailadressen Audience Manager met het bestemmingsplatform kan delen.

[!DNL Shareable Audiences] is metrisch die u helpt publieksgegevens in de context van interpreteren [!DNL People-Based Destinations]. U kunt deze metrische waarde op de [!UICONTROL Destinations] pagina en op de [!UICONTROL Segment] pagina zien.

## Segment Shareable Publiek {#segment-shareable-audiences}

Metrisch in de segmentpagina wijst op het aantal gehakte e-mailadressen van de gegevensbron met passende [!DNL Segment Shareable Audience] DPUUIDs [](../../reference/ids-in-aam.md), die ook voor het bepaalde segment in de bepaalde terugkijkperiode kwalificeren, gezien de toegepaste regel van de profielfusie, en die Audience Manager kan met het bestemmingsplatform delen.

Deze metrische waarde heeft een terugkijkperiode van 1 dag. Dit helpt u het publieksbereik voor het segment in een specifieke bestemming begrijpen.

## Bestemmingsdeelbaar publiek {#destination-shareable-audience}

Metrisch in een op mensen-gebaseerde bestemmingspagina wijst op het totale aantal gehakte e-mailadressen van de gegevensbron met passende [!DNL Destination Shareable Audience] DPUUIDs [](../../reference/ids-in-aam.md), die Audience Manager met het bestemmingsplatform, van alle segmenten kan delen die aan die bestemming worden in kaart gebracht.

![deelbaar publiek](assets/dest-shareable-audiences.png)

Deze metrische waarde heeft een terugkijkperiode van het leven. Zo krijgt u meer inzicht in de schaal van het publiek dat u kunt bereiken via de gegevensbron voor gehashte e-mailadressen.

## Voorbeeld

Een klant van de Audience Manager heeft een gegevensbron met 110.000 [DPUUIDs](../../reference/ids-in-aam.md) (CRM IDs). Zij nemen 100.000 gehakte e-mailadressen in Audience Manager op, om hen met veelvoudige op mensen-gebaseerde bestemmingen te gebruiken, en een synchronisatie van identiteitskaart voor de 100.000 gehakte e-mailadressen tegen CRM IDs uit te voeren. De klant kan de [!DNL All Cross-Device Profiles] fusieregel gebruiken om drie publiekssegmenten tot stand te brengen:

* segment A met een bevolkingsaantal van 10.000, toegewezen aan bestemming A;
* segment B met een bevolkingsaantal van 20.000, toegewezen aan bestemming A;
* Segment C met een aantal inwoners van 50.000, toegewezen aan doel B.

In dit scenario:

* Segment A Shareable Audience = 10,000;
* Segment B Aandeelbaar publiek = 20,000;
* Segment C Aandeelbaar publiek = 50,000;
* doel A Aandeelbaar publiek = segment A Aandeelbaar publiek + segment B Aandeelbaar publiek = 30,000;
* Bestemming B Aandeelbaar publiek = Segment C Aandeelbaar publiek = 50.000.

![deelbaar publiek-diagram](assets/shareable-audiences.png)

>[!NOTE]
>
>In het bovenstaande voorbeeld betekent dit niet dat alle 80.000 gehashte e-mailadressen van de drie segmenten overeenkomen met bestaande accounts op de doelplatforms. Het betekent slechts dat de Audience Manager de gehakte herkenningstekens van de drie segmenten naar hun respectieve bestemmingen verzendt. Wanneer het verzenden van publiekssegmenten naar op mensen-gebaseerde bestemmingen, komt de publieksaanpassing op de partnerkant voor. Bestemming A kan tot 30.000 passende gebruikersrekeningen hebben, terwijl Bestemming B tot 50.000 passende gebruikersrekeningen kan hebben, maar er is geen garantie van gelijke tarieven. Adobe heeft geen toegang tot partnerspecifieke gegevens. Zie [Tarieven](../../faq/faq-people-based-destinations.md#match-rates) van de Gelijke voor vaak gestelde vragen over Op mensen-Gebaseerde de zichtbaarheid van Doelen in gelijke tarieven.
