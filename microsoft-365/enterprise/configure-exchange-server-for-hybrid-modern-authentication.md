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
description: Узнайте, как настроить локальную систему Exchange Server для использования гибридной современной проверки подлинности (HMA), обеспечивая более безопасную проверку подлинности и авторизацию пользователей.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8db74c04335e0846666991d74980648cedb4d9d7
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47547134"
---
# <a name="how-to-configure-exchange-server-on-premises-to-use-hybrid-modern-authentication"></a>Как настроить локальное развертывание Exchange Server для использования гибридной современной проверки подлинности

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Гибридная современная проверка подлинности (HMA) — это способ управления удостоверениями, обеспечивающий более безопасную проверку подлинности и авторизацию пользователей, а также доступный для локальных гибридных развертываний Exchange Server.

## <a name="fyi"></a>СВЕДЕНИЮ

Прежде чем начать, я вызываю:

- Гибридная современная проверка подлинности \> HMA

- Локальная служба Exchange ( \> Дов)

- Exchange Online \> exo

Кроме того, *Если рисунок в этой статье содержит объект с серым или затемненным элементом, то это означает, что элемент, отображаемый серым цветом, не включается в конфигурацию, характерную для HMA* .

## <a name="enabling-hybrid-modern-authentication"></a>Включение гибридной современной проверки подлинности

При повороте HMA на средних отключаются:

1. Прежде чем приступить к работе, убедитесь, что вы соответствуете пререкс.

1. Так как многие **Предварительные требования** распространены как для Skype для бизнеса, так и для Exchange, [Гибридная современная проверка подлинности и предварительные требования для их использования с локальными серверами Skype для бизнеса и Exchange](hybrid-modern-auth-overview.md). Выполните это действие, прежде чем приступать к каким – либо действиям, описанным в этой статье.

1. Добавление локальных URL-адресов веб-служб в Azure AD в качестве **имен участников-служб (SPN)** .

1. Обеспечение включения всех виртуальных каталогов в верхнюю область памяти

1. Проверка наличия объекта сервера проверки подлинности Евостс

1. Включение HMA в КУРСах

 **Note (Примечание** ) Поддерживает ли ваша версия Office мА? Узнайте [, как работает современная проверка подлинности для клиентских приложений office 2013 и office 2016](modern-auth-for-office-2013-and-2016.md).

## <a name="make-sure-you-meet-all-the-prerequisites"></a>Убедитесь, что все необходимые компоненты соблюдены.

Так как многие предварительные требования распространены как для Skype для бизнеса, так и для Exchange, ознакомьтесь с [обзором гибридной современной проверки подлинности и необходимыми требованиями для его использования с локальными серверами Skype для бизнеса и Exchange](hybrid-modern-auth-overview.md). Выполните это действие,  *прежде чем*  приступать к каким – либо действиям, описанным в этой статье.

## <a name="add-on-premises-web-service-urls-as-spns-in-azure-ad"></a>Добавление локальных URL-адресов веб-служб в Azure AD в качестве SPN

Выполните команды, которые назначают URL-адреса локальной веб-службы как SPN Azure AD. Имена участников-служб используются клиентскими компьютерами и устройствами во время проверки подлинности и авторизации. Все URL-адреса, которые могут использоваться для подключения из локальной в Azure Active Directory (Azure AD), должны быть зарегистрированы в Azure AD (сюда входят как внутренние, так и внешние пространства имен).

Сначала соберите все URL-адреса, которые необходимо добавить в AAD. Выполните следующие команды в локальной среде:

```powershell
Get-MapiVirtualDirectory | FL server,*url*
Get-WebServicesVirtualDirectory | FL server,*url*
Get-ClientAccessServer | fl Name, AutodiscoverServiceInternalUri
Get-OABVirtualDirectory | FL server,*url*
Get-AutodiscoverVirtualDirectory | FL server,*url*
Get-OutlookAnywhere | FL server,*url*
```

Убедитесь, что URL-адреса, к которым могут подключаться клиенты, указаны как имена субъектов-служб HTTPS в AAD.

1. Для начала подключитесь к AAD с помощью [приведенных ниже инструкций](connect-to-microsoft-365-powershell.md).

   **Note (Примечание** ) Для использования указанной ниже команды необходимо использовать параметр _Connect-MsolService_ на этой странице.

2. Для URL-адресов, относящихся к Exchange, введите следующую команду:

   ```powershell
   Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 | select -ExpandProperty ServicePrincipalNames
   ```

   Запишите (и снимок экрана для последующего сравнения) выходные данные этой команды, которые должны содержать URL-адрес https://  *autodiscover.yourdomain.com*  и HTTPS://  *mail.yourdomain.com* , но в основном состоит из имен участников-служб, начинающихся с 00000002-0000-0ff1-ce00-000000000000/. Если у вас есть URL-адреса https://из локальной среды, которые отсутствуют, вам потребуется добавить эти записи в этот список.

3. Если вы не видите внутреннюю и внешнюю записи MAPI/HTTP, EWS, ActiveSync, OAB и автообнаружения в этом списке, их необходимо добавить с помощью приведенной ниже команды (например, URL-адреса " `mail.corp.contoso.com` " и " `owa.contoso.com` "), но вы **заменили свои примеры URL-адресов своими собственными** :

   ```powershell
   $x= Get-MsolServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000
   $x.ServicePrincipalnames.Add("https://mail.corp.contoso.com/")
   $x.ServicePrincipalnames.Add("https://owa.contoso.com/")
   Set-MSOLServicePrincipal -AppPrincipalId 00000002-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
   ```

4. Проверьте, были ли добавлены новые записи, выполнив команду Get – MsolServicePrincipal повторно с шага 2 и просмотрев результаты. Сравнение списка и снимка экрана перед новым списком имен участников-служб (вы также можете создать список снимков экрана для записи). В случае успеха в списке отобразятся два новых URL-адреса. В нашем примере список SPN теперь включает определенные URL-адреса  `https://mail.corp.contoso.com`  и  `https://owa.contoso.com` .

## <a name="verify-virtual-directories-are-properly-configured"></a>Проверка правильности настройки виртуальных каталогов

Теперь проверьте правильность включения OAuth в Exchange для всех виртуальных каталогов, которые Outlook может использовать, выполнив следующие команды:

```powershell
Get-MapiVirtualDirectory | FL server,*url*,*auth*
Get-WebServicesVirtualDirectory | FL server,*url*,*oauth*
Get-OABVirtualDirectory | FL server,*url*,*oauth*
Get-AutoDiscoverVirtualDirectory | FL server,*oauth*
```

Проверьте выходные данные, чтобы убедиться в том, что **OAuth** включен для каждого из этих вдирс, он будет выглядеть примерно так, как показано в разделе "OAuth".

```powershell
Get-MapiVirtualDirectory | fl server,*url*,*auth*

Server                        : EX1
InternalUrl                   : https://mail.contoso.com/mapi
ExternalUrl                   : https://mail.contoso.com/mapi
IISAuthenticationMethods      : {Ntlm, OAuth, Negotiate}
InternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
ExternalAuthenticationMethods : {Ntlm, OAuth, Negotiate}
```

Если OAuth отсутствует на каком-либо сервере и в любом из четырех виртуальных каталогов, необходимо добавить его с помощью соответствующих команд перед продолжением работы ([Set-мапивиртуалдиректори](https://docs.microsoft.com/powershell/module/exchange/set-mapivirtualdirectory), [Set-webservicesvirtualdirectory используется](https://docs.microsoft.com/powershell/module/exchange/set-webservicesvirtualdirectory), [Set-OABVirtualDirectory](https://docs.microsoft.com/powershell/module/exchange/set-oabvirtualdirectory)и [Set-AutodiscoverVirtualDirectory используется](https://docs.microsoft.com/powershell/module/exchange/set-autodiscovervirtualdirectory)).

## <a name="confirm-the-evosts-auth-server-object-is-present"></a>Подтвердите, что присутствует объект сервера проверки подлинности Евостс

Вернитесь в локальную консоль управления Exchange для последней команды. Теперь вы можете проверить, что в локальной организации есть запись для поставщика проверки подлинности Евостс:

```powershell
Get-AuthServer | where {$_.Name -eq "EvoSts"}
```

В выходных данных должен отображаться AuthServer имени Евостс, а состояние Enabled должно иметь значение true. Если вы не видите это значение, скачайте и запустите последнюю версию мастера гибридной конфигурации.

 **Важно!** Если вы используете Exchange 2010 в своей среде, то поставщик проверки подлинности Евостс не будет создан.

## <a name="enable-hma"></a>Включение HMA

Выполните в командной консоли Exchange следующую команду:

```powershell
Set-AuthServer -Identity EvoSTS -IsDefaultAuthorizationEndpoint $true
Set-OrganizationConfig -OAuth2ClientProfileEnabled $true
```

## <a name="verify"></a>Читаем

После включения HMA для следующего входа клиента будет использоваться новый процесс проверки подлинности. Обратите внимание, что просто включение HMA не вызывает повторную проверку подлинности для любого клиента. Клиенты повторно проходят проверку подлинности на основе времени существования маркеров и/или сертификатов проверки подлинности.

Кроме того, следует удерживать нажатой клавишу CTRL, щелкнув значок клиента Outlook (также в области уведомлений Windows), и выберите пункт "состояние подключения". Найдите SMTP-адрес клиента для типа "определения" носителя "Bearer \* ", который представляет токен носителя, используемый в OAuth.

 **Note (Примечание** ) Требуется настроить Skype для бизнеса с HMA? Вам потребуются две статьи: одна, в которой перечислены [Поддерживаемые топологии](https://docs.microsoft.com/skypeforbusiness/plan-your-deployment/modern-authentication/topologies-supported)и одна, которая показывает, [как выполнить настройку](configure-skype-for-business-for-hybrid-modern-authentication.md).

## <a name="using-hybrid-modern-authentication-with-outlook-for-ios-and-android"></a>Гибридная современная проверка подлинности в случае Outlook для iOS и Android

Если вы являетесь локальным клиентом, использующим Exchange Server по протоколу TCP 443, белом следующие диапазоны IP-адресов:

```text
52.125.128.0/20
52.127.96.0/23
```

## <a name="related-topics"></a>Статьи по теме

[Требования к конфигурации современного режима проверки подлинности для перехода от Office 365 выделенный/ITAR к vNext](https://docs.microsoft.com/exchange/troubleshoot/modern-authentication/modern-authentication-configuration)
