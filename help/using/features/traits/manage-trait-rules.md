---
description: In Trait Builder kunt u met Expression Builder regels maken en testen die kwalificatievereisten voor het publiek vaststellen. Regels bestaan uit sleutelwaardeparen zoals "color == blue" of "price &gt; 100". Vergelijkingsoperatoren bepalen de relatie tussen sleutels en waarden. Booleaanse expressies bepalen de relatie tussen regelgroepen.
seo-description: In Trait Builder, the Expression Builder lets you create and test rules that establish audience qualification requirements. Rules consist of key-value pairs such as "color == blue" or "price &gt; 100". Comparison operators establish the relationship between keys and values. Boolean expressions determine the relationship between rule groups.
seo-title: Managing Trait Rules
solution: Audience Manager
title: Trait-regels beheren
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
exl-id: 4561b19a-bbb5-41ec-ac79-ab3e2ab75548
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '678'
ht-degree: 0%

---

# Trait-regels beheren {#managing-trait-rules}

In [!UICONTROL Trait Builder] kunt u met [!UICONTROL Expression Builder] regels maken en testen die kwalificatievereisten voor het publiek vastleggen. Regels bestaan uit sleutel-waardeparen zoals `color == blue` of `price > 100` . Vergelijkingsoperatoren bepalen de relatie tussen sleutels en waarden. [!DNL Boolean] -expressies bepalen de relatie tussen regelgroepen.

<!-- c_tb_rules.xml -->

## Belangrijkste kenmerken van signaalregels beschreven

![](assets/manage-trait-rules.png)

1. De tabbladen **[!UICONTROL Expression Builder]** of **[!UICONTROL Code View]** bieden een overzicht van de regels in uw kenmerk. Met het tabblad **[!UICONTROL Expression Builder]** kunt u regels maken met velden en vervolgkeuzemenu&#39;s. Met **[!UICONTROL Code View]** kunt u regels maken door die expressies handmatig als code te schrijven. In de bovenstaande afbeelding ziet u een eenvoudig kenmerk dat bestaat uit een signaal dat gegevens evalueert voor een in aanmerking komende voorwaarde waarbij een productsleutel gelijk is aan een specifieke waarde, in dit geval `color == "blue"` .

1. Met de velden en besturingselementen in deze sectie kunt u signalen van sleutelwaardeparen maken en de relatie tussen deze velden en een vergelijkingsoperator instellen. Er zijn een sleutel, operator en waarde vereist.
1. Met de [!UICONTROL Data Explorer Options] kunt u de realisaties van de eigenschap voor uw signalen terugvullen.

   >[!NOTE]
   >
   >Deze optie is alleen beschikbaar voor [!UICONTROL Data Explorer] -klanten. Neem contact op met uw Adobe-consultant voor meer informatie.

1. In deze sectie ziet u een schatting van de resultaten van de afgelopen 7 dagen voor de signalen die zijn gedefinieerd in de [!UICONTROL Expression Builder] , voor teruggevulde en niet-teruggevulde kenmerken.

   >[!NOTE]
   >
   >Deze optie is alleen beschikbaar voor [!UICONTROL Data Explorer] -klanten. Neem contact op met uw Adobe-consultant voor meer informatie.

1. Met de testvelden kunt u combinaties van signaalregels of de [!DNL URL] s valideren die u wilt gebruiken wanneer u gegevens naar Audience Manager verzendt.

## Een regel voor overtrekken maken {#create-trait-rule}

Regels (of expressies) bestaan uit afzonderlijke of groepen sleutelwaardeparen. Vergelijkingsoperatoren stellen de relatie in tussen sleutelwaardeparen. Als u een regel wilt maken, geeft u een sleutel, een waarde, selecteert u een operator en klikt u op **[!UICONTROL Add Rule]** .

<!-- t_tb_create_rules.xml -->

Voltooi de vereiste gebieden in de **[!UICONTROL Basic Information]** sectie *alvorens* het creëren van trekregels.

1. Vouw de sectie **[!UICONTROL Trait Expression]** uit en voer een sleutel- en waardenaam in. Hiermee maakt u een *`signal`* .

   >[!NOTE]
   >
   >Neem het voorvoegsel `c_` (of een andere naamgevingsconventie) voor de toetsvariabele op als uw gebeurtenisaanroepen gegevens naar [!DNL Audience Manager] verzenden met behulp van die syntaxis.

1. Selecteer a [ vergelijkingsexploitant ](../../features/traits/trait-comparison-operators.md) van **[!UICONTROL Operator]** dropdown. De vergelijkingsexploitant evalueert de verhouding tussen de elementen in een signaal.

   >[!NOTE]
   >
   >De [!DNL Boolean] [!UICONTROL OR] exploitant vestigt de verhouding tussen veelvoudige signalen *binnen* een groep en kan niet worden veranderd.

1. Klik op **[!UICONTROL Add Rule]**. De opgeslagen regel wordt weergegeven in de werkruimte Kenmerken boven de velden voor gegevensinvoer.

### Voorbeeld {#example-trait-rule}

In het onderstaande voorbeeld heeft een gebruiker een nieuwe regel voor het kenmerk gemaakt op basis van de product-id. Om deze regel samen te stellen, heeft de gebruiker de sleutel `productkey` die is gekoppeld met een gelijkheidsoperator ( `==` ), opgegeven met de waarde `2093` .

![](assets/tb_sample_rule1.png)

Als u op **[!UICONTROL Add Rule]** klikt, wordt de eigenschap opgeslagen en verplaatst naar de werkruimte van [!UICONTROL Expression Builder] .

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

1. Selecteer een [!DNL Boolean] -operator ([!UICONTROL AND] , [!UICONTROL OR] , [!UICONTROL AND NOT] ) in de vervolgkeuzelijst om de relatie tussen de regelgroepen in te stellen.

## Regels verplaatsen tussen groepen {#move-rules-between-groups}

Als u een regel wilt verplaatsen, klikt u erop en sleept u deze naar een andere groep.

## Een overtrek bewerken {#edit-trait}

In deze procedure wordt beschreven hoe u een eigenschap kunt bewerken.

<!-- t_tb_edit.xml -->

1. Houd de muisaanwijzer boven de kolom [!UICONTROL Traits] in het dashboard van **[!UICONTROL Actions]** voor het kenmerk dat u wilt bewerken. Dit brengt de pictogrammen van het trekkenbeheer naar voren.
1. Klik op het potlood om de eigenschap te bewerken.

   ![](assets/tb_edit_trait.png)

## Een regel voor overtrekken verwijderen {#delete-trait}

Deze procedure beschrijft hoe te om een treklijn te schrappen.

<!-- t_tb_delete_rule.xml -->

1. Houd de aanwijzer boven de [!UICONTROL Traits] -kolommen voor het kenmerk dat u wilt bewerken in het dashboard van [!UICONTROL Actions] en klik op het potloodpictogram. Dit brengt de pictogrammen van het trekkenbeheer naar voren.
1. Vouw de sectie [!UICONTROL Trait Expression] uit.
1. Houd de cursor boven de regel die u wilt verwijderen en klik op het X-pictogram. De regel wordt onmiddellijk verwijderd.

>[!MORELIKETHIS]
>
>* [ creeer een Nieuwe Groep van de Regel ](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [ Beweeg Regels tussen Groepen ](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [ creeer een Regel van het Tpoor ](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [ Schrap een Regel van het Spoor ](../../features/traits/manage-trait-rules.md#delete-trait)
>* [ Beweeg Regels tussen Groepen ](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
