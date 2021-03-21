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
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce
search.appverid:
- MET150
description: Узнайте, как использовать комлет AllowSelfServicePurchase PowerShell для отключения покупки самообслужива.
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: 9fb5593855f9523198a3d70548e444a831e82c80
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918246"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="89e8b-103">Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="89e8b-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="89e8b-104">Модуль **MSCommerce** PowerShell теперь доступен в [Галерее PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="89e8b-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="89e8b-105">Модуль содержит значение **параметра PolicyID** для **AllowSelfServicePurchase,** которое позволяет контролировать, могут ли пользователи в организации делать покупки с помощью самообслужива.</span><span class="sxs-lookup"><span data-stu-id="89e8b-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="89e8b-106">Модуль **MSCommerce** PowerShell можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="89e8b-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="89e8b-107">Просмотр состояния параметра **AllowSelfServicePurchase** по умолчанию — включено оно или отключено.</span><span class="sxs-lookup"><span data-stu-id="89e8b-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="89e8b-108">Просмотр списка применимых продуктов и включена ли покупка самообслуживки или отключена</span><span class="sxs-lookup"><span data-stu-id="89e8b-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="89e8b-109">Просмотр или изменение текущего параметра для определенного продукта, чтобы включить или отключить его</span><span class="sxs-lookup"><span data-stu-id="89e8b-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="89e8b-110">Требования</span><span class="sxs-lookup"><span data-stu-id="89e8b-110">Requirements</span></span>

<span data-ttu-id="89e8b-111">Чтобы использовать **модуль MSCommerce** PowerShell, необходимо:</span><span class="sxs-lookup"><span data-stu-id="89e8b-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="89e8b-112">Устройство Windows 10</span><span class="sxs-lookup"><span data-stu-id="89e8b-112">A Windows 10 device</span></span>
- <span data-ttu-id="89e8b-113">Разрешение администратора для устройства</span><span class="sxs-lookup"><span data-stu-id="89e8b-113">Administrator permission for the device</span></span>
- <span data-ttu-id="89e8b-114">Роль администратора глобального или биллинга для клиента</span><span class="sxs-lookup"><span data-stu-id="89e8b-114">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="89e8b-115">Установка модуля MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="89e8b-115">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="89e8b-116">Один раз **установите модуль MSCommerce** PowerShell на устройстве Windows 10 и импортируете его в каждую начинаемую сессию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89e8b-116">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="89e8b-117">Скачайте **модуль MSCommerce** PowerShell из [галереи PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="89e8b-117">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="89e8b-118">Чтобы установить **модуль MSCommerce** PowerShell с **PowerShellGet,** запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89e8b-118">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="89e8b-119">Импорт MSCommerce в сеанс PowerShell</span><span class="sxs-lookup"><span data-stu-id="89e8b-119">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="89e8b-120">После установки модуля на устройстве Windows 10 вы импортируете его в каждую начинаемую сессию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="89e8b-120">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="89e8b-121">Чтобы импортировать его в сеанс PowerShell, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89e8b-121">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="89e8b-122">Подключение к MSCommerce с учетными данными</span><span class="sxs-lookup"><span data-stu-id="89e8b-122">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="89e8b-123">Чтобы подключиться к модуле PowerShell с учетными данными, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="89e8b-123">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="89e8b-124">Эта команда соединяет текущий сеанс PowerShell с клиентом Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="89e8b-124">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="89e8b-125">Команда подсказыет вам имя пользователя и пароль для клиента, к который необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="89e8b-125">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="89e8b-126">Если для учетных данных включена многофакторная проверка подлинности, для входа в систему используется интерактивный параметр.</span><span class="sxs-lookup"><span data-stu-id="89e8b-126">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="89e8b-127">Просмотр сведений для AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="89e8b-127">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="89e8b-128">Чтобы просмотреть описание значения параметров **AllowSelfServicePurchase** и состояния по умолчанию, основанного на организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89e8b-128">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="89e8b-129">Просмотр списка продуктов самообслуживки и их состояния</span><span class="sxs-lookup"><span data-stu-id="89e8b-129">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="89e8b-130">Чтобы просмотреть список всех доступных продуктов самообслуживки и состояние каждого из них, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89e8b-130">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="89e8b-131">В следующей таблице перечислены доступные продукты и **их ProductId.**</span><span class="sxs-lookup"><span data-stu-id="89e8b-131">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="89e8b-132">Продукт</span><span class="sxs-lookup"><span data-stu-id="89e8b-132">Product</span></span> | <span data-ttu-id="89e8b-133">ProductId</span><span class="sxs-lookup"><span data-stu-id="89e8b-133">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="89e8b-134">Power Apps на пользователя</span><span class="sxs-lookup"><span data-stu-id="89e8b-134">Power Apps per user</span></span> | <span data-ttu-id="89e8b-135">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="89e8b-135">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="89e8b-136">Power Automate для каждого пользователя</span><span class="sxs-lookup"><span data-stu-id="89e8b-136">Power Automate per user</span></span> | <span data-ttu-id="89e8b-137">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="89e8b-137">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="89e8b-138">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="89e8b-138">Power Automate RPA</span></span> | <span data-ttu-id="89e8b-139">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="89e8b-139">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="89e8b-140">Power BI Premium (автономный)</span><span class="sxs-lookup"><span data-stu-id="89e8b-140">Power BI Premium (standalone)</span></span> | <span data-ttu-id="89e8b-141">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="89e8b-141">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="89e8b-142">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="89e8b-142">Power BI Pro</span></span> | <span data-ttu-id="89e8b-143">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="89e8b-143">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="89e8b-144">Project Plan 1</span><span class="sxs-lookup"><span data-stu-id="89e8b-144">Project Plan 1</span></span> | <span data-ttu-id="89e8b-145">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="89e8b-145">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="89e8b-146">Project Plan 3</span><span class="sxs-lookup"><span data-stu-id="89e8b-146">Project Plan 3</span></span> | <span data-ttu-id="89e8b-147">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="89e8b-147">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="89e8b-148">Visio Plan 1</span><span class="sxs-lookup"><span data-stu-id="89e8b-148">Visio Plan 1</span></span> | <span data-ttu-id="89e8b-149">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="89e8b-149">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="89e8b-150">Visio Plan 2</span><span class="sxs-lookup"><span data-stu-id="89e8b-150">Visio Plan 2</span></span> | <span data-ttu-id="89e8b-151">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="89e8b-151">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="89e8b-152">Просмотр или настройка состояния для AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="89e8b-152">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="89e8b-153">После просмотра списка продуктов, доступных для самостоятельной покупки, можно просмотреть или изменить параметр для определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="89e8b-153">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="89e8b-154">Чтобы получить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89e8b-154">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="89e8b-155">Чтобы включить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89e8b-155">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="89e8b-156">Чтобы отключить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="89e8b-156">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="89e8b-157">Пример сценария отключения AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="89e8b-157">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="89e8b-158">В следующем примере вы можете узнать, как импортировать модуль **MSCommerce,** войти в учетную запись, получить **ProductId** для power Automate, а затем отключить **AllowSelfServicePurchase** для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="89e8b-158">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="89e8b-159">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="89e8b-159">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="89e8b-160">Проблема</span><span class="sxs-lookup"><span data-stu-id="89e8b-160">Problem</span></span>

<span data-ttu-id="89e8b-161">Вы видите следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="89e8b-161">You see the following error message:</span></span>

> <span data-ttu-id="89e8b-162">HandleError. Не удалось получить политику с помощью PolicyId "AllowSelfServicePurchase", ErrorMessage . Первое подключение было закрыто: при отправке произошла неожиданная ошибка.</span><span class="sxs-lookup"><span data-stu-id="89e8b-162">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="89e8b-163">Это может быть связано со старой версией безопасности транспортного слоя (TLS).</span><span class="sxs-lookup"><span data-stu-id="89e8b-163">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="89e8b-164">Чтобы подключить эту службу, необходимо использовать TLS 1.2 или более</span><span class="sxs-lookup"><span data-stu-id="89e8b-164">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="89e8b-165">Решение</span><span class="sxs-lookup"><span data-stu-id="89e8b-165">Solution</span></span>

<span data-ttu-id="89e8b-166">Обновление до TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="89e8b-166">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->