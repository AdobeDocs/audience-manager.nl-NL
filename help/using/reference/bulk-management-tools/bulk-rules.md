---
description: De aantekenwerkbladen maken en bijwerken accepteren een header traitRule waarmee u meerdere regels in één bewerking kunt toepassen. Volg deze instructies om bulkregelverzoeken te maken.
seo-description: De aantekenwerkbladen maken en bijwerken accepteren een header traitRule waarmee u meerdere regels in één bewerking kunt toepassen. Volg deze instructies om bulkregelverzoeken te maken.
seo-title: Regels en segmentregels voor eigenschappen maken of bijwerken
solution: Audience Manager
title: Regels en segmentregels voor eigenschappen maken of bijwerken
uuid: bdd5f8f1-bb83-4844-b681-654e45ace3e1
feature: BAAAM
exl-id: 9b697606-5534-4e6e-a3f2-b1a4c26bb707
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '352'
ht-degree: 10%

---

# Regels en segmentregels voor eigenschappen maken of bijwerken{#create-or-update-trait-rules-and-segment-rules}

De aantekenwerkbladen maken en bijwerken accepteren een header traitRule waarmee u meerdere regels in één bewerking kunt toepassen. Volg deze instructies om bulkregelverzoeken te maken.

<!-- 

<p>c_bulk_rules.xml </p>

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen die ](../../features/administration/administration-overview.md) zijn toegewezen in de  [!DNL Audience Manager] gebruikersinterface, worden gerespecteerd in de  [!UICONTROL Bulk Management Tools].

## Werken met tekenregels {#trait-rules}

In uw aantekenvel, keert de de regelkolom van de eigenschap terug en keurt regels goed die uit uitdrukkingen Van Boole, vergelijkingsexploitanten, en regelmatige uitdrukkingen bestaan. U kunt regels met eigenschap of segmentbouwer in [!DNL Audience Manager] tot stand brengen en hen kopiëren aan uw aantekenvel. Of, als u met regelsyntaxis vertrouwd bent, kunt u uitdrukkingen direct in aantekenvellen schrijven.

## Voorbeeld van regelbuilder {#rule-builder-example}

Neem een voorbeeld dat aantoont hoe te om [!UICONTROL Segment Builder] te gebruiken om een regel tot stand te brengen u aan het bulkaantekenvel kunt. Nochtans, is dit geen reeks geleidelijke instructies voor die hulpmiddelen. In plaats daarvan beginnen we met een eenvoudige regel die al is gemaakt. Voor instructies over hoe te om de regelbouwers te gebruiken zie [de Bouwer van het Segment](../../features/segments/segment-builder.md) en [Trait Builder](../../features/traits/about-trait-builder.md).

Met de visuele regelbouwer, hebben wij een segmentregel met 3 eigenschappen en een exploitant Van Boole [!UICONTROL AND] gecreeerd.

![](assets/visualrule.png)

Klik **[!UICONTROL Code View]** om de tekstversie van deze regel te krijgen.

>[!TIP]
>
>Klik **[!UICONTROL Validate Expression]** om uw regellogica te controleren. Zo voorkomt u dat een ongeldige regel wordt geüpload.

![](assets/coderule.png)

Plak de regel in het [!UICONTROL Bulk Management Tools] werkblad en wijs uw wijzigingen toe om segmentregels bulksgewijs bij te werken.

![](assets/segmentrule.png)

## Uw eigen regels maken {#create-rules}

U kunt uw eigen regels buiten [!UICONTROL Rule Builder] schrijven. Lees voordat u begint de documentatie over bijvoorbeeld operatoren, expressies en vereiste variabelen. We raden u aan het volgende te controleren:

* [Werken met vergelijkingsoperatoren in Trait Builder](../../features/traits/trait-comparison-operators.md)
* [Volgorde van de werkzaamheden](../../features/traits/trait-operator-precedence.md)
* [Voorvoegselvereisten voor belangrijke variabelen](../../features/traits/trait-variable-prefixes.md)
* [Voorbeeldexpressies met booleaanse en vergelijkingsoperatoren](../../features/traits/trait-expression-samples.md)
