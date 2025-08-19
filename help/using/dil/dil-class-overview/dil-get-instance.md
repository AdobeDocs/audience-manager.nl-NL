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
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '143'
ht-degree: 1%

---

# getDil{#getdil}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan moeten gebruiken.

Hiermee wordt een partnerspecifieke DIL-instantie opgehaald.

**de Handtekening van de Functie:** `getDil: function (partner, containerNSID) {}`

<!-- r_dil_get_dil.xml -->

## Parameters

| Naam | Type | Beschrijving |
|---|---|---|
| `partner` | String | De partnernaam aan onderzoek naar. |
| `containerNSID` | Geheel | De standaardwaarde is `0` . NSID van de container u zoekt naar. Optioneel. |

## Antwoord

Een succesvolle partner en container NSID keert een partner-specifieke [!UICONTROL DIL] instantie terug. Als er geen overeenkomst is, retourneert de API (geen fout) met het bericht &quot; `The DIL instance with partner <name> and containerNSID <ID> was not found.`&quot;

## Voorbeeldcode

<pre class="java"><code>DIL.getDil('<i>partner</i>', <i>containerNSID</i>); 
DIL.getDil('<i>partner</i>');</code></pre>
