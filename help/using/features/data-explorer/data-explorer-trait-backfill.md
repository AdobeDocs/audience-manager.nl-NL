---
description: De realisaties van het terugvullingsspoor om historische publiek te vangen en verlies van relevante gegevens te vermijden voorafgaand aan een de aanmaakdatum van het spoor.
seo-description: De realisaties van het terugvullingsspoor om historische publiek te vangen en verlies van relevante gegevens te vermijden voorafgaand aan een de aanmaakdatum van het spoor.
seo-title: Aanvulling van eigenschaprealisaties
title: Aanvulling van eigenschaprealisaties
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '451'
ht-degree: 1%

---


# Aanvulling van eigenschaprealisaties {#backfill-trait-realizations}

De realisaties van het terugvullingsspoor om historische publiek te vangen en verlies van relevante gegevens te vermijden voorafgaand aan een de aanmaakdatum van het spoor.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] is een premiumfunctie die de Audience Manager-ervaring vergroot door het ontgrendelen van extra gebruiksgevallen. Voor back-up is extra verwerkingskracht nodig en deze is tegen extra kosten beschikbaar voor alle klanten van de Audience Manager. Neem contact op met uw Adobe-verkoper voor meer informatie.

Wanneer u eigenschappen van ongebruikte signalen creeert, kunt u verkiezen om de karakterrealisaties over een specifieke periode te herhalen. [!DNL Audience Manager] vangt de historische gegevens over publiek dat voor het nieuwe spoor in aanmerking komt en slaat hen op het overeenkomstige profiel op. U kunt **[!UICONTROL Backfill Options]** in [!UICONTROL Trait Expression] sectie van **[Trait Builder](../../features/traits/about-trait-builder.md)** zien.

>[!NOTE]
>
>U kunt de verwezenlijking van de het vullingseigenschap voor regel-gebaseerde en ongebogen eigenschappen terugvullen.

Hieronder wordt beschreven hoe u de gemaakte fouten kunt terugvullen:

1. Ga naar [!UICONTROL Audience Data > Signals > Search] en voer een Signals Onderzoek in of gebruik [Signals Dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) om de signalen te identificeren in het nieuwe bezit te gebruiken.
1. Maak een nieuw kenmerk op basis van de gewenste signalen.
1. Gebruik **[!UICONTROL Backfill Options]** in de **[!UICONTROL Trait Expression]** sectie om het tijdinterval te selecteren waarvoor u de verwezenlijking van de het dienstreis wilt terugvullen. Vooraf gedefinieerde backfill-intervallen zijn 1, 7, 14 en 30 dagen. U kunt ook een aangepast datumbereik van maximaal 30 dagen kiezen.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Optioneel) Klik op **[!UICONTROL Estimate Realizations]** in de sectie **[!UICONTROL Estimated Trait Realizations]** om de geschatte [!UICONTROL Unique Trait Realizations]- en [!UICONTROL Total Trait Population]-waarden voor de teruggevulde eigenschap in de afgelopen 7 dagen te bekijken.

   ![ramen en waarheidsgetrouwheid](assets/estimate-trait-realizations.png)

   >[!IMPORTANT]
   >
   >Terugvullen en schatten van het spoor zijn niet beschikbaar voor eigenschappen met uitdrukkingen die de volgende exploitanten gebruiken:
   >    * `!=`
   >    * `matchesregex`
   >    * `matcheswords`

1. Maak de eigenschap.

Zodra u klaar bent met het maken van de eigenschap, ziet u de achtergevulde realisaties die zijn opgenomen in de realisatiestatistieken.

Bekijk de video hieronder voor een videodemonstratie van hoe u terugvullingseigenschappen kunt gebruiken.

>[!VIDEO](https://video.tv.adobe.com/v/25169/)

## Latentie achtergrondvulling {#trait-backfilling-latency}

Nieuwe traits maken het publiek twee tot drie uur na het maken vast. Vanwege het grote gegevensvolume dat [!DNL Audience Manager] dagelijks uitvoert, wordt de teruggevulde populatie echter niet onmiddellijk weerspiegeld in de [!UICONTROL Unique Trait Realizations]- en [!UICONTROL Total Trait Population]-grafieken.

Audience Manager werkt [!UICONTROL Trait Graph] met de achtergevulde populatie bij binnen 48 uur na het creëren van de eigenschap.

## Limiet voor achteruitvullen {#trait-backfilling-limit}

[!UICONTROL Data Explorer] staat u toe om tot 50 eigenschappen per maand terug te vullen, met de backfill teller wordt teruggesteld op de 1 dag van elke maand.

>[!NOTE]
>
>De quota voor het terugvullen van de tonijn worden niet overgedragen van de vorige maanden. Bijvoorbeeld, als u 30 eigenschappen deze maand terugvult, wordt het quotum van de standaard backfill voor de volgende maand teruggesteld aan 50, niet 70.

## Gevolgen voor rapportage {#reporting-impact}

Achtergevulde taakrealisaties worden weerspiegeld in de meetwaarden [!UICONTROL Unique Trait Realizations] en [!UICONTROL Total Trait Population], aangezien [!DNL Audience Manager] historische signalen omzet in tekrealisaties.

De [!UICONTROL Trait Graph], [!UICONTROL General Reports] en [!UICONTROL Trend Reports] worden echter niet retroactief bijgewerkt met historische meetgegevens die vóór de aanmaakdatum van de eigenschap zijn teruggezet.