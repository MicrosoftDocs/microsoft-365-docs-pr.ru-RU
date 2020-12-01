---
title: Определение работы централизованного развертывания надстроек для вашей организации
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Определите, отвечает ли клиент и пользователи требованиям, чтобы можно было использовать централизованное развертывание для развертывания надстроек Office.
ms.openlocfilehash: 04c5f9090ca788f00f2d17d3af59e8022195e9be
ms.sourcegitcommit: d3ca8021f7da00a474ac14aac5f1358204a848f2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/01/2020
ms.locfileid: "49519369"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="daba5-103">Определение работы централизованного развертывания надстроек для вашей организации</span><span class="sxs-lookup"><span data-stu-id="daba5-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="daba5-104">Централизованное развертывание — это рекомендуемый и наиболее полнофункциональный способ развертывания надстроек Office для пользователей и групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="daba5-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="daba5-105">Если вы являетесь администратором, воспользуйтесь этим руководством, чтобы определить, отвечает ли ваша организация и пользователи требованиям, чтобы вы могли использовать централизованное развертывание.</span><span class="sxs-lookup"><span data-stu-id="daba5-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="daba5-106">Централизованное развертывание обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="daba5-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="daba5-107">Глобальный администратор может назначить надстройку непосредственно пользователю, нескольким пользователям через группу или ко всем пользователям в Организации.</span><span class="sxs-lookup"><span data-stu-id="daba5-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="daba5-108">При запуске соответствующего приложения Office надстройка автоматически загружается.</span><span class="sxs-lookup"><span data-stu-id="daba5-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="daba5-109">Если надстройка поддерживает команды надстроек, надстройка автоматически появляется на ленте в приложении Office.</span><span class="sxs-lookup"><span data-stu-id="daba5-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="daba5-110">Надстройки больше не отображаются для пользователей, если администратор отключает или удаляет надстройку, или если пользователь удален из Azure Active Directory или из группы, которой назначена эта надстройка.</span><span class="sxs-lookup"><span data-stu-id="daba5-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="daba5-111">Централизованное развертывание поддерживает три системные платформы Windows, Mac и приложения Office в Интернете.</span><span class="sxs-lookup"><span data-stu-id="daba5-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="daba5-112">Централизованное развертывание также поддерживает iOS и Android (только надстройки Outlook Mobile).</span><span class="sxs-lookup"><span data-stu-id="daba5-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="daba5-113">Чтобы надстройка отображалась для всех пользователей, она может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="daba5-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="daba5-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="daba5-114">Requirements</span></span>

<span data-ttu-id="daba5-115">Для централизованного развертывания надстроек необходимо, чтобы пользователи применялись к Microsoft 365 Enterprise SKU: E3/F3/F3 или Business SKU: Business Basic, Business Standard, Business Premium (и вошли в Office с помощью своего идентификатора организации) и имеют почтовые ящики Exchange Online и Active Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="daba5-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="daba5-116">Ваш каталог подписки должен быть либо либо в, либо в Федеративной для Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="daba5-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="daba5-117">Вы можете просмотреть определенные требования для Office и Exchange ниже или использовать [средство проверки совместимости централизованного развертывания](#centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="daba5-117">You can view specific requirements for Office and Exchange below, or use the [Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="daba5-118">Централизованное развертывание не поддерживает:</span><span class="sxs-lookup"><span data-stu-id="daba5-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="daba5-119">надстройки, ориентированные на Word, Excel или PowerPoint в Office 2013;</span><span class="sxs-lookup"><span data-stu-id="daba5-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="daba5-120">локальную службу каталогов;</span><span class="sxs-lookup"><span data-stu-id="daba5-120">An on-premises directory service</span></span>
- <span data-ttu-id="daba5-121">Развертывание надстроек в локальный почтовый ящик Exchange</span><span class="sxs-lookup"><span data-stu-id="daba5-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="daba5-122">развертывание надстроек для SharePoint;</span><span class="sxs-lookup"><span data-stu-id="daba5-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="daba5-123">Приложения Teams</span><span class="sxs-lookup"><span data-stu-id="daba5-123">Teams apps</span></span>
- <span data-ttu-id="daba5-124">Развертывание надстроек модели компонентных объектов (COM) или Visual Studio Tools для Office (VSTO).</span><span class="sxs-lookup"><span data-stu-id="daba5-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins.</span></span>
- <span data-ttu-id="daba5-125">В число развертываний Microsoft 365, которые не включают Exchange Online, такие как SKU: Microsoft 365 приложения для бизнеса и приложения Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="daba5-125">Deployments of Microsoft 365 that do not include Exchange Online such as SKUs: Microsoft 365 Apps for Business and Microsoft 365 Apps for Enterprise.</span></span>

### <a name="office-requirements"></a><span data-ttu-id="daba5-126">Требования к Office</span><span class="sxs-lookup"><span data-stu-id="daba5-126">Office Requirements</span></span>

- <span data-ttu-id="daba5-127">Для надстроек Word, Excel и PowerPoint пользователям необходимо использовать один из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="daba5-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="daba5-128">На устройстве с Windows версии 1704 или более поздней версии для Microsoft 365 Enterprise SKU: E3/F3/F3 или Business SKU: бизнес-базовый, Бизнес-стандарт, бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="daba5-128">On a Windows device, Version 1704 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="daba5-129">На компьютере Mac версии 15,34 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="daba5-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="daba5-130">Для работы с Outlook пользователи должны использовать один из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="daba5-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="daba5-131">Версия 1701 или более поздняя версия корпорации Майкрософт 365 корпоративный SKU: E3/F3/F3 или предприятие: бизнес-базовые, Бизнес-стандарты, бизнес премиум.</span><span class="sxs-lookup"><span data-stu-id="daba5-131">Version 1701 or later of Microsoft 365 Enterprise SKUs: E3/E5/F3 or Business SKUs: Business Basic, Business Standard, Business Premium.</span></span>
  - <span data-ttu-id="daba5-132">Версия 1808 или более поздняя версия Office профессиональный плюс 2019 или Office Стандартный 2019.</span><span class="sxs-lookup"><span data-stu-id="daba5-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="daba5-133">Версия 16.0.4494.1000 или более поздняя версия Office профессиональный плюс 2016 (MSI) или Office Стандартный 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="daba5-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="daba5-134">Версия 15.0.4937.1000 или более поздняя версия Office профессиональный плюс 2013 (MSI) или Office Стандартный 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="daba5-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="daba5-135">Версия 16.0.9318.1000 или более поздняя версия Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="daba5-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="daba5-136">Версия 2.75.0 или более поздняя версия Outlook Mobile для iOS</span><span class="sxs-lookup"><span data-stu-id="daba5-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="daba5-137">Версия 2.2.145 или более поздняя версия Outlook Mobile для Android</span><span class="sxs-lookup"><span data-stu-id="daba5-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="daba5-138">\* MSI для Outlook. в соответствующей ленте Outlook отображаются надстройки, установленные администратором, а не раздел "Мои надстройки".</span><span class="sxs-lookup"><span data-stu-id="daba5-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>

### <a name="exchange-online-requirements"></a><span data-ttu-id="daba5-139">Требования Exchange Online</span><span class="sxs-lookup"><span data-stu-id="daba5-139">Exchange Online requirements</span></span>

<span data-ttu-id="daba5-140">Microsoft Exchange хранит манифесты надстроек в клиенте Организации.</span><span class="sxs-lookup"><span data-stu-id="daba5-140">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="daba5-141">Надстройки, развернутые администратором, и пользователи, получающие надстройку, должны находиться в версии Exchange Online, поддерживающей проверку подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="daba5-141">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="daba5-p106">Чтобы узнать, какая конфигурация используется, обратитесь к администратору Exchange своей организации. Подключение OAuth можно проверить для каждого пользователя с помощью командлета PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="daba5-p106">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="daba5-144">Средство проверки совместимости централизованного развертывания</span><span class="sxs-lookup"><span data-stu-id="daba5-144">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="daba5-145">С помощью средства проверки совместимости централизованного развертывания можно проверить, настроены ли пользователи клиента для использования централизованного развертывания для Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="daba5-145">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="daba5-146">Средство проверки совместимости не требуется для поддержки Outlook.</span><span class="sxs-lookup"><span data-stu-id="daba5-146">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="daba5-147">Скачайте средство проверки совместимости [здесь](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="daba5-147">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="daba5-148">Запуск средства проверки совместимости</span><span class="sxs-lookup"><span data-stu-id="daba5-148">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="daba5-149">Запустите окно PowerShell.exe с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="daba5-149">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="daba5-150">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="daba5-150">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="daba5-151">Выполните команду **Invoke – компатабилитичекк** :</span><span class="sxs-lookup"><span data-stu-id="daba5-151">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="daba5-152">Эта команда запрашивает  *_тенантдомаин_* (например, *таилспинтойсинкорпоратед. onmicrosoft). </span> com*) и учетные данные  *_TenantAdmin_* (Используйте свои учетные данные глобального администратора), а затем запрашивает согласие.</span><span class="sxs-lookup"><span data-stu-id="daba5-152">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="daba5-153">В зависимости от количества пользователей в клиенте средство завершит проверку в течение нескольких минут или часов.</span><span class="sxs-lookup"><span data-stu-id="daba5-153">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="daba5-154">По завершении работы средство создаст выходной файл в формате с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="daba5-154">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="daba5-155">По умолчанию файл сохраняется в **C:\Windows\System32** .</span><span class="sxs-lookup"><span data-stu-id="daba5-155">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="daba5-156">Выходной файл содержит такие сведения:</span><span class="sxs-lookup"><span data-stu-id="daba5-156">The output file contains the following information:</span></span>
  
- <span data-ttu-id="daba5-157">имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="daba5-157">User Name</span></span>
    
- <span data-ttu-id="daba5-158">ИД пользователя (электронный адрес пользователя);</span><span class="sxs-lookup"><span data-stu-id="daba5-158">User ID (User's email address)</span></span>
    
- <span data-ttu-id="daba5-159">подтверждение готовности к централизованному развертыванию, если остальные пункты содержат нужные сведения;</span><span class="sxs-lookup"><span data-stu-id="daba5-159">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="daba5-160">План Office — это план Office, для которого у них есть лицензия</span><span class="sxs-lookup"><span data-stu-id="daba5-160">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="daba5-161">подтверждение активации Office, если пользователь активировал пакет Office;</span><span class="sxs-lookup"><span data-stu-id="daba5-161">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="daba5-162">сведения о том, что почтовый ящик поддерживается, если применяется почтовый ящик с поддержкой OAuth.</span><span class="sxs-lookup"><span data-stu-id="daba5-162">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>

> [!NOTE]
> <span data-ttu-id="daba5-163">Многофакторная проверка подлинности не поддерживается при использовании модуля центрального развертывания PowerShell.</span><span class="sxs-lookup"><span data-stu-id="daba5-163">Multifactor authentication is not supported when using the Central Deployment PowerShell module.</span></span>
  
## <a name="user-and-group-assignments"></a><span data-ttu-id="daba5-164">Назначения для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="daba5-164">User and group assignments</span></span>

<span data-ttu-id="daba5-165">В настоящее время функция централизованного развертывания поддерживает большинство групп, поддерживаемых Azure Active Directory, включая группы Microsoft 365, списки рассылки и группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="daba5-165">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="daba5-166">Сейчас группы безопасности без электронной почты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="daba5-166">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="daba5-167">Централизованное развертывание поддерживает назначения для отдельных пользователей, групп и всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="daba5-167">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="daba5-168">Централизованное развертывание поддерживает пользователей в группах или группах верхнего уровня без родительских групп, но не пользователей в вложенных группах или группах с родительскими группами.</span><span class="sxs-lookup"><span data-stu-id="daba5-168">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="daba5-p110">Просмотрите пример ниже, в котором надстройка назначается Регине, Ольге и группе Sales Department. Так как группа West Coast Sales является вложенной, надстройка не назначается Николаю и Максиму.</span><span class="sxs-lookup"><span data-stu-id="daba5-p110">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Схема отдела продаж](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="daba5-172">Проверка наличия вложенных групп в группе</span><span class="sxs-lookup"><span data-stu-id="daba5-172">Find out if a group contains nested groups</span></span>

<span data-ttu-id="daba5-173">Самый простой способ проверить, содержит ли группа вложенные группы,  посмотреть ее карточку контакта в Outlook.</span><span class="sxs-lookup"><span data-stu-id="daba5-173">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="daba5-174">Если ввести имя группы в поле " **Кому** " электронного письма, а затем выбрать имя группы при разрешении, оно покажет, содержит ли она пользователей или вложенные группы.</span><span class="sxs-lookup"><span data-stu-id="daba5-174">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="daba5-175">В примере ниже на вкладке **Участники** карточки контакта Outlook видно, что в группе Test Group нет пользователей и есть две подгруппы.</span><span class="sxs-lookup"><span data-stu-id="daba5-175">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Вкладка "участники" карточки контакта Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="daba5-p112">Подключив группу, вы также можете выполнить обратную проверку и узнать, входит ли она в состав другой. В примере ниже на вкладке **Членство** карточки контакта Outlook видно, что группа Sub Group 1 входит в группу Test Group.</span><span class="sxs-lookup"><span data-stu-id="daba5-p112">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Вкладка "членство" карточки контакта Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="daba5-p113">Кроме того, вы можете выполнять запросы и находить списки групп, входящих в состав определенной группы, с помощью API Graph Azure Active Directory. Дополнительные сведения см. в статье [Действия с группами | Справка по API Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="daba5-p113">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="daba5-182">Обращение в службу поддержки Майкрософт</span><span class="sxs-lookup"><span data-stu-id="daba5-182">Contacting Microsoft for support</span></span>

<span data-ttu-id="daba5-183">Если вы или ваши пользователи столкнулись с проблемами при загрузке надстройки при использовании приложений Office для Интернета (Word, Excel и т. д.), которые были централизованно развернуты, вам может потребоваться обратиться в службу поддержки Майкрософт ([Узнайте, как](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="daba5-183">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="daba5-184">Предоставьте следующие сведения о среде Microsoft 365 в билете поддержки.</span><span class="sxs-lookup"><span data-stu-id="daba5-184">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="daba5-185">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="daba5-185">**Platform**</span></span>|<span data-ttu-id="daba5-186">**Данные отладки**</span><span class="sxs-lookup"><span data-stu-id="daba5-186">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="daba5-187">Office</span><span class="sxs-lookup"><span data-stu-id="daba5-187">Office</span></span>  <br/> | <span data-ttu-id="daba5-188">Журналы Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="daba5-188">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="daba5-189">Идентификатор клиента ( [инструкции по его определению](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="daba5-189">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="daba5-190">ИД.</span><span class="sxs-lookup"><span data-stu-id="daba5-190">CorrelationID.</span></span> <span data-ttu-id="daba5-191">Просмотрите источник одной из страниц Office и найдите значение идентификатора корреляции и отправьте его в службу поддержки:</span><span class="sxs-lookup"><span data-stu-id="daba5-191">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="daba5-192">Классические клиенты (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="daba5-192">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="daba5-193">Журналы Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="daba5-193">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="daba5-194">Номера сборок клиентского приложения (желательно в виде снимка экрана из **файла или учетной записи**)</span><span class="sxs-lookup"><span data-stu-id="daba5-194">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   
