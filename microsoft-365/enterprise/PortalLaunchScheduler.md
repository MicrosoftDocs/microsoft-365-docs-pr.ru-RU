---
title: Запуск портала с помощью планивщика запуска портала
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
description: В этой статье описывается, как можно запустить портал с помощью планивщика запуска портала
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864880"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Запуск портала с помощью планивщика запуска портала

Портал — это сайт SharePoint в вашей интрасети, у которого есть большое количество посетителей сайта, использующих его содержимое. Запуск портала волнами является важной частью обеспечения у пользователей плавного и емких способов доступа к новому порталу SharePoint Online. 

Запуск в волны — это ключевой способ выкатить портал, как описано в планировании плана запуска портала в [SharePoint Online.](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide) Планер запуска портала предназначен для того, чтобы помочь вам следовать подходу к поэтапному или волновому выпуску, управляя перенаправлениями для нового портала. Во время каждой волны можно собирать отзывы пользователей и отслеживать производительность во время каждой волны развертывания. Это дает возможность постепенно внедрять портал, предоставляя возможность приостановить и устранить проблемы перед тем, как двигаться к следующей волне, и в конечном итоге обеспечить положительное впечатление для пользователей. 

Существует два типа перенаправления: 
- двухнаправленный запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint 
- перенаправление временных страниц: запуск нового современного портала SharePoint Online без существующего портала SharePoint

Планировать запуск портала можно только для запуска современных порталов SharePoint Online (то есть информационных сайтов). Запуски должны быть запланированы по крайней мере за 7 дней до этого. Требуемая частота волн определяется ожидаемым количеством пользователей. Перед планированием запуска портала необходимо запустить средство диагностики страниц [Для SharePoint,](https://aka.ms/perftool) чтобы убедиться, что домашняя страница на портале работает. После запуска портала все пользователи с разрешениями на доступ к сайту смогут получить доступ к новому сайту. 

Для получения дополнительных сведений об успешном запуске портала следуйте базовым принципам, рекомендациям и рекомендациям, подробно описанным в этой теме. [](https://docs.microsoft.com/sharepoint/portal-health) 

> [!NOTE]
> Эта функция недоступна для планов Office 365 Germany, Office 365 под управлением 21Vianet (Китай) или Microsoft 365 для государственных органов США.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Настройка приложения и подключение к SharePoint Online
1. [Скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу "Установка и удаление программ" и удалите компонент "Командная консоль SharePoint Online".<br>На странице Центра загрузки выберите нужный язык и нажмите кнопку "Скачать". Вам будет предложено скачать версию x64 или x86 файла MSI. Для 64-разрядной версии Windows скачайте файл x64, а для 32-разрядной — файл x86. Если вы не знаете свою разрядность, см. статью [Какая у меня версия операционной системы Windows?](https://support.microsoft.com/help/13443/windows-which-operating-system) После скачивания файла запустите его и следуйте инструкциям мастера настройки.

2. Подключите SharePoint, используя [права глобального администратора или администратора SharePoint](/sharepoint/sharepoint-admin-role) в Microsoft 365. Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Просмотр существующих настроек запуска портала

Чтобы узнать, существуют ли конфигурации запуска портала:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Запланировать запуск портала на сайте

Необходимое количество волн зависит от ожидаемого размера запуска. 
- Менее 10 000 пользователей: 1 волна
- От 10 до 30 000 пользователей: 3 волны 
- От 30 000 до 100 000 пользователей: 5 волн
- Более 100 000 пользователей: 5 волн и свяжитесь со своей командой учетных записей Майкрософт

### <a name="steps-for-bidirectional-redirection"></a>Действия по перенаправлению междунаправлениями

Двухнаправленное перенаправление включает запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint. Пользователи в активных волнах будут перенаправлены на новый сайт независимо от того, переходят ли они на старый или новый сайт. Пользователи в не запускаемой волне, которые пытаются получить доступ к новому сайту, будут перенаправлены обратно на старый сайт, пока их волны не будут запущены. 

Мы поддерживаем только перенаправление между домашней страницей по умолчанию на старом сайте и домашней страницей по умолчанию на новом сайте. Если у вас есть администраторы или владельцы, которые нуждаются в доступе к старым и новым сайтам без перенаправления, убедитесь, что они указаны с помощью `WaveOverrideUsers` параметра.

Поэтапное перенос пользователей с существующего сайта SharePoint на новый сайт SharePoint:

1. Чтобы назначить волны запуска портала, запустите следующую команду.
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Пример:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Полная проверка. Настройка перенаправления в службе может занять от 5 до 10 минут. 

### <a name="steps-for-redirection-to-temporary-page"></a>Действия для перенаправления на временную страницу

Если портал SharePoint не существует, следует использовать временное перенаправление страниц. Пользователи поэтапно направляются на новый современный портал SharePoint Online. Если пользователь находится в волне, которая не была запущена, он будет перенаправлен на временную страницу (любой URL-адрес). 

1. Чтобы назначить волны запуска портала, запустите следующую команду.
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

Пример:
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. Полная проверка. Настройка перенаправления в службе может занять от 5 до 10 минут. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Приостановка или перезапуск запуска портала на сайте

1. Чтобы приостановить запуск портала и временно запретить переходы на новую волну, запустите следующую команду:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Проверка перенаправления всех пользователей на старый сайт. 

3. Чтобы перезапустить приостановленный запуск портала, запустите следующую команду:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Проверьте, восстановлено ли перенаправление. 

## <a name="delete-a-portal-launch-on-the-site"></a>Удаление запуска портала на сайте

1. Чтобы удалить запланированный или запущенный портал для сайта, запустите следующую команду.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Проверьте, не происходит ли перенаправление для всех пользователей.

## <a name="learn-more"></a>Дополнительные сведения
[Планирование плана запуска портала в SharePoint Online](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
