---
title: Просмотр лицензий и служб Microsoft 365 с помощью PowerShell
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/17/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Ent_Office_Other
- O365ITProTrain
- LIL_Placement
- PowerShell
ms.assetid: bb5260a9-a6a3-4f34-b19a-06c6699f6723
description: Сведения о том, как использовать PowerShell для просмотра сведений о планах лицензирования, службах и лицензиях, доступных в вашей организации Microsoft 365.
ms.openlocfilehash: 3275a513de3c114076e792ab6c5ef86b1413571c
ms.sourcegitcommit: 79065e72c0799064e9055022393113dfcf40eb4b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/14/2020
ms.locfileid: "46693198"
---
# <a name="view-microsoft-365-licenses-and-services-with-powershell"></a><span data-ttu-id="e9833-103">Просмотр лицензий и служб Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9833-103">View Microsoft 365 licenses and services with PowerShell</span></span>

<span data-ttu-id="e9833-104">*Эта статья относится к Microsoft 365 корпоративный и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="e9833-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="e9833-105">Каждая подписка на Microsoft 365 состоит из следующих элементов:</span><span class="sxs-lookup"><span data-stu-id="e9833-105">Every Microsoft 365 subscription consists of the following elements:</span></span>

- <span data-ttu-id="e9833-106">**Планы лицензирования** Они также называются планами лицензирования или планами Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9833-106">**Licensing plans** These are also known as license plans or Microsoft 365 plans.</span></span> <span data-ttu-id="e9833-107">Планы лицензирования определяют службы Microsoft 365, доступные пользователям.</span><span class="sxs-lookup"><span data-stu-id="e9833-107">Licensing plans define the Microsoft 365 services that are available to users.</span></span> <span data-ttu-id="e9833-108">Ваша подписка на Microsoft 365 может содержать несколько планов лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e9833-108">Your Microsoft 365 subscription may contain multiple licensing plans.</span></span> <span data-ttu-id="e9833-109">Примером плана лицензирования может быть Microsoft 365 E3.</span><span class="sxs-lookup"><span data-stu-id="e9833-109">An example licensing plan would be Microsoft 365 E3.</span></span>
    
- <span data-ttu-id="e9833-110">**Службы** Они также называются планами обслуживания.</span><span class="sxs-lookup"><span data-stu-id="e9833-110">**Services** These are also known as service plans.</span></span> <span data-ttu-id="e9833-111">Службы — это продукты, функции и возможности Microsoft 365, доступные в каждом плане лицензирования, например Exchange Online и приложения Microsoft 365 для предприятий (ранее они назывались Office 365 профессиональныйplus).</span><span class="sxs-lookup"><span data-stu-id="e9833-111">Services are the Microsoft 365 products, features, and capabilities that are available in each licensing plan, for example, Exchange Online and Microsoft 365 Apps for enterprise (previously named Office 365 ProPlus).</span></span> <span data-ttu-id="e9833-112">Пользователям может быть назначено несколько лицензий из разных планов лицензирования, которые будут предоставлять доступ к различным службам.</span><span class="sxs-lookup"><span data-stu-id="e9833-112">Users can have multiple licenses assigned to them from different licensing plans that grant access to different services.</span></span>
    
- <span data-ttu-id="e9833-113">**Лицензии** Каждый план лицензирования содержит количество приобретенных лицензий.</span><span class="sxs-lookup"><span data-stu-id="e9833-113">**Licenses** Each licensing plan contains the number of licenses that you purchased.</span></span> <span data-ttu-id="e9833-114">Вы назначаете лицензии пользователям, чтобы они могли использовать службы Microsoft 365, определенные в плане лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e9833-114">You assign licenses to users so they can use the Microsoft 365 services that are defined by the licensing plan.</span></span> <span data-ttu-id="e9833-115">Для каждой учетной записи пользователя требуется по крайней мере одна лицензия из одного плана лицензирования, чтобы они могли войти в Microsoft 365 и использовать службы.</span><span class="sxs-lookup"><span data-stu-id="e9833-115">Every user account requires at least one license from one licensing plan so they can log on to Microsoft 365 and use the services.</span></span>
    
<span data-ttu-id="e9833-116">С помощью PowerShell для Microsoft 365 вы можете просмотреть сведения о доступных планах лицензирования, лицензиях и службах в организации Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e9833-116">You can use PowerShell for Microsoft 365 to view details about the available licensing plans, licenses, and services in your Microsoft 365 organization.</span></span> <span data-ttu-id="e9833-117">Дополнительные сведения о продуктах, функциях и службах, доступных в различных подписках на Office 365, см. в параметрах плана [Office 365.](https://go.microsoft.com/fwlink/p/?LinkId=691147)</span><span class="sxs-lookup"><span data-stu-id="e9833-117">For more information about the products, features, and services that are available in different Office 365 subscriptions, see [Office 365 Plan Options](https://go.microsoft.com/fwlink/p/?LinkId=691147).</span></span>


## <a name="use-the-azure-active-directory-powershell-for-graph-module"></a><span data-ttu-id="e9833-118">Использование модуля PowerShell Azure Active Directory для Graph</span><span class="sxs-lookup"><span data-stu-id="e9833-118">Use the Azure Active Directory PowerShell for Graph module</span></span>

<span data-ttu-id="e9833-119">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)</span><span class="sxs-lookup"><span data-stu-id="e9833-119">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="e9833-120">Чтобы просмотреть сводную информацию о текущих планах лицензирования и доступных лицензиях для каждого плана, запустите данная команда:</span><span class="sxs-lookup"><span data-stu-id="e9833-120">To view summary information about your current licensing plans and the available licenses for each plan, run this command:</span></span>
  
```powershell
Get-AzureADSubscribedSku | Select -Property Sku*,ConsumedUnits -ExpandProperty PrepaidUnits
```

<span data-ttu-id="e9833-121">Результаты содержат:</span><span class="sxs-lookup"><span data-stu-id="e9833-121">The results contain:</span></span>
  
- <span data-ttu-id="e9833-122">**SkuPartNumber:** Показывает доступные планы лицензирования для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e9833-122">**SkuPartNumber:** Shows the available licensing plans for your organization.</span></span> <span data-ttu-id="e9833-123">Например, `ENTERPRISEPACK` это имя плана лицензии для Office 365 корпоративный E3.</span><span class="sxs-lookup"><span data-stu-id="e9833-123">For example, `ENTERPRISEPACK` is the license plan name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="e9833-124">**Включено:** Количество лицензий, приобретенных для определенного плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e9833-124">**Enabled:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="e9833-125">**ConsumedUnits:** Количество лицензий, которые вы написали пользователям из определенного плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e9833-125">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="e9833-126">Чтобы просмотреть сведения о службах Microsoft 365, доступных во всех планах лицензирования, сначала отобразите список планов лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e9833-126">To view details about the Microsoft 365 services that are available in all of your license plans, first display a list of your license plans.</span></span>

```powershell
Get-AzureADSubscribedSku | Select SkuPartNumber
```

<span data-ttu-id="e9833-127">Затем храните сведения о планах лицензий в переменной.</span><span class="sxs-lookup"><span data-stu-id="e9833-127">Next, store the license plans information in a variable.</span></span>

```powershell
$licenses = Get-AzureADSubscribedSku
```

<span data-ttu-id="e9833-128">Затем отобразить службы в определенном плане лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e9833-128">Next, display the services in a specific license plan.</span></span>

```powershell
$licenses[<index>].ServicePlans
```

<span data-ttu-id="e9833-129">\<index> — это целый ряд, который указывает номер строки плана лицензирования из отображения команды `Get-AzureADSubscribedSku | Select SkuPartNumber` минус 1.</span><span class="sxs-lookup"><span data-stu-id="e9833-129">\<index> is an integer that specifies the row number of the license plan from the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command, minus 1.</span></span>

<span data-ttu-id="e9833-130">Например, если команда отображается `Get-AzureADSubscribedSku | Select SkuPartNumber` так:</span><span class="sxs-lookup"><span data-stu-id="e9833-130">For example, if the display of the `Get-AzureADSubscribedSku | Select SkuPartNumber` command is this:</span></span>

```powershell
SkuPartNumber
-------------
WIN10_VDA_E5
EMSPREMIUM
ENTERPRISEPREMIUM
FLOW_FREE
```

<span data-ttu-id="e9833-131">Затем команда для отображения служб для плана лицензирования ENTERPRISEPREMIUM будет такой:</span><span class="sxs-lookup"><span data-stu-id="e9833-131">Then the command to display the services for the ENTERPRISEPREMIUM license plan is this:</span></span>

```powershell
$licenses[2].ServicePlans
```

<span data-ttu-id="e9833-132">ENTERPRISEPREMIUM — это третья строка.</span><span class="sxs-lookup"><span data-stu-id="e9833-132">ENTERPRISEPREMIUM is the third row.</span></span> <span data-ttu-id="e9833-133">Таким образом, индекс имеет значение (3–1) или 2.</span><span class="sxs-lookup"><span data-stu-id="e9833-133">Therefore, the index value is (3 - 1), or 2.</span></span>

<span data-ttu-id="e9833-134">Полный список планов лицензирования (также известных как названия продуктов), включенных в них планов обслуживания и соответствующих названий см. в соответствующем списке названий продуктов и идентификаторов планов обслуживания для [лицензирования.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="e9833-134">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

## <a name="use-the-microsoft-azure-active-directory-module-for-windows-powershell"></a><span data-ttu-id="e9833-135">Использование модуля Microsoft Azure Active Directory для Windows PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9833-135">Use the Microsoft Azure Active Directory Module for Windows PowerShell</span></span>

<span data-ttu-id="e9833-136">Сначала [подключите клиент Microsoft 365.](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell)</span><span class="sxs-lookup"><span data-stu-id="e9833-136">First, [connect to your Microsoft 365 tenant](connect-to-microsoft-365-powershell.md#connect-with-the-microsoft-azure-active-directory-module-for-windows-powershell).</span></span>

>[!Note]
><span data-ttu-id="e9833-137">Кроме того, вы можете воспользоваться сценарием PowerShell, который автоматизирует выполнение процедур, описанных в этой статье.</span><span class="sxs-lookup"><span data-stu-id="e9833-137">A PowerShell script is available that automates the procedures described in this topic.</span></span> <span data-ttu-id="e9833-138">В частности, сценарий позволяет просматривать и отключать службы в организации Microsoft 365, включая Sway.</span><span class="sxs-lookup"><span data-stu-id="e9833-138">Specifically, the script lets you view and disable services in your Microsoft 365 organization, including Sway.</span></span> <span data-ttu-id="e9833-139">Дополнительные сведения см. в [подстраховке "Отключение доступа к Sway с помощью PowerShell".](disable-access-to-sway-with-microsoft-365-powershell.md)</span><span class="sxs-lookup"><span data-stu-id="e9833-139">For more information, see [Disable access to Sway with PowerShell](disable-access-to-sway-with-microsoft-365-powershell.md).</span></span>
>
    
<span data-ttu-id="e9833-140">Чтобы просмотреть сводную информацию о текущих планах лицензирования и доступных лицензиях для каждого плана, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9833-140">To view summary information about your current licensing plans and the available licenses for each plan, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku
```

>[!Note]
><span data-ttu-id="e9833-141">В PowerShell Core не поддерживается модуль Microsoft Azure Active Directory для Windows PowerShell и командлеты с компонентом **Msol** в имени.</span><span class="sxs-lookup"><span data-stu-id="e9833-141">PowerShell Core does not support the Microsoft Azure Active Directory Module for Windows PowerShell module and cmdlets with **Msol** in their name.</span></span> <span data-ttu-id="e9833-142">Чтобы использовать эти командлеты, необходимо запустить их из Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e9833-142">To continue using these cmdlets, you must run them from Windows PowerShell.</span></span>
>

<span data-ttu-id="e9833-143">Результаты содержат сведения, указанные ниже.</span><span class="sxs-lookup"><span data-stu-id="e9833-143">The results contain the following information:</span></span>
  
- <span data-ttu-id="e9833-144">**AccountSkuId:** Показать доступные планы лицензирования для организации с помощью синтаксиса. `<CompanyName>:<LicensingPlan>`</span><span class="sxs-lookup"><span data-stu-id="e9833-144">**AccountSkuId:** Show the available licensing plans for your organization by using the syntax `<CompanyName>:<LicensingPlan>`.</span></span>  <span data-ttu-id="e9833-145">_\<CompanyName>_ это значение, которое вы предоставили при регистрации в Microsoft 365 и уникально для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e9833-145">_\<CompanyName>_ is the value that you provided when you enrolled in Microsoft 365, and is unique for your organization.</span></span> <span data-ttu-id="e9833-146">Значение _\<LicensingPlan>_ одинаково для всех.</span><span class="sxs-lookup"><span data-stu-id="e9833-146">The _\<LicensingPlan>_ value is the same for everyone.</span></span> <span data-ttu-id="e9833-147">Например, в значении название компании — и имя плана лицензирования, которое является системным именем `litwareinc:ENTERPRISEPACK`  `litwareinc` Office  `ENTERPRISEPACK` 365 корпоративный E3.</span><span class="sxs-lookup"><span data-stu-id="e9833-147">For example, in the value `litwareinc:ENTERPRISEPACK`, the company name is  `litwareinc`, and the licensing plan name  `ENTERPRISEPACK`, which is the system name for Office 365 Enterprise E3.</span></span>
    
- <span data-ttu-id="e9833-148">**ActiveUnits:** Количество лицензий, приобретенных для определенного плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e9833-148">**ActiveUnits:** Number of licenses that you've purchased for a specific licensing plan.</span></span>
    
- <span data-ttu-id="e9833-149">**WarningUnits:** Количество лицензий в плане лицензирования, которые вы не продлевали и срок действия которых истекает после 30-дневного льготного периода.</span><span class="sxs-lookup"><span data-stu-id="e9833-149">**WarningUnits:** Number of licenses in a licensing plan that you haven't renewed, and that will expire after the 30-day grace period.</span></span>
    
- <span data-ttu-id="e9833-150">**ConsumedUnits:** Количество лицензий, которые вы написали пользователям из определенного плана лицензирования.</span><span class="sxs-lookup"><span data-stu-id="e9833-150">**ConsumedUnits:** Number of licenses that you've assigned to users from a specific licensing plan.</span></span>
    
<span data-ttu-id="e9833-151">Чтобы просмотреть сведения о службах Microsoft 365, доступных во всех планах лицензирования, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="e9833-151">To view details about the Microsoft 365 services that are available in all of your license plans, run the following command:</span></span>
  
```powershell
Get-MsolAccountSku | Select -ExpandProperty ServiceStatus
```

<span data-ttu-id="e9833-152">В следующей таблице показаны планы обслуживания Microsoft 365 и их названия для наиболее распространенных служб.</span><span class="sxs-lookup"><span data-stu-id="e9833-152">The following table shows the Microsoft 365 service plans and their friendly names for the most common services.</span></span> <span data-ttu-id="e9833-153">Ваш список планов обслуживания может отличаться.</span><span class="sxs-lookup"><span data-stu-id="e9833-153">Your list of service plans might be different.</span></span> 
  
|<span data-ttu-id="e9833-154">**План обслуживания**</span><span class="sxs-lookup"><span data-stu-id="e9833-154">**Service plan**</span></span>|<span data-ttu-id="e9833-155">**Описание**</span><span class="sxs-lookup"><span data-stu-id="e9833-155">**Description**</span></span>|
|:-----|:-----|
| `SWAY` <br/> |<span data-ttu-id="e9833-156">Sway</span><span class="sxs-lookup"><span data-stu-id="e9833-156">Sway</span></span>  <br/> |
| `TEAMS1` <br/> |<span data-ttu-id="e9833-157">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e9833-157">Microsoft Teams</span></span>  <br/> |
| `YAMMER_ENTERPRISE` <br/> |<span data-ttu-id="e9833-158">Yammer</span><span class="sxs-lookup"><span data-stu-id="e9833-158">Yammer</span></span>  <br/> |
| `RMS_S_ENTERPRISE` <br/> |<span data-ttu-id="e9833-159">Azure Rights Management (RMS)</span><span class="sxs-lookup"><span data-stu-id="e9833-159">Azure Rights Management (RMS)</span></span>  <br/> |
| `OFFICESUBSCRIPTION` <br/> |<span data-ttu-id="e9833-160">Приложения Microsoft 365 для предприятий (ранее называлось *Office 365 профессиональныйplus)*</span><span class="sxs-lookup"><span data-stu-id="e9833-160">Microsoft 365 Apps for enterprise *(previously named Office 365 ProPlus)*</span></span>  <br/> |
| `MCOSTANDARD` <br/> |<span data-ttu-id="e9833-161">Skype для бизнеса Online</span><span class="sxs-lookup"><span data-stu-id="e9833-161">Skype for Business Online</span></span>  <br/> |
| `SHAREPOINTWAC` <br/> |<span data-ttu-id="e9833-162">Office</span><span class="sxs-lookup"><span data-stu-id="e9833-162">Office</span></span>  <br/> |
| `SHAREPOINTENTERPRISE` <br/> |<span data-ttu-id="e9833-163">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="e9833-163">SharePoint Online</span></span>  <br/> |
| `EXCHANGE_S_ENTERPRISE` <br/> |<span data-ttu-id="e9833-164">Exchange Online (план 2)</span><span class="sxs-lookup"><span data-stu-id="e9833-164">Exchange Online Plan 2</span></span>  <br/> |
   
<span data-ttu-id="e9833-165">Полный список планов лицензирования (также известных как названия продуктов), включенных в них планов обслуживания и соответствующих названий см. в соответствующем списке названий продуктов и идентификаторов планов обслуживания для [лицензирования.](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference)</span><span class="sxs-lookup"><span data-stu-id="e9833-165">For a complete list of license plans (also known as product names), their included service plans, and their corresponding friendly names, see [Product names and service plan identifiers for licensing](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-service-plan-reference).</span></span>

<span data-ttu-id="e9833-166">Чтобы просмотреть сведения о службах Microsoft 365, доступных в определенном плане лицензирования, используйте следующий синтаксис.</span><span class="sxs-lookup"><span data-stu-id="e9833-166">To view details about the Microsoft 365 services that are available in a specific licensing plan, use the following syntax.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "<AccountSkuId>"}).ServiceStatus
```

<span data-ttu-id="e9833-167">В этом примере показаны службы, доступные в плане лицензирования litwareinc:ENTERPRISEPACK (Office 365 корпоративный E3).</span><span class="sxs-lookup"><span data-stu-id="e9833-167">This example shows the services that are available in the litwareinc:ENTERPRISEPACK (Office 365 Enterprise E3) licensing plan.</span></span>
  
```powershell
(Get-MsolAccountSku | where {$_.AccountSkuId -eq "litwareinc:ENTERPRISEPACK"}).ServiceStatus
```

## <a name="see-also"></a><span data-ttu-id="e9833-168">См. также</span><span class="sxs-lookup"><span data-stu-id="e9833-168">See also</span></span>

[<span data-ttu-id="e9833-169">Управление учетными записями пользователей Microsoft 365, лицензиями и группами с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9833-169">Manage Microsoft 365 user accounts, licenses, and groups with PowerShell</span></span>](manage-user-accounts-and-licenses-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e9833-170">Управление Microsoft 365 с помощью PowerShell</span><span class="sxs-lookup"><span data-stu-id="e9833-170">Manage Microsoft 365 with PowerShell</span></span>](manage-microsoft-365-with-microsoft-365-powershell.md)
  
[<span data-ttu-id="e9833-171">Начало работы с PowerShell для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e9833-171">Getting started with PowerShell for Microsoft 365</span></span>](getting-started-with-microsoft-365-powershell.md)
