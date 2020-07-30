---
description: 'Lees hieronder voor een overzicht van klantenvereisten waaraan u moet voldoen alvorens zich voor op mensen-Gebaseerde Doelen te ondertekenen.  '
seo-description: 'Lees hieronder voor een overzicht van klantenvereisten waaraan u moet voldoen alvorens zich voor op mensen-Gebaseerde Doelen te ondertekenen.  '
seo-title: Vereisten en overwegingen voor op mensen gebaseerde doelen
solution: Audience Manager
title: Vereisten en overwegingen
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: 0ca118abd4e4e8aa3eb8b01123d1f02b712841b2
workflow-type: tm+mt
source-wordcount: '1015'
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

### [!DNL Facebook]

Voordat u uw eerste-partijpubliek [!UICONTROL People-Based Destinations] [!UICONTROL segments] [!DNL Facebook]naar kunt sturen, moet u controleren of aan de volgende vereisten is voldaan:

1. Voor uw [!DNL Facebook] gebruikersaccount moet de machtiging **Campagnes** beheren zijn ingeschakeld voor de advertentieaccount die u wilt gebruiken.
2. Add the **Adobe Experience Cloud** business account as an advertising partner in your [!DNL Facebook Ad Account]. Gebruik `business ID=206617933627973`. See [Add Partners to Your Business Manager](https://www.facebook.com/business/help/1717412048538897) for details.
   >[!IMPORTANT]
   > When configuring the permissions for Adobe Experience Cloud, you must enable the **Manage campaigns** permission. Dit is nodig voor de [!UICONTROL People-Based Destinations]-integratie.
3. Lees en onderteken de [!DNL Facebook Custom Audiences] Servicevoorwaarden. Ga daarvoor naar `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, waarbij `accountID` uw [!DNL Facebook Ad Account ID] is.

### [!DNL LinkedIn]

Voordat u [!UICONTROL People-Based Destinations] de doelsegmenten van de eerste partij naar kunt sturen, moet u ervoor zorgen dat uw [!DNL LinkedIn]account het machtigingsniveau [!DNL LinkedIn Campaign Manager] [!DNL Creative Manager] of hoger heeft.

Leer hoe te om uw [!DNL LinkedIn Campaign Manager] gebruikerstoestemmingen uit te geven, zie [toevoegen, uitgeven, en verwijdert de Toestemmingen van de Gebruiker op Advertising Rekeningen](https://www.linkedin.com/help/lms/answer/5753) in de documentatie LinkedIn.

Zie [Begrip en het Vormen LinkedIn op mensen-Gebaseerde Bestemming](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) voor videoinstructies.

### [!DNL Google Customer Match]

Alvorens u kunt gebruiken [!UICONTROL People-Based Destinations] om uw segment van het eerste partijpubliek naar een [!DNL Google Customer Match] bestemming te verzenden, is het verplicht dat u aan hun lijst van gewenste personen [!DNL Google] toevoegt.

Neem contact op met uw [!DNL Google] vertegenwoordiger en volg de instructies van de lijst van gewenste personen die in de [Use Customer Match Partners worden beschreven om uw gegevensdocumentatie](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) te uploaden [!DNL Google] .

Zodra dit proces is voltooid, kunt u uw [!UICONTROL People-Based Destination]tot stand brengen.

## Data-onboarding {#data-onboarding}

Gegevensinvoer voor [!UICONTROL People-Based Destinations] momenteel ondersteunt maximaal 10 gehashte e-mailadressen gekoppeld aan één klant-id ([!DNL CRM ID]) per batchoverdracht. Het uploaden van meer dan 10 gehakte e-mailadressen verbonden aan één klant identiteitskaart veroorzaakt Audience Manager om 10 van hen in te gaan, in geen specifieke orde.

Door meer dan 10 gehashte e-mailadressen te uploaden die aan één klant-id zijn gekoppeld in meerdere batchoverdrachten, behoudt de Audience Manager de meest recente 10 toegevoegde e-mailadressen.

## Data Privacy {#data-privacy}

Hoewel u [!UICONTROL People-Based Destinations] doelgroepen kunt kiezen op basis van hashed-e-mailadressen die door u zijn geüpload, kunt u nog steeds geen rechtstreeks identificeerbare bezoekersgegevens naar de Audience Manager uploaden. In de gegevensinstapfase moet u ervoor zorgen dat de e-mailadressen die u wilt gebruiken, met het [!DNL SHA256] algoritme worden gehasht. Anders kunt u ze niet gebruiken in [!UICONTROL People-Based Destinations].

## Gegevenshashing versus codering {#data-hashing-encryption}

Codering is een bidirectionele functie. Gecodeerde informatie kan ook worden gedecodeerd met de juiste decoderingssleutel. Het versleutelen van gegevens in het kader van de Audience Manager brengt ernstige risico&#39;s met zich mee, aangezien gecodeerde vormen van persoonlijk identificeerbare informatie ook kunnen worden gedecodeerd. In tegenstelling tot versleuteling, [!UICONTROL People-Based Destinations] zijn deze in plaats daarvan ontworpen om met gehashte gegevens te werken.

Hashing is een eenrichtingsfunctie die de invoer roteert om een uniek resultaat te produceren. Door het gebruiken van juiste het hakken algoritmen, zoals [!DNL SHA256], is er geen manier om de het hakken functie om te keren en de onbezoedelde informatie te openbaren. De e-mailadressen die u aan boord aan Audience Manager zult zijn moeten met het [!DNL SHA256] algoritme worden gehakt. Op deze manier kunt u ervoor zorgen dat er geen ononderbroken e-mailadressen bij de Audience Manager terechtkomen.

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

Adobe Experience Cloud biedt u de mogelijkheid om de klant-id&#39;s via het [!DNL Adobe Experience Platform Identity Service (ECID)]venster te verbergen. Zie [SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) voor gedetailleerde informatie over hoe te om ECID te gebruiken om klant IDs te hakken.

## Gebruikersmachtiging verkrijgen {#obtaining-user-permission}

Aangezien u [!UICONTROL People-Based Destinations] helpt de gegevens van het eerste publiek in mensen-gebaseerde kanalen activeren, is het uw verantwoordelijkheid om het even welke noodzakelijke toestemmingen van uw klanten te informeren en te verkrijgen over hoe u hun gegevens voor reclame of andere doeleinden zult gebruiken.

Voordat u zich aanmeldt voor [!UICONTROL People-Based Destinations], moet u ervoor zorgen dat uw klanten hiervoor toestemming krijgen voordat u hun informatie voor reclamedoeleinden gebruikt.

Als uw klanten zich willen afmelden voor reclamecampagnes, raadpleegt u [](../../overview/data-security-and-privacy/data-privacy-requests.md) Afmelden voor meer informatie over hoe u kunt voorkomen dat Audience Managers nog meer gegevens verzamelen.

## Het afdwingen van de Activering van Gegevens van de Eerste Partij {#enforcing-first-party-activation}

Wanneer het gebruiken [!UICONTROL People-Based Destinations], kunt u eerste-partijgegevens slechts gebruiken om publiekssegmenten in op mensen-gebaseerde kanalen te activeren. U kunt geen gegevens van derden of derden gebruiken voor activering van het publiek in op personen gebaseerde kanalen.

Wanneer het gebruiken [!UICONTROL People-Based Destinations], de Controles [van de Uitvoer van](../data-export-controls.md) Gegevens gebruiken om uw [!UICONTROL data sources] en [!UICONTROL destinations] volgens de richtlijnen en de vereisten van bestemmingsplatforms en gegevensleveranciers te etiketteren.

## Aan boord voor authentiek verklaarde Hashed IDs door Verklaarde identiteitskaart richtend {#onboard-authenticated-declared-id}

Er zijn twee manieren waarop u offline data in Audience Manager kunt opnemen voor [!UICONTROL People-Based Destinations].

* [Batchgegevens](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) naar Audience Manager verzenden om gehashte e-mailadressen in te voeren. Met deze methode kunt u ervoor kiezen om de gehashte e-mailadressen van uw [!DNL CRM] database in te gebruiken [!UICONTROL People-Based Destinations]. Als u deze methode gebruikt, kunt u bovendien ook de gehashte e-mailadressen kwalificeren voor [ongeregistreerde kenmerken](../traits/trait-and-segment-qualification-reference.md).
* Use [Declared IDs](../declared-ids.md) to declare hashed email addresses when passing in authenticated customer IDs. When using this method, Audience Manager, on your behalf, only sends to [!UICONTROL People-Based Destinations] the hashed email addresses from users who have authenticated online. De e-mailadressen die via op personen gebaseerde kanalen worden geactiveerd, zijn alleen de adressen in de gedeclareerde id-gebeurtenisaanroepen. Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in realtime verzonden.
