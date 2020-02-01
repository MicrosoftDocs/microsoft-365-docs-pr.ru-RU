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
ms.openlocfilehash: ab57bcd3cd21d691e8c2dc669a55588dbcaa886b
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41595556"
---
# <a name="create-a-search"></a>Создание поискового запроса

На вкладке **поиски** можно создать новый поиск, нажав кнопку **Новый поиск** и следуя инструкциям мастера.

## <a name="name-your-search-and-give-it-a-description"></a>Назовите Поиск и присвойте ему описание

Каждый Поиск с обращением должен иметь уникальное имя. При необходимости можно ввести описание поиска. 

## <a name="define-your-search-query-and-conditions"></a>Определение запросов и условий поиска

Вы можете определить запрос ключевых слов и условия поиска с помощью встроенных карточек условий или с помощью языка запросов по ключевым словам (KQL). Более подробную информацию можно узнать в статье [Создание поисковых запросов](building-search-queries.md).

## <a name="choose-the-custodians-to-search-from"></a>Выбор custodians для поиска

Определив условия, необходимо выбрать расположения, в которых будет выполняться поиск. Один из способов сделать это — указать, какие custodians вы уже добавили в тот случай, когда вы хотите выполнить поиск. Выбрав хранитель, вы будете выполнять поиск по всем источникам данных, сопоставленным с хранитель. Для получения дополнительных сведений о том, как добавить custodians к своему случаю и управлять их источниками данных, ознакомьтесь со статьей [Working with custodians](managing-custodians.md) .

## <a name="choose-non-custodial-locations"></a>Выбор расположений, не являющихся кустодиалми

В некоторых случаях может потребоваться поиск в источниках данных, которые не сопоставлены с хранитель. В этом случае можно указать расположения, в которых требуется выполнить поиск, или выбрать поиск по всем расположениям для определенной службы Office 365 (например, поиск по всем почтовым ящикам Exchange или всем сайтам SharePoint и OneDrive для бизнеса).