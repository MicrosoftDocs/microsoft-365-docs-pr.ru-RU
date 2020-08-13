---
title: Использование Алловселфсервицепурчасе для модуля PowerShell Мскоммерце
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- commerce
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
description: Узнайте, как использовать командлет PowerShell Алловселфсервицепурчасе для включения или отключения самостоятельной покупки.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653717"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="91b11-103">Использование Алловселфсервицепурчасе для модуля PowerShell Мскоммерце</span><span class="sxs-lookup"><span data-stu-id="91b11-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="91b11-104">Теперь модуль PowerShell **мскоммерце** доступен в [коллекции PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="91b11-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="91b11-105">Модуль включает значение параметра **полициид** для **алловселфсервицепурчасе** , позволяющее контролировать, могут ли пользователи в вашей организации совершать собственные покупки.</span><span class="sxs-lookup"><span data-stu-id="91b11-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="91b11-106">С помощью модуля PowerShell **мскоммерце** можно выполнять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="91b11-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="91b11-107">Просмотр состояния, используемого по умолчанию для значения параметра **алловселфсервицепурчасе** , независимо от того, включена он или отключен</span><span class="sxs-lookup"><span data-stu-id="91b11-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="91b11-108">Просмотр списка доступных продуктов и включение или отключение самостоятельной покупки</span><span class="sxs-lookup"><span data-stu-id="91b11-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="91b11-109">Просмотр или изменение текущего значения для конкретного продукта, чтобы включить или отключить его</span><span class="sxs-lookup"><span data-stu-id="91b11-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="91b11-110">Требования</span><span class="sxs-lookup"><span data-stu-id="91b11-110">Requirements</span></span>

<span data-ttu-id="91b11-111">Чтобы использовать модуль PowerShell **мскоммерце** , вам потребуется следующее:</span><span class="sxs-lookup"><span data-stu-id="91b11-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="91b11-112">Устройство с Windows 10</span><span class="sxs-lookup"><span data-stu-id="91b11-112">A Windows 10 device</span></span>
- <span data-ttu-id="91b11-113">Разрешение администратора для устройства</span><span class="sxs-lookup"><span data-stu-id="91b11-113">Administrator permission for the device</span></span>
- <span data-ttu-id="91b11-114">Глобальная роль администратора или роль администратора выставления счетов для клиента</span><span class="sxs-lookup"><span data-stu-id="91b11-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="91b11-115">Установка модуля PowerShell Мскоммерце</span><span class="sxs-lookup"><span data-stu-id="91b11-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="91b11-116">Вы устанавливаете модуль PowerShell **мскоммерце** на устройстве с Windows 10, а затем импортируете его в каждый запущенный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b11-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="91b11-117">Скачайте модуль PowerShell **мскоммерце** из [коллекции PowerShell](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span><span class="sxs-lookup"><span data-stu-id="91b11-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="91b11-118">Чтобы установить модуль PowerShell **мскоммерце** с помощью **PowerShellGet**, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="91b11-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="91b11-119">Импорт Мскоммерце в сеанс PowerShell</span><span class="sxs-lookup"><span data-stu-id="91b11-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="91b11-120">После установки модуля на устройстве с Windows 10 импортируйте его в каждый запущенный сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="91b11-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="91b11-121">Чтобы импортировать его в сеанс PowerShell, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="91b11-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="91b11-122">Подключение к Мскоммерце с вашими учетными данными</span><span class="sxs-lookup"><span data-stu-id="91b11-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="91b11-123">Чтобы подключиться к модулю PowerShell с вашими учетными данными, выполните следующую команду.</span><span class="sxs-lookup"><span data-stu-id="91b11-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="91b11-124">Эта команда подключает текущий сеанс PowerShell к клиенту Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="91b11-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="91b11-125">В командной строке запрашивается имя пользователя и пароль для клиента, к которому вы хотите подключиться.</span><span class="sxs-lookup"><span data-stu-id="91b11-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="91b11-126">Если учетные данные включены с многофакторной проверкой подлинности, для входа используется интерактивный режим.</span><span class="sxs-lookup"><span data-stu-id="91b11-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="91b11-127">Просмотр сведений для Алловселфсервицепурчасе</span><span class="sxs-lookup"><span data-stu-id="91b11-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="91b11-128">Чтобы просмотреть описание значения параметра **алловселфсервицепурчасе** и состояние по умолчанию на основе вашей организации, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="91b11-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="91b11-129">Просмотр списка самостоятельных продуктов покупки и их состояния</span><span class="sxs-lookup"><span data-stu-id="91b11-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="91b11-130">Чтобы просмотреть список всех доступных продуктов для самостоятельной покупки и состояние каждой из них, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="91b11-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="91b11-131">В следующей таблице перечислены доступные продукты и их **ProductID**.</span><span class="sxs-lookup"><span data-stu-id="91b11-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="91b11-132">Продукт</span><span class="sxs-lookup"><span data-stu-id="91b11-132">Product</span></span> | <span data-ttu-id="91b11-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="91b11-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="91b11-134">Power Apps для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="91b11-134">Power Apps per user</span></span> | <span data-ttu-id="91b11-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="91b11-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="91b11-136">Автоматизация управления питанием на пользователя</span><span class="sxs-lookup"><span data-stu-id="91b11-136">Power Automate per user</span></span> | <span data-ttu-id="91b11-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="91b11-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="91b11-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="91b11-138">Power BI Pro</span></span> | <span data-ttu-id="91b11-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="91b11-139">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="91b11-140">План проекта 1</span><span class="sxs-lookup"><span data-stu-id="91b11-140">Project Plan 1</span></span> | <span data-ttu-id="91b11-141">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="91b11-141">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="91b11-142">План проекта 3</span><span class="sxs-lookup"><span data-stu-id="91b11-142">Project Plan 3</span></span> | <span data-ttu-id="91b11-143">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="91b11-143">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="91b11-144">План Visio 1</span><span class="sxs-lookup"><span data-stu-id="91b11-144">Visio Plan 1</span></span> | <span data-ttu-id="91b11-145">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="91b11-145">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="91b11-146">Visio (план 2)</span><span class="sxs-lookup"><span data-stu-id="91b11-146">Visio Plan 2</span></span> | <span data-ttu-id="91b11-147">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="91b11-147">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="91b11-148">Просмотр или установка состояния Алловселфсервицепурчасе</span><span class="sxs-lookup"><span data-stu-id="91b11-148">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="91b11-149">После просмотра списка продуктов, доступных для самостоятельной покупки, вы можете просмотреть или изменить параметр для определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="91b11-149">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="91b11-150">Чтобы получить параметр политики для определенного продукта, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="91b11-150">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="91b11-151">Чтобы включить параметр политики для определенного продукта, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="91b11-151">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="91b11-152">Чтобы отключить параметр политики для определенного продукта, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="91b11-152">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="91b11-153">Пример скрипта для отключения Алловселфсервицепурчасе</span><span class="sxs-lookup"><span data-stu-id="91b11-153">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="91b11-154">В приведенном ниже примере показано, как импортировать модуль **мскоммерце** , войти с помощью учетной записи, получить **ProductID** для Power автоматизировать, а затем отключить **алловселфсервицепурчасе** для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="91b11-154">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="91b11-155">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="91b11-155">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="91b11-156">Проблема</span><span class="sxs-lookup"><span data-stu-id="91b11-156">Problem</span></span>

<span data-ttu-id="91b11-157">Отображается следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="91b11-157">You see the following error message:</span></span>

> <span data-ttu-id="91b11-158">HandleError: не удалось получить политику с помощью Полициид "Алловселфсервицепурчасе", ErrorMessage — базовое подключение было закрыто: при отправке произошла непредвиденная ошибка.</span><span class="sxs-lookup"><span data-stu-id="91b11-158">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="91b11-159">Это может быть вызвано более старой версией протокола TLS.</span><span class="sxs-lookup"><span data-stu-id="91b11-159">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="91b11-160">Чтобы подключить эту службу, необходимо использовать протокол TLS 1,2 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="91b11-160">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="91b11-161">Решение</span><span class="sxs-lookup"><span data-stu-id="91b11-161">Solution</span></span>

<span data-ttu-id="91b11-162">Обновление до TLS 1,2:[https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="91b11-162">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
