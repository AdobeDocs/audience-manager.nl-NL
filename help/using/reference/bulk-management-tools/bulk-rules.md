---
description: De aantekenwerkbladen maken en bijwerken accepteren een header traitRule waarmee u meerdere regels in één bewerking kunt toepassen. Volg deze instructies om bulkregelverzoeken te maken.
seo-description: The create and update worksheets accept a traitRule header that lets you apply multiple rules in a single operation. Follow these instructions to make bulk rule requests.
seo-title: Create or Update Trait Rules and Segment Rules
solution: Audience Manager
title: Regels en segmentregels voor eigenschappen maken of bijwerken
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
source-git-commit: bd1ad233dd69bc8683731d0c63dc3fb74ef91ade
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# Regels en segmentregels voor eigenschappen maken of bijwerken{#create-or-update-trait-rules-and-segment-rules}

De aantekenwerkbladen maken en bijwerken accepteren een header traitRule waarmee u meerdere regels in één bewerking kunt toepassen. Volg deze instructies om bulkregelverzoeken te maken.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) toegewezen in de [!DNL Audience Manager] UI wordt gerespecteerd in [!UICONTROL Bulk Management Tools].

## Werken met tekenregels {#trait-rules}

In uw aantekenvel, keert de de regelkolom van de eigenschap terug en keurt regels goed die uit uitdrukkingen Van Boole, vergelijkingsexploitanten, en regelmatige uitdrukkingen bestaan. U kunt regels maken met de functie Tandbeeld of Segmentbuilder in [!DNL Audience Manager] en kopieert u deze naar uw werkblad. Of, als u met regelsyntaxis vertrouwd bent, kunt u uitdrukkingen direct in aantekenvellen schrijven.

## Voorbeeld van een regelbouwer {#rule-builder-example}

Neem een voorbeeld dat aantoont hoe te om te gebruiken [!UICONTROL Segment Builder] om een regel tot stand te brengen kunt u aan het bulkaantekenvel. Nochtans, is dit geen reeks geleidelijke instructies voor die hulpmiddelen. In plaats daarvan beginnen we met een eenvoudige regel die al is gemaakt. Voor instructies over hoe te om de regelbouwers te gebruiken zie [Segment Builder](../../features/segments/segment-builder.md) en [Trait Builder](../../features/traits/about-trait-builder.md).

Met de visuele regelbouwer, hebben wij een segmentregel met 3 eigenschappen en een Van Boole gecreeerd [!UICONTROL AND] operator.

![](assets/visualrule.png)

Klikken **[!UICONTROL Code View]** om de tekstversie van deze regel op te halen.

>[!TIP]
>
>Klikken **[!UICONTROL Validate Expression]** om uw regellogica te controleren. Zo voorkomt u dat een ongeldige regel wordt geüpload.

![](assets/coderule.png)

Plak de lijn in de [!UICONTROL Bulk Management Tools] werkblad en verbind uw veranderingen aan de regels van het updatesegment bulksgewijs.

![](assets/segmentrule.png)

## Uw eigen regels maken {#create-rules}

U kunt uw eigen regels schrijven buiten [!UICONTROL Rule Builder]. Lees voordat u begint de documentatie over bijvoorbeeld operatoren, expressies en vereiste variabelen. We raden u aan het volgende te controleren:

* [Werken met vergelijkingsoperatoren in Trait Builder](../../features/traits/trait-comparison-operators.md)
* [Volgorde van de werkzaamheden](../../features/traits/trait-operator-precedence.md)
* [Voorvoegselvereisten voor belangrijke variabelen](../../features/traits/trait-variable-prefixes.md)
* [Voorbeeldexpressies met booleaanse en vergelijkingsoperatoren](../../features/traits/trait-expression-samples.md)
