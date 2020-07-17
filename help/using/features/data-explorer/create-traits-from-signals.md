---
description: Maak nieuwe kenmerken van alle signalen, inclusief de signalen die al worden gebruikt in kenmerken, en leg toekomstige doelgroepen vast die in aanmerking komen na het maken van sporen.
seo-description: Maak nieuwe kenmerken van alle signalen, inclusief de signalen die al worden gebruikt in kenmerken, en leg toekomstige doelgroepen vast die in aanmerking komen na het maken van sporen.
seo-title: Eigenschappen maken van signalen
title: Eigenschappen maken van signalen
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
translation-type: tm+mt
source-git-commit: e05eff3cc04e4a82399752c862e2b2370286f96f
workflow-type: tm+mt
source-wordcount: '359'
ht-degree: 3%

---


# Eigenschappen maken van signalen

Maak nieuwe kenmerken van alle signalen, inclusief de signalen die al worden gebruikt in kenmerken, en leg toekomstige doelgroepen vast die in aanmerking komen na het maken van sporen. Bekijk de video voor een snelle demonstratie of lees de video voor gedetailleerde informatie:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Traits maken van het dashboard voor handtekeningen {#create-traits-from-signal-dashboard}

Met [!UICONTROL Signal Dashboard] deze opdracht kunt u nieuwe kenmerken maken van de opgeslagen zoekopdrachten [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals]en de opgeslagen zoekopdrachten.

Wanneer u een nieuw bezit creeert, is het trektype vooraf ingesteld gebaseerd op het signaaltype:

* **[!UICONTROL Rule-based]** karakteristieken voor realtime signalen, actioneerbare logbestanden en [!DNL Adobe Analytics] signalen;

* **[!UICONTROL Onboarded]** kenmerken voor aan boord genomen signalen.

Als u nieuwe kenmerken wilt maken van het object, identificeert u het signaal dat u wilt gebruiken in het kenmerk **[!UICONTROL Signal Dashboard]** en klikt u op de bijbehorende **[!UICONTROL Create Rule-Based Trait]** of **[!UICONTROL Create Onboarded Trait]** koppeling.

![](assets/signals-create-trait.png)

U wordt omgeleid naar de **[Trait Builder](../../features/traits/about-trait-builder.md)**om uw nieuwe eigenschap(pen) te maken.

## Traits maken van signaalzoekopdracht {#create-traits-from-signal-search}

Maak kenmerken op basis van gebruikte of ongebruikte signalen die niet in de [!UICONTROL Signal Dashboard]code worden weergegeven.

Zoek naar specifieke signalen en creeer op regel-gebaseerde of ongebogen eigenschappen die op de resultaten worden gebaseerd. Dit doet u als volgt:

1. Ga naar **[!UICONTROL Audience Data > Signals > Search]** en stel een onderzoek in dat op de zeer belangrijk-waardeparen wordt gebaseerd die u zoekt, of klik **[!UICONTROL Search]** zonder een zeer belangrijk-waardepaar in te gaan om alle resultaten te tonen.
2. Identificeer de signalen die u in het bezit, in de resultatenlijst wilt gebruiken.
   * Als u een kenmerk wilt maken van één signaal, klikt u op de bijbehorende **[!UICONTROL Create Rule-Based Trait]** of **[!UICONTROL Create Onboarded Trait]** koppeling.
   * Als u een eigenschap wilt maken van meerdere signalen, klikt u op het bijbehorende selectievakje van elk signaal en vervolgens klikt u **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >U kunt eigenschappen van signalen van het zelfde type slechts tot stand brengen. U kunt geen eigenschap tot stand brengen die op een combinatie van een signaal in real time en aan boord wordt gebaseerd.
   >
   > ![](assets/signals-create-trait-search.png)
   >U kunt ook eigenschappen maken van gebruikte signalen. Signalen die al in kenmerken worden gebruikt, hebben het aantal kenmerken dat in de **[!UICONTROL Included in Traits]** kolom wordt weergegeven. Klik op de pijl om de kenmerken weer te geven die het signaal bevatten.
   >
   >![](assets/signals-used-traits.png)

3. Met de **[Trait Builder](../../features/traits/about-trait-builder.md)**kunt u nieuwe kenmerken maken.
