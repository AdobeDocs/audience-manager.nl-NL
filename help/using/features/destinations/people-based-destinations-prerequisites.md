---
description: 'Lees hieronder voor een overzicht van klantenvereisten waaraan u moet voldoen alvorens zich voor op mensen-Gebaseerde Doelen te ondertekenen.  '
seo-description: 'Lees hieronder voor een overzicht van klantenvereisten waaraan u moet voldoen alvorens zich voor op mensen-Gebaseerde Doelen te ondertekenen.  '
seo-title: Vereisten en overwegingen voor op mensen gebaseerde doelen
solution: Audience Manager
title: Vereisten en overwegingen
translation-type: tm+mt
source-git-commit: 8493705b0f200b5b43d937dfd452210403a52b33

---


# Vereisten en overwegingen {#prerequisites-considerations}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

Hieronder vindt u een overzicht van de behoeften van klanten waaraan u moet voldoen voordat u zich aanmeldt voor [!DNL People-Based Destinations].

>[!IMPORTANT]
> Lees dit artikel zorgvuldig door voordat u verdergaat met de implementatiefase.

## Aanmelden voor op mensen gebaseerde doelen {#signing-up}

[!DNL People-Based Destinations] is een premiumfunctie die uw ervaring in Audience Manager verbetert door u toe te staan om uw eerste-partijpubliekssegmenten in op mensen-gebaseerde milieu&#39;s te activeren, door uw publiek met aangepaste aanbiedingen op sociale netwerken of door e-mailmarketing te richten.

Neem contact op met uw Adobe-vertegenwoordiger om deze premiumfunctie te gebruiken.

## Partner-specifieke vereisten {#partner-prerequisites}

### [!DNL Facebook]

Alvorens u kunt gebruiken [!DNL People-Based Destinations] [!DNL Facebook]om uw eerste-partijpubliekssegmenten naar te verzenden, zorg ervoor u aan de volgende vereisten voldoet:

1. Voor uw [!DNL Facebook] gebruikersaccount moet de machtiging **Campagnes** beheren zijn ingeschakeld voor de advertentieaccount die u wilt gebruiken.
2. Voeg het **Adobe Experience Cloud** -bedrijfsaccount toe als een advertentiepartner in uw [!DNL Facebook Ad Account]. Gebruik `business ID=206617933627973`. Zie Partners [toevoegen aan uw Business Manager](https://www.facebook.com/business/help/1717412048538897) voor meer informatie.
   >[!IMPORTANT]
   > Wanneer u de machtigingen voor Adobe Experience Cloud configureert, moet u de machtiging **Campagnes** beheren inschakelen. Dit is nodig voor de [!DNL People-Based Destinations] integratie.
3. Lees en onderteken de [!DNL Facebook Custom Audiences] Servicevoorwaarden. Om dit te doen, ga naar `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, waar `accountID` is je [!DNL Facebook Ad Account ID].

### [!DNL LinkedIn]

>[!IMPORTANT]
>
> De [!DNL People-Based Destinations] integratie met [!DNL LinkedIn] is momenteel in de bètatestfase en is slechts beschikbaar voor een beperkt aantal klanten.
> 
> Zodra de bètatests zijn beëindigd, is deze integratie beschikbaar voor alle klanten van Audience Manager die zich hebben aangemeld voor [!DNL People-Based Destinations].

Voordat u [!DNL People-Based Destinations] de doelsegmenten van de eerste partij naar kunt sturen, moet u ervoor zorgen dat uw [!DNL LinkedIn]account het machtigingsniveau [!DNL LinkedIn Campaign Manager] [!DNL Creative Manager] of hoger heeft.

Als u wilt leren hoe u uw [!DNL LinkedIn Campaign Manager] gebruikersmachtigingen kunt bewerken, raadpleegt u Gebruikersmachtigingen [toevoegen, bewerken en verwijderen voor Advertising Accounts](https://www.linkedin.com/help/lms/answer/5753)

## Gegevens aan boord {#data-onboarding}

Gegevensinvoer voor [!DNL People-Based Destinations] momenteel ondersteunt maximaal 10 gehashte e-mailadressen gekoppeld aan één klant-id ([!DNL CRM ID]) per batchoverdracht. Het uploaden van meer dan 10 gehakte e-mailadressen verbonden aan één klant identiteitskaart veroorzaakt de Manager van het Publiek om 10 van hen in te voeren, in geen specifieke orde.

Als u in meerdere batchoverdrachten meer dan 10 gehashte e-mailadressen uploadt die aan één klant-id zijn gekoppeld, blijft Audience Manager de meest recente 10 toegevoegde e-mailadressen behouden.

## Gegevensprivacy {#data-privacy}

Hoewel u [!DNL People-Based Destinations] doelgroepen kunt kiezen op basis van hashed-e-mailadressen die door u zijn geüpload, kunt u nog steeds geen rechtstreeks identificeerbare bezoekersgegevens uploaden naar Audience Manager. In de gegevensinstapfase moet u ervoor zorgen dat de e-mailadressen die u wilt gebruiken, met het [!DNL SHA256] algoritme worden gehasht. Anders kunt u ze niet gebruiken in [!DNL People-Based Destinations].

## Gegevenshashing versus codering {#data-hashing-encryption}

Codering is een bidirectionele functie. Gecodeerde informatie kan ook worden gedecodeerd met de juiste decoderingssleutel. Het versleutelen van gegevens in het kader van Audience Manager brengt ernstige risico&#39;s met zich mee, aangezien gecodeerde vormen van persoonlijk identificeerbare gegevens ook kunnen worden gedecodeerd. In tegenstelling tot versleuteling, [!DNL People-Based Destinations] zijn deze in plaats daarvan ontworpen om met gehashte gegevens te werken.

Hashing is een eenrichtingsfunctie die de invoer roteert om een uniek resultaat te produceren. Door het gebruiken van juiste het hakken algoritmen, zoals [!DNL SHA256], is er geen manier om de het hakken functie om te keren en de onbezoedelde informatie te openbaren. De e-mailadressen die u aan boord zult gaan aan de Manager van het Publiek moeten met het [!DNL SHA256] algoritme worden gehakt. Op deze manier kunt u ervoor zorgen dat geen ononderbroken e-mailadressen Audience Manager bereiken.

## Hashing-vereisten {#hashing-requirements}

Wanneer het hashen van de e-mailadressen, zorg ervoor om aan de volgende vereisten te voldoen:

* Alle spaties aan het begin en aan het einde uit de e-mailtekenreeks bijsnijden. voorbeeld: `johndoe@example.com`, niet `<space>johndoe@example.com<space>`;
* Wanneer u de e-mailtekenreeksen hasht, moet u de kleine-lettertekenreeks hashen.
   * Voorbeeld: `example@email.com`, niet `EXAMPLE@EMAIL.COM`;
* Controleer of de hashtekenreeks in kleine letters staat
   * Voorbeeld: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, niet `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Zilp de tekenreeks niet.

Bekijk de onderstaande video om te zien wat de hashingvereisten zijn voor [!UICONTROL People-Based Destinations].

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Met Adobe Experience Cloud kunt u de id&#39;s van klanten via de Adobe Experience Platform Identity Service verbergen. Zie [SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) voor gedetailleerde informatie over hoe te om ECID te gebruiken om klant IDs te hakken.

## Gebruikersmachtiging verkrijgen {#obtaining-user-permission}

Aangezien u [!DNL People-Based Destinations] helpt de gegevens van het eerste publiek in mensen-gebaseerde kanalen activeren, is het uw verantwoordelijkheid om het even welke noodzakelijke toestemmingen van uw klanten te informeren en te verkrijgen over hoe u hun gegevens voor reclame of andere doeleinden zult gebruiken.

Voordat u zich aanmeldt voor [!DNL People-Based Destinations], moet u ervoor zorgen dat uw klanten hiervoor toestemming krijgen voordat u hun informatie voor reclamedoeleinden gebruikt.

Als uw klanten zich willen afmelden voor reclamecampagnes, raadpleegt u [](../../overview/data-security-and-privacy/data-privacy-requests.md) Afmelden voor meer informatie over hoe u Audience Manager kunt beletten gegevens verder te verzamelen.

## Het afdwingen van de Activering van Gegevens van de Eerste Partij {#enforcing-first-party-activation}

Wanneer het gebruiken [!DNL People-Based Destinations], kunt u eerste-partijgegevens slechts gebruiken om publiekssegmenten in op mensen-gebaseerde kanalen te activeren. U kunt geen gegevens van derden of derden gebruiken voor activering van het publiek in op personen gebaseerde kanalen.

Wanneer het gebruiken van [!UICONTROL People-Based Destinations], de Controles [van de Uitvoer van](../data-export-controls.md) Gegevens om uw gegevensbronnen en bestemmingen volgens de richtlijnen en de vereisten van bestemmingsplatforms en gegevensleveranciers te etiketteren.

## Aan boord voor authentiek verklaarde Hashed IDs door Verklaarde identiteitskaart richtend {#onboard-authenticated-declared-id}

Er zijn twee manieren u uw off-line gegevens aan de Manager van het Publiek voor kunt brengen [!DNL People-Based Destinations].

* [Verzend batchgegevens](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) naar Audience Manager om gehashte e-mailadressen in te voeren. Met deze methode kunt u ervoor kiezen om de gehashte e-mailadressen van uw [!DNL CRM] database in te gebruiken [!DNL People-Based Destinations]. Als u deze methode gebruikt, kunt u bovendien ook de gehashte e-mailadressen kwalificeren voor [ongeregistreerde kenmerken](../traits/trait-and-segment-qualification-reference.md).
* Gebruik [gedeclareerde id&#39;s](../declared-ids.md) om gehashte e-mailadressen te declareren wanneer u geverifieerde klant-id&#39;s doorgeeft. Als u deze methode gebruikt, stuurt Audience Manager namens u alleen de gehashte e-mailadressen naar [!DNL People-Based Destinations] de gebruikers die online zijn geverifieerd. De e-mailadressen die via op personen gebaseerde kanalen worden geactiveerd, zijn alleen de adressen in de gedeclareerde id-gebeurtenisaanroepen. Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in realtime verzonden.
