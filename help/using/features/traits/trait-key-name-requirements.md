---
description: In dit artikel worden de naamconventies beschreven die door de toetsvariabele in een sleutelwaardepaar worden gebruikt.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Naam vereisten voor belangrijkste variabelen
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '105'
ht-degree: 0%

---

# Naam vereisten voor belangrijkste variabelen {#name-requirements-for-key-variables}

In dit artikel worden de naamconventies beschreven die door de toetsvariabele in een sleutelwaardepaar worden gebruikt.

## Naamgevingsvereisten voor sleutels

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], kan de naam van een zeer belangrijke variabele in een zeer belangrijk-waardepaar uit om het even welk aantal cijfers bestaan dat door 1 (of meer) letters, een streepje, een onderstrepingsteken, en extra cijfers wordt gevolgd.

* Geldige sleutelnamen: `price123`, `123price`, `price-123`, `c_price123`.

* Ongeldige sleutelnamen: `123`, `price!123` .

## Hoofdvariabelen vooraf bepalen met `c_`

Het `c_` voorvoegsel wordt *altijd* vereist als de parameters die in gegevens over een gebeurtenisvraag URL verzenden die syntaxis gebruiken.
