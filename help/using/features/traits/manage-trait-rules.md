---
description: In Trait Builder kunt u met Expression Builder regels maken en testen die kwalificatievereisten voor het publiek vaststellen. Regels bestaan uit sleutelwaardeparen zoals "color == blue" of "price &gt"; 100". Vergelijkingsoperatoren bepalen de relatie tussen sleutels en waarden. Booleaanse expressies bepalen de relatie tussen regelgroepen.
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: Eigenschapregels beheren
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '677'
ht-degree: 1%

---

# Eigenschapregels beheren {#managing-trait-rules}

In [!UICONTROL Trait Builder]de [!UICONTROL Expression Builder] Hiermee kunt u regels maken en testen die kwalificatievereisten voor het publiek vastleggen. Regels bestaan uit sleutelwaardeparen, zoals `color == blue` of `price > 100`. Vergelijkingsoperatoren bepalen de relatie tussen sleutels en waarden. [!DNL Boolean] expressies bepalen de relatie tussen regelgroepen.

<!-- c_tb_rules.xml -->

## Belangrijkste kenmerken van signaalregels beschreven

![](assets/manage-trait-rules.png)

1. De **[!UICONTROL Expression Builder]** of **[!UICONTROL Code View]** tabs geven een overzicht van de regels in uw kenmerk. De **[!UICONTROL Expression Builder]** kunt u regels maken met velden en vervolgkeuzemenu&#39;s. De **[!UICONTROL Code View]** Hiermee kunt u regels maken door die expressies handmatig als code te schrijven. In de bovenstaande afbeelding ziet u een eenvoudig kenmerk dat bestaat uit een signaal dat gegevens evalueert voor een in aanmerking komende voorwaarde waarbij een productsleutel gelijk is aan een specifieke waarde, in dit geval `color == "blue"`.

1. Met de velden en besturingselementen in deze sectie kunt u signalen van sleutelwaardeparen maken en de relatie tussen deze velden en een vergelijkingsoperator instellen. Er zijn een sleutel, operator en waarde vereist.
1. De [!UICONTROL Data Explorer Options] staat u toe om het bezit van het terugvullingsbezit voor uw signalen.

   >[!NOTE]
   >
   >Deze optie is alleen beschikbaar voor [!UICONTROL Data Explorer] klanten. Neem contact op met uw Adobe consultant voor meer informatie.

1. In deze sectie ziet u een schatting van de resultaten van de afgelopen 7 dagen voor de signalen die zijn gedefinieerd in het dialoogvenster [!UICONTROL Expression Builder], voor teruggevulde en niet-teruggevulde kenmerken.

   >[!NOTE]
   >
   >Deze optie is alleen beschikbaar voor [!UICONTROL Data Explorer] klanten. Neem contact op met uw Adobe consultant voor meer informatie.

1. Met de testvelden kunt u combinaties van signaalregels of de [!DNL URL]is die u wilt gebruiken wanneer het verzenden van gegevens naar Audience Manager.

## Een overtrekregel maken {#create-trait-rule}

Regels (of expressies) bestaan uit afzonderlijke of groepen sleutelwaardeparen. Vergelijkingsoperatoren stellen de relatie in tussen sleutelwaardeparen. Als u een regel wilt maken, typt u een sleutel, een waarde, selecteert u een operator en klikt u op **[!UICONTROL Add Rule]**.

<!-- t_tb_create_rules.xml -->

Vul de vereiste velden in het dialoogvenster **[!UICONTROL Basic Information]** sectie *voor* regels voor kenmerken maken.

1. Breid uit **[!UICONTROL Trait Expression]** en voert u een sleutel- en waardenaam in. Hiermee maakt u een *`signal`*.

   >[!NOTE]
   >
   >Inclusief de `c_` prefix (of een andere naamgevingsconventie) voor een toetsvariabele als uw gebeurtenisaanroep gegevens verzendt naar [!DNL Audience Manager] die syntaxis gebruiken.

1. Selecteer een [vergelijkingsoperator](../../features/traits/trait-comparison-operators.md) van de **[!UICONTROL Operator]** vervolgkeuzelijst. De vergelijkingsexploitant evalueert de verhouding tussen de elementen in een signaal.

   >[!NOTE]
   >
   >De [!DNL Boolean] [!UICONTROL OR] exploitant vestigt de verhouding tussen veelvoudige signalen *binnen* een groep en kan niet worden gewijzigd.

1. Klik op **[!UICONTROL Add Rule]**. De opgeslagen regel wordt weergegeven in de werkruimte Kenmerken boven de velden voor gegevensinvoer.

### Voorbeeld {#example-trait-rule}

In het onderstaande voorbeeld heeft een gebruiker een nieuwe regel voor het kenmerk gemaakt op basis van de product-id. Om deze regel te bouwen, verstrekte de gebruiker de sleutel `productkey` gekoppeld aan een equals operator ( `==`) aan de waarde `2093`.

![](assets/tb_sample_rule1.png)

Klikken **[!UICONTROL Add Rule]** slaat de eigenschap op en verplaatst deze naar de [!UICONTROL Expression Builder] werkruimte.

![](assets/tb_sample_rule2.png)

## Nieuwe regelgroep maken {#create-rule-group}

Deze procedure beschrijft hoe te om een nieuwe regelgroep tot stand te brengen.

<!-- t_tb_new_rule_group.xml -->

Uw eigenschap moet minstens twee regels bevatten alvorens u een nieuwe regelgroep kunt tot stand brengen.

1. Plaats de cursor op de regel die u wilt verplaatsen om deze te markeren.
1. Houd de cursor boven de gemarkeerde rand van de regel.

   Hierdoor wordt de regel automatisch gescheiden van de huidige groep en verplaatst naar een nieuwe groep.

   >[!NOTE]
   >
   >Sleep een regel terug naar de oorspronkelijke groep als u deze onbedoeld verplaatst.

1. Selecteer een [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) in het keuzemenu om de relatie tussen de regelgroepen in te stellen.

## Regels verplaatsen tussen groepen {#move-rules-between-groups}

Als u een regel wilt verplaatsen, klikt u erop en sleept u deze naar een andere groep.

## Een overtrek bewerken {#edit-trait}

In deze procedure wordt beschreven hoe u een eigenschap kunt bewerken.

<!-- t_tb_edit.xml -->

1. In de [!UICONTROL Traits] dashboard, aanwijzen boven de **[!UICONTROL Actions]** voor de eigenschap die u wilt bewerken. Dit brengt de pictogrammen van het trekkenbeheer naar voren.
1. Klik op het potlood om de eigenschap te bewerken.

   ![](assets/tb_edit_trait.png)

## Een regel voor overtrekken verwijderen {#delete-trait}

Deze procedure beschrijft hoe te om een treklijn te schrappen.

<!-- t_tb_delete_rule.xml -->

1. In de [!UICONTROL Traits] dashboard, aanwijzen boven de [!UICONTROL Actions] kolommen voor de eigenschap u wilt uitgeven en het potloodpictogram klikken. Dit brengt de pictogrammen van het trekkenbeheer naar voren.
1. Vouw de sectie [!UICONTROL Trait Expression] uit.
1. Houd de cursor boven de regel die u wilt verwijderen en klik op het X-pictogram. De regel wordt onmiddellijk verwijderd.

>[!MORELIKETHIS]
>
>* [Nieuwe regelgroep maken](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Regels verplaatsen tussen groepen](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Een overtrekregel maken](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Een regel voor overtrekken verwijderen](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Regels verplaatsen tussen groepen](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

