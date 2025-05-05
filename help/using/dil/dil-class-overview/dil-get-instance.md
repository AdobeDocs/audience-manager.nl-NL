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
source-wordcount: '155'
ht-degree: 2%

---

# getDil{#getdil}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangemoedigd om te evalueren [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun strategie voor het verzamelen van gegevens op lange termijn.
>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan.

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
