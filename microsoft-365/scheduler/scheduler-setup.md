---
title: Настройка scheduler для Microsoft 365.
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: Настройка scheduler для Microsoft 365.
ms.openlocfilehash: 924b25e3d921f402c97632f7475ed5beea98d5c7
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362550"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Настройка планировщика для Microsoft 365


Чтобы настроить планировщик для Microsoft 365, необходимо следующее:

| Что мне нужно? | Описание |
|-------------------|-------------|
|Кортана почтовый ящик |Администраторам клиента необходимо настроить почтовый ящик в качестве почтового ящика "Кортана" (то есть cortana@yourdomain.com).         |
|Почтовый ящик Exchange Online |Пользователи должны иметь Exchange Online и календарь         |
|Лицензия планировщика |Сведения о лицензировании и ценах [см.](https://www.microsoft.com/en-us/microsoft-365/meeting-scheduler-pricing)в Microsoft 365.        |

## <a name="create-a-mailbox-for-cortana"></a>Создание почтового ящика для Кортана

Почтовый Exchange в клиенте выступает в качестве Кортана для клиента для отправки и получения сообщений электронной почты в Кортана. Все электронные сообщения, отправленные Кортана, сохраняются в почтовом ящике Кортана клиента на основе политики хранения.

- Используйте Центр администрирования Microsoft 365 для создания почтового ящика пользователя. Рекомендуется использовать 30-дневную политику хранения. 
- Используйте имя Кортана в основном SMTP-адресе почтового ящика. Такие имена, как "Кортана@yourdomain.com", "CortanaScheduler@contoso.com", "Кортана". Scheduler@yourdomain.com рекомендуется.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Назначь почтовый ящик помощником планировщика

После создания уникального почтового ящика Кортана scheduler необходимо назначить почтовый ящик для Microsoft 365. После того как вы назначите Кортана scheduler, он будет доступен для расписания собраний от имени пользователей.

Чтобы назначить Кортана scheduler, авторизованный администратор должен запустить команду PowerShell с одной линией. 

1. Подключение для Microsoft 365 PowerShell для запуска пространства для вашей организации.

2. Запустите следующий скрипт PowerShell, чтобы назначить почтовый ящик для Scheduler:

    ```powershell
    Set-mailbox cortana@contoso.com -SchedulerAssistant:$true
    ```
    
    После запуска этой команды "set" в почтовом ящике Кортана Scheduler на почтовом ящике установлена новая "PersistedCapability", чтобы отметить, что этот почтовый ящик является "SchedulerAssistant".

> [!NOTE]
> Выполните следующие действия, чтобы подключить организацию к PowerShell, если вы не сделали этого ранее: Подключение Microsoft 365 [с PowerShell](../enterprise/connect-to-microsoft-365-powershell.md).

Чтобы узнать, какой почтовый ящик в организации в настоящее время Кортана помощником по расписанию, запустите функцию get:

```powershell
Get-mailbox | where {$_.PersistedCapabilities -Match "SchedulerAssistant"}
```

> [!IMPORTANT]
> Чтобы выполнить полную подготовка к набору возможности SchedulerAssistant, почтовому ящику Scheduler может потребоваться до двух часов.

## <a name="exchange-online-mailbox"></a>Почтовый ящик Exchange Online
Лицензия Scheduler — это надстройка для Microsoft 365, которая позволяет организатору собраний делегировать свои задачи планирования собраний своему помощнику-планировщику. Для работы scheduler, как правило, Microsoft 365 лицензии, организаторам собраний требуются следующие компоненты:

- Почтовый ящик, назначенный в качестве почтового ящика помощника планировщика
- Лицензия планировщика
- Exchange Online почтовый ящик и календарь

Участникам собрания не требуется лицензия scheduler или Microsoft 365.

## <a name="scheduler-end-user-license-requirements"></a>Требования к лицензии конечных пользователей scheduler

Лицензия scheduler требует одну из следующих лицензий:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Основные бизнес-Premium
- Exchange Online Лицензия plan 1 или Plan 2. 

> [!Note]

> Планировщик Microsoft 365 доступен в разных средах на английском языке. **Планировка Microsoft 365** недоступна пользователям:

- Microsoft 365 21Vianet в Китае
- Microsoft 365 с немецким облаком, использующим доверителем данных немецкий Telekom
- Облако правительства, включая GCC, consumer, GCC high или DoD

Планировщик поддерживает пользователей в Германии, расположение данных которых не находится в немецком центрах обработки данных.
