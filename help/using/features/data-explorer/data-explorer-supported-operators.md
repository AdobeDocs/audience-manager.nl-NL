---
description: Gebruik logische operatoren om sleutelwaardeparen en terugvullingskenmerken te groeperen.
seo-description: Gebruik logische operatoren om sleutelwaardeparen en terugvullingskenmerken te groeperen.
seo-title: Ondersteunde logische operatoren
title: Ondersteunde logische operatoren
uuid: 645fcb6f-50ac-49bc-8df9-c699c749cf8f
translation-type: tm+mt
source-git-commit: 1f26460d746a93ddc36c375360fcfbd9feb06fbb

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
| **[!UICONTROL Contains]** | De waarde in een sleutelwaardepaar *bevat* tekens die door deze operator worden opgegeven. |
| **[!UICONTROL Startswith]** | De waarde in een sleutelwaardepaar *begint met* tekens die door deze operator worden opgegeven. |
| **[!UICONTROL Endswith]** | De waarde in een sleutelwaardepaar *eindigt met* de tekens die door deze operator worden opgegeven. |

## Ondersteunde operatoren voor traitback-up en -raming {#supported-operators-backfilling}

U kunt terugvullingskenmerken gebruiken die expressies bevatten met een van de operatoren die worden ondersteund door [!UICONTROL Signal Search]. Naast deze operatoren worden ook de operatoren [!UICONTROL AND], [!UICONTROL OR]en [!UICONTROL AND NOT] logische operatoren ondersteund voor het terugvullen en schatten van sporen, die worden gebruikt om sleutelwaardeparen te combineren binnen de opgevulde standaardexpressies.