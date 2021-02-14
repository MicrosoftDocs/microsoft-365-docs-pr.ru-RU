---
title: Как настроить локальное развертывание Skype для бизнеса для использования гибридной современной проверки подлинности
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 522d5cec-4e1b-4cc3-937f-293570717bc6
ms.collection:
- M365-security-compliance
f1.keywords:
- NOCSH
description: Learn how to configure Skype for Business on-premises to use Hybrid Modern Authentication (HMA), offering you more secure user authentication and authorization.
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 74c8e3e0514fbfd8779c2f65e9c541c33b281c59
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46695026"
---
# <a name="how-to-configure-skype-for-business-on-premises-to-use-hybrid-modern-authentication"></a>Как настроить локальное развертывание Skype для бизнеса для использования гибридной современной проверки подлинности

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Современная проверка подлинности — это метод управления удостоверениями, который обеспечивает более безопасную проверку подлинности и авторизацию пользователей, доступен для локального сервера Skype для бизнеса и локального сервера Exchange, а также гибридных вариантов Skype для бизнеса с разделенным доменом.
  
 **Важно!** Хотите узнать больше о современной проверке подлинности и о том, почему вы предпочитаете использовать ее в своей компании или организации? Ознакомьтесь [с обзором](hybrid-modern-auth-overview.md) этого документа. Если вам нужно знать, какие topologies Skype для бизнеса поддерживаются с помощью ma, это описано здесь!
  
 **Прежде чем начать,** я использую указанные здесь термины.
  
- Современная проверка подлинности (MA)

- Гибридная современная проверка подлинности (HMA)

- Локальное exchange (EXCH)

- Exchange Online (EXO)

- Локальное приложение Skype для бизнеса (SFB)

- Skype для бизнеса Online (SFBO)

Кроме того, если на рисунке в этой статье имеется объект, серый или  серый, это означает, что элемент, показанный серым цветом, не включен в конфигурацию, специфическую для ma.
  
## <a name="read-the-summary"></a>Чтение сводки

Эта сводка разбивает процесс на шаги, которые в противном случае могут быть потеряны во время выполнения, и хорошо для общего контрольного списка для отслеживания того, где вы находитесь в этом процессе.
  
1. Во-первых, убедитесь, что вы соответствуете всем предварительным требованиям.

1. Так как **многие предварительные** условия являются общими как для Skype для бизнеса, так и для Exchange, см. обзорную статью контрольного списка перед [повторной проверкой.](hybrid-modern-auth-overview.md) Сделайте  *это,*  прежде чем приступить к любому из действий, которые необходимо предпринять в этой статье.

1. Соберет сведения, необходимые для HMA, в файле или OneNote.

1. Включит современную проверку подлинности для EXO (если она еще не включена).

1. Включит современную проверку подлинности для SFBO (если она еще не включена).

1. Включит гибридную современную проверку подлинности для локальной системы Exchange.

1. Turn ON Hybrid Modern Authentication for Skype for Business on-premises.

Эти действия включит ma для SFB, SFBO, EXCH и EXO, то есть все продукты, которые могут участвовать в конфигурации HMA SFB и SFBO (включая зависимости от EXCH/EXO). Другими словами, если ваши пользователи находятся в/имеют почтовые ящики, созданные в любой части гибридной системы (EXO + SFBO, EXO + SFB, EXCH + SFBO или EXCH + SFB), ваш готовый продукт будет выглядеть так:
  
![A Mixed 6 Skype for business HMA topology has MA on in all four possible locations.](../media/ab89cdf2-160b-49ac-9b71-0160800acfc8.png)
  
Как вы видите, есть четыре различных места для включаемой ma! Для лучшего пользовательского интерфейса мы рекомендуем включить ma во всех четырех этих расположениях. Если вы не можете включить ma во всех этих расположениях, настройте действия, чтобы включить ma только в расположениях, необходимых для вашей среды.
  
[Поддерживаемыеpologies см.](https://technet.microsoft.com/library/mt803262.aspx) в разделе "Поддержка Skype для бизнеса с ma".
  
 **Важно!** Перед началом убедитесь, что выполнены все необходимые условия. Эти сведения можно найти в обзоре современной гибридной проверки подлинности [и предварительных условиях.](hybrid-modern-auth-overview.md)
  
## <a name="collect-all-hma-specific-info-youll-need"></a>Соберйте все необходимые сведения о HMA

После двойного проверки того, [](hybrid-modern-auth-overview.md) что вы соответствуете предварительным требованиям для использования современной проверки подлинности (см. примечание выше), необходимо создать файл, в который будут вместить сведения, необходимые для настройки HMA на шагах вперед. Примеры, используемые в этой статье:
  
- **Домен SIP/SMTP**

  - Ex. contoso.com (федература с Office 365)

- **Идентификатор клиента**

  - GUID, который представляет клиент Office 365 (при входе contoso.onmicrosoft.com).

- **URL-адреса веб-службы SFB 2015 CU5**

Вам потребуется внутренний и внешний URL-адреса веб-служб для всех развернутых пулов SfB 2015. Чтобы получить эти данные, запустите в оболочке управления Skype для бизнеса следующее:
  
```powershell
Get-CsService -WebServer | Select-Object PoolFqdn, InternalFqdn, ExternalFqdn | FL
```

- Ex. Внутренний: https://lyncwebint01.contoso.com

- Ex. Внешний: https://lyncwebext01.contoso.com

Если вы используете сервер Standard Edition, внутренний URL-адрес будет пустым. В этом случае используйте для внутреннего URL-адреса fqdn пула.
  
## <a name="turn-on-modern-authentication-for-exo"></a>Включить современную проверку подлинности для EXO

Следуйте инструкциям в [Exchange Online: как](https://social.technet.microsoft.com/wiki/contents/articles/32711.exchange-online-how-to-enable-your-tenant-for-modern-authentication.aspx) включить современную проверку подлинности для клиента.
  
## <a name="turn-on-modern-authentication-for-sfbo"></a>Включить современную проверку подлинности для SFBO

Следуйте инструкциям здесь: [Skype для бизнеса Online: включить современную](https://social.technet.microsoft.com/wiki/contents/articles/34339.skype-for-business-online-enable-your-tenant-for-modern-authentication.aspx)проверку подлинности для клиента.
  
## <a name="turn-on-hybrid-modern-authentication-for-exchange-on-premises"></a>Включить гибридную современную проверку подлинности для локальной системы Exchange

Следуйте инструкциям здесь: как Exchange Server локально использовать гибридную современную [проверку подлинности.](configure-exchange-server-for-hybrid-modern-authentication.md)
  
## <a name="turn-on-hybrid-modern-authentication-for-skype-for-business-on-premises"></a>Turn on Hybrid Modern Authentication for Skype for Business on-premises

### <a name="add-on-premises-web-service-urls-as-spns-in-azure-active-directory"></a>Добавление URL-адресов локальной веб-службы в качестве SPNs в Azure Active Directory

Теперь необходимо выполнить команды, чтобы добавить URL-адреса (собранные ранее) в качестве основных служб в SFBO.
  
 **Примечание** Имена основных служб (SPNs) определяют веб-службы и связывают их с основными службами безопасности (например, именем учетной записи или группой), чтобы служба могли действовать от имени авторизованного пользователя. Клиенты, которые используют проверку подлинности на сервере, используют сведения, содержащиеся в SPNs.
  
1. Сначала подключите к Azure Active Directory (Azure AD) с [помощью этих инструкций.](https://docs.microsoft.com/powershell/azure/active-directory/overview?view=azureadps-1.0)

2. Чтобы получить список URL-адресов веб-службы SFB, запустите эту команду локально.

   Обратите внимание, что AppPrincipalId начинается с `00000004` . Это соответствует Skype для бизнеса Online.

   Обратите внимание (и снимок экрана для более позднего сравнения) результатов этой команды, которые будут включать SE и URL-адрес WS, но в основном состоят из SPNs, которые начинаются `00000004-0000-0ff1-ce00-000000000000/` с .

```powershell
Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 | Select -ExpandProperty ServicePrincipalNames
```

3. Если внутренние **или** внешние URL-адреса SFB из локальной системы отсутствуют (например, нам потребуется добавить эти записи в https://lyncwebint01.contoso.com этот https://lyncwebext01.contoso.com) список.

    Не забудьте заменить  *url-адреса примера ниже* на фактические URL-адреса в командах "Добавить"!
  
```powershell
$x= Get-MsolServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000
$x.ServicePrincipalnames.Add("https://lyncwebint01.contoso.com/")
$x.ServicePrincipalnames.Add("https://lyncwebext01.contoso.com/")
Set-MSOLServicePrincipal -AppPrincipalId 00000004-0000-0ff1-ce00-000000000000 -ServicePrincipalNames $x.ServicePrincipalNames
```
  
4. Убедитесь, что новые записи были добавлены, снова выпустив команду **Get-MsolServicePrincipal** из шага 2 и проверив выходные данные. Сравните список или снимок экрана с новым списком spNs. Вы также можете сделать снимок экрана с новым списком для ваших записей. В случае успеха вы увидите два новых URL-адреса в списке. В нашем примере список SPNs теперь будет включать определенные URL-адреса https://lyncwebint01.contoso.com и https://lyncwebext01.contoso.com/ .

### <a name="create-the-evosts-auth-server-object"></a>Создание объекта сервера веб-службы Веб-службы

Запустите следующую команду в командной оболочке Skype для бизнеса.
  
```powershell
New-CsOAuthServer -Identity evoSTS -MetadataURL https://login.windows.net/common/FederationMetadata/2007-06/FederationMetadata.xml -AcceptSecurityIdentifierInformation $true -Type AzureAD
```

### <a name="enable-hybrid-modern-authentication"></a>Включить гибридную современную проверку подлинности

На этом этапе фактически включается ma. Все предыдущие шаги можно выполнить заранее, не изменяя поток проверки подлинности клиента. Когда вы будете готовы изменить поток проверки подлинности, запустите эту команду в командной оболочке Skype для бизнеса.

```powershell
Set-CsOAuthConfiguration -ClientAuthorizationOAuthServerIdentity evoSTS
```

## <a name="verify"></a>Проверка

После того как вы в включить HMA, следующий вход клиента будет использовать новый поток авторов. Обратите внимание, что простое включение HMA не вызовет повторной оценки для любого клиента. Клиенты повторно проавтоматируют их в зависимости от срока действия маркеров и/или сертификатов, которые у них есть.
  
Чтобы проверить работу HMA после включения, выйдите из тестового клиента Windows SFB и нажмите кнопку "Удалить мои учетные данные". Снова во входе. Теперь клиент должен использовать поток современной проверки право на проверку, и теперь для входа в систему будет включен запрос **Office 365** для учетной записи "Рабочий или учебный", который будет виден прямо перед тем, как клиент свянется с сервером и занося вас в систему.
  
Также следует проверить "Сведения о конфигурации" для клиентов Skype для бизнеса на "OAuth Authority". Для этого на клиентских компьютерах удерживайте клавишу CTRL, щелкнув правой кнопкой мыши значок Skype для бизнеса в области уведомлений Windows. Щелкните **"Сведения о** конфигурации" в меню. In the 'Skype for Business Configuration Information' window that will appear on the desktop, look for the following:
  
![The Configuration information of a Skype for Business Client using Modern Authentication shows a Lync and EWS OAUTH Authority URL of https://login.windows.net/common/oauth2/authorize .](../media/4e54edf5-c8f8-4e7f-b032-5d413b0232de.png)
  
Также следует удерживать клавишу CTRL одновременно с щелчком правой кнопкой мыши по значку клиента Outlook (также в области уведомлений Windows) и нажатием кнопки "Состояние подключения". Наберем SMTP-адрес клиента по типу AuthN "Bearer", который представляет маркер носитера, используемый \* в OAuth.
  
## <a name="related-articles"></a>Статьи по теме

[Ссылка на обзор современной проверки подлинности.](hybrid-modern-auth-overview.md)
  
Нужно знать, как использовать современную проверку подлинности (ADAL) для клиентов Skype для бизнеса? У нас есть по [шагам здесь.](https://technet.microsoft.com/library/mt710548.aspx)
