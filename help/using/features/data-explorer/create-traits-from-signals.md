---
description: Maak nieuwe kenmerken van alle signalen, inclusief de signalen die al worden gebruikt in kenmerken, en leg toekomstige doelgroepen vast die in aanmerking komen na het maken van sporen.
seo-description: Create new traits from all signals, including those that are already used in traits, and capture future audiences that qualify after trait creation.
seo-title: Create Traits from Signals
title: Eigenschappen maken van signalen
uuid: 4f324404-0c24-4e3b-96c1-7c1b28a4536d
feature: Data Explorer
exl-id: 14308ef0-58eb-4b76-858c-d0da560f55fd
source-git-commit: 4d3c859cc4dc5294286680b0e63c287e0409f7fd
workflow-type: tm+mt
source-wordcount: '332'
ht-degree: 2%

---

# Eigenschappen maken van signalen

Maak nieuwe kenmerken van alle signalen, inclusief de signalen die al worden gebruikt in kenmerken, en leg toekomstige doelgroepen vast die in aanmerking komen na het maken van sporen. Bekijk de video voor een snelle demonstratie of lees de video voor gedetailleerde informatie:

>[!VIDEO](https://video.tv.adobe.com/v/25169/?quality=12)

## Traits maken van het dashboard voor handtekeningen {#create-traits-from-signal-dashboard}

De [!UICONTROL Signal Dashboard] kunt u nieuwe kenmerken maken op basis van de [!UICONTROL Top Unused Signals], [!UICONTROL New Unused Signals]en uw opgeslagen zoekopdrachten.

Wanneer u een nieuw bezit creeert, is het trektype vooraf ingesteld gebaseerd op het signaaltype:

* **[!UICONTROL Rule-based]** de kenmerken voor signalen in real time, actionable logboekdossiers en [!DNL Adobe Analytics] signalen;

* **[!UICONTROL Onboarded]** kenmerken voor aan boord genomen signalen.

Om nieuwe eigenschappen van te creëren **[!UICONTROL Signal Dashboard]**, identificeert het signaal dat u in het bezit wilt gebruiken, dan klik het overeenkomstige **[!UICONTROL Create Rule-Based Trait]** of **[!UICONTROL Create Onboarded Trait]** koppeling.

![](assets/signals-create-trait.png)

U wordt omgeleid naar de **[Trait Builder](../../features/traits/about-trait-builder.md)** om uw nieuwe eigenschap(pen) te maken.

## Traits maken van signaalzoekopdracht {#create-traits-from-signal-search}

Maak kenmerken op basis van gebruikte of ongebruikte signalen die niet worden weergegeven in het dialoogvenster [!UICONTROL Signal Dashboard].

Zoek naar specifieke signalen en creeer op regel-gebaseerde of ongebogen eigenschappen die op de resultaten worden gebaseerd. Dit doet u als volgt:

1. Ga naar **[!UICONTROL Audience Data > Signals > Search]** en voer een zoekopdracht uit op basis van de sleutelwaardeparen die u zoekt, of klik op **[!UICONTROL Search]** zonder een sleutelwaardepaar in te voeren om alle resultaten weer te geven.
2. Identificeer de signalen die u in het bezit, in de resultatenlijst wilt gebruiken.
   * Als u een kenmerk wilt maken van één signaal, klikt u op de bijbehorende **[!UICONTROL Create Rule-Based Trait]** of **[!UICONTROL Create Onboarded Trait]** koppeling.
   * Als u een kenmerk wilt maken van meerdere signalen, klikt u op het bijbehorende selectievakje van elk signaal en vervolgens klikt u op **[!UICONTROL Create Trait from Multiple Signals]**.

   >[!NOTE]
   >U kunt eigenschappen van signalen van het zelfde type slechts tot stand brengen. U kunt geen eigenschap tot stand brengen die op een combinatie van een signaal in real time en aan boord wordt gebaseerd.
   >
   > ![](assets/signals-create-trait-search.png)
   >U kunt ook eigenschappen maken van gebruikte signalen. Signalen die al in kenmerken worden gebruikt, hebben het aantal kenmerken dat in de **[!UICONTROL Included in Traits]** kolom. Klik op de pijl om de kenmerken weer te geven die het signaal bevatten.
   >
   >![](assets/signals-used-traits.png)

3. Gebruik de **[Trait Builder](../../features/traits/about-trait-builder.md)** om nieuwe kenmerken te maken.
