---
title: Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 06/16/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: cef3044d-d4cb-4586-8e82-ee97bd3b14ad
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Узнайте, как настроить локальное Exchange Server для использования гибридной современной проверки подлинности (HMA), предлагая более безопасную проверку подлинности и авторизацию пользователей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 21ffec620ac3e262679fc0e2385f6f0f1b31933b
ms.sourcegitcommit: f7fbf45af64c5c0727fd5eaab309d20ad097a483
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/09/2021
ms.locfileid: "53362262"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Гибридная современная проверка подлинности (HMA) — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей и доступен для Exchange локального гибридного развертывания.

## <a name="fyi"></a>FYI

Перед началом работы я вызываю:

- Гибридная современная \> проверка подлинности HMA

- Exchange \> локальной EXCH

- \>Exchange Online EXO

Кроме того, если на рисунке в этой статье имеется объект с "серым" или "замутненым", это означает, что элемент, показанный в сером цвете, не входит в конфигурацию, определенную *HMA.*

## <a name="enabling-hybrid-modern-authentication"></a>Включение гибридной современной проверки подлинности

Включение HMA означает:

1. Убедитесь, что перед началом работы вы встретите предварительные окрики.

1. Поскольку  для Skype для бизнеса и Exchange часто используется множество необходимых условий, обзор гибридной современной проверки подлинности и необходимые условия для его использования на локальном Skype для бизнеса [и Exchange серверах](hybrid-modern-auth-overview.md). Сделайте это, прежде чем приступить к любым шагам в этой статье.

1. Добавление URL-адресов веб-служб локальной службы в качестве имен основных служб **(SPNs)** в Azure AD. В том случае, если EXCH гибридна с несколькими клиентами, эти URL-адреса веб-службы локального уровня должны быть добавлены в качестве URL-адресов в Azure AD всех клиентов, которые находятся в гибридной связи с EXCH.

1. Обеспечение включения всех виртуальных каталогов для HMA

1. Проверка объекта Auth Server EvoSTS

1. Включение HMA в EXCH.

> [!NOTE]
> Поддерживает ли ваша версия Office ma? Узнайте, как работает современная [проверка подлинности для Office 2013 и Office 2016 г.](modern-auth-for-office-2013-and-2016.md)


## <a name="make-sure-you-meet-all-the-prerequisites"></a>Убедитесь, что вы соответствуете всем необходимым требованиям

Поскольку многие необходимые условия являются общими как для Skype для бизнеса, так и для Exchange, просмотрите обзор гибридной современной проверки подлинности и необходимые условия для ее использования на локальном Skype для бизнеса [и Exchange серверах](hybrid-modern-auth-overview.md). Сделайте  *это,*  прежде чем приступить к любым шагам в этой статье.

> [!NOTE]
> Outlook Web App и Exchange панель управления не работает с гибридной современной проверкой подлинности.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Добавление URL-адресов веб-службы на локальной основе в качестве SPNs в Azure AD

Запустите команды, которые назначают URL-адреса локальной веб-службы в качестве SPNs Azure AD. SpNs используются клиентские машины и устройства во время проверки подлинности и авторизации. Все URL-адреса, которые можно использовать для подключения из локального в Azure Active Directory (Azure AD), должны быть зарегистрированы в Azure AD (это включает как внутренние, так и внешние пространства имен).

Сначала соберйте все URL-адреса, которые необходимо добавить в AAD. Запустите эти команды на месте:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
```

Убедитесь, что клиенты URL-адресов могут подключаться к числу основных имен служб HTTPS в AAD. В случае, если EXCH гибридна с несколькими **арендаторами,** эти VPN HTTPS должны быть добавлены в AAD всех клиентов в гибриде с EXCH.

1. Во-первых, подключите К AAD с [этими инструкциями.](connect-to-microsoft-365-powershell.md)

    > [!NOTE]
    > Чтобы использовать команду _ниже, необходимо использовать Подключение-MsolService_ на этой странице.

2. Для URL Exchange связанных с Exchange, введите следующую команду:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Обратите внимание (и снимок экрана для более позднего сравнения) вывода этой команды, которая должна включать URL-адрес https://  *autodiscover.yourdomain.com*  и https://  *mail.yourdomain.com,* но в основном состоит из SPNs, которые начинаются с 0000002-0000-0ff1-ce00-0000000000000/. Если из локального https:// отсутствуют URL-адреса, нам потребуется добавить эти конкретные записи в этот список.

3. Если вы не видите в этом списке внутренние и внешние записи MAPI/HTTP, EWS, ActiveSync, OAB и Autodiscover, необходимо добавить их с помощью команд ниже (например URL-адреса в примере ' и ', но вы замените URL-адреса примера `mail.corp.contoso.com` `owa.contoso.com` собственными): 

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Убедитесь, что новые записи были добавлены, Get-MsolServicePrincipal команду из шага 2 и проверив выход. Сравните список и снимок экрана до нового списка spNs. Вы также можете сделать снимок экрана нового списка для записей. Если вы были успешными, вы увидите два новых URL-адреса в списке. В нашем примере список СНО теперь будет включать конкретные  `https://mail.corp.contoso.com`  URL-адреса и  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Проверка правильной настройки виртуальных каталогов

Теперь убедитесь, что OAuth включен Exchange во всех виртуальных каталогах Outlook, которые можно использовать при запуске следующих команд:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Проверьте вывод, чтобы убедиться, что **OAuth** включен в каждом из этих VDirs, он будет выглядеть так (и главное, что нужно посмотреть, это OAuth):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Если OAuth отсутствует на любом сервере и любом из четырех виртуальных каталогов, его необходимо добавить с помощью соответствующих команд перед началом работы[(Set-MapiVirtualDirectory,](/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](/powershell/module/exchange/set-oabvirtualdirectory)и [Set-AutodiscoverVirtualDirectory).](/powershell/module/exchange/set-autodiscovervirtualdirectory)

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Подтверждение на наличие объекта Auth Server EvoSTS

Возвращайся к локальной Exchange командной оболочке для этой последней команды. Теперь вы можете проверить, есть ли у локального поставщика проверки подлинности evoSTS запись:

```powershell
Get-AuthServer | where {$_.Name -like "EvoSts"}
```

На выходе должен быть показываться AuthServer имени EvoSts, а состояние "Включено" должно быть True. Если этого не видно, следует скачать и запустить новейшую версию мастера гибридной конфигурации.

> [!NOTE]
> В том случае, если EXCH гибридна с несколькими арендаторами, на выходе должен быть по одному AuthServer name EvoSts — {GUID} для каждого клиента в гибриде с EXCH, а состояние "Включено" должно быть true для всех этих объектов AuthServer.

 **Важно** Если в среде Exchange 2010 г., поставщик проверки подлинности EvoSTS не будет создан.

## <a name="enable-hma"></a>Включить HMA

Запустите следующую команду в локальной Exchange командной оболочке:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

Если версия EXCH Exchange 2016 (CU18 или выше) или Exchange 2019 (CU7 или выше) и гибридная была настроена с HCW, загруженным после сентября 2020 г., запустите следующую команду в локальной Exchange Management Shell:

```powershell
Set-AuthServer -Identity "EvoSTS - {GUID}" -DomainName "Tenant Domain" -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

> [!NOTE]
> Если EXCH гибридна с несколькими арендаторами, в EXCH присутствует несколько объектов AuthServer с доменами, соответствующими каждому клиенту.  Флаг **IsDefaultAuthorizationEndpoint** должен быть задан для true (с помощью **cmdlet IsDefaultAuthorizationEndpoint)** для любого из этих объектов AuthServer. Этот флаг не может быть задан для всех объектов Authserver и HMA будет включен, даже если один из этих объектов AuthServer **isDefaultAuthorizationEndpoint** флаг установлен для true.

## <a name="verify"></a>Проверка

После встраив HMA, следующий вход клиента будет использовать новый поток auth. Обратите внимание, что простое включение HMA не вызовет повторной оценки для любого клиента, и для Exchange может потребоваться некоторое время.

Кроме того, необходимо удерживать клавишу CTRL одновременно с правой кнопкой мыши значок для клиента Outlook (также в подносе Windows уведомлений) и нажмите кнопку "Состояние подключения". Иском адрес SMTP клиента в отношении типа 'Authn' 'Bearer', который представляет маркер носители, используемый \* в OAuth.

> [!NOTE]
> Необходимо настроить Skype для бизнеса с HMA? Вам потребуется две статьи: одна из них, которая перечисляет поддерживаемые [топологии,](/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)и одна, которая показывает, как [сделать конфигурацию.](configure-skype-for-business-for-hybrid-modern-authentication.md)


## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Гибридная современная проверка подлинности в случае Outlook для iOS и Android

Если вы — локальное клиент, использующее сервер Exchange TCP 443, обходить обработку трафика для следующих диапазонов IP-адресов:

```text
52.125.128.0/20
52.127.96.0/23
```

Приложение Outlook для iOS и Android разработано как лучший способ испытать Microsoft 365 или Office 365 на вашем мобильном устройстве с помощью службы Майкрософт для поиска, планирования и приоритетов вашей повседневной жизни и работы. Дополнительные сведения можно получить в ссылке Использование гибридной современной проверки подлинности [Outlook для iOS и Android.](/exchange/clients/outlook-for-ios-and-android/use-hybrid-modern-auth)

## <a name="related-topics"></a>Статьи по теме

[Современные требования к конфигурации проверки подлинности для перехода Office 365/ITAR на vNext](/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
