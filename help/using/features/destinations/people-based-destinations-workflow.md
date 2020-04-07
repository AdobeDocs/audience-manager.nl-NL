---
description: Mensen-Gebaseerde Doelen biedt veelvoudige implementatiestrategieën aan, afhankelijk van hoe uw klantengegevens gestructureerd zijn. Dit artikel verstrekt een overzicht van de implementatiestappen die u voor Op mensen-Gebaseerde Doelen, afhankelijk van uw scenario moet volgen.
seo-description: 'Mensen-Gebaseerde Doelen biedt veelvoudige implementatiestrategieën aan, afhankelijk van hoe uw klantengegevens gestructureerd zijn. Dit artikel verstrekt een overzicht van de implementatiestappen die u voor Op mensen-Gebaseerde Doelen, afhankelijk van uw scenario moet volgen.  '
seo-title: Implementatieleiding voor op personen gebaseerde doelen
solution: Audience Manager
title: Implementatieleiding
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Implementatieleiding {#implementation-guidance}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

[!DNL People-Based Destinations] biedt veelvoudige implementatiestrategieën aan, afhankelijk van hoe uw klantengegevens gestructureerd zijn. Dit artikel biedt een overzicht van de implementatiestappen die u moet volgen, [!DNL People-Based Destinations]afhankelijk van uw scenario.

## Overzicht {#overview}

De configuratie van [!DNL People-Based Destinations] neemt u door veelvoudige secties van de Manager van het Publiek en vereist verschillende montages en gegevens over het in kaart brengen methodes, afhankelijk van welk soort klantengegevens u reeds in de Manager van het Publiek hebt, en welk soort publiek richt u wilt uitvoeren.

>[!IMPORTANT]
> Lees dit artikel zorgvuldig en volledig voordat u het configureert [!DNL People-Based Destinations]. Na het lezen van deze gids, zou u een duidelijk inzicht in het scenario moeten hebben dat u door zult toelaten [!DNL People-Based Destinations].

Er zijn zes implementatieaspecten die u moet verduidelijken voordat u kunt gebruiken [!DNL People-Based Destinations]. Dit artikel zal u helpen begrijpen wat uw huidige configuratie is, zodat u de implementatiestappen voor uw scenario kunt correct volgen.

![pbd-implementatie](assets/pbd-implementation.png)

## 1. Gebruiksscenario definiëren {#defining-your-use-case}

Voordat u begint met het implementeren [!DNL People-Based Destinations], moet u duidelijk definiëren voor welk gebruiksscenario u deze functie gebruikt. U kunt op twee manieren [!DNL People-Based Destinations] aan doelpubliek gebruiken, gebaseerd op publieksactiviteit:

**A) Doelgerichtheid van het publiek op basis van uw gecombineerde online- en offlinegebruikersactiviteit**. In dit scenario, wilt u bestaande publieksgegevens van de Manager van het Publiek met gegevens van uw intern [!DNL CRM] systeem combineren, en de resulterende publiekssegmenten verzenden aan [!DNL People-Based Destinations]. Hier is een voorbeeld dat dit scenario illustreert:

Uw bedrijf, een luchtvaartmaatschappij, heeft verschillende klantniveaus (Bronze, Silver, en Goud), en u wilt elk van de niveaus van gepersonaliseerde aanbiedingen via sociale platforms voorzien. U gebruikt Audience Manager om de klantactiviteiten op uw website te analyseren. Niet alle klanten gebruiken echter de mobiele app van de luchtvaartmaatschappij en sommige van hen hebben zich niet aangemeld bij de website van het bedrijf. Uw klantgegevens zijn meestal beperkt tot lidmaatschap-id&#39;s en e-mailadressen.

Als u deze wilt afstemmen op sociale media en vergelijkbare kanalen voor personen, kunt u uw gehashte e-mailadressen [](people-based-destinations-prerequisites.md) overbrengen naar Audience Manager en deze combineren met uw bestaande online activiteitenkenmerken om nieuwe publiekssegmenten te maken. Vervolgens kunt u deze segmenten gebruiken om uw doelgroep door te bladeren [!DNL People-Based Destinations].

**B) Doelgerichtheid van het publiek uitsluitend gebaseerd op uw offlinegebruikersactiviteit**. In dit scenario, bevat uw [!DNL CRM] systeem uw klanten e-mailadressen en andere klantenattributen, maar de klanten hebben helemaal niet met uw website in wisselwerking gestaan, zodat hebt u geen klantenactiviteit in de Manager van het Publiek. Hier is een voorbeeld dat dit scenario illustreert:

Uw bedrijf, een leverancier van de telecomdiensten, houdt klantengegevens zoals e-mailadressen en gekochte telecomplannen in een intern [!DNL CRM]. U wilt bestaande klanten op sociale platforms als doel hebben om hun upgradepakketten aan te bieden op basis van hun bestaande abonnementen. Om dit te doen, kunt u uw gehakte klanten e-mailadressen in de Manager van het Publiek opnemen, en segmenten creëren die op de bestaande klantenabonnementen worden gebaseerd. Vervolgens kunt u deze segmenten naar uw klanten sturen [!DNL People-Based Destinations] met persoonlijke aanbiedingen.

## 2. Het type e-mailadressen definiëren {#define-target-email}

De tweede stap bij het bepalen van uw implementatiestrategie bepaalt welk type van klant e-mailadressen u wilt richten.

**A) Doelgerichtheid van het publiek op basis van uw geverifieerde e-mailadressen**. In dit scenario zijn er meerdere accounts gekoppeld aan meerdere e-mailadressen en wilt u deze richten op persoonlijke aanbiedingen die alleen zijn gebaseerd op het e-mailadres dat ze in real-time op uw website verifiëren.

**B) Doelgerichtheid van het publiek op basis van al uw e-mailadressen**. In dit scenario zijn er meerdere accounts gekoppeld aan meerdere e-mailadressen en wilt u deze richten op al hun gekoppelde e-mailadressen, ongeacht de geverifieerde activiteit.

## 3. Identificeer het type van Klant IDs (CRM IDs) dat u hebt {#identify-customer-id}

Voor doelgroepen in [!DNL People-Based Destinations] hebt u [SHA256-gehashte](people-based-destinations-prerequisites.md) versies van uw e-mailadressen van klanten nodig. Afhankelijk van uw bestaande configuratie van de Manager van de Publiek, kunt u in één van de volgende twee scenario&#39;s vinden:

**A) De klant-id&#39;s ([DPUUID&#39;s](../../reference/ids-in-aam.md)) van de Audience Manager zijn al in kleine letters, gehashte e-mailadressen**. In dit scenario kunt u deze bestaande id&#39;s gebruiken om uw doelgroepen in te stellen [!DNL People-Based Destinations].

**B) De klant-id&#39;s ([DPUUID&#39;s](../../reference/ids-in-aam.md)) van de Audience Manager zijn geen kleine, gehashte e-mailadressen**. In dit scenario, kan uw bestaande klant IDs niet worden verzonden naar [!DNL People-Based Destinations]. Om te gebruiken [!DNL People-Based Destinations], moet u een synchronisatie van identiteitskaart tussen uw bestaande klant IDs en kleine, gehakte versies van uw klanten e-mailadressen uitvoeren. U doet dit door op [bestanden gebaseerde id-synchronisatie](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) of door [gedeclareerde id&#39;s](../declared-ids.md)te gebruiken.

## 4. Kwalificatie {#trait-qualification}

Om uw publiek binnen nauwkeurig te richten [!DNL People-Based Destinations], moeten uw gebruikers voor of regel-gebaseerde of ongebogen eigenschappen in aanmerking komen, afhankelijk van het type van publiek dat richt dat u wilt uitvoeren.

**A) Kwalificeer uw klant IDs en apparaat IDs in echt - tijd voor op regel-gebaseerde eigenschappen**. Deze optie is van toepassing op geval A van [1. Het definiëren van het hoofdlettergebruik](people-based-destinations-workflow.md#defining-your-use-case). Als uw plan doelpubliek op online en off-line activiteit wordt gebaseerd, dan zult u hoogstwaarschijnlijk reeds uw publiek voor op [regel-gebaseerde trekken](../traits/trait-and-segment-qualification-reference.md)kwalificeren.

**B) Ingebouwde gegevensbestanden** maken gebruik van de inwendige kenmerken van uw klant-id&#39;s. Deze optie is van toepassing op geval B van [1. Het definiëren van het hoofdlettergebruik](people-based-destinations-workflow.md#defining-your-use-case). Wanneer het richten van uw publiek dat op puur off-line activiteit wordt gebaseerd, moet u klant IDs voor aan boord genomen eigenschappen door [binnenkomende gegevensdossiers](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md)kwalificeren.

## 5. Gegevensbronnen en gehashte e-mailadressen aan boord maken of labelen {#create-label-data-sources}

Afhankelijk van het type van klant IDs dat u in de Manager van het Publiek hebt (zie [3. Identificeer het Type van identiteitskaart van de Klant (CRM IDs) dat u hebt](people-based-destinations-workflow.md#identify-customer-id), zult u in één van de volgende scenario&#39;s vinden:

**A) Een label toewijzen aan een bestaande gegevensbron**. Deze optie is van toepassing op het scenario waarin uw klanten-id&#39;s ([DPUUID&#39;s](../../reference/ids-in-aam.md)) van Audience Manager al in kleine letters zijn en gehashte e-mailadressen bevatten. In deze situatie, wat u moet doen is uw gegevensbron etiketteren die u identiteitskaarts in als [!DNL PII] gegevensbron opslaat. Zie [Gegevensbroninstellingen](../datasources-list-and-settings.md) voor meer informatie over de gegevensbroninstellingen. U moet ervoor zorgen dat de optie Kan niet worden gekoppeld aan persoonlijk identificeerbare gegevens is uitgeschakeld.

**B) Maak een nieuwe gegevensbron**. Deze optie is van toepassing op het scenario waarbij de klant-id&#39;s ([DPUUID&#39;s](../../reference/ids-in-aam.md)) van de Audience Manager geen gehashte e-mailadressen zijn. In dit geval moet u een nieuwe gegevensbron voor alle apparaten maken en de gehashte e-mailadressen aan boord van deze gegevensbron plaatsen. U kunt dit op twee manieren doen:

* Synchronisatie van op een bestand gebaseerde id gebruiken. Zie [Naam en Inhoudsvereisten voor ID-synchronisatiebestanden](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) voor meer informatie over hoe de id-synchronisatiebestanden eruit moeten zien. Wanneer u deze methode gebruikt, kunt u al uw gehashte e-mailadressen vanuit uw [!DNL CRM] database als doel instellen.
* Gebruik [gedeclareerde id&#39;s](../declared-ids.md) om uw gehashte e-mailadressen te declareren wanneer u geverifieerde klant-id&#39;s doorgeeft. Wanneer u deze methode gebruikt, richt Audience Manager namens u alleen uw gehashte e-mailadressen op van gebruikers die online zijn geverifieerd. De e-mailadressen die in op mensen-gebaseerde kanalen worden gericht zijn slechts degenen in de verklaarde de gebeurtenisvraag van identiteitskaart Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in realtime geactiveerd.

## 6. Een regel voor het samenvoegen van profielen gebruiken voor segmentatie {#use-profile-merge-rules}

Afhankelijk van uw gebruikscase (zie [1). Het bepalen van Uw Geval](people-based-destinations-workflow.md#defining-your-use-case)van het Gebruik), zijn er twee manieren om [!DNL Profile Merge Rules] voor segmentatie te gebruiken.

**A) Bestaande gebruiken[!DNL Profile Merge Rules]**. Deze optie is van toepassing op het eerste gebruiksgeval (doelgroep gebaseerd op gecombineerde online- en offlinegebruikersactiviteiten). In dit scenario, hebt u bestaande klantenactiviteit in de Manager van het Publiek en u hebt reeds minstens één Regel van de Fusie van het Profiel bepaald die u in segmentatie hebt gebruikt. In dit geval hoeft u geen nieuwe bestanden te maken[!DNL Profile Merge Rules].

**B) Maak een nieuwe regel voor[!DNL All Cross-Device Profiles]samenvoegen**. Deze optie is van toepassing op het tweede gebruiksgeval (doelgroep die uitsluitend op offlinegebruikersactiviteit is gebaseerd). In dit scenario brengt u uw off-line klantengegevens van uw [!DNL CRM] in de Manager van het Publiek, en wilt segmenten van die gegevens tot stand brengen. Hiertoe introduceert [!DNL People-Based Destinations] u een nieuwe, vierde regel voor het samenvoegen van profielen, genaamd **[!DNL All Cross-Device Profiles]**. Dit is de regel die u moet gebruiken wanneer het segmenteren van zuiver off-line gegevens.
