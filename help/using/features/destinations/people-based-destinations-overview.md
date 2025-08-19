---
description: Gebruik op mensen gebaseerde bestemmingen om de segmenten van het eerste-partijpubliek naar op mensen-gebaseerde milieu's te verzenden. Deze omgevingen zijn gesloten ecosystemen die behoren tot één entiteit die de inhoud beheert die erin wordt weergegeven. Hieronder vallen sociale platforms zoals Facebook en andere platforms die afhankelijk zijn van klantenaccounts om de weergegeven inhoud aan te passen.
seo-description: Use people-based destinations to send first-party audience segments to people-based environments. These environments are closed ecosystems belonging to one entity that controls the content that is being displayed within it. They include social platforms such as Facebook, and other platforms that rely on customer accounts to personalize the displayed content.
seo-title: People-Based Destinations Overview and Use Cases
solution: Audience Manager
title: Gevallen voor overzicht en gebruik
feature: People-based Destinations
exl-id: 2edbda3b-e2a3-4a92-965b-206a21764cc8
source-git-commit: ab3361a0a54a7200d2f0c03a82ae6ef61a755be9
workflow-type: tm+mt
source-wordcount: '865'
ht-degree: 0%

---

# Gevallen voor overzicht en gebruik {#overview-use-cases}

Gebruik [!DNL People-Based Destinations] om doelsegmenten van de eerste partij naar op mensen gebaseerde omgevingen te verzenden. Deze omgevingen zijn gesloten ecosystemen die behoren tot één entiteit die de inhoud beheert die erin wordt weergegeven. Hieronder vallen sociale platforms zoals [!DNL Facebook] en andere platforms die afhankelijk zijn van klantenaccounts om de weergegeven inhoud aan te passen.

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

## Overzicht {#overview}

[!DNL People-Based Destinations] laat u toe om segmentatie op online en off-line gegevens toe te passen om publiekssegmenten tot stand te brengen die op [ worden gebaseerd gehakt herkenningstekens ](people-based-destinations-prerequisites.md#hashing-requirements), zoals e-mailadressen. Vervolgens kunt u deze segmenten naar zogenaamde tuinen [!DNL Facebook] sturen, waar u uw doelgroep kunt richten op de sociale platforms. [!DNL People-Based Destinations] kan u helpen:

* Offline en online doelpubliek richten op platforms zoals [!DNL Facebook] , op basis van gehashte e-mailadressen;
* bestaande Audience Manager-functionaliteit voor apparaat- en cookiedoelen aanvullen;
* kosten wegnemen die verband houden met gegevens van derden over instapoplossingen;
* Elimineer kosten verbonden aan het ontwikkelen van douanegegevens op instapwerkschema&#39;s;
* doelpubliek in omgevingen zonder cookie;
* Doelpubliek door gehashte e-mailadressen te dedupliceren die overeenkomen met klant-id&#39;s.

Met [!DNL People-Based Destinations] kunt u klanten met een hoge waarde segmenteren en als doel instellen die uw website mogelijk niet bezoeken, of u kunt niet langer doelgroepen maken voor klanten die al offline zijn geconverteerd. Bovendien kunt u [!DNL Profile Merge Rules] gebruiken om uw offline gegevens van de eerste partij te combineren met uw online gegevens van de eerste partij, waaronder klantgegevens van andere Adobe Experience Cloud-oplossingen, om uw advertentieinspanningen voor sociale media te optimaliseren.

![ pbd-overzicht ](assets/pbd-overview.png)

## Beschikbaarheid {#availability}

[!DNL People-Based Destinations] is een eersteklas Audience Manager-integratie. Neem contact op met uw Adobe-vertegenwoordiger om gebruik te maken van deze premiumfunctie.

## Waarom moet u [!UICONTROL People-Based Destinations] gebruiken? {#why-use}

**verstrek uw klanten verenigbare dwars-kanaalervaringen door uw volledige publiekssegmentatie van binnen Audience Manager te beheren.**

Als u uw publiekssegmenten niet via Audience Manager in op mensen gebaseerde kanalen activeert, ontstaat een onsamenhangende ervaring tussen wat uw klanten zien wanneer ze uw website bezoeken en wat ze bijvoorbeeld in hun [!DNL Facebook] -feeds zien. Als u een consistente keuze hebt gemaakt tussen verschillende kanalen, kunt u uw advertentie-inkomsten verhogen en uw advertentiepatronen optimaliseren.

**Bereik publiek in op mensen-gebaseerde kanalen zonder de behoefte van specifieke gegevens op het instappen van oplossing of douanewerkschema&#39;s om publiek te verzenden.**

De meer &quot;traditionele&quot;manier om publiek over op mensen-gebaseerde kanalen te richten impliceert u het moeten uw klantengegevens in een formaat uitvoeren dat door het platform wordt goedgekeurd dat u wilt adverteren, en dan het gebruiken van de specifieke gegevens van het platform op instapmethode om uw klantengegevens aan uw adverteerderrekening te brengen. Dit is al handwerk dat u moet doen voor elk platform waarop u wilt adverteren. Bovendien kunnen verschillende platforms verschillende gegevensindelingsvereisten hebben, waardoor het proces nog vervelender wordt.

![ pbd-overzicht ](assets/pbd-diagram.png)

Via [!DNL People-Based Destinations] helpt Audience Manager u uw klantgegevens te centraliseren, publiekssegmenten te maken en deze via meerdere op personen gebaseerde kanalen te activeren. U kunt dit alles vanuit de gebruikersinterface van Audience Manager doen, zodat u geen extra werkzaamheden hoeft uit te voeren om handmatig gegevens naar elk platform te uploaden en kostbare tijd bespaart in het proces.

**creeer en activeer publiekssegmenten van zuiver off-line profielen.**

[!DNL People-Based Destinations] lost het probleem op dat u eerder alleen publiekssegmenten kon activeren op basis van apparaatactiviteiten. Met [!DNL People-Based Destinations] kunt u segmenten maken op basis van zuiver offline gegevens uit uw eigen [!DNL CRM] en deze activeren op platformen voor mensen. Bovendien kunt u uw offlinegegevens correleren met apparaatgegevens die al in Audience Manager beschikbaar zijn.

**de gegevensbeheer en privacycontroles van Audience Manager van de hefboomwerking om klantengegevens veilig te behandelen.**

[!DNL People-Based Destinations] vereist dat u alleen onomkeerbare gehashte id&#39;s gebruikt. Dit vermindert het risico verbonden aan manueel het uploaden van klantengegevens in elk bestemmingsplatform.

Bekijk de onderstaande video voor een overzicht van de gegevensstroom bij gebruik van [!UICONTROL People-Based Destinations] .

>[!VIDEO](https://video.tv.adobe.com/v/28968/)

## Gevallen gebruiken {#use-cases}

Voor een beter begrip van het gebruik van [!DNL People-Based Destinations] zijn er twee voorbeelden van gebruiksproblemen die Audience Manager-klanten met deze functie kunnen oplossen.

### Hoofdletters en kleine letters gebruiken 1 {#use-case-1}

Een online retailer wil bestaande klanten bereiken via sociale platforms en hun persoonlijke aanbiedingen laten zien op basis van hun eerdere bestellingen. Met [!DNL People-Based Destinations] kan de online retailer hashed-e-mailadressen innemen van hun eigen [!DNL CRM] naar Audience Manager, segmenten van hun eigen offlinegegevens maken en deze segmenten naar de sociale platforms sturen waar ze op willen adverteren, zodat hun advertentie-uitgaven worden geoptimaliseerd.

### Hoofdletters en kleine letters gebruiken 2 {#use-case-2}

Een luchtvaartmaatschappij heeft verschillende klantniveaus (Bronze, Silver en Gold) en wil elk niveau via sociale platforms voorzien van persoonlijke aanbiedingen. Het bedrijf gebruikt Audience Manager om klantactiviteiten op de website te analyseren. Niet alle klanten gebruiken echter de mobiele app van de luchtvaartmaatschappij en sommige van hen hebben zich niet aangemeld bij de website van het bedrijf. De enige id&#39;s die het bedrijf over deze klanten heeft, zijn id&#39;s voor lidmaatschap en e-mailadressen.

Als ze zich op sociale media en vergelijkbare, op mensen gebaseerde kanalen willen richten, kunnen ze de klantgegevens van hun [!DNL CRM] naar Audience Manager opnemen, waarbij ze de gehashte e-mailadressen als id&#39;s gebruiken.

Vervolgens kunnen ze hun offlinegegevens combineren met hun bestaande online activiteitskenmerken om nieuwe publiekssegmenten te maken die ze kunnen gebruiken via [!DNL People-Based Destinations] .
