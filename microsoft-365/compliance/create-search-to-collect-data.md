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
description: ''
ms.openlocfilehash: 47d30cb2da91eff1260ffcf07838bd066917b4a1
ms.sourcegitcommit: dcea75af89f5f80ec6670346ee176407e043de54
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/12/2020
ms.locfileid: "42610646"
---
# <a name="create-a-search"></a>Создание поискового запроса

На вкладке **поиски** можно создать новый поиск, нажав кнопку **Новый поиск** и следуя инструкциям мастера.

![Мастер поиска в расширенном случае обнаружения электронных данных](../media/AeDSearch1.png)

## <a name="name-the-search-and-give-it-a-description"></a>Назовите Поиск и присвойте ему описание

Каждый Поиск с обращением должен иметь уникальное имя. При необходимости можно ввести описание поиска. 

## <a name="choose-the-custodians-and-custodial-locations-to-search"></a>Выбор расположений custodians и кустодиал для поиска

Выберите хранитель расположения контента для поиска, указав, что к этому случаю добавляется custodians. Выбрав хранитель, вы будете выполнять поиск по всем источникам данных, сопоставленным с хранитель. Кроме того, существует возможность сужения поиска до выбранных источников данных для каждого хранитель. Дополнительные сведения о том, как добавлять custodians и управлять их источниками данных, приведены [в статье работа с custodians](managing-custodians.md).

## <a name="choose-non-custodial-locations"></a>Выбор расположений, не являющихся кустодиалми

В некоторых случаях может потребоваться поиск в источниках данных, не связанных с хранитель. В этом случае можно указать расположения для поиска или выбрать поиск по всем расположениям для определенной службы Office 365 (например, поиск по всем почтовым ящикам Exchange или всем сайтам SharePoint и учетным записям OneDrive).

## <a name="define-the-search-query-and-conditions"></a>Определение запроса и условий поиска

Вы можете определить запрос ключевых слов и условия поиска с помощью встроенных карточек условий или с помощью языка запросов по ключевым словам (KQL). Более подробную информацию можно узнать в статье [Создание поисковых запросов](building-search-queries.md).
