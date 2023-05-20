---
description: Met mapkenmerken kunt u automatisch kenmerken die zich in dezelfde map bevinden en alle onderliggende mappen samenvoegen tot een doelsegment.
keywords: schatting van segmentgrootte;sse
seo-description: Folder traits let you automatically aggregate traits that reside within the same folder and all child folders into a targetable segment.
seo-title: Folder Traits  About
solution: Audience Manager
title: Maphandleidingen over
uuid: e561ce8f-6c90-44a7-b034-685533f29030
feature: Traits
exl-id: 779d1ab3-3a69-4975-b45a-acd95ab86a37
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '522'
ht-degree: 1%

---

# Mapeigenschappen: Info {#folder-traits-about}

[!UICONTROL Folder traits] Hiermee kunt u kenmerken die zich in dezelfde map bevinden en alle onderliggende mappen automatisch samenvoegen tot een doelsegment.

## Voordelen van het gebruik van maptraits {#benefits}

A [!UICONTROL folder trait] bevat alle kenmerken in een bovenliggende map en de bijbehorende onderliggende mappen. Hiermee kunt u uw gebruikers automatisch segmenteren en richten op verschillende mapniveaus. Stel dat u een mapstructuur hebt zoals:

`*` Elektronica (bovenliggend)

    `*` Laptops (onderliggend)

        `*` Merken (kleinkind)

[!UICONTROL Folder traits] kwalificeer alle gebruikers in deze omslagen in automatisch gecreeerd [!DNL Electronics] [!UICONTROL Folder Trait] (op basis van de naam van de bovenliggende map). En dit proces herhaalt zich terwijl u de bestandsstructuur omlaag beweegt. In dit geval worden met de mapkenmerken alle gebruikers in de mappen Laptops en Groepen van automatisch gemaakte laptops vastgelegd [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] zijn selecteerbaar in segmentexpressies. Een [!UICONTROL folder trait] is gelijk aan het selecteren van alle kenmerken in die map en de bijbehorende submappen met een [!UICONTROL OR] groeperen.

![](assets/folder-traits-compare-border.jpg)

## Maptraits realisatie - Recente en Frequente {#folder-traits-realization}

Het aantal frequenties van een mapkenmerk is de som van de realisaties van de kenmerken in de map en de onderliggende mappen. In de onderstaande afbeelding ziet u de kenmerken A, B en C die in de map Automobile staan. Bedenk dat elk van de kenmerken de volgende realisaties heeft:

* Trait A: 5
* Vak B: 1
* Vak C: 1

In dit geval worden de [!DNL Automobile Folder Trait] heeft 7 realisaties.

![](assets/folder_traits_rollup_border.png)

## Maptransactierapportage {#folder-traits-reporting}

[!UICONTROL Folder traits] leg alle gebruikers vast van de kenmerken in de mappenstructuur eronder. Als u een kenmerk van een map naar een andere map verplaatst, wordt de wijziging doorgegeven aan onze [gegevensverzamelingsservers](../../reference/system-components/components-data-collection.md) net als bij een wijziging van de gedragslijn. De rapportage wordt in de volgende verslagperiode geactualiseerd om deze wijziging in de verslagdatumbereiken weer te geven (1, 7, 14, 30, 60, 90). De oude rapportnummers van de vorige dagen worden niet gewijzigd.

## Rolgebaseerde toegangsbeheerrechten (RBAC) {#role-based-access-controls}

Voor bedrijven die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]), uw gebruikers met de aangewezen [!UICONTROL RBAC] machtigingen kunnen de gegevensbron wijzigen die is gekoppeld aan de [!UICONTROL folder trait]. Een gebruiker moet tot een groep met één van beiden van het volgende behoren:

* `READ` en `WRITE` groepsmachtigingen voor een gegevensbron met geldige gegevens.
* `VIEW_ALL_TRAITS` en `EDIT_ALL_TRAITS` jokertekens voor gegevensbronnen met geldige gegevens.

Leer hoe u kunt toewijzen [!UICONTROL RBAC] machtigingen in onze [administratie documentatie](../../features/administration/administration-overview.md#create-group).

## Limieten en andere overwegingen {#limits}

| Item | Beschrijving |
|---|---|
| Type overtrek | [!UICONTROL Onboarded traits] en [!UICONTROL algorithmic traits] maximaal 1 realisatie bijdragen tot een [!UICONTROL folder trait]De frequentie. |
| Kenmerken verplaatsen tussen mappen | Als u een kenmerk van een map naar een andere map verplaatst, wordt dat kenmerk van de eerste mapkenmerk uitgesloten en wordt het kenmerk voor de tweede map gekwalificeerd [!UICONTROL folder trait]. Dit betekent dat als u een eigenschap verwijdert of verplaatst uit de map, de gebruikers in de populatie van het kenmerk niet zijn gesegmenteerd van de segmenten en de mapeigenschap als segmentexpressie gebruiken. <br> Wanneer het in kaart brengen van de segmenten van Adobe Analytics of rapportsuites aan uw organisatie van Experience Cloud, Audience Manager automatisch tot nieuwe, overeenkomstige, read-only segmenten en eigenschappen leidt. U kunt de opslaglocatie van deze kenmerken niet bewerken of wijzigen vanuit Audience Manager. Elke wijziging die u uitvoert op uw toegewezen Adobe Analytics-segmenten of rapportsuites, wordt echter weerspiegeld in de Audience Manager. |
| Systeemvariabelen | [!UICONTROL Folder traits] kan niet worden gerealiseerd in gebeurtenisvraag gebruikend `d_sid` parameter. |
| Rapportage | [!UICONTROL Folder traits] zijn automatisch berekende kenmerken en verschijnen niet in **[!UICONTROL Overlap Reports]**. |
