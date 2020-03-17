---
description: In dit artikel worden de vergelijkingsoperatoren beschreven die door Trait Builder worden gebruikt.
seo-description: In dit artikel worden de vergelijkingsoperatoren beschreven die door Trait Builder worden gebruikt.
seo-title: Werken met vergelijkingsoperatoren in Trait Builder
solution: Audience Manager
title: Werken met vergelijkingsoperatoren in Trait Builder
uuid: 41bec3b3-e5df-4a6f-abb0-80ce4c75f5e7
translation-type: tm+mt
source-git-commit: d6abb45fa8b88248920b64db3ac4e72c53ecee13

---


# Werken met vergelijkingsoperatoren in Trait Builder {#working-with-comparison-operators-in-trait-builder}

In dit artikel worden de vergelijkingsoperatoren beschreven die door [!UICONTROL Trait Builder]worden gebruikt.

## Doel van de vergelijkingsoperatoren

<!-- c_tb_comparison_operators.xml -->

Vergelijkingsoperatoren (of relationele operatoren) worden gebruikt om de relatie tussen verschillende waarden te vergelijken, te testen of te evalueren. In [!UICONTROL Trait Builder], wanneer het bouwen van signaalregels, laten de vergelijkingsexploitanten u de verhouding tussen verschillende zeer belangrijke-waardeparen testen. U kunt bijvoorbeeld een signaalregel maken om een publiek voor dure camerakoppen te definiëren. In dit geval kunt u een camera/prijs-sleutelwaardepaar maken en een gebruiker kwalificeren als deze naar een camera heeft gezocht met een prijs die gelijk is aan of hoger is dan een ingestelde hoeveelheid.

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

## Benoemde operatoren

U kunt regels maken met de volgende benoemde operatoren:

| Operator | Evalueert naar [!DNL True] Wanneer |
|---|---|
| **[!UICONTROL Contains]** | De waarde in een sleutelwaardepaar *bevat* tekens die door deze operator worden opgegeven. |
| **[!UICONTROL Matcheswords]** | De waarde in een sleutelwaardepaar *komt overeen met* het patroon dat door deze operator is opgegeven. |
| **[!UICONTROL Startswith]** | De waarde in een sleutelwaardepaar *begint met* tekens die door deze operator worden opgegeven. |
| **[!UICONTROL Endswith]** | De waarde in een sleutelwaardepaar *eindigt met* de tekens die door deze operator worden opgegeven. |
| **[!UICONTROL Matchesregex]** | De waarde in een sleutelwaardepaar *komt overeen met* het patroon dat door een reguliere expressie wordt opgegeven. [Leer meer](../../features/traits/trait-builder-regex.md) over het gebruik van reguliere expressies in [!UICONTROL Trait Builder]. |

>[!MORELIKETHIS]
>
>* [Booleaanse expressies in Trait and Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [Booleaanse expressies begrijpen in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Orde van Verrichtingen in Uitdrukkingen TraitBuilder](../../features/traits/trait-operator-precedence.md)
>* [Voorbeeldexpressies met Booleaanse en vergelijkingsoperatoren](../../features/traits/trait-expression-samples.md)

