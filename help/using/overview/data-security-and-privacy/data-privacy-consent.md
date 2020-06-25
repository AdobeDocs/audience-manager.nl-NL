---
description: In dit document wordt uitgelegd hoe beheer van machtigingen in de Audience Manager werkt.
seo-description: In dit document wordt uitgelegd hoe beheer van machtigingen in de Audience Manager werkt.
seo-title: Beheer van toestemming
solution: Audience Manager
keywords: GDPR UI, GDPR API, CCPA, privacy, consent
title: Beheer van toestemming
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: data governance & privacy
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '737'
ht-degree: 0%

---


# Beheer van toestemming

## Overzicht {#overview}

In gevallen waarin toestemming voor bepaalde marketingactiviteiten nodig is, moeten de klanten van de Audience Manager het toepassingsgebied en, en of bepaalde toestemmingen moeten worden vernieuwd om verder gebruik te kunnen maken van de gegevens.

Audience Manager biedt u hulpmiddelen om uw capaciteit te helpen om de vereiste toestemmingen van uw gebruikers te verkrijgen, zodat u gepersonaliseerde ervaringen aan hen over kanalen kunt leveren.

>[!IMPORTANT]
>
> De inhoud van dit document is geen juridisch advies en is niet bedoeld ter vervanging van juridisch advies.
>
> Als uw gegevensverwerker kan Adobe geen juridisch advies geven over het verkrijgen van toestemming. U kunt ook overwegen om met een leverancier van de oplossing van het toestemmingsbeheer, zoals [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) of [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/)te werken, en de juridische afdeling van uw bedrijf voor advies over toestemming en praktijken te raadplegen wanneer het opzetten van uw opt-in implementatie.

## Experience Cloud Opt-in-service

Met de [Experience Cloud Opt-In Service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) kunt u protocollen voor de bezoeker instellen om u te helpen bepalen of u een cookie kunt instellen op het apparaat of de browser van het individu wanneer u uw site bezoekt.

Dit is een uitbreiding van het [!DNL Experience Cloud ID (ECID) Service]programma, dat u in staat stelt te bepalen of en welke Experience Cloud-oplossingen cookies op webpagina&#39;s kunnen plaatsen voordat de gebruiker hiermee instemt.

Met de [Experience Cloud Opt-In Service](https://docs.adobe.com/content/help/en/id-service/using/implementation/opt-in-service/optin-overview.html) kunt u ook protocollen instellen om te integreren met uw Consent Management Platform (CMP) en bestaande systemen als onderdeel van uw grotere ontwerp.

## Opt-in beheren / Toestemming verkrijgen

Klanten van Audience Managers hebben de mogelijkheid om toestemming van de gebruiker op te slaan voor verschillende gebruiksgevallen, zoals reclame of personalisatie als kenmerk in de Audience Manager. Segmenten die u met deze kenmerken maakt, omvatten dan alleen gebruikers die de respectieve toestemming voor elk van deze gebruiksgevallen geven. Houd er rekening mee dat deze methode gegevensverzameling niet stopt, maar alleen invloed heeft op het gegevensgebruik wanneer u segmenten voor activering verzendt. Wanneer gebruikers hun toestemming intrekken, kunt u deze kenmerken uit het gebruikersprofiel verwijderen met behulp van het [inkomende batchproces](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) van de Audience Manager of de Audience Manager-optie zoals hieronder beschreven.

## Opt-out beheren/intrekking van toestemming

U kunt de optie Uitschakelen voor de Adobe Experience Cloud beheren via de pagina [Uw privacyopties](https://www.adobe.com/privacy/opt-out.html#customeruse) . Met de functies voor 1 klik kunnen eindgebruikers de gegevensverzameling beheren en uitschakelen met de Adobe Experience Cloud-advertentieoplossingen (waaronder Audience Manager). Specifiek, zie de [bedrijfsklantensectie](https://www.adobe.com/privacy/opt-out.html#customeruse) van de pagina van de Keuzen van de Privacy. Voor browsers die cookies van derden niet ondersteunen, raadpleegt u [Gedeclareerde ID-toewijzing](../../features/declared-ids.md#declared-id-targeting). Voor mobiele apparaten haalt u de desbetreffende Audience Manager-id&#39;s op en roept u de Audience Manager-uitschakelAPI&#39;s op, zoals vermeld in de [gedeclareerde id-voorbeelden](../../features/declared-ids.md#opt-out-examples). Daarna kunt u alle gegevensverzameling voor die gebruikers beëindigen met de plug-in-API&#39;s van de Mobile SDK - zie [Android-apparaten](https://docs.adobe.com/content/help/en/mobile-services/android/gdpr-privacy-android/privacy.html) en [iOS-apparaten](https://docs.adobe.com/content/help/en/mobile-services/ios/privacy-gdpr-ios/privacy.html). Meer informatie over de optie om te weigeren vindt u in de documentatie bij [privacyverzoeken voor](../../overview/data-security-and-privacy/data-privacy-requests.md)gegevens.

## Het beheren van Toestemming voor de Partners van de Tweede Partij

De tweede Partners van de Partij zijn over het algemeen ook Controllers van Gegevens en bezitten het proces voor het verkrijgen van om het even welke noodzakelijke toestemming van de Onderwerp van Gegevens om gegevens met hun tweede partners van partijgegevens te delen. Het is uw verantwoordelijkheid, als Klant van de Audience Manager, om te bepalen als de Tweede Partner de noodzakelijke toestemming voor uw gebruiksgeval heeft verkregen. Meer details over het verkrijgen van toestemming worden hierboven besproken.

## Toegang beheren voor Audience Marketplace-partners van derden

Audience Marketplace-partners van derden zijn ook gegevenscontrollers en bezitten hun proces voor het verkrijgen van toestemming en het beheren van toegang-/verwijderings-/correctieverzoeken. Adobe vraagt proactief dat Audience Marketplace-partners hun bedrijfsprofielgegevens in de [Adobe Audience Finder](https://www.adobe-audience-finder.com/) bijwerken met aanvullende informatie over het verzamelen van gebruikersgegevens. De informatie zal van de derde Partners van Audience Marketplace worden gedownload en op regelmatige basis bijgewerkt. Nochtans, is het aan elke Klant van de Audience Manager om te bepalen dat de Partner van de Derde Audience Marketplace de noodzakelijke toestemming voor het gebruiksgeval van die klant heeft verkregen. Adobe maakt geen opmerkingen over het bereik of de geldigheid van de toestemming die door een Audience Marketplace-partner van derden voor een bepaalde gebruikszaak is verkregen of gemeld.
