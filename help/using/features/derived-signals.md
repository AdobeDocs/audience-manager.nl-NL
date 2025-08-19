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
source-wordcount: '261'
ht-degree: 0%

---

# Afgeleide signalen {#derived-signals}

Een [!UICONTROL derived signal] kwalificeert sitebezoekers voor extra kenmerken op basis van een kenmerk dat ze al hebben gezien. Met andere woorden, aanvullende vakkwalificatie kan worden afgeleid van een momenteel tentoongestelde eigenschap, zelfs als een gebruiker de nieuwe eigenschap nog niet eerder heeft gezien.

<!-- c_tb_derived_signal.xml -->

## Doel van Afgeleide signalen

In [!DNL Audience Manager], kunt u een verhouding tot stand brengen tussen signalen (of trekkenregels) die tijdens een gebeurtenisvraag aan andere, gespecificeerde signalen of eigenschappen worden overgegaan. Stel dat een gebeurtenisaanroep wordt doorgegeven in een signaal dat bestaat uit de sleutelwaarde [!DNL "product = new_car"] ( `https://<domain alias>/event?product=new_car` ). [!DNL Audience Manager] zou dat signaal verbinden met andere gebruikers die met het gereedschap [!UICONTROL derived signals] zijn gemaakt. Hoewel de gekoppelde signalen alle opgegeven sleutelwaarden kunnen zijn, zijn ze het meest nuttig wanneer ze worden gekoppeld aan bestaande signalen die al zijn ingesteld als [!UICONTROL Trait Builder] -regels. In de onderstaande afbeelding kunt u bijvoorbeeld aangeven dat wanneer een actie van de gebruiker het signaal [!DNL "product = new car"] activeert, die gebruiker ook in aanmerking kan komen voor kenmerken die worden gedefinieerd door de doeltoets en -waardensignalen.

![](assets/derived_signal_example.png)

## Locatie van afgeleide signalen

Maak en beheer [!UICONTROL derived signals] in **[!UICONTROL Tools > Derived Signals]** via de zijbalknavigatie.

## Een afgeleid signaal maken {#create}

<!-- t_tb_create_derived.xml -->

Een [!UICONTROL derived signal] maken:

1. Selecteer **[!UICONTROL Derived Signals]** in het menu [!UICONTROL Tools] .
1. Geef een overzicht:
   * *(Optioneel)* [!UICONTROL Integration Code]
   * [!UICONTROL Source Key]
   * [!UICONTROL Source Value]
   * [!UICONTROL Target Key]
   * [!UICONTROL Target Value]
1. Klik op **[!UICONTROL Add Signal]**.

>[!NOTE]
>
>De tekenlimiet voor de velden [!UICONTROL Source Key] , [!UICONTROL Source Value] , [!UICONTROL Target Key] en [!UICONTROL Target Value] is 228 tekens.

## Afgeleid signaal bewerken {#edit}

<!-- t_tb_edit_derived.xml -->

Een [!UICONTROL derived signal] bewerken:

1. Houd de cursor boven het signaal en klik op **[!UICONTROL Edit]** .
2. Wijzig de vereiste code, sleutel of waarde en klik op **[!UICONTROL Save]** .

## Afgeleid signaal verwijderen {#delete}

<!-- t_tb_delete_derived.xml -->

Als u een [!UICONTROL derived signal] wilt verwijderen, plaatst u de cursor boven het signaal en klikt u op **[!UICONTROL Delete]** .
