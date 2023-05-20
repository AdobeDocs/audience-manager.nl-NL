---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Predictive Audiences help you classify unknown audiences into distinct personas in real-time, using data science.
seo-title: Managing Predictive Audiences
solution: Audience Manager
title: Aan de slag met Predictieve doelgroepen
feature: Algorithmic Models
exl-id: beb314de-f679-4397-8e14-2dd6576243fd
source-git-commit: 319be4dade263c5274624f07616b404decb7066f
workflow-type: tm+mt
source-wordcount: '552'
ht-degree: 4%

---

# Aan de slag met Predictieve doelgroepen {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

## Een voorspellend model voor soorten publiek maken {#create-predictive-audiences}

Voordat u een [!UICONTROL Predictive Audiences] model, moet u beslissen welke bron van de eerste-partijgegevens u uw wilt toewijzen [!UICONTROL Predictive Audiences] kenmerken en segmenten tot. U kunt een bestaande bron van eerste-partijgegevens gebruiken, of nieuwe creëren. Zie [Gegevensbronnen beheren](https://experienceleague.adobe.com/docs/audience-manager/user-guide/features/data-sources/manage-datasources.html) voor details over hoe te om een nieuwe bron van de eerste-partijgegevens tot stand te brengen.

Volg de onderstaande stappen als u weet welke gegevensbron u wilt gebruiken.

1. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. In de [!UICONTROL Predictive Audiences] sectie, klikt u op **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definieer vervolgens de personen waarop u de doelgroep wilt classificeren. U kunt dit doen door of eigenschappen of segmenten te kiezen om persona&#39;s van te bouwen. Gebruik de [!UICONTROL Traits] en [!UICONTROL Segments] in de linkerbovenhoek van het scherm om te schakelen tussen de catalogus voor kenmerken en segmenten. Zodra u de eigenschappen of de segmenten hebt geïdentificeerd die u als persona&#39;s wilt gebruiken, klik het overeenkomstige **[!UICONTROL Add]** in het deelvenster [!UICONTROL Action] kolom.
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >U moet een minimum van of twee eigenschappen of twee segmenten voor uw basislijnpersona&#39;s kiezen. U kunt geen combinatie van zowel kenmerken als segmenten gebruiken.
1. Klikken **[!UICONTROL Next]** nadat je je persona&#39;s hebt gedefinieerd.
1. Selecteer vervolgens het publiek van de eerste partij dat u wilt classificeren door een eersteklas kenmerk of segment voor dit publiek te kiezen. Gebruik de [!UICONTROL Traits] en [!UICONTROL Segments] in de linkerbovenhoek van het scherm om te schakelen tussen de catalogus met eigenschappen en segmenten. Selecteer de eigenschap of het segment van de eerste partij die u als uw publiek wilt gebruiken, om het aan het model toe te voegen.
   ![smart-persona-select-publiek](assets/predictive-audiences-audience.png)
1. Klikken **[!UICONTROL Next]** nadat je je publiek hebt gekozen.
1. Vul de modelgegevens in:
   * **[!UICONTROL Model Name]**: Voer een beschrijvende naam in voor het model, zodat u het later kunt herkennen. De namen van de segmenten die door het model worden gegenereerd, beginnen met de naam van het model.
   * **[!UICONTROL Description]**: Voer een beschrijving in van het model dat u helpt bij het identificeren van het gebruikte hoofdlettergebruik.
   * **[!UICONTROL Data Source]**: Selecteer de eerste gegevensbron die u wilt [!UICONTROL Predictive Audiences] segmenten van dit model die moeten worden toegewezen aan.
   * **[!UICONTROL Profile Merge Rule]**: Selecteer [!UICONTROL Profile Merge Rule] toe te wijzen voor alle voorspellingen [!UICONTROL segments] gemaakt door dit model. Als uw geselecteerde doelpubliek een [!UICONTROL segment], adviseren wij het zelfde te selecteren [!UICONTROL Profile Merge Rule] van het doelpubliek.
      ![voorspellend publiek-sparen](assets/predictive-audiences-save.png)
1. Klik op **[!UICONTROL Save]**.

## Predictive Audience Models klonen en bewerken {#clone-predictive-audiences}

Audience Manager biedt geen ondersteuning voor het bewerken van bestaande [!UICONTROL Predictive Audiences] modellen. Als u de configuratie van een model wilt wijzigen, kunt u een kloon van een bestaand model maken en bewerken. Zo kunt u dit doen:

1. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Klik op de naam van de [!UICONTROL Predictive Audiences] model dat u wilt klonen.
3. Klik op de knop **[!UICONTROL Clone]** in de linkerbovenhoek van het scherm.
   ![voorspellend publiek-kloon](assets/predictive-audiences-clone.png)
4. Nadat u het model hebt gekloond, gaat u naar de [!DNL Save & Configure] pagina van het gekloonde model. Op deze pagina kunt u de [!UICONTROL data source] en de toegewezen[!UICONTROL Profile Merge Rule] van het model. Als u de personen en het doelpubliek van het gekloonde model wilt bewerken, gebruikt u de opdracht [!UICONTROL Back] en [!UICONTROL Next] om tussen de drie tabbladen te navigeren of klik op de drie tabnamen

   ![voorspellend publiek-kloonnavigatie](assets/predictive-audiences-clone-navigate.png)

5. Als u klaar bent met het bewerken van een model, klikt u op **[!UICONTROL Save]**.

## Voorspelend publiek verwijderen {#delete-predictive-audiences}

Een [!UICONTROL Predictive Audiences] model, ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, zoek het model dat u wilt verwijderen en klik op de knop **[!UICONTROL Delete]** pictogram.
