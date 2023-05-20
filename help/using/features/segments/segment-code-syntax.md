---
description: De Bouwer van het segment laat u eigenschapregels voor een segment bouwen gebruikend een coderedacteur. Klik op het tabblad Segmentexpressies (Codeweergave) in het deelvenster Vertrekken om deze functie te openen.
seo-description: Segment Builder lets you build trait rules for a segment using a code editor. Click the Segment Expressions (Code View) tab in the Traits panel to access this feature.
seo-title: Code Syntax Used in the Segment Expression Editor
solution: Audience Manager
title: Gebruikte codesyntaxis in de Segment Expression Editor
uuid: 7b4b06ca-7879-4501-8ba7-b2b6467b8a3b
feature: Segments
exl-id: 64fa6f03-cef9-4187-866f-28c54f45f72e
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '297'
ht-degree: 9%

---

# Gebruikte codesyntaxis in de Segment Expression Editor {#code-syntax-used-in-the-segment-expression-editor}

[!UICONTROL Segment Builder] Hiermee kunt u met een code-editor eigenschapsregels voor een segment maken. Klik op de knop **[!UICONTROL Segment Expressions (Code View)]** in de [!UICONTROL Traits] voor toegang tot deze functie.

## Syntaxis expressiebouwcode

In plaats van slepen- en neerzetfuncties te gebruiken, kunt u ook tekenregels toevoegen aan een segment met code. Vervang bij het coderen cursieve elementen in het voorbeeld door een werkelijke expressie of waarde. De basiscode gebruikt de volgende syntaxis:

```
FREQUENCY([<traitID1>T,<traitID2>T]<Recency Operator><Numeric Value>D)
<Frequency Operator><Numeric Value>
```

>[!NOTE]
>
>Standaard, [!DNL Boolean] [!UICONTROL OR] voorwaarden zijn van toepassing op meerdere kenmerken *binnen* een expressie.

### Segmenten samenvoegen met Booleaanse operatoren

Als u groepen segmenten wilt samenstellen, plaatst u de frequentiefunctie tussen haakjes en stelt u de relatie in *Tussen* elke expressie met een [!DNL Boolean] operator ([!UICONTROL AND], [!UICONTROL OR], en [!UICONTROL NOT]).

### Parameters

>[!NOTE]
>
>Alle parameters zijn vereist, tenzij anders vermeld.

| Naam of variabele | Beschrijving |
|---|---|
| `FREQUENCY` | Een letterlijke waarde die aan de expressie moet voorafgaan. |
| ` [`&lt;`traitID`>`T]` | Een array met referentie-id&#39;s, gevolgd door de letter `T`. Scheid meerdere kenmerken met een komma. Bijvoorbeeld, `[123T, 456T]`. |
| ` <Recency Operator><Numeric Value>D` | *(Optioneel)* Hiermee stelt u recentieregels in voor de kenmerken in het segment. De brief `D` Hiermee wordt aangegeven dat de periode in dagen recursief is. |
| ` <Frequency Operator><Numeric Value>` | Hiermee stelt u de frequentieregels voor kenmerken in het segment in. |

### Toegestane operatoren voor recentie en frequentie

Set [recentie en frequentie](../../features/segments/recency-and-frequency.md) intervallen met een vergelijkingsoperator en een geheel getal. [!UICONTROL Segment Builder] gebruikt standaardexpressies zoals &lt; (kleiner dan), > (groter dan), == (gelijk), enz. De typen toegestane operatoren variëren echter wanneer u de frequentie of de frequentie instelt. In de onderstaande tabel worden de toegestane frequentie-/recenentie-operatoren weergegeven.

<table id="table_2F92617CB472442BA5639E24DB4E43D3"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Recente operatoren </th> 
   <th colname="col2" class="entry"> Frequentieoperatoren </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> 
    <ul id="ul_66D11A34097648A997BA5C6CCC38503A"> 
     <li id="li_EA0B607E58834E62B427C0B7626C2BD1">&gt;= (groter dan/gelijk aan) </li> 
     <li id="li_CFE3D2DBEF424093A0497A70324D5B31">&lt;= (kleiner dan/gelijk aan) </li> 
    </ul> </td> 
   <td colname="col2"> 
    <ul id="ul_A5A38BCD71B844F0B5FB28256069F87E"> 
     <li id="li_EA17C353214E4C2EA2B70169C94A2E53">&gt;= (groter dan/gelijk aan) </li> 
     <li id="li_87CE5CCC6B44446BB2FD0AAD47712368">&lt;= (kleiner dan/gelijk aan) </li> 
     <li id="li_7E922AEF3A524E78A18A9F6ECBF7460B">== (gelijk aan) </li> 
    </ul> </td> 
  </tr> 
 </tbody> 
</table>

>[!MORELIKETHIS]
>
>* [Recentheid en frequentie](../../features/segments/recency-and-frequency.md)
>* [Booleaanse expressies in Trait en Segment Builder](../../reference/boolean-expressions-tsb.md)
>* [Werken met vergelijkingsoperatoren in TraitBuilder](../../features/traits/trait-comparison-operators.md)
>* [Orde van Verrichtingen in Uitdrukkingen TraitBuilder](../../features/traits/trait-operator-precedence.md)

