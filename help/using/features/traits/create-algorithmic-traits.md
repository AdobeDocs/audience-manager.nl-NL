---
description: Beschrijft opstellingsstappen en eigenschappen uniek aan het algoritmische proces van de karakterverwezenlijking.
seo-description: Beschrijft opstellingsstappen en eigenschappen uniek aan het algoritmische proces van de karakterverwezenlijking.
seo-title: Algoritmische eigenschappen maken
solution: Audience Manager
title: Algoritmische eigenschappen maken
uuid: 50c2d2d1-f412-479b-bb70-4f139429c388
feature: Traits
translation-type: tm+mt
source-git-commit: dfb0191e3ea6f6c360991a2012a15570b5cab771
workflow-type: tm+mt
source-wordcount: '322'
ht-degree: 5%

---


# Algoritmische eigenschappen maken {#create-algorithmic-traits}

<!-- t_algo_trait_build.xml -->

Als u een algoritmische eigenschap wilt maken, gaat u naar [!UICONTROL Traits] en volgt u de onderstaande stappen:

1. Klik **[!UICONTROL Create New Trait]** en selecteer **[!UICONTROL Algorithmic]** van het drop-down menu.
1. In de sectie [Basisinformatie](../../features/traits/create-onboarded-rule-based-traits.md)
   * Geef de eigenschap een naam.
   * Selecteer een gegevensbron.
   * Kies een opslagmap.
1. Breid [!UICONTROL Configuration] ruit uit en klik **[!UICONTROL Browse All Models]**.
Hierdoor wordt een nieuw venster geopend waarin u het model kunt selecteren dat u met de eigenschap wilt gebruiken.
1. Selecteer een model en klik **[!UICONTROL Add Selected Model to Trait]**.
Wanneer u het model toevoegt, worden de bereik- en nauwkeurigheidsinstellingen weergegeven.
1. Selecteer als doel bereik of nauwkeurigheid en kies een waarde in de desbetreffende vervolgkeuzemenu&#39;s. Klik **[!UICONTROL Save]** wanneer gereed.

## Configuratie-instellingen voor Algorithmic Traits {#configure-settings}

In [!UICONTROL Trait Builder], laat de [!UICONTROL Configuration] sectie u een algoritmisch model aan een eigenschap associëren. Als u het proces voor het maken van algoritmische kenmerken wilt voltooien, selecteert u een model en kiest u een doel voor bereik of nauwkeurigheid.

### Vereisten

<!-- r_algo_trait_config_section.xml -->

* [Een look-alike-model maken](../../features/algorithmic-models/create-model.md).
* Wacht op het bericht-e-mail die u laat weten dat de modelgegevens zijn uitgevoerd.
* Vul de vereiste velden in de sectie [Basisinformatie](../../features/traits/create-onboarded-rule-based-traits.md) in.

### Configuratievelden en -instellingen

| Interface-element | Toelichting |
|---|---|
| **[!UICONTROL Select Model for Algorithmic Trait]** | Klik op de knop **[!UICONTROL Update]** om het venster Modellen te openen. Selecteer in het venster het algoritmische model dat u wilt gebruiken om de eigenschap te maken. |
| **[!UICONTROL Select Goal Accuracy]** | Selecteer deze optie om een eigenschap op basis van nauwkeurigheid te maken. Nauwkeurigheid is een gecodeerde waarde die aangeeft hoe dicht potentiële gebruikers zich bij de basislijn bevinden. De nauwkeurigheidsschaal loopt van 0 (minst nauwkeurig) tot en met 1 (meest nauwkeurig). |
| **[!UICONTROL Reach and Accuracy Data Columns]** | Rechts in deze sectie worden maximaal 21 rijen numerieke gegevens weergegeven die de waarden voor nauwkeurigheid en bereik van het model weergeven. |
| **[!UICONTROL Reach and Accuracy Slider]** | Onder aan de grafiek ziet u de schuifregelaar waarmee u een numerieke waarde kunt instellen voor het bereiken of de nauwkeurigheidsdoelen. U kunt de schuifregelaar instellen en vervolgens de knop voor het doel van het bereik of de nauwkeurigheid kiezen om een kenmerk te maken. |

>[!MORELIKETHIS]
>
>* [Nauwkeurigheid en bereik](../../features/traits/trait-accuracy-reach.md)

