---
description: In de Bouwer van de Bestemming, bevat de sectie van de Configuratie het Domein van de Koek en publiceert Gegevens aan gebieden. Hiermee kunt u regels maken om te bepalen of een doel een cookie instelt of een cookie retourneert. Cookie-domein en publicatiegegevens om onafhankelijk van elkaar te werken en zijn optioneel. U kunt een koekjesbestemming tot stand brengen zonder één van beiden van hen te gebruiken.
seo-description: In de Bouwer van de Bestemming, bevat de sectie van de Configuratie het Domein van de Koek en publiceert Gegevens aan gebieden. Hiermee kunt u regels maken om te bepalen of een doel een cookie instelt of een cookie retourneert. Cookie-domein en publicatiegegevens om onafhankelijk van elkaar te werken en zijn optioneel. U kunt een koekjesbestemming tot stand brengen zonder één van beiden van hen te gebruiken.
seo-title: Optionele instellingen voor cookiebestemmingen
solution: Audience Manager
title: Optionele instellingen voor cookiebestemmingen
feature: Destination Basics
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '461'
ht-degree: 6%

---


# Optionele instellingen voor cookiebestemmingen {#optional-settings-cookies}

In [!UICONTROL Destination Builder], [!UICONTROL Configuration section] bevat het de [!UICONTROL Cookie Domain] en [!UICONTROL Publish Data To] gebieden. Hiermee kunt u regels maken om te bepalen of een doel een cookie instelt of een cookie retourneert. [!UICONTROL Cookie Domain] en [!UICONTROL Publish Data To] werken onafhankelijk van elkaar en zijn optioneel. U kunt een koekjesbestemming tot stand brengen zonder één van beiden van hen te gebruiken.

## Cookie-domein: Syntaxis en voorbeelden {#cookie-domain-syntax}

<!-- cookie-destination-options.xml -->

<table id="table_4F4F7562AFEE49F8917AAE5712B5CCE4"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Cookie-domein </th> 
   <th colname="col2" class="entry"> Beschrijving </th> 
  </tr>
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p><b>Syntaxis</b> </p> </td> 
   <td colname="col2"> <p>Het veld <span class="wintitle"> Koekjesdomein</span> accepteert een eenvoudige tekstreeks waarmee u cookies kunt instellen voor een bepaald domein of voor alle domeinen. Wanneer u deze functie gebruikt: </p> <p> 
     <ul id="ul_473CB59F2C0C4B358201BE5C8B27D73D"> 
      <li id="li_4E7F4691C1B54415963F7D5AA1558C9A">Stel slechts één domein in voor elk cookiedoel. Typ geen meerdere domeinen in het veld <span class="wintitle"> Koekjesdomein</span> . Maak in plaats hiervan een ander <span class="wintitle"> doel</span> . </li> 
      <li id="li_AEBF5C5F3C264C5EA4A2A6063C3F377D">Gebruik geen jokertekens. </li> 
     </ul> </p> <p> Laat het veld <span class="wintitle"> Koekjesdomein</span> leeg om een cookie in te stellen op alle domeinen. Dit is de standaardinstelling. </p> <p>Cookies instellen op een specifiek domein en subdomeinen: </p> <p> 
     <ul id="ul_F25BC0D8C40641A2A5CA338E5C258435"> 
      <li id="li_E236D8DEE4F24F9BBA36074F7049C12C">Typ de naam van het domein in het veld <span class="wintitle"> Koekjesdomein</span> . </li> 
      <li id="li_0471C198EE344DE5963A3C2F70B9E78B">Start de domeinnaam met een punt. Bijvoorbeeld, <code> .somedomain.com</code>. </li> 
      <li id="li_73D06F2BEF45487280C2245E1F6B8ED0">Het <code> https://www</code> voorvoegsel is niet vereist. </li> 
     </ul> </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p><b>Voorbeeld</b> </p> </td> 
   <td colname="col2"> <p>Als eenvoudig voorbeeld, zeggen wij een fictieve plaats genoemd sport.com. Sports.com heeft domeinen voor golf, honkbal, en voetbal. Als u een cookie in alle sportdomeinen wilt instellen, typt u dat in het vak <span class="wintitle"> Koekjesdomein</span> , zoals hieronder wordt weergegeven: </p> <p> <img src="assets/sports-domain.png" id="image_8883477BB3B543648C97A441AD34C6DE" /> </p> <p>Dit vertelt <span class="keyword"> Audience Manager</span> om een koekje in om het even welk domein te plaatsen dat patroon <code><i>something</i></code>.sport.com bevat. Zie hieronder voor een complexere reeks voorbeelden. </p> </td> 
  </tr> 
 </tbody> 
</table>

### Complexe voorbeelden van cookie-domeinen

Deze voorbeelden tonen u als een koekje zal plaatsen op hoe de [!DNL Audience Manager] [!UICONTROL Cookie Domain] optie wordt gevormd.

<table id="table_3A7B9479CDA6493FA8104D8D9841E914"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Website </th> 
   <th colname="col2" class="entry">Cookie-domein: .sport.com <p>Cookie-set </p> </th> 
   <th colname="col3" class="entry">Cookie-domein: .golf.sport.com <p>Cookie-set </p> </th> 
   <th colname="col4" class="entry">Cookie-domein: Leeg <p>Cookie-set </p> </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <b>sport.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nee </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>golf.sport.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Ja </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>honkbal.sport.com</b> </p> </td> 
   <td colname="col2"> Ja </td> 
   <td colname="col3"> Nee </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <b>sport.golf.com</b> </p> </td> 
   <td colname="col2"> Nee </td> 
   <td colname="col3"> Nee </td> 
   <td colname="col4"> Ja </td> 
  </tr> 
 </tbody> 
</table>

## Gegevens publiceren naar {#publish-data-to}

De [!UICONTROL Publish Data To] instellingen retourneren een cookie als het domein voldoet aan de criteria die zijn ingesteld door de opties die u selecteert. De volgende opties zijn beschikbaar:

* **[!UICONTROL All of our domains]**: (Standaard) Geeft een waarde [!DNL cookie] voor een willekeurig domein.
* **[!UICONTROL Only the selected domains]**: Retourneert alleen een cookie voor de domeinen die in de lijst met domeinen zijn geselecteerd.
* **[!UICONTROL All of our domains except the selected domains]**: Hiermee voorkomt u dat geselecteerde domeinen een [!DNL cookie]. Alle andere domeinen kunnen een [!DNL cookie].

>[!MORELIKETHIS]
>
>* [Een doel voor cookies maken](../../features/destinations/create-cookie-destination.md)