---
description: Audience Manager maakt gebruik van gedistribueerde, 'edge-computing' topologieën om tegemoet te komen aan de eisen die externe bronnen stellen aan onze systemen.
seo-description: Audience Manager uses distributed, edge-computing topologies to meet the demands placed on our systems by external sources.
seo-title: Understanding the Edge Data Center
solution: Audience Manager
title: Edge Data Center
uuid: 4177e666-99f4-453d-94dd-058c6182c8d2
feature: System Components
exl-id: 28958b49-3075-4601-9271-ef2913721a66
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '222'
ht-degree: 0%

---

# Edge Data Center{#understanding-the-edge-data-center}

Audience Manager maakt gebruik van gedistribueerde, &#39;edge-computing&#39; topologieën om tegemoet te komen aan de eisen die externe bronnen stellen aan onze systemen.

## Basisprincipes van Edge-datacenter {#edge-data-center-basics}

<!-- 

c_compedge.xml

 -->

Edge computing biedt betere prestaties als reactie op diffuse, internet-brede vraag, omdat de &quot;edge&quot; zelf een wereldwijde grens is. Dit betekent dat [!DNL Audience Manager] de verwerking dynamisch het dichtst bij de bronnen van vraag plaatst en gegevens door de kortst mogelijke weg terugkeert. Edge Computing helpt de siteprestaties te behouden, waardoor de gebruikerservaring op uw website behouden blijft. Het Edge-gegevenscentrum is een belangrijke gateway voor het in- en uitschakelen van gegevens in [!DNL Audience Manager] .

Het datacenter van de [!DNL Audience Manager] edge bevat:

* **Servers van de Kern:** dit zijn de belangrijkste [!DNL Audience Manager] systemen. Ze werken de Edge-servers bij en verschaffen gegevens aan de Edge-servers.

* **de Servers van Edge:** typisch, zijn dit toepassing en/of Webservers. Ze zitten aan de grens tussen [!DNL Audience Manager] en internet. Edge-servers, zoals de [!DNL DCS] - of Akamai-systemen, verwerken doorgaans gegevens en aanvragen die van en naar [!DNL Audience Manager] gaan.

* **de Balancers van de Lading:** beheert ongelijke gegevensverwerking/verwerkingseisen inherent aan de toepassingen van Internet. Deze balanceringen voorkomen dat clusters van servers worden overbelast terwijl andere inactief blijven.

In het volgende diagram wordt de omgeving van het Audience Manager edge-datacenter geïllustreerd.

![](assets/edge_data_center.png)

## Geografische verdeling en taakverdeling {#geo-dist-balance}

Zie de [!DNL DCS] sectie in [&#x200B; Componenten van de Inzameling van Gegevens &#x200B;](../../reference/system-components/components-data-collection.md).
