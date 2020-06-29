---
description: In dit artikel worden de naamconventies beschreven die door de toetsvariabele in een sleutelwaardepaar worden gebruikt.
seo-description: In dit artikel worden de naamconventies beschreven die door de toetsvariabele in een sleutelwaardepaar worden gebruikt.
seo-title: Naam vereisten voor belangrijkste variabelen
solution: Audience Manager
title: Naam vereisten voor belangrijkste variabelen
uuid: fa72e732-895d-4cf6-bea0-66b404c2b059
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '124'
ht-degree: 0%

---


# Naam vereisten voor belangrijkste variabelen {#name-requirements-for-key-variables}

In dit artikel worden de naamconventies beschreven die door de toetsvariabele in een sleutelwaardepaar worden gebruikt.

## Naamgevingsvereisten voor sleutels

<!-- c_tb_key_name_requirements.xml -->

In [!UICONTROL Expression Builder], kan de naam van een zeer belangrijke variabele in een zeer belangrijk-waardepaar uit om het even welk aantal cijfers bestaan dat door 1 (of meer) letters, een streepje, een onderstrepingsteken, en extra cijfers wordt gevolgd.

* Geldige sleutelnamen: `price123`, `123price`, `price-123`, `c_price123`.

* Ongeldige sleutelnamen: `123`, `price!123`.

## Hoofdvariabelen vooraf bepalen met `c_`

Het `c_` voorvoegsel is *altijd* vereist als de parameters die gegevens verzenden over een gebeurtenisaanroep-URL die syntaxis gebruiken.