---
title: Сведения о политике предотвращения потери данных по умолчанию в Microsoft Teams (предварительный просмотр)
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
ms.openlocfilehash: 3992daf9431dbd87ed5e947a1e5a2b0acd20edce
ms.sourcegitcommit: 450661071e44854f0a0a92af648f76d907767b71
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2021
ms.locfileid: "50826250"
---
# <a name="learn-about-the-default-data-loss-prevention-policy-in-microsoft-teams-preview"></a>Сведения о политике предотвращения потери данных по умолчанию в Microsoft Teams (предварительный просмотр)

[Возможности по предотвращению](data-loss-prevention-policies.md) потери данных (DLP) расширены, включив сообщения чатов и каналов Microsoft Teams, включая сообщения частных каналов. В рамках этого выпуска мы создали политику DLP по умолчанию для первых клиентов центра соответствия требованиям.

## <a name="applies-to"></a>Область применения

Любой клиент, который имеет лицензию с одной или более ниже лицензий и имеет активных пользователей Teams
 
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
> ![Политика DLP команд по умолчанию](../media/default-teams-dlp-policy.png)

## <a name="edit-or-delete-the-default-policy"></a>Изменение или удаление политики по умолчанию

Чтобы [изменить политику по умолчанию для улучшения](create-test-tune-dlp-policy.md#tune-a-dlp-policy)производительности или удалить ее, просто используйте учетную запись с разрешениями управления соответствием требованиям **DLP.** Дополнительные сведения см. в ["Разрешениях".](create-test-tune-dlp-policy.md#permissions)

