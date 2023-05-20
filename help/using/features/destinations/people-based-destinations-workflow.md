---
description: Mensen-Gebaseerde Doelen biedt veelvoudige implementatiestrategieën aan, afhankelijk van hoe uw klantengegevens gestructureerd zijn. Dit artikel verstrekt een overzicht van de implementatiestappen die u voor Op mensen-Gebaseerde Doelen, afhankelijk van uw scenario moet volgen.
seo-description: People-Based Destinations offers multiple implementation strategies, depending on how your customer data is structured. This article provides an overview of the implementation steps that you need to follow for People-Based Destinations, depending on your scenario.
seo-title: People-Based Destinations Implementation Guidance
solution: Audience Manager
title: Implementatieleiding
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1340'
ht-degree: 2%

---

# Implementatieleiding {#implementation-guidance}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

[!DNL People-Based Destinations] biedt veelvoudige implementatiestrategieën aan, afhankelijk van hoe uw klantengegevens gestructureerd zijn. Dit artikel biedt een overzicht van de implementatiestappen die u moet volgen voor [!DNL People-Based Destinations], afhankelijk van uw scenario.

## Overzicht {#overview}

De configuratie van [!DNL People-Based Destinations] neemt u door veelvoudige secties van Audience Manager en vereist verschillende montages en gegevens op het instappen methodes, afhankelijk van welk soort klantengegevens u reeds in Audience Manager hebt, en welk soort publiek richt u wilt uitvoeren.

>[!IMPORTANT]
> Voor het configureren [!DNL People-Based Destinations]Lees dit artikel zorgvuldig en volledig door. Na het lezen van deze gids, zou u een duidelijk inzicht in het scenario moeten hebben dat u door zult toelaten [!DNL People-Based Destinations].

Er zijn zes implementatieaspecten die u moet verduidelijken voordat u kunt gebruiken [!DNL People-Based Destinations]. Dit artikel zal u helpen begrijpen wat uw huidige configuratie is, zodat u de implementatiestappen voor uw scenario kunt correct volgen.

![pbd-implementatie](assets/pbd-implementation.png)

## 1. Gebruiksscenario definiëren {#defining-your-use-case}

Voordat u begint met implementeren [!DNL People-Based Destinations], moet u duidelijk het gebruiksgeval bepalen dat u deze eigenschap voor zult gebruiken. U kunt [!DNL People-Based Destinations] doelgroepen op twee manieren te richten , op basis van publieksactiviteiten :

**A) Doelgerichtheid van het publiek op basis van uw gecombineerde online- en offlinegebruikersactiviteit**. In dit scenario, wilt u bestaande publieksgegevens van Audience Manager met gegevens van uw intern combineren [!DNL CRM] systeem, en verzend de resulterende publiekssegmenten naar [!DNL People-Based Destinations]. Hier is een voorbeeld dat dit scenario illustreert:

Uw bedrijf, een luchtvaartmaatschappij, heeft verschillende klantniveaus (Bronze, Silver, en Goud), en u wilt elk van de niveaus van gepersonaliseerde aanbiedingen via sociale platforms voorzien. U gebruikt Audience Manager om klantactiviteiten op uw website te analyseren. Niet alle klanten gebruiken echter de mobiele app van de luchtvaartmaatschappij en sommige van hen hebben zich niet aangemeld bij de website van het bedrijf. Uw klantgegevens zijn meestal beperkt tot lidmaatschap-id&#39;s en e-mailadressen.

Als u deze wilt gebruiken voor verschillende sociale media en vergelijkbare kanalen voor personen, kunt u uw [gehashte e-mailadressen](people-based-destinations-prerequisites.md) in Audience Manager en combineer hen met uw bestaande online activiteiteneigenschappen, om nieuwe publiekssegmenten te bouwen. Vervolgens kunt u die segmenten gebruiken om uw publiek door te bladeren [!DNL People-Based Destinations].

**B) Doelgerichtheid van het publiek uitsluitend gebaseerd op uw offlinegebruikersactiviteit**. In dit scenario, uw [!DNL CRM] Het systeem bevat uw klanten e-mailadressen en andere klantenattributen, maar klanten hebben helemaal niet met uw website in wisselwerking gestaan, zodat hebt u geen klantenactiviteit in Audience Manager. Hier is een voorbeeld dat dit scenario illustreert:

Uw bedrijf, een aanbieder van telecommunicatiediensten, houdt klantgegevens zoals e-mailadressen en aangekochte telecomplannen in een intern [!DNL CRM]. U wilt bestaande klanten op sociale platforms als doel hebben om hun upgradepakketten aan te bieden op basis van hun bestaande abonnementen. Om dit te doen, kunt u uw gehakte klanten e-mailadressen in Audience Manager opnemen, en segmenten creëren die op de bestaande klantenabonnementen worden gebaseerd. Vervolgens kunt u deze segmenten naar [!DNL People-Based Destinations] om uw klanten met gepersonaliseerde aanbiedingen te richten.

## 2. Het type e-mailadressen definiëren {#define-target-email}

De tweede stap bij het bepalen van uw implementatiestrategie bepaalt welk type van klant e-mailadressen u wilt richten.

**A) Doelgerichtheid van het publiek op basis van uw geverifieerde e-mailadressen**. In dit scenario zijn er meerdere accounts gekoppeld aan meerdere e-mailadressen en wilt u deze richten op persoonlijke aanbiedingen die alleen zijn gebaseerd op het e-mailadres dat ze in real-time op uw website verifiëren.

**B) Doelgerichtheid van het publiek op basis van al uw bijbehorende e-mailadressen**. In dit scenario zijn er meerdere accounts gekoppeld aan meerdere e-mailadressen en wilt u deze richten op al hun gekoppelde e-mailadressen, ongeacht de geverifieerde activiteit.

## 3. Identificeer het type van Klant IDs (CRM IDs) dat u hebt {#identify-customer-id}

Doelgroepen in [!DNL People-Based Destinations] vereist dat u [SHA256 hashed](people-based-destinations-prerequisites.md) versies van uw klanten e-mailadressen. Afhankelijk van uw bestaande configuratie van de Audience Manager, kunt u in één van de volgende twee scenario&#39;s vinden:

**A) De klant-id&#39;s van uw Audience Manager ([DPUUID&#39;s](../../reference/ids-in-aam.md)) zijn al in kleine letters, e-mailadressen met hashing**. In dit scenario kunt u deze bestaande id&#39;s gebruiken om uw doelgroepen in te stellen [!DNL People-Based Destinations].

**B) Customer ID&#39;s van uw Audience Manager ([DPUUID&#39;s](../../reference/ids-in-aam.md)) zijn geen kleine letters, gehashte e-mailadressen**. In dit scenario kunnen uw bestaande klant-id&#39;s niet worden verzonden naar [!DNL People-Based Destinations]. Te gebruiken [!DNL People-Based Destinations], moet u een synchronisatie uitvoeren van identiteitskaart tussen uw bestaande klant IDs en kleine, gehakte versies van uw klanten e-mailadressen. Je doet dit via [bestandsgebaseerde id-synchronisatie](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) of door [gedeclareerde id&#39;s](../declared-ids.md).

## 4. Kwalificatie {#trait-qualification}

Uw doelgroep nauwkeurig instellen in [!DNL People-Based Destinations], moeten uw gebruikers voor of regel-gebaseerde of ongeboete eigenschappen in aanmerking komen, afhankelijk van het type van publiek gericht dat u wilt uitvoeren.

**A) Kwalificeer uw klant IDs en apparaat IDs in echt - tijd voor op regel-gebaseerde eigenschappen**. Deze optie is van toepassing op het gebruik van geval A van [1. Gebruiksscenario definiëren](people-based-destinations-workflow.md#defining-your-use-case). Als uw plan doelpubliek op online en off-line activiteit moet richten, dan zult u hoogstwaarschijnlijk reeds uw publiek voor kwalificeren [op regels gebaseerde kenmerken](../traits/trait-and-segment-qualification-reference.md).

**B) Ingebouwde traits tegen uw klant-id&#39;s via binnenkomende gegevensbestanden**. Deze optie is van toepassing op het gebruik van geval B vanuit [1. Gebruiksscenario definiëren](people-based-destinations-workflow.md#defining-your-use-case). Wanneer het richten van uw publiek dat op puur off-line activiteit wordt gebaseerd, moet u klant IDs voor onboard trekken door kwalificeren [binnenkomende gegevensbestanden](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md).

## 5. Gegevensbronnen en gehashte e-mailadressen aan boord maken of labelen {#create-label-data-sources}

Afhankelijk van het type klant-id&#39;s in Audience Manager (zie [3. Identificeer het type van Klant IDs (CRM IDs) dat u hebt](people-based-destinations-workflow.md#identify-customer-id), zult u in één van de volgende scenario&#39;s vinden:

**A) Een label toewijzen aan een bestaande gegevensbron**. Deze optie is op het scenario van toepassing waar uw klant-id&#39;s van de Audience Manager ([DPUUID&#39;s](../../reference/ids-in-aam.md)) zijn al kleine, gehashte e-mailadressen. In dit geval moet u een label toewijzen aan de gegevensbron waarin u de id&#39;s opslaat als een [!DNL PII] gegevensbron. Zie [Instellingen gegevensbron](../datasources-list-and-settings.md) voor meer informatie over de gegevensbroninstellingen. U moet ervoor zorgen dat de optie Kan niet worden gekoppeld aan persoonlijk identificeerbare gegevens is uitgeschakeld.

**B) Een nieuwe gegevensbron maken**. Deze optie is op het scenario van toepassing waar uw klant-id&#39;s van de Audience Manager ([DPUUID&#39;s](../../reference/ids-in-aam.md)) zijn geen gehashte e-mailadressen. In dit geval moet u een nieuwe gegevensbron voor alle apparaten maken en de gehashte e-mailadressen aan boord van deze gegevensbron plaatsen. U kunt dit op twee manieren doen:

* Gebruik op bestand-id gebaseerde synchronisatie. Zie [Naam- en contentvereisten voor id-synchronisatiebestanden](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) voor details over hoe id-synchronisatiebestanden eruit moeten zien. Als u deze methode gebruikt, kunt u zich richten op al uw gehashte e-mailadressen vanuit uw [!DNL CRM] database.
* Gebruiken [gedeclareerde id&#39;s](../declared-ids.md) om uw gehashte e-mailadressen te verklaren wanneer het overgaan in voor authentiek verklaarde klant IDs. Wanneer u deze methode gebruikt, richt Audience Manager namens u alleen uw gehashte e-mailadressen op van gebruikers die online zijn geverifieerd. De e-mailadressen die in op mensen-gebaseerde kanalen worden gericht zijn slechts degenen in de verklaarde de gebeurtenisvraag van identiteitskaart Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in real time geactiveerd.

## 6. Een regel voor het samenvoegen van profielen gebruiken voor segmentatie {#use-profile-merge-rules}

Afhankelijk van uw gebruikscase (zie [1. Gebruiksscenario definiëren](people-based-destinations-workflow.md#defining-your-use-case)), zijn er twee manieren om te gebruiken [!DNL Profile Merge Rules] voor segmentatie.

**A) Bestaande gebruiken[!DNL Profile Merge Rules]**. Deze optie is van toepassing op het eerste gebruiksgeval (doelgroep gebaseerd op gecombineerde online- en offlinegebruikersactiviteiten). In dit scenario, hebt u bestaande klantenactiviteit in Audience Manager en u hebt reeds minstens één Regel van de Fusie van het Profiel bepaald die u in segmentatie hebt gebruikt. In dit geval hoeft u geen nieuwe [!DNL Profile Merge Rules].

**B) Maak een nieuwe [!DNL All Cross-Device Profiles] Regel samenvoegen**. Deze optie is van toepassing op het tweede gebruiksgeval (doelgroep die uitsluitend op offlinegebruikersactiviteit is gebaseerd). In dit scenario brengt u uw off-line klantengegevens van uw [!DNL CRM] in Audience Manager, en wil segmenten van die gegevens tot stand brengen. Om dit te doen, [!DNL People-Based Destinations] introduceert een nieuwe, vierde regel voor het samenvoegen van profielen, genaamd **[!DNL All Cross-Device Profiles]**. Dit is de regel die u moet gebruiken wanneer het segmenteren van zuiver off-line gegevens.
