---
title: Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: mijeffer, pablom
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: None
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_ssp
search.appverid:
- MET150
description: Узнайте, как использовать комлет AllowSelfServicePurchase PowerShell для отключения покупки самообслужива.
ROBOTS: NOINDEX, NOFOLLOW
ms.date: 03/18/2021
ms.openlocfilehash: 012874a8794e006d97c4f74014e92e1f7f3c2709
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52536134"
---
# <a name="use-allowselfservicepurchase-for-the-mscommerce-powershell-module"></a><span data-ttu-id="28701-103">Использование AllowSelfServicePurchase для модуля MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="28701-103">Use AllowSelfServicePurchase for the MSCommerce PowerShell module</span></span>

<span data-ttu-id="28701-104">Модуль **MSCommerce** PowerShell теперь доступен в [Галерее PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="28701-104">The **MSCommerce** PowerShell module is now available on [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span> <span data-ttu-id="28701-105">Модуль содержит значение **параметра PolicyID** для **AllowSelfServicePurchase,** которое позволяет контролировать, могут ли пользователи в организации делать покупки с помощью самообслужива.</span><span class="sxs-lookup"><span data-stu-id="28701-105">The module includes a **PolicyID** parameter value for **AllowSelfServicePurchase** that lets you control whether users in your organization can make self-service purchases.</span></span>

<span data-ttu-id="28701-106">Модуль **MSCommerce** PowerShell можно использовать для:</span><span class="sxs-lookup"><span data-stu-id="28701-106">You can use the **MSCommerce** PowerShell module to:</span></span>

- <span data-ttu-id="28701-107">Просмотр состояния параметра **AllowSelfServicePurchase** по умолчанию — включено оно или отключено.</span><span class="sxs-lookup"><span data-stu-id="28701-107">View the default state of the **AllowSelfServicePurchase** parameter value — whether it's enabled or disabled</span></span>
- <span data-ttu-id="28701-108">Просмотр списка применимых продуктов и включена ли покупка самообслуживки или отключена</span><span class="sxs-lookup"><span data-stu-id="28701-108">View a list of applicable products and whether self-service purchase is enabled or disabled</span></span>
- <span data-ttu-id="28701-109">Просмотр или изменение текущего параметра для определенного продукта, чтобы включить или отключить его</span><span class="sxs-lookup"><span data-stu-id="28701-109">View or modify the current setting for a specific product to either enable or disable it</span></span>

## <a name="requirements"></a><span data-ttu-id="28701-110">Требования</span><span class="sxs-lookup"><span data-stu-id="28701-110">Requirements</span></span>

<span data-ttu-id="28701-111">Чтобы использовать **модуль MSCommerce** PowerShell, необходимо:</span><span class="sxs-lookup"><span data-stu-id="28701-111">To use the **MSCommerce** PowerShell module, you need:</span></span>

- <span data-ttu-id="28701-112">Устройство Windows 10</span><span class="sxs-lookup"><span data-stu-id="28701-112">A Windows 10 device</span></span>
- <span data-ttu-id="28701-113">PowerShell 5 или ниже.</span><span class="sxs-lookup"><span data-stu-id="28701-113">PowerShell 5 or below.</span></span> <span data-ttu-id="28701-114">В настоящее время PowerShell 6.x/7.x не поддерживается с помощью этого модуля.</span><span class="sxs-lookup"><span data-stu-id="28701-114">Currently, PowerShell 6.x/7.x isn't supported with this module.</span></span>
- <span data-ttu-id="28701-115">Разрешение администратора для устройства</span><span class="sxs-lookup"><span data-stu-id="28701-115">Administrator permission for the device</span></span>
- <span data-ttu-id="28701-116">Роль администратора глобального или биллинга для клиента</span><span class="sxs-lookup"><span data-stu-id="28701-116">Global or Billing Admin role for your tenant</span></span>

## <a name="install-the-mscommerce-powershell-module"></a><span data-ttu-id="28701-117">Установка модуля MSCommerce PowerShell</span><span class="sxs-lookup"><span data-stu-id="28701-117">Install the MSCommerce PowerShell module</span></span>

<span data-ttu-id="28701-118">Вы устанавливаете **модуль MSCommerce** PowerShell на Windows 10 устройство, а затем импортируете его в каждую начинаемую сессию PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28701-118">You install the **MSCommerce** PowerShell module on your Windows 10 device once and then import it into each PowerShell session you start.</span></span> <span data-ttu-id="28701-119">Скачайте **модуль MSCommerce** PowerShell из [галереи PowerShell.](https://aka.ms/allowselfservicepurchase-powershell-gallery)</span><span class="sxs-lookup"><span data-stu-id="28701-119">Download the **MSCommerce** PowerShell module from the [PowerShell Gallery](https://aka.ms/allowselfservicepurchase-powershell-gallery).</span></span>

<span data-ttu-id="28701-120">Чтобы установить **модуль MSCommerce** PowerShell с **PowerShellGet,** запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28701-120">To install the **MSCommerce** PowerShell module with **PowerShellGet**, run the following command:</span></span>

```powershell
Install-Module -Name MSCommerce
```

## <a name="import-mscommerce-into-the-powershell-session"></a><span data-ttu-id="28701-121">Импорт MSCommerce в сеанс PowerShell</span><span class="sxs-lookup"><span data-stu-id="28701-121">Import MSCommerce into the PowerShell session</span></span>

<span data-ttu-id="28701-122">После установки модуля на Windows 10 вы импортируете его в каждое начинающееся сеанс PowerShell.</span><span class="sxs-lookup"><span data-stu-id="28701-122">After you install the module on your Windows 10 device, you then import it into each PowerShell session that you start.</span></span> <span data-ttu-id="28701-123">Чтобы импортировать его в сеанс PowerShell, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28701-123">To import it into a PowerShell session, run the following command:</span></span>

```powershell
Import-Module -Name MSCommerce
```

## <a name="connect-to-mscommerce-with-your-credentials"></a><span data-ttu-id="28701-124">Подключение MSCommerce с учетными данными</span><span class="sxs-lookup"><span data-stu-id="28701-124">Connect to MSCommerce with your credentials</span></span>

<span data-ttu-id="28701-125">Чтобы подключиться к модуле PowerShell с учетными данными, запустите следующую команду.</span><span class="sxs-lookup"><span data-stu-id="28701-125">To connect to the PowerShell module with your credentials, run the following command.</span></span>

```powershell
Connect-MSCommerce
```

<span data-ttu-id="28701-126">Эта команда соединяет текущий сеанс PowerShell с Azure Active Directory клиентом.</span><span class="sxs-lookup"><span data-stu-id="28701-126">This command connects the current PowerShell session to an Azure Active Directory tenant.</span></span> <span data-ttu-id="28701-127">Команда подсказыет вам имя пользователя и пароль для клиента, к который необходимо подключиться.</span><span class="sxs-lookup"><span data-stu-id="28701-127">The command prompts you for a username and password for the tenant you want to connect to.</span></span> <span data-ttu-id="28701-128">Если для учетных данных включена многофакторная проверка подлинности, для входа в систему используется интерактивный параметр.</span><span class="sxs-lookup"><span data-stu-id="28701-128">If multi-factor authentication is enabled for your credentials, you use the interactive option to log in.</span></span>

## <a name="view-details-for-allowselfservicepurchase"></a><span data-ttu-id="28701-129">Просмотр сведений для AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="28701-129">View details for AllowSelfServicePurchase</span></span>

<span data-ttu-id="28701-130">Чтобы просмотреть описание значения параметров **AllowSelfServicePurchase** и состояния по умолчанию, основанного на организации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28701-130">To view a description of the **AllowSelfServicePurchase** parameter value and the default status, based on your organization, run the following command:</span></span>

```powershell
Get-MSCommercePolicy -PolicyId AllowSelfServicePurchase
```

## <a name="view-a-list-of-self-service-purchase-products-and-their-status"></a><span data-ttu-id="28701-131">Просмотр списка продуктов самообслуживки и их состояния</span><span class="sxs-lookup"><span data-stu-id="28701-131">View a list of self-service purchase products and their status</span></span>

<span data-ttu-id="28701-132">Чтобы просмотреть список всех доступных продуктов самообслуживки и состояние каждого из них, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28701-132">To view a list of all available self-service purchase products and the status of each, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase
```

<span data-ttu-id="28701-133">В следующей таблице перечислены доступные продукты и **их ProductId.**</span><span class="sxs-lookup"><span data-stu-id="28701-133">The following table lists the available products and their **ProductId**.</span></span>

| <span data-ttu-id="28701-134">Продукт</span><span class="sxs-lookup"><span data-stu-id="28701-134">Product</span></span> | <span data-ttu-id="28701-135">ProductId</span><span class="sxs-lookup"><span data-stu-id="28701-135">ProductId</span></span> |
|-----------------------------|--------------|
| <span data-ttu-id="28701-136">Power Apps на пользователя</span><span class="sxs-lookup"><span data-stu-id="28701-136">Power Apps per user</span></span> | <span data-ttu-id="28701-137">CFQ7TTC0KP0P</span><span class="sxs-lookup"><span data-stu-id="28701-137">CFQ7TTC0KP0P</span></span> |
| <span data-ttu-id="28701-138">Power Automate на пользователя</span><span class="sxs-lookup"><span data-stu-id="28701-138">Power Automate per user</span></span> | <span data-ttu-id="28701-139">CFQ7TTC0KP0N</span><span class="sxs-lookup"><span data-stu-id="28701-139">CFQ7TTC0KP0N</span></span> |
| <span data-ttu-id="28701-140">Power Automate RPA</span><span class="sxs-lookup"><span data-stu-id="28701-140">Power Automate RPA</span></span> | <span data-ttu-id="28701-141">CFQ7TTC0KXG6</span><span class="sxs-lookup"><span data-stu-id="28701-141">CFQ7TTC0KXG6</span></span>  |
| <span data-ttu-id="28701-142">Power BI Premium (автономный)</span><span class="sxs-lookup"><span data-stu-id="28701-142">Power BI Premium (standalone)</span></span> | <span data-ttu-id="28701-143">CFQ7TTC0KXG7</span><span class="sxs-lookup"><span data-stu-id="28701-143">CFQ7TTC0KXG7</span></span>  |
| <span data-ttu-id="28701-144">Power BI Pro</span><span class="sxs-lookup"><span data-stu-id="28701-144">Power BI Pro</span></span> | <span data-ttu-id="28701-145">CFQ7TTC0L3PB</span><span class="sxs-lookup"><span data-stu-id="28701-145">CFQ7TTC0L3PB</span></span> |
| <span data-ttu-id="28701-146">Project, план 1</span><span class="sxs-lookup"><span data-stu-id="28701-146">Project Plan 1</span></span> | <span data-ttu-id="28701-147">CFQ7TTC0KXND</span><span class="sxs-lookup"><span data-stu-id="28701-147">CFQ7TTC0KXND</span></span> |
| <span data-ttu-id="28701-148">Project, план 3</span><span class="sxs-lookup"><span data-stu-id="28701-148">Project Plan 3</span></span> | <span data-ttu-id="28701-149">CFQ7TTC0KXNC</span><span class="sxs-lookup"><span data-stu-id="28701-149">CFQ7TTC0KXNC</span></span> |
| <span data-ttu-id="28701-150">Visio, план 1</span><span class="sxs-lookup"><span data-stu-id="28701-150">Visio Plan 1</span></span> | <span data-ttu-id="28701-151">CFQ7TTC0KXN9</span><span class="sxs-lookup"><span data-stu-id="28701-151">CFQ7TTC0KXN9</span></span> |
| <span data-ttu-id="28701-152">Visio, план 2</span><span class="sxs-lookup"><span data-stu-id="28701-152">Visio Plan 2</span></span> | <span data-ttu-id="28701-153">CFQ7TTC0KXN8</span><span class="sxs-lookup"><span data-stu-id="28701-153">CFQ7TTC0KXN8</span></span> |

## <a name="view-or-set-the-status-for-allowselfservicepurchase"></a><span data-ttu-id="28701-154">Просмотр или настройка состояния для AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="28701-154">View or set the status for AllowSelfServicePurchase</span></span>

<span data-ttu-id="28701-155">После просмотра списка продуктов, доступных для самостоятельной покупки, можно просмотреть или изменить параметр для определенного продукта.</span><span class="sxs-lookup"><span data-stu-id="28701-155">After you view the list of products available for self-service purchase, you can view or modify the setting for a specific product.</span></span>

<span data-ttu-id="28701-156">Чтобы получить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28701-156">To get the policy setting for a specific product, run the following command:</span></span>

```powershell
Get-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N
```

<span data-ttu-id="28701-157">Чтобы включить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28701-157">To enable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $True
```

<span data-ttu-id="28701-158">Чтобы отключить параметр политики для определенного продукта, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="28701-158">To disable the policy setting for a specific product, run the following command:</span></span>

```powershell
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId CFQ7TTC0KP0N -Enabled $False
```

## <a name="example-script-to-disable-allowselfservicepurchase"></a><span data-ttu-id="28701-159">Пример сценария отключения AllowSelfServicePurchase</span><span class="sxs-lookup"><span data-stu-id="28701-159">Example script to disable AllowSelfServicePurchase</span></span>

<span data-ttu-id="28701-160">В следующем примере вы можете узнать, как импортировать модуль **MSCommerce,** войти в учетную запись, получить **ProductId** для Power Automate, а затем отключить **AllowSelfServicePurchase** для этого продукта.</span><span class="sxs-lookup"><span data-stu-id="28701-160">The following example walks you through how to import the **MSCommerce** module, sign in with your account, get the **ProductId** for Power Automate, and then disable **AllowSelfServicePurchase** for that product.</span></span>

```powershell
Import-Module -Name MSCommerce
Connect-MSCommerce #sign-in with your global or billing administrator account when prompted
$product = Get-MSCommerceProductPolicies -PolicyId AllowSelfServicePurchase | where {$_.ProductName -match 'Power Automate'}
Update-MSCommerceProductPolicy -PolicyId AllowSelfServicePurchase -ProductId $product.ProductID -Enabled $false
```

## <a name="troubleshooting"></a><span data-ttu-id="28701-161">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="28701-161">Troubleshooting</span></span>

### <a name="problem"></a><span data-ttu-id="28701-162">Проблема</span><span class="sxs-lookup"><span data-stu-id="28701-162">Problem</span></span>

<span data-ttu-id="28701-163">Вы видите следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="28701-163">You see the following error message:</span></span>

> <span data-ttu-id="28701-164">HandleError. Не удалось получить политику с помощью PolicyId "AllowSelfServicePurchase", ErrorMessage . Первое подключение было закрыто: при отправке произошла неожиданная ошибка.</span><span class="sxs-lookup"><span data-stu-id="28701-164">HandleError : Failed to retrieve policy with PolicyId 'AllowSelfServicePurchase', ErrorMessage - The underlying connection was closed: An unexpected error occurred on a send.</span></span>

<span data-ttu-id="28701-165">Это может быть связано со старой версией безопасности транспортного слоя (TLS).</span><span class="sxs-lookup"><span data-stu-id="28701-165">This may be due to an older version of Transport Layer Security (TLS).</span></span> <span data-ttu-id="28701-166">Чтобы подключить эту службу, необходимо использовать TLS 1.2 или более</span><span class="sxs-lookup"><span data-stu-id="28701-166">To connect this service you need to use TLS 1.2 or greater</span></span>

### <a name="solution"></a><span data-ttu-id="28701-167">Решение</span><span class="sxs-lookup"><span data-stu-id="28701-167">Solution</span></span>

<span data-ttu-id="28701-168">Обновление до TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span><span class="sxs-lookup"><span data-stu-id="28701-168">Upgrade to TLS 1.2: [https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2](/mem/configmgr/core/plan-design/security/enable-tls-1-2)</span></span>

<!--
## Uninstall the MSCommerce module

Before you uninstall the MSCommerce module, close your current PowerShell session, then open a new session with admin rights.

To remove the **MSCommerce** PowerShell module from your computer, run the following command:

```powershell
Uninstall-Module -Name MSCommerce
```-->

## <a name="related-content"></a><span data-ttu-id="28701-169">См. также:</span><span class="sxs-lookup"><span data-stu-id="28701-169">Related content</span></span>

<span data-ttu-id="28701-170">[Управление покупками самообслужива (Admin)](manage-self-service-purchases-admins.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="28701-170">[Manage self-service purchases (Admin)](manage-self-service-purchases-admins.md) (article)</span></span>

<span data-ttu-id="28701-171">[FaQ покупки самообслужива](self-service-purchase-faq.yml) (статья)</span><span class="sxs-lookup"><span data-stu-id="28701-171">[Self-service purchase FAQ](self-service-purchase-faq.yml) (article)</span></span>