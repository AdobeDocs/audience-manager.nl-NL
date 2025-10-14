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
source-wordcount: '533'
ht-degree: 0%

---

# Maptraits: informatie {#folder-traits-about}

Met [!UICONTROL Folder traits] kunt u kenmerken die zich in dezelfde map bevinden en alle onderliggende mappen automatisch samenvoegen tot een doelsegment.

## Voordelen van het gebruik van maptraits {#benefits}

Een [!UICONTROL folder trait] bevat alle kenmerken in een bovenliggende map en de bijbehorende onderliggende mappen. Hiermee kunt u uw gebruikers automatisch segmenteren en richten op verschillende mapniveaus. Stel dat u een mapstructuur hebt zoals:

`*` Electronics (bovenliggend item)

    `*` Laptops (onderliggend)

        `*` Merken (kleinkind)

[!UICONTROL Folder traits] kwalificeert alle gebruikers in deze mappen in een automatisch gemaakt [!DNL Electronics] [!UICONTROL Folder Trait] bestand (op basis van de naam van de bovenliggende map). En dit proces herhaalt zich terwijl u de bestandsstructuur omlaag beweegt. In dit geval worden met mapkenmerken alle gebruikers in de mappen Laptops en Groepen in automatisch gemaakte laptops [!UICONTROL Folder Trait] vastgelegd.

[!UICONTROL Folder traits] zijn selecteerbaar in segmentexpressies. Het selecteren van een [!UICONTROL folder trait] is gelijk aan het selecteren van alle kenmerken in die map en de submappen met een [!UICONTROL OR] -groep.

![](assets/folder-traits-compare-border.jpg)

## Maptraits realisatie - Recente en Frequente {#folder-traits-realization}

Het aantal frequenties van een mapkenmerk is de som van de realisaties van de kenmerken in de map en de onderliggende mappen. In de onderstaande afbeelding ziet u de kenmerken A, B en C die in de map Automobile staan. Bedenk dat elk van de kenmerken de volgende realisaties heeft:

* Trait A: 5
* Vak B: 1
* Trait C: 1

In dit geval heeft [!DNL Automobile Folder Trait] 7 realisaties.

![](assets/folder_traits_rollup_border.png)

## Maptransactierapportage {#folder-traits-reporting}

[!UICONTROL Folder traits] legt alle gebruikers vast uit de kenmerken in de mapstructuur eronder. Als u een spoor van een omslag naar een andere omslag beweegt, verspreidt de verandering zich aan onze [&#x200B; servers van de gegevensinzameling &#x200B;](../../reference/system-components/components-data-collection.md) enkel als verandering van de treklijn. De rapportage wordt in de volgende verslagperiode geactualiseerd om deze wijziging in de verslagdatumbereiken weer te geven (1, 7, 14, 30, 60, 90). De oude rapportnummers van de vorige dagen worden niet gewijzigd.

## Rolgebaseerde toegangsbeheerrechten (RBAC) {#role-based-access-controls}

Voor bedrijven die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) gebruiken, kunnen uw gebruikers met de juiste [!UICONTROL RBAC] machtigingen de gegevensbron wijzigen die aan [!UICONTROL folder trait] is gekoppeld. Een gebruiker moet tot een groep met één van beiden van het volgende behoren:

* `READ` - en `WRITE` -groepsmachtigingen voor een gegevensbron met geldige gegevens.
* `VIEW_ALL_TRAITS` en `EDIT_ALL_TRAITS` wild card permissions for trait data sources.

Leer hoe te om [!UICONTROL RBAC] toestemmingen in onze [&#x200B; beleidsdocumentatie &#x200B;](../../features/administration/administration-overview.md#create-group) toe te wijzen.

## Limieten en andere overwegingen {#limits}

| Item | Beschrijving |
|---|---|
| Type overtrek | [!UICONTROL Onboarded traits] en [!UICONTROL algorithmic traits] leveren maximaal 1 realisatie op voor de frequentie van een [!UICONTROL folder trait] . |
| Kenmerken verplaatsen tussen mappen | Als u een kenmerk van een map naar een andere map verplaatst, wordt die eigenschap van de eerste mapkenmerk uitgesloten en wordt deze voor de tweede [!UICONTROL folder trait] gekwalificeerd. Dit betekent dat als u een eigenschap verwijdert of verplaatst uit de map, de gebruikers in de populatie van het kenmerk niet zijn gesegmenteerd van de segmenten en de mapeigenschap als segmentexpressie gebruiken. <br> Als u Adobe Analytics-segmenten toewijst aan uw Experience Cloud-organisatie of deze gebruikt, maakt Audience Manager automatisch nieuwe, overeenkomende, alleen-lezen segmenten en kenmerken. U kunt de opslaglocatie van deze kenmerken niet wijzigen vanuit Audience Manager. Elke wijziging die u uitvoert op uw toegewezen Adobe Analytics-segmenten of rapportsuites, is echter ook van toepassing op Audience Manager. |
| Systeemvariabelen | [!UICONTROL Folder traits] kan niet worden uitgevoerd bij gebeurtenisaanroepen met de parameter `d_sid` . |
| Rapportage | [!UICONTROL Folder traits] zijn automatisch berekende kenmerken en worden niet weergegeven in **[!UICONTROL Overlap Reports]** . |
