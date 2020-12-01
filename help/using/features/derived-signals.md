---
description: Een afgeleid signaal kwalificeert sitebezoekers voor extra kenmerken op basis van een kenmerk dat ze al hebben gezien. Met andere woorden, aanvullende vakkwalificatie kan worden afgeleid van een momenteel tentoongestelde eigenschap, zelfs als een gebruiker de nieuwe eigenschap nog niet eerder heeft gezien.
seo-description: Een afgeleid signaal kwalificeert sitebezoekers voor extra kenmerken op basis van een kenmerk dat ze al hebben gezien. Met andere woorden, aanvullende vakkwalificatie kan worden afgeleid van een momenteel tentoongestelde eigenschap, zelfs als een gebruiker de nieuwe eigenschap nog niet eerder heeft gezien.
seo-title: Afgeleide signalen
solution: Audience Manager
title: Afgeleide signalen
uuid: e52600e3-26d1-4607-9b96-afd6086a252d
feature: Traits
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '303'
ht-degree: 2%

---


# Afgeleide signalen {#derived-signals}

Een [!UICONTROL derived signal] kwalificeert sitebezoekers voor extra kenmerken op basis van een kenmerk dat ze al hebben gezien. Met andere woorden, aanvullende vakkwalificatie kan worden afgeleid van een momenteel tentoongestelde eigenschap, zelfs als een gebruiker de nieuwe eigenschap nog niet eerder heeft gezien.

<!-- c_tb_derived_signal.xml -->

## Doel van Afgeleide signalen

In [!DNL Audience Manager], kunt u een verband tussen signalen (of de regels van het trekkengedrag) tot stand brengen binnen tijdens een gebeurtenisvraag aan andere, gespecificeerde signalen of trekken wordt overgegaan. Stel bijvoorbeeld dat een gebeurtenisaanroep wordt doorgegeven in een signaal dat bestaat uit de toetswaarde [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car`). [!DNL Audience Manager] zou dat signaal verbinden met andere gebruikers die met het  [!UICONTROL derived signals] gereedschap zijn gemaakt. Hoewel de bijbehorende signalen om het even welke zeer belangrijk-waarden kunnen zijn u specificeert, zijn zij het nuttigst wanneer verbonden met bestaande signalen reeds opstelling als [!UICONTROL Trait Builder] regels. Bijvoorbeeld, in de illustratie hieronder, wanneer een gebruikersactie het signaal [!DNL "product = new car"] in werking stelt kan die gebruiker ook voor eigenschappen kwalificeren die door de doelsleutel en waardesignalen worden bepaald.

![](assets/derived_signal_example.png)

## Locatie van afgeleide signalen

Maak en beheer [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** vanuit de zijbalknavigatie.

## Een afgeleid signaal maken {#create}

<!-- t_tb_create_derived.xml -->

Een [!UICONTROL derived signal] maken:

1. Selecteer **[!UICONTROL Derived Signals]** van [!UICONTROL Tools] menu.
1. Geef een overzicht:
   * *(Optioneel)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klik op **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>De tekenlimiet voor de velden [!UICONTROL Source Key], [!UICONTROL Source Value], [!UICONTROL Target Key] en [!UICONTROL Target Value] is 228 tekens.

## Afgeleid signaal {#edit} bewerken

<!-- t_tb_edit_derived.xml -->

Een [!UICONTROL derived signal] bewerken:

1. Houd de cursor boven het signaal en klik op **[!UICONTROL Edit]**.
2. Wijzig de vereiste code, sleutel of waarde en klik op **[!UICONTROL Save]**.

## Afgeleid signaal {#delete} verwijderen

<!-- t_tb_delete_derived.xml -->

Als u een [!UICONTROL derived signal] wilt verwijderen, plaatst u de cursor boven het signaal en klikt u op **[!UICONTROL Delete]**.
