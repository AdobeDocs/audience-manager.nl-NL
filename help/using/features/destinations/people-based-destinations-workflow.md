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
source-wordcount: '1350'
ht-degree: 2%

---

# Implementatieleiding {#implementation-guidance}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

[!DNL People-Based Destinations] biedt meerdere implementatiestrategieën, afhankelijk van de structuur van uw klantgegevens. Dit artikel biedt een overzicht van de implementatiestappen die u moet volgen voor [!DNL People-Based Destinations] , afhankelijk van uw scenario.

## Overzicht {#overview}

De configuratie van [!DNL People-Based Destinations] doorloopt meerdere secties van Audience Manager en vereist verschillende instellingen en gegevens voor instapmethoden, afhankelijk van het type klantgegevens dat u al hebt in Audience Manager en het soort publiek dat u wilt inzetten.

>[!IMPORTANT]
> Lees dit artikel zorgvuldig en volledig voordat u [!DNL People-Based Destinations] configureert. Nadat u deze handleiding hebt gelezen, hebt u een duidelijk inzicht in het scenario dat u inschakelt via [!DNL People-Based Destinations] .

Er zijn zes implementatieaspecten die u moet verduidelijken voordat u [!DNL People-Based Destinations] gebruikt. Dit artikel zal u helpen begrijpen wat uw huidige configuratie is, zodat u de implementatiestappen voor uw scenario kunt correct volgen.

![&#x200B; pbd-implementatie &#x200B;](assets/pbd-implementation.png)

## &#x200B;1. Uw gebruikscase definiëren {#defining-your-use-case}

Voordat u begint met het implementeren van [!DNL People-Based Destinations] , moet u duidelijk definiëren voor welk gebruiksscenario u deze functie gaat gebruiken. U kunt [!DNL People-Based Destinations] gebruiken om doelgroepen op twee manieren te richten, op basis van publieksactiviteit:

**A) het doelpubliek dat op uw gecombineerde online en off-line gebruikersactiviteit** wordt gebaseerd. In dit scenario wilt u bestaande publieksgegevens van Audience Manager combineren met gegevens van uw interne [!DNL CRM] -systeem en de resulterende publiekssegmenten naar [!DNL People-Based Destinations] sturen. Hier is een voorbeeld dat dit scenario illustreert:

Uw bedrijf, een luchtvaartmaatschappij, heeft verschillende klantniveaus (Bronze, Silver, en Goud), en u wilt elk van de niveaus van gepersonaliseerde aanbiedingen via sociale platforms voorzien. U gebruikt Audience Manager om de klantactiviteiten op uw website te analyseren. Niet alle klanten gebruiken echter de mobiele app van de luchtvaartmaatschappij en sommige van hen hebben zich niet aangemeld bij de website van het bedrijf. Uw klantgegevens zijn meestal beperkt tot lidmaatschap-id&#39;s en e-mailadressen.

Om hen over sociale media en gelijkaardige op mensen-gebaseerde kanalen te richten, kunt u uw [&#x200B; gehakt e-mailadressen &#x200B;](people-based-destinations-prerequisites.md) brengen in Audience Manager en hen combineren met uw bestaande online activiteiteneigenschappen, om nieuwe publiekssegmenten te bouwen. Vervolgens kunt u deze segmenten gebruiken om uw doelgroep te kiezen via [!DNL People-Based Destinations] .

**B) het publiek dat zich richt uitsluitend op uw off-line gebruikersactiviteit** wordt gebaseerd. In dit scenario bevat uw [!DNL CRM] -systeem uw klanten-e-mailadressen en andere klantkenmerken, maar klanten hebben helemaal geen interactie met uw website gehad, zodat u in Audience Manager geen activiteiten van klanten hebt. Hier is een voorbeeld dat dit scenario illustreert:

Uw bedrijf, een aanbieder van telecommunicatiediensten, bewaart klantgegevens zoals e-mailadressen en aangekochte telecomplannen in een intern [!DNL CRM]. U wilt bestaande klanten op sociale platforms als doel hebben om hun upgradepakketten aan te bieden op basis van hun bestaande abonnementen. Hiervoor kunt u uw gehashte e-mailadressen van klanten opnemen in Audience Manager en segmenten maken op basis van de bestaande abonnementen van klanten. Vervolgens kunt u deze segmenten naar [!DNL People-Based Destinations] sturen om uw klanten te richten op persoonlijke aanbiedingen.

## &#x200B;2. Bepaal het type van gerichte e-mailadressen {#define-target-email}

De tweede stap bij het bepalen van uw implementatiestrategie bepaalt welk type van klant e-mailadressen u wilt richten.

**A) het richten van het publiek dat op uw voor authentiek verklaarde e-mailadressen** wordt gebaseerd. In dit scenario zijn er meerdere accounts gekoppeld aan meerdere e-mailadressen en wilt u deze richten op persoonlijke aanbiedingen die alleen zijn gebaseerd op het e-mailadres dat ze in real-time op uw website verifiëren.

**B) het richten van het publiek dat op elk van uw bijbehorende e-mailadressen** wordt gebaseerd. In dit scenario zijn er meerdere accounts gekoppeld aan meerdere e-mailadressen en wilt u deze richten op al hun gekoppelde e-mailadressen, ongeacht de geverifieerde activiteit.

## &#x200B;3. Identificeer het type van Klant IDs (CRM IDs) dat u hebt {#identify-customer-id}

Het richten publiek in [!DNL People-Based Destinations] vereist u om [&#x200B; SHA256 gehakt &#x200B;](people-based-destinations-prerequisites.md) versies van uw klanten e-mailadressen te verzenden. Afhankelijk van uw bestaande configuratie van Audience Manager, kunt u in één van de volgende twee scenario&#39;s vinden:

**A) Uw klant IDs van Audience Manager ([&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md)) is reeds in kleine letters, gehakt e-mailadressen**. In dit scenario kunt u deze bestaande id&#39;s gebruiken om uw publiek in [!DNL People-Based Destinations] als doel in te stellen.

**B) Uw klant IDs van Audience Manager ([&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md)) zijn niet kleine letters, gehakt e-mailadressen**. In dit scenario kunnen uw bestaande klant-id&#39;s niet worden verzonden naar [!DNL People-Based Destinations] . Als u [!DNL People-Based Destinations] wilt gebruiken, moet u een id-synchronisatie uitvoeren tussen uw bestaande klant-id&#39;s en kleine, gehashte versies van uw klanten-e-mailadressen. U doet dit of door [&#x200B; op dossier-gebaseerde synchronisatie van identiteitskaart &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) of door [&#x200B; gedeclareerde IDs &#x200B;](../declared-ids.md) te gebruiken.

## &#x200B;4. Kwalificatie van het goederenverkeer {#trait-qualification}

Om uw publiek in [!DNL People-Based Destinations] nauwkeurig te richten, moeten uw gebruikers voor of regel-gebaseerde of ongebogen eigenschappen in aanmerking komen, afhankelijk van het type van publiek dat richt dat u wilt uitvoeren.

**A) kwalificeer uw klant IDs en apparaat IDs in real time voor op regel-gebaseerde eigenschappen**. Deze optie is op geval A van [&#x200B; 1 van toepassing. Het bepalen van Uw Hoofdlettergebruik &#x200B;](people-based-destinations-workflow.md#defining-your-use-case). Als uw plan publiek moet richten dat op online en off-line activiteit wordt gebaseerd, dan zult u zeer waarschijnlijk reeds uw publiek voor [&#x200B; op regel-gebaseerde trekken &#x200B;](../traits/trait-and-segment-qualification-reference.md) kwalificeren.

**B) De sporen aan boord tegen uw klant IDs via binnenkomende gegevensdossiers**. Deze optie is op geval B van [&#x200B; 1 van toepassing. Het bepalen van Uw Hoofdlettergebruik &#x200B;](people-based-destinations-workflow.md#defining-your-use-case). Wanneer het richten van uw publiek dat op puur off-line activiteit wordt gebaseerd, moet u klant IDs voor aan boord genomen trekken door [&#x200B; binnenkomende gegevensdossiers &#x200B;](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) kwalificeren.

## &#x200B;5. Maak of label gegevensbronnen en e-mailadressen aan boord met hashing {#create-label-data-sources}

Afhankelijk van het type van klant IDs dat u in Audience Manager hebt (zie [&#x200B; . Identificeer het Type van identiteitskaart van de Klant (CRM IDs) dat u &#x200B;](people-based-destinations-workflow.md#identify-customer-id) hebt, zult u in één van de volgende scenario&#39;s vinden:

**A) Etiket een bestaande gegevensbron**. Deze optie is op het scenario van toepassing waar uw klant IDs van Audience Manager ([&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md)) reeds in kleine letters, gehakt e-mailadressen zijn. In dit geval moet u een label toewijzen aan de gegevensbron waarin u de id&#39;s opslaat als een [!DNL PII] -gegevensbron. Zie {de Montages van Source van 0} Gegevens [&#x200B; voor details op de gegevensbronmontages. &#x200B;](../datasources-list-and-settings.md) U moet ervoor zorgen dat de optie Kan niet worden gekoppeld aan persoonlijk identificeerbare gegevens is uitgeschakeld.

**B) creeer een nieuwe gegevensbron**. Deze optie is op het scenario van toepassing waar uw klant IDs van Audience Manager ([&#x200B; DPUUIDs &#x200B;](../../reference/ids-in-aam.md)) geen gehashte e-mailadressen zijn. In dit geval moet u een nieuwe gegevensbron voor alle apparaten maken en de gehashte e-mailadressen aan boord van deze gegevensbron plaatsen. U kunt dit op twee manieren doen:

* Gebruik op bestanden gebaseerde id-synchronisatie. Zie [Naam- en contentvereisten voor id-synchronisatiebestanden](../../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) voor details over hoe id-synchronisatiebestanden eruit moeten zien. Wanneer u deze methode gebruikt, kunt u zich richten op al uw gehashte e-mailadressen vanuit uw [!DNL CRM] -database.
* Het gebruik [&#x200B; verklaarde IDs &#x200B;](../declared-ids.md) om uw gehakt e-mailadressen te verklaren wanneer het overgaan in voor authentiek verklaarde klant IDs. Als u deze methode gebruikt, richt Audience Manager zich namens u alleen op uw gehashte e-mailadressen van gebruikers die online zijn geverifieerd. De e-mailadressen die in op mensen-gebaseerde kanalen worden gericht zijn slechts degenen in de verklaarde de gebeurtenisvraag van identiteitskaart Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in real time geactiveerd.

## &#x200B;6. Een regel voor het samenvoegen van profielen gebruiken voor segmentatie {#use-profile-merge-rules}

Afhankelijk van uw gebruiksgeval (zie [&#x200B; 1. Het bepalen van Uw Geval van het Gebruik &#x200B;](people-based-destinations-workflow.md#defining-your-use-case)), zijn er twee manieren om [!DNL Profile Merge Rules] voor segmentatie te gebruiken.

**A) Gebruik bestaand[!DNL Profile Merge Rules]**. Deze optie is van toepassing op het eerste gebruiksgeval (doelgroep gebaseerd op gecombineerde online- en offlinegebruikersactiviteiten). In dit scenario, hebt u bestaande klantenactiviteit in Audience Manager en u hebt reeds minstens één Regel van de Fusie van het Profiel bepaald die u in segmentatie hebt gebruikt. In dit geval hoeft u geen nieuwe [!DNL Profile Merge Rules] te maken.

**B) creeer een nieuwe, [!DNL All Cross-Device Profiles] Regel van de Fusie**. Deze optie is van toepassing op het tweede gebruiksgeval (doelgroep die uitsluitend op offlinegebruikersactiviteit is gebaseerd). In dit scenario brengt u uw offline klantgegevens van uw [!DNL CRM] naar Audience Manager en wilt u segmenten maken van die gegevens. Hiertoe introduceert [!DNL People-Based Destinations] een nieuwe, vierde regel voor het samenvoegen van profielen, genaamd **[!DNL All Cross-Device Profiles]** . Dit is de regel die u moet gebruiken wanneer het segmenteren van zuiver off-line gegevens.
