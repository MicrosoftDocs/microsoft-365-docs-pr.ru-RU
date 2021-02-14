---
title: Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell
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
description: Узнайте, как включить или отключить самообслуживную покупку с помощью cmdlet AllowSelfServicePurchase PowerShell.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 79ee2d96fa1ae6f49f0402f49ddec34e69257082
ms.sourcegitcommit: 6a1a8aa024fd685d04da97bfcbc8eadacc488534
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/12/2020
ms.locfileid: "46653717"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="48a3e-103">Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="48a3e-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="48a3e-104">Модуль **MSCommerce** PowerShell теперь доступен в [коллекции PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="48a3e-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="48a3e-105">Модуль содержит значение параметра **PolicyID** для **AllowSelfServicePurchase,** которое позволяет контролировать возможность самостоятельного приобретения пользователями в организации.</span><span class="sxs-lookup"><span data-stu-id="48a3e-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="48a3e-106">Модуль **MSCommerce** PowerShell можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="48a3e-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="48a3e-107">Просмотр состояния по умолчанию значения параметра **AllowSelfServicePurchase** — включено ли оно или отключено</span><span class="sxs-lookup"><span data-stu-id="48a3e-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="48a3e-108">Просмотр списка применимых продуктов и включения или отключения самостоятельной покупки</span><span class="sxs-lookup"><span data-stu-id="48a3e-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="48a3e-109">Просмотр или изменение текущего параметра для определенного продукта, чтобы включить или отключить его</span><span class="sxs-lookup"><span data-stu-id="48a3e-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="48a3e-110">Requirements</span><span class="sxs-lookup"><span data-stu-id="48a3e-110">Requirements</span></span>

<span data-ttu-id="48a3e-111">Чтобы использовать модуль **MSCommerce** PowerShell, необходимо:</span><span class="sxs-lookup"><span data-stu-id="48a3e-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="48a3e-112">Устройство с Windows 10</span><span class="sxs-lookup"><span data-stu-id="48a3e-112">A Windows 10 device</span></span>
- <span data-ttu-id="48a3e-113">Разрешение администратора для устройства</span><span class="sxs-lookup"><span data-stu-id="48a3e-113">Administrator permission for the device</span></span>
- <span data-ttu-id="48a3e-114">Роль глобального администратора или администратора вы выставления счета для вашего клиента</span><span class="sxs-lookup"><span data-stu-id="48a3e-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="48a3e-115">Установка модуля MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="48a3e-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="48a3e-116">Модуль **MSCommerce** PowerShell устанавливается на устройстве с Windows 10 один раз, а затем импортируется в каждый запускаемого сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48a3e-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="48a3e-117">Скачайте **модуль MSCommerce** PowerShell из коллекции [PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="48a3e-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="48a3e-118">Чтобы установить модуль **MSCommerce** PowerShell с **помощью PowerShellGet,** запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48a3e-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="48a3e-119">Импорт MSCommerce в сеанс PowerShell</span><span class="sxs-lookup"><span data-stu-id="48a3e-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="48a3e-120">После установки модуля на устройстве с Windows 10 его необходимо импортировать в каждый запуск сеанса PowerShell.</span><span class="sxs-lookup"><span data-stu-id="48a3e-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="48a3e-121">Чтобы импортировать его в сеанс PowerShell, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48a3e-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="48a3e-122">Подключение к MSCommerce с помощью учетных данных</span><span class="sxs-lookup"><span data-stu-id="48a3e-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="48a3e-123">Чтобы подключиться к модуле PowerShell с помощью учетных данных, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="48a3e-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="48a3e-124">Эта команда подключает текущий сеанс PowerShell к клиенту Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="48a3e-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="48a3e-125">Команда запросит имя пользователя и пароль для клиента, к который вы хотите подключиться.</span><span class="sxs-lookup"><span data-stu-id="48a3e-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="48a3e-126">Если для учетных данных включена многофакторная проверка подлинности, для входа используется интерактивный параметр.</span><span class="sxs-lookup"><span data-stu-id="48a3e-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="48a3e-127">Просмотр сведений для AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="48a3e-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="48a3e-128">Чтобы просмотреть описание значения параметра **AllowSelfServicePurchase** и состояния по умолчанию в зависимости от организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48a3e-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="48a3e-129">Просмотр списка продуктов самообслуживки и их состояния</span><span class="sxs-lookup"><span data-stu-id="48a3e-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="48a3e-130">Чтобы просмотреть список всех доступных продуктов самообслуживанию и состояние каждого из них, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48a3e-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="48a3e-131">В следующей таблице перечислены доступные продукты и **их ProductId.**</span><span class="sxs-lookup"><span data-stu-id="48a3e-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="48a3e-132">Продукт</span><span class="sxs-lookup"><span data-stu-id="48a3e-132">Product</span></span> | <span data-ttu-id="48a3e-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="48a3e-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="48a3e-134">Power Apps на пользователя</span><span class="sxs-lookup"><span data-stu-id="48a3e-134">Power Apps per user</span></span> | <span data-ttu-id="48a3e-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="48a3e-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="48a3e-136">Power Automate для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="48a3e-136">Power Automate per user</span></span> | <span data-ttu-id="48a3e-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="48a3e-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="48a3e-138">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="48a3e-138">Power BI Pro</span></span> | <span data-ttu-id="48a3e-139">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="48a3e-139">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="48a3e-140">Проект (план 1)</span><span class="sxs-lookup"><span data-stu-id="48a3e-140">Project Plan 1</span></span> | <span data-ttu-id="48a3e-141">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="48a3e-141">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="48a3e-142">Проект (план 3)</span><span class="sxs-lookup"><span data-stu-id="48a3e-142">Project Plan 3</span></span> | <span data-ttu-id="48a3e-143">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="48a3e-143">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="48a3e-144">Visio (план 1)</span><span class="sxs-lookup"><span data-stu-id="48a3e-144">Visio Plan 1</span></span> | <span data-ttu-id="48a3e-145">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="48a3e-145">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="48a3e-146">Visio (план 2)</span><span class="sxs-lookup"><span data-stu-id="48a3e-146">Visio Plan 2</span></span> | <span data-ttu-id="48a3e-147">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="48a3e-147">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="48a3e-148">Просмотр или настройка состояния allowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="48a3e-148">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="48a3e-149">После просмотра списка продуктов, доступных для самостоятельной покупки, можно просмотреть или изменить параметр для определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="48a3e-149">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="48a3e-150">Чтобы получить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48a3e-150">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="48a3e-151">Чтобы включить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48a3e-151">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="48a3e-152">Чтобы отключить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="48a3e-152">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="48a3e-153">Пример сценария отключения AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="48a3e-153">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="48a3e-154">В следующем примере пошагово импортировать модуль **MSCommerce,** войти в систему с помощью учетной записи, получить **ProductId** для Power Automate, а затем отключить **AllowSelfServicePurchase** для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="48a3e-154">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="48a3e-155">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="48a3e-155">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="48a3e-156">Проблема</span><span class="sxs-lookup"><span data-stu-id="48a3e-156">Problem</span></span>

<span data-ttu-id="48a3e-157">Вы увидите следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="48a3e-157">You see the following error message:</span></span>

> <span data-ttu-id="48a3e-158">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span><span class="sxs-lookup"><span data-stu-id="48a3e-158">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="48a3e-159">Это может быть связано с более старой версией TLS.</span><span class="sxs-lookup"><span data-stu-id="48a3e-159">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="48a3e-160">Чтобы подключить эту службу, необходимо использовать TLS 1.2 или более</span><span class="sxs-lookup"><span data-stu-id="48a3e-160">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="48a3e-161">Решение</span><span class="sxs-lookup"><span data-stu-id="48a3e-161">Solution</span></span>

<span data-ttu-id="48a3e-162">Обновление до TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="48a3e-162">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->
