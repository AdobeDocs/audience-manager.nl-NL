---
description: Beschrijft de vereiste en facultatieve stappen die u een algoritmisch model in ModelBouwer laten tot stand brengen.
keywords: laten zien hoe werkt
seo-description: Describes the required and optional steps that let you create an algorithmic model in Model Builder.
seo-title: Create an Algorithmic Model
solution: Audience Manager
title: Een algoritmisemodel maken
uuid: ccf4fc4e-cf92-445f-b2d9-71c3ca624e26
feature: Algorithmic Models
exl-id: 8b7c4f57-f2c8-46f1-8924-5513fd6ede04
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '629'
ht-degree: 1%

---

# Een look-alike-model maken {#create-an-algorithmic-model}

Beschrijft de vereiste en facultatieve stappen die u laten tot een [!UICONTROL Look-Alike Model].

## Sectie Modelbouwer

[!UICONTROL Model Builder] bestaat uit [!UICONTROL Basic Information] en [!UICONTROL Configuration] secties. Als u een model wilt maken, vult u de vereiste velden in deze twee secties in. Sla het model op om het algoritme te starten. [!DNL Audience Manager] verzendt u een geautomatiseerd bericht nadat de eerste gegevenslooppas voltooit. Nadat u het e-mailbericht hebt ontvangen, kunt u naar [Trait Builder](../../features/traits/about-trait-builder.md) en maak algoritmische kenmerken.

>[!NOTE]
>
>* Het modelleringsproces wordt slechts eenmaal uitgevoerd als u een model maakt en er geen eigenschappen mee bouwt.
>* Bouw modellen van gegevensbronnen die een zinvolle hoeveelheid informatie bevatten. Modellen met onvoldoende gegevens worden uitgevoerd, maar er worden geen resultaten geretourneerd.
>* *Niet gebruiken* modellen maken met andere algoritmische kenmerken of segmenten.
>* Het geautomatiseerde e-mailbericht wordt slechts eenmaal verzonden (na de eerste gegevensuitvoering).


## Het model samenstellen

Volg de onderstaande stappen om een [!UICONTROL Look-Alike Model]:

1. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** en klik op **[!UICONTROL Add New]** in de [!UICONTROL Look-Alike Modeling] sectie.
   ![look-alike-add](assets/look-alike-add.png)
1. In de [Basisinformatie](../../features/algorithmic-models/create-model.md#basic-information) sectie
   * Geef het model een naam.
   * *(Optioneel)* Geef een korte beschrijving van het model op.
   * De status van het model instellen op **[!UICONTROL Active]** of **[!UICONTROL Inactive]**. Inactieve modellen worden niet uitgevoerd en produceren geen gegevens.

      ![look-alike-basic](assets/look-alike-basic.png)
1. In de [Configuratie](../../features/algorithmic-models/create-model.md#configuration) sectie:
   * Klikken **[!UICONTROL Browse All Traits]** of **[!UICONTROL Browse All Segments]** om een eigenschap of een segment te selecteren u tegen wilt modelleren. Zoek naar eigenschappen door naam, identiteitskaart, beschrijving of gegevensbron. Klik tijdens het zoeken op een map om de resultaten te beperken tot die map en de bijbehorende submappen. U kunt ook kenmerken filteren op basis van het type eigenschap ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], en [!UICONTROL Algorithmic]) of type populatie ([Apparaat-id](../../reference/ids-in-aam.md) en [Apparaatoverschrijdende id](../../reference/ids-in-aam.md)).

      ![browsereigenschappen](assets/browse-traits.png)
   * Kies een terugblik periode van 30, 60, of 90 dagen. Hiermee stelt u een tijdbereik in voor het model.
   * De [!UICONTROL TraitWeight] algoritme is standaard geselecteerd.
   * Selecteer een gegevensbron in het menu [!UICONTROL Available Data] lijst.
   * Klikken **[!UICONTROL Save]** wanneer gereed.

      ![look-alike-configuration](assets/look-alike-configuration.png)

Bekijk de onderstaande video voor een gedetailleerde uitleg van de werking van maateenheden op verschillende apparaten.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html)

## Basisinformatie voor algoritmische modellen {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder]de [!UICONTROL Basic Information] Met instellingen kunt u nieuwe modellen maken of bestaande modellen bewerken. Als u een nieuw model wilt maken, voert u een naam in en gaat u naar het [!UICONTROL Configuration] instellingen. Het beschrijvingsveld is optioneel.

| Veld | Beschrijving |
|---|---|
| **[!UICONTROL Name]** | Geef uw model een korte, logische naam die de functie of het doel ervan beschrijft. Vermijd afkortingen, speciale tekens en accenttekens. |
| **[!UICONTROL Description]** | Een veld voor aanvullende beschrijvende informatie over het model. |
| **[!UICONTROL Status]** | Hiermee activeert of deactiveert u het model (standaard geactiveerd). |

## Configuratie {#configuration}

In [!UICONTROL Model Builder]de [!UICONTROL Configuration] kunt u eigenschappen of segmenten aan het model toevoegen. Selecteer in deze sectie een basislijnkenmerk of -segment, een terugkijkperiode en gegevens uit uw eerste en andere gegevensbronnen.

<!-- r_model_configuration.xml -->

### Vereisten

Vul de vereiste velden in het dialoogvenster [!UICONTROL Basic Information] deel 1.

![](assets/lam_exclude_traits_numbered.png)

<table id="table_7A6BE5E5498D4776A30323B743954150"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Veld </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Selecteer een basislijntrack of -segment (1)</b> </p> </td> 
   <td colname="col2"> <p>Klik op het kenmerk of de segmentknop om een lijst met al uw kenmerken of segmenten weer te geven. Uw geselecteerde segment of kenmerk wordt de basislijn die de systeemalgoritmen gebruiken voor modellering. </p> <p> <p><b>Opmerking</b>: Selecteer een merkteken, een op regel gebaseerd kenmerk of een segment als basislijn. Anders worden de modellen niet uitgevoerd. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Selecteer terugkijkperiode (2)</b> </p> </td> 
   <td colname="col2"> <p>Hiermee stelt u een tijdbereik in voor het model. Gebaseerd op uw selectie, omvat het algoritme en evalueert gegevens van de vorige 30, 60, of 90 dagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Algoritme selecteren (3)</b> </p> </td> 
   <td colname="col2"> <p>Op dit moment werkt de Modelbouwer samen met onze bedrijfseigen <span class="keyword"> Dikte van spoor</span> alleen algoritme. <span class="keyword"> Audience Manager</span> kan andere algoritmische functies toevoegen in volgende versies. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b>Modelgegevens selecteren uit gegevensbron (4)</b> </p> </td> 
   <td colname="col2"> <p>Hiermee kunt u de eerste en derde gegevensbronnen selecteren die u in het model wilt gebruiken. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Uitsluitingen (5)</b> </p> </td> 
   <td colname="col2"> <p>U kunt eigenschappen uitsluiten van de gegevensbronnen die u voor modellering hebt geselecteerd. Gebruik de <span class="wintitle"> Uitsluitingen</span> lijst en lezen <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algoritmische modellen: Trait Exclusion</a> voor meer informatie. </p> </td>
  </tr> 
 </tbody>
</table>

Bekijk de onderstaande video om te leren hoe u een model maakt voor de eerste look-alike, zodat u meer van uw eigen bezoekers kunt vinden die er uitzien als uw converters.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [TraitWeight begrijpen](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)

