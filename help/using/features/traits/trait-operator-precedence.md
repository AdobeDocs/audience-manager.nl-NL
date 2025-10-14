---
description: Trait Builder evalueert expressies volgens de onderstaande volgorde van bewerkingen, van hoge tot lage prioriteit. Trait-elementen die worden gedefinieerd door operatoren met een hoge prioriteit worden eerst geëvalueerd, vóór andere operatoren met voorrang. Deze sectie rangschikt elke exploitant volgens belangrijkheid, van hoog aan laag.
seo-description: Trait Builder evaluates expressions according to the order-of-operations listed below, from high to low precedence. Trait elements defined by high-precedence operators are evaluated first, before other precedence operators. This section ranks each operator according to precedence, from high to low.
seo-title: Order of Operations in Trait Builder
solution: Audience Manager
title: Bewerkingsvolgorde in Trait Builder
uuid: df325047-af62-45ad-9ca1-046bfcbe5341
feature: Traits
exl-id: 90700479-4a8e-4a07-81ef-2e9d8a1d9f15
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '161'
ht-degree: 0%

---

# Bewerkingsvolgorde in Trait Builder {#order-of-operations-in-trait-builder}

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
   <td colname="col1">Boolean <span class="wintitle"> EN </span> </td> 
   <td colname="col2"><span class="wintitle"> AND </span> </td> 
   <td colname="col3" morerows="1"> nvt </td> 
  </tr> 
  <tr> 
   <td colname="col1">Boolean <span class="wintitle"> OR</span> </td> 
   <td colname="col2"><span class="wintitle"> OR </span> </td> 
   <td colname="col3" morerows="1"> nvt </td> 
  </tr> 
 </tbody>
</table>

>[!MORELIKETHIS]
>
>* [&#x200B; Werkend met (EN, OF, NIET) Uitdrukkingen Van Boole in TraitBuilder &#x200B;](../../reference/boolean-expressions-tsb.md)
>* [&#x200B; Werkend met de Exploitanten van de Vergelijking in TraitBuilder &#x200B;](../../features/traits/trait-comparison-operators.md)
