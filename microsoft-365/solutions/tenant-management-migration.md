---
title: Этап 4. Миграция для microsoft 365 для корпоративных клиентов
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
description: Перенос устройств Windows, клиентских приложений Office и серверов Office для клиентов Microsoft 365.
ms.openlocfilehash: 336dee2e62c6d0917c437252ba1d741c304998fa
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50929148"
---
# <a name="step-4-migration-for-your-microsoft-365-for-enterprise-tenants"></a>Этап 4. Миграция для microsoft 365 для корпоративных клиентов

Большинство корпоративных организаций имеют разнородную среду, которая включает несколько выпусков операционных систем, клиентского программного обеспечения и серверного программного обеспечения. Microsoft 365 для предприятия включает самые безопасные версии ключевых компонентов ИТ-инфраструктуры. Он также включает функции производительности, предназначенные для использования облачных технологий.

Чтобы максимально увеличить бизнес-значение пакета продуктов Microsoft 365 для корпоративных интегрированных продуктов, приступить к планированию и реализации стратегии переноса этих выпусков:

| From | To |
|:-------|:-----|
| Windows 7 и Windows 8.1 | Windows 10 Корпоративная |
| Клиентские продукты Office, установленные на устройствах вашего рабочего | Приложения Microsoft 365 для предприятий |
| Продукты office server, установленные на локальном сервере | Их эквивалентные облачные службы в Microsoft 365 |
|  |  |

## <a name="migrating-to-windows-10"></a>Перенос в Windows 10

Каждый Microsoft 365 для корпоративной лицензии включает лицензию для Windows 10 Enterprise. Чтобы перенести устройства с Windows 7 или Windows 8.1, можно выполнить обновление на месте. Поддержка windows 7 завершилась *14 января 2020 г.* 

Дополнительные методы установки Windows 10 Enterprise после обновления на месте см. в примере сценариев [развертывания Windows 10.](/windows/deployment/windows-10-deployment-scenarios) Вы также можете [планировать развертывание Windows 10](/windows/deployment/planning/) самостоятельно.

## <a name="migrating-to-microsoft-365-apps-for-enterprise"></a>Перенос в Microsoft 365 Apps для предприятия

Microsoft 365 для предприятия включает Microsoft 365 Apps для предприятия, версию клиентских продуктов Office (Word, PowerPoint, Excel и Outlook), которая устанавливается и обновляется из облака Microsoft. Дополнительные сведения см. [в дополнительных сведениях о приложениях Microsoft 365 для предприятия.](/deployoffice/about-microsoft-365-apps)

Вместо того, чтобы поддерживать ток компьютеров для Версий Office 2019 или более старых версий, необходимо предпринять следующие действия:

1. Получите и назначьте пользователям лицензию Microsoft 365.
2. Удалить Office 2013 или Office 2016 на своих компьютерах.
3. Установите приложения Microsoft 365 для предприятия как индивидуально, так и во время ИТ-2018. Дополнительные сведения см. в [руководстве по развертыванию приложений Microsoft 365.](/deployoffice/deployment-guide-microsoft-365-apps)

Приложения Microsoft 365 для предприятия устанавливают обновления безопасности и обновления новых функций автоматически и могут использовать облачные службы в Microsoft 365 для повышения безопасности и производительности.

## <a name="migrating-on-premises-servers-and-data-to-microsoft-365"></a>Перенос локального сервера и данных в Microsoft 365

Microsoft 365 для предприятия включает облачные версии служб office server, которые используют одни и те же инструменты, что и локальное программное обеспечение сервера Office, например веб-браузеры и клиент Outlook. Эти облачные службы автоматически обновляются для обеспечения безопасности и новых функций. После переноса ИТ-отдел может сэкономить время, необходимое для обслуживания и обновления локального сервера.

Используйте следующие ресурсы для сведений о миграции пользователей и данных для определенных рабочих нагрузок Microsoft 365:

- [Перемещение почтовых ящиков из локального Exchange Server в Exchange Online](/exchange/hybrid-deployment/move-mailboxes)
- [Перенос данных SharePoint с SharePoint Server на SharePoint Online](/sharepointmigration/migrate-to-sharepoint-online)
- [Перенос Skype для бизнеса в Microsoft Teams](/microsoftteams/migration-interop-guidance-for-teams-with-skype)

## <a name="transition-your-entire-organization"></a>Переход всей организации

Чтобы получить представление о том, как переместить всю организацию в продукты и службы в Microsoft 365 для предприятия, скачайте этот плакат перехода:

[![Изображение плаката Переход на Microsoft 365.](../media/microsoft-365-overview/transition-org-to-m365.png)](https://download.microsoft.com/download/2/c/7/2c7bcc04-aae3-4604-9707-1ffff66b9851/transition-org-to-m365.pdf)

Этот двухстраничный плакат позволяет быстро ознакомиться с существующей инфраструктурой. Используйте его для получения рекомендаций по переходу на продукт или службу в Microsoft 365 для предприятия. В нем показаны продукты Windows и Office, а также другие элементы инфраструктуры и безопасности, такие как управление устройствами, защита от личных данных и угроз, а также защита и соответствие требованиям.

## <a name="results-of-step-4"></a>Результаты шага 4

Для миграции клиента Microsoft 365 вы определили:

- На каких устройствах работает Windows 7 или Windows 8.1, и планируется обновить их до Windows 10 Enterprise.
- На каких устройствах запущены клиентские приложения Office и планируется обновить их до приложений Microsoft 365 для предприятия.
- Какие локально-серверные службы Office должны быть перенесены в эквивалент Microsoft 365 и планируется перенести их и их данные.

Вот пример клиента с завершенной миграцией локального сервера.

![Пример клиента с завершенной миграцией локального сервера](../media/tenant-management-overview/tenant-management-tenant-build-step4.png)

На этой иллюстрации организация имеет:

- Перенос локального почтового ящика Exchange Server в Exchange Online.
- Перенос локального сайта и данных SharePoint Server в SharePoint в Microsoft 365.

## <a name="ongoing-maintenance-for-migration"></a>Текущее обслуживание для миграции

На постоянной основе может потребоваться:

- В зависимости от состояния миграции почтовых ящиков Exchange продолжайте перенос перехода в Exchange Online в организацию.
- В зависимости от состояния локальной миграции сайта SharePoint продолжайте переназначение перехода на SharePoint в Microsoft 365 в организацию.

## <a name="next-step"></a>Следующий шаг

[![Шаг 5. Развертывание управления устройствами и приложениями](../media/tenant-management-overview/tenant-management-step-grid-device-mgmt.png)](tenant-management-device-management.md)

Продолжайте с [управлением устройствами и приложениями,](tenant-management-device-management.md) чтобы развернуть управление устройствами и приложениями.