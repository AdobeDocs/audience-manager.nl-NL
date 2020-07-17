---
description: Hiermee wordt een specifieke waarde opgehaald van een advertentieserver.
seo-description: Hiermee wordt een specifieke waarde opgehaald van een advertentieserver.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 5%

---


# dexGetQSVars{#dexgetqsvars}

Hiermee wordt een specifieke waarde opgehaald van een advertentieserver.

**Functiehandtekening:** `dexGetQSVars: function (variableName, partner, containerNSID) {}`

<!-- 

r_dil_get_dexqsvars.xml

 -->

**Parameters**

| Naam | Type | Beschrijving |
|---|---|---|
| `variableName` | String | De naam van de variabele waarvoor u een waarde wilt ophalen. |
| `partner` | String | De partnernaam aan onderzoek naar. |
| `containerNSID` | Geheel | De [!DNL NSID] container waarnaar u zoekt. Standaardwaarden zijn `0`. |

**Antwoord**

Retourneert de variabele waarde voor een [!UICONTROL DIL] instantie.

**Voorbeeldcode**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
