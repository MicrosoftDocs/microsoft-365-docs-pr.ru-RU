---
title: Миграция с Microsoft 365 бизнес на Microsoft 365 E3
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 5b4ba843-24b8-4526-8e1f-f9b9eab89d06
description: Узнайте, как переместить бизнес из Microsoft 365 Бизнес Премиум в Microsoft 365 E3.
ms.openlocfilehash: 10630671f3deb7eff0ad0f601d301b90743ee35f
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164520"
---
# <a name="migrate-from-microsoft-365-business-premium-to-microsoft-365-e3"></a>Миграция с Microsoft 365 бизнес премиум на Microsoft 365 E3

Microsoft 365 Business Premium имеет все необходимое для вашего малого бизнеса, объединяя лучшие в своем классе облачные приложения для повышения производительности с простым управлением устройствами и безопасностью, которые позволяют сотрудникам работать наилучшим образом. Однако в некоторых случаях может потребоваться перенести подписку microsoft 365 Бизнес Премиум на Microsoft 365 E3. 

Например, ваш бизнес вырос и нуждается в более чем 300 лицензиях (кстати, поздравления).

Кроме того, вашему бизнесу необходимы корпоративные функции, такие как Microsoft 365 Apps для предприятия, Windows 10 Enterprise E3 или Корпоративные лицензии на доступ к клиентам (CALs).

Обновление легко: вы можете начать обновление [из центра администрирования.](../commerce/subscriptions/upgrade-to-different-plan.md) Все данные и конфигурация текущей подписки поддерживаются. Ничего не нужно делать для подготовки к миграции и ничего не делать после этого, кроме использования новых функций.

>[!Note]
>Вы также можете использовать подписку Microsoft 365 Бизнес Премиум на 300 мест и получить подписку Microsoft 365 E3 на более чем 300 мест. Однако Microsoft Defender для Office 365 не входит в состав Microsoft 365 E3. Для дальнейшей защиты от угроз следует добавить дополнительные лицензии Defender для Office 365, чтобы все пользователи в области вашей полиции Defender для Office 365 были лицензированы.
>

## <a name="differences-between-microsoft-365-business-premium-and-microsoft-365-enterprise"></a>Различия между Microsoft 365 Бизнес Премиум и Microsoft 365 Корпоративный

В этой таблице показаны различия между Microsoft 365 Business Premium и Microsoft 365 E3.

| Функция    | Поддержка в Microsoft 365 Бизнес Премиум    | Поддержка в Microsoft 365 E3 | 
|:-------|:-----|:-----|
| **Локальная среда**        | | | 
| Windows 10    | Windows 10 для бизнеса  |     Windows 10 Корпоративная E3| 
| Приложения Office*    | [Приложения Microsoft 365 для бизнеса](#office-365-business)    | Приложения Microsoft 365 для предприятий | 
| **Приложения облачной производительности**        | | | 
| Exchange Online и Outlook    | Ограничение хранения 50 ГБ на почтовый ящик и неограниченное архиважи Exchange Online    | Ограничение хранения 100 ГБ на почтовый ящик и неограниченный архив exchange Online | 
| Teams    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| OneDrive для бизнеса    | Ограничение хранения 1 ТБ на пользователя    | Без ограничений | 
| Yammer, SharePoint Online, Planner, Stream    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| **Защита от угроз**        | | | 
| Возможности уменьшения поверхности атаки    | [См. этот список](#threat-protection) | Корпоративное управление аппаратной изоляцией для Microsoft Edge | 
| Defender для Office 365 (план 1) | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | Не включено, но может быть добавлено в | 
| **управление удостоверениями;**        | | | 
| Сброс пароля самообслуживления для гибридных учетных записей Azure Active Directory (Azure AD), многофакторной проверки подлинности Azure AD (MFA), условного доступа, списания паролей для идентификаторов локального доступа|     ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Обнаружение облачных приложений и подключение Azure AD    |     | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Приложения Azure AD Office 365 Sign-On (SSO): 10 приложений на пользователя (приложения Gallery SaaS, такие как Salesforce)* | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Azure AD Premium 1 SSO: без ограничений (локальное приложение с помощью прокси-сервера приложения Azure AD и приложения без галереи с Self-Service шаблонами интеграции приложений)    |     | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| **Управление устройствами и приложениями**        | | | 
| Microsoft Intune, Автопилот Windows|     ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
|Виртуальный настольный доступ (VDA)    |  |     ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
|Виртуальный рабочий стол Windows (WVD)    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png) |     ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
|Активация общего компьютера (SCA)    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png) |     ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Пакет оптимизации рабочего стола Майкрософт    | |     ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| **Защита информации**        | | | 
| Предотвращение потери данных Office 365, План защиты информации Azure 1    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Защита информации окна для конечной точки DLP    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| **Лицензия клиентского доступа (права CAL)**    | | |     
| Корпоративный пакет CAL (Exchange, SharePoint, Skype, Windows, Microsoft Endpoint Configuration Manager, Windows Rights Management)| |         ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| **Соответствие требованиям**        | | | 
| Неограниченное архивативка электронной почты    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Диспетчер соответствия требованиям    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Обнаружение электронных данных    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Удержание на месте и судебное удержание    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
| Теги и политики хранения для управления записями сообщений    | ![Включено с Microsoft 365 Бизнес Премиум](../media/check-mark.png)    | ![Включено в Microsoft 365 E3](../media/check-mark.png) | 
||||

\* Пользователи, которым был назначен доступ к приложениям SaaS, могут получить доступ к SSO до 10 приложений. Администраторы могут настраивать SSO и изменять доступ пользователей к различным приложениям SaaS, но доступ к SSO разрешен только для 10 приложений на одного пользователя одновременно. Все приложения Office 365 считаются одним приложением.

## <a name="migration"></a>Миграция

Чтобы мигрировать, работайте с партнером, чтобы переместить подписку и лицензии Microsoft 365 Бизнес Премиум на подходящую подписку Microsoft 365 E3 с ее лицензиями.

В следующих разделах описываются изменения, которые необходимо внести, если таковые есть, и что можно сделать после миграции.

### <a name="microsoft-365-subscription-configuration-and-data"></a>Конфигурация подписки и данные Microsoft 365

Перед переносом не нужно вносить изменения в текущую подписку или данные, которые включают:

- Конфигурация подписки, например доменные имена DNS.
- Учетные записи пользователей и групп и параметры проверки подлинности, такие как многофакторная проверка подлинности или политики условного доступа.
- Конфигурации служб производительности и их данные, такие как teams, почтовые ящики Exchange Online, сайты SharePoint Online, папки OneDrive для бизнеса и записные книжки OneNote.

Теперь пользователи могут пользоваться неограниченным хранилищем в почтовых ящиках Exchange Online и папках OneDrive для бизнеса.

Для более чем 10 приложений можно приступить к использованию cloud App Discovery, Azure AD Connect Health и SSO.

<a name="threat-protection"></a>
### <a name="threat-protection"></a>Защита от угроз

Windows 10 Business включает следующие средства защиты:

- Правоприменители целостности процесса загрузки операционной системы
- Правоприменители целостности конфиденциальных операционных компонентов
- Расширенный уровень уязвимости и смягчение последствий использования нулевого дня
- Защита сети на основе репутации для Microsoft Edge, Internet Explorer и Chrome
- Брандмауэр на основе хостов
- Смягчение последствий программ-вымогателей
- Аппаратная изоляция для Microsoft Edge
- Управление приложениями с помощью графа интеллектуальной безопасности
- Управление устройствами (USB)
- Защита сети от веб-угроз
- Правила предотвращения вторжений на хост

Windows 10 Enterprise E3 также включает управление корпоративной изолированностью на основе оборудования для Microsoft Edge.

>[!Note]
>Для дальнейшей защиты от угроз пользователям, перенесенным в Microsoft 365 E3, потребуется лицензия Microsoft Defender для Office 365. Не забудьте приобрести дополнительные лицензии Defender для Office 365, чтобы все пользователи в области вашей полиции Defender для Office 365 были лицензированы. 
>

### <a name="device-management-with-intune"></a>Управление устройствами с помощью Intune

Вам не нужно вносить изменения в текущую конфигурацию Intune перед миграцией, которая включает зарегистрированные устройства, устройства и параметры приложений.

### <a name="windows-10"></a>Windows 10

Microsoft 365 Business Premium включает Windows 10 Business, которую можно установить с помощью Windows AutoPilot. При миграции в Microsoft 365 E3 каждая лицензия пользователя включает Windows 10 Enterprise E3, которую можно также установить с помощью Автопилота Windows.

<a name="office-365-business"></a>
###  <a name="microsoft-365-apps-for-business"></a>Приложения Microsoft 365 для бизнеса

Приложения Microsoft 365 для бизнес-клиента, установленные на устройствах, автоматически начнут использовать функции Microsoft 365 Apps для предприятия. После переноса теперь можно использовать:

 - Поддержка групповой политики
 - Сравнение электронных таблиц и запрос
 - Бизнес-аналитика

