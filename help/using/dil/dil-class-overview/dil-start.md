---
description: Beschrijft authentificatievereisten en het tekst formatteren die in de klasse-vlakke documentatie van DIL worden gebruikt.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Aan de slag met DIL-API’s op klasseniveau
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: fcf13cf39f688f8aafd2b1020ddfe4583d67e14f
workflow-type: tm+mt
source-wordcount: '215'
ht-degree: 8%

---

# Aan de slag met DIL-API’s op klasseniveau{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de [!DNL Data Integration Library (DIL)] en de [!DNL DIL] extensie.
><br>
>Bestaande klanten kunnen hun [!DNL DIL] uitvoering. Adobe zal zich echter niet ontwikkelen [!DNL DIL] verder dan dit punt. Klanten worden aangeraden [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) voor hun strategie voor het verzamelen van gegevens op lange termijn.
><br>
>Klanten die na juli 2023 nieuwe integratie voor gegevensverzameling willen implementeren, moeten [Experience Platform Web SDK](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=en) in plaats daarvan.

Met de DIL-API&#39;s op klasseniveau kunt u programmatisch Audience Managers maken en ermee werken. De API&#39;s op klasseniveau werken samen met de andere functies op instantieniveau om waarden in te stellen of gegevens te retourneren.

## Aan de slag met DIL-API’s op klasseniveau {#get-started}

Beschrijft authentificatievereisten en het tekst formatteren die in klasse-niveau worden gebruikt [!UICONTROL DIL] documentatie.

<!-- 

c_class_start.xml

 -->

Wanneer u met de klasse werkt [!UICONTROL DIL] API&#39;s:

* De toegang vereist een partnernaam en container namespace identiteitskaart (NSID). Neem contact op met de accountmanager van de Audience Manager voor deze informatie.
* Een voorbeeld vervangen *cursief* tekst in de API documentatie met waarde, identiteitskaart, of andere variabele zoals vereist door de methode u met werkt.
* [!UICONTROL DIL] gecodeerde gegevens worden naar een doelcookie geschreven. Spaties worden bijvoorbeeld gecodeerd als `%20` en puntkomma&#39;s als `%3B`.
