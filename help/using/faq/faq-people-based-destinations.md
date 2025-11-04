---
description: Antwoorden op veelgestelde vragen over persoonsgebaseerde bestemmingen.
seo-description: Answers to common questions about People-Based Destinations.
seo-title: People-Based Destinations FAQ
solution: Audience Manager
title: Veelgestelde vragen over persoonsgebaseerde bestemmingen
feature: People-based Destinations
exl-id: 56506bf0-45f1-49df-81ac-10f57a2487eb
source-git-commit: fc26861e4a53abc57f8814abf823a51894fb6147
workflow-type: tm+mt
source-wordcount: '1161'
ht-degree: 85%

---

# Veelgestelde vragen over persoonsgebaseerde bestemmingen {#people-based-destinations-faq}

Antwoorden op algemene vragen over [!DNL People-Based Destinations].

## Beschikbaarheid {#availability}

**Ik kan [!DNL People-Based Destinations] niet zien in mijn Audience Manager-account. Wat moet ik weten over beschikbaarheid?**

[!DNL People-Based Destinations] is een premiumfunctie van Audience Manager die bij aankoop beschikbaar is. Neem contact op met uw Adobe-verkoopvertegenwoordiger voor meer informatie over prijzen en beschikbaarheid.

## Gegevens aan boord {#data-onboarding}

**Hoe kan ik e-mailadressen van klanten onboarden in Audience Manager, zodat ik deze in [!DNL People-Based Destinations] kan gebruiken?**

Er zijn twee manieren waarop u offline data in Audience Manager kunt opnemen voor [!DNL People-Based Destinations].

* **Gebruik op bestand-id gebaseerde synchronisatie**. Zie [Naam- en contentvereisten voor id-synchronisatiebestanden](../integration/sending-audience-data/batch-data-transfer-explained/id-sync-file-based.md) voor details over hoe id-synchronisatiebestanden eruit moeten zien. Wanneer u deze methode gebruikt, kunt u alle gehashte e-mailadressen vanuit uw [!DNL CRM]-database targeten.
* **Gebruik gedeclareerde id’s** om gehashte e-mailadressen te declareren wanneer u geverifieerde klant-id’s doorgeeft. Als u deze methode gebruikt, activeert Audience Manager alleen de gehashte e-mailadressen van gebruikers die online zijn geverifieerd. De e-mailadressen die via Facebook worden geactiveerd, zijn alleen de adressen in gedeclareerde id-gebeurteniscalls. Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in real time geactiveerd.

**Kan ik gehashte e-mailadressen verzamelen via een webformulier of mobiele app, of moeten ze doorkomen via een batchbestand?**

U kunt gehashte e-mailadressen via webverificatie verzamelen met behulp van [!DNL ECID] met [gedeclareerde id’s](../features/declared-ids.md). Het partijdossier staat u toe om gehakt e-mailadressen ook te verzamelen die niet door authentificatie (b.v. slapende gebruikers in uw ([!DNL CRM]) kunnen worden verzonden en hen in op mensen-gebaseerde bestemmingen activeren.

**Hoe is het opnemen van gehashte e-mailadressen via webformulieren anders dan het uploaden van gehashte e-mailadressen via batchbestanden?**

Offline dataopname is ontworpen ter ondersteuning van gebruiksscenario’s zonder verificatie, en er is een nieuwe regel voor profielsamenvoeging ([!UICONTROL All Cross-Device Profiles]) beschikbaar als onderdeel van [!DNL People-Based Destinations] die wordt uitgevoerd op alle offline [!DNL CRM]-profielen, ongeacht verificatie. Deze methode is bedoeld als aanvulling op de opname van geverifieerde doelgroepen via online bronnen.

**Wat is de maximale frequentie voor het verzenden/bijwerken van gehashte e-mailadressen?**

* Bij het gebruik van gedeclareerde id’s verzendt Audience Manager de gehashte e-mailadressen in real time naar de bestemming.
* Bij het opnemen van data via id-synchronisatiebestanden verwerkt Audience Manager deze op dagelijkse basis.

**Hoe weet ik of het hashing van e-mailadressen correct is uitgevoerd?**

Audience Manager neemt het onbewerkte e-mailadres niet op en we kunnen niet controleren of de hash correct is uitgevoerd. Zie [Vereisten en overwegingen](../features/destinations/people-based-destinations-prerequisites.md) voor details over hoe u de onboarded data kunt hashen.

## Regels voor profielsamenvoeging {#profile-merge-rules}

**Is er een nieuwe regel voor profielsamenvoeging die ik met [!DNL People-Based Destinations] kan gebruiken?**

Ja. Klanten die [!DNL People-Based Destinations] kopen, krijgen ook toegang tot een nieuwe regel voor profielsamenvoeging voor offline segmentatie. De regel heet [!DNL All Cross-Device Profiles] en wordt uitsluitend gebruikt voor offline segmentatie. Wanneer u zich aanmeldt voor [!DNL People-Based Destinations], is dit de vierde regel voor profielsamenvoeging die u kunt maken, afgezien van de drie bestaande op verificatie gebaseerde regels.

**Moet ik mijn bestaande doelgroepsegmenten dupliceren om ze te activeren in [!DNL People-Based Destinations]?**

Dat hangt van uw gebruiksscenario af. Als u van plan bent bestaande eigen segmenten te activeren in persoonsgebaseerde kanalen, hoeft u geen nieuwe segmenten te maken. U kunt de segmenten gewoon toewijzen aan een persoonsgebaseerde bestemming.

Als u van plan bent nieuwe offline doelgroepen te activeren in persoonsgebaseerde kanalen, moet u nieuwe eigen segmenten maken met de [!DNL All Cross-Device Profiles]-samenvoegingsregel.

>[!NOTE]
>
> U kunt segmenten met eigen data alleen toewijzen aan [!DNL People-Based Destinations]. Onze bestemmingsplatforms accepteren geen segmenten met data van tweede en derde partijen.

## Gelijke tarieven {#match-rates}

**Hebben [!DNL People-Based Destinations] zicht op matchpercentages of adresseerbare doelgroepen?**

Nee. Bij het verzenden van doelgroepsegmenten naar [!DNL People-Based Destinations] vindt doelgroepmatching plaats aan de kant van de partner. Adobe heeft geen toegang tot deze cijfers. Audience Manager toont u de maximaal deelbare doelgroep voor elke bestemming en het realtime-aantal personen dat tot een segment behoort. Deze informatie kan u helpen bij campagneplanning en voorspellingen.

**Hoe zijn matchpercentages die gebruikmaken van [!DNL People-Based Destinations], theoretisch te vergelijken met andere methodes om doelgroepen naar bestemmingsplatforms te verzenden?**

Zolang het e-mailadres correct wordt gehasht en opgenomen, zou er geen verschil in matchpercentage moeten zijn tussen [!DNL People-Based Destinations] en andere methodes. De enige reden dat een overeenkomende snelheid lager is dan 100% is dat de e-mailadressen die naar Audience Manager worden verzonden niet overeenkomen met een e-mailadres in de gebruikerslijst van het doelplatform.

**Ik verzamel werk-e-mailadressen van mijn klanten, die anders zijn dan de persoonlijke e-mailadressen die in sociale netwerken worden gebruikt. Hoe kunt u identiteiten matchen met meerdere e-mailadressen?**

Audience Manager kan per gebruiker maximaal 10 e-mails verzamelen en naar bestemmingsplatforms verzenden, maar de e-mailadressen moeten via synchronisatiebestanden worden vastgelegd. Nadat Audience Manager de e-mailadressen naar bestemmingsplatforms heeft verzonden, is het aan de platforms om de e-mailadressen te matchen met hun eigen gebruikersbase. Sommige platforms hebben mogelijk extra e-mailadresgrafieken om adressen te matchen die vanuit Audience Manager naar gebruikersprofielen worden verzonden.

**Kan ik [!DNL People-Based Destinations] in [!DNL Audience Lab] gebruiken?**

Nee. Momenteel zijn alle [!DNL People-Based Destinations] -doelen uitgesloten van [!DNL Audience Lab] . Aangezien [!DNL People-Based Destinations] en vraagzijdeplatforms verschillende id&#39;s gebruiken, kunt u de prestaties niet testen en meten met een publiek dat er gelijkmatig over verdeeld is.

## Besturingselementen voor gegevensexport {#data-export-controls}

**Hoe werken [!DNL Data Export Controls] met [!DNL People-Based Destinations]?**

[!DNL Data Export Controls] blokkeert alle segmenten met data van tweede en derde partijen die gebruikers proberen naar [!DNL People-Based Destinations] te verzenden. Met [!DNL People-Based Destinations] is alleen het gebruik van eigen data voor targeting toegestaan. [!DNL Data Export Controls] blokkeert ook segmenten die gebruikmaken van [!DNL Profile Merge Rules] met apparaatgrafieken. [!DNL People-Based Destinations] worden gemaakt met de juiste data-exportlabels ingeschakeld, en u kunt de exportinstellingen niet overschrijven.

## Specifieke vragen voor partners {#partner-specific-questions}

### [!DNL Facebook]

**Wat moet ik doen voordat ik doelgroepsegmenten naar [!DNL Facebook] kan sturen?**

Voordat u [!DNL People-Based Destinations] kunt gebruiken om doelgroepsegmenten naar [!DNL Facebook] te sturen, moet u de volgende configuratietaken uitvoeren:

1. Voeg het Adobe Experience Cloud-bedrijfsaccount als een advertentiepartner toe in uw [!DNL Facebook Ad Account]. Gebruik `business ID=206617933627973`. Zie Partners aan uw bedrijfsbeheer toevoegen voor meer informatie.

   >[!IMPORTANT]
   >
   > Wanneer u de toestemmingen voor Adobe Experience Cloud configureert, moet u de toestemming voor Campagnes beheren inschakelen. Dit is nodig voor de [!DNL People-Based Destinations]-integratie.

1. Lees en onderteken de [!DNL Facebook Custom Audiences Terms of Service]. Ga daarvoor naar `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, waarbij `accountID` uw [!DNL Facebook Ad Account ID] is.

**Ondersteunt [!DNL People-Based Destinations] doelgroeptargeting in andere [!DNL Facebook]-apps zoals [!DNL Instagram]?**

U kunt [!DNL People-Based Destinations] gebruiken voor alle [!DNL Facebook] -apps die worden ondersteund door [!DNL Custom Audiences] , zoals [!DNL Facebook] , [!DNL Instagram] , [!DNL Audience Network] en [!DNL Messenger] . De selectie van de app waarin u de campagne wilt voeren, wordt aangegeven op het plaatsingsniveau in [!DNL Facebook Ads Manager].

**wat is het verschil tussen [!DNL People-Based Destinations] en [!DNL Website Custom Audiences]?**

[!DNL People-Based Destinations] maakt gebruik van de [!DNL Custom Audiences (CA)]-integratie met [!DNL Facebook]. Het verschil tussen [!DNL WCA]- en [!DNL CA]-integratie is de sleutel die de klanten gebruiken bij het verzenden van doelgroepen naar [!DNL Facebook]. [!DNL WCA] gebruikt de [!DNL Facebook]-pixel (een websitegebruikers-id) terwijl [!DNL People-Based Destinations] gehashte e-mailadressen gebruikt voor integratie met [!DNL CA].

U kunt zonder extra kosten de Audience Manager [!DNL Facebook] [!DNL WCA] -integratie gebruiken via de [!DNL URL Destinations] -functie.

Deze twee integraties zijn complementair; u kunt beide gebruiken om te zorgen voor een betere doelgroepdekking. Een voorbeeld: [!DNL WCA] kan worden gebruikt voor prospectie wanneer een bedrijf websitebezoekers wil targeten die geen account hebben geregistreerd, terwijl [!DNL People-Based Destinations] u kan helpen bestaande klanten te targeten die hun e-mailadres hebben opgegeven, maar de website misschien niet hebben bezocht.

**steunt de [!DNL People-Based Destinations] integratie met [!DNL Facebook] het ontkwalificeren van een gebruikers van een publiek wanneer zij niet meer voor het kwalificeren?**

Ja, de integratie ondersteunt het verwijderen van gebruikers uit het publiek van [!DNL Facebook] wanneer ze niet langer voor hen in aanmerking komen.
