---
description: De detailspagina voor een individueel bezit verstrekt overzicht van informatie zoals de het handelsnaam, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit bepalen, segmenten het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar Audience Data > Traits en klikt u op de naam van het kenmerk waarmee u wilt werken.
seo-description: De detailspagina voor een individueel bezit verstrekt overzicht van informatie zoals de het handelsnaam, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit bepalen, segmenten het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar Audience Data > Traits en klikt u op de naam van het kenmerk waarmee u wilt werken.
seo-title: Detailpagina Trait
solution: Audience Manager
title: Detailpagina Trait
uuid: 23301376-c1cc-4778-b8c4-9831f6739db9
keywords: identity type breakdown, identity breakdown, audience identity reporting
translation-type: tm+mt
source-git-commit: 51f38819bfbc72c2588f63a63fb8ba2e963919ff

---


# Detailpagina van taak {#trait-details-page}

De detailspagina voor een individueel bezit verstrekt een overzicht van de karakterdetails, zoals de eigenschap, identiteitskaart, prestatiesmetriek, uitdrukkingen die het bezit, de segmenten bepalen het tot, en het logboek van de activiteitencontrole behoort. Als u deze details wilt weergeven, gaat u naar **[!UICONTROL Audience Data]** > **[!UICONTROL Traits]** en klikt u op de naam van het kenmerk waarmee u wilt werken.

## Trainingsbeheertools {#trait-management-tools}

Boven aan de pagina met details over het kenmerk staan de gereedschappen die u kunt gebruiken om uw kenmerken te beheren:

1. **[!UICONTROL Add New]**: Gebruik deze optie om nieuwe op regel-gebaseerde, algoritmische, of ongebogen eigenschappen tot stand te brengen.
2. **[!UICONTROL Edit]**: Gebruik deze optie om de configuratie van het huidige kenmerk te wijzigen.
3. **[!UICONTROL Delete]**: Gebruik deze optie om de huidige eigenschap uit uw account van Audience Manager te verwijderen.
4. **[!UICONTROL Marketplace Recommendations]**: Met deze optie kunt u vergelijkbare kenmerken vinden als de service die u bekijkt, aan de hand van [!UICONTROL Audience Marketplace] gegevenskosten waarop u zich niet hebt geabonneerd. Zie [Audience Marketplace for Data Buyers](../audience-marketplace/marketplace-data-buyers/marketplace-data-buyers.md) om te leren hoe u door de Marketplace kunt navigeren en vergelijkbare kenmerken kunt vinden.

![basisinformatie](assets/basic-trait-information.png)

## Informatie over spoor {#basics}

In de [!UICONTROL Trait Information] sectie vindt u details over de vereiste en optionele velden die u hebt ingevuld bij het maken van de eigenschap. Dit zijn onder andere het type eigenschap, de ID van de eigenschap, de beschrijving, de gegevensbron en andere metagegevens. Deze details variëren afhankelijk van het type van eigenschap (omslag, onboard, of op regel-gebaseerd).

## Grafiek {#trait-graph}

Het [!UICONTROL Trait Graph] biedt in één oogopslag prestatiemetriek voor uw geselecteerde kenmerk. Houd de cursor boven een trendlijn om aanvullende gegevens voor het geselecteerde kenmerk weer te geven.

[!UICONTROL Unique Trait Realizations] Hiermee wordt een aantal unieke gebruikers weergegeven die deze eigenschap binnen het opgegeven tijdbereik aan hun profiel hebben toegevoegd. Het [!UICONTROL Total Trait Population] geeft het aantal unieke gebruikers aan dat momenteel voor deze eigenschap in aanmerking komt.

* Voor op regel-gebaseerde eigenschappen, komt de vakkwalificatie in real time voor, aangezien de gebruikers voor een eigenschap in hun browser kwalificeren.
* Voor onboded eigenschappen, gebeurt de vakkwalificatie nadat een binnenkomend dossier wordt verwerkt, d.w.z. het binnenkomende dossier wordt [gevoerd in de Manager](../../faq/faq-inbound-data-ingestion.md) van de Publiek en dat is wanneer de vakkwalificatie gebeurt.
* **[!UICONTROL Unique Trait Realizations]**: Een aantal unieke gebruikers die deze eigenschap binnen het opgegeven tijdbereik aan hun profiel hebben toegevoegd.
* **[!UICONTROL Total Trait Population]**: Het aantal unieke gebruikers dat momenteel in aanmerking komt voor deze eigenschap.

   ![grafiek](assets/trait-summary.png)

* **[!UICONTROL Identity Type Breakdown]**: De eerste drie ingangen tonen de hoogste drie dwars-apparatengegevensbronnen met het hoogste populatietelling die voor het bezit, in dalende orde hebben gekwalificeerd. De vierde vermelding toont de som van alle andere [!DNL DPUUIDs] ([!DNL CRM IDs]) die voor het kenmerk in aanmerking komen, van de apparaatgegevensbronnen die zich niet in de bovenste drie bevinden. Dit rapport wordt alleen weergegeven als u Apparaatoverschrijdende id selecteert in het [!UICONTROL Show Results By] vervolgkeuzemenu rechtsboven op de pagina. De standaardoptie drop-down is, [!UICONTROL Device ID]waar dit rapport niet wordt getoond.

   ![grafiek](assets/trait-identity.png)
   > [!NOTE]
   > Audience Manager geeft het [!UICONTROL Identity Type Breakdown] rapport alleen weer als u id&#39;s voor alle apparaten hebt die zijn gekwalificeerd voor het kenmerk.

   >[!VIDEO](https://video.tv.adobe.com/v/27977/)

## Trainingsexpressie {#trait-expression}

In het [!UICONTROL Trait Expression] gedeelte ziet u aan welke criteria gebruikers moeten voldoen om in aanmerking te komen voor de eigenschap. Deze regels worden ingesteld wanneer u een kenmerk [maakt of bewerkt](../../features/traits/about-trait-builder.md).

![](assets/traitExpression.png)

## Trait Segments {#trait-segments}

In de [!UICONTROL Segments with this Trait] sectie worden alle segmenten weergegeven waartoe het geselecteerde kenmerk behoort. U kunt op een segmentnaam klikken om details over dat segment te zien.

![](assets/traitSegments.png)

## Logboek Traject-controle/historie {#trait-audit-history}

Voor op regel-gebaseerde en ongebogen eigenschappen, [!UICONTROL Trait Expression Change History] toont het u de laatste 10 veranderingen die aan de regels van de eigenschapuitdrukking worden aangebracht en wie hen aanbracht. Als uw eigenschap meer dan 10 veranderingen heeft, klik **[!UICONTROL Export to CSV]** om het volledige controlelogboek te downloaden. Het controlelogboek is niet beschikbaar voor omslag of algoritmische eigenschappen.

>[!NOTE]
>
>[!UICONTROL Not Available] in de [!UICONTROL By User] kolom betekent dat de account voor die gebruiker is verwijderd.

![](assets/traitHistory.png)