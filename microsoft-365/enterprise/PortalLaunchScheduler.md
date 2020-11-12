---
title: Запуск портала с помощью планировщика запуска портала
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: В этой статье описывается, как можно запустить портал с помощью планировщика запуска портала.
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999595"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Запуск портала с помощью планировщика запуска портала

Вы можете запустить портал с помощью планировщика запуска портала, сначала проверив возможность настройки волн для нового портала администратором клиента. Затем администратор может проверить перенаправление запросов на основании существования пользователя в активных волнах.

Для получения дополнительных сведений о запуске успешного портала следуйте основным принципам, рекомендациям и рекомендациям, описанным в разделе [Создание, запуск и обслуживание работоспособного портала](https://go.microsoft.com/fwlink/?linkid=2105838). 

## <a name="app-setup"></a>Установка приложения
1. Удалить, если вы уже наступили `Microsoft.Online.SharePoint.PowerShell` с компьютера с помощью панели управления.
2. На этапе PowerShell `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` .

## <a name="connect-to-sharepoint-online"></a>Подключение к SharePoint Online
1. Откройте [командную консоль SharePoint Online](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) в Windows.
2. Подключитесь к клиенту от имени администратора.
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  При появлении соответствующего запроса введите пароль.

## <a name="command-to-get-an-existing-setup"></a>Команда для получения существующей программы установки

Чтобы просмотреть существующие конфигурации запуска портала, выполните указанные ниже действия.

1. Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` .
2. Передайте дополнительный параметр, `-DisplayFormat Raw` Если вы хотите просмотреть коллекцию волн, отформатированную как необработанный входной формат.

## <a name="commands-for-bi-directional-redirection"></a>Команды для перенаправления с двунаправленным письмом

Для поэтапной миграции старых пользователей сайта на новый сайт:

1. Создание волновых спусков.
   - Это относится только к этапам проверки раннего выпуска.
   - Чтобы протестировать влияние изменения немедленно, убедитесь, что для первой волновой записи `LaunchDateUtc` задана текущая дата. Если этот флаг не указан, будет выведено сообщение об ошибке. Эта ошибка возникает, так как запуск в рабочей среде должен быть запланирован по крайней мере на 7 дней заранее.

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Выполнение проверки.
  - Перенаправление для завершения настройки в службе может занять до 5 минут, поэтому необходимо подождать, прежде чем продолжить.
  - Если вы выполняете вход с указанным пользователем `WaveOverrideUsers` , ничего не изменится. Вы должны находиться на сайте, на который вы перемещаетесь.
  - Войдите в систему, используя пользователя, который входит в число *посетителей SG1*.
    - Перейдите на старый сайт, и вы должны быть перенаправлены на новый сайт.
    - Перейдите к новому сайту, и вы должны остаться на новом сайте.
    - Войдите в систему с помощью средства "Пользователи" *SG2* и перейдите к старому сайту и оставайтесь на старом сайте.
    - Перейдите к новому сайту, и вы должны быть перенаправлены на старый сайт.

3. Приостановка запуска портала.
  - Если необходимо приостановить номера выпуска, можно приостановить их для "x" дней. Установка `Status` флага приостановить предотвращает все будущие волновые прогрессии. 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - При этом будут проверены, что все пользователи перенаправляются на старый сайт.

4. Перезапустите процесс запуска портала. 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Проверка того, что перенаправление восстановлено.

5. Удаление параметров запуска портала.
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - Проверка того, что перенаправление не выполняется для всех пользователей.

## <a name="commands-for-redirection-to-temporary-page"></a>Команды для перенаправления на временную страницу

Выполните указанные ниже действия, если вы не используете предыдущий сайт и хотите опустить пользователей, не включенных в элемент "волна" на новой странице портала.

Чтобы создать временную страницу на любом из сайтов:

1. Создайте Звукозапись для запуска портала.
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Выполнение проверки.

  - Подождите пять минут, прежде чем продолжить, так как выполнение действия может занять до пяти минут.
  - Войдите в систему пользователя, который входит в состав *посетителей SG1* и:
     - Перейдите к новому сайту, и вы должны остаться на новом сайте.
     - Перейдите на страницу Temp, и вы должны остаться на странице Temp.
  - Войдите в систему пользователя, который входит в состав *посетителей SG2* и:
     - Перейдите к новому сайту, и вы будете перенаправлены на страницу Temp.
     - Перейдите на страницу Temp, и вы должны остаться на странице Temp.

3. Удаление параметров запуска портала.
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - Проверка того, что перенаправление не выполняется для всех пользователей.

## <a name="learn-more"></a>Подробнее
[Планирование развертывания портала для запуска в SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)