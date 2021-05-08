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
ms.openlocfilehash: 79e1596288836770c720cb312580fc706bb7b95f
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286254"
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

- Используйте центр администрирования Microsoft 365 для создания нового почтового ящика. Рекомендуется использовать 30-дневную политику хранения. Используйте имя Кортана в основном SMTP-адресе почтового ящика. Рекомендуется использовать такие имена, как Cortana@yourdomain.com, CortanaScheduler@contoso.com или Cortana.Scheduler@yourdomain.com.
- Свяжитесь с корпорацией Майкрософт (scheduler_m365@microsoft.com), чтобы включить почтовый ящик Кортаны. 

> [!IMPORTANT]
> Чтобы настроить почтовый ящик Кортаны для использования службы Scheduler, необходимо связаться с Корпорацией Майкрософт, чтобы он scheduler_m365@microsoft.com. Включение почтового ящика Кортаны может занять до двух недель.

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
