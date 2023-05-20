---
description: Een afgeleid signaal kwalificeert sitebezoekers voor extra kenmerken op basis van een kenmerk dat ze al hebben gezien. Met andere woorden, aanvullende vakkwalificatie kan worden afgeleid van een momenteel tentoongestelde eigenschap, zelfs als een gebruiker de nieuwe eigenschap nog niet eerder heeft gezien.
seo-description: A derived signal qualifies site visitors for additional traits based on a trait they've already seen. In other words, additional trait qualification can be derived from a currently exhibited trait even if a user has never seen the new trait before.
seo-title: Derived Signals
solution: Audience Manager
title: Afgeleide signalen
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
exl-id: 64bc004a-a31a-49bb-aa58-323fbc92f76f
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '260'
ht-degree: 1%

---

# Afgeleide signalen {#derived-signals}

A [!UICONTROL derived signal] kwalificeert bezoekers van de site voor extra kenmerken op basis van een eigenschap die ze al hebben gezien. Met andere woorden, aanvullende vakkwalificatie kan worden afgeleid van een momenteel tentoongestelde eigenschap, zelfs als een gebruiker de nieuwe eigenschap nog niet eerder heeft gezien.

<!-- c_tb_derived_signal.xml -->

## Doel van Afgeleide signalen

In [!DNL Audience Manager]kunt u een relatie maken tussen signalen (of traitregels) die tijdens een gebeurtenisaanroep worden doorgegeven aan andere, opgegeven signalen of kenmerken. Stel dat een gebeurtenisaanroep wordt doorgegeven in een signaal dat bestaat uit de sleutel-waarde [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] zou dat signaal verbinden met om het even welke anderen die met [!UICONTROL derived signals] gebruiken. Hoewel de bijbehorende signalen om het even welke zeer belangrijk-waarden kunnen zijn u specificeert, zijn zij het nuttigst wanneer verbonden aan bestaande signalen reeds opstelling zoals [!UICONTROL Trait Builder] regels. In de onderstaande afbeelding wordt bijvoorbeeld aangegeven dat wanneer een handeling van de gebruiker het signaal activeert [!DNL "product = new car"] die gebruiker kan ook in aanmerking komen voor kenmerken die worden gedefinieerd door de doelsleutel- en waardesignalen.

![](assets/derived_signal_example.png)

## Locatie van afgeleide signalen

Maken en beheren [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** in de zijbalknavigatie.

## Een afgeleid signaal maken {#create}

<!-- t_tb_create_derived.xml -->

Als u een [!UICONTROL derived signal]:

1. Selecteren **[!UICONTROL Derived Signals]** van de [!UICONTROL Tools] -menu.
1. Geef een overzicht:
   * *(Optioneel)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klik op **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>De tekenlimiet voor de [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key], en [!UICONTROL Target Value] velden bestaan uit 228 tekens.

## Afgeleid signaal bewerken {#edit}

<!-- t_tb_edit_derived.xml -->

Een [!UICONTROL derived signal]:

1. Houd de cursor boven het signaal en klik vervolgens op **[!UICONTROL Edit]**.
2. Breng de vereiste code-, toets- of waardewijzigingen aan en klik vervolgens op **[!UICONTROL Save]**.

## Afgeleid signaal verwijderen {#delete}

<!-- t_tb_delete_derived.xml -->

Een [!UICONTROL derived signal], plaatst u de cursor boven het signaal en klikt u op **[!UICONTROL Delete]**.
