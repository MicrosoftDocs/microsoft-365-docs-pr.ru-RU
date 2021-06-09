---
title: Добавление домена в клиентскую аренду с Windows PowerShell для партнеров DAP
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- M365-subscription-management
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.assetid: f49b4d24-9aa0-48a6-95dd-6bae9cf53d2c
description: Сводка. Используйте PowerShell для Microsoft 365, чтобы добавить альтернативное доменное имя существующему клиенту.
ms.openlocfilehash: b6a40f387f9fc7e513137cda4253a62be2455aad
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905576"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a>Добавление домена к аренде клиента с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)

*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*

Вы можете создавать и связывать новые домены с арендой клиента с PowerShell Microsoft 365 быстрее, чем Microsoft 365 центра администрирования.
  
Партнеры по делегированным правам доступа (DAP)  партнеры по синдикации и поставщики облачных решений (CSP). Они часто бывают поставщиками сети или телекоммуникационных услуг в других компаниях. Они Microsoft 365 подписок в свои предложения по обслуживанию для своих клиентов. Когда они продают подписку Microsoft 365, они автоматически получают разрешения администрирования от имени (AOBO) для клиентов tenancies, чтобы они могли администрирование и отчет о клиентских tenancies.
## <a name="what-do-you-need-to-know-before-you-begin"></a>Что нужно знать перед началом работы

Процедуры в этом разделе требуют подключения Подключение [к Microsoft 365 PowerShell](connect-to-microsoft-365-powershell.md).
  
Вам также необходимы учетные данные администратора для клиента партнера.
  
Кроме того, понадобятся указанные ниже сведения.
  
- Необходимо полное доменное имя (FQDN), которое  требуется вашему клиенту.
    
- Вам необходим идентификатор **TenantId** пользователя.
    
- Полное доменное имя должно быть зарегистрировано у регистратора служб доменных имен Интернета (DNS), например GoDaddy. Дополнительные сведения о том, как публично зарегистрировать доменное имя, см. в статье [Приобретение доменного имени](../admin/get-help-with-domains/buy-a-domain-name.md).
    
- Вам необходимо знать, как добавить запись типа TXT в зарегистрированную зону DNS для своего регистратора DNS. Дополнительные сведения о добавлении записи TXT см. в добавлении [записей DNS для подключения домена.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) Если эти действия вам не помогут, потребуется найти инструкции, касающиеся вашего регистратора DNS.
    
## <a name="create-domains"></a>Создание доменов

 Ваши клиенты, скорее всего, попросят вас создать дополнительные домены, чтобы связать их с со своим клиентом, поскольку они не хотят, чтобы стандартный домен<домен>.onmicrosoft.comбыл основным, который представляет лицо их организации всему миру. Это руководство поможет вам создать новый домен, связанный с пользовательским клиентом.
  
> [!NOTE]
> Чтобы выполнить некоторые из этих операций, учетная запись администратора партнера,  с помощью которых вы входили, должна быть настроена на полное администрирование для назначения административного доступа к компаниям, которые поддерживают параметр, найденный в сведениях учетной записи администратора в центре администрирования Microsoft 365 администратора.  Дополнительные сведения об управлении ролями администратора партнеров см. в [сайте Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435). 
  
### <a name="create-the-domain-in-azure-active-directory"></a>Создание домена в Azure Active Directory

Эта команда создает домен в Azure Active Directory, но не связывает его с публично зарегистрированным доменом. Это происходит, когда вы докажете, что вы владеете общедоступным доменом microsoft Microsoft 365 для предприятий.
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
>В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени. Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a>Получение данных для записи TXT проверки DNS

 Microsoft 365 будет создавать конкретные данные, которые необходимо разместить в записи проверки TXT DNS. Чтобы получить эти данные, выполните указанную ниже команду.
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

Выходные данные будут иметь следующий вид:
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> Этот текст потребуется для создания записи TXT в публично зарегистрированной зоне DNS. Обязательно скопируйте и сохраните его. 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a>Добавление записи TXT в публично зарегистрированную зону DNS

Прежде Microsoft 365 начнет принимать трафик, который направляется на общедоступные доменные имена, необходимо доказать, что у вас есть и есть разрешения администратора на домен. Для этого нужно создать для домена запись типа TXT. Такая запись не выполняет никаких действий в домене, и ее можно удалить, когда ваше владение доменом будет подтверждено. Чтобы создать записи TXT, выполните процедуры в [Add DNS records для подключения домена.](../admin/get-help-with-domains/create-dns-records-at-any-dns-hosting-provider.md) Если эти действия вам не помогут, потребуется найти процедуры для своего регистратора DNS.
  
Убедитесь, что запись TXT создана успешно, с помощью команды nslookup. Используйте следующий синтаксис.
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

Выходные данные будут иметь следующий вид:
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a>Проверка владения доменом в Microsoft 365

На последнем шаге вы проверяете, Microsoft 365, что вы владеете общедоступным доменом. После этого шага Microsoft 365 начнется прием трафика, маршрутного для нового доменного имени. Чтобы завершить процесс создания и регистрации домена, выполните следующую команду. 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Эта команда не возвращает выходных данных, поэтому для проверки выполните следующую команду.
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

Выходные данные имеют следующий вид:

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a>См. также

#### 

[Справка для партнеров](https://go.microsoft.com/fwlink/p/?LinkID=533477)