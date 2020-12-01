---
description: Gebruik logische operatoren om sleutelwaardeparen en terugvullingskenmerken te groeperen.
seo-description: Gebruik logische operatoren om sleutelwaardeparen en terugvullingskenmerken te groeperen.
seo-title: Ondersteunde logische operatoren
title: Ondersteunde logische operatoren
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '164'
ht-degree: 5%

---


# Ondersteunde logische operatoren {#supported-logical-operators}

Gebruik logische operatoren om sleutelwaardeparen en terugvullingskenmerken te groeperen.

## Ondersteunde operatoren voor signaalzoekopdrachten {#supported-operators-search}

Gebruik de volgende ondersteunde logische operatoren om te zoeken naar sleutelwaardeparen:

### Vergelijkingsoperatoren

| Operator | Definitie |
|---|---|
| **==** | Gelijk aan |
| **>** | Groter dan |
| **&lt;>** | Minder dan |
| **=>** | Groter dan/gelijk aan |
| **&lt;>** | Kleiner dan/gelijk aan |

### Benoemde operatoren

| Operator | Evalueert naar [!DNL True] Wanneer |
|---|---|
| **[!UICONTROL Contains]** | De waarde in een sleutel-waardepaar *bevat* karakters die door deze exploitant worden gespecificeerd. |
| **[!UICONTROL Startswith]** | De waarde in een sleutelwaardepaar *begint met* karakters die door deze exploitant worden gespecificeerd. |
| **[!UICONTROL Endswith]** | De waarde in een key-value paar *eindigt met* de tekens die door deze operator zijn opgegeven. |

## Ondersteunde operatoren voor traitback-up en schatting {#supported-operators-backfilling}

U kunt terugvullingseigenschappen die uitdrukkingen omvatten die om het even welke exploitanten bevatten die door [!UICONTROL Signal Search] worden gesteund. Naast deze operatoren ondersteunen terugvullen en schatten van de eigenschap ook de logische operatoren [!UICONTROL AND], [!UICONTROL OR] en [!UICONTROL AND NOT] die worden gebruikt om sleutelwaardeparen te combineren binnen de opgevulde standaardexpressies.