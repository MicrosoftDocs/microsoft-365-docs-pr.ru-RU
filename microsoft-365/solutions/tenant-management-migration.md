---
title: Этап 4. Миграция для Microsoft 365 для корпоративных клиентов
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
- m365solution-tenantmanagement
- tenant-management
- m365solution-scenario
ms.custom:
- Ent_Solutions
description: Перенос устройств Windows, Office клиентских приложений и Office серверов для Microsoft 365 клиентов.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929148"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Этап 4. Миграция для Microsoft 365 для корпоративных клиентов

Большинство корпоративных организаций имеют разнородную среду, которая включает несколько выпусков операционных систем, клиентского программного обеспечения и серверного программного обеспечения. Microsoft 365 для предприятия включает самые безопасные версии ключевых компонентов ИТ-инфраструктуры. Он также включает функции производительности, предназначенные для использования облачных технологий.

Чтобы максимально увеличить бизнес-значение пакета Microsoft 365 корпоративных интегрированных продуктов, приступить к планированию и реализации стратегии переноса этих выпусков:

| From | To |
|:-------|:-----|
| Windows 7 и Windows 8.1 | Windows 10 Корпоративная |
| Office клиентские продукты, установленные на устройствах вашего рабочего | Приложения Microsoft 365 для предприятий |
| Office серверных продуктов, установленных на локальном сервере | Их эквивалентные облачные службы в Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Перенос в Windows 10

Каждый Microsoft 365 для корпоративной лицензии включает лицензию на Windows 10 Корпоративная. Чтобы перенести устройства, Windows 7 или Windows 8.1, можно выполнить обновление на месте. Поддержка завершилась Windows 7 *января 14 2020 г.* 

Дополнительные методы установки Windows 10 Корпоративная после обновления на месте см. в Windows 10 [сценариях развертывания.](/windows/deployment/windows-10-deployment-scenarios) Вы также можете [планировать развертывание Windows 10](/windows/deployment/planning/) самостоятельно.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Миграция в Приложения Microsoft 365 для предприятий

Microsoft 365 для предприятия включает Приложения Microsoft 365 для предприятий версию клиентских продуктов Office (Word, PowerPoint, Excel и Outlook), которая устанавливается и обновляется из облака Майкрософт. Дополнительные сведения см. [в Приложения Microsoft 365 для предприятий.](/deployoffice/about-microsoft-365-apps)

Вместо того, чтобы поддерживать ток компьютеров для Office 2019 или более старых версий, необходимо предпринять следующие действия:

1. Получите и назначьте Microsoft 365 лицензию для пользователей.
2. Удалить Office 2013 или Office 2016 на своих компьютерах.
3. Установите Приложения Microsoft 365 для предприятий, как индивидуально, так и во время ИТ-установки. Дополнительные сведения см. в [руководстве по развертыванию для Приложений Microsoft 365](/deployoffice/deployment-guide-microsoft-365-apps).

Приложения Microsoft 365 для предприятий устанавливает как обновления безопасности, так и новые обновления функций автоматически и может использовать облачные службы в Microsoft 365 для повышения безопасности и производительности.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Перенос локального сервера и данных в Microsoft 365

Microsoft 365 для предприятия включает облачные версии служб Office серверов, которые используют одни и те же инструменты, что и локальное программное обеспечение Office сервера, например веб-браузеры и клиент Outlook. Эти облачные службы автоматически обновляются для обеспечения безопасности и новых функций. После переноса ИТ-отдел может сэкономить время, необходимое для обслуживания и обновления локального сервера.

Используйте следующие ресурсы для сведений о миграции пользователей и данных для определенных Microsoft 365 рабочих нагрузок:

- [Перемещение почтовых ящиков из локального Exchange Server в Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Перенос SharePoint данных с SharePoint Server на SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Перенос Skype для бизнеса в Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Переход всей организации

Чтобы получить представление о том, как переместить всю организацию в продукты и службы в Microsoft 365 для предприятия, скачайте этот плакат перехода:

[![Изображение, показывающая переход на Microsoft 365 плаката.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Этот двухстраничный плакат позволяет быстро ознакомиться с существующей инфраструктурой. Используйте его для получения рекомендаций по переходу на продукт или службу в Microsoft 365 для предприятия. В нем Windows и Office и другие элементы инфраструктуры и безопасности, такие как управление устройствами, защита удостоверений и угроз, защита информации и соответствие требованиям.

## <a name="results-of-step-4"></a>Результаты шага 4

Для миграции Microsoft 365 клиента вы определили:

- Какие устройства работают Windows 7 или Windows 8.1 и план обновления их до Windows 10 Корпоративная.
- Какие устройства запускают Office клиентские приложения и планируют обновить их до Microsoft 365 приложений для предприятия.
- Какие локально Office серверные службы должны быть перенесены в Microsoft 365 эквивалент и план их миграции и их данных.

Вот пример клиента с завершенной миграцией локального сервера.

![Пример клиента с завершенной миграцией локального сервера](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

На этой иллюстрации организация имеет:

- Перенос локального почтового ящика Exchange Server в Exchange Online.
- Перенос локального сайта SharePoint серверов и данных в SharePoint в Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Текущее обслуживание для миграции

На постоянной основе может потребоваться:

- В зависимости от состояния переноса Exchange почтовых ящиков продолжайте перетаповку Exchange Online в организацию.
- В зависимости от состояния локальной миграции SharePoint, продолжайте перенакрутку перехода на SharePoint в Microsoft 365 организации.

## <a name="next-step"></a>Следующий этап

[![Шаг 5. Развертывание управления устройствами и приложениями](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Продолжайте с [управлением устройствами и приложениями,](tenant-management-device-management.md) чтобы развернуть управление устройствами и приложениями.