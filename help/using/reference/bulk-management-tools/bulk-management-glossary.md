---
description: Kolomkoplabels gedefinieerd.
seo-description: Column header labels defined.
seo-title: Bulk Management Tools Glossary
solution: Audience Manager
title: Woordenlijst voor Bulk Management Tools
uuid: 4658a6bc-9515-4d31-9715-0084760b0cea
feature: BAAAM
exl-id: 036d16c7-1546-4539-a318-455b98e10026
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '338'
ht-degree: 2%

---

# Woordenlijst voor Bulk Management Tools{#bulk-management-tools-glossary}

Kolomkoplabels gedefinieerd.

<!-- 

<p>r_bulk_glossary.xml </p>

 -->

>[!NOTE]
>
>[RBAC-groepsmachtigingen](../../features/administration/administration-overview.md) toegewezen in [!DNL Audience Manager] UI wordt gerespecteerd in [!UICONTROL Bulk Management Tools].

<table id="table_2C2BC2FB3EFC443C9A5AE18EFC6FABFD"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Kolomkop </th> 
   <th colname="col2" class="entry"> Definitie </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> dataSourceId</span> </p> </td> 
   <td colname="col2"> <p>De id van een <a href="../../features/datasources-list-and-settings.md#data-sources-list-and-settings"> gegevensbron</a> als u wilt terugkeren of in bulk wilt toewijzen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> derivedSignalId</span> </p> </td> 
   <td colname="col2"> <p>A <a href="../../features/derived-signals.md"> afgeleid signaal</a> ID. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> beschrijving</span> </p> </td> 
   <td colname="col2"> <p>Een korte, informatieve beschrijving die u aan een object kunt geven. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationId</span> </p> </td> 
   <td colname="col2"> <p>De id van de <a href="../../features/destinations/destinations.md"> doel</a> u wilt toewijzen of verwijderen. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> destinationMappingId</span> </p> </td> 
   <td colname="col2"> <p>Een speciale identiteitskaart die aan een segment wordt toegewezen wanneer het aan een bestemming wordt in kaart gebracht. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> folderId</span> </p> </td> 
   <td colname="col2"> <p>De id van het segment of de map Trait. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> name</span> </p> </td> 
   <td colname="col2"> <p>De naam van het object waarmee u werkt. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> parentFolderId</span> </p> </td> 
   <td colname="col2"> <p>De id van een segment of map trait die andere mappen bevat. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> zand</span> </p> </td> 
   <td colname="col2"> <p>Segment-id. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceKey</span> </p> </td> 
   <td colname="col2"> <p>Signalen zijn bits met gegevens die worden doorgegeven aan <span class="keyword"> Audience Manager</span> op basis van gebruikersactiviteit. Deze worden verzonden als <a href="../../reference/key-value-pairs-explained.md"> sleutelwaardeparen</a>. De bronsleutel is een constante die niet verandert. Het helpt de bronwaarde categoriseren die kan veranderen. Zie <a href="../../features/derived-signals.md"> Afgeleide signalen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> sourceValue</span> </p> </td> 
   <td colname="col2"> <p>De bronwaarde is een variabele die wordt doorgegeven als deel a <a href="../../reference/key-value-pairs-explained.md"> sleutelwaardepaar</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> startDate</span> </p> </td> 
   <td colname="col2"> <p>Geeft aan wanneer een segment naar een doel kan worden verzonden. Gebruiksmiddelen <i>jjjj-mm-dd</i> gebruiken. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetKey</span> </p> </td> 
   <td colname="col2">De sleutel die in het afgeleide signaal wordt gebruikt. Zie <a href="../../features/derived-signals.md"> Afgeleide signalen</a>. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> targetValue</span> </p> </td> 
   <td colname="col2"> <p>De waarde die met een afgeleide signaalsleutel wordt overgegaan. Zie <a href="../../features/derived-signals.md"> Afgeleide signalen</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitAlias</span> </p> </td> 
   <td colname="col2"> <p>Een id die wordt doorgegeven aan een niet-cookie-gebaseerd doel. Voor een op cookies gebaseerde bestemming is dit de sleutel in een <a href="../../reference/key-value-pairs-explained.md"> sleutelwaardepaar</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitRule / segmentRule</span> </p> </td> 
   <td colname="col2"> <p>De eigenlijke eigenschap of segmentregel die wordt gebruikt om gegevens te verzamelen. Een bulkverzoek keert de regels terug die in worden gecreeerd <span class="keyword"> Audience Manager</span> met de <a href="../../features/traits/about-trait-builder.md"> trait rule builder</a> of de <a href="../../features/segments/segment-builder.md"> segmentregelbuilder</a>. U kunt deze hulpmiddelen ook gebruiken om regels te bouwen en hen in bulk toe te passen wanneer u een segment of een eigenschap bijwerkt. </p> <p>Zie ook: <a href="../../reference/bulk-management-tools/bulk-rules.md"> Regels en segmentregels voor overtrekken maken of bijwerken</a>. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> traitType</span> </p> </td> 
   <td colname="col2"> <p>Een tekenreeks die het type eigenschap aangeeft. De volgende opties zijn beschikbaar: </p> 
    <ul id="ul_AB5B4F87B14241DCBBE44B0B7BD4EF72"> 
     <li id="li_21F9412CDDC64FAA888C6542E284C436"> <code> RULE_BASED_TRAIT</code> </li> 
     <li id="li_5A5EA9A1EC5C45C991875EBBE7979A5A"> <code> ON_BOARDED_TRAIT </code> </li> 
     <li id="li_F38B58ADE3324E97A71E3F94F11945BE"> <code> SEGMENT</code> </li> 
    </ul> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> url</span> </p> </td> 
   <td colname="col2"> <p>Pixel die door DIL in brand wordt gestoken wanneer een gebruiker voor een segment kwalificeert. </p> </td> 
  </tr> 
  <tr> 
   <td colname="col1"> <p> <span class="term"> valueAlias</span> </p> </td> 
   <td colname="col2"> <p>De toets in een <a href="../../reference/key-value-pairs-explained.md"> sleutelwaardepaar</a> doorgegeven aan een cookiebestemming. </p> </td> 
  </tr> 
 </tbody> 
</table>
