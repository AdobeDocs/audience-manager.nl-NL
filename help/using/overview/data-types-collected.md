---
description: Met Audience Manager kunt u data van eerste, tweede en derde partijen verzamelen en beheren.
seo-description: Met Audience Manager kunt u data van eerste, tweede en derde partijen verzamelen en beheren.
seo-title: Verzamelde datatypen
solution: Audience Manager
title: Verzamelde datatypen
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
feature: overview
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '867'
ht-degree: 73%

---


# Verzamelde datatypen {#types-of-data-collected}

[!DNL Audience Manager]Met kunt u data van eerste, tweede en derde partijen verzamelen en beheren.

Het ontgrendelen van klantinformatie-assets die zijn opgeslagen in meerdere silo’s, is één van de grootste uitdagingen voor data waarmee bedrijven tegenwoordig te maken hebben. From [!DNL CRM] databases, to registration systems, to ad servers, and so forth, companies require tools that help centralize valuable data and manage customer/audience information as a single strategic data asset. [!DNL Audience Manager] helpt u geïsoleerde klantinformatie te ontgrendelen en dataverzameling van meerdere bronnen te beheren. Collected data can be managed based on data element time-to-live ([!DNL TTL]) values, which helps the publisher control data expiration across all sources. [!DNL Audience Manager] is ontworpen om u te helpen de volgende datatypen te beheren:

| Datatype | Waar dat vandaan komen |
|---|---|
| **Eerste partij** | Klanten. Data worden online verzameld (via interacties met consumenten op uw websites) of offline. |
| **Tweede partij** | Strategische partners en adverteerders. |
| **Derde partij** | Dataproviders en/of data-uitwisseling. Data kunnen informatie bevatten zoals intentie, demografie, sociale stijl/levensstijl, psychografie, en meer. |

## Dataverzameling van eerste partijen {#first-party-data}

First-party data collection is a main [!DNL Audience Manager] feature. Met deze kerncompetentie wordt tegemoetgekomen aan de behoeften van onze klanten (uitgevers of adverteerders) die bedrijfseigen data willen gebruiken als de hoeksteen van hun marketingprogramma’s, of die willen targeten en modelleren tegenover andere databronnen.

[!DNL Audience Manager] werkt met klanten om hun datastrategie te begrijpen, en past die strategie vervolgens toe op een aangepast dataverzamelplan. Ons team voor partneroplossingen werkt met u samen om websites, onbewerkte datasignalen en andere gebruikersinteractie op uw websites te evalueren. Aan de hand van deze informatie helpen we u bij het maken van een aangepaste strategie voor dataverzameling die datasignalen op gebruikersniveau van diverse pagina’s in uw inventory vastlegt. Vastgelegde data worden opgeslagen en weer toegepast op een vooraf gedefinieerde taxonomie die op elk moment kan worden bijgewerkt, wanneer uw bedrijfsbehoeften veranderen.

In het volgende voorbeeld ziet u hoe mogelijke data-elementen kunnen worden vastgelegd van voorbeeldwinkelpagina.

![shopping-cart-data](assets/shopping-cart-data.png)

| Item | Beschrijving |
|---|---|
| 1 | **Geslacht**. De voornaam van iemand die winkelt, geeft meestal het geslacht aan. In ons voorbeeld is de voornaam van de winkelende persoon Mary, dus we weten dat het een vrouw is. Namen worden nooit opgeslagen door Audience Manager. |
| 2 | **Interesses**. De artikelen in de winkelwagen kunnen op verschillende interesses wijzen. In ons voorbeeld besteedt Mary veel geld aan fitnessapparatuur. |
| 3 | **Type adres**. Op basis van het verzend- en/of factuuradres kunt u afleiden of Mary fitnessapparatuur koopt voor zichzelf of voor een bedrijf. |
| 4 | **Locatie**. [!DNL ZIP] codes zijn betrouwbaarder dan [!DNL IP] adressen wanneer het aanwijzen van een plaats aankomt. |
| 5 | **Affiniteit met aanbiedingen**. Als iemand die winkelt, reclamecodes of cadeaukaarten gebruikt, is het waarschijnlijk een koopjesjager die de beste deals zoekt. |
| 6 | **Koopkracht**. Price data correlated with [!DNL ZIP+4] codes indicate spending power of a given location. |

After the raw data is collected, it gets mapped back to customer-defined traits within the [!DNL Audience Manager] platform. Zowel de taxonomie als de datatoewijzingen kunnen op elk moment worden aangepast zonder de code voor dataverzameling te hoeven wijzigen.

## Dataverzameling van tweede partijen {#second-party-data}

De data van tweede partijen komen van strategische bedrijfspartners (het zijn geen uitgeversdata). Deze informatie wordt net zo verzameld en beheerd als de data van eerste partijen.

Een gebruiksscenario voor data van tweede partijen sturen adverteerders hun eigen data-assets naar uitgevers om die informatie te combineren met de data van de uitgever en vervolgens een beter getarget advertentieprogramma te kunnen uitvoeren. Bovendien kunnen uitgevers hun pool van doelgroepen uitbreiden door samen te werken met hun adverteerders. In most cases, these arrangements involve contractual relationships limited to putting the [!DNL Audience Manager] container tag on the partner site to facilitate data collection and sharing.

Een voorbeeld van het verzamelen en remarketen van data van tweede partijen is een kledinghandelaar die data verzamelt over zijn producten en deze informatie dan met belangrijke partners deelt. In this case, the retailed could serve different ads across an [!DNL Audience Manager] partner site for consumers who chose various jacket colors and sizes.

![](assets/shopping-cart-traits.png)

## Dataverzameling van derde partijen {#third-party-data}

Data van derde partijen worden verzameld en gedeeld door leveranciers buiten [!DNL Audience Manager].

Third-party data can be used to qualify existing data [!UICONTROL segments] (for example, age, household income, and so forth), provide data that is in demand but not otherwise available, or be used in lookalike modeling against a known user base from first-party and second-party data. [!DNL Audience Manager] werkt met veel externe dataleveranciers en helpt u begrijpen welk type data deze dataleveranciers verzamelen, waardoor u met elke provider de juiste strategische deals kunt maken.

>[!NOTE]
>
>Zie [Adobe Audience Finder](https://www.adobe-audience-finder.com/) voor een volledige lijst met derdepartijdataleveranciers die worden ondersteund door [!DNL Audience Manager].

[!DNL Audience Manager] integreert met andere gegevensleveranciers die op hun beschikbare [!DNL APIs] en gegevensreeksen worden gebaseerd. Dataverzameling werkt in real time, terwijl een gebruiker door uw website bladert, of via out-of-band methodes waar id’s worden gesynchroniseerd tussen partners en data worden overgedragen tussen servers nadat een gebruiker uw website heeft verlaten. In either case, [!DNL Audience Manager] clients get the benefit of having third-party data synchronized on our platform, which means each client, or domain, does not have to perform its own synchronization. Daardoor wordt het bereik groter en vermindert het aantal servercalls van de pagina.

## Matchpartners {#match-partners}

Veel klanten werken bij voorkeur met derdepartij-datamatchpartners. Deze entiteiten hebben relaties met websites die registratievereisten hanteren, en kunnen klantdata verwerken door deze (in real time) te matchen tegen hun registratienetwerk.

![data-provider-match](assets/data-provider-match.png)
