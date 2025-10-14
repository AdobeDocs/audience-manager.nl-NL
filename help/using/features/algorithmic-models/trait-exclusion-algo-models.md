---
description: De Uitsluiting van het spoor verstrekt extra controles in uw modelleringswerkschema, die u toestaan om de noodzakelijke beschermingen aan het model toe te voegen, op uw domeindeskundigheid en regelgevende vereisten wordt gebaseerd. Met de optie Uitzonderingen kunt u selecteren welke kenmerken u wilt negeren bij het maken van modellen uit een of meer gegevensbronnen.
seo-description: Trait Exclusion provides additional controls in your modeling workflow, allowing you to add the necessary guard rails to the model, based on your domain expertise and regulatory requirements. Use the Exclusions option to select which traits to ignore when creating models from one or more data sources.
seo-title: Algorithmic Models  Trait Exclusion
title: Algorithmic Models Trait Exclusion
uuid: 1359800b-6e6c-41e1-88b4-23d31952abb3
feature: Algorithmic Models
exl-id: 7e2df04d-7e07-408d-b82a-9571b5839ff4
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '633'
ht-degree: 0%

---

# look-Alike modellering: Trait Exclusion {#algorithmic-models-trait-exclusion}

[!UICONTROL Trait Exclusion] biedt extra besturingselementen in uw modelleringsworkflow, zodat u de benodigde beveiligingsrails aan het model kunt toevoegen op basis van uw expertise op het domein en uw vereisten op het gebied van regelgeving. Gebruik de optie [!UICONTROL Exclusions] om aan te geven welke kenmerken moeten worden genegeerd bij het maken van modellen uit een of meer gegevensbronnen.

## Gevallen gebruiken {#use-cases}

Hier volgen enkele gebruiksgevallen die u kunt aanpakken met [!UICONTROL Trait Exclusion] :

* Met [!UICONTROL Trait Exclusion] kunt u bepaalde algemene kenmerken uitsluiten, zoals bezoekerskenmerken van de site, zodat u het model niet kunt beïnvloeden. Dit leidt tot vlakke resultaten.
* U kunt kenmerken verwijderen die u niet kent of die u niet vertrouwt van een gegevensbron, om de invloedrijke kenmerken beter te begrijpen.
* U kunt bepaalde kenmerken, zoals demografische kenmerken, uitsluiten om u te helpen aan eventuele nalevingsverplichtingen te voldoen.

>[!IMPORTANT]
>
>Een belangrijke opmerking over het derde geval van gebruik. Als de derdegegevensleverancier een nieuw demografisch bezit aan de gegevensvoer *toevoegt nadat u het model* creeerde, wordt het bezit automatisch opgenomen door het model. U kunt kenmerken niet uitsluiten van modellering nadat u het model hebt gemaakt. Zie [&#x200B; Belangrijke Aspecten &amp; Beperkingen &#x200B;](../../features/algorithmic-models/trait-exclusion-algo-models.md#important-aspects-and-limitations). Wees voorzichtig bij het gebruik van deze functie en werk met de gegevensaanbieder om ervoor te zorgen dat u op de hoogte bent van wijzigingen in de voederstructuur.

![](assets/lam_exclude_traits.png)

## Uitsluitingen trace gebruiken {#how-to-use}

Gebruik [&#x200B; bouwt een model &#x200B;](../../features/algorithmic-models/create-model.md#build-model) werkschema om nieuwe algoritmische modellen te bouwen.

1. De selectie van [!UICONTROL Exclusions] wordt grijs weergegeven totdat u een of meer gegevensbronnen selecteert voor modellering.
2. Druk op **[!UICONTROL Browse All Traits]** nadat u een of meer gegevensbronnen voor modellering hebt geselecteerd.
3. In het venster **[!UICONTROL Select Traits to Exclude]** ziet u alle kenmerken die zijn gekoppeld aan de gegevensbronnen die u eerder hebt geselecteerd. Selecteer de kenmerken die u wilt uitsluiten.
4. U kunt de eigenschappen filtreren door type van het dienstreis, type van de trekpopulatie ([&#x200B; identiteitskaart van het Apparaat &#x200B;](../../reference/ids-in-aam.md) en [&#x200B; identiteitskaart van het dwars-Apparaat &#x200B;](../../reference/ids-in-aam.md)), of u kunt de trekkeromslagen doorbladeren. Merk op dat de reisomslagen slechts de eigenschappen tonen verbonden aan uw geselecteerde gegevensbronnen.
5. Druk op **[!UICONTROL Exclude Selected Traits]**.

![&#x200B; eigenschap-uitsluitingen &#x200B;](assets/trait-exclusions-browse-traits.png)

>[!TIP]
>
>U kunt volledige mappen uitsluiten door de mapkenmerken uit te sluiten in plaats van de kenmerken in de map één voor één uit te sluiten. In een map met 20 kenmerken hoeft u bijvoorbeeld alleen de mapkenmerken uit te sluiten in plaats van alle kenmerken één voor één uit te sluiten.

Bekijk onze videodemo voor Trait Exclusion als u liever videozelfstudies wilt:

>[!VIDEO](https://video.tv.adobe.com/v/25569/?quality=12)

Bekijk de video hieronder voor een gedetailleerde uitleg van de werking van maateenheden op verschillende apparaten.

>[!VIDEO](https://video.tv.adobe.com/v/33445/?quality=12)

## Belangrijke aspecten en beperkingen {#important-aspects-and-limitations}

Houd rekening met de volgende aspecten en beperkingen met betrekking tot [!UICONTROL Trait Exclusion] :

<table id="table_BA5C3545BC9E4717BD567B00C803AA53"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Item </th> 
   <th colname="col2" class="entry"> Beschrijving </th>
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>Uitgesloten traits in Modellen - overzichtsweergave </p> </td>
   <td colname="col2"> <p>De uitgesloten sporen <i> verschijnen niet omhoog </i> in de Samenvattingsmening van Modellen. U kunt de uitgesloten kenmerken alleen zien in de <b><span class="uicontrol"> workflow Model bewerken </span></b> . </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Rolgebaseerde toegangscontroles (RBAC) </p> </td>
   <td colname="col2"> <p>Houd rekening met de volgende beperkingen voor bedrijven die <a href="../../features/administration/administration-overview.md#administration"> RBAC </a> gebruiken: </p> <p>
     <ul id="ul_38A4056C235B428C822EA4A353893786"> 
      <li id="li_2624FB35581F4807B8530910D63FFDBF">Als u geen toegang hebt om een bezit te bekijken, kunt u <i> niet </i> selecteren dat spoor om van het model worden uitgesloten. </li>
      <li id="li_3FD7A12AAAA8462EA84A760C05F20379">Als u geen toegang hebt om een bezit te bekijken, kunt u <i> niet </i> bekijken dat het bezit in de uitgesloten lijst van trekkingen. </li>
     </ul> </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uitgesloten kenmerken wijzigen na opslaan van model </p> </td>
   <td colname="col2"> <p>U kunt de uitgesloten kenmerken niet wijzigen nadat u een model hebt gemaakt en opgeslagen. Als u de resultaten wilt aanpassen, kunt u het model klonen en de uitgesloten kenmerken wijzigen. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Maximumaantal kenmerken dat u kunt uitsluiten </p> </td>
   <td colname="col2"> <p>Het maximumaantal kenmerken dat u van een model kunt uitsluiten, is 500. Gebruik mappenkenmerken om uw uitsluitingen te maximaliseren. </p> </td>
  </tr> 
  <tr> 
   <td colname="col1"> <p>Uitsluiten van basislijnkenmerk </p> </td>
   <td colname="col2"> <p>De basislijneigenschap wordt standaard uitgesloten, zodat deze niet wordt weergegeven in de lijst <b><span class="uicontrol"> Uitsluitingen </span></b> bij het maken van het model. </p> </td>
  </tr>
 </tbody>
</table>

Bekijk de onderstaande video om te leren hoe en waarom u specifieke kenmerken wilt uitsluiten van een [!UICONTROL Look-Alike Model] .

>[!VIDEO](https://video.tv.adobe.com/v/25569/)

## Verwante koppelingen

* [Algorithmic Traits](/help/using/features/algorithmic-models/understanding-models.md)
* [&#x200B; Uitsluiting van het Beetje - Leerprogramma &#x200B;](https://helpx.adobe.com/audience-manager/kt/using/excluding-traits-look-alike-model-feature-video-use.html)
