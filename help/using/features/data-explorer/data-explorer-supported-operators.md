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
ht-degree: 3%

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

### Benoemde operatoren

| Operator | Evalueert naar [!DNL True] Wanneer |
|---|---|
| **[!UICONTROL Contains]** | De waarde in een sleutelwaardepaar *contains* tekens die door deze operator worden opgegeven. |
| **[!UICONTROL Startswith]** | De waarde in een sleutelwaardepaar *begint met* tekens die door deze operator worden opgegeven. |
| **[!UICONTROL Endswith]** | De waarde in een sleutelwaardepaar *eindigt met* de tekens die door deze operator worden opgegeven. |

## Ondersteunde operatoren voor traitback-up en -raming {#supported-operators-backfilling}

U kunt terugvullingskenmerken gebruiken die expressies bevatten die alle operatoren bevatten die worden ondersteund door [!UICONTROL Signal Search]. Naast deze operatoren ondersteunen ook de terugvinding en de schatting van de eigenschap [!UICONTROL AND], [!UICONTROL OR], en [!UICONTROL AND NOT] logische operatoren, die worden gebruikt om sleutelwaardeparen te combineren binnen de opgevulde standaardexpressies.
