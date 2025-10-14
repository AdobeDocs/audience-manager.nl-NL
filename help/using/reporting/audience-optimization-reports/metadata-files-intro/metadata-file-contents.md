---
description: Maak de inhoud van het Audience Optimization-metagegevensbestand op volgens deze specificaties.
seo-description: Format the contents of your Audience Optimization metadata file according to these specifications.
seo-title: Content Format for Metadata Files
solution: Audience Manager
title: Indeling van inhoud voor metagegevensbestanden
uuid: 9ba44738-3e17-40c7-9e8c-5abd8361e16d
feature: Log Files
exl-id: 1aed39f4-f893-4f25-b041-e198895e338a
source-git-commit: fe01ebac8c0d0ad3630d3853e0bf32f0b00f6a44
workflow-type: tm+mt
source-wordcount: '299'
ht-degree: 0%

---

# Indeling van inhoud voor metagegevensbestanden{#content-format-for-metadata-files}

Maak de inhoud van het Audience Optimization-metagegevensbestand op volgens deze specificaties.

## Syntaxis {#syntax}

De volgende syntaxis definieert de structuur van goed gevormde inhoud in een metagegevensbestand. Nota, *cursief* wijst op veranderlijke placeholder.

**Syntaxis:** *inhoudsidentiteitskaart* | *naam* | *-1*

<!--In the contents syntax, you'll notice a parent ID variable. Don't confuse it with the parent ID used in the [metadata file name](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md). These 2 variables seem similar, but they represent different things. In the file name, the parent ID corresponds to a category like "campaign" (ID 1), "placement" (ID 3), or "tactic" (ID 9), etc. In the file body:-->

De derde kolom **- 1** is technisch ouder identiteitskaart, die een erfenisgebied is. De waarde zou altijd als **- 1** moeten worden geplaatst.

>[!NOTE]
>
>Er is één metagegevensbestand per dimensie nodig, dus er worden meerdere metagegevensbestanden verwacht in het emmertje. De dimensies worden vermeld in het artikel [&#x200B; Noemende Conventies voor het Dossier van Meta-gegevens &#x200B;](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**afzonderlijke Ingangen van het Dossier met ^a (controle-A of ASCII 001)**

Gebruik `^a` (controle-A of ASCII 001) om inhoud in uw meta-gegevensdossiers te scheiden. Aangezien dit niet-afdrukbare tekens zijn, wordt in het bovenstaande syntaxisvoorbeeld alleen voor weergavedoeleinden een verticale balk &quot;|&quot; weergegeven.

Indien nodig, kunt u het voorbeelddossier downloaden - [&#x200B; 20181105_0_1 &#x200B;](assets/20181105_0_1.zip). Pak het uit en bewerk het in de editor van uw keuze en pas het aan volgens de inhoud van de metagegevens, aangezien het al het vereiste scheidingsteken bevat.

>[!IMPORTANT]
>
>Voeg geen koptekstrijen toe aan metagegevensbestanden.

## Voorbeelden {#examples}

Laten we eens kijken hoe u de inhoud van een metagegevensbestand structureert. Een deel van deze structuur is afhankelijk van de dimensie. De dimensies worden vermeld in het artikel [&#x200B; Noemende Conventies voor het Dossier van Meta-gegevens &#x200B;](../../../reporting/audience-optimization-reports/metadata-files-intro/metadata-file-names.md#child-dimension).

**Campagne**

In dit voorbeeld is de bestandstitel 20180921_0_1 en de drie kolommen in het bestand zijn: Campagne-id, Naam en Bovenliggende id.

<!--Let's say you want to populate the creative drop down menu with creative names from a particular campaign. In this case, your metadata file name would include ID 1 (campaign) and ID 2 (creative). Following the content syntax, your metadata file would contain the creative ID, creative name, and actual campaign ID.-->

```
//File Title
20180921_0_1

111 Campaign A -1
222 Campaign B -1
333 Campaign C -1
```

**Creative**

In dit voorbeeld is de bestandstitel 20180827_0_2 en de drie kolommen in het bestand zijn: Creative-id, -naam en bovenliggende id.

```
//File Title
20180921_0_2

111 Creative A -1
222 Creative B -1
333 Creative C -1
```

**Plaats**

In dit voorbeeld is de bestandstitel 20180921_0_5 en de drie kolommen in het bestand zijn: Site-id, Naam en Bovenliggende id.

```
//File Title
20180921_0_5

111 Site A -1
222 Site B -1
333 Site C -1
```
