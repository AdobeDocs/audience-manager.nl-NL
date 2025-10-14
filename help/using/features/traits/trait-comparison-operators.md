---
description: In dit artikel worden de vergelijkingsoperatoren beschreven die door Trait Builder worden gebruikt.
seo-description: This article describes the comparison operators used by Trait Builder.
seo-title: Working with Comparison Operators in Trait Builder
solution: Audience Manager
title: Werken met vergelijkingsoperatoren in Trait Builder
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
feature: Traits
exl-id: 93181ca3-46c8-45ee-b0fb-da9ceec19a39
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '339'
ht-degree: 4%

---

# Werken met vergelijkingsoperatoren in Trait Builder {#working-with-comparison-operators-in-trait-builder}

In dit artikel worden de vergelijkingsoperatoren beschreven die door [!UICONTROL Trait Builder] worden gebruikt.

## Doel van de vergelijkingsoperatoren

<!-- c_tb_comparison_operators.xml -->

Vergelijkingsoperatoren (of relationele operatoren) worden gebruikt om de relatie tussen verschillende waarden te vergelijken, te testen of te evalueren. In [!UICONTROL Trait Builder] kunt u bij het samenstellen van signaalregels met vergelijkingsoperatoren de relatie tussen verschillende sleutel-waardeparen testen. U kunt bijvoorbeeld een signaalregel maken om een publiek voor dure camerakoppen te definiëren. In dit geval kunt u een camera/prijs-sleutelwaardepaar maken en een gebruiker kwalificeren als deze naar een camera heeft gezocht met een prijs die gelijk is aan of hoger is dan een ingestelde hoeveelheid.

## Voordelen van vergelijkingsoperatoren

Vergelijkingsoperatoren zijn handig wanneer u eigenschappen op basis van meerdere waarden moet evalueren en maken. Een blik op de prijzen van goederen en diensten kan deze voorwaarde illustreren. Uw bedrijf wil bijvoorbeeld bezoekers identificeren op basis van de prijzen van de producten die ze bekijken. Het kan echter administratief inefficiënt zijn om afzonderlijke segmenten te definiëren op basis van specifieke waarden. Vergelijkingsoperatoren helpen deze hindernis te overwinnen door segmentatiestribbels vast te stellen op basis van prijsdrempels of -bereiken.

## Vergelijkingsoperatoren

U kunt regels maken met de volgende vergelijkingsoperatoren:

| Operator | Definitie |
|---|---|
| **==** | Gelijk aan |
| **!=** | Niet gelijk aan |
| **>** | Groter dan |
| **&lt;** | Minder dan |
| **=>** | Groter dan/gelijk aan |
| **&lt;=** | Kleiner dan/gelijk aan |

## Benoemde operators

U kunt regels maken met de volgende benoemde operatoren:

| Operator | Evalueert naar [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | De waarde in een zeer belangrijk-waardepaar *bevat* karakters die door deze exploitant worden gespecificeerd. |
| **[!UICONTROL Matcheswords]** | De waarde in een zeer belangrijk-waardepaar *past* het patroon aan dat door deze exploitant wordt gespecificeerd. |
| **[!UICONTROL Startswith]** | De waarde in een zeer belangrijk-waardepaar *begint met* karakters die door deze exploitant worden gespecificeerd. |
| **[!UICONTROL Endswith]** | De waarde in een zeer belangrijk-waardepaar *beëindigt met* de karakters die door deze exploitant worden gespecificeerd. |
| **[!UICONTROL Matchesregex]** | De waarde in een zeer belangrijk-waardepaar *past* het patroon aan dat door een regelmatige uitdrukking wordt gespecificeerd. [&#x200B; leer meer &#x200B;](../../features/traits/trait-builder-regex.md) over het gebruiken van regelmatige uitdrukkingen in [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Booleaanse expressies in Trait en Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [&#x200B; Begrijpend de Uitdrukkingen Van Boole in TraitBuilder &#x200B;](../../reference/boolean-expressions-tsb.md)
>* [&#x200B; Orde van Verrichtingen in Uitdrukkingen TraitBuilder &#x200B;](../../features/traits/trait-operator-precedence.md)
>* [Voorbeeldexpressies met booleaanse en vergelijkingsoperatoren](../../features/traits/trait-expression-samples.md)
