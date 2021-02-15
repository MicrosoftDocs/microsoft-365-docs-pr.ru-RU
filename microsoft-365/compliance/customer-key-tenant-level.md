---
title: Ключ клиента для Microsoft 365 на уровне клиента (общедоступная предварительная версия)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 12/17/2020
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
description: Узнайте, как настроить ключ клиента для всех данных в клиенте Microsoft 365.
ms.openlocfilehash: f14bbc0cb6dd29883efa4c8d294d8d65cae98641
ms.sourcegitcommit: 98b889e674ad1d5fa37d4b6c5fc3eda60a1d67f3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/05/2021
ms.locfileid: "49751274"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="83180-103">Обзор ключа клиента для Microsoft 365 на уровне клиента (общая предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="83180-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="83180-104">Используя ключи, вы можете создать политику шифрования данных (DEP) и назначить ее арендатору.</span><span class="sxs-lookup"><span data-stu-id="83180-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="83180-105">DEP шифрует данные в клиенте для этих рабочих нагрузок:</span><span class="sxs-lookup"><span data-stu-id="83180-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="83180-106">Сообщения чата Teams (чаты 1:1, групповые чаты, чаты собраний и беседы в каналах)</span><span class="sxs-lookup"><span data-stu-id="83180-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="83180-107">Сообщения мультимедиа Teams (изображения, фрагменты кода, видео, вики-изображения)</span><span class="sxs-lookup"><span data-stu-id="83180-107">Teams media messages (images, code snippets, videos, wiki images)</span></span>
- <span data-ttu-id="83180-108">Записи вызовов и собраний Teams, хранимые в хранилище Teams</span><span class="sxs-lookup"><span data-stu-id="83180-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="83180-109">Уведомления чата Teams</span><span class="sxs-lookup"><span data-stu-id="83180-109">Teams chat notifications</span></span>
- <span data-ttu-id="83180-110">Предложения в чате Teams от Кортаны</span><span class="sxs-lookup"><span data-stu-id="83180-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="83180-111">Сообщения о состоянии Teams</span><span class="sxs-lookup"><span data-stu-id="83180-111">Teams status messages</span></span>
- <span data-ttu-id="83180-112">Сведения о пользователях и сигналах для Exchange Online</span><span class="sxs-lookup"><span data-stu-id="83180-112">User and signal information for Exchange Online</span></span>

<span data-ttu-id="83180-113">В Microsoft Teams ключ клиента на уровне клиента шифрует новые данные с того времени, когда DEP назначен клиенту.</span><span class="sxs-lookup"><span data-stu-id="83180-113">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="83180-114">Общедоступный предварительный просмотр не поддерживает шифрование прошлых данных.</span><span class="sxs-lookup"><span data-stu-id="83180-114">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="83180-115">В Exchange Online ключ клиента шифрует все существующие и новые данные.</span><span class="sxs-lookup"><span data-stu-id="83180-115">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="83180-116">Вы можете создать несколько DEP для каждого клиента, но в любой момент времени можно назначить только одного DEP.</span><span class="sxs-lookup"><span data-stu-id="83180-116">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="83180-117">При назначении DEP шифрование начинается автоматически, но может занять некоторое время в зависимости от размера клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-117">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="83180-118">Политики на уровне клиента добавляют более широкий контроль в ключ клиента для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="83180-118">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="83180-119">Если вы уже настроили ключ клиента для Exchange Online и Sharepoint Online, вот как подходит новая предварительная версия на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-119">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="83180-120">Создаемая политика шифрования на уровне клиента шифрует все данные для рабочих нагрузок Microsoft Teams и Exchange Online в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83180-120">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="83180-121">Эта политика не мешает точно настроенным DEP, уже созданным в ключе клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-121">This policy doesn't interfere with finely tuned DEPs you've already created in Customer Key.</span></span>

<span data-ttu-id="83180-122">Примеры:</span><span class="sxs-lookup"><span data-stu-id="83180-122">Examples:</span></span>

<span data-ttu-id="83180-123">Файлы Microsoft Teams и некоторые записи вызовов и собраний Teams, сохраненные в OneDrive для бизнеса и SharePoint, шифруются deP в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="83180-123">Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="83180-124">Один deP в SharePoint Online шифрует контент в одном географическом области.</span><span class="sxs-lookup"><span data-stu-id="83180-124">A single SharePoint Online DEP encrypts content within a single geo.</span></span> <span data-ttu-id="83180-125">DEP на уровне клиента снова зашифрует зашифрованные данные с помощью новой политики.</span><span class="sxs-lookup"><span data-stu-id="83180-125">The tenant-level DEP will encrypt the encrypted data again with the new policy.</span></span>

<span data-ttu-id="83180-126">Для Exchange Online можно создать DEP, который шифрует один или несколько почтовых ящиков пользователей с помощью ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-126">For Exchange Online, you can create a DEP that encrypts one or more user mailboxes with Customer Key.</span></span> <span data-ttu-id="83180-127">При создании политики на уровне клиента эта политика не шифрует зашифрованные почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="83180-127">When you create a tenant-level policy, that policy will not encrypt the encrypted mailboxes.</span></span> <span data-ttu-id="83180-128">Однако ключ на уровне клиента будет шифровать почтовые ящики, на которые уже не влияет DEP.</span><span class="sxs-lookup"><span data-stu-id="83180-128">However,  the tenant-level key will encrypt the mailboxes that are not affected by a DEP already.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="83180-129">Настройка ключа клиента на уровне клиента (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="83180-129">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="83180-130">Эти действия похожи, но не идентичны шагам по настройке ключа клиента на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="83180-130">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="83180-131">Этот общедоступный предварительный просмотр следует использовать только с тестовой версией в тестовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="83180-131">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="83180-132">Не используйте этот выпуск с производственными данными или в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="83180-132">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="83180-133">Если у вас уже есть производственное развертывание ключа клиента, с помощью этих действий можно настроить ключ клиента на уровне клиента в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="83180-133">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span>

<span data-ttu-id="83180-134">Большинство этих задач можно выполнить с помощью удаленного подключения к Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83180-134">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="83180-135">Для наилучших результатов используйте Azure PowerShell версии 4.4.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="83180-135">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="83180-136">Перед началом работы убедитесь в следующем:</span><span class="sxs-lookup"><span data-stu-id="83180-136">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="83180-137">Чтобы настроить ключ клиента на уровне клиента, необходимо использовать учетную запись для работы или учебного заведения с ролью администратора соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="83180-137">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="83180-138">Убедитесь, что у вас есть соответствующее лицензирование для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="83180-138">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="83180-139">Используйте платную подписку Azure, выставленную с помощью Соглашение Enterprise или поставщика облачных служб.</span><span class="sxs-lookup"><span data-stu-id="83180-139">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="83180-140">Подписки Azure, приобретенные с помощью планов Оплата по мере использования или с помощью кредитной карты, не поддерживаются для ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-140">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="83180-141">С 1 апреля 2020 г. ключ клиента в Office 365 предлагается в службах Office 365 E5, M365 E5, M365 E5 Compliance и M365 E5 Information Protection & Governance SKUs.</span><span class="sxs-lookup"><span data-stu-id="83180-141">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="83180-142">Office 365 Advanced Compliance SKU больше не доступен для получения новых лицензий.</span><span class="sxs-lookup"><span data-stu-id="83180-142">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="83180-143">Существующие лицензии Office 365 Advanced Compliance по-прежнему будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="83180-143">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="83180-144">Хотя службу можно включить как минимум с одной лицензией в клиенте с соответствующей лицензией, необходимо убедиться, что все пользователи, которые получают преимущества от этой службы, имеют соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="83180-144">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="83180-145">Создание двух новых подписок Azure</span><span class="sxs-lookup"><span data-stu-id="83180-145">Create two new Azure subscriptions</span></span>

<span data-ttu-id="83180-146">Для ключа клиента требуются два ключа для каждой политики шифрования данных (DEP).</span><span class="sxs-lookup"><span data-stu-id="83180-146">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="83180-147">Для этого необходимо создать две подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="83180-147">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="83180-148">Рекомендуется, чтобы у вас были отдельные члены вашей организации, которые могут настраивать один ключ в каждой подписке.</span><span class="sxs-lookup"><span data-stu-id="83180-148">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="83180-149">Используйте только эти подписки Azure для администрирования ключей шифрования для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83180-149">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="83180-150">Это защищает организацию на случай, если один из ваших операторов случайно, намеренно или злонамеренно удалит или неправильно укатит ключи, за которые они отвечают.</span><span class="sxs-lookup"><span data-stu-id="83180-150">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="83180-151">На практике нет ограничений на количество подписок Azure, которые можно создать для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="83180-151">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="83180-152">Следуя этой методике, вы сможете свести к минимуму влияние человеческих ошибок, а также управлять ресурсами, используемыми ключом клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-152">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="83180-153">Регистрация подписок Azure для использования обязательного периода хранения</span><span class="sxs-lookup"><span data-stu-id="83180-153">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="83180-154">Временная или постоянная потеря корневых ключей шифрования может нарушить работу службы или даже привести к катастрофическому сбою и потере данных.</span><span class="sxs-lookup"><span data-stu-id="83180-154">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="83180-155">По этой причине ресурсы, используемые с ключом клиента, требуют сильной защиты.</span><span class="sxs-lookup"><span data-stu-id="83180-155">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="83180-156">Все ресурсы Azure, используемые с ключом клиента, предлагают механизмы защиты за пределами конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83180-156">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="83180-157">Подписки Azure можно пометить или зарегистрировать таким образом, чтобы предотвратить немедленную и неупроверяемую отмену.</span><span class="sxs-lookup"><span data-stu-id="83180-157">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="83180-158">Это называется регистрацией на обязательный период хранения.</span><span class="sxs-lookup"><span data-stu-id="83180-158">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="83180-159">Действия, необходимые для регистрации подписок Azure на обязательный период хранения, требуют совместной работы с корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="83180-159">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="83180-160">Этот процесс может занять до пяти бизнес-дней.</span><span class="sxs-lookup"><span data-stu-id="83180-160">This process can take up to five business days.</span></span> <span data-ttu-id="83180-161">Раньше это иногда называлось "Не отменять".</span><span class="sxs-lookup"><span data-stu-id="83180-161">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="83180-162">Перед связью с командой Microsoft 365 необходимо выполнить следующие действия для каждой подписки Azure, которая используется с ключом клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-162">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="83180-163">Перед началом установки убедитесь, что у вас установлен модуль [Azure PowerShell Az.](https://docs.microsoft.com/powershell/azure/new-azureps-module-az)</span><span class="sxs-lookup"><span data-stu-id="83180-163">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="83180-164">Во входе с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83180-164">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="83180-165">Инструкции см. в [документе "Вход с помощью Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="83180-165">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="83180-166">Запустите Register-AzProviderFeature, чтобы зарегистрировать подписки, чтобы использовать обязательный период хранения.</span><span class="sxs-lookup"><span data-stu-id="83180-166">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="83180-167">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="83180-167">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="83180-168">Обратитесь в корпорацию Майкрософт, чтобы завершить процесс по [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="83180-168">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="83180-169">Включите в сообщение электронной почты следующее:</span><span class="sxs-lookup"><span data-stu-id="83180-169">Include the following in your email:</span></span>

   <span data-ttu-id="83180-170">**Тема:** ключ клиента для \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="83180-170">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="83180-171">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span><span class="sxs-lookup"><span data-stu-id="83180-171">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="83180-172">Выходные данные Get-AzProviderFeature для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="83180-172">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="83180-173">Соглашение об уровне обслуживания (SLA) для завершения этого процесса составляет пять бизнес-дней после уведомления (и проверки) корпорации Майкрософт о том, что вы зарегистрировали подписки на использование обязательного периода хранения.</span><span class="sxs-lookup"><span data-stu-id="83180-173">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="83180-174">После получения уведомления от корпорации Майкрософт о том, что регистрация завершена, проверьте состояние регистрации, вы выполните команду Get-AzProviderFeature следующим образом.</span><span class="sxs-lookup"><span data-stu-id="83180-174">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="83180-175">Если проверка подтверждена, Get-AzProviderFeature возвращает значение **Registered для** свойства **Registration State.**</span><span class="sxs-lookup"><span data-stu-id="83180-175">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="83180-176">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="83180-176">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="83180-177">Чтобы завершить процесс, выполните команду Register-AzResourceProvider.</span><span class="sxs-lookup"><span data-stu-id="83180-177">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="83180-178">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="83180-178">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="83180-179">Создание хранилища Azure Key Vault премиум-класса в каждой подписке</span><span class="sxs-lookup"><span data-stu-id="83180-179">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="83180-180">Действия по созданию хранилища ключей описаны в руководстве ["Начало](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)работы с Azure Key Vault", в котором описана установка и запуск Azure PowerShell, подключение к подписке Azure, создание группы ресурсов и создание хранилища ключей в этой группе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="83180-180">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="83180-181">При создании хранилища ключей необходимо выбрать SKU: Standard или Premium.</span><span class="sxs-lookup"><span data-stu-id="83180-181">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="83180-182">Стандартный SKU позволяет защитить ключи Azure Key Vault программным обеспечением без защиты ключей аппаратного модуля безопасности (HSM), а SKU Premium позволяет использовать HSM для защиты ключей Key Vault.</span><span class="sxs-lookup"><span data-stu-id="83180-182">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="83180-183">Ключ клиента принимает хранилища ключей, которые используют любой SKU, хотя Корпорация Майкрософт настоятельно рекомендует использовать только SKU Premium.</span><span class="sxs-lookup"><span data-stu-id="83180-183">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="83180-184">Стоимость операций с ключами обоих типов не отличается, поэтому единственная разница в стоимости — это стоимость каждого ключа, защищенного с помощью HSM, в месяц.</span><span class="sxs-lookup"><span data-stu-id="83180-184">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="83180-185">Подробные [сведения см. в ценах Key Vault.](https://azure.microsoft.com/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="83180-185">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="83180-186">Используйте хранилища ключей SKU Premium и ключи, защищенные HSM, для производственных данных и используйте только стандартные хранилища ключей SKU и ключи для тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="83180-186">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="83180-187">Используйте общий префикс для хранилищ ключей и включаем аббревиатуру использования и область использования хранилища ключей и ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-187">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="83180-188">Например, для службы Contoso, где хранилища будут расположены в Северной Америке, возможной парой имен является Contoso-O365-NA-VaultA1 и Contoso-O365-NA-VaultA2.</span><span class="sxs-lookup"><span data-stu-id="83180-188">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="83180-189">Имена хранилищ — это глобальные уникальные строки в Azure, поэтому вам может потребоваться попробовать варианты нужных имен, если нужные имена уже затверяются другими клиентами Azure.</span><span class="sxs-lookup"><span data-stu-id="83180-189">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="83180-190">После настройки имена хранилищ нельзя изменить, поэтому лучше иметь письменный план установки и использовать второго человека для проверки правильности выполнения плана.</span><span class="sxs-lookup"><span data-stu-id="83180-190">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="83180-191">По возможности создайте хранилища в непарных регионах.</span><span class="sxs-lookup"><span data-stu-id="83180-191">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="83180-192">Парные регионы Azure обеспечивают высокую доступность в доменах сбоев служб.</span><span class="sxs-lookup"><span data-stu-id="83180-192">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="83180-193">Таким образом, региональные пары можно использовать в качестве резервной области друг друга.</span><span class="sxs-lookup"><span data-stu-id="83180-193">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="83180-194">Это означает, что ресурс Azure, размещенный в одном регионе, автоматически получает сбой в парной области.</span><span class="sxs-lookup"><span data-stu-id="83180-194">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="83180-195">По этой причине выбор областей для двух хранилищ, используемых в политике шифрования данных, где эти регионы сопряжены, означает, что используется всего два региона доступности.</span><span class="sxs-lookup"><span data-stu-id="83180-195">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="83180-196">В большинстве географических регионов есть только две области, поэтому выбрать непарные регионы пока невозможно.</span><span class="sxs-lookup"><span data-stu-id="83180-196">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="83180-197">По возможности выберите две непарные области для двух хранилищ, используемых с политикой шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="83180-197">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="83180-198">Это дает преимущества из четырех областей доступности.</span><span class="sxs-lookup"><span data-stu-id="83180-198">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="83180-199">Дополнительные сведения см. в списке "Непрерывность бизнеса и аварийное [восстановление" (BCDR). Парные](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) регионы Azure для текущего списка региональных пар.</span><span class="sxs-lookup"><span data-stu-id="83180-199">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="83180-200">Назначение разрешений каждому хранилищу ключей</span><span class="sxs-lookup"><span data-stu-id="83180-200">Assign permissions to each key vault</span></span>

<span data-ttu-id="83180-201">Для каждого хранилища ключей необходимо определить три отдельных набора разрешений для ключа клиента в зависимости от вашей реализации.</span><span class="sxs-lookup"><span data-stu-id="83180-201">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="83180-202">Например, необходимо определить один набор разрешений для каждого из следующих ок.</span><span class="sxs-lookup"><span data-stu-id="83180-202">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="83180-203">**Администраторы хранилища ключей,** которые будут выполнять ежедневное управление хранилищем ключей для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="83180-203">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="83180-204">К этим задачам относятся резервное копирование, создание, get, импорт, список и восстановление.</span><span class="sxs-lookup"><span data-stu-id="83180-204">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="83180-205">Набор разрешений, присвоенный администраторам хранилищ ключей, не включает разрешение на удаление ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-205">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="83180-206">Это сделано намеренно и важно.</span><span class="sxs-lookup"><span data-stu-id="83180-206">This is intentional and an important practice.</span></span> <span data-ttu-id="83180-207">Удаление ключей шифрования обычно не делается, так как это окончательно уничтожает данные.</span><span class="sxs-lookup"><span data-stu-id="83180-207">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="83180-208">По умолчанию не делайте этого разрешения администраторам хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-208">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="83180-209">Вместо этого следует зарезервировать это значение для участников хранилища ключей и назначить его администратору только на короткое время, только когда будет понято четкое понимание последствий.</span><span class="sxs-lookup"><span data-stu-id="83180-209">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="83180-210">Чтобы назначить эти разрешения пользователю в вашей организации, войдите в свою подписку Azure с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83180-210">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="83180-211">Инструкции см. в [документе "Вход с помощью Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="83180-211">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="83180-212">Запустите Set-AzKeyVaultAccessPolicy, чтобы назначить необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="83180-212">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="83180-213">Пример:</span><span class="sxs-lookup"><span data-stu-id="83180-213">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="83180-214">**Участники хранилища ключей,** которые могут изменять разрешения для самого хранилища Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="83180-214">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="83180-215">Вам потребуется изменить эти разрешения по мере того, как сотрудники уйдут из группы или присоединятся к ней, или в редких случаях, когда администраторам хранилища ключей действительно требуется разрешение на удаление или восстановление ключа.</span><span class="sxs-lookup"><span data-stu-id="83180-215">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="83180-216">Этому набору участников хранилища ключей необходимо предоставить роль "Участник" в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-216">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="83180-217">Эту роль можно назначить с помощью Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="83180-217">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="83180-218">Дополнительные сведения см. в Role-Based [управления доступом](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) для управления доступом к ресурсам подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="83180-218">For detailed steps, see [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="83180-219">Администратор, создавший подписку, имеет такой доступ по умолчанию и возможность назначать роли участника другим администраторам.</span><span class="sxs-lookup"><span data-stu-id="83180-219">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="83180-220">Служба шифрования неанимных данных **Microsoft 365,** которая работает с ключом клиента на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-220">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="83180-221">Чтобы предоставить разрешение на доступ к  Microsoft 365, запустите следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="83180-221">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="83180-222">Где:</span><span class="sxs-lookup"><span data-stu-id="83180-222">Where:</span></span>

  - <span data-ttu-id="83180-223">*имя хранилища* — это имя созданного хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-223">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="83180-224">Пример. Для службы шифрования данных Microsoft 365 в rest замените  *appID Microsoft 365* на `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="83180-224">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="83180-225">Включить и подтвердить возможность мягкого удаления в хранилищах ключей</span><span class="sxs-lookup"><span data-stu-id="83180-225">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="83180-226">Если вы сможете быстро восстановить ключи, вы с меньшей вероятностью будете испытывать расширенные отключения службы из-за случайного или злонамеренного удаления ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-226">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="83180-227">Прежде чем использовать ключи с ключом клиента, в этой конфигурации необходимо включить эту конфигурацию, которая называется "Мягкое удаление".</span><span class="sxs-lookup"><span data-stu-id="83180-227">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="83180-228">Включение функции soft Delete позволяет восстанавливать ключи или хранилища в течение 90 дней после удаления без необходимости восстановления их из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="83180-228">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="83180-229">Чтобы включить soft Delete в хранилищах ключей, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="83180-229">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="83180-230">Sign in to your Azure subscription with Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="83180-230">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="83180-231">Инструкции см. в [документе "Вход с помощью Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="83180-231">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="83180-232">Запустите [cmdlet Get-AzKeyVault.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)</span><span class="sxs-lookup"><span data-stu-id="83180-232">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="83180-233">В этом примере *имя хранилища* — это имя хранилища ключей, для которого вы включите возможность мягкого удаления:</span><span class="sxs-lookup"><span data-stu-id="83180-233">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="83180-234">Подтвердите, что для хранилища ключей настроено мягкое удаление, вы можете с помощью **get-AzKeyVault.**</span><span class="sxs-lookup"><span data-stu-id="83180-234">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="83180-235">Если мягкое удаление настроено правильно для хранилища ключей, свойство _Soft Delete Enabled_ возвращает значение **True:**</span><span class="sxs-lookup"><span data-stu-id="83180-235">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="83180-236">Добавление ключа в каждое хранилище ключей путем создания или импорта ключа</span><span class="sxs-lookup"><span data-stu-id="83180-236">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="83180-237">Существует два способа добавления ключей в хранилище Azure Key Vault. вы можете создать ключ непосредственно в Хранилище Key Vault или импортировать ключ.</span><span class="sxs-lookup"><span data-stu-id="83180-237">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="83180-238">Создание ключа непосредственно в Хранилище Key Vault — менее сложный метод, а импорт ключа обеспечивает полный контроль над тем, как создается ключ.</span><span class="sxs-lookup"><span data-stu-id="83180-238">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="83180-239">Используйте ключи RSA.</span><span class="sxs-lookup"><span data-stu-id="83180-239">Use the RSA keys.</span></span> <span data-ttu-id="83180-240">Хранилище Azure Key Vault не поддерживает перенос и развёртывание с помощью ключей эллиптических кривых.</span><span class="sxs-lookup"><span data-stu-id="83180-240">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="83180-241">Чтобы создать ключ непосредственно в хранилище ключей, выполните cmdlet [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83180-241">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="83180-242">Где:</span><span class="sxs-lookup"><span data-stu-id="83180-242">Where:</span></span>

- <span data-ttu-id="83180-243">*имя хранилища* — это имя хранилища ключей, в котором необходимо создать ключ.</span><span class="sxs-lookup"><span data-stu-id="83180-243">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="83180-244">*имя ключа* — это имя, которое вы хотите предоставить новому ключу.</span><span class="sxs-lookup"><span data-stu-id="83180-244">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="83180-245">Клавиши имен, использующие аналогичное соглашение об именовом имени, как описано выше, для хранилищ ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-245">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="83180-246">Таким образом, в средствах, которые показывают только имя ключа, строка является самоо описанной.</span><span class="sxs-lookup"><span data-stu-id="83180-246">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="83180-247">Если вы собираетесь защитить ключ с помощью HSM, убедитесь, что в качестве значения параметра _Destination_ указывается **HSM,** в противном случае укажите **Software.**</span><span class="sxs-lookup"><span data-stu-id="83180-247">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="83180-248">Пример.</span><span class="sxs-lookup"><span data-stu-id="83180-248">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="83180-249">Проверка уровня восстановления ключей</span><span class="sxs-lookup"><span data-stu-id="83180-249">Check the recovery level of your keys</span></span>

<span data-ttu-id="83180-250">Microsoft 365 требует, чтобы для подписки Azure Key Vault было установлено значение "Не отменять" и что для ключей, используемых ключом клиента, включено мягкое удаление.</span><span class="sxs-lookup"><span data-stu-id="83180-250">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="83180-251">Вы можете подтвердить это, изусмотрив уровень восстановления на ключах.</span><span class="sxs-lookup"><span data-stu-id="83180-251">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="83180-252">Чтобы проверить уровень восстановления ключа, в Azure PowerShell выполните Get-AzKeyVaultKey следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83180-252">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="83180-253">Если свойство _уровня_ восстановления возвращает что-либо, кроме значения **Recoverable+ProtectedSubscription,** необходимо просмотреть эту статью и убедиться, что вы следовали всем шагам, чтобы поместить подписку в список "Не отменять" и что включено "мягкое удаление" в каждом хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-253">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="83180-254">Затем отправьте снимок экрана с выходным сообщением `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` электронной почты m365ck@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="83180-254">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="83180-255">Back up Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83180-255">Back up Azure Key Vault</span></span>

<span data-ttu-id="83180-256">Сразу после создания или изменения ключа выполните резервное копирование и хранение копий резервного копирования как в сети, так и в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="83180-256">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="83180-257">Не подключайте автономные копии к какой-либо сети.</span><span class="sxs-lookup"><span data-stu-id="83180-257">Don't connect offline copies to any network.</span></span> <span data-ttu-id="83180-258">Вместо этого храните их в физическом безопасном или коммерческом хранилище.</span><span class="sxs-lookup"><span data-stu-id="83180-258">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="83180-259">По крайней мере одна копия резервной копии должна храниться в расположении, которое будет доступно в случае аварии.</span><span class="sxs-lookup"><span data-stu-id="83180-259">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="83180-260">Резервные BLOB-ели являются единственным средством восстановления материала ключа, если ключ Key Vault будет окончательно уничтожен или иным образом отрисовке неоперабельно.</span><span class="sxs-lookup"><span data-stu-id="83180-260">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="83180-261">Ключи, которые являются внешними по внешнему хранилищу Azure Key Vault и были импортироваться в Azure Key Vault, не являются резервными, так как метаданные, необходимые для использования ключа клиента, не существуют с внешним ключом.</span><span class="sxs-lookup"><span data-stu-id="83180-261">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="83180-262">Для операций восстановления с помощью ключа клиента можно использовать только резервную копию, взятую из хранилища Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="83180-262">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="83180-263">Поэтому важно создать резервную копию хранилища Azure Key Vault после отправки или создания ключа.</span><span class="sxs-lookup"><span data-stu-id="83180-263">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="83180-264">Чтобы создать резервную копию ключа Azure Key Vault, выполните его с использованием резервного копирования [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83180-264">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="83180-265">Убедитесь, что выходной файл использует `.backup` суффикс.</span><span class="sxs-lookup"><span data-stu-id="83180-265">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="83180-266">Выходной файл, который является результатом этого cmdlet, шифруется и не может использоваться за пределами хранилища Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="83180-266">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="83180-267">Резервную копию можно восстановить только в подписке Azure, из которой была сделана резервная копия.</span><span class="sxs-lookup"><span data-stu-id="83180-267">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="83180-268">Пример:</span><span class="sxs-lookup"><span data-stu-id="83180-268">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="83180-269">Проверка параметров конфигурации Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83180-269">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="83180-270">Выполнение проверки перед использованием ключей в DEP является необязательным, но настоятельно рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="83180-270">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="83180-271">В частности, при использовании действий по настройке ключей и хранилищ, не описанных в этой теме, необходимо проверить состояние ресурсов Azure Key Vault перед настройкой ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-271">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="83180-272">Чтобы убедиться, что для ваших ключей включены операции get, wrapKey и unwrapKey:</span><span class="sxs-lookup"><span data-stu-id="83180-272">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="83180-273">Запустите [cmdlet Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83180-273">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="83180-274">В выходных данных найди политику доступа и соответствующий GUID приложения Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83180-274">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="83180-275">Все три операции, get, wrapKey и unwrapKey, должны быть показаны в области "Разрешения на ключи".</span><span class="sxs-lookup"><span data-stu-id="83180-275">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="83180-276">Если конфигурация политики доступа неправильная, выполните Set-AzKeyVaultAccessPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83180-276">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="83180-277">Пример. Для службы шифрования данных Microsoft 365 в rest замените  *appID Microsoft 365* на `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="83180-277">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="83180-278">Чтобы убедиться, что дата окончания срока действия ключей не установлена, выполните cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="83180-278">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="83180-279">Ключ клиента не может использовать ключ клиента с истекшим сроком действия, что может привести к сбойу службы.</span><span class="sxs-lookup"><span data-stu-id="83180-279">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="83180-280">Настоятельно рекомендуется, чтобы у ключей, используемых с ключом клиента, не было даты окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="83180-280">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="83180-281">Установленную дату окончания срока действия невозможно удалить, но ее можно изменить на другую дату.</span><span class="sxs-lookup"><span data-stu-id="83180-281">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="83180-282">Если необходимо использовать ключ с установленным сроком действия, измените значение срока действия на 31.01.9999.</span><span class="sxs-lookup"><span data-stu-id="83180-282">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="83180-283">Ключи с датой окончания срока действия, задав не более 31.01.9999, не проходят проверку Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="83180-283">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="83180-284">Чтобы изменить дату окончания срока действия, которая была установлена на любое значение, кроме 31.01.9999, выполните этот запуск следующим образом: [](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey)</span><span class="sxs-lookup"><span data-stu-id="83180-284">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="83180-285">Получение URI для каждого ключа Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="83180-285">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="83180-286">После завершения всех действий в Azure по настройкам хранилищ ключей и добавлению ключей, запустите следующую команду, чтобы получить URI для ключа в каждом хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-286">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="83180-287">Эти ЮРИС потребуется использовать при создании и назначении каждого DEP позже, поэтому сохраните эти сведения в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="83180-287">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="83180-288">Не забудьте выполнить эту команду один раз для каждого хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="83180-288">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="83180-289">В Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="83180-289">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="83180-290">Настройка политики шифрования ключа клиента для клиента</span><span class="sxs-lookup"><span data-stu-id="83180-290">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="83180-291">Для запуска этих cmdlets необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="83180-291">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="83180-292">Хотя в этой статье перечислены все параметры для этих параметров, некоторые параметры могут быть не доступны, если они не включены в соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="83180-292">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="83180-293">Сведения о необходимых разрешениях для запуска командлетов и использования параметров в организации см. в статье [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span><span class="sxs-lookup"><span data-stu-id="83180-293">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="83180-294">Создание политики</span><span class="sxs-lookup"><span data-stu-id="83180-294">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

<span data-ttu-id="83180-295">Описание: в этом случае администратор соответствия требованиям может создать новую политику шифрования данных (DEP) с помощью двух корневых ключей AKV.</span><span class="sxs-lookup"><span data-stu-id="83180-295">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="83180-296">После создания политика может быть назначена с помощью Set-M365DataAtRestEncryptionPolicy управления.</span><span class="sxs-lookup"><span data-stu-id="83180-296">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span> <span data-ttu-id="83180-297">После первого назначения ключей или после поворота клавиш может занять до 24 часов, чтобы новые ключи вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="83180-297">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="83180-298">Если новый DEP вступает в силу более 24 часов, обратитесь в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="83180-298">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="83180-299">Пример.</span><span class="sxs-lookup"><span data-stu-id="83180-299">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="83180-300">Параметры:</span><span class="sxs-lookup"><span data-stu-id="83180-300">Parameters:</span></span>

| <span data-ttu-id="83180-301">Имя</span><span class="sxs-lookup"><span data-stu-id="83180-301">Name</span></span> | <span data-ttu-id="83180-302">Описание</span><span class="sxs-lookup"><span data-stu-id="83180-302">Description</span></span> | <span data-ttu-id="83180-303">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="83180-303">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="83180-304">Имя</span><span class="sxs-lookup"><span data-stu-id="83180-304">Name</span></span>|<span data-ttu-id="83180-305">Удобное имя политики шифрования данных</span><span class="sxs-lookup"><span data-stu-id="83180-305">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="83180-306">N</span><span class="sxs-lookup"><span data-stu-id="83180-306">N</span></span>|
|<span data-ttu-id="83180-307">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="83180-307">AzureKeyIDs</span></span>|<span data-ttu-id="83180-308">Указывает два значения URI ключей хранилища ключей Azure, разделенных запятой, для связи с политикой шифрования данных</span><span class="sxs-lookup"><span data-stu-id="83180-308">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="83180-309">N</span><span class="sxs-lookup"><span data-stu-id="83180-309">N</span></span>|
|<span data-ttu-id="83180-310">Описание</span><span class="sxs-lookup"><span data-stu-id="83180-310">Description</span></span>|<span data-ttu-id="83180-311">Описание политики шифрования данных</span><span class="sxs-lookup"><span data-stu-id="83180-311">Description of the data encryption policy</span></span>|<span data-ttu-id="83180-312">N</span><span class="sxs-lookup"><span data-stu-id="83180-312">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="83180-313">Назначение политики</span><span class="sxs-lookup"><span data-stu-id="83180-313">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

<span data-ttu-id="83180-314">Описание: этот cmdlet используется для настройки политики шифрования данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="83180-314">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="83180-315">Эта политика будет использоваться для шифрования данных во всех рабочих нагрузках поддержки.</span><span class="sxs-lookup"><span data-stu-id="83180-315">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="83180-316">Пример.</span><span class="sxs-lookup"><span data-stu-id="83180-316">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

<span data-ttu-id="83180-317">Параметры:</span><span class="sxs-lookup"><span data-stu-id="83180-317">Parameters:</span></span>
| <span data-ttu-id="83180-318">Имя</span><span class="sxs-lookup"><span data-stu-id="83180-318">Name</span></span> | <span data-ttu-id="83180-319">Описание</span><span class="sxs-lookup"><span data-stu-id="83180-319">Description</span></span> | <span data-ttu-id="83180-320">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="83180-320">Optional (Y/N)</span></span> |
|--|--|--|
<span data-ttu-id="83180-321">-Policy</span><span class="sxs-lookup"><span data-stu-id="83180-321">-Policy</span></span>|<span data-ttu-id="83180-322">Указывает политику шифрования данных, которую необходимо на назначенную; укажите имя политики или ИД политики.</span><span class="sxs-lookup"><span data-stu-id="83180-322">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="83180-323">N</span><span class="sxs-lookup"><span data-stu-id="83180-323">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="83180-324">Изменение или обновление политики</span><span class="sxs-lookup"><span data-stu-id="83180-324">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="83180-325">Описание: этот cmdlet можно использовать для изменения или обновления существующей политики.</span><span class="sxs-lookup"><span data-stu-id="83180-325">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="83180-326">Его также можно использовать для включаемой или отключаемой политики.</span><span class="sxs-lookup"><span data-stu-id="83180-326">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="83180-327">После первого назначения ключей или после вращения клавиш может занять до 24 часов, чтобы новые ключи вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="83180-327">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="83180-328">Если новый DEP вступает в силу более 24 часов, обратитесь в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="83180-328">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="83180-329">Примеры:</span><span class="sxs-lookup"><span data-stu-id="83180-329">Examples:</span></span>

<span data-ttu-id="83180-330">Отключать политику шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="83180-330">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="83180-331">Обновите политику шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="83180-331">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

<span data-ttu-id="83180-332">Параметры:</span><span class="sxs-lookup"><span data-stu-id="83180-332">Parameters:</span></span>
| <span data-ttu-id="83180-333">Имя</span><span class="sxs-lookup"><span data-stu-id="83180-333">Name</span></span> | <span data-ttu-id="83180-334">Описание</span><span class="sxs-lookup"><span data-stu-id="83180-334">Description</span></span> | <span data-ttu-id="83180-335">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="83180-335">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="83180-336">-Identity</span><span class="sxs-lookup"><span data-stu-id="83180-336">-Identity</span></span>|<span data-ttu-id="83180-337">Указывает политику шифрования данных, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="83180-337">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="83180-338">N</span><span class="sxs-lookup"><span data-stu-id="83180-338">N</span></span>|
|<span data-ttu-id="83180-339">-Refresh</span><span class="sxs-lookup"><span data-stu-id="83180-339">-Refresh</span></span>|<span data-ttu-id="83180-340">Используйте переключатель Refresh для обновления политики шифрования данных после поворота любых связанных ключей в хранилище Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="83180-340">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="83180-341">С этим параметром не нужно указывать значение.</span><span class="sxs-lookup"><span data-stu-id="83180-341">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="83180-342">Да</span><span class="sxs-lookup"><span data-stu-id="83180-342">Y</span></span>|
|<span data-ttu-id="83180-343">-Enabled</span><span class="sxs-lookup"><span data-stu-id="83180-343">-Enabled</span></span>|<span data-ttu-id="83180-344">Параметр Enabled включает или отключать политику шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="83180-344">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="83180-345">Перед отключением политики необходимо отоименовать ее от клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-345">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="83180-346">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="83180-346">Valid values are:</span></span></br > <span data-ttu-id="83180-347">$true: политика включена</span><span class="sxs-lookup"><span data-stu-id="83180-347">$true: The policy is enabled</span></span></br > <span data-ttu-id="83180-348">$true. Политика включена. Это значение задается по умолчанию.
</span><span class="sxs-lookup"><span data-stu-id="83180-348">$false: The policy is disabled.</span></span>|<span data-ttu-id="83180-349">Да</span><span class="sxs-lookup"><span data-stu-id="83180-349">Y</span></span>|
|<span data-ttu-id="83180-350">-Name</span><span class="sxs-lookup"><span data-stu-id="83180-350">-Name</span></span>|<span data-ttu-id="83180-351">Параметр Name задает уникальное имя политики шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="83180-351">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="83180-352">Да</span><span class="sxs-lookup"><span data-stu-id="83180-352">Y</span></span>
|<span data-ttu-id="83180-353">-Description</span><span class="sxs-lookup"><span data-stu-id="83180-353">-Description</span></span>|<span data-ttu-id="83180-354">Параметр Description задает необязательное описание политики шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="83180-354">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="83180-355">Да</span><span class="sxs-lookup"><span data-stu-id="83180-355">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="83180-356">Получить сведения о политике</span><span class="sxs-lookup"><span data-stu-id="83180-356">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="83180-357">Описание: этот cmdlet перечисляет все политики шифрования M365DataAtRest, созданные для клиента, или сведения о конкретной политике.</span><span class="sxs-lookup"><span data-stu-id="83180-357">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="83180-358">Примеры:</span><span class="sxs-lookup"><span data-stu-id="83180-358">Examples:</span></span>

<span data-ttu-id="83180-359">В этом примере возвращается сводный список политик шифрования M365DatAtRest в организации.</span><span class="sxs-lookup"><span data-stu-id="83180-359">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="83180-360">В этом примере возвращаются подробные сведения о политике шифрования данных с именем "Политика NAM".</span><span class="sxs-lookup"><span data-stu-id="83180-360">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="83180-361">Параметры:</span><span class="sxs-lookup"><span data-stu-id="83180-361">Parameters:</span></span>

| <span data-ttu-id="83180-362">Имя</span><span class="sxs-lookup"><span data-stu-id="83180-362">Name</span></span> | <span data-ttu-id="83180-363">Описание</span><span class="sxs-lookup"><span data-stu-id="83180-363">Description</span></span> | <span data-ttu-id="83180-364">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="83180-364">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="83180-365">-Identity</span><span class="sxs-lookup"><span data-stu-id="83180-365">-Identity</span></span>|<span data-ttu-id="83180-366">Указывает политику шифрования данных, сведения о которую необходимо у вас получить.</span><span class="sxs-lookup"><span data-stu-id="83180-366">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="83180-367">Да</span><span class="sxs-lookup"><span data-stu-id="83180-367">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="83180-368">Получить сведения о назначении политики</span><span class="sxs-lookup"><span data-stu-id="83180-368">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="83180-369">Описание: этот cmdlet перечисляет политику, которая в настоящее время назначена для клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-369">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="83180-370">Отключение ключа клиента</span><span class="sxs-lookup"><span data-stu-id="83180-370">Offboarding from Customer Key</span></span>

<span data-ttu-id="83180-371">Если вам нужно вернуться к ключам, управляемым Майкрософт, вы можете.</span><span class="sxs-lookup"><span data-stu-id="83180-371">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="83180-372">При отключении ваши данные повторно шифруются с использованием шифрования по умолчанию, поддерживаемого каждой отдельной рабочей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="83180-372">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="83180-373">Например, Exchange Online поддерживает шифрование по умолчанию с помощью ключей, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="83180-373">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="83180-374">Если вы решили отключить клиент от ключа клиента на уровне клиента, отправьте корпорации Майкрософт запрос по электронной почте, чтобы "отключить" службу для клиента по [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="83180-374">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to “disable” the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="83180-375">Отключение не то же самое, что очистка данных.</span><span class="sxs-lookup"><span data-stu-id="83180-375">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="83180-376">При очистке данных окончательно криптографическая очистка удаляет данные вашей организации из Microsoft 365, отключение не происходит.</span><span class="sxs-lookup"><span data-stu-id="83180-376">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="83180-377">Вы не можете выполнить очистку данных для политики на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="83180-377">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="83180-378">Сведения о пути очистки данных см. в переочистке ключей и начале процесса [очистки данных.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)</span><span class="sxs-lookup"><span data-stu-id="83180-378">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="83180-379">О ключе доступности</span><span class="sxs-lookup"><span data-stu-id="83180-379">About the availability key</span></span>

<span data-ttu-id="83180-380">Сведения о ключе доступности см. в сведениях [о ключе доступности.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="83180-380">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="83180-381">Поворот клавиш</span><span class="sxs-lookup"><span data-stu-id="83180-381">Key rotation</span></span>

<span data-ttu-id="83180-382">Сведения о вращении или вращении ключей, используемых с ключом клиента, см. в подкатеголи или повороте ключа клиента или [ключа доступности.](customer-key-availability-key-roll.md)</span><span class="sxs-lookup"><span data-stu-id="83180-382">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="83180-383">При обновлении DEP для использования новой версии ключей будет запускаться Set-M365DataAtRestEncryptionPolicy, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="83180-383">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="83180-384">Связанные статьи:</span><span class="sxs-lookup"><span data-stu-id="83180-384">Related articles:</span></span>

- [<span data-ttu-id="83180-385">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="83180-385">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="83180-386">Смена или ротация ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="83180-386">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="83180-387">Узнайте о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="83180-387">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="83180-388">Шифрование службы</span><span class="sxs-lookup"><span data-stu-id="83180-388">Service Encryption</span></span>](office-365-service-encryption.md)
