---
description: In dit artikel worden de naamconventies beschreven die door de toetsvariabele in een sleutelwaardepaar worden gebruikt.
seo-description: This article describes the naming conventions used by the key variable in a key-value pair.
seo-title: Name Requirements for Key Variables
solution: Audience Manager
title: Naamvereisten voor belangrijke variabelen
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
exl-id: 5d1e5842-bebc-4d75-958f-078ba0061dfa
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '104'
ht-degree: 9%

---

# Naamvereisten voor belangrijke variabelen {#name-requirements-for-key-variables}

In dit artikel worden de naamconventies beschreven die door de toetsvariabele in een sleutelwaardepaar worden gebruikt.

## Naamgevingsvereisten voor sleutels

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], kan de naam van een zeer belangrijke variabele in een zeer belangrijk-waardepaar uit om het even welk aantal cijfers bestaan dat door 1 (of meer) letters, een streepje, een onderstrepingsteken, en extra cijfers wordt gevolgd.

* Geldige sleutelnamen: `price123`, `123price`, `price-123`, `c_price123`.

* Ongeldige sleutelnamen: `123`, `price!123`.

## Hoofdvariabelen vooraf bepalen met `c_`

De `c_` prefix is *altijd* vereist als de parameters die gegevens verzenden over een gebeurtenisaanroep-URL die syntaxis gebruiken.
