---
description: Hiermee wordt een specifieke waarde opgehaald van een advertentieserver.
seo-description: Retrieves a specific value from an ad server.
seo-title: dexGetQSVars
solution: Audience Manager
title: dexGetQSVars
uuid: 6d21c7a4-43f8-456b-8831-47343dbb047e
feature: DIL Implementation
exl-id: 814268bc-4387-4e06-ae94-eda86993a967
source-git-commit: 152b3101e69e99dfe19c1be93edceaea6adc4fec
workflow-type: tm+mt
source-wordcount: '0'
ht-degree: 0%

---

# dexGetQSVars{#dexgetqsvars}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
><br><br>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangeraden [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun strategie voor het verzamelen van gegevens op lange termijn.
><br><br>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan.

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
