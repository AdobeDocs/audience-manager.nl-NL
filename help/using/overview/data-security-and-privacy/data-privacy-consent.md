---
description: In dit document wordt uitgelegd hoe beheer van machtigingen werkt in Audience Manager.
seo-description: In dit document wordt uitgelegd hoe beheer van machtigingen werkt in Audience Manager.
seo-title: Beheer van toestemming
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Beheer van toestemming
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
translation-type: tm+mt
source-git-commit: 9004dc46c0ac431e9f193467a2147a2d9ac36cdc

---


# Beheer van toestemming

## Overzicht {#overview}

In gevallen waarin toestemming voor bepaalde marketingactiviteiten nodig is, moeten klanten van Audience Manager het bereik en de vraag bepalen of bepaalde toestemmingen moeten worden vernieuwd om door te kunnen gaan met het gebruik van gegevens.

De Manager van de Publiek biedt u hulpmiddelen helpen uw capaciteit steunen om de vereiste toestemmingen van uw gebruikers te verkrijgen, zodat u gepersonaliseerde ervaringen aan hen over kanalen kunt leveren.

>[!IMPORTANT]
>
> De inhoud van dit document is geen juridisch advies en is niet bedoeld ter vervanging van juridisch advies.
>
> Als uw gegevensverwerker kan Adobe geen juridisch advies geven over het verkrijgen van toestemming. U kunt ook overwegen om met een leverancier van de oplossing van het toestemmingsbeheer, zoals [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) of [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/)te werken, en de juridische afdeling van uw bedrijf voor advies over toestemming en praktijken te raadplegen wanneer het opzetten van uw opt-in implementatie.

## Experience Cloud Opt-In Service

Met de [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) kunt u protocollen instellen voor de bezoeker om u te helpen bepalen of u een cookie kunt instellen op het apparaat of de browser van de gebruiker wanneer u uw site bezoekt.

Dit is een uitbreiding van het [!DNL Experience Cloud ID (ECID) Service]programma waarmee u kunt bepalen of en welke Experience Cloud-oplossingen cookies op webpagina&#39;s kunnen plaatsen voordat de gebruiker hiermee akkoord gaat.

Met de [Experience Cloud Opt-in Service](https://docs.adobe.com/content/help/en/id-service/using/implementation-guides/opt-in-service/optin-overview.html) kunt u ook protocollen instellen om te integreren met uw Consent Management Platform (CMP) en bestaande systemen als onderdeel van uw grotere ontwerp.

## Opt-in beheren / Toestemming verkrijgen

De klanten van de Manager van het publiek hebben de capaciteit om gebruikerstoestemming voor diverse gebruiksgevallen zoals reclame of verpersoonlijking als eigenschappen in de Manager van het Publiek op te slaan. Segmenten die u met deze kenmerken maakt, omvatten dan alleen gebruikers die de respectieve toestemming voor elk van deze gebruiksgevallen geven. Houd er rekening mee dat deze methode gegevensverzameling niet stopt, maar alleen invloed heeft op het gegevensgebruik wanneer u segmenten voor activering verzendt. Wanneer gebruikers hun toestemming intrekken, kunt u deze kenmerken uit het gebruikersprofiel verwijderen met behulp van het [ingebouwde batchproces](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) van Audience Manager of de procedure om te weigeren in Audience Manager (Audience Manager), zoals hieronder wordt beschreven.

## Opt-out beheren/intrekking van toestemming

U kunt de optie Uitschakelen voor de Adobe Experience Cloud beheren via de pagina [Uw privacyopties](https://www.adobe.com/privacy/opt-out.html#customeruse) . Met de functies voor 1 klik kunnen eindgebruikers de gegevensverzameling beheren en uitschakelen met de Adobe Experience Cloud-advertentieoplossingen (waaronder Audience Manager). Specifiek, zie de [bedrijfsklantensectie](https://www.adobe.com/privacy/opt-out.html#customeruse) van de pagina van de Keuzen van de Privacy. Voor browsers die cookies van derden niet ondersteunen, raadpleegt u [Gedeclareerde ID-toewijzing](../../features/declared-ids.md#declared-id-targeting). Voor mobiele apparaten haalt u de relevante id&#39;s van Audience Manager op en roept u de API&#39;s van Audience Manager (Opt-Out voor [](../../features/declared-ids.md#opt-out-examples)gedeclareerde id&#39;s) op. Daarna kunt u alle gegevensverzameling voor die gebruikers beëindigen met de plug-in-API&#39;s van de Mobile SDK - zie [Android-apparaten](https://marketing.adobe.com/resources/help/en_US/mobile/android/privacy.html) en [iOS-apparaten](https://marketing.adobe.com/resources/help/en_US/mobile/ios/privacy.html). Meer informatie over de optie om te weigeren vindt u in de documentatie bij [privacyverzoeken voor](../../overview/data-security-and-privacy/data-privacy-requests.md)gegevens.

## Het beheren van Toestemming voor de Partners van de Tweede Partij

De tweede Partners van de Partij zijn over het algemeen ook Controllers van Gegevens en bezitten het proces voor het verkrijgen van om het even welke noodzakelijke toestemming van de Onderwerp van Gegevens om gegevens met hun tweede partners van partijgegevens te delen. Het is uw verantwoordelijkheid, als Klant van de Manager van het Publiek, om te bepalen als de Tweede Partner de noodzakelijke toestemming voor uw gebruiksgeval heeft verkregen. Meer details over het verkrijgen van toestemming worden hierboven besproken.

## Het beheren van Toestemming voor de Partners van de Derde van de Marktplaats van het Publiek

De Partners van de Derde van de Marktplaats van het publiek zijn ook de Controllers van Gegevens en bezitten hun proces om toestemming te verkrijgen en toegang/schrapping/correctieverzoeken te beheren. Adobe vraagt proactief dat de Partners van de Marktplaats van het Publiek hun informatie van het bedrijfsprofiel binnen de Vinder [van het Publiek van](https://www.adobe-audience-finder.com/) Adobe met extra informatie over de inzameling van gebruikersgegevens bijwerken. De informatie zal van de Partners van de derde van de Marktprijs van het Publiek worden geërfd en op regelmatige basis bijgewerkt. Nochtans, is het aan elke Klant van de Manager van het Publiek om te bepalen dat de Partner van de Derde van de Marktplaats van het Publiek de noodzakelijke toestemming voor het gebruiksgeval van die klant heeft verkregen. Adobe maakt geen opmerkingen over het bereik of de geldigheid van de toestemming die door een partner van de derde partij van de Audience Marketplace voor een bepaald gebruiksgeval wordt verkregen of gerapporteerd.
