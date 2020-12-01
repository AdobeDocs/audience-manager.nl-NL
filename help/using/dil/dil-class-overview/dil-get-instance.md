---
description: Hiermee wordt een partnerspecifieke DIL-instantie opgehaald.
keywords: audience manager api;aam api;audience manager apis;aam apis
seo-description: Hiermee wordt een partnerspecifieke DIL-instantie opgehaald.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '73'
ht-degree: 6%

---


# getDil{#getdil}

Hiermee wordt een partnerspecifieke DIL-instantie opgehaald.

**Functiehandtekening:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameters

| Naam | Type | Beschrijving |
|---|---|---|
| `partner` | String | De partnernaam aan onderzoek naar. |
| `containerNSID` | Geheel | Standaardwaarden is `0`. NSID van de container u zoekt naar. Optioneel. |

## Antwoord

Een succesvolle partner en container NSID keert een partner-specifieke [!UICONTROL DIL] instantie terug. Als er geen overeenkomst is, keert API (veroorzaakt niet) een fout met het bericht terug, &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Voorbeeldcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
