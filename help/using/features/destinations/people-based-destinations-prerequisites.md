---
description: 'Lees hieronder voor een overzicht van klantenvereisten waaraan u moet voldoen alvorens zich voor op mensen-Gebaseerde Doelen te ondertekenen.  '
seo-description: 'Lees hieronder voor een overzicht van klantenvereisten waaraan u moet voldoen alvorens zich voor op mensen-Gebaseerde Doelen te ondertekenen.  '
seo-title: Vereisten en overwegingen voor op mensen gebaseerde doelen
solution: Audience Manager
title: Vereisten en overwegingen
feature: People-Based Destinations
translation-type: tm+mt
source-git-commit: d3184195d6a51ff013a3d1fc8526ca9afd3386c2
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

### [!DNL Facebook] {#facebook}

Voordat u [!UICONTROL People-Based Destinations] kunt gebruiken om uw eerste-partijpubliek [!UICONTROL segments] naar [!DNL Facebook] te verzenden, moet u ervoor zorgen dat u aan de volgende vereisten voldoet:

1. Voor uw [!DNL Facebook]-gebruikersaccount moet de **machtiging Campagnes beheren** zijn ingeschakeld voor de Advertentieaccount die u wilt gebruiken.
2. Voeg de **Adobe Experience Cloud** bedrijfsaccount toe als advertentiepartner in uw [!DNL Facebook Ad Account]. Gebruik `business ID=206617933627973`. Zie [Partners toevoegen aan Uw BedrijfsManager](https://www.facebook.com/business/help/1717412048538897) voor details.
   >[!IMPORTANT]
   > Wanneer het vormen van de toestemmingen voor Adobe Experience Cloud, moet u **Manage campagnes** toestemming toelaten. Dit is nodig voor de [!UICONTROL People-Based Destinations]-integratie.
3. Lees en onderteken de [!DNL Facebook Custom Audiences] Servicevoorwaarden. Ga daarvoor naar `https://business.facebook.com/ads/manage/customaudiences/tos/?act=[accountID]`, waarbij `accountID` uw [!DNL Facebook Ad Account ID] is.

### [!DNL LinkedIn] {#linkedin}

Voordat u [!UICONTROL People-Based Destinations] kunt gebruiken om uw eerste-partijpubliekssegmenten naar [!DNL LinkedIn] te verzenden, zorg ervoor uw [!DNL LinkedIn Campaign Manager] rekening [!DNL Creative Manager] of hoger toestemmingsniveau heeft.

Om te leren hoe te om uw [!DNL LinkedIn Campaign Manager] gebruikerstoestemmingen uit te geven, zie [Gebruikerstoestemmingen op Advertising Accounts toevoegen, uitgeven en verwijderen ](https://www.linkedin.com/help/lms/answer/5753) in de documentatie LinkedIn.

Zie [Begrijpen en het Vormen LinkedIn op mensen-Gebaseerde Doel](https://docs.adobe.com/content/help/en/audience-manager-learn/tutorials/data-activation/people-based-destinations/understanding-and-configuring-the-linkedin-pbd.html) voor videoinstructies.

### [!DNL Google Customer Match] {#gcm}

Alvorens u [!UICONTROL People-Based Destinations] kunt gebruiken om uw eerste-partijpubliekssegmenten naar een [!DNL Google Customer Match] bestemming te verzenden, is het verplicht dat [!DNL Google] u aan hun lijst van gewenste personen toevoegt.

Neem contact op met uw [!DNL Google]-vertegenwoordiger en volg de instructies van de lijst van gewenste personen die worden beschreven in de [Gebruik Customer Match-partners om uw gegevens te uploaden](https://support.google.com/google-ads/answer/7361372?hl=en&amp;ref_topic=6296507) [!DNL Google] documentatie.

Nadat dit proces is voltooid, kunt u uw [!UICONTROL People-Based Destination] maken.

## Data-onboarding {#data-onboarding}

Gegevensinvoer voor [!UICONTROL People-Based Destinations] ondersteunt momenteel maximaal 10 gehashte e-mailadressen gekoppeld aan één klant-id ([!DNL CRM ID]) per batchoverdracht. Het uploaden van meer dan 10 gehakte e-mailadressen verbonden aan één klant identiteitskaart veroorzaakt Audience Manager om 10 van hen in te gaan, in geen specifieke orde.

Door meer dan 10 gehashte e-mailadressen te uploaden die aan één klant-id zijn gekoppeld in meerdere batchoverdrachten, behoudt de Audience Manager de meest recente 10 toegevoegde e-mailadressen.

## Data Privacy {#data-privacy}

Hoewel u [!UICONTROL People-Based Destinations] toestaat om doelpubliek te richten dat op gehakte e-mailadressen wordt gebaseerd door u worden geupload, blijft het u verboden om het even welke direct identificeerbare bezoekersinformatie in Audience Manager te uploaden. In de gegevens op instapniveau fase, moet u ervoor zorgen dat de e-mailadressen u van plan bent te gebruiken met het [!DNL SHA256] algoritme worden gehakt. Anders, zult u niet hen in [!UICONTROL People-Based Destinations] kunnen gebruiken.

## Gegevenshashing versus codering {#data-hashing-encryption}

Codering is een bidirectionele functie. Gecodeerde informatie kan ook worden gedecodeerd met de juiste decoderingssleutel. Het versleutelen van gegevens in het kader van de Audience Manager brengt ernstige risico&#39;s met zich mee, aangezien gecodeerde vormen van persoonlijk identificeerbare informatie ook kunnen worden gedecodeerd. In tegenstelling tot codering is [!UICONTROL People-Based Destinations] ontworpen om met gehashte gegevens te werken.

Hashing is een eenrichtingsfunctie die de invoer roteert om een uniek resultaat te produceren. Door het gebruiken van juiste het hakken algoritmen, zoals [!DNL SHA256], is er geen manier om de het hakken functie om te keren en de unscramabled informatie te openbaren. De e-mailadressen die u aan boord aan Audience Manager zult moeten met het [!DNL SHA256] algoritme worden gehakt. Op deze manier kunt u ervoor zorgen dat er geen ononderbroken e-mailadressen bij de Audience Manager terechtkomen.

## Hashing-vereisten {#hashing-requirements}

Wanneer het hashen van de e-mailadressen, zorg ervoor om aan de volgende vereisten te voldoen:

* Alle spaties aan het begin en aan het einde uit de e-mailtekenreeks bijsnijden. voorbeeld: `johndoe@example.com`, niet `<space>johndoe@example.com<space>`;
* Wanneer u de e-mailtekenreeksen hasht, moet u de kleine-lettertekenreeks hashen.
   * Voorbeeld: `example@email.com`, niet `EXAMPLE@EMAIL.COM`;
* Controleer of de hashtekenreeks in kleine letters staat
   * Voorbeeld: `55e79200c1635b37ad31a378c39feb12f120f116625093a19bc32fff15041149`, niet `55E79200C1635B37AD31A378C39FEB12F120F116625093A19bC32FFF15041149`;
* Zilp de tekenreeks niet.

Bekijk de video hieronder om de hashing-vereisten van [!UICONTROL People-Based Destinations] te begrijpen.

>[!VIDEO](https://video.tv.adobe.com/v/29003/)

Adobe Experience Cloud biedt u de optie om klant-id&#39;s via de [!DNL Adobe Experience Platform Identity Service (ECID)] te verbergen. Zie [SHA256 Hashing Support for setCustomerIDs](https://docs.adobe.com/content/help/en/id-service/using/reference/hashing-support.html) voor gedetailleerde informatie over hoe u ECID kunt gebruiken om klant-id&#39;s te hashen.

## Machtiging van gebruiker {#obtaining-user-permission} verkrijgen

Aangezien [!UICONTROL People-Based Destinations] u helpt om de gegevens van het eerste publiek in mensen-gebaseerde kanalen te activeren, is het uw verantwoordelijkheid om om het even welke noodzakelijke toestemmingen van uw klanten te informeren en te verkrijgen over hoe u hun gegevens voor reclame of andere doeleinden zult gebruiken.

Voordat u zich aanmeldt voor [!UICONTROL People-Based Destinations], moet u ervoor zorgen dat uw klanten hun toestemming krijgen voordat u hun informatie voor reclamedoeleinden gebruikt.

Als uw klanten zich willen afmelden voor reclamecampagnes, raadpleegt u [Afmelden-beheer](../../overview/data-security-and-privacy/data-privacy-requests.md) voor meer informatie over hoe u ervoor kunt zorgen dat Audience Manager geen gegevens meer kan verzamelen.

## Bezig met afdwingen van eerste gegevensactivering {#enforcing-first-party-activation}

Als u [!UICONTROL People-Based Destinations] gebruikt, kunt u alleen gegevens van de eerste partij gebruiken om publiekssegmenten in op personen gebaseerde kanalen te activeren. U kunt geen gegevens van derden of derden gebruiken voor activering van het publiek in op personen gebaseerde kanalen.

Wanneer u [!UICONTROL People-Based Destinations] gebruikt, gebruikt u [Besturingselementen voor gegevensuitvoer](../data-export-controls.md) om [!UICONTROL data sources] en [!UICONTROL destinations] te labelen volgens de richtlijnen en vereisten van doelplatforms en gegevensleveranciers.

## Aan boord voor authentiek verklaarde Hashed IDs door Verklaarde identiteitskaart richtend {#onboard-authenticated-declared-id}

Er zijn twee manieren waarop u offline data in Audience Manager kunt opnemen voor [!UICONTROL People-Based Destinations].

* [Audience Manager ](../../integration/sending-audience-data/batch-data-transfer-explained/batch-data-transfer-overview.md) van batchgegevens verzenden naar ingestort e-mailadres. Met deze methode kunt u ervoor kiezen om de gehashte e-mailadressen uit uw [!DNL CRM]-database te gebruiken in [!UICONTROL People-Based Destinations]. Wanneer u deze methode gebruikt, kunt u bovendien de gehashte e-mailadressen kwalificeren voor [onboded traits](../traits/trait-and-segment-qualification-reference.md).
* Gebruik [Opgegeven id&#39;s](../declared-ids.md) om gehashte e-mailadressen te declareren wanneer u geverifieerde klant-id&#39;s doorgeeft. Wanneer u deze methode gebruikt, stuurt Audience Manager namens u alleen de gehashte e-mailadressen van gebruikers die online zijn geverifieerd naar [!UICONTROL People-Based Destinations]. De e-mailadressen die via op personen gebaseerde kanalen worden geactiveerd, zijn alleen de adressen in de gedeclareerde id-gebeurtenisaanroepen. Andere e-mailadressen die aan de klant-id zijn gekoppeld, worden niet in realtime verzonden.
