---
description: De aantekenwerkbladen maken en bijwerken accepteren een header traitRule waarmee u meerdere regels in één bewerking kunt toepassen. Volg deze instructies om bulkregelverzoeken te maken.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Regels en segmentregels voor overtrekken maken of bijwerken
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '343'
ht-degree: 1%

---

# Regels en segmentregels voor overtrekken maken of bijwerken{#create-or-update-trait-rules-and-segment-rules}

De aantekenwerkbladen maken en bijwerken accepteren een header traitRule waarmee u meerdere regels in één bewerking kunt toepassen. Volg deze instructies om bulkregelverzoeken te maken.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[&#x200B; RBAC groepstoestemmingen &#x200B;](../../features/administration/administration-overview.md) die in [!DNL Audience Manager] worden toegewezen UI wordt geëerd in [!UICONTROL Bulk Management Tools].

## Werken met tekenregels {#trait-rules}

In uw aantekenvel, keert de de regelkolom van de eigenschap terug en keurt regels goed die uit uitdrukkingen Van Boole, vergelijkingsexploitanten, en regelmatige uitdrukkingen bestaan. U kunt regels maken met de functie of segmentbuilder in [!DNL Audience Manager] en deze kopiëren naar uw werkblad. Of, als u met regelsyntaxis vertrouwd bent, kunt u uitdrukkingen direct in aantekenvellen schrijven.

## Voorbeeld van een regelbouwer {#rule-builder-example}

Neem een voorbeeld dat aantoont hoe te om [!UICONTROL Segment Builder] te gebruiken om een regel tot stand te brengen u aan het bulkaantekenvel kunt. Nochtans, is dit geen reeks geleidelijke instructies voor die hulpmiddelen. In plaats daarvan beginnen we met een eenvoudige regel die al is gemaakt. Voor instructies over hoe te om de regelbouwers te gebruiken zie [&#x200B; de Bouwer van het Segment van 0&rbrace; en &#x200B;](../../features/segments/segment-builder.md) Trait Builder [.](../../features/traits/about-trait-builder.md)

Met de visuele regelbouwer, hebben wij een segmentregel met 3 eigenschappen en een exploitant Van Boole [!UICONTROL AND] gecreeerd.

![](assets/visualrule.png)

Klik op **[!UICONTROL Code View]** om de tekstversie van deze regel op te halen.

>[!TIP]
>
>Klik op **[!UICONTROL Validate Expression]** om de logica van de regel te controleren. Zo voorkomt u dat een ongeldige regel wordt geüpload.

![](assets/coderule.png)

Plak de regel in het werkblad van [!UICONTROL Bulk Management Tools] en wijs uw wijzigingen toe om segmentregels bulksgewijs bij te werken.

![](assets/segmentrule.png)

## Uw eigen regels maken {#create-rules}

U kunt uw eigen regels buiten [!UICONTROL Rule Builder] schrijven. Lees voordat u begint de documentatie over bijvoorbeeld operatoren, expressies en vereiste variabelen. We raden u aan het volgende te controleren:

* [&#x200B; het Werken met vergelijkingsexploitanten in Trait Builder &#x200B;](../../features/traits/trait-comparison-operators.md)
* [&#x200B; Orde van Verrichtingen &#x200B;](../../features/traits/trait-operator-precedence.md)
* [Voorvoegselvereisten voor belangrijke variabelen](../../features/traits/trait-variable-prefixes.md)
* [Voorbeeldexpressies met Booleaanse en vergelijkingsoperatoren](../../features/traits/trait-expression-samples.md)
