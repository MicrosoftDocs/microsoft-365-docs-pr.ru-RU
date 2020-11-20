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
ms.openlocfilehash: 7e488caba5e4df47bb3f51f195e093891565d95c
ms.sourcegitcommit: 001e64f89f9c3cd6bbd4a25459f5bee3b966820c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2020
ms.locfileid: "49367205"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Запуск портала с помощью планировщика запуска портала

Портал — это сайт SharePoint в вашей интрасети, у которого есть большое количество посетителей сайта, использующих его содержимое. Запуск портала в волне является важной частью обеспечения гладкого и производительного взаимодействия пользователей с доступом к новому порталу SharePoint Online. 

Запуск в волнах — это ключевой способ развертывания портала, как описано в разделе [Планирование развертывания портала для запуска в SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide). Планировщик запуска портала предназначен для выполнения поэтапного и поэтапного развертывания с помощью управления перенаправлениями для нового портала. Во время каждой волны вы можете собирать отзывы пользователей и мониторинг производительности во время каждой волны развертывания. Благодаря этому вы можете приостановить и устранить проблемы, прежде чем переходить к следующему волнам, и в конечном счете обеспечить положительную работу пользователей. 

Существует два типа перенаправления: 
- Двунаправленная: запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint 
- временное перенаправление страниц: запуск нового современного портала SharePoint Online без существующего портала SharePoint

Планировщик запуска портала доступен только для запуска современных порталов SharePoint Online, например сайтов для общения и современных сайтов групп. Запуск должен быть запланирован по крайней мере на 7 дней заранее. Количество требуемых волн определяется ожидаемым количеством пользователей. Перед планированием запуска портала необходимо запустить [средство диагностики страниц для SharePoint](https://aka.ms/perftool) , чтобы убедиться, что домашняя страница на портале работоспособна. После запуска портала все пользователи с разрешениями на сайт смогут получить доступ к новому сайту. 

Для получения дополнительных сведений о запуске успешного портала следуйте основным принципам, рекомендациям и рекомендациям, описанным в разделе [Создание, запуск и обслуживание работоспособного портала](https://docs.microsoft.com/sharepoint/portal-health). 

> [!NOTE]
> Эта функция недоступна для Office 365 Германия, Office 365 под управлением 21Vianet (Китай) или Microsoft 365 для государственных организаций США.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Установка приложений и подключение к SharePoint Online
1. [Скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу "Установка и удаление программ" и удалите компонент "Командная консоль SharePoint Online". <br>На странице Центра загрузки выберите нужный язык и нажмите кнопку "Скачать". Вам будет предложено скачать версию x64 или x86 файла MSI. Для 64-разрядной версии Windows скачайте файл x64, а для 32-разрядной — файл x86. Если вы не знаете свою разрядность, см. статью [Какая у меня версия операционной системы Windows?](https://support.microsoft.com/help/13443/windows-which-operating-system) После скачивания файла запустите его и следуйте инструкциям мастера настройки.

2. Подключите SharePoint, используя [права глобального администратора или администратора SharePoint](/sharepoint/sharepoint-admin-role) в Microsoft 365. Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Просмотр всех существующих настроек запуска портала

Чтобы проверить наличие существующих конфигураций запуска портала:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Планирование запуска портала на сайте

Количество требуемых волн зависит от предполагаемого размера запуска. 
- Менее 10 000 пользователей: 1 волна
- 10 000 к пользователям 30k: 3 волны 
- 30k + до 100 000 пользователей: 5 волн
- Более 100 КБ пользователей: 5 волнах и обращение к группе учетных записей Майкрософт

### <a name="steps-for-bidirectional-redirection"></a>Действия для перенаправления с двунаправленным письмом

Двунаправленное перенаправление включает в себя запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint. Пользователи в активных волнах будут перенаправляться на новый сайт независимо от того, переходить на старый или новый сайт. Пользователи в незапущенной волне, который пытается получить доступ к новому сайту, будут перенаправлены на старый сайт, пока не будет запущена звуковая волна. 

Поддерживается перенаправление только между домашней страницей по умолчанию на старом сайте и домашней страницей по умолчанию на новом сайте. Если у вас есть администраторы или владельцы, которым необходим доступ к старым и новым сайтам без перенаправления, убедитесь, что они указаны с помощью `WaveOverrideUsers` параметра. Если у вас есть администраторы или владельцы, которым необходим доступ к старым и новым сайтам без перенаправления, убедитесь, что они указаны с помощью `WaveOverrideUsers` параметра. Поддерживается перенаправление только между домашней страницей по умолчанию на старом сайте и домашней страницей по умолчанию на новом сайте.

Для поэтапной миграции пользователей с существующего сайта SharePoint на новый сайт SharePoint выполните указанные ниже действия.

1. Выполните следующую команду, чтобы назначить запускаемые волны портала.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Пример.
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Выполнение проверки. Перенаправление для завершения настройки в службе может занять 5-10 минут. 

### <a name="steps-for-redirection-to-temporary-page"></a>Действия для перенаправления на временную страницу

Временное перенаправление страницы следует использовать, если существующий портал SharePoint не существует. В поэтапной манере пользователи направлены на новый современный портал SharePoint Online. Если пользователь находится в волне, который еще не запущен, он будет перенаправлен на временную страницу (любой URL-адрес). 

1. Выполните следующую команду, чтобы назначить запускаемые волны портала.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Пример.
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Выполнение проверки. Перенаправление для завершения настройки в службе может занять 5-10 минут. 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Приостановка и перезапуск запуска портала на сайте

1. Чтобы приостановить запуск портала в ходе выполнения и временно предотвратить появление будущих поступающих в нее действий, выполните следующую команду:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Проверка того, что все пользователи перенаправляются на старый сайт. 

3. Чтобы перезапустить приостановленный запуск портала, выполните следующую команду:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Проверка того, что перенаправление восстановлено. 

## <a name="delete-a-portal-launch-on-the-site"></a>Удаление запуска портала на сайте
1. Создайте Звукозапись для запуска портала.
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. Выполните приведенную ниже команду, чтобы удалить запланированное или выполняемое для сайта время запуска портала.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. Проверка того, что перенаправление не выполняется для всех пользователей.

## <a name="learn-more"></a>Подробнее
[Планирование развертывания портала для запуска в SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
