---
description: De realisaties van het terugvullingsspoor om historische publiek te vangen en verlies van relevante gegevens te vermijden voorafgaand aan een de aanmaakdatum van het spoor.
seo-description: Backfill trait realizations to capture historical audiences and avoid loss of relevant data prior to a trait creation date.
seo-title: Backfill Trait Realizations
title: Redalisaties achtergrondvulling
uuid: 8b0ef4e6-d16a-4d1d-94f1-b84eebffa9a5
feature: Data Explorer
exl-id: 6be54999-eeeb-48cd-a630-021f17289431
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '441'
ht-degree: 0%

---

# Redalisaties achtergrondvulling {#backfill-trait-realizations}

De realisaties van het terugvullingsspoor om historische publiek te vangen en verlies van relevante gegevens te vermijden voorafgaand aan een de aanmaakdatum van het spoor.

>[!IMPORTANT]
>
>[!UICONTROL Data Explorer Trait Backfill] is een premiumfunctie die de Audience Manager-ervaring vergroot door extra gebruiksgevallen te ontgrendelen. Back-up vereist extra verwerkingskracht en is tegen hogere kosten beschikbaar voor alle Audience Manager-klanten. Neem contact op met je Adobe-verkoper voor meer informatie.

Wanneer u eigenschappen van ongebruikte signalen creeert, kunt u verkiezen om de karakterrealisaties over een specifieke periode te herhalen. [!DNL Audience Manager] legt de historische gegevens vast over het publiek dat in aanmerking komt voor het nieuwe kenmerk en slaat deze op in het corresponderende profiel. U kunt **[!UICONTROL Backfill Options]** in de [!UICONTROL Trait Expression] sectie van **[Trait Builder](../../features/traits/about-trait-builder.md)** zien.

>[!NOTE]
>
>U kunt de verwezenlijking van de het vullingseigenschap voor regel-gebaseerde en ongebogen eigenschappen terugvullen.

Hieronder wordt beschreven hoe u de gemaakte fouten kunt terugvullen:

1. Ga naar [!UICONTROL Audience Data > Signals > Search] en stel een Signalen Onderzoek in werking of gebruik het [&#x200B; Signals Dashboard &#x200B;](../../features/data-explorer/data-explorer-signals-dashboard.md) om de signalen te identificeren in het nieuwe bezit te gebruiken.
1. Maak een nieuw kenmerk op basis van de gewenste signalen.
1. Gebruik **[!UICONTROL Backfill Options]** in de **[!UICONTROL Trait Expression]** sectie om het tijdinterval te selecteren waarvoor u de resultaten van de eigenschap wilt terugvullen. Vooraf gedefinieerde backfill-intervallen zijn 1, 7, 14 en 30 dagen. U kunt ook een aangepast datumbereik van maximaal 30 dagen kiezen.

   ![&#x200B; spoor-terugvulling &#x200B;](assets/signals-trait-backfill.png)

1. (Optioneel) Klik op **[!UICONTROL Estimate Realizations]** in de sectie **[!UICONTROL Estimated Trait Realizations]** om de geschatte [!UICONTROL Unique Trait Realizations] en [!UICONTROL Total Trait Population] waarden voor de teruggevulde eigenschap in de afgelopen 7 dagen te bekijken.

   ![&#x200B; raming-eigenschap-realisaties &#x200B;](assets/estimate-trait-realizations.png)

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

Nieuwe traits maken het publiek twee tot drie uur na het maken vast. Vanwege het grote gegevensvolume dat [!DNL Audience Manager] dagelijks uitvoert, wordt de populatie met teruggevulde gegevens echter niet direct weerspiegeld in de [!UICONTROL Unique Trait Realizations] - en [!UICONTROL Total Trait Population] -grafieken.

Audience Manager werkt [!UICONTROL Trait Graph] binnen 48 uur na het maken van de eigenschap bij met de populatie met terugwerkende kracht.

## Limiet voor achteruitvullen {#trait-backfilling-limit}

In [!UICONTROL Data Explorer] kunt u tot 50 kenmerken per maand terugzetten, waarbij de terugvullingteller op de 1 dag van elke maand wordt teruggezet.

>[!NOTE]
>
>De quota voor het terugvullen van de tonijn worden niet overgedragen van de vorige maanden. Bijvoorbeeld, als u 30 eigenschappen deze maand terugvult, wordt het quotum van de standaard backfill voor de volgende maand teruggesteld aan 50, niet 70.

## Gevolgen voor de verslaglegging {#reporting-impact}

De gerealiseerde resultaten van een teruggevuld kenmerk worden weerspiegeld in de metriek [!UICONTROL Unique Trait Realizations] en [!UICONTROL Total Trait Population] , aangezien [!DNL Audience Manager] historische signalen omzet in realisaties van het kenmerk.

De [!UICONTROL Trait Graph], [!UICONTROL General Reports] en [!UICONTROL Trend Reports] worden echter niet retroactief bijgewerkt met historische meetgegevens die zijn teruggevuld vóór de aanmaakdatum van de eigenschap.
