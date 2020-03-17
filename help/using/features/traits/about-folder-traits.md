---
description: Met mapkenmerken kunt u automatisch kenmerken die zich in dezelfde map bevinden en alle onderliggende mappen samenvoegen tot een doelsegment.
keywords: segment size estimator;sse
seo-description: Met mapkenmerken kunt u automatisch kenmerken die zich in dezelfde map bevinden en alle onderliggende mappen samenvoegen tot een doelsegment.
seo-title: Maphandleidingen over
solution: Audience Manager
title: Maphandleidingen over
uuid: e561ce8f-6c90-44a7-b034-685533f29030
translation-type: tm+mt
source-git-commit: 9fa5a558c839da89286b1abdf77e835a92747c87

---


# Maptraits: Info {#folder-traits-about}

[!UICONTROL Folder traits] Hiermee kunt u kenmerken die zich in dezelfde map bevinden en alle onderliggende mappen automatisch samenvoegen tot een doelsegment.

## Voordelen van het gebruik van maptraits {#benefits}

Een map [!UICONTROL folder trait] bevat alle kenmerken in een bovenliggende map en de bijbehorende onderliggende mappen. Hiermee kunt u uw gebruikers automatisch segmenteren en richten op verschillende mapniveaus. Stel dat u een mapstructuur hebt zoals:

`*` Elektronica (bovenliggend)

    `*` Laptops (onderliggend)

        `*` Merken (kleinkind)

[!UICONTROL Folder traits] alle gebruikers in deze mappen kwalificeren in een automatisch gemaakt bestand [!DNL Electronics] [!UICONTROL Folder Trait] (op basis van de naam van de bovenliggende map). En dit proces herhaalt zich terwijl u de bestandsstructuur omlaag beweegt. In dit geval worden met de mapkenmerken alle gebruikers in de mappen Laptops en Groepen van automatisch gemaakte laptops vastgelegd [!UICONTROL Folder Trait].

[!UICONTROL Folder traits] zijn selecteerbaar in segmentexpressies. Het selecteren van een [!UICONTROL folder trait] submap is hetzelfde als het selecteren van alle kenmerken in die map en de submappen met een [!UICONTROL OR] groep.

![](assets/folder-traits-compare-border.jpg)

## Maptraits realisatie - Recente en Frequente {#folder-traits-realization}

Het aantal frequenties van een mapkenmerk is de som van de realisaties van de kenmerken in de map en de onderliggende mappen. In de onderstaande afbeelding ziet u de kenmerken A, B en C die in de map Automobile staan. Bedenk dat elk van de kenmerken de volgende realisaties heeft:

* Trait A: 5
* Vak B: 1
* Vak C: 1

In dit geval [!DNL Automobile Folder Trait] heeft de Commissie 7 realisaties.

![](assets/folder_traits_rollup_border.png)

## Maptransactierapportage {#folder-traits-reporting}

[!UICONTROL Folder traits] leg alle gebruikers vast van de kenmerken in de mappenstructuur eronder. Als u een eigenschap van een omslag naar een andere omslag verplaatst, verspreidt de verandering zich aan onze servers [van de](../../reference/system-components/components-data-collection.md) gegevensinzameling enkel als een verandering van de trekkerregel. De rapportage wordt in de volgende verslagperiode geactualiseerd om deze wijziging in de verslagdatumbereiken weer te geven (1, 7, 14, 30, 60, 90). De oude rapportnummers van de vorige dagen worden niet gewijzigd.

## Rolgebaseerde toegangsbeheerrechten (RBAC) {#role-based-access-controls}

Voor bedrijven die [!UICONTROL Role-Based Access Controls] ([!UICONTROL RBAC]) gebruiken, kunnen uw gebruikers met de aangewezen [!UICONTROL RBAC] toestemmingen de gegevensbron veranderen verbonden aan [!UICONTROL folder trait]. Een gebruiker moet tot een groep met één van beiden van het volgende behoren:

* `READ` en `WRITE` groepsmachtigingen aan een gegevensbron van de eigenschap.
* `VIEW_ALL_TRAITS` en `EDIT_ALL_TRAITS` jokertekenmachtigingen voor gegevensbronnen op het taakgebied.

Leer hoe u [!UICONTROL RBAC] machtigingen toewijst in onze [beheerdocumentatie](../../features/administration/administration-overview.md#create-group).

## Limieten en andere overwegingen {#limits}

| Item | Beschrijving |
|---|---|
| Type overtrek | [!UICONTROL Onboarded traits] en [!UICONTROL algorithmic traits] ten hoogste 1 realisatie aan de frequentie [!UICONTROL folder trait]van een project bijdragen. |
| Kenmerken verplaatsen tussen mappen | Als u een kenmerk van een map naar een andere map verplaatst, wordt die eigenschap niet meer in aanmerking genomen voor de eerste mapkenmerk en voor de tweede [!UICONTROL folder trait]. Dit betekent dat als u een eigenschap verwijdert of verplaatst uit de map, de gebruikers in de populatie van het kenmerk niet zijn gesegmenteerd van de segmenten en de mapeigenschap als segmentexpressie gebruiken. <br> Als u Adobe Analytics-segmenten toewijst aan uw Experience Cloud-organisatie, maakt Audience Manager automatisch nieuwe, overeenkomende, alleen-lezen segmenten en kenmerken. U kunt de opslaglocatie van deze kenmerken niet bewerken of wijzigen in Audience Manager. Elke wijziging die u uitvoert op uw toegewezen Adobe Analytics-segmenten of rapportsuites, wordt echter weerspiegeld in Audience Manager. |
| Systeemvariabelen | [!UICONTROL Folder traits] kan niet worden gerealiseerd in gebeurtenisvraag gebruikend de `d_sid` parameter. |
| Rapportage | [!UICONTROL Folder traits] zijn automatisch berekende kenmerken en worden niet weergegeven in **[!UICONTROL Overlap Reports]**. |