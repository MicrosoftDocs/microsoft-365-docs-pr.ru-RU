---
title: Сведения о политике защиты от потери данных по умолчанию в Microsoft Teams (предварительная версия)
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: Сведения о политике предотвращения потери данных по умолчанию в Microsoft Teams
ms.openlocfilehash: 0663c370373708009346d4f858729e17436f0f62
ms.sourcegitcommit: 05f40904f8278f53643efa76a907968b5c662d9a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/30/2021
ms.locfileid: "52114147"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Сведения о политике защиты от потери данных по умолчанию в Microsoft Teams (предварительная версия)

[Возможности предотвращения](dlp-learn-about-dlp.md) потери данных были расширены для Microsoft Teams сообщений чата и каналов, включая сообщения частных каналов. В рамках этого выпуска мы создали политику DLP по умолчанию для первых клиентов центра соответствия требованиям.

## <a name="applies-to"></a>Область применения

Любой клиент, который имеет одну или несколько лицензий ниже и имеет активных Teams пользователей
 
- ME5, 
- MA5, 
- Соответствие требованиям E5/A5, 
- IP+G, 
- OE5, 
- O365 Advanced Compliance 
- EMS E5


## <a name="what-does-the-default-policy-do"></a>Что делает политика по умолчанию?

Политика DLP по умолчанию отслеживает все номера кредитных карт, общие внутри организации и внешне. Эта политика по умолчанию для всех пользователей клиента. Он не создает никаких советов по политике для конечных пользователей, но создает событие Оповещения, а также вызывает сообщение с низкой степенью серьезности администратору (добавлено в политику). Администратор может просматривать действия и изменять сведения о политиках, входя в центр соответствия требованиям.

Администраторы могут просматривать эту политику на странице [>](https://compliance.microsoft.com/compliancesettings) политики защиты от потери данных.


> [!div class="mx-imgBorder"]
> ![политика Teams DLP](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Изменение или удаление политики по умолчанию

Чтобы [изменить политику по умолчанию для улучшения](create-test-tune-dlp-policy.md#tune-a-dlp-policy)производительности или удалить ее, просто используйте учетную запись с разрешениями управления соответствием требованиям **DLP.** Дополнительные сведения см. в ["Разрешениях".](create-test-tune-dlp-policy.md#permissions)

