---
description: 'Antwoorden op gemeenschappelijke vragen over op mensen-Gebaseerde Doelen.  '
seo-description: 'Antwoorden op gemeenschappelijke vragen over op mensen-Gebaseerde Doelen.  '
seo-title: Veelgestelde vragen over op mensen gebaseerde doelen
solution: Audience Manager
title: Veelgestelde vragen over op mensen gebaseerde doelen
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '1105'
ht-degree: 0%

---


# Veelgestelde vragen over op mensen gebaseerde doelen {#people-based-destinations-faq}

Antwoorden op algemene vragen over [!DNL People-Based Destinations].

## Beschikbaarheid {#availability}

**Ik zie[!DNL People-Based Destinations]mijn Audience Manager niet. Wat moet ik weten over beschikbaarheid?**

[!DNL People-Based Destinations] is een premiumfunctie voor Audience Managers die bij aankoop beschikbaar is. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie over prijzen en beschikbaarheid.

## Gegevens aan boord {#data-onboarding}

**Hoe kan ik de e-mailadressen van de klant in Audience Manager, zodat ik hen binnen kan gebruiken[!DNL People-Based Destinations]?**

Er zijn twee manieren u uw off-line gegevens aan Audience Manager voor kunt brengen [!DNL People-Based Destinations].

* **Synchronisatie** van op een bestand gebaseerde id gebruiken. Zie [Naam en Inhoudsvereisten voor ID-synchronisatiebestanden](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) voor meer informatie over hoe de id-synchronisatiebestanden eruit moeten zien. Wanneer u deze methode gebruikt, kunt u alle gehashte e-mailadressen vanuit uw [!DNL CRM] database als doel instellen.
* **Gebruik gedeclareerde id&#39;s** om gehashte e-mailadressen te declareren wanneer u geautoriseerde klant-id&#39;s doorgeeft. Als u deze methode gebruikt, activeert Audience Manager alleen de gehashte e-mailadressen van gebruikers die online zijn geverifieerd. De e-mailadressen die via Facebook worden geactiveerd, zijn alleen de adressen in de oproepen voor gedeclareerde id-gebeurtenissen. Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in realtime geactiveerd.

**Kan ik gehashte e-mailadressen verzamelen via een webformulier of mobiele app of moeten ze doorlopen in een batchbestand?**

U kunt gehashte e-mailadressen via webverificatie verzamelen met behulp [!DNL ECID] van [gedeclareerde id&#39;s](../features/declared-ids.md). Met het batchbestand kunt u ook gehashte e-mailadressen verzamelen die niet via verificatie kunnen worden verzonden (bijvoorbeeld slapende gebruikers in uw ([!DNL CRM])) en deze activeren in op personen gebaseerde doelen.

**Hoe wordt het invoeren van gehashte e-mailadressen via webformulieren anders dan het uploaden van gehashte e-mailadressen via batchbestanden?**

Offlinegegevensinvoer is ontworpen ter ondersteuning van gebruiksgevallen zonder verificatie en een nieuwe regel voor het samenvoegen van profielen ([!UICONTROL All Cross-Device Profiles]) die wordt uitgevoerd op alle offline [!DNL CRM] profielen, ongeacht de verificatie, is beschikbaar als onderdeel van [!DNL People-Based Destinations]. Deze methode is bedoeld als aanvulling op de inname van geverifieerde doelgroepen via onlinebronnen.

**Wat is de maximumfrequentie waarmee ik gehashte e-mailadressen kan verzenden/bijwerken?**

* Wanneer het gebruiken van Verklaarde IDs, verzendt de Audience Manager de gehakte e-mailadressen naar de bestemming in echt - tijd.
* Wanneer het opnemen van gegevens door de dossiers van de synchronisatie van identiteitskaart, verwerkt de Audience Manager hen op een dagelijkse basis.

**Hoe weet ik of het hashing van het e-mailadres correct wordt gedaan?**

Audience Manager neemt het onbewerkte e-mailadres niet op en we kunnen niet controleren of de hash correct is uitgevoerd. Zie [Vereisten en Overwegingen](../features/destinations/people-based-destinations-prerequisites.md) voor details over hoe u de ingekapselde gegevens zou moeten hakken.

## Regels voor samenvoegen van profielen {#profile-merge-rules}

**Is er een nieuwe regel van de profielfusie die ik met kan gebruiken[!DNL People-Based Destinations]?**

Ja. Klanten die aankopen [!DNL People-Based Destinations] krijgen ook toegang tot een nieuwe regel voor het samenvoegen van profielen voor offline segmentatie. De regel wordt geroepen [!DNL All Cross-Device Profiles] en het wordt gebruikt voor offline-slechts segmentatie. Wanneer u omhoog voor [!DNL People-Based Destinations], dit de vierde regel van de profielfusie bent die u, naast de drie bestaande op authentificatie-gebaseerde regels kunt tot stand brengen.

**Moet ik mijn bestaande publiekssegmenten dupliceren om ze in te activeren[!DNL People-Based Destinations]?**

Het hangt van uw gebruikscase af. Als u op het activeren van bestaande eerste-partijsegmenten in op mensen-gebaseerde kanalen van plan bent, te hoeven u om geen nieuwe segmenten tot stand te brengen. U kunt de segmenten alleen toewijzen aan een op mensen gebaseerd doel.

Als u op het activeren van nieuwe off-line publiek in op mensen-gebaseerde kanalen van plan bent, moet u nieuwe eerste-partijsegmenten tot stand brengen gebruikend de [!DNL All Cross-Device Profiles] fusieregel.
>[!NOTE]
>
> U kunt segmenten met gegevens van de eerste partij slechts in kaart brengen aan [!DNL People-Based Destinations]. Onze doelplatforms accepteren geen segmenten met gegevens van derden.

## Gelijke tarieven {#match-rates}

**Heb[!DNL People-Based Destinations]zicht in gelijke tarieven of adresseerbare publiek?**

Nee. Wanneer het verzenden van publiekssegmenten naar [!DNL People-Based Destinations], publieksaanpassing gebeurt aan de partnerkant. Adobe heeft geen toegang tot deze gegevens. De Audience Manager toont u het maximum deelbare publiek voor elke bestemming en het aantal in real time van mensen die tot een segment behoren. Deze informatie kan u met campagneplanning en het voorspellen helpen.

**Hoe zouden de tarieven die[!DNL People-Based Destinations]theoretisch vergelijken met andere methodes om publiek naar bestemmingsplatforms te verzenden?**

Zolang het e-mailadres wordt gehasht en correct wordt opgenomen, zou er geen verschil in het gelijke tarief tussen [!DNL People-Based Destinations] en andere methodes moeten zijn. De enige reden een gelijke tarief onder 100% zou zijn is als de e-mailadressen die in Audience Manager worden gebracht niet met een e-mailadres in het de gebruikersbasis van het bestemmingsplatform kunnen worden aangepast.

**Ik verzamel werk-e-mailadressen van mijn klanten, die van de persoonlijke e-mailadressen verschillend zijn die in sociale netwerken worden gebruikt. Hoe kunt u identiteiten over veelvoudige e-mailadressen aanpassen?**

Audience Managers kunnen per gebruiker maximaal 10 e-mails verzamelen en verzenden naar doelplatforms, maar de e-mailadressen moeten via synchronisatiebestanden worden vastgelegd. Nadat de Audience Manager de e-mailadressen naar bestemmingsplatforms verzendt, is het aan de platforms om de e-mailadressen aan hun eigen gebruikersbasis aan te passen. Sommige platforms hebben mogelijk extra e-mailadresgrafieken die overeenkomen met adressen die van Audience Manager naar gebruikersprofielen worden verzonden.

## Besturingselementen voor gegevensexport {#data-export-controls}

**Hoe[!DNL Data Export Controls]werkt u met[!DNL People-Based Destinations]?**

[!DNL Data Export Controls] zullen om het even welke segmenten blokkeren die tweede en derdegegevens bevatten die de gebruikers proberen te verzenden naar [!DNL People-Based Destinations]. [!DNL People-Based Destinations] staan alleen toe dat gegevens van de eerste partij voor het richten worden gebruikt. [!DNL Data Export Controls] bloksegmenten die ook worden gebruikt [!DNL Profile Merge Rules] met apparaatgrafieken. [!DNL People-Based Destinations] worden gemaakt met de juiste exportlabels voor gegevens ingeschakeld en u kunt de exportinstellingen niet overschrijven.

## Specifieke vragen voor partners {#partner-specific-questions}

### [!DNL Facebook]

**Wat moet ik doen voordat ik publiekssegmenten naar kan sturen[!DNL Facebook]?**

Alvorens u kunt gebruiken [!DNL People-Based Destinations] [!DNL Facebook]om publiekssegmenten naar te verzenden, moet u de volgende configuratietaken uitvoeren:

1. Voeg het Adobe Experience Cloud-bedrijfsaccount toe als een advertentiepartner in uw [!DNL Facebook Ad Account]account. Gebruik `business ID=206617933627973`. Zie Partners aan Uw BedrijfsManager voor details toevoegen.

   >[!IMPORTANT]
   >
   > Wanneer u de machtigingen voor Adobe Experience Cloud configureert, moet u de machtiging Campagnes beheren inschakelen. Dit is nodig voor de [!DNL People-Based Destinations] integratie.

1. Lees en onderteken de [!DNL Facebook Custom Audiences Terms of Service]handleiding. Om dit te doen, ga naar `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, waar `accountID` is je [!DNL Facebook Ad Account ID].

**Biedt[!DNL People-Based Destinations]ondersteuning voor doelgroepen in andere[!DNL Facebook]apps, zoals[!DNL Instagram]?**

U kunt toepassingen gebruiken [!DNL People-Based Destinations] uit [!DNL Facebook]de verschillende families die worden ondersteund door [!DNL Custom Audiences], inclusief [!DNL Facebook], [!DNL Instagram][!DNL Audience Network] en [!DNL Messenger]. De selectie van de app waarop u de campagne wilt uitvoeren, wordt aangegeven op het plaatsingsniveau in [!DNL Facebook Ads Manager].

**Wat is het verschil tussen[!DNL People-Based Destinations]en[!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] hefboomwerkingen de [!DNL Custom Audiences (CA)] integratie met [!DNL Facebook]. Het verschil tussen [!DNL WCA] en [!DNL CA] integratie is de sleutel die de klanten gebruiken wanneer het verzenden van publiek naar [!DNL Facebook]. [!DNL WCA] gebruikt de [!DNL Facebook] pixel (die een identiteitskaart van de websitegebruiker zou zijn) terwijl [!DNL People-Based Destinations] gebruik gehakt e-mailadressen om met te integreren [!DNL CA].

U kunt de [!DNL Facebook] integratie van de Audience Manager zonder extra kosten gebruiken via de [!DNL WCA] [!DNL URL Destinations] functie.

Deze twee integraties zijn complementair; u kunt beide gebruiken om een betere publieksdekking te verzekeren. Een voorbeeld: [!DNL WCA] kan worden gebruikt voor prospectie wanneer een bedrijf websitebezoekers wil bereiken die geen account hebben geregistreerd, terwijl [!DNL People-Based Destinations] u bestaande klanten die hun e-mailadres hebben opgegeven maar de website misschien niet hebben bezocht, kunt helpen.
