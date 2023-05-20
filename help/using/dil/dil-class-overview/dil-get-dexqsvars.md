---
description: Hiermee wordt een specifieke waarde opgehaald van een advertentieserver.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '64'
ht-degree: 4%

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
| `containerNSID` | Geheel | De [!DNL NSID] van de container waarnaar u zoekt. Standaardwaarden is `0`. |

**Antwoord**

Hiermee wordt de waarde van de variabele voor een geretourneerd [!UICONTROL DIL] -instantie.

**Voorbeeldcode**

<pre class="java"><code>var value = DIL.dexGetQSVars('<i>variableName</i>','<i>partnerName</i>',<i>containerNSID</i>);</code></pre>
