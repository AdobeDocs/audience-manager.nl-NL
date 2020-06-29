---
description: In Trait Builder kunt u met Expression Builder regels maken en testen die kwalificatievereisten voor het publiek vaststellen. Regels bestaan uit sleutelwaardeparen zoals "color == blue" of "price > 100". Vergelijkingsoperatoren bepalen de relatie tussen sleutels en waarden. Booleaanse expressies bepalen de relatie tussen regelgroepen.
seo-description: In Trait Builder kunt u met Expression Builder regels maken en testen die kwalificatievereisten voor het publiek vaststellen. Regels bestaan uit sleutelwaardeparen zoals "color == blue" of "price > 100". Vergelijkingsoperatoren bepalen de relatie tussen sleutels en waarden. Booleaanse expressies bepalen de relatie tussen regelgroepen.
seo-title: Trait-regels beheren
solution: Audience Manager
title: Trait-regels beheren
uuid: 827d4567-2b6f-411e-bd5c-9735c916291a
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '723'
ht-degree: 0%

---


# Trait-regels beheren {#managing-trait-rules}

In [!UICONTROL Trait Builder], [!UICONTROL Expression Builder] laat u regels tot stand brengen en testen die de vereisten van de publiekskwalificatie bepalen. Regels bestaan uit sleutel-waardeparen zoals `color == blue` of `price > 100`. Vergelijkingsoperatoren bepalen de relatie tussen sleutels en waarden. [!DNL Boolean] expressies bepalen de relatie tussen regelgroepen.

<!-- c_tb_rules.xml -->

## Belangrijkste kenmerken van signaalregels beschreven

![](assets/manage-trait-rules.png)

1. De **[!UICONTROL Expression Builder]** tabbladen of **[!UICONTROL Code View]** tabbladen bieden een overzicht van de regels in uw kenmerk. Op het **[!UICONTROL Expression Builder]** tabblad kunt u regels maken met velden en vervolgkeuzemenu&#39;s. Met de code **[!UICONTROL Code View]** kunt u regels maken door die expressies handmatig als code te schrijven. In de bovenstaande afbeelding ziet u een eenvoudig kenmerk dat bestaat uit een signaal dat gegevens evalueert voor een in aanmerking komende voorwaarde waarbij een productsleutel gelijk is aan een specifieke waarde, in dit geval `color == "blue"`.

1. Met de velden en besturingselementen in deze sectie kunt u signalen van sleutelwaardeparen maken en de relatie tussen deze velden en een vergelijkingsoperator instellen. Er zijn een sleutel, operator en waarde vereist.
1. Met [!UICONTROL Data Explorer Options] deze optie kunt u de eigenschapresultaten voor uw signalen terugzetten.
   >[!NOTE]
   >
   >Deze optie is alleen beschikbaar voor [!UICONTROL Data Explorer] klanten. Neem contact op met uw Adobe-consultant voor meer informatie.
1. In deze sectie ziet u een schatting van de resultaten van de afgelopen 7 dagen voor de signalen die in de code zijn gedefinieerd, voor [!UICONTROL Expression Builder]teruggevulde en niet-teruggevulde kenmerken.
   >[!NOTE]
   >
   >Deze optie is alleen beschikbaar voor [!UICONTROL Data Explorer] klanten. Neem contact op met uw Adobe-consultant voor meer informatie.
1. Met de testvelden kunt u combinaties van signaalregels of de [!DNL URL]s valideren die u wilt gebruiken wanneer u gegevens naar de Audience Manager verzendt.

## Een overtrekregel maken {#create-trait-rule}

Regels (of expressies) bestaan uit afzonderlijke of groepen sleutelwaardeparen. Vergelijkingsoperatoren stellen de relatie in tussen sleutelwaardeparen. Als u een regel wilt maken, typt u een sleutel, een waarde, selecteert u een operator en klikt u **[!UICONTROL Add Rule]** op deze toets.

<!-- t_tb_create_rules.xml -->

Vul de vereiste velden in de **[!UICONTROL Basic Information]** sectie in *voordat* u de regels voor de eigenschap maakt.

1. Vouw de **[!UICONTROL Trait Expression]** sectie uit en voer een sleutel- en waardenaam in. Hiermee maakt u een *`signal`*.
   >[!NOTE]
   >
   >Neem het `c_` voorvoegsel (of een andere naamgevingsconventie) voor de toetsvariabele op als uw gebeurtenisaanroepen gegevens naar [!DNL Audience Manager] die syntaxis verzenden.
1. Selecteer een [vergelijkingsoperator](../../features/traits/trait-comparison-operators.md) in het **[!UICONTROL Operator]** vervolgkeuzemenu. De vergelijkingsexploitant evalueert de verhouding tussen de elementen in een signaal.
   >[!NOTE]
   >
   >De [!DNL Boolean] exploitant vestigt de verhouding tussen veelvoudige signalen [!UICONTROL OR] binnen ** een groep en kan niet worden veranderd.
1. Klik op **[!UICONTROL Add Rule]**. De opgeslagen regel wordt weergegeven in de werkruimte Kenmerken boven de velden voor gegevensinvoer.

### Voorbeeld {#example-trait-rule}

In het onderstaande voorbeeld heeft een gebruiker een nieuwe regel voor het kenmerk gemaakt op basis van de product-id. Om deze regel te bouwen, verstrekte de gebruiker de sleutel `productkey` verbonden aan een gelijkenis exploitant ( `==`) aan de waarde `2093`.
![](assets/tb_sample_rule1.png)

Klik op Opslaan **[!UICONTROL Add Rule]** en verplaatst de eigenschap naar de [!UICONTROL Expression Builder] werkruimte.

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
1. Selecteer een [!DNL Boolean] exploitant ( [!UICONTROL AND], [!UICONTROL OR], [!UICONTROL AND NOT]) van het drop-down menu om de verhouding tussen de regelgroepen te plaatsen.

## Regels verplaatsen tussen groepen {#move-rules-between-groups}

Als u een regel wilt verplaatsen, klikt u erop en sleept u deze naar een andere groep.

## Een overtrek bewerken {#edit-trait}

In deze procedure wordt beschreven hoe u een eigenschap kunt bewerken.

<!-- t_tb_edit.xml -->

1. Houd de muisaanwijzer boven de [!UICONTROL Traits] kolom voor het kenmerk dat u wilt bewerken in het **[!UICONTROL Actions]** dashboard. Dit brengt de pictogrammen van het trekkenbeheer naar voren.
1. Klik op het potlood om de eigenschap te bewerken.

   ![](assets/tb_edit_trait.png)

## Een regel voor overtrekken verwijderen {#delete-trait}

Deze procedure beschrijft hoe te om een treklijn te schrappen.

<!-- t_tb_delete_rule.xml -->

1. Houd de muisaanwijzer boven de [!UICONTROL Traits] kolommen van het te bewerken kenmerk in het [!UICONTROL Actions] dashboard en klik op het potloodpictogram. Dit brengt de pictogrammen van het trekkenbeheer naar voren.
1. Vouw de sectie [!UICONTROL Trait Expression] uit.
1. Houd de cursor boven de regel die u wilt verwijderen en klik op het X-pictogram. De regel wordt onmiddellijk verwijderd.

>[!MORELIKETHIS]
>
>* [Nieuwe regelgroep maken](../../features/traits/manage-trait-rules.md#create-rule-group)
>* [Regels verplaatsen tussen groepen](../../features/traits/manage-trait-rules.md#move-rules-between-groups)
>* [Een overtrekregel maken](../../features/traits/manage-trait-rules.md#create-trait-rule)
>* [Een regel voor overtrekken verwijderen](../../features/traits/manage-trait-rules.md#delete-trait)
>* [Regels verplaatsen tussen groepen](../../features/traits/manage-trait-rules.md#move-rules-between-groups)

