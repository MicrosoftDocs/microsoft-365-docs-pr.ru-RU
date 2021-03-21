---
title: Запуск портала с помощью планера запуска портала
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
description: В этой статье описывается, как можно запустить портал с помощью план-графика запуска портала
ms.openlocfilehash: e39f00dbc63ae7f1dcaf907d9c67df2c1683efc6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50926146"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>Запуск портала с помощью планера запуска портала

Портал — это сайт SharePoint в вашей интрасети, у которого есть большое количество посетителей сайта, использующих его содержимое. Запуск портала в волнах является важной частью обеспечения бесперебойного доступа пользователей к новому порталу SharePoint Online. 

Запуск в волнах — это ключевой способ запуска портала, как описано в планировании плана запуска портала [в SharePoint Online.](./planportallaunchroll-out.md?view=o365-worldwide) План-график запуска портала предназначен для того, чтобы помочь вам следовать подходу к поэтапному и поэтапному выкату, управляя перенаправлениями для нового портала. Во время каждой волны можно собирать отзывы пользователей и отслеживать производительность во время каждой волны развертывания. Это имеет преимущество медленного внедрения портала, предоставляя вам возможность приостановить и устранить проблемы перед началом следующей волны и в конечном счете обеспечить положительный опыт для пользователей. 

Существует два типа перенаправления: 
- bidirectional: запустите новый современный портал SharePoint Online, чтобы заменить существующий классический или современный портал SharePoint 
- временное перенаправление страниц: запуск нового современного портала SharePoint Online без существующего портала SharePoint

План-график запуска портала доступен только для запуска современных порталов SharePoint Online (то есть сайтов связи). Запуски должны быть запланированы не менее чем за 7 дней до начала. Количество требуемого количества волн определяется ожидаемым числом пользователей. Перед планированием запуска портала необходимо запустить средство [Page Diagnostics for SharePoint,](./page-diagnostics-for-spo.md) чтобы убедиться, что домашняя страница на портале здорова. По завершении запуска портала все пользователи с разрешениями на сайт смогут получить доступ к новому сайту. 

Дополнительные сведения о запуске успешного портала, следуйте основным принципам, практикам и рекомендациям, подробным в создании, запуске и обслуживании [здорового портала.](/sharepoint/portal-health) 

> [!NOTE]
> Эта функция недоступна для Office 365 Germany, Office 365, выполняемого 21Vianet (Китай) или планов правительства США Microsoft 365.

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>Настройка приложения и подключение к SharePoint Online
1. [Скачайте последнюю версию командной консоли SharePoint Online](https://go.microsoft.com/fwlink/p/?LinkId=255251).

    > [!NOTE]
    > Если вы установили предыдущую версию командной консоли SharePoint Online, перейдите к разделу "Установка и удаление программ" и удалите компонент "Командная консоль SharePoint Online".<br>На странице Центра загрузки выберите нужный язык и нажмите кнопку "Скачать". Вам будет предложено скачать версию x64 или x86 файла MSI. Для 64-разрядной версии Windows скачайте файл x64, а для 32-разрядной — файл x86. Если вы не знаете свою разрядность, см. статью [Какая у меня версия операционной системы Windows?](https://support.microsoft.com/help/13443/windows-which-operating-system) После скачивания файла запустите его и следуйте инструкциям мастера настройки.

2. Подключите SharePoint, используя [права глобального администратора или администратора SharePoint](/sharepoint/sharepoint-admin-role) в Microsoft 365. Сведения о том, как это сделать, см. в статье [Начало работы с командной консолью SharePoint Online](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online).


## <a name="view-any-existing-portal-launch-setups"></a>Просмотр всех существующих установок запуска портала

Чтобы узнать, существуют ли существующие конфигурации запуска портала:

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>Расписание запуска портала на сайте

Количество требуемого количества волн зависит от ожидаемого размера запуска. 
- Менее 10k пользователей: 1 волна
- 10k до 30k пользователей: 3 волны 
- 30k+ до 100k пользователей: 5 волн
- Более 100k пользователей: 5 волн и свяжитесь с командой учетных записей Майкрософт

### <a name="steps-for-bidirectional-redirection"></a>Действия по перенаправлению бидеректов

Перенаправление бидеректов предполагает запуск нового современного портала SharePoint Online для замены существующего классического или современного портала SharePoint. Пользователи в активных волнах будут перенаправлены на новый сайт независимо от того, переходят ли они на старый или новый сайт. Пользователи не запущенной волны, которые пытаются получить доступ к новому сайту, будут перенаправлены обратно на старый сайт до запуска волны. 

Мы поддерживаем только перенаправление между домашней страницей по умолчанию на старом сайте и домашней страницей по умолчанию на новом сайте. Если у вас есть администраторы или владельцы, которые нуждаются в доступе к старым и новым сайтам без перенаправления, убедитесь, что они указаны с помощью `WaveOverrideUsers` параметра.

Поэтапное перенос пользователей с существующего сайта SharePoint на новый сайт SharePoint:

1. Запустите следующую команду, чтобы назначить волны запуска портала.
   
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

2. Полная проверка. Перенаправление может занять 5-10 минут, чтобы завершить конфигурацию по службе. 

### <a name="steps-for-redirection-to-temporary-page"></a>Действия по перенаправлению на временную страницу

При отсутствие существующего портала SharePoint необходимо использовать временную перенаправление страниц. Пользователи направляются на новый современный портал SharePoint Online поэтапно. Если пользователь находится в волне, которая не была запущена, он будет перенаправлен на временную страницу (любой URL-адрес). 

1. Запустите следующую команду, чтобы назначить волны запуска портала.
   
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

2. Полная проверка. Перенаправление может занять 5-10 минут, чтобы завершить конфигурацию по службе. 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>Приостановка или перезапуск запуска портала на сайте

1. Чтобы приостановить запуск портала и временно предотвратить предстоящие прогрессии волн, запустите следующую команду:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. Проверка перенаправления всех пользователей на старый сайт. 

3. Чтобы перезапустить приостановленный запуск портала, запустите следующую команду:

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. Проверка восстановления перенаправления. 

## <a name="delete-a-portal-launch-on-the-site"></a>Удаление запуска портала на сайте

1. Запустите следующую команду, чтобы удалить запланированный или запущенный запуск портала для сайта.

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. Проверка того, что перенаправление не происходит для всех пользователей.

## <a name="learn-more"></a>Подробнее
[Планирование плана запуска портала в SharePoint Online](./planportallaunchroll-out.md)