---
title: Разрешения на функции в службе EOP
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 1/30/2018
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: 34674847-a6b7-4a7e-9eaa-b64f22bc150d
description: Разрешения, необходимые для выполнения задач по управлению службой Microsoft Exchange Online Protection (EOP), зависят от управляемых функций.
ms.openlocfilehash: e3b41ea2b58397a9af2a1cb8ba979b5f816b416b
ms.sourcegitcommit: 70e920f76526f47fc849df615de4569e0ac2f4be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/07/2019
ms.locfileid: "38031914"
---
# <a name="feature-permissions-in-eop"></a>Разрешения на функции в службе EOP

Разрешения, необходимые для выполнения задач по управлению Exchange Online Protection (EOP), зависят от компонента, который вы управляете.

Для настройки EOP ваша ученая запись должна обладать правами глобального администратора Office 365 или администратора компании Exchange (группа ролей управления организацией).

## <a name="exchange-online-protection-permissions"></a>Разрешения Exchange Online Protection

Чтобы узнать, какие нужны разрешения для управления функциями EOP, обратитесь к таблице ниже. Если для функции указано несколько групп ролей, то для ее использования достаточно относиться к одной из этих групп.

|**Функция**|**Необходимые разрешения**|
|:-----|:-----|
|Функции защиты от вредоносных программ|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Управление санацией](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Защита от нежелательной почты|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Управление санацией](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Правила потока обработки почты|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Records Management](https://technet.microsoft.com/library/0e0c95ce-6109-4591-b86d-c6cfd44d21f5.aspx)|
|Домены|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Advanced Threat protection (ATP)|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [Управление санацией](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Соединители Office 365|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Трассировка сообщений|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx)|
|Конфигурация организации|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)|
|Карантин|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Пользователи, контакты и группы ролей|[Управление организацией](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Группы рассылки и группы безопасности|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx) <br/> [View-Only Organization Management](https://technet.microsoft.com/library/c514c6d0-0157-4c52-9ec6-441d9a30f3df.aspx) <br/> [Hygiene Management](https://technet.microsoft.com/library/fc0a9ec2-9c3d-42f6-8442-8603fb29d464.aspx)|
|Просмотр отчетов|[Organization Management](https://technet.microsoft.com/library/0bfd21c1-86ac-4369-86b7-aeba386741c8.aspx)  у пользователей есть доступ к отчетам по защите электронной почты.  <br/> [View-Only Recipients](https://technet.microsoft.com/library/37e66b92-81d3-412f-b7a9-e1bb8cbeb468.aspx)  у пользователей есть доступ к отчетам о защите почты.  <br/> [Compliance Management](https://technet.microsoft.com/library/b91b23a4-e9c7-4bd0-9ee3-ec5cb498da15.aspx)  у пользователей есть доступ к отчетам по защите электронной почты и отчетам защиты от потери данных (DLP) (если их подписка поддерживает возможности DLP).|
