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
source-wordcount: '633'
ht-degree: 0%

---

# Een model maken dat lijkt op het uiterlijk {#create-an-algorithmic-model}

Beschrijft de vereiste en optionele stappen waarmee u een [!UICONTROL Look-Alike Model] kunt maken.

## Sectie Modelbouwer

[!UICONTROL Model Builder] bestaat uit de secties [!UICONTROL Basic Information] en [!UICONTROL Configuration] . Als u een model wilt maken, vult u de vereiste velden in deze twee secties in. Sla het model op om het algoritme te starten. [!DNL Audience Manager] verzendt u een geautomatiseerd bericht nadat de eerste gegevensuitvoering is voltooid. Nadat u e-mail ontvangt, kunt u naar [ Trait Builder ](../../features/traits/about-trait-builder.md) gaan en algoritmische eigenschappen tot stand brengen.

>[!NOTE]
>
>* Het modelleringsproces wordt slechts eenmaal uitgevoerd als u een model maakt en er geen eigenschappen mee bouwt.
>* Bouw modellen van gegevensbronnen die een zinvolle hoeveelheid informatie bevatten. Modellen met onvoldoende gegevens worden uitgevoerd, maar leveren geen resultaten op.
>* *creeer geen* modellen met andere algoritmische eigenschappen of segmenten.
>* Het geautomatiseerde e-mailbericht wordt slechts één keer verzonden (na de eerste gegevensuitvoering).

## Het model samenstellen

Voer de onderstaande stappen uit om een [!UICONTROL Look-Alike Model] te maken:

1. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]** en klik op **[!UICONTROL Add New]** in de sectie [!UICONTROL Look-Alike Modeling] .
   ![ blik-alike-voeg ](assets/look-alike-add.png) toe
1. In de [ Basisinformatie ](../../features/algorithmic-models/create-model.md#basic-information) sectie
   * Geef het model een naam.
   * *(Facultatief)* verstrek een korte beschrijving over het model.
   * Stel de status voor het model in op **[!UICONTROL Active]** of **[!UICONTROL Inactive]** . Inactieve modellen worden niet uitgevoerd en produceren geen gegevens.
     ![ look-alike-basic ](assets/look-alike-basic.png)
1. In de [ sectie van de Configuratie ](../../features/algorithmic-models/create-model.md#configuration):
   * Klik op **[!UICONTROL Browse All Traits]** of **[!UICONTROL Browse All Segments]** om een kenmerk of segment te selecteren waarop u wilt modelleren. Zoek naar eigenschappen door naam, identiteitskaart, beschrijving of gegevensbron. Klik tijdens het zoeken op een map om de resultaten te beperken tot die map en de bijbehorende submappen. U kunt eigenschappen door het type van het dienstreis ([!UICONTROL Folder Trait], [!UICONTROL Rule-based], [!UICONTROL Onboarded], en [!UICONTROL Algorithmic]) of bevolkingstype ([ identiteitskaart van het Apparaat ](../../reference/ids-in-aam.md) en [ identiteitskaart van het Apparaat ](../../reference/ids-in-aam.md)) ook filtreren.
     ![ doorbladeren-traits ](assets/browse-traits.png)
   * Kies een terugblik periode van 30, 60, of 90 dagen. Hiermee stelt u een tijdbereik in voor het model.
   * Het algoritme [!UICONTROL TraitWeight] is standaard geselecteerd.
   * Selecteer een gegevensbron in de lijst [!UICONTROL Available Data] .
   * Klik op **[!UICONTROL Save]** als u klaar bent.
     ![ blik-alias-configuratie ](assets/look-alike-configuration.png)

Bekijk de onderstaande video voor een gedetailleerde uitleg van de werking van maateenheden op verschillende apparaten.

>[!VIDEO](https://experienceleague.adobe.com/docs/audience-manager-learn/tutorials/build-and-manage-audiences/profile-merge/understanding-cross-device-metrics-in-audience-manager.html?lang=nl-NL)

## Basisinformatie voor algoritmische modellen {#basic-information}

<!-- r_model_basic.xml -->

In [!UICONTROL Model Builder] kunt u met de [!UICONTROL Basic Information] -instellingen nieuwe modellen maken of bestaande modellen bewerken. Als u een nieuw model wilt maken, geeft u een naam op en gaat u naar de [!UICONTROL Configuration] -instellingen. Het beschrijvingsveld is optioneel.

| Veld | Beschrijving |
|---|---|
| **[!UICONTROL Name]** | Geef uw model een korte, logische naam die de functie of het doel ervan beschrijft. Vermijd afkortingen, speciale tekens en accenttekens. |
| **[!UICONTROL Description]** | Een veld voor aanvullende beschrijvende informatie over het model. |
| **[!UICONTROL Status]** | Hiermee activeert of deactiveert u het model (standaard geactiveerd). |

## Configuratie {#configuration}

In [!UICONTROL Model Builder] kunt u met de sectie [!UICONTROL Configuration] eigenschappen of segmenten aan het model toevoegen. Selecteer in deze sectie een basislijnkenmerk of -segment, een terugkijkperiode en gegevens uit uw eerste en andere gegevensbronnen.

<!-- r_model_configuration.xml -->

### Vereisten

Vul de vereiste velden eerst in de sectie [!UICONTROL Basic Information] in.

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
   <td colname="col1"> <p><b> Uitgezocht een Beetje of Segment van de Basislijn (1) </b> </p> </td> 
   <td colname="col2"> <p>Klik op het kenmerk of de segmentknop om een lijst met al uw kenmerken of segmenten weer te geven. Uw geselecteerde segment of kenmerk wordt de basislijn die de systeemalgoritmen gebruiken voor modellering. </p> <p> <p><b> Nota </b>: Selecteer een onboard, een op regel-gebaseerd bezit, of een segment als basislijn. Anders worden de modellen niet uitgevoerd. </p> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Uitgezochte Achterperiode (2) </b> </p> </td> 
   <td colname="col2"> <p>Hiermee stelt u een tijdbereik in voor het model. Gebaseerd op uw selectie, omvat het algoritme en evalueert gegevens van de vorige 30, 60, of 90 dagen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Uitgezochte Algoritme (3) </b> </p> </td> 
   <td colname="col2"> <p>Op dit moment werkt de Modelbouwer alleen met het eigen algoritme <span class="keyword"> Dikte van de eigenschap </span> . <span class="keyword"> Audience Manager </span> kan andere algoritmische functies in verdere versies toevoegen. </p> </td>
  </tr>
  <tr> 
   <td colname="col1"> <p><b> Uitgezochte Modelgegevens van Gegevens Source (4) </b> </p> </td> 
   <td colname="col2"> <p>Hiermee kunt u de eerste en derde gegevensbronnen selecteren die u in het model wilt gebruiken. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p><b> Uitsluitingen (5) </b> </p> </td> 
   <td colname="col2"> <p>U kunt eigenschappen uitsluiten van de gegevensbronnen die u voor modellering hebt geselecteerd. Gebruik de lijst <span class="wintitle"> Uitsluitingen </span> en lees <a href="../../features/algorithmic-models/trait-exclusion-algo-models.md"> Algorithmic Models: Trait Exclusion </a> om meer te leren. </p> </td>
  </tr> 
 </tbody>
</table>

Bekijk de onderstaande video om te leren hoe u een model maakt voor de eerste look-alike, zodat u meer van uw eigen bezoekers kunt vinden die er uitzien als uw converters.

>[!VIDEO](https://video.tv.adobe.com/v/23504/)

>[!MORELIKETHIS]
>
>* [ Begrijpend TraitWeight ](../../features/algorithmic-models/understanding-models.md#understanding-traitweight)
