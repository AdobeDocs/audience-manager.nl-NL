---
description: Lees hieronder voor een overzicht van klantenvereisten waaraan u moet voldoen alvorens zich voor op mensen-Gebaseerde Doelen te ondertekenen.
seo-description: Read below for an overview of customer requirements that you need to meet before signing up for People-Based Destinations.
seo-title: People-Based Destinations Prerequisites and Considerations
solution: Audience Manager
title: Vereisten en overwegingen
feature: People-based Destinations
exl-id: 7656aa3e-3410-4052-8e29-b702bd0bf149
source-git-commit: cd40e1e3cc2199d1937950934d674cfad301f3e8
workflow-type: tm+mt
source-wordcount: '996'
ht-degree: 3%

---

# Vereisten en overwegingen {#prerequisites-considerations}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Hieronder vindt u een overzicht van de behoeften van klanten waaraan u moet voldoen voordat u zich aanmeldt voor [!UICONTROL People-Based Destinations].

>[!IMPORTANT]
> Lees dit artikel zorgvuldig door voordat u verdergaat met de implementatiefase.

## Aanmelden voor [!UICONTROL People-Based Destinations] {#signing-up}

[!UICONTROL People-Based Destinations] is een premiumfunctie die uw Audience Manager-ervaring vergroot door u toe te staan om uw eersteklas publiekssegmenten in op mensen gebaseerde omgevingen te activeren, door uw publiek te richten op aangepaste aanbiedingen op sociale netwerken of via e-mailmarketing.

Neem contact op met uw Adobe-vertegenwoordiger om gebruik te maken van deze premiumfunctie.

## Partner-specifieke vereisten {#partner-prerequisites}

### [!DNL Facebook] {#facebook}

Voordat u [!UICONTROL People-Based Destinations] om uw eerste publiek te verzenden [!UICONTROL segments] tot [!DNL Facebook]voldoet aan de volgende vereisten:

1. Uw [!DNL Facebook] gebruikersaccount moet de **Campagnes beheren** Toestemming ingeschakeld voor de advertentie-account die u wilt gebruiken.
2. Voeg de **Adobe Experience Cloud** zakelijke account als advertentiepartner in uw [!DNL Facebook Ad Account]. Gebruik `business ID=206617933627973`. Zie [Partners toevoegen aan uw Business Manager](https://www.facebook.com/business/help/1717412048538897) voor meer informatie.
   >[!IMPORTANT]
   > Wanneer u de machtigingen voor Adobe Experience Cloud configureert, moet u de optie **Campagnes beheren** toestemming. Dit is nodig voor de [!UICONTROL People-Based Destinations]-integratie.
3. Lees en onderteken de [!DNL Facebook Custom Audiences] Servicevoorwaarden. Ga daarvoor naar `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, waarbij `accountID` uw [!DNL Facebook Ad Account ID] is.

### [!DNL LinkedIn] {#linkedin}

Voordat u [!UICONTROL People-Based Destinations] om uw segmenten van het eerste publiek naar te sturen [!DNL LinkedIn], zorg ervoor dat uw [!DNL LinkedIn Campaign Manager] account bevat [!DNL Creative Manager] of hoger machtigingsniveau.

Meer informatie over het bewerken van uw [!DNL LinkedIn Campaign Manager] gebruikersmachtigingen, zie [Gebruikersmachtigingen toevoegen, bewerken en verwijderen voor advertentieaccounts](https://www.linkedin.com/help/lms/answer/5753) in de documentatie van LinkedIn.

Zie [Het begrip van en het Vormen van de op mensen-Gebaseerde Bestemming van LinkedIn](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) voor video-instructies.

### [!DNL Google Customer Match] {#gcm}

Voordat u [!UICONTROL People-Based Destinations] om uw segmenten van het eerste publiek naar een [!DNL Google Customer Match] bestemming, zorg ervoor u leest en aan het beleid van Google hanteert voor het gebruiken [!DNL Customer Match], die in de [Google-ondersteuningsdocumentatie](https://support.google.com/google-ads/answer/6299717).

Controleer vervolgens of [!DNL Google] account is geconfigureerd voor een [!DNL Standard] of hoger machtigingsniveau. Zie de [Google Ads-documentatie](https://support.google.com/google-ads/answer/9978556?visit_id=637611563637058259-4176462731&amp;rd=1) voor meer informatie.

Klanten met compatibele accounts worden automatisch door Google aangeboden.

## Data-onboarding {#data-onboarding}

Gegevensinvoer voor [!UICONTROL People-Based Destinations] ondersteunt momenteel maximaal 10 gehashte e-mailadressen gekoppeld aan één klant-id ([!DNL CRM ID]), per partij. Het uploaden van meer dan 10 gehakte e-mailadressen verbonden aan één klant identiteitskaart veroorzaakt Audience Manager om 10 van hen in te gaan, in geen specifieke orde.

Door meer dan 10 gehashte e-mailadressen te uploaden die aan één klant-id zijn gekoppeld in meerdere batchoverdrachten, behoudt de Audience Manager de meest recente 10 toegevoegde e-mailadressen.

## Data Privacy {#data-privacy}

Hoewel [!UICONTROL People-Based Destinations] zodat u doelgroepen kunt kiezen op basis van gehashte e-mailadressen die door u zijn geüpload, kunt u nog steeds geen rechtstreeks identificeerbare bezoekersgegevens naar de Audience Manager uploaden. In de gegevensinstapfase moet u ervoor zorgen dat de e-mailadressen die u wilt gebruiken, worden gekoppeld aan de [!DNL SHA256] algoritme. Anders kunt u ze niet gebruiken in [!UICONTROL People-Based Destinations].

## Gegevenshashing versus codering {#data-hashing-encryption}

Codering is een bidirectionele functie. Gecodeerde informatie kan ook worden gedecodeerd met de juiste decoderingssleutel. Het versleutelen van gegevens in het kader van de Audience Manager brengt ernstige risico&#39;s met zich mee, aangezien gecodeerde vormen van persoonlijk identificeerbare informatie ook kunnen worden gedecodeerd. In tegenstelling tot versleuteling [!UICONTROL People-Based Destinations] zijn ontworpen om te werken met gehashte gegevens.

Hashing is een eenrichtingsfunctie die de invoer roteert om een uniek resultaat te produceren. Door juiste hash-algoritmen te gebruiken, zoals [!DNL SHA256], is er geen manier om de hashing functie om te keren en de onverstrooide informatie te onthullen. De e-mailadressen die u aan boord aan Audience Manager gaat, moeten met de [!DNL SHA256] algoritme. Op deze manier kunt u ervoor zorgen dat er geen ononderbroken e-mailadressen bij de Audience Manager terechtkomen.

## Hashing-vereisten {#hashing-requirements}

Wanneer het hashen van de e-mailadressen, zorg ervoor om aan de volgende vereisten te voldoen:

* Alle spaties aan het begin en aan het einde uit de e-mailtekenreeks bijsnijden. voorbeeld: `johndoe@example.com`, niet `<space>johndoe@example.com<space>`;
* Wanneer u de e-mailtekenreeksen hasht, moet u de kleine-lettertekenreeks hashen.
   * Voorbeeld: `example@email.com`, niet `EXAMPLE@EMAIL.COM`;
* Controleer of de hashtekenreeks in kleine letters staat
   * Voorbeeld: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, niet `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Zilp de tekenreeks niet.

Bekijk de onderstaande video om te zien wat de hashvereisten zijn voor [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud biedt u de mogelijkheid om de klant-id&#39;s via de [!DNL Adobe Experience Platform Identity Service (ECID)]. Zie [SHA256 Hashing Support for setCustomerIDs](https://experienceleague.adobe.com/docs/id-service/using/reference/hashing-support.html) voor gedetailleerde informatie over hoe te om ECID te gebruiken om klant IDs te hakken.

## Gebruikersmachtiging verkrijgen {#obtaining-user-permission}

Sinds [!UICONTROL People-Based Destinations] helpt u de gegevens van het eerste publiek in mensen-gebaseerde kanalen activeren, is het uw verantwoordelijkheid om het even welke noodzakelijke toestemmingen van uw klanten te informeren en te verkrijgen over hoe u hun gegevens voor reclame of andere doeleinden zult gebruiken.

Voordat u zich aanmeldt voor [!UICONTROL People-Based Destinations], zorg ervoor dat u de toestemming van uw klanten krijgt voordat u de informatie voor reclamedoeleinden gebruikt.

Als uw klanten zich willen afmelden voor reclamecampagnes, raadpleegt u [Uitschakelen van beheer](../../overview/data-security-and-privacy/data-privacy-requests.md) voor meer informatie over hoe kan worden voorkomen dat de Audience Manager gegevens verder verzamelt.

## Het afdwingen van de Activering van Gegevens van de Eerste Partij {#enforcing-first-party-activation}

Wanneer u [!UICONTROL People-Based Destinations], kunt u gegevens van de eerste partij slechts gebruiken om publiekssegmenten in op mensen-gebaseerde kanalen te activeren. U kunt geen gegevens van derden of derden gebruiken voor activering van het publiek in op personen gebaseerde kanalen.

Wanneer u [!UICONTROL People-Based Destinations], gebruik [Besturingselementen voor gegevensexport](../data-export-controls.md) om uw [!UICONTROL data sources] en [!UICONTROL destinations] volgens de richtsnoeren en eisen van de doelplatforms en de gegevensverstrekkers.

## Aan boord voor authentiek verklaarde Hashed IDs door Verklaarde identiteitskaart richtend {#onboard-authenticated-declared-id}

Er zijn twee manieren waarop u offline data in Audience Manager kunt opnemen voor [!UICONTROL People-Based Destinations].

* [Batchgegevens verzenden](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) naar Audience Manager om gehashte e-mailadressen in te voeren. Met deze methode kunt u de gehashte e-mailadressen uit uw [!DNL CRM] database in [!UICONTROL People-Based Destinations]. Als u deze methode gebruikt, kunt u bovendien ook de gehashte e-mailadressen kwalificeren voor [ongebogen eigenschappen](../traits/trait-and-segment-qualification-reference.md).
* Gebruiken [Opgegeven id&#39;s](../declared-ids.md) gehashte e-mailadressen declareren wanneer geverifieerde klant-id&#39;s worden doorgegeven. Wanneer het gebruiken van deze methode, verzendt de Audience Manager, namens u slechts naar [!UICONTROL People-Based Destinations] de gehashte e-mailadressen van gebruikers die online zijn geverifieerd. De e-mailadressen die via op personen gebaseerde kanalen worden geactiveerd, zijn alleen de adressen in de gedeclareerde id-gebeurtenisaanroepen. Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in realtime verzonden.
