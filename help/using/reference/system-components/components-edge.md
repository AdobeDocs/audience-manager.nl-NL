---
description: De Audience Manager gebruikt verdeelde, rand-gegevensverwerkingstopologieën om aan de eisen te voldoen die op onze systemen door externe bronnen worden geplaatst.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Werken met het Edge-datacenter
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 4%

---

# Werken met het Edge-datacenter{#understanding-the-edge-data-center}

De Audience Manager gebruikt verdeelde, rand-gegevensverwerkingstopologieën om aan de eisen te voldoen die op onze systemen door externe bronnen worden geplaatst.

## Basisbeginselen van Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge Computing biedt betere prestaties in reactie op diffuse, internet-brede vraag, omdat de &quot;edge&quot; zelf een wereldwijde grens is. Dit betekent [!DNL Audience Manager] Plaatst dynamisch de verwerking dichtst bij de bronnen van vraag en keert gegevens door de kortst mogelijke weg terug. Edge Computing helpt de siteprestaties te behouden, waardoor de gebruikerservaring op uw website behouden blijft. Het centrum van randgegevens is een zeer belangrijke gateway voor het bewegen van gegevens binnen en uit [!DNL Audience Manager].

De [!DNL Audience Manager] edge data center omvat:

* **Kernservers:** Dit zijn de belangrijkste [!DNL Audience Manager] systemen. Ze werken de Edge-servers bij en verschaffen gegevens aan de Edge-servers.

* **Edge-servers:** Dit zijn doorgaans toepassings- en/of webservers. Ze zitten op de grens tussen [!DNL Audience Manager] en het internet. Edge-servers, zoals de [!DNL DCS] of Akamai-systemen, verwerken doorgaans gegevens en verzoeken die van en naar [!DNL Audience Manager].

* **Balans laden:** Beheer ongelijkmatige verwerkings-/verwerkingsvereisten die inherent zijn aan internettoepassingen. Deze balanceringen voorkomen dat clusters van servers worden overbelast terwijl andere inactief blijven.

Het volgende diagram illustreert de omgeving van het datacenter van de rand van de Audience Manager.

![](assets/edge_data_center.png)

## Geografische verdeling en taakverdeling {#geo-dist-balance}

Zie de [!DNL DCS] sectie in [Componenten gegevensverzameling](../../reference/system-components/components-data-collection.md).
