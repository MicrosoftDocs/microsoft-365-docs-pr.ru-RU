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
ms.openlocfilehash: 4bd81dcf1d1ee6221a3519baac0a3b1bc63b791f
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131738"
---
# <a name="determine-if-centralized-deployment-of-add-ins-works-for-your-organization"></a><span data-ttu-id="68b1a-103">Определение работы централизованного развертывания надстроек для вашей организации</span><span class="sxs-lookup"><span data-stu-id="68b1a-103">Determine if Centralized Deployment of add-ins works for your organization</span></span>

<span data-ttu-id="68b1a-104">Централизованное развертывание — это рекомендуемый и наиболее полнофункциональный способ развертывания надстроек Office для пользователей и групп в Организации.</span><span class="sxs-lookup"><span data-stu-id="68b1a-104">Centralized Deployment is the recommended and most feature-rich way for most customers to deploy Office add-ins to users and groups within your organization.</span></span> <span data-ttu-id="68b1a-105">Если вы являетесь администратором, воспользуйтесь этим руководством, чтобы определить, отвечает ли ваша организация и пользователи требованиям, чтобы вы могли использовать централизованное развертывание.</span><span class="sxs-lookup"><span data-stu-id="68b1a-105">If you're an admin, use this guidance to determine if your organization and users meet the requirements so that you can use Centralized Deployment.</span></span>

<span data-ttu-id="68b1a-106">Централизованное развертывание обеспечивает следующие преимущества:</span><span class="sxs-lookup"><span data-stu-id="68b1a-106">Centralized Deployment provides the following benefits:</span></span>
  
- <span data-ttu-id="68b1a-107">Глобальный администратор может назначить надстройку непосредственно пользователю, нескольким пользователям через группу или ко всем пользователям в Организации.</span><span class="sxs-lookup"><span data-stu-id="68b1a-107">A Global admin can assign an add-in directly to a user, to multiple users via a group, or to everyone in the organization.</span></span>
    
- <span data-ttu-id="68b1a-108">При запуске соответствующего приложения Office надстройка автоматически загружается.</span><span class="sxs-lookup"><span data-stu-id="68b1a-108">When the relevant Office application starts, the add-in automatically downloads.</span></span> <span data-ttu-id="68b1a-109">Если надстройка поддерживает команды надстроек, надстройка автоматически появляется на ленте в приложении Office.</span><span class="sxs-lookup"><span data-stu-id="68b1a-109">If the add-in supports add-in commands, the add-in automatically appears in the ribbon within the Office application.</span></span>
    
- <span data-ttu-id="68b1a-110">Надстройки больше не отображаются для пользователей, если администратор отключает или удаляет надстройку, или если пользователь удален из Azure Active Directory или из группы, которой назначена эта надстройка.</span><span class="sxs-lookup"><span data-stu-id="68b1a-110">Add-ins no longer appear for users if the admin turns off or deletes the add-in, or if the user is removed from Azure Active Directory or from a group that the add-in is assigned to.</span></span>

<span data-ttu-id="68b1a-111">Централизованное развертывание поддерживает три системные платформы Windows, Mac и приложения Office в Интернете.</span><span class="sxs-lookup"><span data-stu-id="68b1a-111">Centralized Deployment supports three desktop platforms Windows, Mac and Online Office apps.</span></span> <span data-ttu-id="68b1a-112">Централизованное развертывание также поддерживает iOS и Android (только надстройки Outlook Mobile).</span><span class="sxs-lookup"><span data-stu-id="68b1a-112">Centralized Deployment also supports iOS and Android (Outlook Mobile Add-ins Only).</span></span>

<span data-ttu-id="68b1a-113">Чтобы надстройка отображалась для всех пользователей, она может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="68b1a-113">It can take up to 24 hours for an add-in to show up for client for all users.</span></span>
  
## <a name="requirements"></a><span data-ttu-id="68b1a-114">Requirements</span><span class="sxs-lookup"><span data-stu-id="68b1a-114">Requirements</span></span>

<span data-ttu-id="68b1a-115">Для централизованного развертывания надстроек необходимо, чтобы пользователи использовали приложения Microsoft 365 для предприятий (и вошли в Office с помощью своего идентификатора организации), а также почтовые ящики Exchange Online и Active Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="68b1a-115">Centralized deployment of add-ins requires that the users are using Microsoft 365 Apps for enterprise (and are signed into Office using their organizational ID), and have Exchange Online and active Exchange Online mailboxes.</span></span> <span data-ttu-id="68b1a-116">Ваш каталог подписки должен быть либо либо в, либо в Федеративной для Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="68b1a-116">Your subscription directory must either be in, or federated to Azure Active Directory.</span></span>
<span data-ttu-id="68b1a-117">Вы можете просмотреть определенные требования для Office и Exchange ниже или использовать[средство проверки совместимости централизованного развертывания](#centralized-deployment-compatibility-checker).</span><span class="sxs-lookup"><span data-stu-id="68b1a-117">You can view specific requirements for Office and Exchange below, or use the[Centralized Deployment Compatibility Checker](#centralized-deployment-compatibility-checker).</span></span>

<span data-ttu-id="68b1a-118">Централизованное развертывание не поддерживает:</span><span class="sxs-lookup"><span data-stu-id="68b1a-118">Centralized Deployment doesn't support the following:</span></span>
  
- <span data-ttu-id="68b1a-119">надстройки, ориентированные на Word, Excel или PowerPoint в Office 2013;</span><span class="sxs-lookup"><span data-stu-id="68b1a-119">Add-ins that target Word, Excel, or PowerPoint in Office 2013</span></span> 
- <span data-ttu-id="68b1a-120">локальную службу каталогов;</span><span class="sxs-lookup"><span data-stu-id="68b1a-120">An on-premises directory service</span></span>
- <span data-ttu-id="68b1a-121">Развертывание надстроек в локальный почтовый ящик Exchange</span><span class="sxs-lookup"><span data-stu-id="68b1a-121">Add-in Deployment to an Exchange On-Prem Mailbox</span></span>
- <span data-ttu-id="68b1a-122">развертывание надстроек для SharePoint;</span><span class="sxs-lookup"><span data-stu-id="68b1a-122">Add-in deployment to SharePoint</span></span>  
- <span data-ttu-id="68b1a-123">Приложения Teams</span><span class="sxs-lookup"><span data-stu-id="68b1a-123">Teams apps</span></span>
- <span data-ttu-id="68b1a-124">развертывание надстроек для модели COM или набора средств Visual Studio для системы Office (VSTO).</span><span class="sxs-lookup"><span data-stu-id="68b1a-124">Deployment of Component Object Model (COM) or Visual Studio Tools for Office (VSTO) add-ins</span></span>
- <span data-ttu-id="68b1a-125">Развертывания Microsoft 365, которые не включают Exchange, такие как приложения Microsoft 365 для бизнеса</span><span class="sxs-lookup"><span data-stu-id="68b1a-125">Deployments of Microsoft 365 that do not include Exchange such as Microsoft 365 Apps for business</span></span>

### <a name="office-requirements"></a><span data-ttu-id="68b1a-126">Требования к Office</span><span class="sxs-lookup"><span data-stu-id="68b1a-126">Office Requirements</span></span>

- <span data-ttu-id="68b1a-127">Для надстроек Word, Excel и PowerPoint пользователям необходимо использовать один из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="68b1a-127">For Word, Excel, and PowerPoint add-ins, your users must be using one of the following:</span></span>
  - <span data-ttu-id="68b1a-128">На устройстве с Windows версии 1704 или более поздней версии для корпоративных приложений Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68b1a-128">On a Windows device, Version 1704 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="68b1a-129">На компьютере Mac версии 15,34 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="68b1a-129">On a Mac, Version 15.34 or later.</span></span>

- <span data-ttu-id="68b1a-130">Для работы с Outlook пользователи должны использовать один из следующих компонентов:</span><span class="sxs-lookup"><span data-stu-id="68b1a-130">For Outlook, your users must be using one of the following:</span></span> 
  - <span data-ttu-id="68b1a-131">Версия 1701 или более поздняя версия приложений Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="68b1a-131">Version 1701 or later of Microsoft 365 Apps for enterprise.</span></span>
  - <span data-ttu-id="68b1a-132">Версия 1808 или более поздняя версия Office профессиональный плюс 2019 или Office Стандартный 2019.</span><span class="sxs-lookup"><span data-stu-id="68b1a-132">Version 1808 or later of Office Professional Plus 2019 or Office Standard 2019.</span></span>
  - <span data-ttu-id="68b1a-133">Версия 16.0.4494.1000 или более поздняя версия Office профессиональный плюс 2016 (MSI) или Office Стандартный 2016 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="68b1a-133">Version 16.0.4494.1000 or later of Office Professional Plus 2016 (MSI) or Office Standard 2016 (MSI)\*</span></span>
  - <span data-ttu-id="68b1a-134">Версия 15.0.4937.1000 или более поздняя версия Office профессиональный плюс 2013 (MSI) или Office Стандартный 2013 (MSI)\*</span><span class="sxs-lookup"><span data-stu-id="68b1a-134">Version 15.0.4937.1000 or later of Office Professional Plus 2013 (MSI) or Office Standard 2013 (MSI)\*</span></span>
  - <span data-ttu-id="68b1a-135">Версия 16.0.9318.1000 или более поздняя версия Office 2016 для Mac</span><span class="sxs-lookup"><span data-stu-id="68b1a-135">Version 16.0.9318.1000 or later of Office 2016 for Mac</span></span> 
- <span data-ttu-id="68b1a-136">Версия 2.75.0 или более поздняя версия Outlook Mobile для iOS</span><span class="sxs-lookup"><span data-stu-id="68b1a-136">Version 2.75.0 or later of Outlook mobile for iOS</span></span> 
- <span data-ttu-id="68b1a-137">Версия 2.2.145 или более поздняя версия Outlook Mobile для Android</span><span class="sxs-lookup"><span data-stu-id="68b1a-137">Version 2.2.145 or later of Outlook mobile for Android</span></span> 
    
    <span data-ttu-id="68b1a-138">\* MSI для Outlook. в соответствующей ленте Outlook отображаются надстройки, установленные администратором, а не раздел "Мои надстройки".</span><span class="sxs-lookup"><span data-stu-id="68b1a-138">\*MSI versions of Outlook show admin-installed add-ins in the appropriate Outlook ribbon, not the "My add-ins" section.</span></span>
    

#### <a name="find-out-if-microsoft-365-apps-for-enterprise-is-installed"></a><span data-ttu-id="68b1a-139">Как узнать, установлены ли приложения Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="68b1a-139">Find out if Microsoft 365 Apps for enterprise is installed</span></span>

<span data-ttu-id="68b1a-140">Чтобы использовать приложения Microsoft 365 для предприятий, пользователю должна быть предоставлена учетная запись Microsoft 365 и должна быть назначена лицензия.</span><span class="sxs-lookup"><span data-stu-id="68b1a-140">To use Microsoft 365 Apps for enterprise, a user must have an Microsoft 365 account and must have been assigned a license.</span></span> <span data-ttu-id="68b1a-141">Более подробную информацию можно найти в [статье Обзор приложений Microsoft 365 для предприятий](https://go.microsoft.com/fwlink/p/?linkid=846328).</span><span class="sxs-lookup"><span data-stu-id="68b1a-141">For more information, see [Overview of Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846328).</span></span>

<span data-ttu-id="68b1a-142">Самый простой способ определить, имеет ли пользователь приложение Microsoft 365 для Enterprise установлено и недавно использовал его, — использовать отчет об активации Microsoft Office, который доступен в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="68b1a-142">The simplest way to detect if a user has Microsoft 365 Apps for enterprise installed and has been using it recently is to use the Microsoft Office Activations report, which is available in the Microsoft 365 admin center.</span></span> <span data-ttu-id="68b1a-143">В отчете представлен список всех пользователей, которые активировали приложения Microsoft 365 для предприятий в течение последних 7 дней, 30 дней, 90 дней или 180 дней.</span><span class="sxs-lookup"><span data-stu-id="68b1a-143">The report provides a list of all users who have activated Microsoft 365 Apps for enterprise within the last 7 days, 30 days, 90 days, or 180 days.</span></span> <span data-ttu-id="68b1a-144">В целях централизованного развертывания активации настольных систем для Windows или Mac являются важными столбцами отчета.</span><span class="sxs-lookup"><span data-stu-id="68b1a-144">For centralized deployment purposes, the desktop activations for Windows or Mac are the important columns in the report.</span></span> <span data-ttu-id="68b1a-145">Вы можете экспортировать отчет в Excel.</span><span class="sxs-lookup"><span data-stu-id="68b1a-145">You can export the report to Excel.</span></span> <span data-ttu-id="68b1a-146">Более подробную информацию об отчете можно узнать [в статье Microsoft 365 Reports в центре администрирования — активации Microsoft Office](../activity-reports/microsoft-office-activations.md).</span><span class="sxs-lookup"><span data-stu-id="68b1a-146">For more information about the report, see [Microsoft 365 Reports in the Admin Center - Microsoft Office activations](../activity-reports/microsoft-office-activations.md).</span></span>
  
<span data-ttu-id="68b1a-147">Если вы не хотите использовать отчет об активации, можно попросить пользователя открыть приложение Office, например Word, на своем компьютере, а затем выбрать пункт **File** \> **учетная запись**файла.</span><span class="sxs-lookup"><span data-stu-id="68b1a-147">If you don't want to use the Activations report, you can ask a user to open an Office application such as Word on their machine, and then choose **File** \> **Account**.</span></span> <span data-ttu-id="68b1a-148">В разделе **сведения о продукте**вы должны увидеть **продукт подписки** и **Microsoft 365 для предприятий**или Microsoft 365 бизнес премиум, как показано на следующем рисунке.</span><span class="sxs-lookup"><span data-stu-id="68b1a-148">Under **Product Information**, you should see **Subscription Product** and **Microsoft 365 for enterprise**,or Microsoft 365 Business Premium, similar to what is shown in the following image.</span></span>

![Сведения о продукте в приложении Office](../../media/product-information-microsoft-365-enterprise.png)
  
<span data-ttu-id="68b1a-150">Для получения справки о приложениях Microsoft 365 для предприятий ознакомьтесь с [советами по устранению неполадок приложений microsoft 365 для предприятий](https://go.microsoft.com/fwlink/p/?linkid=846339).</span><span class="sxs-lookup"><span data-stu-id="68b1a-150">For help with Microsoft 365 Apps for enterprise, see [Troubleshooting tips for Microsoft 365 Apps for enterprise](https://go.microsoft.com/fwlink/p/?linkid=846339).</span></span>


### <a name="exchange-online-requirements"></a><span data-ttu-id="68b1a-151">Требования Exchange Online</span><span class="sxs-lookup"><span data-stu-id="68b1a-151">Exchange Online requirements</span></span>

<span data-ttu-id="68b1a-152">Microsoft Exchange хранит манифесты надстроек в клиенте Организации.</span><span class="sxs-lookup"><span data-stu-id="68b1a-152">Microsoft Exchange stores the add-in manifests within your organization's tenant.</span></span> <span data-ttu-id="68b1a-153">Надстройки, развернутые администратором, и пользователи, получающие надстройку, должны находиться в версии Exchange Online, поддерживающей проверку подлинности OAuth.</span><span class="sxs-lookup"><span data-stu-id="68b1a-153">The admin deploying add-ins and the users receiving those add-ins must be on a version of Exchange Online that supports OAuth authentication.</span></span>
  
<span data-ttu-id="68b1a-p109">Чтобы узнать, какая конфигурация используется, обратитесь к администратору Exchange своей организации. Подключение OAuth можно проверить для каждого пользователя с помощью командлета PowerShell [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351).</span><span class="sxs-lookup"><span data-stu-id="68b1a-p109">Check with your organization's Exchange admin to find out which configuration is in use. OAuth connectivity per user can be verified by using the [Test-OAuthConnectivity](https://go.microsoft.com/fwlink/p/?linkid=846351) PowerShell cmdlet.</span></span> 


### <a name="centralized-deployment-compatibility-checker"></a><span data-ttu-id="68b1a-156">Средство проверки совместимости централизованного развертывания</span><span class="sxs-lookup"><span data-stu-id="68b1a-156">Centralized Deployment Compatibility Checker</span></span>

<span data-ttu-id="68b1a-157">С помощью средства проверки совместимости централизованного развертывания можно проверить, настроены ли пользователи клиента для использования централизованного развертывания для Word, Excel и PowerPoint.</span><span class="sxs-lookup"><span data-stu-id="68b1a-157">Using the Centralized Deployment Compatibility Checker, you can verify whether the users on your tenant are set up to use Centralized Deployment for Word, Excel and PowerPoint.</span></span> <span data-ttu-id="68b1a-158">Средство проверки совместимости не требуется для поддержки Outlook.</span><span class="sxs-lookup"><span data-stu-id="68b1a-158">The Compatibility Checker is not required for Outlook support.</span></span> <span data-ttu-id="68b1a-159">Скачайте средство проверки совместимости [здесь](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span><span class="sxs-lookup"><span data-stu-id="68b1a-159">Download the compatibility checker [here](https://aka.ms/officeaddindeploymentorgcompatibilitychecker).</span></span>
  
#### <a name="run-the-compatibility-checker"></a><span data-ttu-id="68b1a-160">Запуск средства проверки совместимости</span><span class="sxs-lookup"><span data-stu-id="68b1a-160">Run the compatibility checker</span></span>
  
1. <span data-ttu-id="68b1a-161">Запустите окно PowerShell.exe с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="68b1a-161">Start an elevated PowerShell.exe window.</span></span>
    
2. <span data-ttu-id="68b1a-162">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="68b1a-162">Run the following command:</span></span>

   ```powershell
   Import-Module O365CompatibilityChecker
   ```
    
3. <span data-ttu-id="68b1a-163">Выполните команду **Invoke – компатабилитичекк** :</span><span class="sxs-lookup"><span data-stu-id="68b1a-163">Run the **Invoke-CompatabilityCheck** command:</span></span>

   ```powershell
   Invoke-CompatibilityCheck
   ```
   <span data-ttu-id="68b1a-164">Эта команда запрашивает  *_тенантдомаин_* (например, *таилспинтойсинкорпоратед. onmicrosoft). </span> com*) и учетные данные  *_TenantAdmin_* (Используйте свои учетные данные глобального администратора), а затем запрашивает согласие.</span><span class="sxs-lookup"><span data-stu-id="68b1a-164">This command prompts you for  *_TenantDomain_* (for example, *TailspinToysIncorporated.onmicrosoft.</span>com*) and  *_TenantAdmin_* credentials (use your global admin credentials), and then requests consent.</span></span>
    
   > [!NOTE]
   > <span data-ttu-id="68b1a-165">В зависимости от количества пользователей в клиенте средство завершит проверку в течение нескольких минут или часов.</span><span class="sxs-lookup"><span data-stu-id="68b1a-165">Depending on the number of users in your tenant, the checker could complete in minutes or hours.</span></span> 
  
<span data-ttu-id="68b1a-166">По завершении работы средство создаст выходной файл в формате с разделителями-запятыми (CSV).</span><span class="sxs-lookup"><span data-stu-id="68b1a-166">When the tool finishes running, it produces an output file in comma-separated (.csv) format.</span></span> <span data-ttu-id="68b1a-167">По умолчанию файл сохраняется в **C:\Windows\System32** .</span><span class="sxs-lookup"><span data-stu-id="68b1a-167">The file is saved to **C:\windows\system32** by default.</span></span> <span data-ttu-id="68b1a-168">Выходной файл содержит такие сведения:</span><span class="sxs-lookup"><span data-stu-id="68b1a-168">The output file contains the following information:</span></span>
  
- <span data-ttu-id="68b1a-169">имя пользователя;</span><span class="sxs-lookup"><span data-stu-id="68b1a-169">User Name</span></span>
    
- <span data-ttu-id="68b1a-170">ИД пользователя (электронный адрес пользователя);</span><span class="sxs-lookup"><span data-stu-id="68b1a-170">User ID (User's email address)</span></span>
    
- <span data-ttu-id="68b1a-171">подтверждение готовности к централизованному развертыванию, если остальные пункты содержат нужные сведения;</span><span class="sxs-lookup"><span data-stu-id="68b1a-171">Centralized Deployment ready - If the remaining items are true</span></span>
    
- <span data-ttu-id="68b1a-172">План Office — это план Office, для которого у них есть лицензия</span><span class="sxs-lookup"><span data-stu-id="68b1a-172">Office plan - The plan of Office they are licensed for</span></span>
    
- <span data-ttu-id="68b1a-173">подтверждение активации Office, если пользователь активировал пакет Office;</span><span class="sxs-lookup"><span data-stu-id="68b1a-173">Office Activated - If they have activated Office</span></span>
    
- <span data-ttu-id="68b1a-174">сведения о том, что почтовый ящик поддерживается, если применяется почтовый ящик с поддержкой OAuth.</span><span class="sxs-lookup"><span data-stu-id="68b1a-174">Supported Mailbox - If they are on an OAuth-enabled mailbox</span></span>


  
## <a name="user-and-group-assignments"></a><span data-ttu-id="68b1a-175">Назначения для пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="68b1a-175">User and group assignments</span></span>

<span data-ttu-id="68b1a-176">В настоящее время функция централизованного развертывания поддерживает большинство групп, поддерживаемых Azure Active Directory, включая группы Microsoft 365, списки рассылки и группы безопасности.</span><span class="sxs-lookup"><span data-stu-id="68b1a-176">The Centralized Deployment feature currently supports the majority of groups supported by Azure Active Directory, including Microsoft 365 groups, distribution lists, and security groups.</span></span>
  
> [!NOTE]
> <span data-ttu-id="68b1a-177">Сейчас группы безопасности без электронной почты не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="68b1a-177">Non-mail enabled security groups are not currently supported.</span></span> 
  
<span data-ttu-id="68b1a-178">Централизованное развертывание поддерживает назначения для отдельных пользователей, групп и всех пользователей в клиенте.</span><span class="sxs-lookup"><span data-stu-id="68b1a-178">Centralized Deployment supports assignments to individual users, groups, and everyone in the tenant.</span></span> <span data-ttu-id="68b1a-179">Централизованное развертывание поддерживает пользователей в группах или группах верхнего уровня без родительских групп, но не пользователей в вложенных группах или группах с родительскими группами.</span><span class="sxs-lookup"><span data-stu-id="68b1a-179">Centralized Deployment supports users in top-level groups or groups without parent groups, but not users in nested groups or groups that have parent groups.</span></span>
   
<span data-ttu-id="68b1a-p113">Просмотрите пример ниже, в котором надстройка назначается Регине, Ольге и группе Sales Department. Так как группа West Coast Sales является вложенной, надстройка не назначается Николаю и Максиму.</span><span class="sxs-lookup"><span data-stu-id="68b1a-p113">Take a look at the following example where Sandra, Sheila, and the Sales Department group are assigned to an add-in. Because the West Coast Sales Department is a nested group, Bert and Fred aren't assigned to an add-in.</span></span>
  
![Схема отдела продаж](../../media/683094bb-1160-4cce-810d-26ef7264c592.png)

   
### <a name="find-out-if-a-group-contains-nested-groups"></a><span data-ttu-id="68b1a-183">Проверка наличия вложенных групп в группе</span><span class="sxs-lookup"><span data-stu-id="68b1a-183">Find out if a group contains nested groups</span></span>

<span data-ttu-id="68b1a-184">Самый простой способ проверить, содержит ли группа вложенные группы,  посмотреть ее карточку контакта в Outlook.</span><span class="sxs-lookup"><span data-stu-id="68b1a-184">The easiest way to detect if a group contains nested groups is to view the group contact card within Outlook.</span></span> <span data-ttu-id="68b1a-185">Если ввести имя группы в поле " **Кому** " электронного письма, а затем выбрать имя группы при разрешении, оно покажет, содержит ли она пользователей или вложенные группы.</span><span class="sxs-lookup"><span data-stu-id="68b1a-185">If you enter the group name within the **To** field of an email and then select the group name when it resolves, it will show you if it contains users or nested groups.</span></span> <span data-ttu-id="68b1a-186">В примере ниже на вкладке **Участники** карточки контакта Outlook видно, что в группе Test Group нет пользователей и есть две подгруппы.</span><span class="sxs-lookup"><span data-stu-id="68b1a-186">In the example below, the **Members** tab of the Outlook contact card for the Test Group shows no users and only two sub groups.</span></span> 
  
![Вкладка "участники" карточки контакта Outlook](../../media/d9db88c4-d752-426c-a480-b11a5b3adcd6.png)
  
<span data-ttu-id="68b1a-p115">Подключив группу, вы также можете выполнить обратную проверку и узнать, входит ли она в состав другой. В примере ниже на вкладке **Членство** карточки контакта Outlook видно, что группа Sub Group 1 входит в группу Test Group.</span><span class="sxs-lookup"><span data-stu-id="68b1a-p115">You can do the opposite query by resolving the group to see if it's a member of any group. In the example below, you can see under the **Membership** tab of the Outlook contact card that Sub Group 1 is a member of the Test Group.</span></span> 
  
![Вкладка "членство" карточки контакта Outlook](../../media/a9f9b6ab-9c19-4822-9e3d-414ca068c42f.png)
  
<span data-ttu-id="68b1a-p116">Кроме того, вы можете выполнять запросы и находить списки групп, входящих в состав определенной группы, с помощью API Graph Azure Active Directory. Дополнительные сведения см. в статье [Действия с группами | Справка по API Graph](https://go.microsoft.com/fwlink/p/?linkid=846342).</span><span class="sxs-lookup"><span data-stu-id="68b1a-p116">Alternately, you can use the Azure Active Directory Graph API to run queries to find the list of groups within a group. For more information, see [Operations on groups | Graph API reference](https://go.microsoft.com/fwlink/p/?linkid=846342).</span></span>
  
### <a name="contacting-microsoft-for-support"></a><span data-ttu-id="68b1a-193">Обращение в службу поддержки Майкрософт</span><span class="sxs-lookup"><span data-stu-id="68b1a-193">Contacting Microsoft for support</span></span>

<span data-ttu-id="68b1a-194">Если вы или ваши пользователи столкнулись с проблемами при загрузке надстройки при использовании приложений Office для Интернета (Word, Excel и т. д.), которые были централизованно развернуты, вам может потребоваться обратиться в службу поддержки Майкрософт ([Узнайте, как](../contact-support-for-business-products.md)).</span><span class="sxs-lookup"><span data-stu-id="68b1a-194">If you or your users encounter problems loading the add-in while using Office apps for the web (Word, Excel, etc.), which were centrally deployed, you may need to contact Microsoft support ([learn how](../contact-support-for-business-products.md)).</span></span> <span data-ttu-id="68b1a-195">Предоставьте следующие сведения о среде Microsoft 365 в билете поддержки.</span><span class="sxs-lookup"><span data-stu-id="68b1a-195">Provide the following information about your Microsoft 365 environment in the support ticket.</span></span>
  
|<span data-ttu-id="68b1a-196">**Платформа**</span><span class="sxs-lookup"><span data-stu-id="68b1a-196">**Platform**</span></span>|<span data-ttu-id="68b1a-197">**Данные отладки**</span><span class="sxs-lookup"><span data-stu-id="68b1a-197">**Debug information**</span></span>|
|:-----|:-----|
|<span data-ttu-id="68b1a-198">Office</span><span class="sxs-lookup"><span data-stu-id="68b1a-198">Office</span></span>  <br/> | <span data-ttu-id="68b1a-199">Журналы Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="68b1a-199">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="68b1a-200">Идентификатор клиента ( [инструкции по его определению](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span><span class="sxs-lookup"><span data-stu-id="68b1a-200">Tenant ID ( [learn how](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id.aspx))</span></span>  <br/>  <span data-ttu-id="68b1a-201">ИД.</span><span class="sxs-lookup"><span data-stu-id="68b1a-201">CorrelationID.</span></span> <span data-ttu-id="68b1a-202">Просмотрите источник одной из страниц Office и найдите значение идентификатора корреляции и отправьте его в службу поддержки:</span><span class="sxs-lookup"><span data-stu-id="68b1a-202">View the source of one of the office pages and look for the Correlation ID value and send it to support:</span></span>  <br/>`<input name=" **wdCorrelationId**" type="hidden" value=" **{BC17079E-505F-3000-C177-26A8E27EB623}**">`  <br/>  `<input name="user_id" type="hidden" value="1003bffd96933623"></form>`  <br/> |
|<span data-ttu-id="68b1a-203">Классические клиенты (Windows, Mac)</span><span class="sxs-lookup"><span data-stu-id="68b1a-203">Rich clients (Windows, Mac)</span></span>  <br/> | <span data-ttu-id="68b1a-204">Журналы Charles/Fiddler</span><span class="sxs-lookup"><span data-stu-id="68b1a-204">Charles/Fiddler logs</span></span>  <br/>  <span data-ttu-id="68b1a-205">Номера сборок клиентского приложения (желательно в виде снимка экрана из **файла или учетной записи**)</span><span class="sxs-lookup"><span data-stu-id="68b1a-205">Build numbers of the client app (preferably as a screenshot from **File/Account**)</span></span>  <br/> |
   

