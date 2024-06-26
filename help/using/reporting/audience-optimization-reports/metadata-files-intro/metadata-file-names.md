---
description: Geef het bestand met Audience Optimization-metagegevens een naam op basis van deze specificaties.
seo-description: Name your Audience Optimization metadata file according to these specifications.
seo-title: Naming Conventions for Metadata Files
solution: Audience Manager
title: Naamgevingsconventies voor metadatabestanden
uuid: cab55b2a-2e54-45f6-aeea-3735b911f821
feature: Log Files
exl-id: 7a895c4f-1100-4ba1-947e-abb47307fb40
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '199'
ht-degree: 5%

---

# Naamgevingsconventies voor metadatabestanden{#naming-conventions-for-metadata-files}

Geef het bestand met Audience Optimization-metagegevens een naam op basis van deze specificaties.

## Syntaxis- en id-categorieën {#syntax}

De volgende syntaxis definieert de structuur van een correct gevormde naam van een metagegevensbestand. Opmerking: *cursief* Hiermee wordt een tijdelijke aanduiding voor een variabele aangegeven. De andere elementen zijn constanten en veranderen niet.

**Syntaxis:** *`yyyymmdd_0_childID`*

>[!NOTE]
>
>*Niet gebruiken* gebruik bestandsextensies in uw metagegevensbestanden (.txt of andere).

<!--In the name syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file contents](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-contents.md). These 2 variables seem similar, but they represent different things:-->

* De middelste component **0** is technisch gezien de Bovenliggende ID, een verouderd veld. De waarde moet altijd worden ingesteld als **0**.
* De onderliggende id kan een waarde tussen 1 en 10 hebben, afhankelijk van de dimensie. Zie hieronder:

## Dimensies van onderliggende id&#39;s {#child-dimension}

In de naam van het metagegevensbestand is de onderliggende id een id waarmee het type gegevens in een bestand wordt geclassificeerd en in een hiërarchie wordt geplaatst. U kunt de onderliggende id in de bestandsnaam labelen met de volgende categorie-id&#39;s:

1. Campagne
1. Creatief
1. Plaatsing
1. Exchange
1. Site
1. Adverteerder (als u integratiecodes gebruikt in een [gegevensbron](../../../features/manage-datasources.md#details))
1. Invoegvolgorde (IO)
1. Verticaal (d.w.z. een specifieke industrie- of bedrijfscategorie zoals &quot;computers&quot;, &quot;auto&#39;s&quot;, &quot;onroerend goed&quot; enz.)
1. Tactisch
1. Bedrijfseenheid of merk

## Voorbeeld {#example}

Voor een Creative-metagegevensbestand kan de bestandsnaam 20190115_0_2 zijn.

<!--Let's take a look at how you would use these IDs in a metadata file name. As an example, say your data file consists of campaign creatives. In this case, the campaign is a parent object and the creatives are child objects because they belong to, or are contained by, the campaign. As a result, you'd choose the following IDs for the metadata file name:

* Parent ID: `1` 
* Child ID: `2`

Your metadata file name would look like this: `20150827_1_2`

Sometimes, you might have data that does not belong to a parent object. Whenever this is the case, select ID 0 for the parent ID. In this case, your file title would look like this: `20150827_0_2`. -->
