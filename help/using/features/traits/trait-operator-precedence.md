---
description: Trait Builder evalueert expressies volgens de onderstaande volgorde van bewerkingen, van hoge tot lage prioriteit. Trait-elementen die worden gedefinieerd door operatoren met een hoge prioriteit worden eerst geëvalueerd, vóór andere operatoren met voorrang. Deze sectie rangschikt elke exploitant volgens belangrijkheid, van hoog aan laag.
seo-description: Trait Builder evalueert expressies volgens de onderstaande volgorde van bewerkingen, van hoge tot lage prioriteit. Trait-elementen die worden gedefinieerd door operatoren met een hoge prioriteit worden eerst geëvalueerd, vóór andere operatoren met voorrang. Deze sectie rangschikt elke exploitant volgens belangrijkheid, van hoog aan laag.
seo-title: Bewerkingsvolgorde in Eigenschapbuilder
solution: Audience Manager
title: Bewerkingsvolgorde in Eigenschapbuilder
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '207'
ht-degree: 9%

---


# Bewerkingsvolgorde in Eigenschapbuilder {#order-of-operations-in-trait-builder}

[!UICONTROL Trait Builder] evalueert expressies volgens de onderstaande volgorde van bewerkingen, van hoge tot lage prioriteit. Trait-elementen die worden gedefinieerd door operatoren met een hoge prioriteit worden eerst geëvalueerd, vóór andere operatoren met voorrang. Deze sectie rangschikt elke exploitant volgens belangrijkheid, van hoog aan laag.

<!-- c_tb_operator_precedence.xml -->

<table id="table_F0FA45B652C7464B90D35526817110FF"> 
 <thead> 
  <tr> 
   <th colname="col1" class="entry"> Operatorprioriteit </th> 
   <th colname="col2" class="entry"> Symbool </th> 
   <th colname="col3" class="entry"> Opmerkingen </th> 
  </tr> 
 </thead>
 <tbody> 
  <tr> 
   <td colname="col1"> Haakje </td> 
   <td colname="col2"> ( ) </td> 
   <td colname="col3"> Expressies tussen haakjes worden altijd eerst geëvalueerd en volgen de prioriteitsvolgorde. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Vergelijkingsoperatoren </td> 
   <td colname="col2"> &lt; &gt; &lt;= &gt;= </td> 
   <td colname="col3"> Vervolgens wordt minder dan, groter dan, kleiner dan/gelijk aan, groter dan/gelijk aan geëvalueerd. </td> 
  </tr> 
  <tr> 
   <td colname="col1"> Gelijkheidsoperatoren </td> 
   <td colname="col2"> == != </td> 
   <td colname="col3"> Gelijk aan, niet gelijk aan worden geëvalueerd na de vorige exploitanten. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Booleaanse <span class="wintitle"> EN</span> </td> 
   <td colname="col2"><span class="wintitle"> AND</span> </td> 
   <td colname="col3" morerows="1"> n.v.t. </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OF</span> </td> 
   <td colname="col3" morerows="1"> n.v.t. </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [Werken met Booleaanse expressies (AND, OR, NOT) in TraitBuilder](../../reference/boolean-expressions-tsb.md)
>* [Werken met vergelijkingsoperatoren in TraitBuilder](../../features/traits/trait-comparison-operators.md)

