---
description: Met de gereedschappen voor bulkbeheer kunt u meerdere objecten tegelijk maken en beheren met één bewerking. U kunt Bulk de Hulpmiddelen van het Beheer gebruiken om met gegevensbronnen, afgeleide signalen, bestemmingen, omslagen, segmenten, en trekken te werken.
keywords: basam;BAAAM;download, baam
seo-description: The Bulk Management Tools let you create and manage multiple objects at once with single operation. You can use Bulk Management Tools to work with data sources, derived signals, destinations, folders, segments, and traits.
seo-title: Getting Started With Bulk Management
solution: Audience Manager
title: Aan de slag met Bulk Management
uuid: 4bc6ae0a-315c-4ce7-a68e-cc0c6c6aa2f1
feature: BAAAM
exl-id: 5603146e-7172-4181-90ad-4606129176dd
source-git-commit: 0c9c333f4e8d6d416d497f336e3e447e2e251d47
workflow-type: tm+mt
source-wordcount: '715'
ht-degree: 0%

---


# Aan de slag met Bulk Management{#getting-started-with-bulk-management}

Met [!DNL Bulk Management Tools] kunt u meerdere objecten tegelijk maken en beheren met één bewerking. U kunt [!DNL Bulk Management Tools] gebruiken om met [!UICONTROL data sources], [!UICONTROL derived signals], [!UICONTROL destinations], [!UICONTROL folders], [!UICONTROL models], [!UICONTROL segments] en [!UICONTROL traits] te werken.

>[!IMPORTANT]
>
>De Bulk Management Tools zijn geen officieel ondersteunde Adobe-aanbieding. Problemen oplossen en support via de klantenservice worden per geval behandeld.

<!-- 

c_bulk_start.xml

 -->

>[!NOTE]
>
>[ RBAC groepstoestemmingen ](../../features/administration/administration-overview.md) die in het [!DNL Audience Manager] gebruikersinterface worden toegewezen worden in [!UICONTROL Bulk Management Tools] gerespecteerd.

## Overzicht {#overview}

Deze functie gebruikt een [!DNL Microsoft Excel] -werkblad met macro&#39;s die beveiligde, geverifieerde aanroepen van de [!DNL Audience Manager] API&#39;s uitvoeren. De API biedt de methoden en services waarmee u bulksgewijs wijzigingen kunt aanbrengen. U hoeft niet te weten hoe u code kunt schrijven of met onze API&#39;s kunt werken om deze te gebruiken. Het werkblad bevat kolomkoppen en -tabbladen die specifieke functies voor bulkwijzigingen uitvoeren. Als u bulksgewijs wijzigingen wilt aanbrengen, voegt u alleen de vooraf gedefinieerde kopteksten toe aan specifieke werkbladen, geeft u de informatie op die u bulksgewijs wilt wijzigen en klikt u op een actieknop. Het werkblad en de API&#39;s doen de rest van het werk voor u.

## Downloaden {#download}

Download het recentste aantekenvel **[hier](assets/BAAAM_V2_20210609.xlsm)** (laatst bijgewerkt in Juni 2021).

## Vereisten {#prereqs}

U hebt het volgende nodig om [!DNL Bulk Management Tools] te gebruiken:

* Uw [!DNL Experience Cloud] -aanmelding. Als klant hebt u deze gegevens al.
* Het werkblad [!DNL Bulk Management Tools] . [ Download het aantekenvel ](assets/BAAAM_V2_20210609.xlsm) om de recentste versie te krijgen.
* [!DNL Microsoft Excel] wordt uitgevoerd op 64-bits [!DNL Microsoft Windows] . We raden u aan de nieuwste versie van [!DNL Microsoft Excel] te gebruiken. De Bulk Management Tools worden niet ondersteund op [!DNL macOS] .
* Wanneer het openen van het aantekenvel, moet u **Macro&#39;s** voor [!DNL Bulk Management Tools] toelaten om te werken.

## Verificatievereisten en opties {#auth-reqs}

Bulkwijzigingen vereisen verificatie. Voordat u een handeling kunt uitvoeren, moet u zich aanmelden. Omdat het aantekenvel API vraag maakt, moet u het vormen om in uw gebruikersrekening voor authentiek te verklaren.

**API authentificatievereisten**

De tweede versie van [!DNL Bulk Management Tools], die in oktober 2019 is uitgebracht, vereenvoudigt het verificatieproces. De verificatiestappen in deze versie worden hieronder beschreven:

1. Open het werkblad en navigeer naar het **[!UICONTROL Config]** -werkblad.
2. Voer de stappen uit die in het werkblad worden beschreven.
   ![](assets/baaam-authentication.png)
3. Nadat u de stappen hebt uitgevoerd, kunt u bulksgewijs wijzigingen aanbrengen.

Bij het aanbrengen van bulkveranderingen, zult u nog moeten bevestigen dat u gemachtigd bent om de veranderingen aan te brengen, maar API authentificatie is automatisch.

**de authentificatieopties van het Domein**

De authentificatie van het domein geeft u de optie om bulkverzoeken te testen of hen rechtstreeks op uw productierekening toe te passen. Het aanbrengen van grote wijzigingen in de bètaomgeving heeft geen invloed op uw productieaccount. Productieveranderingen zijn onmiddellijk van kracht. Met het bulkbeheerblad kunt u in de volgende omgevingen werken:

* Beta
* Productie

## Handelingen en handelingen {#actions-ops}

Het werkblad van [!UICONTROL Bulk Management Tools] bestaat uit verificatieknoppen, tabbladen voor handelingen, actieknoppen en een tabblad **[!UICONTROL Headers]** . Het tabblad **[!UICONTROL Headers]** bevat de vooraf opgemaakte kolomkoppen die worden gebruikt door de tabbladen voor handelingen. De handelingstabellen bevatten macro&#39;s die de geselecteerde bulkbewerking uitvoeren. Als u een bulkbewerking wilt uitvoeren, kopieert u een reeks kopteksten naar het juiste handelingstabblad, voert u koptekstgegevens in en klikt u op een actieknop.

Na [ het voor authentiek verklaren ](#auth-reqs), klik een actieknoop om begonnen te worden.

![](assets/baaam-worksheet.png)

In de onderstaande tabel staan de bewerkingen die u kunt uitvoeren en items die u kunt bewerken met de werkbladen van [!UICONTROL Bulk Management Tools] .

<table id="table_B9B3E09B692E42BAA52FB32C18B00709"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Handelingen </th> 
   <th colname="col2" class="entry"> Objecten </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p>De bulkacties verschijnen in lusjes bij de bodem van het aantekenvel en omvatten: </p> <p> 
     <ul id="ul_49F46B9E00C045D29E40258EB7BDCFBB"> 
      <li id="li_193C41EA19EF4D738FBA037D2BF9B05C">Verzoeken </li> 
      <li id="li_5BE2E13D839F4958AAA5C01B7EFC5096">Bijwerken </li> 
      <li id="li_4CCCC739795945DF8C89787F9A67EB88">Maken </li> 
      <li id="li_C7D36D2BDF0448CEAF3A5EABE41038E8">Schatting </li> 
      <li id="li_07A3E94326124A3092362D9896EB7732">Verwijderen </li> 
     </ul> </p> </td> 
   <td colname="col2"> <p>De voorwerpen u in bulk kunt veranderen worden gevestigd onder <b><span class="uicontrol"> Kopballen </span></b> tabel en omvatten: </p> <p> 
     <ul id="ul_A7A96F2B1B63430B9A1E1184AC5FA8F2"> 
      <li id="li_E3D9E2E190B04BE685337AC6140C371C"> <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> Gegevensbronnen </a> </li> 
      <li id="li_B645385E40684FA28770913EAF18CB2C"> <a href="../../features/derived-signals.md"> Afgeleide signalen </a> </li> 
      <li id="li_9059F8C4A41A410899BDEFC76D3F5949"> <a href="../../features/destinations/destinations.md"> Doelen </a> </li> 
      <li> <a href="../../features/algorithmic-models/understanding-models.md"> Modellen </a> </li> 
      <li id="li_BB5A445150754E53AA38C78461326932"> <a href="../../features/traits/trait-storage.md#trait-storage"> Mappen </a> en segmentmappen overtrekken </li> 
      <li id="li_7A27DBF64E0945CF8AE8C96E8C6EDA09"> <a href="../../features/segments/segments-purpose.md"> Segmenten </a> </li> 
      <li id="li_A4640A34930040DEA8555EAF0AE2A702"> <a href="../../features/traits/trait-details-page.md"> Traits </a> </li> 
     </ul> </p> </td> 
  </tr> 
 </tbody> 
</table>

**Bulk verrichtingsvoorbeeld**

Laten we bijvoorbeeld eens kijken hoe u meerdere kenmerken tegelijk kunt maken. Om veelvoudige eigenschappen in een bulkverrichting tot stand te brengen zou u:

1. Klik op de tab **[!UICONTROL Headers]** en kopieer alle labels onder de optie [!UICONTROL Create a Trait] .
2. Klik op de tab **[!UICONTROL Create]** en plak de labels vanaf rij 1, kolom A.
3. Geef informatie over elke kolomkop op en klik op **[!UICONTROL Create Traits]** . Deze actie zet u ertoe aan om uw authentificatie te bevestigen. De bulktaak wordt uitgevoerd nadat u uw verificatie hebt bevestigd. Controleer de linkerbenedenhoek van het werkblad voor een bericht over de taakstatus.


>[!NOTE]
>
>Als u met grote aanvragen werkt, reageert het werkblad mogelijk niet meer en lijkt het inactief te zijn. Laat het in deze gevallen alleen maar. Het aantekenvel zal ontvankelijk worden wanneer het bulkverzoek volledig is. Als het aantekenvel niet voor een lange periode antwoordt, zie de [ het oplossen van problemensectie ](../../reference/bulk-management-tools/bulk-troubleshooting.md).
