---
title: Добавление домена в клиентскую тенантность с Windows PowerShell для партнеров DAP
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
description: Сводка. Добавление альтернативного доменного имени в существующий клиент клиента с помощью PowerShell для Microsoft 365.
ms.openlocfilehash: 23137d2e2461e75a22d0403f9b8246a29e48019f
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693535"
---
# <a name="add-a-domain-to-a-client-tenancy-with-windows-powershell-for-delegated-access-permission-dap-partners"></a><span data-ttu-id="e7b91-103">Добавление домена к аренде клиента с помощью Windows PowerShell для партнеров службы разрешений делегированного доступа (DAP)</span><span class="sxs-lookup"><span data-stu-id="e7b91-103">Add a domain to a client tenancy with Windows PowerShell for Delegated Access Permission (DAP) partners</span></span>

<span data-ttu-id="e7b91-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="e7b91-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e7b91-105">Вы можете создавать и связывать новые домены с клиентом клиента с помощью PowerShell для Microsoft 365 быстрее, чем с помощью Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e7b91-105">You can create and associate new domains with your customer's tenancy with PowerShell for Microsoft 365 faster than using the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="e7b91-106">Партнеры по делегированным правам доступа (DAP)  партнеры по синдикации и поставщики облачных решений (CSP).</span><span class="sxs-lookup"><span data-stu-id="e7b91-106">Delegated Access Permission (DAP) partners are Syndication and Cloud Solution Providers (CSP) Partners.</span></span> <span data-ttu-id="e7b91-107">Они часто бывают поставщиками сети или телекоммуникационных услуг в других компаниях.</span><span class="sxs-lookup"><span data-stu-id="e7b91-107">They are frequently network or telecom providers to other companies.</span></span> <span data-ttu-id="e7b91-108">Они предлагают своим клиентам подписки на Microsoft 365 в пакете.</span><span class="sxs-lookup"><span data-stu-id="e7b91-108">They bundle Microsoft 365 subscriptions into their service offerings to their customers.</span></span> <span data-ttu-id="e7b91-109">При продаже подписки На Microsoft 365 им автоматически ируются разрешения на администрирование от имени (AOBO) для клиентов клиента, чтобы они могли администрировать и сообщать о клиентах.</span><span class="sxs-lookup"><span data-stu-id="e7b91-109">When they sell a Microsoft 365 subscription, they are automatically granted Administer On Behalf Of (AOBO) permissions to the customer tenancies so they can administer and report on the customer tenancies.</span></span>
## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="e7b91-110">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="e7b91-110">What do you need to know before you begin?</span></span>

<span data-ttu-id="e7b91-111">Процедуры в этом разделе требуют подключения к [Microsoft 365 с помощью PowerShell.](connect-to-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e7b91-111">The procedures in this topic require you to connect to [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md).</span></span>
  
<span data-ttu-id="e7b91-112">Вам также необходимы учетные данные администратора для клиента партнера.</span><span class="sxs-lookup"><span data-stu-id="e7b91-112">You also need your partner tenant administrator credentials.</span></span>
  
<span data-ttu-id="e7b91-113">Кроме того, понадобятся указанные ниже сведения.</span><span class="sxs-lookup"><span data-stu-id="e7b91-113">You also need the following information:</span></span>
  
- <span data-ttu-id="e7b91-114">Необходимо полное доменное имя (FQDN), которое  требуется вашему клиенту.</span><span class="sxs-lookup"><span data-stu-id="e7b91-114">You need the fully qualified domain name (FQDN) that your customer wants.</span></span>
    
- <span data-ttu-id="e7b91-115">Вам необходим идентификатор **TenantId** пользователя.</span><span class="sxs-lookup"><span data-stu-id="e7b91-115">You need the customer's **TenantId**.</span></span>
    
- <span data-ttu-id="e7b91-p102">Полное доменное имя должно быть зарегистрировано у регистратора служб доменных имен Интернета (DNS), например GoDaddy. Дополнительные сведения о том, как публично зарегистрировать доменное имя, см. в статье [Приобретение доменного имени](https://go.microsoft.com/fwlink/p/?LinkId=532541).</span><span class="sxs-lookup"><span data-stu-id="e7b91-p102">The FQDN must be registered with an Internet domain name service (DNS) registrar, such as GoDaddy. For more information on how to publically register a domain name, see [How to buy a domain name](https://go.microsoft.com/fwlink/p/?LinkId=532541).</span></span>
    
- <span data-ttu-id="e7b91-118">Вам необходимо знать, как добавить запись типа TXT в зарегистрированную зону DNS для своего регистратора DNS.</span><span class="sxs-lookup"><span data-stu-id="e7b91-118">You need to know how to add a TXT record to the registered DNS zone for your DNS registrar.</span></span> <span data-ttu-id="e7b91-119">Дополнительные сведения о добавлении записи TXT см. в подключении домена к записи ["Добавление записей DNS".](https://go.microsoft.com/fwlink/p/?LinkId=532542)</span><span class="sxs-lookup"><span data-stu-id="e7b91-119">For more information on how to add a TXT record, see [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="e7b91-120">Если эти действия вам не помогут, потребуется найти инструкции, касающиеся вашего регистратора DNS.</span><span class="sxs-lookup"><span data-stu-id="e7b91-120">If those procedures don't work for you, you will need to find the procedures for your DNS registrar.</span></span>
    
## <a name="create-domains"></a><span data-ttu-id="e7b91-121">Создание доменов</span><span class="sxs-lookup"><span data-stu-id="e7b91-121">Create domains</span></span>

 <span data-ttu-id="e7b91-p104">Ваши клиенты, скорее всего, попросят вас создать дополнительные домены, чтобы связать их с со своим клиентом, поскольку они не хотят, чтобы стандартный домен<домен>.onmicrosoft.comбыл основным, который представляет лицо их организации всему миру. Это руководство поможет вам создать новый домен, связанный с пользовательским клиентом.</span><span class="sxs-lookup"><span data-stu-id="e7b91-p104">Your customers will likely ask you to create additional domains to associate with their tenancy because they don't want the default <domain>.onmicrosoft.com domain to be the primary one that represents their corporate identities to the world. This procedure walks you through creating a new domain associated with your customer's tenancy.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e7b91-124">Для выполнения некоторых из этих операций учетной записи администратора партнера,  с помощью которых вы выполняете вход, необходимо задать полное администрирование для назначения административного доступа компаниям, которые вы поддерживаете параметр, указанный в сведениях учетной записи администратора в Центре администрирования Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="e7b91-124">To perform some of these operations, the partner administrator account you sign in with must be set to **Full administration** for the **Assign administrative access to companies you support** setting found in the details of the admin account in the Microsoft 365 admin center.</span></span> <span data-ttu-id="e7b91-125">Дополнительные сведения об управлении ролями администраторов партнеров см. в [сведениях о партнерах: предложение делегирования администрирования.](https://go.microsoft.com/fwlink/p/?LinkId=532435)</span><span class="sxs-lookup"><span data-stu-id="e7b91-125">For more information on managing partner administrator roles, see [Partners: Offer delegated administration](https://go.microsoft.com/fwlink/p/?LinkId=532435).</span></span> 
  
### <a name="create-the-domain-in-azure-active-directory"></a><span data-ttu-id="e7b91-126">Создание домена в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="e7b91-126">Create the domain in Azure Active Directory</span></span>

<span data-ttu-id="e7b91-127">Эта команда создает домен в Azure Active Directory, но не связывает его с публично зарегистрированным доменом.</span><span class="sxs-lookup"><span data-stu-id="e7b91-127">This command creates the domain in Azure Active Directory but does not associate it with the publicly registered domain.</span></span> <span data-ttu-id="e7b91-128">Это происходит, когда вы докажете, что вы владеете публично зарегистрированным доменом в Microsoft Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="e7b91-128">That comes when you prove that you own the publicly registered domain to Microsoft Microsoft 365 for enterprises.</span></span>
  
```powershell
New-MsolDomain -TenantId <customer TenantId> -Name <FQDN of new domain>
```

>[!Note]
><span data-ttu-id="e7b91-129">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="e7b91-129">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e7b91-130">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e7b91-130">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

### <a name="get-the-data-for-the-dns-txt-verification-record"></a><span data-ttu-id="e7b91-131">Получение данных для записи TXT проверки DNS</span><span class="sxs-lookup"><span data-stu-id="e7b91-131">Get the data for the DNS TXT verification record</span></span>

 <span data-ttu-id="e7b91-132">Microsoft 365 создает определенные данные, которые необходимо разместить в записи проверки DNS TXT.</span><span class="sxs-lookup"><span data-stu-id="e7b91-132">Microsoft 365 will generate the specific data that you need to place into the DNS TXT verification record.</span></span> <span data-ttu-id="e7b91-133">Чтобы получить эти данные, выполните указанную ниже команду.</span><span class="sxs-lookup"><span data-stu-id="e7b91-133">To get the data, run this command.</span></span>
  
```powershell
Get-MsolDomainVerificationDNS -TenantId <customer TenantId> -DomainName <FQDN of new domain> -Mode DnsTxtRecord
```

<span data-ttu-id="e7b91-134">Выходные данные будут иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="e7b91-134">This will give you output like:</span></span>
  
 `Label: domainname.com`
  
 `Text: MS=ms########`
  
 `Ttl: 3600`
  
> [!NOTE]
> <span data-ttu-id="e7b91-135">Этот текст потребуется для создания записи TXT в публично зарегистрированной зоне DNS.</span><span class="sxs-lookup"><span data-stu-id="e7b91-135">You will need this text to create the TXT record in the publicly registered DNS zone.</span></span> <span data-ttu-id="e7b91-136">Обязательно скопируйте и сохраните его.</span><span class="sxs-lookup"><span data-stu-id="e7b91-136">Be sure to copy and save it.</span></span> 
  
### <a name="add-a-txt-record-to-the-publically-registered-dns-zone"></a><span data-ttu-id="e7b91-137">Добавление записи TXT в публично зарегистрированную зону DNS</span><span class="sxs-lookup"><span data-stu-id="e7b91-137">Add a TXT record to the publically registered DNS zone</span></span>

<span data-ttu-id="e7b91-138">Прежде чем Microsoft 365 начнет принимать трафик, направленный на публично зарегистрированное доменное имя, необходимо доказать, что вы владеете доменом и имеете права администратора.</span><span class="sxs-lookup"><span data-stu-id="e7b91-138">Before Microsoft 365 will start accepting traffic that is directed to the publicly registered domain name, you must prove that you own and have administrator permissions to the domain.</span></span> <span data-ttu-id="e7b91-139">Для этого нужно создать для домена запись типа TXT.</span><span class="sxs-lookup"><span data-stu-id="e7b91-139">You prove you own the domain by creating a TXT record in the domain.</span></span> <span data-ttu-id="e7b91-140">Такая запись не выполняет никаких действий в домене, и ее можно удалить, когда ваше владение доменом будет подтверждено.</span><span class="sxs-lookup"><span data-stu-id="e7b91-140">A TXT record doesn't do anything in your domain, and it can be deleted after your ownership of the domain is established.</span></span> <span data-ttu-id="e7b91-141">Чтобы создать записи TXT, выполните процедуры, которые необходимо выполнять при добавлении [записей DNS для подключения домена.](https://go.microsoft.com/fwlink/p/?LinkId=532542)</span><span class="sxs-lookup"><span data-stu-id="e7b91-141">To create the TXT records, follow the procedures at [Add DNS records to connect your domain](https://go.microsoft.com/fwlink/p/?LinkId=532542).</span></span> <span data-ttu-id="e7b91-142">Если эти действия вам не помогут, потребуется найти процедуры для своего регистратора DNS.</span><span class="sxs-lookup"><span data-stu-id="e7b91-142">If those procedures don't work for you , you need to find the procedures for your DNS registrar.</span></span>
  
<span data-ttu-id="e7b91-p111">Убедитесь, что запись TXT создана успешно, с помощью команды nslookup. Используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="e7b91-p111">Confirm the successful creation of the TXT record via nslookup. Follow this syntax.</span></span>
  
```console
nslookup -type=TXT <FQDN of registered domain>
```

<span data-ttu-id="e7b91-145">Выходные данные будут иметь следующий вид:</span><span class="sxs-lookup"><span data-stu-id="e7b91-145">This will give you output like:</span></span>
  
 `Non-authoritative answer:`
  
 `FQDN of the registered domain`
  
 `text=MS=ms########`
  
### <a name="validate-domain-ownership-in-microsoft-365"></a><span data-ttu-id="e7b91-146">Проверка владения доменом в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e7b91-146">Validate domain ownership in Microsoft 365</span></span>

<span data-ttu-id="e7b91-147">На последнем этапе вы проверяете в Microsoft 365, что вы владеете публично зарегистрированным доменом.</span><span class="sxs-lookup"><span data-stu-id="e7b91-147">In this last step, you validate to Microsoft 365 that you own the publically registered domain.</span></span> <span data-ttu-id="e7b91-148">После этого Шага Microsoft 365 начнет принимать трафик, на который будет перенаться новое доменное имя.</span><span class="sxs-lookup"><span data-stu-id="e7b91-148">After this step, Microsoft 365 will begin accepting traffic routed to the new domain name.</span></span> <span data-ttu-id="e7b91-149">Чтобы завершить процесс создания и регистрации домена, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e7b91-149">To complete the domain creation and registration process, run this command.</span></span> 
  
```powershell
Confirm-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="e7b91-150">Эта команда не возвращает выходных данных, поэтому для проверки выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="e7b91-150">This command won't return any output, so to confirm that this worked, run this command.</span></span>
  
```powershell
Get-MsolDomain -TenantId <customer TenantId> -DomainName <FQDN of new domain>
```

<span data-ttu-id="e7b91-151">Выходные данные имеют следующий вид:</span><span class="sxs-lookup"><span data-stu-id="e7b91-151">This will return something like this</span></span>

```console
Name                   Status      Authentication
--------------------   ---------   --------------
FQDN of new domain     Verified    Managed
```

   
## <a name="see-also"></a><span data-ttu-id="e7b91-152">См. также</span><span class="sxs-lookup"><span data-stu-id="e7b91-152">See also</span></span>

#### 

[<span data-ttu-id="e7b91-153">Справка для партнеров</span><span class="sxs-lookup"><span data-stu-id="e7b91-153">Help for partners</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=533477)

