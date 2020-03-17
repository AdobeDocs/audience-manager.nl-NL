---
description: Met Audience Manager kunt u gegevens van eerste en tweede bedrijven en van derden verzamelen en beheren.
seo-description: Met Audience Manager kunt u gegevens van eerste en tweede bedrijven en van derden verzamelen en beheren.
seo-title: Typen verzamelde gegevens
solution: Audience Manager
title: Typen verzamelde gegevens
uuid: a2ddf470-32e6-41ec-a1d7-a6232ef084b9
translation-type: tm+mt
source-git-commit: 708c998fbe1cbd3e9acb51e31ee1c89e2f06d28d

---


# Typen verzamelde gegevens{#types-of-data-collected}

Met Audience Manager kunt u gegevens van eerste en tweede bedrijven en van derden verzamelen en beheren.

Het ontgrendelen van de middelen van de klanteninformatie die in veelvoudige silo&#39;s worden opgeslagen is één van de grootste gegevensuitdagingen waarmee bedrijven vandaag worden geconfronteerd. Van de gegevensbestanden van CRM, tot registratiesystemen, tot en met servers, etc., vereisen de bedrijven hulpmiddelen die helpen waardevolle gegevens centraliseren en klant/publieksinformatie als één enkel strategisch gegevensmiddel beheren. De Manager van de publiek helpt u geïsoleerde klanteninformatie ontgrendelen en gegevensinzameling van veelvoudige bronnen beheren. De verzamelde gegevens kunnen worden beheerd gebaseerd op tijd-aan-levende (TTL) waarden van het gegevenselement, die de gegevensvervalsing van de uitgeverscontrole over alle bronnen helpt. Publiek Manager wordt ontworpen om u te helpen de volgende types van gegevens beheren:

| Gegevenstype | Waarvan gegevens afkomstig zijn |
|---|---|
| **Eerste partij** | Klanten. Gegevens worden online (via consumenteninteracties op uw websites) of offline verzameld. |
| **Tweede partij** | Strategische partners en adverteerders. |
| **Derden** | Verleners en/of uitwisseling van gegevens. De gegevens kunnen informatie zoals intent, demografie, sociale/levensstijl, psychografisch, en meer omvatten. |

## Gegevensverzameling van eerste partijen {#first-party-data}

De gegevensinzameling van de eerste partij is een belangrijkste eigenschap van de Manager van de Publiek. Met deze kerncompetentie wordt tegemoetgekomen aan de behoeften van onze klanten (uitgevers of adverteerders) die bedrijfseigen gegevens willen gebruiken als de hoeksteen van hun marketingprogramma&#39;s, of die zich willen richten op en modelleren van andere gegevensbronnen.

<!-- 

c_1st_party_data.xml

 -->

De Manager van het publiek werkt met cliënten om hun gegevensstrategie te begrijpen en brengt dan die strategie terug naar een douane gegeven-inzamelingsplan in kaart. Ons team van Oplossingen van de Partner werkt met u om plaatsen, ruwe gegevenssignalen, en andere gebruikersinteractie op uw websites te evalueren. Op basis van deze informatie helpen we u een op maat gemaakte strategie voor gegevensverzameling te ontwikkelen waarmee op gebruikersniveau gegevenssignalen van verschillende pagina&#39;s in uw overzicht worden vastgelegd. Vastgelegde gegevens worden opgeslagen en terug toegewezen aan een vooraf bepaalde taxonomie, die op elk ogenblik kan worden bijgewerkt, aangezien uw bedrijfsbehoeften veranderen.

In het volgende voorbeeld ziet u hoe mogelijke gegevenselementen kunnen worden vastgelegd op een pagina waarop u monsters kunt nemen.

![winkelwagentje](assets/shopping-cart-data.png)

| Item | Beschrijving |
|---|---|
| 1 | **Geslacht**. De voornaam van een winkelier geeft meestal het geslacht aan. In ons voorbeeld is de voornaam van de verkoopster Mary, dus we weten dat de verkoopster een vrouw is. Namen worden nooit opgeslagen door Audience Manager. |
| 2 | **Belangen**. De artikelen in het winkelwagentje kunnen verschillende belangen aangeven. In ons voorbeeld besteedt Mary veel aan fitnessapparatuur. |
| 3 | **Huisvestingstype**. Op basis van de verzendings- en/of factureringsadressen kunt u afleiden of Mary fitness-apparatuur voor zichzelf of voor een bedrijf koopt. |
| 4 | **Locatie**. ZIP-codes zijn betrouwbaarder dan IP-adressen wanneer een locatie wordt aangewezen. |
| 5 | **Promotie-affiniteit**. Als een winkelier promotionele codes of cadeaukaarten gebruikt, is het waarschijnlijk een jager die naar de beste deals zoekt. |
| 6 | **Besparing**. Prijsgegevens die zijn gecorreleerd met ZIP+4-codes geven de bestedingskracht van een bepaalde locatie aan. |

Nadat de ruwe gegevens worden verzameld, wordt het in kaart gebracht terug naar klant-bepaalde eigenschappen binnen het platform van de Manager van de Publiek. Zowel de taxonomie als de gegevenstoewijzingen kunnen op elk ogenblik worden aangepast zonder veranderingen in de code van de gegevensinzameling aan te brengen.

## Gegevensverzameling van tweede partijen {#second-party-data}

De gegevens van de tweede partij komen van een strategische bedrijfspartner (het is geen uitgeversgegevens). Deze informatie wordt verzameld en beheerd enkel zoals de gegevens van de eerste partij.

<!-- 

c_2nd_party_data.xml

 -->

In een tweede gegevensscenario sturen adverteerders hun eigen gegevensmiddelen naar uitgevers zodat ze die informatie kunnen combineren met de gegevens van de uitgever en vervolgens een gerichter reclameprogramma kunnen uitvoeren. Bovendien kunnen uitgevers hun publiek uitbreiden door samen te werken met hun adverteerders. In de meeste gevallen, impliceren deze regelingen contractuele verhoudingen beperkt tot het zetten van de de containermarkering van de Manager van de Publiek op de partnerplaats om gegevensinzameling en het delen te vergemakkelijken.

Een voorbeeld van verzameling en hermarketing van gegevens van de tweede partij zou een kledinghandelaar kunnen omvatten die gegevens over zijn producten verzamelt en dan deze informatie met zeer belangrijke partners deelt. In dit geval, kon detailhandelde verschillende advertenties over een de partnerplaats van de Manager van de Publiek voor consumenten dienen die diverse jaskleuren en grootte kozen.

![](assets/shopping-cart-traits.png)

## Gegevensverzameling van derden {#third-party-data}

Gegevens van derden worden verzameld en gedeeld door leveranciers buiten Audience Manager.

<!-- 

c_3rd_party_data.xml

 -->

Gegevens van derden kunnen worden gebruikt om bestaande gegevenssegmenten (bijvoorbeeld leeftijd, inkomen van huishoudens, enzovoort) te kwalificeren, om gegevens te verstrekken die in vraag zijn maar niet anderszins beschikbaar zijn, of om te worden gebruikt in normale modellering tegen een bekende gebruikersbasis van gegevens van eerste en tweede partij. Audience Manager werkt met veel externe gegevensleveranciers en helpt u het type gegevens te begrijpen dat deze gegevensleveranciers verzamelen, zodat u de juiste strategische deals met elke leverancier kunt maken.

>[!NOTE]
>
>Raadpleeg de [!DNL Audience Manager]Adobe Audience Finder voor een volledige lijst met gegevensproviders van derden die worden ondersteund door [Adobe](https://www.adobe-audience-finder.com/).

Audience Manager kan worden geïntegreerd met andere gegevensproviders op basis van hun beschikbare API&#39;s en gegevenssets. De inzameling van gegevens werkt in real time, aangezien een gebruiker uw plaats doorbladert, of via out-of-band methodes waar IDs tussen partners wordt gesynchroniseerd en het gegeven tussen servers wordt overgebracht nadat een gebruiker uw plaats heeft verlaten. In beide gevallen krijgen clients van Audience Manager het voordeel dat gegevens van derden op ons platform worden gesynchroniseerd. Dit houdt in dat elke client of domein geen eigen synchronisatie hoeft uit te voeren. Dit helpt bereik verhogen en vermindert servervraag van de pagina.

## Identieke partners {#match-partners}

Vele cliënten verkiezen om met derdegegevens-gelijke partners te werken. Deze entiteiten hebben verhoudingen met plaatsen die registratievereisten hebben en kunnen dossiers van klantengegevens verwerken door hen (in real time) aan te passen die op hun registratienetwerk worden gebaseerd.

![data-provider-match](assets/data-provider-match.png)
