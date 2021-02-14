---
title: Создание поискового запроса
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: Узнайте, как создавать, определять и выбирать хранителей и расположения для поиска в случае Advanced eDiscovery.
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 1d9051824ff3f28484d0750b982edd70334a9b88
ms.sourcegitcommit: a45cf8b887587a1810caf9afa354638e68ec5243
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/05/2020
ms.locfileid: "44035771"
---
# <a name="create-a-search"></a>Создание поискового запроса

На **вкладке "Поиск"** в вашем случае можно создать новый поиск, нажав кнопку **"Создать поиск"** и следуя за мастером.

![Мастер поиска в случае Advanced eDiscovery](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>Назовем поиск и описаем его

Каждый поиск с делом должен иметь уникальное имя. При желании вы можете предоставить описание для поиска. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>Выбор хранителей и местоположений для поиска

Выберите расположения контента хранителей для поиска, указав, что хранители вы добавили в дело. Выбрав хранителя, вы будете запускать поиск по всем источникам данных, которые сонабираются с хранителями. Вы также можете сузить поиск до выбранных источников данных для каждого хранителя. Дополнительные сведения о добавлении хранителей и управлении их источниками данных см. в [подстройки "Работа с хранителями".](managing-custodians.md)

## <a name="choose-non-custodial-locations"></a>Выбор местоположений, не в которые не будет хранителя

В некоторых случаях может потребоваться поиск источников данных, не связанных с хранителями. В этом случае можно указать расположения для поиска или выбрать поиск во всех расположениях контента для определенной службы Майкрософт (например, поиск во всех почтовых ящиках Exchange, на всех сайтах SharePoint и в учетных записях OneDrive).

## <a name="define-the-search-query-and-conditions"></a>Определение поискового запроса и условий

Вы можете определить запрос ключевых слов и любые условия для поиска с помощью встроенных карточек условий или языка запросов по ключевым словам (KQL). Дополнительные сведения см. в [подстройки поисковых запросов.](building-search-queries.md)
