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
description: Узнайте, как настроить Exchange Server локально для использования гибридной современной проверки подлинности (HMA), что обеспечивает более безопасную проверку подлинности и авторизацию пользователей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3841f429399500cfc24ebadc89c74d478d2290d9
ms.sourcegitcommit: ec293978e951b09903b79e6642aa587824935e0c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/07/2021
ms.locfileid: "49780288"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Гибридная современная проверка подлинности (HMA) — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей и доступен для локального гибридного развертывания сервера Exchange Server.

## <a name="fyi"></a>FYI

Прежде чем начать, я вызываю:

- HMA гибридной \> современной проверки подлинности

- Exchange on-premises \> EXCH

- Exchange Online \> EXO

Кроме того, если на рисунке в этой статье имеется объект с серым или серым цветом, это означает, что элемент, показанный серым цветом, не включен в конфигурацию, специфиченную для *HMA.*

## <a name="enabling-hybrid-modern-authentication"></a>Включение гибридной современной проверки подлинности

Включение HMA означает:

1. Перед началом убедитесь, что вы соответствуете предварительным требованиям.

1. Так **как** многие предварительные условия являются общими как для Skype для бизнеса, так и для Exchange, обзор гибридной современной проверки подлинности и необходимые условия для ее использования с локальной skype для бизнеса и [серверами Exchange.](hybrid-modern-auth-overview.md) Сделайте это, прежде чем приступить к любому из действий, которые необходимо предпринять в этой статье.

1. Добавление URL-адресов локальной веб-службы в качестве имен основных служб **(SPNs)** в Azure AD.

1. Обеспечение включения HMA для всех виртуальных каталогов

1. Проверка на предмет объекта Веб-сервер проверки Веб-службы СтиСТА

1. Включение HMA в EXCH.

 **Примечание** Поддерживает ли ваша версия Office ma? Узнайте, как работает современная проверка подлинности для клиентских приложений [Office 2013 и Office 2016.](modern-auth-for-office-2013-and-2016.md)

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Убедитесь, что вы соответствуете всем предварительным требованиям

Так как многие предварительные условия являются общими как для Skype для бизнеса, так и для Exchange, просмотрите обзор гибридной современной проверки подлинности и необходимые условия для ее использования с локальной версией Skype для бизнеса и [серверами Exchange.](hybrid-modern-auth-overview.md) Сделайте  *это,*  прежде чем приступить к любому из действий, которые необходимо предпринять в этой статье.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Добавление URL-адресов локальной веб-службы в качестве SPNs в Azure AD

Запустите команды, которые назначают URL-адреса локальной веб-службы в качестве spNs Azure AD. SpNs используются клиентских компьютеров и устройств во время проверки подлинности и авторизации. Все URL-адреса, которые могут использоваться для подключения локально к Azure Active Directory (Azure AD), должны быть зарегистрированы в Azure AD (к ним относятся как внутренние, так и внешние пространства имен).

Сначала соберем все URL-адреса, которые необходимо добавить в AAD. Запустите эти команды локально:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

Убедитесь, что клиенты URL-адресов, к которые могут подключаться, указаны в AAD как имена основных служб HTTPS.

1. Во-первых, подключите AAD с [помощью этих инструкций.](connect-to-microsoft-365-powershell.md)

   **Примечание** Чтобы использовать приведенную ниже команду, необходимо использовать параметр _Connect-MsolService_ на этой странице.

2. Для URL-адресов, связанных с Exchange, введите следующую команду:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Обратите внимание (и снимок экрана для более позднего сравнения) результатов этой команды, которые должны включать URL-адрес https://  *autodiscover.yourdomain.com*  и https://  *mail.yourdomain.com,* но в основном состоят из SPNs, которые начинаются с 000000002-0000-0ff1-ce00-000000000000/. Если отсутствуют https:// url-адреса из локальной данной области, нам потребуется добавить эти записи в этот список.

3. Если в этом списке нет внутренних и внешних записей MAPI/HTTP, EWS, ActiveSync, OAB и Autodiscover, их необходимо добавить с помощью приведенной ниже команды (например, URL-адреса " и "", но вы замените примеры URL-адресов `mail.corp.contoso.com` `owa.contoso.com` собственными): 

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Убедитесь, что новые записи были добавлены, вы Get-MsolServicePrincipal команду из шага 2 и проверьте выходные данные. Сравните список или снимок экрана с новым списком spNs. Вы также можете сделать снимок экрана с новым списком для ваших записей. Если вы успешно сравнелись, вы увидите два новых URL-адреса в списке. В нашем примере список SPNs теперь будет включать определенные URL-адреса  `https://mail.corp.contoso.com`  и  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Проверка правильной настройки виртуальных каталогов

Теперь убедитесь, что OAuth правильно включен в Exchange во всех виртуальных каталогах Outlook, вы можете использовать следующие команды:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Проверьте выходные данные, чтобы убедиться, что **OAuth** включен в каждом из этих VDirs, он будет выглядеть так (и ключевой момент, на который нужно посмотреть, — OAuth):

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Если OAuth отсутствует на любом сервере и в любом из четырех виртуальных каталогов, необходимо добавить его, используя соответствующие команды, прежде чем перезапись ([Set-MapiVirtualDirectory,](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory) [Set-WebServicesVirtualDirectory,](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory) [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)и [Set-AutodiscoverVirtualDirectory).](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Подтверждение на наличие объекта сервера Веб-службы СтиСТА

Вернись к локальной командной оболочке Exchange для этой последней команды. Теперь вы можете проверить, есть ли в локальной сети запись для поставщика проверки подлинности premisestS:

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

Выходные данные должны показывать AuthServer для Name Sts, а состояние Enabled должно быть True. Если вы этого не видите, скачайте и запустите наиболее новую версию мастера гибридной конфигурации.

 **Важно!** Если в вашей среде запущен Exchange 2010, поставщик проверки подлинности ЛожSTS не будет создан.

## <a name="enable-hma"></a>Включить HMA

В локальной командной оболочке Exchange запустите следующую команду:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Проверка

После того как вы в включить HMA, следующий вход клиента будет использовать новый поток авторов. Обратите внимание, что простое включение HMA не вызовет повторной оценки для любого клиента. Клиенты повторно проавтоматируют их в зависимости от срока действия маркеров и/или сертификатов, которые у них есть.

Также следует удерживать клавишу CTRL одновременно с щелчком правой кнопкой мыши по значку клиента Outlook (также в области уведомлений Windows) и нажатием кнопки "Состояние подключения". Наберем SMTP-адрес клиента по типу "Authn" типа "Bearer", который представляет маркер носители, используемый \* в OAuth.

 **Примечание** Необходимо настроить Skype для бизнеса с HMA? Вам потребуется две статьи: в одной из них перечислены поддерживаемыеpologies, а в одной — показано, как [это сделать.](configure-skype-for-business-for-hybrid-modern-authentication.md) [](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Гибридная современная проверка подлинности в случае Outlook для iOS и Android

Если вы используете сервер Exchange Server на локальном сервере TCP 443, обходить обработку трафика для следующих диапазонов IP-адресов:

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>Связанные статьи

[Требования к конфигурации современной проверки подлинности для перехода с office 365 dedicated/ITAR на vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
