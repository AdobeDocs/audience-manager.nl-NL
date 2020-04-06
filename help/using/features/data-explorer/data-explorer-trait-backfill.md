---
description: De realisaties van het terugvullingsspoor om historische publiek te vangen en verlies van relevante gegevens te vermijden voorafgaand aan een de aanmaakdatum van het spoor.
seo-description: De realisaties van het terugvullingsspoor om historische publiek te vangen en verlies van relevante gegevens te vermijden voorafgaand aan een de aanmaakdatum van het spoor.
seo-title: Redalisaties achtergrondvulling
title: Redalisaties achtergrondvulling
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
translation-type: tm+mt
source-git-commit: 75fe1e0f7321107930a28e354ca2f4a256a477ac

---


# Redalisaties achtergrondvulling {#backfill-trait-realizations}

De realisaties van het terugvullingsspoor om historische publiek te vangen en verlies van relevante gegevens te vermijden voorafgaand aan een de aanmaakdatum van het spoor.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] is een premiumfunctie die de ervaring van Audience Manager verbetert door extra gebruiksgevallen te ontgrendelen. Voor een back-up is extra verwerkingskracht vereist en deze is tegen extra kosten beschikbaar voor alle klanten van Audience Manager. Neem contact op met uw Adobe-vertegenwoordiger voor meer informatie.

Wanneer u eigenschappen van ongebruikte signalen creeert, kunt u verkiezen om de karakterrealisaties over een specifieke periode te herhalen. [!DNL Audience Manager] vangt de historische gegevens over publiek dat voor het nieuwe spoor in aanmerking komt en slaat hen op het overeenkomstige profiel op. U kunt de sectie **[!UICONTROL Backfill Options]** in de [!UICONTROL Trait Expression] sectie van de **[Trait Builder](../../features/traits/about-trait-builder.md)**zien.

>[!NOTE]
>
>U kunt de verwezenlijking van de het vullingseigenschap voor regel-gebaseerde en ongebogen eigenschappen terugvullen.

Hieronder wordt beschreven hoe u de gemaakte fouten kunt terugvullen:

1. Ga naar [!UICONTROL Audience Data > Signals > Search] en voer een Signals-zoekopdracht uit of gebruik het [Signals-dashboard](../../features/data-explorer/data-explorer-signals-dashboard.md) om de signalen te identificeren die in het nieuwe kenmerk moeten worden gebruikt.
1. Maak een nieuw kenmerk op basis van de gewenste signalen.
1. Gebruik het **[!UICONTROL Backfill Options]** gedeelte in de **[!UICONTROL Trait Expression]** sectie om het tijdinterval te selecteren waarvoor u de resultaten van de eigenschap wilt terugvullen. Vooraf gedefinieerde backfill-intervallen zijn 1, 7, 14 en 30 dagen. U kunt ook een aangepast datumbereik van maximaal 30 dagen kiezen.

   ![trait-backfill](assets/signals-trait-backfill.png)

1. (Optioneel) Klik **[!UICONTROL Estimate Realizations]** in de **[!UICONTROL Estimated Trait Realizations]** sectie om de geschatte [!UICONTROL Unique Trait Realizations] en [!UICONTROL Total Trait Population] waarden van de teruggevulde eigenschap in de afgelopen 7 dagen te bekijken.

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

## Latentie achtergrondvulling afsluiten {#trait-backfilling-latency}

Nieuwe traits maken het publiek twee tot drie uur na het maken vast. Vanwege het grote gegevensvolume dat dagelijks [!DNL Audience Manager] wordt uitgevoerd, wordt de achtergevulde populatie echter niet onmiddellijk weergegeven in de [!UICONTROL Unique Trait Realizations] en [!UICONTROL Total Trait Population] grafieken.

Audience Manager werkt de [!UICONTROL Trait Graph] verzameling met de opgevulde populatie bij binnen 48 uur na het maken van de eigenschap.

## Limiet voor achteruitvullen {#trait-backfilling-limit}

[!UICONTROL Data Explorer] staat u toe om tot 50 eigenschappen per maand terug te vullen, met de backfill teller wordt teruggesteld op de 1 dag van elke maand.

>[!NOTE]
>
>De quota voor het terugvullen van de tonijn worden niet overgedragen van de vorige maanden. Bijvoorbeeld, als u 30 eigenschappen deze maand terugvult, wordt het quotum van de standaard backfill voor de volgende maand teruggesteld aan 50, niet 70.

## Gevolgen voor de verslaglegging {#reporting-impact}

De achtergevulde het eigenlijke realisaties worden weerspiegeld in de [!UICONTROL Unique Trait Realizations] en [!UICONTROL Total Trait Population] metriek, aangezien [!DNL Audience Manager] verandert historische signalen in tekrealisaties.

Nochtans, [!UICONTROL Trait Graph], [!UICONTROL General Reports]en [!UICONTROL Trend Reports] niet met terugwerkende kracht bijgewerkt met historische metriek die vóór de datum van de eigenschapverwezenlijking worden teruggevuld.