---
description: De Manager van het publiek gebruikt verdeelde, rand-gegevensverwerkingstopologieën om aan de eisen te voldoen die op onze systemen door externe bronnen worden geplaatst.
seo-description: De Manager van het publiek gebruikt verdeelde, rand-gegevensverwerkingstopologieën om aan de eisen te voldoen die op onze systemen door externe bronnen worden geplaatst.
seo-title: Werken met Edge Data Center
solution: Audience Manager
title: Werken met Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
translation-type: tm+mt
source-git-commit: c9737315132e2ae7d72c250d8c196abe8d9e0e43

---


# Werken met Edge Data Center{#understanding-the-edge-data-center}

De Manager van het publiek gebruikt verdeelde, rand-gegevensverwerkingstopologieën om aan de eisen te voldoen die op onze systemen door externe bronnen worden geplaatst.

## Basisbeginselen van Edge Data Center {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge Computing biedt betere prestaties in reactie op diffuse, internet-brede vraag, omdat de &quot;edge&quot; zelf een wereldwijde grens is. Dit betekent [!DNL Audience Manager] dynamisch verwerking dichtst bij de bronnen van vraag plaatst en gegevens door de kortst mogelijke weg terugkeert. Edge Computing helpt de siteprestaties te behouden, waardoor de gebruikerservaring op uw website behouden blijft. Het centrum van randgegevens is een zeer belangrijke gateway voor het bewegen van gegevens binnen en uit [!DNL Audience Manager].

Het datacenter van de [!DNL Audience Manager] rand bevat:

* **Kernservers:** Dit zijn de belangrijkste [!DNL Audience Manager] systemen. Ze werken de Edge-servers bij en verschaffen gegevens aan de Edge-servers.

* **Edge-servers:** Dit zijn doorgaans toepassings- en/of webservers. Ze zitten aan de grens tussen [!DNL Audience Manager] en het internet. Edge-servers, zoals de [!UICONTROL DCS] - of Akamai-systemen, verwerken doorgaans gegevens en verzoeken die van en naar [!DNL Audience Manager]komen.

* **Balans laden:** Beheer ongelijkmatige verwerkings-/verwerkingsvereisten die inherent zijn aan internettoepassingen. Deze balanceringen voorkomen dat clusters van servers worden overbelast terwijl andere inactief blijven.

Het volgende diagram illustreert de omgeving van het Edge-datacenter van Audience Manager.

![](assets/edge_data_center.png)

## Geografische verdeling en taakverdeling {#geo-dist-balance}

Zie de [!UICONTROL DCS] sectie in de Componenten [van de](../../reference/system-components/components-data-collection.md)Gegevensverzameling.
