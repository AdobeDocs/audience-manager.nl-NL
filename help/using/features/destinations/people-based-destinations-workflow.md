---
description: Mensen-Gebaseerde Doelen biedt veelvoudige implementatiestrategieën aan, afhankelijk van hoe uw klantengegevens gestructureerd zijn. Dit artikel verstrekt een overzicht van de implementatiestappen die u voor Op mensen-Gebaseerde Doelen, afhankelijk van uw scenario moet volgen.
seo-description: 'Mensen-Gebaseerde Doelen biedt veelvoudige implementatiestrategieën aan, afhankelijk van hoe uw klantengegevens gestructureerd zijn. Dit artikel verstrekt een overzicht van de implementatiestappen die u voor Op mensen-Gebaseerde Doelen, afhankelijk van uw scenario moet volgen.  '
seo-title: Implementatieleiding voor op personen gebaseerde doelen
solution: Audience Manager
title: Implementatieleiding
feature: People-based Destinations
exl-id: 224334d5-419c-4bb1-b76c-ce996a543b7a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '1381'
ht-degree: 2%

---

# Implementatieleiding {#implementation-guidance}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

[!DNL People-Based Destinations] biedt veelvoudige implementatiestrategieën aan, afhankelijk van hoe uw klantengegevens gestructureerd zijn. Dit artikel verstrekt een overzicht van de implementatiestappen die u voor [!DNL People-Based Destinations], afhankelijk van uw scenario moet volgen.

## Overzicht {#overview}

De configuratie van [!DNL People-Based Destinations] neemt u door veelvoudige secties van Audience Manager en vereist verschillende montages en gegevens op instapingsmethodes, afhankelijk van welk soort klantengegevens u reeds in Audience Manager hebt, en welk soort publiek richt u wilt uitvoeren.

>[!IMPORTANT]
> Lees dit artikel zorgvuldig en volledig voordat u [!DNL People-Based Destinations] configureert. Na het lezen van deze gids, zou u een duidelijk inzicht in het scenario moeten hebben dat u door [!DNL People-Based Destinations] zult toelaten.

Er zijn zes implementatieaspecten die u moet verduidelijken voordat u [!DNL People-Based Destinations] gebruikt. Dit artikel zal u helpen begrijpen wat uw huidige configuratie is, zodat u de implementatiestappen voor uw scenario kunt correct volgen.

![pbd-implementatie](assets/pbd-implementation.png)

## 1. Uw gebruiksscenario {#defining-your-use-case} definiëren

Voordat u met de implementatie van [!DNL People-Based Destinations] begint, moet u duidelijk het gebruiksscenario definiëren waarvoor u deze functie gebruikt. U kunt [!DNL People-Based Destinations] aan doelpubliek op twee manieren gebruiken, gebaseerd op publieksactiviteit:

**A) Doelgerichtheid van het publiek op basis van uw gecombineerde online- en offlinegebruikersactiviteit**. In dit scenario, wilt u bestaande publieksgegevens van Audience Manager met gegevens van uw intern [!DNL CRM] systeem combineren, en de resulterende publiekssegmenten verzenden naar [!DNL People-Based Destinations]. Hier is een voorbeeld dat dit scenario illustreert:

Uw bedrijf, een luchtvaartmaatschappij, heeft verschillende klantniveaus (Bronze, Silver, en Goud), en u wilt elk van de niveaus van gepersonaliseerde aanbiedingen via sociale platforms voorzien. U gebruikt Audience Manager om klantactiviteiten op uw website te analyseren. Niet alle klanten gebruiken echter de mobiele app van de luchtvaartmaatschappij en sommige van hen hebben zich niet aangemeld bij de website van het bedrijf. Uw klantgegevens zijn meestal beperkt tot lidmaatschap-id&#39;s en e-mailadressen.

Als u deze wilt gebruiken voor verschillende sociale media en vergelijkbare kanalen voor personen, kunt u uw [gehashte e-mailadressen](people-based-destinations-prerequisites.md) in de Audience Manager plaatsen en deze combineren met uw bestaande online activiteitenkenmerken, zodat u nieuwe publiekssegmenten kunt maken. Vervolgens kunt u die segmenten gebruiken om uw publiek als doel in te stellen via [!DNL People-Based Destinations].

**B) Doelgerichtheid van het publiek uitsluitend gebaseerd op uw offlinegebruikersactiviteit**. In dit scenario bevat uw [!DNL CRM]-systeem uw klanten e-mailadressen en andere klantkenmerken, maar klanten hebben helemaal niet met uw website gewerkt, zodat u geen activiteiten van klanten in de Audience Manager hebt. Hier is een voorbeeld dat dit scenario illustreert:

Uw bedrijf, een aanbieder van telecommunicatieservices, bewaart klantgegevens zoals e-mailadressen en aangekochte telecomplannen in een interne [!DNL CRM]. U wilt bestaande klanten op sociale platforms als doel hebben om hun upgradepakketten aan te bieden op basis van hun bestaande abonnementen. Om dit te doen, kunt u uw gehakte klanten e-mailadressen in Audience Manager opnemen, en segmenten creëren die op de bestaande klantenabonnementen worden gebaseerd. Vervolgens kunt u deze segmenten naar [!DNL People-Based Destinations] sturen om uw klanten te richten op persoonlijke aanbiedingen.

## 2. Bepaal het Type van Gerichte E-mailadressen {#define-target-email}

De tweede stap bij het bepalen van uw implementatiestrategie bepaalt welk type van klant e-mailadressen u wilt richten.

**A) Doelgerichtheid van het publiek op basis van uw geverifieerde e-mailadressen**. In dit scenario zijn er meerdere accounts gekoppeld aan meerdere e-mailadressen en wilt u deze richten op persoonlijke aanbiedingen die alleen zijn gebaseerd op het e-mailadres dat ze in real-time op uw website verifiëren.

**B) Doelgerichtheid van het publiek op basis van al uw e-mailadressen**. In dit scenario zijn er meerdere accounts gekoppeld aan meerdere e-mailadressen en wilt u deze richten op al hun gekoppelde e-mailadressen, ongeacht de geverifieerde activiteit.

## 3. Identificeer het type van Klant IDs (CRM IDs) dat u {#identify-customer-id} hebt

Voor doelgroepen in [!DNL People-Based Destinations] moet u [SHA256 hashed](people-based-destinations-prerequisites.md) versies van uw e-mailadressen van de klant verzenden. Afhankelijk van uw bestaande configuratie van de Audience Manager, kunt u in één van de volgende twee scenario&#39;s vinden:

**A) De klant-id&#39;s van uw Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) zijn al in kleine letters, gehashte e-mailadressen**. In dit scenario, kunt u deze bestaande IDs gebruiken om uw publiek in [!DNL People-Based Destinations] te richten.

**B) De klant-id&#39;s van uw Audience Manager ([DPUUIDs](../../reference/ids-in-aam.md)) zijn geen kleine, gehashte e-mailadressen**. In dit scenario kunnen uw bestaande klant-id&#39;s niet worden verzonden naar [!DNL People-Based Destinations]. Als u [!DNL People-Based Destinations] wilt gebruiken, moet u een id-synchronisatie uitvoeren tussen uw bestaande klant-id&#39;s en kleine, gehashte versies van uw klanten-e-mailadressen. U doet dit of door [op dossier-gebaseerde synchronisatie van identiteitskaart](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) of door [verklaarde IDs](../declared-ids.md) te gebruiken.

## 4. Kwalificatie volgens handelsmerk {#trait-qualification}

Om uw publiek in [!DNL People-Based Destinations] nauwkeurig te richten, moeten uw gebruikers voor of op regel-gebaseerde of onboard eigenschappen kwalificeren, afhankelijk van het type van publiek gericht dat u wilt uitvoeren.

**A) Kwalificeer uw klant IDs en apparaat IDs in echt - tijd voor op regel-gebaseerde eigenschappen**. Deze optie is van toepassing op geval A van [1. Het bepalen van Uw Geval van het Gebruik](people-based-destinations-workflow.md#defining-your-use-case). Als uw plan doelpubliek op online en off-line activiteit wordt gebaseerd, dan zult u hoogstwaarschijnlijk reeds uw publiek voor [op regel-gebaseerde trekken](../traits/trait-and-segment-qualification-reference.md) kwalificeren.

**B) Ingebouwde gegevensbestanden** maken gebruik van de inwendige kenmerken van uw klant-id&#39;s. Deze optie is van toepassing op geval B van [1. Het bepalen van Uw Geval van het Gebruik](people-based-destinations-workflow.md#defining-your-use-case). Wanneer het richten van uw publiek dat op puur off-line activiteit wordt gebaseerd, moet u klant IDs voor aan boord genomen eigenschappen door [binnenkomende gegevensdossiers](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) kwalificeren.

## 5. Gegevensbronnen maken of labelen en gehashte e-mailadressen aan boord {#create-label-data-sources}

Afhankelijk van het type klant-id&#39;s dat u in Audience Manager hebt (zie [3. Identificeer het Type van identiteitskaart van de Klant (CRM IDs) dat u](people-based-destinations-workflow.md#identify-customer-id) hebt, zult u in één van de volgende scenario&#39;s vinden:

**A) Een label toewijzen aan een bestaande gegevensbron**. Deze optie is van toepassing op het scenario waarin uw klant-id&#39;s voor de Audience Manager ([DPUUID&#39;s](../../reference/ids-in-aam.md)) al in kleine letters zijn, gehashte e-mailadressen. In deze situatie, wat u moet doen is uw gegevensbron etiketteren die u identiteitskaarts in als [!DNL PII] gegevensbron opslaat. Zie [Gegevensbroninstellingen](../datasources-list-and-settings.md) voor meer informatie over de gegevensbroninstellingen. U moet ervoor zorgen dat de optie Kan niet worden gekoppeld aan persoonlijk identificeerbare gegevens is uitgeschakeld.

**B) Maak een nieuwe gegevensbron**. Deze optie is van toepassing op het scenario waarin uw klant-id&#39;s voor Audience Managers ([DPUUID&#39;s](../../reference/ids-in-aam.md)) geen gehashte e-mailadressen zijn. In dit geval moet u een nieuwe gegevensbron voor alle apparaten maken en de gehashte e-mailadressen aan boord van deze gegevensbron plaatsen. U kunt dit op twee manieren doen:

* Gebruik op bestand-id gebaseerde synchronisatie. Zie [Naam- en contentvereisten voor id-synchronisatiebestanden](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) voor details over hoe id-synchronisatiebestanden eruit moeten zien. Wanneer u deze methode gebruikt, kunt u al uw gehakte e-mailadressen van uw [!DNL CRM] gegevensbestand richten.
* Gebruik [gedeclareerde id&#39;s](../declared-ids.md) om uw gehashte e-mailadressen te declareren wanneer u geverifieerde klant-id&#39;s doorgeeft. Wanneer u deze methode gebruikt, richt Audience Manager namens u alleen uw gehashte e-mailadressen op van gebruikers die online zijn geverifieerd. De e-mailadressen die in op mensen-gebaseerde kanalen worden gericht zijn slechts degenen in de verklaarde de gebeurtenisvraag van identiteitskaart Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in real time geactiveerd.

## 6. Een regel voor het samenvoegen van profielen gebruiken voor segmentatie {#use-profile-merge-rules}

Afhankelijk van uw gebruiksgeval (zie [1. Het bepalen van Uw Geval van het Gebruik ](people-based-destinations-workflow.md#defining-your-use-case)), zijn er twee manieren om [!DNL Profile Merge Rules] voor segmentatie te gebruiken.

**A) Bestaande gebruiken[!DNL Profile Merge Rules]**. Deze optie is van toepassing op het eerste gebruiksgeval (doelgroep gebaseerd op gecombineerde online- en offlinegebruikersactiviteiten). In dit scenario, hebt u bestaande klantenactiviteit in Audience Manager en u hebt reeds minstens één Regel van de Fusie van het Profiel bepaald die u in segmentatie hebt gebruikt. In dit geval hoeft u geen nieuwe [!DNL Profile Merge Rules] te maken.

**B) Maak een nieuwe regel voor  [!DNL All Cross-Device Profiles] samenvoegen**. Deze optie is van toepassing op het tweede gebruiksgeval (doelgroep die uitsluitend op offlinegebruikersactiviteit is gebaseerd). In dit scenario brengt u uw off-line klantengegevens van uw [!DNL CRM] in Audience Manager, en wilt tot segmenten van die gegevens leiden. Om dit te doen, [!DNL People-Based Destinations] introduceert een nieuwe, vierde Regel van de Fusie van het Profiel, genoemd **[!DNL All Cross-Device Profiles]**. Dit is de regel die u moet gebruiken wanneer het segmenteren van zuiver off-line gegevens.
