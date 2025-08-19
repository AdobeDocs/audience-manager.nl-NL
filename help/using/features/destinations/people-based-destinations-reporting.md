---
description: Mensen-Gebaseerde Doelen introduceren het begrip van Aandeelbare Publiek aan Audience Manager. Deze maatstaf helpt u te begrijpen hoeveel van de gehakte e-mailadressen Audience Manager met het bestemmingsplatform kan delen.
seo-description: People-Based Destinations introduce the notion of Shareable Audiences to Audience Manager. This metric helps you understand how many of the hashed email addresses Audience Manager can share with the destination platform.
seo-title: Shareable Audiences
solution: Audience Manager
title: Aandeelbaar publiek
feature: People-based Destinations
exl-id: 2860c105-1091-4779-bf40-e66faa941af0
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '505'
ht-degree: 0%

---

# Aandeelbaar publiek {#shareable-audiences}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

[!DNL People-Based Destinations] brengt de notie van [!DNL Shareable Audiences] naar Audience Manager. Deze maatstaf helpt u te begrijpen hoeveel van de gehakte e-mailadressen Audience Manager met het bestemmingsplatform kan delen.

[!DNL Shareable Audiences] is een metrische waarde die u helpt publieksgegevens te interpreteren in de context van [!DNL People-Based Destinations] . Deze maateenheid wordt weergegeven op de pagina [!UICONTROL Destinations] en op de pagina [!UICONTROL Segment] .

## Segment Shareable Publiek {#segment-shareable-audiences}

[!DNL Segment Shareable Audience] metrisch in de segmentpagina wijst op het aantal gehakte e-mailadressen van de gegevensbron met passende [ DPUUIDs ](../../reference/ids-in-aam.md), die ook voor het bepaalde segment in de bepaalde terugblik-achterperiode kwalificeren, gezien de profielfusieregel die op het wordt toegepast, en die Audience Manager met het bestemmingsplatform kan delen.

Deze metrische waarde heeft een terugkijkperiode van 1 dag. Dit helpt u het publieksbereik voor het segment in een specifieke bestemming begrijpen.

## Bestemmingsdeelbaar publiek {#destination-shareable-audience}

[!DNL Destination Shareable Audience] metrisch in een op mensen-gebaseerde bestemmingspagina wijst op het totale aantal gehakte e-mailadressen van de gegevensbron met passende [ DPUUIDs ](../../reference/ids-in-aam.md), die Audience Manager met het bestemmingsplatform, van alle segmenten kan delen die aan die bestemming worden in kaart gebracht.

![ shareable-publiek ](assets/dest-shareable-audiences.png)

Deze metrische waarde heeft een terugkijkperiode van het leven. Zo krijgt u meer inzicht in de schaal van het publiek dat u kunt bereiken via de gegevensbron voor gehashte e-mailadressen.

## Voorbeeld

Een klant van Audience Manager heeft een gegevensbron met 110.000 [ DPUUIDs ](../../reference/ids-in-aam.md) (CRM IDs). Zij nemen 100.000 gehakte e-mailadressen in Audience Manager op, om hen met veelvoudige op mensen-gebaseerde bestemmingen te gebruiken, en een synchronisatie van identiteitskaart voor de 100.000 gehakte e-mailadressen tegen CRM IDs uit te voeren. De klant kan de samenvoegregel [!DNL All Cross-Device Profiles] gebruiken om drie publiekssegmenten te maken:

* segment A met een bevolkingsaantal van 10.000, toegewezen aan bestemming A;
* segment B met een bevolkingsaantal van 20.000, toegewezen aan bestemming A;
* Segment C met een aantal inwoners van 50.000, toegewezen aan doel B.

In dit scenario:

* Segment A Shareable Audience = 10,000;
* Segment B Aandeelbaar publiek = 20,000;
* Segment C Aandeelbaar publiek = 50,000;
* doel A Aandeelbaar publiek = segment A Aandeelbaar publiek + segment B Aandeelbaar publiek = 30,000;
* Bestemming B Aandeelbaar publiek = Segment C Aandeelbaar publiek = 50.000.

![ shareable-publiek-diagram ](assets/shareable-audiences.png)

>[!NOTE]
>
>In het bovenstaande voorbeeld betekent dit niet dat alle 80.000 gehashte e-mailadressen van de drie segmenten overeenkomen met bestaande accounts op de doelplatforms. Het betekent alleen dat Audience Manager de hashed-id&#39;s van de drie segmenten naar hun respectieve bestemmingen verzendt. Wanneer het verzenden van publiekssegmenten naar op mensen-gebaseerde bestemmingen, komt de publieksaanpassing op de partnerkant voor. Bestemming A kan tot 30.000 passende gebruikersrekeningen hebben, terwijl Bestemming B tot 50.000 passende gebruikersrekeningen kan hebben, maar er is geen garantie van gelijke tarieven. Adobe heeft geen toegang tot partner-specifieke metriek. Zie [ Tarieven van de Gelijke ](../../faq/faq-people-based-destinations.md#match-rates) voor vaak gestelde vragen over Op mensen-Gebaseerde zicht van Doelen in gelijke tarieven.
