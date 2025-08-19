---
description: In dit document wordt uitgelegd hoe toestemmingsbeheer werkt in Audience Manager.
seo-description: This document explains how consent management works in Audience Manager.
seo-title: Consent Management
solution: Audience Manager
keywords: GDPR-gebruikersinterface, GDPR-API, CCPA, privacy, toestemming
title: Consent Management
uuid: ed23a478-32be-460d-bb03-a735317f7c0f
feature: Data Governance & Privacy
exl-id: 9e545e8d-dbe4-4df9-8801-af3c2c73e406
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '685'
ht-degree: 98%

---

# Consent Management

## Overzicht {#overview}

In gevallen waarin toestemming voor bepaalde marketingactiviteiten nodig is, moeten klanten van Audience Manager bepalen wat het bereik is, en of bepaalde toestemmingen moeten worden vernieuwd om door te kunnen gaan met het gebruik van data.

Audience Manager biedt u tools ter ondersteuning van uw vermogen om de vereiste toestemmingen van uw gebruikers te verkrijgen, zodat u hun gepersonaliseerde ervaringen kunt leveren via diverse kanalen.

>[!IMPORTANT]
>
>  De inhoud van dit document is geen juridisch advies en is niet bedoeld ter vervanging van juridisch advies.
>
> Als uw dataprocessor kan Adobe geen juridisch advies geven over het verkrijgen van toestemming. U kunt ook overwegen om te werken met een oplossingenleverancier voor toestemmingsbeheer zoals [Evidon](https://theblog.adobe.com/evidon-builds-gdpr-universal-consent-integration-with-launch-by-adobe/) of [TrustArc](https://theblog.adobe.com/trustarc-builds-consent-integration-launch-adobe/), en de juridische afdeling van uw bedrijf te raadplegen voor advies over toestemming en praktijken bij het instellen van uw opt-in-implementatie.

## Experience Cloud Opt-In Service

Met de [Experience Cloud Opt-in Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=nl-NL) kunt u protocollen instellen voor de bezoeker om u te helpen bepalen of u een cookie kunt instellen op het apparaat of de browser van de individuele gebruiker wanneer deze uw website bezoekt.

Dit is een uitbreiding van de [!DNL Experience Cloud ID (ECID) Service], waarmee u kunt bepalen of en welke Experience Cloud-oplossingen cookies op webpagina’s kunnen plaatsen voor gebruikers voordat ze hiermee akkoord zijn gegaan.

Met de [Experience Cloud Opt-in Service](https://experienceleague.adobe.com/docs/id-service/using/implementation/opt-in-service/optin-overview.html?lang=nl-NL) kunt u ook protocollen instellen om te integreren met uw Consent Management Platform (CMP) en bestaande systemen als onderdeel van uw grotere ontwerp.

## Opt-in beheren/Toestemming verkrijgen

De klanten van Audience Manager hebben de mogelijkheid om gebruikerstoestemming op te slaan voor diverse gebruiksscenario’s, zoals adverteren personalisatie als eigenschappen in Audience Manager. Segmenten die u met deze eigenschappen maakt, bevatten dan alleen gebruikers die de betreffende toestemming voor elk van deze gebruiksscenario’s hebben gegeven. Houd er rekening mee dat deze aanpak de dataverzameling niet beëindigt, maar alleen invloed heeft op het datagebruik wanneer u segmenten verzendt voor activering. Wanneer gebruikers hun toestemming intrekken, kunt u deze eigenschappen verwijderen uit het gebruikersprofiel met behulp van het [ingebouwde batchproces](../../integration/sending-audience-data/batch-data-transfer-explained/inbound-file-contents.md) van Audience Manager, of het opt-outproces van Audience Manager zoals hieronder wordt beschreven.

## Opt-out beheren/Toestemming intrekken

U kunt opt-out voor de Adobe Experience Cloud beheren via de pagina [Uw privacyopties](https://www.adobe.com/nl/privacy/opt-out.html#customeruse). Met 1-klikfuncties kunnen uw eindgebruikers de verzameling van hun data door de Adobe Experience Cloud-advertentieoplossingen (inclusief Audience Manager) beheren en uitschakelen. Zie met name de [sectie voor zakelijke klanten](https://www.adobe.com/nl/privacy/opt-out.html#customeruse) van de pagina voor privacyopties. Voor browsers die cookies van derden niet ondersteunen, raadpleegt u [Gedeclareerde id-targeting](../../features/declared-ids.md#declared-id-targeting). Voor mobiele apparaten haalt u de relevante Audience Manager-id’s op en roept u de opt-out-API’s van Audience Manager op zoals vermeld in [Voorbeelden van gedeclareerde id-opt-outs](../../features/declared-ids.md#opt-out-examples). Daarna kunt u alle dataverzameling beëindigen voor gebruikers met de opt-out-API’s van de Mobile SDK: zie [Android-apparaten](https://experienceleague.adobe.com/docs/mobile-services/android/gdpr-privacy-android/privacy.html?lang=nl-NL) en [iOS-apparaten](https://experienceleague.adobe.com/docs/mobile-services/ios/privacy-gdpr-ios/privacy.html?lang=nl-NL). Meer informatie over opt-out vindt u in de [documentatie bij Data Privacy-aanvragen](../../overview/data-security-and-privacy/data-privacy-requests.md).

## Toestemming beheren voor tweedepartijpartners

Tweedepartijpartners zijn over het algemeen ook datacontrollers en beschikken over het proces voor verkrijging van elke vereiste toestemming van de geregistreerde persoon om hun data te delen met hun tweedepartijpartners. Het is uw verantwoordelijkheid als Audience Manager-klant om te bepalen of de tweedepartijpartner de noodzakelijke toestemming voor uw gebruiksscenario heeft verkregen. Meer details over het verkrijgen van toestemming worden hierboven besproken.

## Toestemmingsbeheer voor derdepartijpartners van Audience Marketplace

De derdepartijpartners van Audience Marketplace zijn eveneens datacontrollers en beschikken over het proces voor verkrijging van toestemming en het beheer van aanvragen voor toegang/verwijdering/correctie. Adobe verzoekt derdepartijpartners van Audience Marketplace proactief om hun bedrijfsprofielinformatie bij te werken binnen [Adobe Audience Finder](https://www.adobe-audience-finder.com/) met aanvullende informatie over de verzameling van gebruikersdata. De informatie is afkomstig van de derdepartijpartners van Audience Marketplace en worden regelmatig bijgewerkt. Het is echter aan elke Audience Manager-klant om te bepalen of de derdepartijpartner van Audience Manager de noodzakelijke toestemming voor het gebruiksscenario van een bepaalde klant heeft verkregen. Adobe doet geen uitspraken over de omvang of de geldigheid van de toestemming die door een derdepartijpartner van Audience Marketplace voor een bepaald gebruiksscenario is verkregen of gemeld.
