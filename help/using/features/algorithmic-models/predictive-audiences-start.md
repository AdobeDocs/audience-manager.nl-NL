---
description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-description: Met Predictieve doelgroepen kunt u onbekende doelgroepen in real time indelen in verschillende persona's aan de hand van datawetenschap.
seo-title: Voorspelend publiek beheren
solution: Audience Manager
title: Predictieve doelgroepen in Audience Manager
feature: Algorithmic Models
translation-type: tm+mt
source-git-commit: 48bf17a2899fd06c525ba6b4fddb9ec805efb5c3
workflow-type: tm+mt
source-wordcount: '571'
ht-degree: 7%

---


# Aan de slag met Predictieve doelgroepen {#predictive-audiences-getting-started}

>[!IMPORTANT]
>Dit artikel bevat productdocumentatie die u door de opstelling en het gebruik van deze eigenschap moet begeleiden. Niets in dit document is juridisch advies. Raadpleeg uw eigen juridisch adviseur voor juridische begeleiding.

## Model {#create-predictive-audiences} voor voorspellend publiek maken

Voordat u een [!UICONTROL Predictive Audiences]-model maakt, moet u bepalen aan welke gegevensbron van de eerste partij u de [!UICONTROL Predictive Audiences]-kenmerken en -segmenten wilt toewijzen. U kunt een bestaande bron van eerste-partijgegevens gebruiken, of nieuwe creëren. Zie [Gegevensbronnen beheren](https://docs.adobe.com/content/help/en/audience-manager/user-guide/features/data-sources/manage-datasources.html) voor meer informatie over het maken van een nieuwe gegevensbron van de eerste partij.

Volg de onderstaande stappen als u weet welke gegevensbron u wilt gebruiken.

1. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
1. Klik in de sectie [!UICONTROL Predictive Audiences] op **[!UICONTROL Add New]**.

   ![smart-persona-add](assets/predictive-audiences-add.png)

1. Definieer vervolgens de personen waarop u de doelgroep wilt classificeren. U kunt dit doen door of eigenschappen of segmenten te kiezen om persona&#39;s van te bouwen. Gebruik de tabbladen [!UICONTROL Traits] en [!UICONTROL Segments] in de linkerbovenhoek van het scherm om te schakelen tussen uw trait- en segmentcatalogus. Nadat u de kenmerken of segmenten hebt geïdentificeerd die u als personen wilt gebruiken, klikt u op het bijbehorende pictogram **[!UICONTROL Add]** in de kolom [!UICONTROL Action].
   ![smart-persona-select-personas](assets/predictive-audiences-persona.png)
   >[!NOTE]
   >U moet een minimum van of twee eigenschappen of twee segmenten voor uw basislijnpersona&#39;s kiezen. U kunt geen combinatie van zowel kenmerken als segmenten gebruiken.
1. Klik **[!UICONTROL Next]** nadat u uw persona&#39;s hebt bepaald.
1. Selecteer vervolgens het publiek van de eerste partij dat u wilt classificeren door een eersteklas kenmerk of segment voor dit publiek te kiezen. Gebruik de tabbladen [!UICONTROL Traits] en [!UICONTROL Segments] in de linkerbovenhoek van het scherm om te schakelen tussen de catalogus met kenmerken en segmenten. Selecteer de eigenschap of het segment van de eerste partij die u als uw publiek wilt gebruiken, om het aan het model toe te voegen.
   ![smart-persona-select-publiek](assets/predictive-audiences-audience.png)
1. Klik **[!UICONTROL Next]** nadat u uw publiek hebt gekozen.
1. Vul de modelgegevens in:
   * **[!UICONTROL Model Name]**: Voer een beschrijvende naam in voor het model, zodat u het later kunt herkennen. De namen van de segmenten die door het model worden gegenereerd, beginnen met de naam van het model.
   * **[!UICONTROL Description]**: Voer een beschrijving in van het model dat u helpt bij het identificeren van het gebruikte hoofdlettergebruik.
   * **[!UICONTROL Data Source]**: Selecteer de eerste gegevensbron waaraan u de  [!UICONTROL Predictive Audiences] segmenten van dit model wilt toewijzen.
   * **[!UICONTROL Profile Merge Rule]**: Selecteer het model  [!UICONTROL Profile Merge Rule] dat moet worden toegewezen voor alle voorspellende  [!UICONTROL segments] elementen die door dit model worden gemaakt. Als uw geselecteerde doelpubliek [!UICONTROL segment] is, adviseren wij het zelfde [!UICONTROL Profile Merge Rule] van het doelpubliek te selecteren.
      ![voorspellend publiek-sparen](assets/predictive-audiences-save.png)
1. Klik op **[!UICONTROL Save]**.

## Predictive Audience Models {#clone-predictive-audiences} klonen en bewerken

Audience Manager biedt geen ondersteuning voor het bewerken van bestaande [!UICONTROL Predictive Audiences]-modellen. Als u de configuratie van een model wilt wijzigen, kunt u een kloon van een bestaand model maken en bewerken. Zo kunt u dit doen:

1. Ga naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**.
2. Klik op de naam van het model [!UICONTROL Predictive Audiences] dat u wilt klonen.
3. Klik op de knop **[!UICONTROL Clone]** linksboven in het scherm.
   ![voorspellend publiek-kloon](assets/predictive-audiences-clone.png)
4. Nadat u het model hebt gekloond, gaat u naar de pagina [!DNL Save & Configure] van het gekloonde model. In deze pagina, kunt u [!UICONTROL data source] en toegewezen [!UICONTROL Profile Merge Rule] van het model veranderen. Als u de personen en het doelpubliek van het gekloonde model wilt bewerken, gebruikt u de knoppen [!UICONTROL Back] en [!UICONTROL Next] om tussen de drie tabbladen te navigeren of klikt u op de drie tabnamen

   ![voorspellend publiek-kloonnavigatie](assets/predictive-audiences-clone-navigate.png)

5. Wanneer u klaar bent met het bewerken van een model, klikt u op **[!UICONTROL Save]**.

## Voorspelend publiek verwijderen {#delete-predictive-audiences}

Als u een [!UICONTROL Predictive Audiences]-model wilt verwijderen, gaat u naar **[!UICONTROL Audience Data]** > **[!UICONTROL Models]**, zoekt u het model dat u wilt verwijderen en klikt u op het pictogram **[!UICONTROL Delete]**.
