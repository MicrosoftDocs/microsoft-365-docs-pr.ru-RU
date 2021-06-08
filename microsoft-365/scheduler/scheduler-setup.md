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
ms.openlocfilehash: c17cdbbf71359a2725a3b0a145cba5feffd7c853
ms.sourcegitcommit: e1e275eb88153bafddf93327adf8f82318913a8d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52809195"
---
# <a name="setting-up-scheduler-for-microsoft-365"></a>Настройка scheduler для Microsoft 365

Чтобы настроить планировщик для Microsoft 365, необходимо следующее:

|**Что мне нужно?** |**Описание** |
|-------------------|-------------|
|Почтовый ящик Кортаны |Администраторам клиентов необходимо настроить почтовый ящик в качестве почтового ящика "Кортана" (то есть cortana@yourdomain.com).         |
|Почтовый ящик Exchange Online |Пользователи должны иметь Exchange Online и календарь         |
|Лицензия планировщика |Сведения о лицензировании и ценах [см.](https://www.microsoft.com/microsoft-365/meeting-scheduler-pricing)в Microsoft 365.        |

## <a name="create-a-mailbox-for-cortana"></a>Создание почтового ящика для Кортаны
Почтовый Exchange в клиенте выступает в качестве почтового ящика Кортаны для клиента для отправки и получения сообщений электронной почты в Кортану и из нее. Все электронные письма, отправленные в Кортана, сохраняются в почтовом ящике кортаны клиента на основе политики хранения.

- Используйте центр администрирования Microsoft 365 для создания почтового ящика пользователя. Рекомендуется использовать 30-дневную политику хранения. 
- Используйте имя Кортана в основном SMTP-адресе почтового ящика. Рекомендуется использовать такие имена, как Cortana@yourdomain.com, CortanaScheduler@contoso.com или Cortana.Scheduler@yourdomain.com.

## <a name="designate-the-mailbox-as-the-scheduler-assistant"></a>Назначь почтовый ящик помощником планировщика

После создания уникального почтового ящика для календаря Кортаны необходимо назначить почтовый ящик Microsoft 365 формально. После того как вы назначите почтовый ящик Планер Кортаны, он будет доступен для расписания собраний от имени пользователей.

Чтобы назначить почтовый ящик Планиров Кортаны, авторизованный администратор должен запустить команду PowerShell с одной линией. 

1. Подключение для Microsoft 365 PowerShell для запуска пространства для вашей организации.
2. Запустите следующий скрипт PowerShell, чтобы назначить почтовый ящик для Scheduler:

```powershell

Set-mailbox cortana@contoso.com -SchedulerAssistant:$true

```

После запуска этой "наборной" команды в почтовом ящике Планиров кортаны на почтовом ящике установлен новый "PersistedCapability", чтобы отметить, что этот почтовый ящик является "SchedulerAssistant".

> [!NOTE]
> Выполните следующие действия, чтобы подключить организацию к PowerShell, если вы ранее этого не делали: Подключение Microsoft 365 [с PowerShell - Microsoft 365 корпоративный | Документы Майкрософт](../enterprise/connect-to-microsoft-365-powershell.md)

Чтобы узнать, какой почтовый ящик в организации в настоящее время задан в качестве помощника планиров Кортаны, запустите функцию get:
 
```powershell

Get-mailbox -Organization contoso.com | where {($_.PersistedCapabilities -like "SchedulerAssistant")}

```

> [!IMPORTANT]
> Чтобы выполнить полную подготовка к набору возможности SchedulerAssistant, почтовому ящику Scheduler может потребоваться до двух часов.

## <a name="exchange-online-mailbox"></a>Почтовый ящик Exchange Online
Scheduler — это надстройка для Microsoft 365. Организаторы собраний должны иметь Exchange Online почтовый ящик и календарь для работы scheduler.

## <a name="exchange-requirements"></a>Требования для Exchange

В дополнение к лицензированию Scheduler необходимо иметь одну из следующих лицензий:

- Microsoft 365 E3, A3, E5, A5
- Business Basic, Business, Business Standard, Business Premium
- Office 365 E1, A1, E3, A3, E5, A5
- Основные бизнес-Premium
- Exchange Online Лицензия plan 1 или Plan 2. 

> [!Note]
> **Планировка Microsoft 365** недоступна для пользователей Office 365 21Vianet в Китае. Он также не доступен для пользователей Microsoft 365 с немецким облаком, использующим доверяемого данным немецкого Telekom. Средство поддерживается для пользователей в Германии, чьи данные хранятся не в немецком центре обработки данных.
>
>Эта функция также не поддерживается для пользователей облака для государственных организаций, включая GCC, Consumer, GCC High и DoD.
