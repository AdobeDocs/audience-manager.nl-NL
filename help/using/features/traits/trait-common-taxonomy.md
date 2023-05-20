---
description: Dit artikel biedt een algemeen overzicht van het classificeren van kenmerken met een gemeenschappelijke taxonomie.
keywords: DIL
seo-description: This article provides general overview about classifying traits with a common taxonomy.
seo-title: Classifying Traits with a Common Taxonomy
solution: Audience Manager
title: Eigenschappen classificeren met een gemeenschappelijke taxonomie
uuid: 2e177344-07d9-40a7-8c99-c6c6518b9d97
feature: Traits
exl-id: 59000dc7-66cf-4e7e-8e9b-9d48157203bd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '370'
ht-degree: 3%

---

# Eigenschappen classificeren met een gemeenschappelijke taxonomie {#classifying-traits-with-a-common-taxonomy}

Dit artikel biedt een algemeen overzicht van het classificeren van kenmerken met een gemeenschappelijke taxonomie.

## De Audience Manager Taxonomie

<!-- c_common_taxonomy_about.xml -->

De [!DNL Audience Manager] taxonomie is een optionele functie waarmee kenmerken worden geclassificeerd volgens uniforme, logische en algemeen begrepen naamconventies. Het werkt op platformniveau om de consistentie van namen in de gehele [!DNL Audience Manager] ecosysteem. Uiteindelijk is de gemeenschappelijke taxonomie bedoeld om ons product beter af te stemmen op de industrienormen inzake privacy en opt-out.

## Voordelen van de Trait-classificatie

Het is van essentieel belang dat onze klanten aangepaste segmenten en gegevensmodellen kunnen maken [!DNL Audience Manager] model en uw mogelijkheid om waarde vast te leggen vanaf ons platform. Wat ook wordt vereist, echter, is een robuust en scalable middel om informatie over segmenten aan uw klanten en partners mee te delen. Bovendien vereist deze mededeling dat de segmentinformatie in een makkelijk te begrijpen en universeel begrepen taal wordt gedeeld terwijl het beschermen van uw merkgebonden eigenschap en segmentnamen. De [!DNL Audience Manager] de gemeenschappelijke taxonomie verstrekt deze taal en vermogen.

## De taxonomie gebruikt industriestandaard classificatiecategorieën

De gemeenschappelijke taxonomie is gebaseerd op de classificaties die door de [!DNL Interactive Advertising Bureau (IAB)]. Zie de [!DNL IAB]s [website](https://www.iab.net/iab_products_and_industry_services/508676/ne_guidelines) voor meer informatie over richtsnoeren voor kwaliteitsborging voor netwerken en uitwisselingen.

## Taxonomische organisatie

De [!DNL Audience Manager] taxonomie organiseert gegevens in geneste categorieën, lagen genaamd. Elke categorie kan maximaal drie verschillende lagen bevatten voor gegevensclassificatie. Op het hoogste niveau groepeert een categorie van Tier 1 gegevens in de meest algemene vorm (bv. geografie). Opeenvolgende lagen zorgen voor meer specificiteit ten opzichte van het hogere niveau, de algemene categorie (bv. *geografie —> Verenigde Staten —> New York*). Niet elke categorie heeft echter drie lagen, sommigen slechts 2.

## Verrichtingen in gegevenscategorieën classificeren

U wijst taxonomische classificaties toe wanneer u eigenschappen maakt of bewerkt in het dialoogvenster [!UICONTROL Add New Trait Wizard] (bevindt zich in * **[!UICONTROL Audience Data > Traits]***). Zie de [documentatie over het maken van eigenschappen](../../features/traits/create-onboarded-rule-based-traits.md) voor meer informatie .

## Werken met de taxonomie: Aanvullende overwegingen

Als u besluit om eigenschappen volgens onze gemeenschappelijke taxonomie te classificeren, is het belangrijk om te herinneren:

* Classificatie is *optioneel*.
* Treinen *zijn* die standaard aan een taxonomische categorie zijn toegewezen (d.w.z. dat de kenmerken niet als &quot;onbekend&quot; of &quot;niet-gecategoriseerd&quot; enz. worden geclassificeerd).
* Treinen kunnen behoren tot *één* alleen taxonomische categorieën (meervoudige en kruiscategorieclassificaties zijn niet toegestaan).
