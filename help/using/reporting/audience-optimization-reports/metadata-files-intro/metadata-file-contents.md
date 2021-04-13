---
description: Maak de inhoud van het Audience Optimization-metagegevensbestand op volgens deze specificaties.
seo-description: Maak de inhoud van het Audience Optimization-metagegevensbestand op volgens deze specificaties.
seo-title: Indeling van content voor metadatabestanden
solution: Audience Manager
title: Indeling van content voor metadatabestanden
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Logbestanden
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
translation-type: tm+mt
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '306'
ht-degree: 4%

---

# Indeling van content voor metadatabestanden{#content-format-for-metadata-files}

Maak de inhoud van het Audience Optimization-metagegevensbestand op volgens deze specificaties.

## Syntaxis {#syntax}

De volgende syntaxis definieert de structuur van goed gevormde inhoud in een metagegevensbestand. Opmerking: *cursief* geeft een variabele plaatsaanduiding aan.

**Syntaxis:**  *inhoud-id* |  *naam* |  *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

De derde kolom **-1** is technisch gezien de Ouder identiteitskaart, die een erfenisgebied is. De waarde moet altijd worden ingesteld als **-1**.

>[!NOTE]
>
>Er is één metagegevensbestand per dimensie nodig, dus er worden meerdere metagegevensbestanden verwacht in het emmertje. De afmetingen worden vermeld in het artikel [Naamgevingsconventies voor metagegevensbestand](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Bestandsinvoer scheiden met ^a (besturingselement-A of ASCII 001)**

Gebruik `^a` (controle-A of ASCII 001) om inhoud in uw meta-gegevensdossiers te scheiden. Aangezien dit niet-afdrukbare tekens zijn, wordt in het bovenstaande syntaxisvoorbeeld alleen voor weergavedoeleinden een verticale balk &quot;|&quot; weergegeven.

Indien nodig, kunt u het voorbeelddossier downloaden - [20181105_0_1](assets/20181105_0_1.zip). Pak het uit en bewerk het in de editor van uw keuze en pas het aan volgens de inhoud van de metagegevens, aangezien het al het vereiste scheidingsteken bevat.

>[!IMPORTANT]
>
>Voeg geen koptekstrijen toe aan metagegevensbestanden.

## Voorbeelden {#examples}

Laten we eens kijken hoe u de inhoud van een metagegevensbestand structureert. Een deel van deze structuur is afhankelijk van de dimensie. De afmetingen worden vermeld in het artikel [Naamgevingsconventies voor metagegevensbestand](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campagne**

In dit voorbeeld is de bestandstitel 20180921_0_1 en de drie kolommen in het bestand zijn: Campagne-id, naam en bovenliggende id.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creatief**

In dit voorbeeld is de bestandstitel 20180827_0_2 en de drie kolommen in het bestand zijn: Creative ID, Name en Parent ID.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Site**

In dit voorbeeld is de bestandstitel 20180921_0_5 en de drie kolommen in het bestand zijn: Site-id, naam en bovenliggende id.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
