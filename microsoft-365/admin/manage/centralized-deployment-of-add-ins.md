---
title: Определите, работает ли централизованное развертывание надстройок для вашей организации
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: b4527d49-4073-4b43-8274-31b7a3166f92
description: Определите, соответствуют ли требованиям клиент и пользователи, чтобы можно было использовать централизованное развертывание для развертывания Office надстройки.
ms.openlocfilehash: e5d3337cdf1bbb0dc18ee6940ab8bd289d2e5f65
ms.sourcegitcommit: b0d3abbccf4dd37e32d69664d3ebc9ab8dea760d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/21/2021
ms.locfileid: "52593925"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="5aab0-103">Определите, работает ли централизованное развертывание надстройок для вашей организации</span><span class="sxs-lookup"><span data-stu-id="5aab0-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="5aab0-104">Централизованное развертывание — это рекомендуемый и наиболее насыщенный функцией способ для большинства клиентов развертывать надстройки Office пользователям и группам в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="5aab0-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="5aab0-105">Если вы администратор, используйте это руководство, чтобы определить, соответствуют ли организации и пользователям требования, чтобы можно было использовать централизованное развертывание.</span><span class="sxs-lookup"><span data-stu-id="5aab0-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="5aab0-106">Централизованное развертывание обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="5aab0-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="5aab0-107">Глобальный администратор может назначить надстройки непосредственно пользователю, нескольким пользователям через группу или всем в организации.</span><span class="sxs-lookup"><span data-stu-id="5aab0-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="5aab0-108">Когда соответствующее приложение Office, надстройка автоматически загружается.</span><span class="sxs-lookup"><span data-stu-id="5aab0-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="5aab0-109">Если надстройка поддерживает команды надстройки, надстройка автоматически появляется в ленте в Office приложении.</span><span class="sxs-lookup"><span data-stu-id="5aab0-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="5aab0-110">Надстройки больше не отображаются для пользователей, если администратор отключит или удаляет надстройки, или если пользователь удален из Azure Active Directory или из группы, которую надстройка назначена.</span><span class="sxs-lookup"><span data-stu-id="5aab0-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="5aab0-111">Централизованное развертывание поддерживает три настольные платформы Windows, Mac и Online Office приложения.</span><span class="sxs-lookup"><span data-stu-id="5aab0-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="5aab0-112">Централизованное развертывание также поддерживает iOS и Android (Outlook только мобильные надстройки).</span><span class="sxs-lookup"><span data-stu-id="5aab0-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="5aab0-113">Для показа надстройки для клиента для всех пользователей может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="5aab0-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="5aab0-114">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="5aab0-114">Before you begin</span></span>

<span data-ttu-id="5aab0-115">Централизованное развертывание надстройок требует, чтобы пользователи использовали Microsoft 365 корпоративный skUs: E3/E5/F3 или бизнес-skUs: Business Basic, Business Standard, Business Premium (и подписывался в Office с помощью их организационного ID), а также Exchange Online и активных Exchange Online почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="5aab0-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="5aab0-116">Каталог подписки должен быть либо в каталоге, либо в федерате, чтобы Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="5aab0-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="5aab0-117">Вы можете просмотреть конкретные требования для Office и Exchange ниже или использовать централизованную проверку совместимости [развертывания.](#centralized-deployment-compatibility-checker)</span><span class="sxs-lookup"><span data-stu-id="5aab0-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="5aab0-118">Централизованное развертывание не поддерживает:</span><span class="sxs-lookup"><span data-stu-id="5aab0-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="5aab0-119">надстройки, ориентированные на Word, Excel или PowerPoint в Office 2013;</span><span class="sxs-lookup"><span data-stu-id="5aab0-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="5aab0-120">локальную службу каталогов;</span><span class="sxs-lookup"><span data-stu-id="5aab0-120">An on-premises directory service</span></span>
- <span data-ttu-id="5aab0-121">Развертывание надстройки в Exchange почтового ящика on-Prem</span><span class="sxs-lookup"><span data-stu-id="5aab0-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="5aab0-122">развертывание надстроек для SharePoint;</span><span class="sxs-lookup"><span data-stu-id="5aab0-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="5aab0-123">Teams приложения</span><span class="sxs-lookup"><span data-stu-id="5aab0-123">Teams apps</span></span>
- <span data-ttu-id="5aab0-124">Развертывание компонентной объектной модели (COM) или набор средств Visual Studio для Office (VSTO) надстройки.</span><span class="sxs-lookup"><span data-stu-id="5aab0-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="5aab0-125">Развертывание Microsoft 365, которые не включают Exchange Online, такие как SKUs: Приложения Microsoft 365 для бизнеса и Приложения Microsoft 365 для Enterprise.</span><span class="sxs-lookup"><span data-stu-id="5aab0-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="5aab0-126">Office Требования</span><span class="sxs-lookup"><span data-stu-id="5aab0-126">Office Requirements</span></span>

- <span data-ttu-id="5aab0-127">Для word, Excel и PowerPoint надстройки пользователи должны использовать одно из следующих:</span><span class="sxs-lookup"><span data-stu-id="5aab0-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="5aab0-128">На устройстве Windows версии 1704 или более поздней версии Microsoft 365 корпоративный skUs: E3/E5/F3 или бизнес-skUs: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="5aab0-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="5aab0-129">На Mac версии 15.34 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5aab0-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="5aab0-130">Для Outlook пользователи должны использовать один из следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="5aab0-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="5aab0-131">Версия 1701 или более поздний Microsoft 365 корпоративный skUs: E3/E5/F3 или бизнес-skUs: Business Basic, Business Standard, Business Premium.</span><span class="sxs-lookup"><span data-stu-id="5aab0-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="5aab0-132">Версия 1808 или более поздней версии Office профессиональный плюс 2019 или Office стандартный 2019.</span><span class="sxs-lookup"><span data-stu-id="5aab0-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="5aab0-133">Версия 16.0.4494.1000 или более поздней версии Office профессиональный плюс 2016 (MSI) или Office стандартный 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="5aab0-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="5aab0-134">Версия 15.0.4937.1000 или более поздней версии Office профессиональный плюс 2013 (MSI) или Office стандартный 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="5aab0-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="5aab0-135">Версия 16.0.9318.1000 или более поздней версии Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="5aab0-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="5aab0-136">Версия 2.75.0 или более поздней версии Outlook для iOS</span><span class="sxs-lookup"><span data-stu-id="5aab0-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="5aab0-137">Версия 2.2.145 или более поздней версии Outlook для Android</span><span class="sxs-lookup"><span data-stu-id="5aab0-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="5aab0-138">\*MSI-версии Outlook показывают надстройки, установленные администратором, в соответствующей ленте Outlook, а не в разделе "Мои надстройки".</span><span class="sxs-lookup"><span data-stu-id="5aab0-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="5aab0-139">Exchange Online требования</span><span class="sxs-lookup"><span data-stu-id="5aab0-139">Exchange Online requirements</span></span>

<span data-ttu-id="5aab0-140">Microsoft Exchange хранит манифесты надстройки в клиенте организации.</span><span class="sxs-lookup"><span data-stu-id="5aab0-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="5aab0-141">Администратор, развертывающий надстройки, и пользователи, получающие эти надстройки, должны быть в версии Exchange Online, которая поддерживает проверку подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="5aab0-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="5aab0-p106">Чтобы узнать, какая конфигурация используется, обратитесь к администратору Exchange своей организации. Подключение OAuth можно проверить для каждого пользователя с помощью командлета PowerShell [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity).</span><span class="sxs-lookup"><span data-stu-id="5aab0-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](/powershell/module/exchange/test-oauthconnectivity) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="5aab0-144">Централизованная проверка совместимости развертывания</span><span class="sxs-lookup"><span data-stu-id="5aab0-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="5aab0-145">С помощью централизованной проверки совместимости развертывания можно проверить, настроены ли пользователи клиента на использование централизованного развертывания для word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="5aab0-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="5aab0-146">Средство проверки совместимости не требуется для поддержки Outlook.</span><span class="sxs-lookup"><span data-stu-id="5aab0-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="5aab0-147">Скачайте средство проверки совместимости [здесь](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="5aab0-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="5aab0-148">Запуск проверки совместимости</span><span class="sxs-lookup"><span data-stu-id="5aab0-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="5aab0-149">Запустите окно с повышенным PowerShell.exe.</span><span class="sxs-lookup"><span data-stu-id="5aab0-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="5aab0-150">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="5aab0-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="5aab0-151">Запустите **команду Invoke-CompatabilityCheck:**</span><span class="sxs-lookup"><span data-stu-id="5aab0-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="5aab0-152">Эта команда подсказывает вам  *_tenantDomain_* (например, *TailspinToysIncorporated.onmicrosoft. </span> com)* и  *_учетные данные TenantAdmin_* (используйте глобальные учетные данные администратора), а затем запрашивает согласие.</span><span class="sxs-lookup"><span data-stu-id="5aab0-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="5aab0-153">В зависимости от количества пользователей в клиенте средство завершит проверку в течение нескольких минут или часов.</span><span class="sxs-lookup"><span data-stu-id="5aab0-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="5aab0-154">По завершении работы средство создаст выходной файл в формате с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="5aab0-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="5aab0-155">По умолчанию файл сохранен **в C:\windows\system32.**</span><span class="sxs-lookup"><span data-stu-id="5aab0-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="5aab0-156">Выходной файл содержит такие сведения:</span><span class="sxs-lookup"><span data-stu-id="5aab0-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="5aab0-157">имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="5aab0-157">User Name</span></span>
    
- <span data-ttu-id="5aab0-158">ИД пользователя (электронный адрес пользователя);</span><span class="sxs-lookup"><span data-stu-id="5aab0-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="5aab0-159">подтверждение готовности к централизованному развертыванию, если остальные пункты содержат нужные сведения;</span><span class="sxs-lookup"><span data-stu-id="5aab0-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="5aab0-160">Office плана — план Office лицензирован для</span><span class="sxs-lookup"><span data-stu-id="5aab0-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="5aab0-161">подтверждение активации Office, если пользователь активировал пакет Office;</span><span class="sxs-lookup"><span data-stu-id="5aab0-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="5aab0-162">сведения о том, что почтовый ящик поддерживается, если применяется почтовый ящик с поддержкой OAuth.</span><span class="sxs-lookup"><span data-stu-id="5aab0-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="5aab0-163">Многофакторная проверка подлинности не поддерживается при использовании модуля Central Deployment PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5aab0-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="5aab0-164">Назначения для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="5aab0-164">User and group assignments</span></span>

<span data-ttu-id="5aab0-165">В настоящее время функция централизованного развертывания поддерживает большинство групп, поддерживаемых Azure Active Directory, включая группы Microsoft 365, списки рассылки и группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="5aab0-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="5aab0-166">Сейчас группы безопасности без электронной почты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="5aab0-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="5aab0-167">Централизованное развертывание поддерживает назначения отдельным пользователям, группам и всем пользователям в клиенте.</span><span class="sxs-lookup"><span data-stu-id="5aab0-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="5aab0-168">Централизованное развертывание поддерживает пользователей в группах верхнего уровня или группах без родительских групп, но не пользователей в вложенных группах или группах с родительскими группами.</span><span class="sxs-lookup"><span data-stu-id="5aab0-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="5aab0-p110">Просмотрите пример ниже, в котором надстройка назначается Регине, Ольге и группе Sales Department. Так как группа West Coast Sales является вложенной, надстройка не назначается Николаю и Максиму.</span><span class="sxs-lookup"><span data-stu-id="5aab0-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Схема отдела продаж](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="5aab0-172">Проверка наличия вложенных групп в группе</span><span class="sxs-lookup"><span data-stu-id="5aab0-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="5aab0-173">Самый простой способ проверить, содержит ли группа вложенные группы,  посмотреть ее карточку контакта в Outlook.</span><span class="sxs-lookup"><span data-stu-id="5aab0-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="5aab0-174">Если вы введите имя группы в поле **To** электронной почты, а затем выберите имя группы, когда оно разрешится, оно покажет, содержит ли оно пользователей или вложенные группы.</span><span class="sxs-lookup"><span data-stu-id="5aab0-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="5aab0-175">В примере ниже на вкладке **Участники** карточки контакта Outlook видно, что в группе Test Group нет пользователей и есть две подгруппы.</span><span class="sxs-lookup"><span data-stu-id="5aab0-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Вкладка участников Outlook контактной карточки](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="5aab0-p112">Подключив группу, вы также можете выполнить обратную проверку и узнать, входит ли она в состав другой. В примере ниже на вкладке **Членство** карточки контакта Outlook видно, что группа Sub Group 1 входит в группу Test Group.</span><span class="sxs-lookup"><span data-stu-id="5aab0-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Вкладка членство Outlook контактной карточки](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="5aab0-p113">Кроме того, вы можете выполнять запросы и находить списки групп, входящих в состав определенной группы, с помощью API Graph Azure Active Directory. Дополнительные сведения см. в статье [Действия с группами | Справка по API Graph](/previous-versions/azure/ad/graph/api/groups-operations).</span><span class="sxs-lookup"><span data-stu-id="5aab0-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](/previous-versions/azure/ad/graph/api/groups-operations).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="5aab0-182">Обращение в службу поддержки Майкрософт</span><span class="sxs-lookup"><span data-stu-id="5aab0-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="5aab0-183">Если у вас или ваших пользователей возникают проблемы с загрузкой надстройки при использовании Office приложений для Интернета (Word, Excel и т.д.), которые были развернуты централизованно, вам может потребоваться обратиться в службу поддержки Майкрософт[(узнайте,](../../business-video/get-help-support.md)как).</span><span class="sxs-lookup"><span data-stu-id="5aab0-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../../business-video/get-help-support.md)).</span></span> <span data-ttu-id="5aab0-184">Укайте следующую информацию о Microsoft 365 среде в билете поддержки.</span><span class="sxs-lookup"><span data-stu-id="5aab0-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="5aab0-185">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="5aab0-185">**Platform**</span></span>|<span data-ttu-id="5aab0-186">**Данные отладки**</span><span class="sxs-lookup"><span data-stu-id="5aab0-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="5aab0-187">Office</span><span class="sxs-lookup"><span data-stu-id="5aab0-187">Office</span></span>  <br/> | <span data-ttu-id="5aab0-188">Журналы Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="5aab0-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="5aab0-189">Идентификатор клиента ( [инструкции по его определению](/onedrive/find-your-office-365-tenant-id.md))</span><span class="sxs-lookup"><span data-stu-id="5aab0-189">Tenant ID ( [learn how](/onedrive/find-your-office-365-tenant-id.md))</span></span>  <br/>  <span data-ttu-id="5aab0-190">CorrelationID.</span><span class="sxs-lookup"><span data-stu-id="5aab0-190">CorrelationID.</span></span> <span data-ttu-id="5aab0-191">Просмотреть источник одной из страниц office и найти значение Correlation ID и отправить его в поддержку:</span><span class="sxs-lookup"><span data-stu-id="5aab0-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="5aab0-192">Классические клиенты (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="5aab0-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="5aab0-193">Журналы Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="5aab0-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="5aab0-194">Сборка номеров клиентского приложения (желательно в качестве скриншота из **File/Account)**</span><span class="sxs-lookup"><span data-stu-id="5aab0-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |

## <a name="related-content"></a><span data-ttu-id="5aab0-195">См. также:</span><span class="sxs-lookup"><span data-stu-id="5aab0-195">Related content</span></span>

<span data-ttu-id="5aab0-196">[Развертывание надстройок в центре администрирования](../manage/manage-deployment-of-add-ins.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5aab0-196">[Deploy add-ins in the admin center](../manage/manage-deployment-of-add-ins.md) (article)</span></span>

<span data-ttu-id="5aab0-197">[Управление надстройки в центре администрирования](manage-addins-in-the-admin-center.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5aab0-197">[Manage add-ins in the admin center](manage-addins-in-the-admin-center.md) (article)</span></span>

<span data-ttu-id="5aab0-198">[Централизованный faQ развертывания](../manage/centralized-deployment-faq.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="5aab0-198">[Centralized Deployment FAQ](../manage/centralized-deployment-faq.md) (article)</span></span>

<span data-ttu-id="5aab0-199">[Обновление Microsoft 365 для бизнес-пользователей](../setup/upgrade-users-to-latest-office-client.md) до Office клиента (статья)</span><span class="sxs-lookup"><span data-stu-id="5aab0-199">[Upgrade your Microsoft 365 for business users to the latest Office client](../setup/upgrade-users-to-latest-office-client.md) (article)</span></span>
 