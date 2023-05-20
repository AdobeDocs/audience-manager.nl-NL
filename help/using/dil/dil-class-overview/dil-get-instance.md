---
description: Hiermee wordt een partnerspecifieke DIL-instantie opgehaald.
keywords: publieksmanager api;am api;publieksmanager apis;am apis
seo-description: Retrieves a partner-specific DIL instance.
seo-title: getDil
solution: Audience Manager
title: getDil
uuid: 7b95f9bf-14c0-4c74-b6b9-d6b38513d487
feature: DIL Implementation
exl-id: a1e9e715-3921-4298-bce1-5a6c2110e71b
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '77'
ht-degree: 5%

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

De succesvolle partner en de container NSID komen een partner-specifiek terug [!UICONTROL DIL] -instantie. Als er geen overeenkomst is, retourneert de API (geen fout) met het bericht &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Voorbeeldcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
