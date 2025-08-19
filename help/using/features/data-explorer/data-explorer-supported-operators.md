---
description: Gebruik logische operatoren om sleutelwaardeparen en terugvullingskenmerken te groeperen.
seo-description: Use logical operators to group key-value pairs and backfill traits.
seo-title: Supported Logical Operators
title: Ondersteunde logische operatoren
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
feature: Data Explorer
exl-id: 5e405390-1c19-4e43-b3f9-598e8aa6bd99
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '151'
ht-degree: 0%

---

# Ondersteunde logische operatoren {#supported-logical-operators}

Gebruik logische operatoren om sleutelwaardeparen en terugvullingskenmerken te groeperen.

## Ondersteunde operatoren voor Signal Search {#supported-operators-search}

Gebruik de volgende ondersteunde logische operatoren om te zoeken naar sleutelwaardeparen:

### Vergelijkingsoperatoren

| Operator | Definitie |
|---|---|
| **==** | Gelijk aan |
| **>** | Groter dan |
| **&lt;** | Minder dan |
| **=>** | Groter dan/gelijk aan |
| **&lt;=** | Kleiner dan/gelijk aan |

### Benoemde operators

| Operator | Evalueert naar [!DNL True] When |
|---|---|
| **[!UICONTROL Contains]** | De waarde in een zeer belangrijk-waardepaar *bevat* karakters die door deze exploitant worden gespecificeerd. |
| **[!UICONTROL Startswith]** | De waarde in een zeer belangrijk-waardepaar *begint met* karakters die door deze exploitant worden gespecificeerd. |
| **[!UICONTROL Endswith]** | De waarde in een zeer belangrijk-waardepaar *beëindigt met* de karakters die door deze exploitant worden gespecificeerd. |

## Ondersteunde operatoren voor traitback-up en -raming {#supported-operators-backfilling}

U kunt terugvullingskenmerken gebruiken die expressies bevatten die een van de operatoren bevatten die door [!UICONTROL Signal Search] worden ondersteund. Naast deze operatoren worden ook de logische operatoren [!UICONTROL AND] , [!UICONTROL OR] en [!UICONTROL AND NOT] voor het combineren van sleutelwaardeparen binnen de opgevulde standaardexpressies ondersteund.
