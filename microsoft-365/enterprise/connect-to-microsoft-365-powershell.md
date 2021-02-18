---
title: Подключение к Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- LIL_Placement
- O365ITProTrain
- Ent_Office_Other
ms.assetid: 5ebc0e21-b72d-46d8-96fa-00643b18eaec
description: Подключитесь к клиенту Microsoft 365, используя PowerShell для Microsoft 365, чтобы выполнять задачи администрирования из командной строки.
ms.openlocfilehash: 0691304a2d40f7ae4262e6761902f16b4f6d5ee2
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/18/2021
ms.locfileid: "50288117"
---
# <a name="connect-to-microsoft-365-with-powershell"></a><span data-ttu-id="c44db-103">Подключение к Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c44db-103">Connect to Microsoft 365 with PowerShell</span></span>

<span data-ttu-id="c44db-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="c44db-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="c44db-105">С помощью PowerShell для Microsoft 365 можно управлять параметрами Microsoft 365 из командной строки.</span><span class="sxs-lookup"><span data-stu-id="c44db-105">PowerShell for Microsoft 365 enables you to manage your Microsoft 365 settings from the command line.</span></span> <span data-ttu-id="c44db-106">Для подключения к PowerShell достаточно лишь установить необходимое программное обеспечения, а затем подключиться к организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c44db-106">To connect to PowerShell, just install the required software and then connect to your Microsoft 365 organization.</span></span>

<span data-ttu-id="c44db-107">Существует две версии модуля PowerShell, которые используются для подключения к Microsoft 365 и управления учетными записями пользователей, группами и лицензиями:</span><span class="sxs-lookup"><span data-stu-id="c44db-107">There are two versions of the PowerShell module that you can use to connect to Microsoft 365 and administer user accounts, groups, and licenses:</span></span>

- <span data-ttu-id="c44db-108">Azure Active Directory PowerShell для Graph (имена командлетов содержат *AzureAD*)</span><span class="sxs-lookup"><span data-stu-id="c44db-108">Azure Active Directory PowerShell for Graph, whose cmdlets include *AzureAD* in their name</span></span>
- <span data-ttu-id="c44db-109">Модуль Microsoft Azure Active Directory для Windows PowerShell (имена командлетов содержат *Msol*)</span><span class="sxs-lookup"><span data-stu-id="c44db-109">Microsoft Azure Active Directory Module for Windows PowerShell, whose cmdlets include *Msol* in their name</span></span>

<span data-ttu-id="c44db-110">В настоящее время модуль Azure Active Directory PowerShell для Graph не полностью заменяет функциональность модуля Microsoft Azure Active Directory для Windows PowerShell в отношении администрирования пользователей, групп и лицензий.</span><span class="sxs-lookup"><span data-stu-id="c44db-110">Currently, the Azure Active Directory PowerShell for Graph module doesn't completely replace the functionality of the Microsoft Azure Active Directory Module for Windows PowerShell module for user, group, and license administration.</span></span> <span data-ttu-id="c44db-111">В некоторых случаях необходимо использовать обе версии.</span><span class="sxs-lookup"><span data-stu-id="c44db-111">In some cases, you need to use both versions.</span></span> <span data-ttu-id="c44db-112">Вы можете безопасно установить обе версии на одном компьютере.</span><span class="sxs-lookup"><span data-stu-id="c44db-112">You can safely install both versions on the same computer.</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="c44db-113">Что нужно знать перед началом работы?</span><span class="sxs-lookup"><span data-stu-id="c44db-113">What do you need to know before you begin?</span></span>


<span data-ttu-id="c44db-114">**Операционная система**</span><span class="sxs-lookup"><span data-stu-id="c44db-114">**Operating system**</span></span>

<span data-ttu-id="c44db-115">Требуется 64-разрядная версия Windows.</span><span class="sxs-lookup"><span data-stu-id="c44db-115">You must use a 64-bit version of Windows.</span></span> <span data-ttu-id="c44db-116">Поддержка 32-разрядной версии модуля Microsoft Azure Active Directory Module для Windows PowerShell прекращена с 2014 года.</span><span class="sxs-lookup"><span data-stu-id="c44db-116">Support for the 32-bit version of the Microsoft Azure Active Directory Module for Windows PowerShell ended in 2014.</span></span>

<span data-ttu-id="c44db-117">Ниже приведены версии Windows, которые можно использовать.</span><span class="sxs-lookup"><span data-stu-id="c44db-117">You can use the following versions of Windows:</span></span>
    
  - <span data-ttu-id="c44db-118">Windows 10, Windows 8.1, Windows 8 или Windows 7 с пакетом обновления 1 (SP1)</span><span class="sxs-lookup"><span data-stu-id="c44db-118">Windows 10, Windows 8.1, Windows 8, or Windows 7 Service Pack 1 (SP1)</span></span> 
    
  - <span data-ttu-id="c44db-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012 или Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="c44db-119">Windows Server 2019, Windows Server 2016, Windows Server 2012 R2, Windows Server 2012, or Windows Server 2008 R2 SP1</span></span>

>[!Note]
><span data-ttu-id="c44db-120">Для Windows 8.1, Windows 8, Windows 7 с пакетом обновления 1 (SP1), Windows Server 2012 R2, Windows Server 2012 и Windows Server 2008 R2 SP1 скачайте и установите [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span><span class="sxs-lookup"><span data-stu-id="c44db-120">For Windows 8.1, Windows 8, Windows 7 Service Pack 1 (SP1), Windows Server 2012 R2, Windows Server 2012, and Windows Server 2008 R2 SP1, download and install the [Windows Management Framework 5.1](https://www.microsoft.com/download/details.aspx?id=54616).</span></span>

<span data-ttu-id="c44db-121">**PowerShell**</span><span class="sxs-lookup"><span data-stu-id="c44db-121">**PowerShell**</span></span>

- <span data-ttu-id="c44db-122">Для модуля Azure Active Directory PowerShell для Graph требуется использовать PowerShell версии 5.1 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="c44db-122">For the Azure Active Directory PowerShell for Graph module, you must use PowerShell version 5.1 or later.</span></span>

- <span data-ttu-id="c44db-123">Для модуля Microsoft Azure Active Directory для Windows PowerShell требуется использовать PowerShell версии от 5.1 до 6.</span><span class="sxs-lookup"><span data-stu-id="c44db-123">For the Microsoft Azure Active Directory Module for Windows PowerShell module, you must use PowerShell version 5.1 or later, up to PowerShell version 6.</span></span> <span data-ttu-id="c44db-124">Использовать PowerShell версии 7 невозможно.</span><span class="sxs-lookup"><span data-stu-id="c44db-124">You can't use PowerShell version 7.</span></span>
       
>[!Note]
><span data-ttu-id="c44db-125">Эти процедуры предназначены для пользователей, которым назначена роль администраторов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c44db-125">These procedures are intended for users who are members of a Microsoft 365 admin role.</span></span> <span data-ttu-id="c44db-126">Дополнительные сведения см. в статье [О ролях администраторов](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span><span class="sxs-lookup"><span data-stu-id="c44db-126">For more information, see [About admin roles](https://go.microsoft.com/fwlink/p/?LinkId=532367).</span></span>


## <a name="connect-with-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="c44db-127">Подключение к модулю Azure Active Directory PowerShell для Graph</span><span class="sxs-lookup"><span data-stu-id="c44db-127">Connect with the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="c44db-128">Имена командлетов в модуле Azure Active Directory PowerShell для Graph включают компонент *AzureAD*.</span><span class="sxs-lookup"><span data-stu-id="c44db-128">Commands in the Azure Active Directory PowerShell for Graph module have *AzureAD* in their cmdlet name.</span></span> <span data-ttu-id="c44db-129">Вы можете установить модуль [Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) или [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span><span class="sxs-lookup"><span data-stu-id="c44db-129">You can install the [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) module or [Azure PowerShell](https://docs.microsoft.com/powershell/azure/install-az-ps).</span></span>

<span data-ttu-id="c44db-130">Если процедурам требуются новые командлеты в модуле PowerShell Azure Active Directory для Graph, выполните эти действия, чтобы установить этот модуль и подключить его к вашей подписке Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c44db-130">For procedures that require the new cmdlets in the Azure Active Directory PowerShell for Graph module, follow these steps to install the module and connect to your Microsoft 365 subscription.</span></span>

> [!Note]
> <span data-ttu-id="c44db-131">Сведения о поддержке различных версий Windows см. в статье [модуль Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span><span class="sxs-lookup"><span data-stu-id="c44db-131">For information about support for different versions of Windows, see [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) .</span></span>

### <a name="step-1-install-the-required-software"></a><span data-ttu-id="c44db-132">Шаг 1. Установите необходимое программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="c44db-132">Step 1: Install the required software</span></span>

<span data-ttu-id="c44db-133">Перечисленные действия необходимо выполнить на компьютере только один раз.</span><span class="sxs-lookup"><span data-stu-id="c44db-133">These steps are required only one time on your computer.</span></span> <span data-ttu-id="c44db-134">При этом, вероятно, потребуется регулярно обновлять программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="c44db-134">But you'll likely need to update the software periodically.</span></span>
  
1. <span data-ttu-id="c44db-135">Откройте командную строку Windows PowerShell с повышенными правами (запустите Windows PowerShell от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="c44db-135">Open an elevated Windows PowerShell Command Prompt window (run Windows PowerShell as an administrator).</span></span>
    
2. <span data-ttu-id="c44db-136">Выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c44db-136">Run this command:</span></span>
    
    ```powershell
    Install-Module -Name AzureAD
    ```

   <span data-ttu-id="c44db-137">Если появится предложение установить модуль из недоверенного репозитория, введите **Y** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c44db-137">If you're prompted to install a module from an untrusted repository, type **Y** and press Enter.</span></span>

### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="c44db-138">Шаг 2. Установите подключение к Azure AD для вашей подписки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c44db-138">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="c44db-139">Чтобы установить подключение к Azure Active Directory (Azure AD) для вашей подписки Microsoft 365 с учетной записью и паролем или с многофакторной проверкой подлинности, выполните одну из следующих команд в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c44db-139">To connect to Azure Active Directory (Azure AD) for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="c44db-140">(повышенные права не требуются).</span><span class="sxs-lookup"><span data-stu-id="c44db-140">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="c44db-141">Облачная служба Office 365</span><span class="sxs-lookup"><span data-stu-id="c44db-141">Office 365 cloud</span></span> | <span data-ttu-id="c44db-142">Команда</span><span class="sxs-lookup"><span data-stu-id="c44db-142">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="c44db-143">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="c44db-143">Office 365 Worldwide (+GCC)</span></span> | `Connect-AzureAD` |
| <span data-ttu-id="c44db-144">Office 365, предоставляемый 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="c44db-144">Office 365 operated by 21 Vianet</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureChinaCloud` |
| <span data-ttu-id="c44db-145">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c44db-145">Office 365 Germany</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureGermanyCloud` |
| <span data-ttu-id="c44db-146">Office 365 для DoD государственных организаций США и Office 365 для GCC High государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="c44db-146">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-AzureAD -AzureEnvironmentName AzureUSGovernment` |
|||

<span data-ttu-id="c44db-147">В диалоговом окне **Вход в учетную запись** введите имя пользователя и пароль своей рабочей или учебной учетной записи Microsoft 365 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c44db-147">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="c44db-148">Если используется многофакторная проверка подлинности, следуйте инструкциям в дополнительных диалоговых окнах, чтобы предоставить дополнительные сведения для проверки подлинности, например код проверки.</span><span class="sxs-lookup"><span data-stu-id="c44db-148">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

<span data-ttu-id="c44db-149">После подключения можно использовать командлеты для [модуля Azure Active Directory PowerShell для Graph](https://docs.microsoft.com/powershell/module/azuread).</span><span class="sxs-lookup"><span data-stu-id="c44db-149">After you connect, you can use the cmdlets for the [Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/powershell/module/azuread).</span></span>

## <a name="connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="c44db-150">Подключение к модулю Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c44db-150">Connect with the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

>[!Note]
><span data-ttu-id="c44db-151">Имена командлетов в модуле Microsoft Azure Active Directory для Windows PowerShell содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="c44db-151">Cmdlets in the Microsoft Azure Active Directory Module for Windows PowerShell have *Msol* in their name.</span></span>

<span data-ttu-id="c44db-152">В PowerShell версии 7 и более поздних версиях не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="c44db-152">PowerShell version 7 and later don't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c44db-153">Для PowerShell версии 7 и более поздних версий требуется использовать модуль Azure Active Directory PowerShell для Graph или Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c44db-153">For PowerShell version 7 and later, you must use the Azure Active Directory PowerShell for Graph module or Azure PowerShell.</span></span>

<span data-ttu-id="c44db-154">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты, имена которых содержат *Msol*.</span><span class="sxs-lookup"><span data-stu-id="c44db-154">PowerShell Core doesn't support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with *Msol* in their name.</span></span> <span data-ttu-id="c44db-155">Эти командлеты требуется запускать из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c44db-155">Run these cmdlets from Windows PowerShell.</span></span>
    
### <a name="step-1-install-the-required-software"></a><span data-ttu-id="c44db-156">Шаг 1. Установите необходимое программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="c44db-156">Step 1: Install the required software</span></span>

<span data-ttu-id="c44db-157">Перечисленные действия необходимо выполнить на компьютере только один раз.</span><span class="sxs-lookup"><span data-stu-id="c44db-157">These steps are required only one time on your computer.</span></span> <span data-ttu-id="c44db-158">При этом, вероятно, потребуется регулярно обновлять программное обеспечение.</span><span class="sxs-lookup"><span data-stu-id="c44db-158">But you'll likely need to update the software periodically.</span></span>
  
1.  <span data-ttu-id="c44db-159">Если вы не используете операционную систему Windows 10, установите 64-разрядную версию помощника по входу в Microsoft Online Services. См. статью [Помощник по входу в Microsoft Online Services для ИТ-специалистов, RTW](https://www.microsoft.com/Download/details.aspx?id=28177).</span><span class="sxs-lookup"><span data-stu-id="c44db-159">If you're not running Windows 10, install the 64-bit version of the Microsoft Online Services Sign-in Assistant: [Microsoft Online Services Sign-in Assistant for IT Professionals RTW](https://www.microsoft.com/Download/details.aspx?id=28177).</span></span>
    
2. <span data-ttu-id="c44db-160">Чтобы установить модуль Microsoft Azure Active Directory для Windows PowerShell, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="c44db-160">Follow these steps to install the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
   1. <span data-ttu-id="c44db-161">Откройте командную строку Windows PowerShell с повышенными привилегиями (запустите Windows PowerShell от имени администратора).</span><span class="sxs-lookup"><span data-stu-id="c44db-161">Open an elevated Windows PowerShell command prompt (run Windows PowerShell as an administrator).</span></span>
   1.  <span data-ttu-id="c44db-162">Выполните команду **Install-Module MSOnline**.</span><span class="sxs-lookup"><span data-stu-id="c44db-162">Run the **Install-Module MSOnline** command.</span></span>
   1. <span data-ttu-id="c44db-163">Если будет предложено установить поставщик NuGet, введите **Y** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c44db-163">If you're prompted to install the NuGet provider, type **Y** and press Enter.</span></span>
   1. <span data-ttu-id="c44db-164">Если будет предложено установить модуль из PSGallery, введите **Y** и нажмите клавишу ВВОД.</span><span class="sxs-lookup"><span data-stu-id="c44db-164">If you're prompted to install the module from PSGallery, type **Y** and press Enter.</span></span>
    
### <a name="step-2-connect-to-azure-ad-for-your-microsoft-365-subscription"></a><span data-ttu-id="c44db-165">Шаг 2. Установите подключение к Azure AD для вашей подписки Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c44db-165">Step 2: Connect to Azure AD for your Microsoft 365 subscription</span></span>

<span data-ttu-id="c44db-166">Чтобы установить подключение к Azure AD для вашей подписки Microsoft 365 с учетной записью и паролем или с многофакторной проверкой подлинности, выполните одну из следующих команд в командной строке Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="c44db-166">To connect to Azure AD for your Microsoft 365 subscription with an account name and password or with multi-factor authentication, run one of these commands from a Windows PowerShell command prompt.</span></span> <span data-ttu-id="c44db-167">(повышенные права не требуются).</span><span class="sxs-lookup"><span data-stu-id="c44db-167">(It doesn't have to be elevated.)</span></span>

| <span data-ttu-id="c44db-168">Облачная служба Office 365</span><span class="sxs-lookup"><span data-stu-id="c44db-168">Office 365 cloud</span></span> | <span data-ttu-id="c44db-169">Команда</span><span class="sxs-lookup"><span data-stu-id="c44db-169">Command</span></span> |
|:-------|:-----|
| <span data-ttu-id="c44db-170">Office 365 Worldwide (+GCC)</span><span class="sxs-lookup"><span data-stu-id="c44db-170">Office 365 Worldwide (+GCC)</span></span> | `Connect-MsolService` |
| <span data-ttu-id="c44db-171">Office 365, предоставляемый 21 Vianet</span><span class="sxs-lookup"><span data-stu-id="c44db-171">Office 365 operated by 21 Vianet</span></span> | `Connect-MsolService -AzureEnvironment AzureChinaCloud` |
| <span data-ttu-id="c44db-172">Office 365 Germany</span><span class="sxs-lookup"><span data-stu-id="c44db-172">Office 365 Germany</span></span> | `Connect-MsolService -AzureEnvironment AzureGermanyCloud` |
| <span data-ttu-id="c44db-173">Office 365 для DoD государственных организаций США и Office 365 для GCC High государственных организаций США</span><span class="sxs-lookup"><span data-stu-id="c44db-173">Office 365 U.S. Government DoD and Office 365 U.S. Government GCC High</span></span> | `Connect-MsolService -AzureEnvironment USGovernment` |
|||

<span data-ttu-id="c44db-174">В диалоговом окне **Вход в учетную запись** введите имя пользователя и пароль своей рабочей или учебной учетной записи Microsoft 365 и нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="c44db-174">In the **Sign into your account** dialog box, type your Microsoft 365 work or school account user name and password, and then select **OK**.</span></span>

<span data-ttu-id="c44db-175">Если используется многофакторная проверка подлинности, следуйте инструкциям в дополнительных диалоговых окнах, чтобы предоставить дополнительные сведения для проверки подлинности, например код проверки.</span><span class="sxs-lookup"><span data-stu-id="c44db-175">If you're using multi-factor authentication, follow the instructions to provide additional authentication information, such as a verification code.</span></span>

### <a name="how-do-you-know-it-worked"></a><span data-ttu-id="c44db-176">Как узнать, что все прошло успешно?</span><span class="sxs-lookup"><span data-stu-id="c44db-176">How do you know it worked?</span></span>

<span data-ttu-id="c44db-177">Если нет сообщений об ошибках, подключение успешно установлено.</span><span class="sxs-lookup"><span data-stu-id="c44db-177">If you don't get an error message, you connected successfully.</span></span> <span data-ttu-id="c44db-178">Для проверки запустите любой командлет Microsoft 365, например **Get-MsolUser**, и проверьте результаты.</span><span class="sxs-lookup"><span data-stu-id="c44db-178">For quick test,  run a Microsoft 365 cmdlet, such as  **Get-MsolUser**, and see the results.</span></span>
  
<span data-ttu-id="c44db-179">Если появится сообщение об ошибке, проверьте следующее:</span><span class="sxs-lookup"><span data-stu-id="c44db-179">If you get an error message, check the following issues:</span></span>
  
- <span data-ttu-id="c44db-180">**Распространенная проблема: неправильный пароль**.</span><span class="sxs-lookup"><span data-stu-id="c44db-180">**A common problem is an incorrect password**.</span></span> <span data-ttu-id="c44db-181">Повторите [шаг 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription), внимательно проверив имя пользователя и пароль.</span><span class="sxs-lookup"><span data-stu-id="c44db-181">Run [Step 2](#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) again, and pay close attention to the user name and password that you enter.</span></span>
    
- <span data-ttu-id="c44db-182">**Для работы модуля Microsoft Azure Active Directory для Windows PowerShell необходимо, чтобы на вашем компьютере был включен компонент Microsoft .NET Framework 3.5.* x*. Скорее всего, на вашем компьютере установлена более новая версия этого компонента (например, 4 или 4.5.\* x\*).</span><span class="sxs-lookup"><span data-stu-id="c44db-182">**The Microsoft Azure Active Directory Module for Windows PowerShell requires that Microsoft .NET Framework 3.5.* x* is enabled on your computer**. It's likely that your computer has a newer version installed (for example, 4 or 4.5.* x*).</span></span> <span data-ttu-id="c44db-183">При этом можно включить или отключить режим обратной совместимости с более ранними версиями .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="c44db-183">But backward compatibility with older versions of the .NET Framework can be enabled or disabled.</span></span> <span data-ttu-id="c44db-184">Дополнительные сведения см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="c44db-184">For more information, see the following articles:</span></span>
    
  - <span data-ttu-id="c44db-185">Windows Server 2012 или Windows Server 2012 R2: см. статью [Включение .NET Framework 3.5 с помощью мастера добавления ролей и функций](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span><span class="sxs-lookup"><span data-stu-id="c44db-185">For Windows Server 2012 or Windows Server 2012 R2, see [Enable .NET Framework 3.5 by using the Add Roles and Features Wizard](https://go.microsoft.com/fwlink/p/?LinkId=532368).</span></span>
    
  - <span data-ttu-id="c44db-186">Windows 7 или Windows Server 2008 R2: см. статью [Не удается открыть модуль Azure Active Directory для Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span><span class="sxs-lookup"><span data-stu-id="c44db-186">For Windows 7 or Windows Server 2008 R2, see [You can't open the Azure Active Directory Module for Windows PowerShell](https://go.microsoft.com/fwlink/p/?LinkId=532370).</span></span>

  - <span data-ttu-id="c44db-187">Windows 10, Windows 8.1 и Windows 8: см. статью [Установка .NET Framework 3.5 в Windows 10, Windows 8.1 и Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span><span class="sxs-lookup"><span data-stu-id="c44db-187">For Windows 10, Windows 8.1, and Windows 8, see [Install the .NET Framework 3.5 on Windows 10, Windows 8.1, and Windows 8](https://docs.microsoft.com/dotnet/framework/install/dotnet-35-windows-10).</span></span>

  
- <span data-ttu-id="c44db-188">**Возможно, ваша версия модуля Microsoft Azure Active Directory для Windows PowerShell устарела.**</span><span class="sxs-lookup"><span data-stu-id="c44db-188">**Your version of the Microsoft Azure Active Directory Module for Windows PowerShell might be out of date.**</span></span> <span data-ttu-id="c44db-189">Чтобы проверить, выполните следующую команду в PowerShell для Microsoft 365 или в модуле Microsoft Azure Active Directory для Windows PowerShell:</span><span class="sxs-lookup"><span data-stu-id="c44db-189">To check, run the following command in PowerShell for Microsoft 365 or the Microsoft Azure Active Directory Module for Windows PowerShell:</span></span>
    
  ```powershell
  (Get-Item C:\Windows\System32\WindowsPowerShell\v1.0\Modules\MSOnline\Microsoft.Online.Administration.Automation.PSModule.dll).VersionInfo.FileVersion
  ```

    <span data-ttu-id="c44db-190">Если возвращенный номер версии меньше *1.0.8070.2*, удалите модуль Microsoft Azure Active Directory для Windows PowerShell и выполните установку с [шага 1](#step-1-install-the-required-software), описанного выше.</span><span class="sxs-lookup"><span data-stu-id="c44db-190">If the version number returned is lower than *1.0.8070.2*, uninstall the Microsoft Azure Active Directory Module for Windows PowerShell and install from [Step 1](#step-1-install-the-required-software), above.</span></span>

- <span data-ttu-id="c44db-191">**Если появится сообщение об ошибке подключение**, см. статью [Ошибка "Connect-MsolService: исключение типа"](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span><span class="sxs-lookup"><span data-stu-id="c44db-191">**If you get a connection error message**, see ["Connect-MsolService: Exception of type was thrown" error](https://go.microsoft.com/fwlink/p/?LinkId=532377).</span></span>
    
- <span data-ttu-id="c44db-192">**Если появляется сообщение об ошибке "Get-Item: не удается найти путь"**, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c44db-192">**If you get a "Get-Item: Cannot find path" error message**, run this command:</span></span>


   ```powershell
     (dir "C:\Program Files\WindowsPowerShell\Modules\MSOnline").Name
   ```

## <a name="see-also"></a><span data-ttu-id="c44db-193">См. также</span><span class="sxs-lookup"><span data-stu-id="c44db-193">See also</span></span>

- [<span data-ttu-id="c44db-194">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="c44db-194">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c44db-195">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c44db-195">Get started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
- [<span data-ttu-id="c44db-196">Подключение ко всем службам Microsoft 365 в одном окне Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="c44db-196">Connect to all Microsoft 365 services in a single Windows PowerShell window</span></span>](connect-to-all-microsoft-365-services-in-a-single-windows-powershell-window.md)
