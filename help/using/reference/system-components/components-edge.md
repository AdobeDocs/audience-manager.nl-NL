---
description: De Audience Manager gebruikt verdeelde, rand-gegevensverwerkingstopologieën om aan de eisen te voldoen die op onze systemen door externe bronnen worden geplaatst.
seo-description: De Audience Manager gebruikt verdeelde, rand-gegevensverwerkingstopologieën om aan de eisen te voldoen die op onze systemen door externe bronnen worden geplaatst.
seo-title: Werken met het Edge-datacenter
solution: Audience Manager
title: Werken met het Edge-datacenter
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: system components
translation-type: tm+mt
source-git-commit: 9e4f2f26b83fe6e5b6f669107239d7edaf11fed3
workflow-type: tm+mt
source-wordcount: '244'
ht-degree: 6%

---


# Werken met het Edge-datacenter{#understanding-the-edge-data-center}

De Audience Manager gebruikt verdeelde, rand-gegevensverwerkingstopologieën om aan de eisen te voldoen die op onze systemen door externe bronnen worden geplaatst.

## Basisbeginselen van Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge Computing biedt betere prestaties in reactie op diffuse, internet-brede vraag, omdat de &quot;edge&quot; zelf een wereldwijde grens is. Dit betekent [!DNL Audience Manager] dynamisch verwerking dichtst bij de bronnen van vraag plaatst en gegevens door het kortst mogelijke weg terugkeert. Edge Computing helpt de siteprestaties te behouden, waardoor de gebruikerservaring op uw website behouden blijft. Het centrum van randgegevens is een zeer belangrijke gateway voor het bewegen van gegevens binnen en uit [!DNL Audience Manager].

Het [!DNL Audience Manager] Edge-datacenter bevat:

* **Core Servers:** dit zijn de belangrijkste  [!DNL Audience Manager] systemen. Ze werken de Edge-servers bij en verschaffen gegevens aan de Edge-servers.

* **Edge-servers:** doorgaans zijn dit toepassings- en/of webservers. Zij zitten bij de grens tussen [!DNL Audience Manager] en Internet. Edge-servers, zoals de [!DNL DCS]- of Akamai-systemen, verwerken doorgaans gegevens en verzoeken die van en naar [!DNL Audience Manager] stromen.

* **Load Balancers:** beheer ongelijke rekenkracht-/verwerkingsvereisten die inherent zijn aan internettoepassingen. Deze balanceringen voorkomen dat clusters van servers worden overbelast terwijl andere inactief blijven.

Het volgende diagram illustreert de omgeving van het datacenter van de rand van de Audience Manager.

![](assets/edge_data_center.png)

## Geografische verdeling en taakverdeling {#geo-dist-balance}

Zie de sectie [!DNL DCS] in [Componenten van gegevensverzameling](../../reference/system-components/components-data-collection.md).
