---
description: Beschrijft authentificatievereisten en het tekst formatteren die in de klasse-vlakke documentatie van DIL worden gebruikt.
seo-description: Describes authentication requirements and the text formatting used in the class-level DIL documentation.
seo-title: Getting Started With Class-level DIL APIs
solution: Audience Manager
title: Aan de slag met DIL API's op klasseniveau
uuid: 00c1136a-5f08-4104-b0ed-3de847cecd16
feature: DIL Implementation
exl-id: 909d39a1-0da6-467e-a13b-19a57f9186a1
source-git-commit: cad38e2c523e9b762aa996c275daefa96c8e14b0
workflow-type: tm+mt
source-wordcount: '203'
ht-degree: 0%

---

# Aan de slag met DIL API&#39;s op klasseniveau{#getting-started-with-class-level-dil-apis}

>[!WARNING]
>
>Vanaf juli 2023 heeft Adobe de ontwikkeling van de extensie [!DNL Data Integration Library (DIL)] en [!DNL DIL] stopgezet.
>
>Bestaande klanten kunnen hun [!DNL DIL] -implementatie blijven gebruiken. Adobe ontwikkelt [!DNL DIL] echter niet verder dan dit punt. De klanten worden aangemoedigd om [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) voor hun lange termijn strategie van de gegevensinzameling te evalueren.
>
>De klanten die nieuwe integratie van de gegevensinzameling na Juli 2023 willen uitvoeren zouden [ SDK van het Web van Experience Platform ](https://experienceleague.adobe.com/docs/experience-platform/edge/home.html?lang=nl-NL) in plaats daarvan moeten gebruiken.

Met DIL API&#39;s op klasseniveau kunt u programmatisch Audience Manager-objecten maken en ermee werken. De API&#39;s op klasseniveau werken samen met de andere functies op instantieniveau om waarden in te stellen of gegevens te retourneren.

## Aan de slag met DIL API&#39;s op klasseniveau {#get-started}

Beschrijft authentificatievereisten en het tekst formatteren die in de klasse-vlakke [!UICONTROL DIL] documentatie worden gebruikt.

<!-- 

c_class_start.xml

 -->

Wanneer u werkt met de API&#39;s op klasseniveau [!UICONTROL DIL] :

* De toegang vereist een partnernaam en container namespace identiteitskaart (NSID). Neem contact op met uw Audience Manager-accountmanager voor deze informatie.
* Vervang om het even welke steekproef *cursief* tekst in de API documentatie met waarde, identiteitskaart, of andere variabele zoals die door de methode wordt vereist u met werkt.
* [!UICONTROL DIL] schrijft gecodeerde gegevens naar een doelcookie. Spaties worden bijvoorbeeld gecodeerd als `%20` en puntkomma&#39;s als `%3B` .
