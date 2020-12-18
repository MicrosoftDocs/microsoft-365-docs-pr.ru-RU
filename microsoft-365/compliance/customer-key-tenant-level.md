---
title: Ключ клиента для Microsoft 365 на уровне клиента (предварительная версия)
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
ms.openlocfilehash: eedf0e8c9d56131016bc798af8ae471df3005bdc
ms.sourcegitcommit: 0867495cb02d0b38b439b16bdce97e6eda483ba9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/18/2020
ms.locfileid: "49712533"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="086d8-103">Обзор ключа клиента для Microsoft 365 на уровне клиента (общая предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="086d8-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="086d8-104">Используя ключи, вы можете создать политику шифрования данных (DEP) и назначить ее арендатору.</span><span class="sxs-lookup"><span data-stu-id="086d8-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="086d8-105">DEP шифрует данные в клиенте для этих рабочих нагрузок:</span><span class="sxs-lookup"><span data-stu-id="086d8-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="086d8-106">Сообщения чата Teams (чаты 1:1, групповые чаты, чаты собраний и беседы в каналах)</span><span class="sxs-lookup"><span data-stu-id="086d8-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="086d8-107">Сообщения мультимедиа Teams (изображения, фрагменты кода, видео, вики-изображения)</span><span class="sxs-lookup"><span data-stu-id="086d8-107">Teams media messages (images, code snippets, videos, wiki images)</span></span>
- <span data-ttu-id="086d8-108">Записи вызовов и собраний Teams, хранимые в хранилище Teams</span><span class="sxs-lookup"><span data-stu-id="086d8-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="086d8-109">Уведомления чата Teams</span><span class="sxs-lookup"><span data-stu-id="086d8-109">Teams chat notifications</span></span>
- <span data-ttu-id="086d8-110">Предложения в чате Teams от Кортаны</span><span class="sxs-lookup"><span data-stu-id="086d8-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="086d8-111">Сообщения о состоянии Teams</span><span class="sxs-lookup"><span data-stu-id="086d8-111">Teams status messages</span></span>
- <span data-ttu-id="086d8-112">Сведения о пользователях и сигналах для Exchange Online</span><span class="sxs-lookup"><span data-stu-id="086d8-112">User and signal information for Exchange Online</span></span>

<span data-ttu-id="086d8-113">В Microsoft Teams ключ клиента на уровне клиента шифрует новые данные с того времени, когда DEP назначен клиенту.</span><span class="sxs-lookup"><span data-stu-id="086d8-113">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="086d8-114">Общедоступный предварительный просмотр не поддерживает шифрование прошлых данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-114">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="086d8-115">В Exchange Online ключ клиента шифрует все существующие и новые данные.</span><span class="sxs-lookup"><span data-stu-id="086d8-115">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="086d8-116">Вы можете создать несколько DEP для каждого клиента, но в любой момент времени можно назначить только одну DEP.</span><span class="sxs-lookup"><span data-stu-id="086d8-116">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="086d8-117">При назначении DEP шифрование начинается автоматически, но может занять некоторое время в зависимости от размера клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-117">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="086d8-118">Политики на уровне клиента добавляют более широкий контроль в ключ клиента для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="086d8-118">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="086d8-119">Если вы уже настроили ключ клиента для Exchange Online и Sharepoint Online, вот как подходит новая предварительная версия на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-119">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="086d8-120">Создаемая политика шифрования на уровне клиента шифрует все данные для рабочих нагрузок Microsoft Teams и Exchange Online в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="086d8-120">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="086d8-121">Эта политика не мешает точно настроенным DEP, уже созданным в ключе клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-121">This policy doesn't interfere with finely tuned DEPs you've already created in Customer Key.</span></span>

<span data-ttu-id="086d8-122">Примеры:</span><span class="sxs-lookup"><span data-stu-id="086d8-122">Examples:</span></span>

<span data-ttu-id="086d8-123">Файлы Microsoft Teams и некоторые записи вызовов и собраний Teams, сохраненные в OneDrive для бизнеса и SharePoint, шифруются deP в SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="086d8-123">Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="086d8-124">Один deP в SharePoint Online шифрует контент в одном географическом области.</span><span class="sxs-lookup"><span data-stu-id="086d8-124">A single SharePoint Online DEP encrypts content within a single geo.</span></span> <span data-ttu-id="086d8-125">DeP на уровне клиента снова зашифрует зашифрованные данные с помощью новой политики.</span><span class="sxs-lookup"><span data-stu-id="086d8-125">The tenant-level DEP will encrypt the encrypted data again with the new policy.</span></span>

<span data-ttu-id="086d8-126">Для Exchange Online можно создать DEP, который шифрует один или несколько почтовых ящиков пользователей с помощью ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-126">For Exchange Online, you can create a DEP that encrypts one or more user mailboxes with Customer Key.</span></span> <span data-ttu-id="086d8-127">При создании политики на уровне клиента эта политика не шифрует зашифрованные почтовые ящики.</span><span class="sxs-lookup"><span data-stu-id="086d8-127">When you create a tenant-level policy, that policy will not encrypt the encrypted mailboxes.</span></span> <span data-ttu-id="086d8-128">Однако ключ на уровне клиента шифрует почтовые ящики, на которые не влияет DEP.</span><span class="sxs-lookup"><span data-stu-id="086d8-128">However,  the tenant-level key will encrypt the mailboxes that are not affected by a DEP already.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="086d8-129">Настройка ключа клиента на уровне клиента (общедоступный предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="086d8-129">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="086d8-130">Эти действия похожи, но не идентичны шагам по настройке ключа клиента на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="086d8-130">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="086d8-131">Этот общедоступный предварительный просмотр следует использовать только с тестовой версией в тестовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="086d8-131">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="086d8-132">Не используйте этот выпуск с производственными данными или в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="086d8-132">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="086d8-133">Если у вас уже есть производственное развертывание ключа клиента, с помощью этих действий можно настроить ключ клиента на уровне клиента в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="086d8-133">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span>

<span data-ttu-id="086d8-134">Большинство этих задач можно выполнить с помощью удаленного подключения к Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="086d8-134">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="086d8-135">Для наилучших результатов используйте Azure PowerShell версии 4.4.0 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="086d8-135">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="086d8-136">Перед началом работы убедитесь в следующем:</span><span class="sxs-lookup"><span data-stu-id="086d8-136">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="086d8-137">Чтобы настроить ключ клиента на уровне клиента, необходимо использовать учетную запись для работы или учебного заведения с ролью администратора соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="086d8-137">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="086d8-138">Убедитесь, что у вас есть соответствующее лицензирование для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="086d8-138">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="086d8-139">Используйте платную подписку Azure, выставленную с помощью Соглашение Enterprise или поставщика облачных служб.</span><span class="sxs-lookup"><span data-stu-id="086d8-139">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="086d8-140">Подписки Azure, приобретенные с помощью планов Оплата по мере использования или с помощью кредитной карты, не поддерживаются для ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-140">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="086d8-141">С 1 апреля 2020 г. ключ клиента в Office 365 предлагается в office 365 E5, M365 E5, M365 E5 Compliance и M365 E5 Information Protection & Governance SKUs.</span><span class="sxs-lookup"><span data-stu-id="086d8-141">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="086d8-142">Office 365 Advanced Compliance SKU больше не доступен для получения новых лицензий.</span><span class="sxs-lookup"><span data-stu-id="086d8-142">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="086d8-143">Существующие лицензии Office 365 Advanced Compliance по-прежнему будут поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="086d8-143">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="086d8-144">Хотя службу можно включить как минимум с одной лицензией в клиенте с соответствующей лицензией, необходимо убедиться, что все пользователи, которые получают преимущества от этой службы, имеют соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="086d8-144">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span> <span data-ttu-id="086d8-145">Вам потребуется одна из следующих лицензий:</span><span class="sxs-lookup"><span data-stu-id="086d8-145">You'll need one of the following licenses:</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="086d8-146">Создание двух новых подписок Azure</span><span class="sxs-lookup"><span data-stu-id="086d8-146">Create two new Azure subscriptions</span></span>

<span data-ttu-id="086d8-147">Для ключа клиента требуются два ключа для каждой политики шифрования данных (DEP).</span><span class="sxs-lookup"><span data-stu-id="086d8-147">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="086d8-148">Для этого необходимо создать две подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="086d8-148">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="086d8-149">Рекомендуется, чтобы у вас были отдельные члены вашей организации, которые могут настраивать один ключ в каждой подписке.</span><span class="sxs-lookup"><span data-stu-id="086d8-149">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="086d8-150">Используйте только эти подписки Azure для администрирования ключей шифрования для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="086d8-150">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="086d8-151">Это защищает организацию на случай, если один из ваших операторов случайно, намеренно или злонамеренно удалит или неправильно укатит ключи, за которые они отвечают.</span><span class="sxs-lookup"><span data-stu-id="086d8-151">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="086d8-152">На практике нет ограничений на количество подписок Azure, которые можно создать для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="086d8-152">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="086d8-153">Следуя этой методике, вы сможете свести к минимуму влияние человеческих ошибок, а также управлять ресурсами, используемыми ключом клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-153">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="086d8-154">Регистрация подписок Azure для использования обязательного периода хранения</span><span class="sxs-lookup"><span data-stu-id="086d8-154">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="086d8-155">Временная или постоянная потеря корневых ключей шифрования может нарушить работу службы или даже привести к катастрофическому сбою и потере данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-155">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="086d8-156">По этой причине ресурсы, используемые с ключом клиента, требуют сильной защиты.</span><span class="sxs-lookup"><span data-stu-id="086d8-156">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="086d8-157">Все ресурсы Azure, используемые с ключом клиента, предлагают механизмы защиты за пределами конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="086d8-157">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="086d8-158">Подписки Azure можно пометить или зарегистрировать таким образом, чтобы предотвратить немедленную и неупроверяемую отмену.</span><span class="sxs-lookup"><span data-stu-id="086d8-158">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="086d8-159">Это называется регистрацией на обязательный период хранения.</span><span class="sxs-lookup"><span data-stu-id="086d8-159">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="086d8-160">Действия, необходимые для регистрации подписок Azure на обязательный период хранения, требуют совместной работы с корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="086d8-160">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="086d8-161">Этот процесс может занять до пяти дней.</span><span class="sxs-lookup"><span data-stu-id="086d8-161">This process can take up to five business days.</span></span> <span data-ttu-id="086d8-162">Раньше это иногда называлось "Не отменять".</span><span class="sxs-lookup"><span data-stu-id="086d8-162">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="086d8-163">Перед связью с командой Microsoft 365 необходимо выполнить следующие действия для каждой подписки Azure, которая используется с ключом клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-163">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="086d8-164">Перед началом установки убедитесь, что у вас установлен модуль [Azure PowerShell Az.](https://docs.microsoft.com/powershell/azure/new-azureps-module-az)</span><span class="sxs-lookup"><span data-stu-id="086d8-164">Ensure that you have the [Azure PowerShell Az](https://docs.microsoft.com/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="086d8-165">Во входе с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="086d8-165">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="086d8-166">Инструкции см. в [документе "Вход с помощью Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="086d8-166">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="086d8-167">Запустите Register-AzProviderFeature, чтобы зарегистрировать подписки, чтобы использовать обязательный период хранения.</span><span class="sxs-lookup"><span data-stu-id="086d8-167">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="086d8-168">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="086d8-168">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="086d8-169">Обратитесь в корпорацию Майкрософт, чтобы завершить процесс по [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="086d8-169">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="086d8-170">Включите в сообщение электронной почты следующее:</span><span class="sxs-lookup"><span data-stu-id="086d8-170">Include the following in your email:</span></span>

   <span data-ttu-id="086d8-171">**Тема:** ключ клиента для \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="086d8-171">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="086d8-172">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span><span class="sxs-lookup"><span data-stu-id="086d8-172">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="086d8-173">Выходные данные Get-AzProviderFeature для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="086d8-173">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="086d8-174">Соглашение об уровне обслуживания (SLA) для завершения этого процесса составляет пять бизнес-дней после уведомления (и проверки) корпорации Майкрософт о том, что вы зарегистрировали подписки на использование обязательного периода хранения.</span><span class="sxs-lookup"><span data-stu-id="086d8-174">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="086d8-175">После получения уведомления от корпорации Майкрософт о том, что регистрация завершена, проверьте состояние регистрации, вы выполните команду Get-AzProviderFeature следующим образом.</span><span class="sxs-lookup"><span data-stu-id="086d8-175">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="086d8-176">Если проверка подтверждена, Get-AzProviderFeature возвращает значение **Registered для** свойства **Registration State.**</span><span class="sxs-lookup"><span data-stu-id="086d8-176">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="086d8-177">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="086d8-177">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="086d8-178">Чтобы завершить процесс, выполните команду Register-AzResourceProvider.</span><span class="sxs-lookup"><span data-stu-id="086d8-178">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="086d8-179">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="086d8-179">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="086d8-180">Создание хранилища Azure Key Vault премиум-класса в каждой подписке</span><span class="sxs-lookup"><span data-stu-id="086d8-180">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="086d8-181">Действия по созданию хранилища ключей описаны в руководстве "Начало работы с [Azure Key Vault",](https://azure.microsoft.com/documentation/articles/key-vault-get-started/)в котором описана установка и запуск Azure PowerShell, подключение к подписке Azure, создание группы ресурсов и создание хранилища ключей в этой группе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="086d8-181">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](https://azure.microsoft.com/documentation/articles/key-vault-get-started/), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="086d8-182">При создании хранилища ключей необходимо выбрать SKU: Standard или Premium.</span><span class="sxs-lookup"><span data-stu-id="086d8-182">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="086d8-183">Стандартный SKU позволяет защитить ключи Azure Key Vault программным обеспечением без защиты ключей аппаратного модуля безопасности (HSM), а SKU Premium позволяет использовать HSM для защиты ключей Key Vault.</span><span class="sxs-lookup"><span data-stu-id="086d8-183">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="086d8-184">Ключ клиента принимает хранилища ключей, которые используют любой SKU, хотя Корпорация Майкрософт настоятельно рекомендует использовать только SKU Premium.</span><span class="sxs-lookup"><span data-stu-id="086d8-184">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="086d8-185">Затраты на операции с ключами обоих типов одинаковы, поэтому единственное различие в стоимости — это стоимость каждого ключа, защищенного с помощью HSM.</span><span class="sxs-lookup"><span data-stu-id="086d8-185">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="086d8-186">Подробные [сведения см. в ценах Key Vault.](https://azure.microsoft.com/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="086d8-186">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="086d8-187">Используйте хранилища ключей SKU Premium и ключи, защищенные HSM, для производственных данных и используйте только стандартные хранилища ключей SKU и ключи для тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="086d8-187">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="086d8-188">Используйте общий префикс для хранилищ ключей и включаем аббревиатуру использования и область использования хранилища ключей и ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-188">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="086d8-189">Например, для службы Contoso, где хранилища будут расположены в Северной Америке, возможной парой имен является Contoso-O365-NA-VaultA1 и Contoso-O365-NA-VaultA2.</span><span class="sxs-lookup"><span data-stu-id="086d8-189">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="086d8-190">Имена хранилищ — это глобальные уникальные строки в Azure, поэтому вам может потребоваться попробовать варианты нужных имен, если нужные имена уже затверяются другими клиентами Azure.</span><span class="sxs-lookup"><span data-stu-id="086d8-190">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="086d8-191">После настройки имена хранилищ нельзя изменить, поэтому лучше иметь письменный план установки и использовать второго человека для проверки правильности выполнения плана.</span><span class="sxs-lookup"><span data-stu-id="086d8-191">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="086d8-192">По возможности создайте хранилища в непарных регионах.</span><span class="sxs-lookup"><span data-stu-id="086d8-192">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="086d8-193">Парные регионы Azure обеспечивают высокую доступность в доменах сбоев служб.</span><span class="sxs-lookup"><span data-stu-id="086d8-193">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="086d8-194">Таким образом, региональные пары можно использовать в качестве резервной области друг друга.</span><span class="sxs-lookup"><span data-stu-id="086d8-194">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="086d8-195">Это означает, что ресурс Azure, размещенный в одном регионе, автоматически получает сбой в парной области.</span><span class="sxs-lookup"><span data-stu-id="086d8-195">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="086d8-196">По этой причине выбор областей для двух хранилищ, используемых в политике шифрования данных, где эти регионы сопряжены, означает, что используется всего два региона доступности.</span><span class="sxs-lookup"><span data-stu-id="086d8-196">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="086d8-197">В большинстве географических регионов есть только две области, поэтому выбрать непарные регионы пока невозможно.</span><span class="sxs-lookup"><span data-stu-id="086d8-197">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="086d8-198">По возможности выберите две непарные области для двух хранилищ, используемых с политикой шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-198">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="086d8-199">Это дает преимущества из четырех областей доступности.</span><span class="sxs-lookup"><span data-stu-id="086d8-199">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="086d8-200">Дополнительные сведения см. в списке "Непрерывность бизнеса и аварийное [восстановление" (BCDR). Парные](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) регионы Azure для текущего списка региональных пар.</span><span class="sxs-lookup"><span data-stu-id="086d8-200">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](https://docs.microsoft.com/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="086d8-201">Назначение разрешений каждому хранилищу ключей</span><span class="sxs-lookup"><span data-stu-id="086d8-201">Assign permissions to each key vault</span></span>

<span data-ttu-id="086d8-202">Для каждого хранилища ключей необходимо определить три отдельных набора разрешений для ключа клиента в зависимости от вашей реализации.</span><span class="sxs-lookup"><span data-stu-id="086d8-202">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="086d8-203">Например, необходимо определить один набор разрешений для каждого из следующих ок.</span><span class="sxs-lookup"><span data-stu-id="086d8-203">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="086d8-204">**Администраторы хранилища ключей,** которые будут выполнять ежедневное управление хранилищем ключей для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="086d8-204">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="086d8-205">К этим задачам относятся резервное копирование, создание, get, импорт, список и восстановление.</span><span class="sxs-lookup"><span data-stu-id="086d8-205">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="086d8-206">Набор разрешений, присвоенный администраторам хранилищ ключей, не включает разрешение на удаление ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-206">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="086d8-207">Это сделано намеренно и важно.</span><span class="sxs-lookup"><span data-stu-id="086d8-207">This is intentional and an important practice.</span></span> <span data-ttu-id="086d8-208">Удаление ключей шифрования обычно не делается, так как это окончательно уничтожает данные.</span><span class="sxs-lookup"><span data-stu-id="086d8-208">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="086d8-209">По умолчанию не делайте этого разрешения администраторам хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-209">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="086d8-210">Вместо этого следует зарезервировать это для участников хранилища ключей и назначить его администратору только на короткое время, только когда будет понято четкое понимание последствий.</span><span class="sxs-lookup"><span data-stu-id="086d8-210">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="086d8-211">Чтобы назначить эти разрешения пользователю в организации, войдите в свою подписку Azure с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="086d8-211">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="086d8-212">Инструкции см. в [документе "Вход с помощью Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="086d8-212">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="086d8-213">Запустите Set-AzKeyVaultAccessPolicy, чтобы назначить необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="086d8-213">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="086d8-214">Пример:</span><span class="sxs-lookup"><span data-stu-id="086d8-214">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="086d8-215">**Участники хранилища ключей,** которые могут изменять разрешения для самого хранилища Ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="086d8-215">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="086d8-216">Вам потребуется изменить эти разрешения по мере того, как сотрудники уйдут из группы или присоединятся к ней, или в редких случаях, когда администраторам хранилища ключей действительно требуется разрешение на удаление или восстановление ключа.</span><span class="sxs-lookup"><span data-stu-id="086d8-216">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="086d8-217">Этому набору участников хранилища ключей необходимо предоставить роль "Участник" в хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-217">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="086d8-218">Эту роль можно назначить с помощью Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="086d8-218">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="086d8-219">Дополнительные сведения см. в Role-Based [управления доступом](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) для управления доступом к ресурсам подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="086d8-219">For detailed steps, see [Use Role-Based Access Control](https://docs.microsoft.com/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="086d8-220">Администратор, создавший подписку, имеет такой доступ по умолчанию и возможность назначать роли участника другим администраторам.</span><span class="sxs-lookup"><span data-stu-id="086d8-220">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="086d8-221">Служба шифрования неанимных данных **Microsoft 365,** которая работает с ключом клиента на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-221">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="086d8-222">Чтобы предоставить разрешение на доступ к  Microsoft 365, запустите следующий синтаксис:</span><span class="sxs-lookup"><span data-stu-id="086d8-222">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="086d8-223">Где:</span><span class="sxs-lookup"><span data-stu-id="086d8-223">Where:</span></span>

  - <span data-ttu-id="086d8-224">*имя хранилища* — это имя созданного хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-224">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="086d8-225">Пример. Для службы шифрования данных Microsoft 365 в rest замените  *appID Microsoft 365* на `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="086d8-225">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="086d8-226">Включить и подтвердить возможность мягкого удаления в хранилищах ключей</span><span class="sxs-lookup"><span data-stu-id="086d8-226">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="086d8-227">Если вы сможете быстро восстановить ключи, вы с меньшей вероятностью будете испытывать расширенный с выход из-за случайного или злонамеренного удаления ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-227">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="086d8-228">Прежде чем использовать ключи с ключом клиента, в этой конфигурации необходимо включить эту конфигурацию, которая называется "Мягкое удаление".</span><span class="sxs-lookup"><span data-stu-id="086d8-228">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="086d8-229">Включение функции soft Delete позволяет восстанавливать ключи или хранилища в течение 90 дней после удаления без необходимости восстановления их из резервной копии.</span><span class="sxs-lookup"><span data-stu-id="086d8-229">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="086d8-230">Чтобы включить soft Delete в хранилищах ключей, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="086d8-230">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="086d8-231">Sign in to your Azure subscription with Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="086d8-231">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="086d8-232">Инструкции см. в [документе "Вход с помощью Azure PowerShell".](https://docs.microsoft.com/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="086d8-232">For instructions, see [Sign in with Azure PowerShell](https://docs.microsoft.com/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="086d8-233">Запустите [cmdlet Get-AzKeyVault.](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault)</span><span class="sxs-lookup"><span data-stu-id="086d8-233">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="086d8-234">В этом примере *имя хранилища* — это имя хранилища ключей, для которого вы включите возможность мягкого удаления:</span><span class="sxs-lookup"><span data-stu-id="086d8-234">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="086d8-235">Подтвердите, что для хранилища ключей настроено мягкое удаление, вы можете с помощью **get-AzKeyVault.**</span><span class="sxs-lookup"><span data-stu-id="086d8-235">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="086d8-236">Если мягкое удаление настроено правильно для хранилища ключей, свойство _Soft Delete Enabled_ возвращает значение **True:**</span><span class="sxs-lookup"><span data-stu-id="086d8-236">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="086d8-237">Добавление ключа в каждое хранилище ключей путем создания или импорта ключа</span><span class="sxs-lookup"><span data-stu-id="086d8-237">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="086d8-238">Существует два способа добавления ключей в хранилище Azure Key Vault. вы можете создать ключ непосредственно в Хранилище Key Vault или импортировать ключ.</span><span class="sxs-lookup"><span data-stu-id="086d8-238">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="086d8-239">Создание ключа непосредственно в Хранилище Key Vault является менее сложным методом, а импорт ключа обеспечивает полный контроль над тем, как создается ключ.</span><span class="sxs-lookup"><span data-stu-id="086d8-239">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="086d8-240">Используйте ключи RSA.</span><span class="sxs-lookup"><span data-stu-id="086d8-240">Use the RSA keys.</span></span> <span data-ttu-id="086d8-241">Хранилище Azure Key Vault не поддерживает перенос и развёртывание с помощью ключей эллиптических кривых.</span><span class="sxs-lookup"><span data-stu-id="086d8-241">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="086d8-242">Чтобы создать ключ непосредственно в хранилище [](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) ключей, выполните его следующим образом:</span><span class="sxs-lookup"><span data-stu-id="086d8-242">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="086d8-243">Где:</span><span class="sxs-lookup"><span data-stu-id="086d8-243">Where:</span></span>

- <span data-ttu-id="086d8-244">*имя хранилища* — это имя хранилища ключей, в котором необходимо создать ключ.</span><span class="sxs-lookup"><span data-stu-id="086d8-244">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="086d8-245">*имя ключа* — это имя, которое вы хотите предоставить новому ключу.</span><span class="sxs-lookup"><span data-stu-id="086d8-245">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="086d8-246">Клавиши имен, использующие аналогичное соглашение об именовом имени, как описано выше, для хранилищ ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-246">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="086d8-247">Таким образом, в средствах, которые показывают только имя ключа, строка является самоо описанной.</span><span class="sxs-lookup"><span data-stu-id="086d8-247">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="086d8-248">Если вы собираетесь защитить ключ с помощью HSM, убедитесь, что в качестве значения параметра _Destination_ указывается **HSM,** в противном случае укажите **Программное обеспечение.**</span><span class="sxs-lookup"><span data-stu-id="086d8-248">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="086d8-249">Пример.</span><span class="sxs-lookup"><span data-stu-id="086d8-249">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="086d8-250">Проверка уровня восстановления ключей</span><span class="sxs-lookup"><span data-stu-id="086d8-250">Check the recovery level of your keys</span></span>

<span data-ttu-id="086d8-251">Microsoft 365 требует, чтобы для подписки Azure Key Vault было установлено значение "Не отменять" и что для ключей, используемых ключом клиента, включено мягкое удаление.</span><span class="sxs-lookup"><span data-stu-id="086d8-251">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="086d8-252">Вы можете подтвердить это, изусмотрив уровень восстановления на ключах.</span><span class="sxs-lookup"><span data-stu-id="086d8-252">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="086d8-253">Чтобы проверить уровень восстановления ключа, в Azure PowerShell выполните Get-AzKeyVaultKey следующим образом:</span><span class="sxs-lookup"><span data-stu-id="086d8-253">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="086d8-254">Если свойство _уровня_ восстановления возвращает что-либо, кроме значения **Recoverable+ProtectedSubscription,** необходимо просмотреть эту статью и убедиться, что вы следовали всем шагам, чтобы поместить подписку в список "Не отменять" и что включено "мягкое удаление" в каждом хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-254">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="086d8-255">Затем отправьте снимок экрана с выводом сообщения `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` электронной почты m365ck@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="086d8-255">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="086d8-256">Back up Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="086d8-256">Back up Azure Key Vault</span></span>

<span data-ttu-id="086d8-257">Сразу после создания или изменения ключа выполните резервное копирование и хранение копий резервного копирования как в сети, так и в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="086d8-257">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="086d8-258">Не подключайте автономные копии к какой-либо сети.</span><span class="sxs-lookup"><span data-stu-id="086d8-258">Don't connect offline copies to any network.</span></span> <span data-ttu-id="086d8-259">Вместо этого храните их в физическом безопасном или коммерческом хранилище.</span><span class="sxs-lookup"><span data-stu-id="086d8-259">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="086d8-260">По крайней мере одна копия резервной копии должна храниться в расположении, которое будет доступно в случае аварии.</span><span class="sxs-lookup"><span data-stu-id="086d8-260">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="086d8-261">Резервные BLOB-ели являются единственным средством восстановления материала ключа, если ключ Key Vault будет окончательно уничтожен или иным образом отрисовке неанимательным.</span><span class="sxs-lookup"><span data-stu-id="086d8-261">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="086d8-262">Ключи, которые являются внешними по внешнему хранилищу Azure Key Vault и были импортироваться в Azure Key Vault, не являются резервными, так как метаданные, необходимые для использования ключа клиента, не существуют с внешним ключом.</span><span class="sxs-lookup"><span data-stu-id="086d8-262">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="086d8-263">Для операций восстановления с помощью ключа клиента можно использовать только резервную копию, взятую из хранилища Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="086d8-263">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="086d8-264">Поэтому важно создать резервную копию хранилища Azure Key Vault после отправки или создания ключа.</span><span class="sxs-lookup"><span data-stu-id="086d8-264">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="086d8-265">Чтобы создать резервную копию ключа Azure Key Vault, выполните его с использованием резервного копирования [AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="086d8-265">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="086d8-266">Убедитесь, что выходной файл использует `.backup` суффикс.</span><span class="sxs-lookup"><span data-stu-id="086d8-266">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="086d8-267">Выходной файл, который является результатом этого cmdlet, шифруется и не может использоваться за пределами хранилища Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="086d8-267">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="086d8-268">Резервную копию можно восстановить только в подписке Azure, из которой была сделана резервная копия.</span><span class="sxs-lookup"><span data-stu-id="086d8-268">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="086d8-269">Пример:</span><span class="sxs-lookup"><span data-stu-id="086d8-269">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="086d8-270">Проверка параметров конфигурации Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="086d8-270">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="086d8-271">Выполнение проверки перед использованием ключей в DEP является необязательным, но настоятельно рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="086d8-271">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="086d8-272">В частности, при использовании действий по настройке ключей и хранилищ, не описанных в этом разделе, необходимо проверить состояние ресурсов Azure Key Vault перед настройкой ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-272">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="086d8-273">Чтобы убедиться, что для ваших ключей включены операции get, wrapKey и unwrapKey:</span><span class="sxs-lookup"><span data-stu-id="086d8-273">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="086d8-274">Запустите [cmdlet Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="086d8-274">Run the [Get-AzKeyVault](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="086d8-275">В выходных данных найди политику доступа и соответствующий guID приложения Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="086d8-275">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="086d8-276">Все три операции, get, wrapKey и unwrapKey, должны быть показаны в области "Разрешения для ключей".</span><span class="sxs-lookup"><span data-stu-id="086d8-276">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="086d8-277">Если конфигурация политики доступа неправильная, выполните Set-AzKeyVaultAccessPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="086d8-277">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="086d8-278">Пример. Для службы шифрования данных Microsoft 365 в rest замените  *appID Microsoft 365* на `c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="086d8-278">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="086d8-279">Чтобы убедиться, что дата окончания срока действия ключей не установлена, выполните cmdlet [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="086d8-279">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="086d8-280">Ключ клиента не может использовать ключ клиента с истекшим сроком действия, что может привести к сбойу службы.</span><span class="sxs-lookup"><span data-stu-id="086d8-280">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="086d8-281">Настоятельно рекомендуется, чтобы у ключей, используемых с ключом клиента, не было даты окончания срока действия.</span><span class="sxs-lookup"><span data-stu-id="086d8-281">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="086d8-282">Установленную дату окончания срока действия невозможно удалить, но ее можно изменить на другую дату.</span><span class="sxs-lookup"><span data-stu-id="086d8-282">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="086d8-283">Если необходимо использовать ключ с установленным сроком действия, измените значение срока действия на 31.01.9999.</span><span class="sxs-lookup"><span data-stu-id="086d8-283">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="086d8-284">Ключи с датой окончания срока действия, задав не более 31.01.9999, не проходят проверку Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="086d8-284">Keys with an expiration date set to a date other than 12/31/9999 will not pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="086d8-285">Чтобы изменить дату окончания срока действия, которая была установлена на любое значение, кроме 31.01.9999, выполните этот запуск следующим образом: [](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey)</span><span class="sxs-lookup"><span data-stu-id="086d8-285">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](https://docs.microsoft.com/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="086d8-286">Получение URI для каждого ключа Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="086d8-286">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="086d8-287">После завершения всех действий в Azure по настройкам хранилищ ключей и добавлению ключей, запустите следующую команду, чтобы получить URI для ключа в каждом хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-287">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="086d8-288">Эти ЮРИС потребуется использовать при создании и назначении каждого DEP позже, поэтому сохраните эти сведения в надежном месте.</span><span class="sxs-lookup"><span data-stu-id="086d8-288">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="086d8-289">Не забудьте выполнить эту команду один раз для каждого хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="086d8-289">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="086d8-290">В Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="086d8-290">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="086d8-291">Настройка политики шифрования ключа клиента для клиента</span><span class="sxs-lookup"><span data-stu-id="086d8-291">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="086d8-292">Для запуска этих cmdlets необходимы соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="086d8-292">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="086d8-293">Хотя в этой статье перечислены все параметры для этих параметров, некоторые параметры могут быть не доступны, если они не включены в соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="086d8-293">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="086d8-294">Сведения о необходимых разрешениях для запуска командлетов и использования параметров в организации см. в статье [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span><span class="sxs-lookup"><span data-stu-id="086d8-294">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](https://docs.microsoft.com/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="086d8-295">Создание политики</span><span class="sxs-lookup"><span data-stu-id="086d8-295">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>] [-Enabled <Boolean>]
```

<span data-ttu-id="086d8-296">Описание: в этом случае администратор соответствия требованиям может создать новую политику шифрования данных (DEP) с помощью двух корневых ключей AKV.</span><span class="sxs-lookup"><span data-stu-id="086d8-296">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="086d8-297">После создания политика может быть назначена с помощью Set-M365DataAtRestEncryptionPolicy управления.</span><span class="sxs-lookup"><span data-stu-id="086d8-297">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicy cmdlet.</span></span> <span data-ttu-id="086d8-298">После первого назначения ключей или после вращения клавиш может занять до 24 часов, чтобы новые ключи вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="086d8-298">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="086d8-299">Если новый DEP вступает в силу более 24 часов, обратитесь в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="086d8-299">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="086d8-300">Пример:</span><span class="sxs-lookup"><span data-stu-id="086d8-300">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="086d8-301">Параметры:</span><span class="sxs-lookup"><span data-stu-id="086d8-301">Parameters:</span></span>

| <span data-ttu-id="086d8-302">Имя</span><span class="sxs-lookup"><span data-stu-id="086d8-302">Name</span></span> | <span data-ttu-id="086d8-303">Описание</span><span class="sxs-lookup"><span data-stu-id="086d8-303">Description</span></span> | <span data-ttu-id="086d8-304">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="086d8-304">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="086d8-305">Имя</span><span class="sxs-lookup"><span data-stu-id="086d8-305">Name</span></span>|<span data-ttu-id="086d8-306">Удобное имя политики шифрования данных</span><span class="sxs-lookup"><span data-stu-id="086d8-306">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="086d8-307">N</span><span class="sxs-lookup"><span data-stu-id="086d8-307">N</span></span>|
|<span data-ttu-id="086d8-308">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="086d8-308">AzureKeyIDs</span></span>|<span data-ttu-id="086d8-309">Указывает два значения URI ключей хранилища ключей Azure, разделенных запятой, для связи с политикой шифрования данных</span><span class="sxs-lookup"><span data-stu-id="086d8-309">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="086d8-310">N</span><span class="sxs-lookup"><span data-stu-id="086d8-310">N</span></span>|
|<span data-ttu-id="086d8-311">Описание</span><span class="sxs-lookup"><span data-stu-id="086d8-311">Description</span></span>|<span data-ttu-id="086d8-312">Описание политики шифрования данных</span><span class="sxs-lookup"><span data-stu-id="086d8-312">Description of the data encryption policy</span></span>|<span data-ttu-id="086d8-313">N</span><span class="sxs-lookup"><span data-stu-id="086d8-313">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="086d8-314">Назначение политики</span><span class="sxs-lookup"><span data-stu-id="086d8-314">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “<Default_PolicyName or Default_PolicyID>”
```

<span data-ttu-id="086d8-315">Описание: этот cmdlet используется для настройки политики шифрования данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="086d8-315">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="086d8-316">Эта политика будет использоваться для шифрования данных во всех рабочих нагрузках поддержки.</span><span class="sxs-lookup"><span data-stu-id="086d8-316">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="086d8-317">Пример:</span><span class="sxs-lookup"><span data-stu-id="086d8-317">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -Policy “Tenant default policy”
```

<span data-ttu-id="086d8-318">Параметры:</span><span class="sxs-lookup"><span data-stu-id="086d8-318">Parameters:</span></span>
| <span data-ttu-id="086d8-319">Имя</span><span class="sxs-lookup"><span data-stu-id="086d8-319">Name</span></span> | <span data-ttu-id="086d8-320">Описание</span><span class="sxs-lookup"><span data-stu-id="086d8-320">Description</span></span> | <span data-ttu-id="086d8-321">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="086d8-321">Optional (Y/N)</span></span> |
|--|--|--|
<span data-ttu-id="086d8-322">-Policy</span><span class="sxs-lookup"><span data-stu-id="086d8-322">-Policy</span></span>|<span data-ttu-id="086d8-323">Указывает политику шифрования данных, которую необходимо на назначенное; укажите имя политики или ИД политики.</span><span class="sxs-lookup"><span data-stu-id="086d8-323">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="086d8-324">N</span><span class="sxs-lookup"><span data-stu-id="086d8-324">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="086d8-325">Изменение или обновление политики</span><span class="sxs-lookup"><span data-stu-id="086d8-325">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="086d8-326">Описание: этот cmdlet можно использовать для изменения или обновления существующей политики.</span><span class="sxs-lookup"><span data-stu-id="086d8-326">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="086d8-327">Его также можно использовать для включаемой или отключенной политики.</span><span class="sxs-lookup"><span data-stu-id="086d8-327">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="086d8-328">После первого назначения ключей или после поворота клавиш может занять до 24 часов, чтобы новые ключи вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="086d8-328">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="086d8-329">Если новый DEP вступает в силу более 24 часов, обратитесь в корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="086d8-329">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="086d8-330">Примеры:</span><span class="sxs-lookup"><span data-stu-id="086d8-330">Examples:</span></span>

<span data-ttu-id="086d8-331">Отключать политику шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-331">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="086d8-332">Обновите политику шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-332">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity “EUR Policy” -Refresh
```

<span data-ttu-id="086d8-333">Параметры:</span><span class="sxs-lookup"><span data-stu-id="086d8-333">Parameters:</span></span>
| <span data-ttu-id="086d8-334">Имя</span><span class="sxs-lookup"><span data-stu-id="086d8-334">Name</span></span> | <span data-ttu-id="086d8-335">Описание</span><span class="sxs-lookup"><span data-stu-id="086d8-335">Description</span></span> | <span data-ttu-id="086d8-336">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="086d8-336">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="086d8-337">-Identity</span><span class="sxs-lookup"><span data-stu-id="086d8-337">-Identity</span></span>|<span data-ttu-id="086d8-338">Указывает политику шифрования данных, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="086d8-338">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="086d8-339">N</span><span class="sxs-lookup"><span data-stu-id="086d8-339">N</span></span>|
|<span data-ttu-id="086d8-340">-Refresh</span><span class="sxs-lookup"><span data-stu-id="086d8-340">-Refresh</span></span>|<span data-ttu-id="086d8-341">Используйте переключатель Refresh для обновления политики шифрования данных после поворота любых связанных ключей в хранилище Azure Key Vault.</span><span class="sxs-lookup"><span data-stu-id="086d8-341">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="086d8-342">С этим параметром не нужно указывать значение.</span><span class="sxs-lookup"><span data-stu-id="086d8-342">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="086d8-343">Да</span><span class="sxs-lookup"><span data-stu-id="086d8-343">Y</span></span>|
|<span data-ttu-id="086d8-344">-Enabled</span><span class="sxs-lookup"><span data-stu-id="086d8-344">-Enabled</span></span>|<span data-ttu-id="086d8-345">Параметр Enabled включает или отключать политику шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-345">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="086d8-346">Перед отключением политики необходимо отоименовать ее от клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-346">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="086d8-347">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="086d8-347">Valid values are:</span></span></br > <span data-ttu-id="086d8-348">$true: политика включена</span><span class="sxs-lookup"><span data-stu-id="086d8-348">$true: The policy is enabled</span></span></br > <span data-ttu-id="086d8-349">$true. Политика включена. Это значение задается по умолчанию.
</span><span class="sxs-lookup"><span data-stu-id="086d8-349">$false: The policy is disabled.</span></span>|<span data-ttu-id="086d8-350">Да</span><span class="sxs-lookup"><span data-stu-id="086d8-350">Y</span></span>|
|<span data-ttu-id="086d8-351">-Name</span><span class="sxs-lookup"><span data-stu-id="086d8-351">-Name</span></span>|<span data-ttu-id="086d8-352">Параметр Name задает уникальное имя политики шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-352">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="086d8-353">Да</span><span class="sxs-lookup"><span data-stu-id="086d8-353">Y</span></span>
|<span data-ttu-id="086d8-354">-Description</span><span class="sxs-lookup"><span data-stu-id="086d8-354">-Description</span></span>|<span data-ttu-id="086d8-355">Параметр Description задает необязательное описание политики шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-355">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="086d8-356">Да</span><span class="sxs-lookup"><span data-stu-id="086d8-356">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="086d8-357">Получить сведения о политике</span><span class="sxs-lookup"><span data-stu-id="086d8-357">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] < M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="086d8-358">Описание: этот cmdlet перечисляет все политики шифрования M365DataAtRest, созданные для клиента, или сведения о конкретной политике.</span><span class="sxs-lookup"><span data-stu-id="086d8-358">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="086d8-359">Примеры:</span><span class="sxs-lookup"><span data-stu-id="086d8-359">Examples:</span></span>

<span data-ttu-id="086d8-360">В этом примере возвращается сводный список политик шифрования M365DatRest в организации.</span><span class="sxs-lookup"><span data-stu-id="086d8-360">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="086d8-361">В этом примере возвращаются подробные сведения о политике шифрования данных с именем "Политика NAM".</span><span class="sxs-lookup"><span data-stu-id="086d8-361">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="086d8-362">Параметры:</span><span class="sxs-lookup"><span data-stu-id="086d8-362">Parameters:</span></span>

| <span data-ttu-id="086d8-363">Имя</span><span class="sxs-lookup"><span data-stu-id="086d8-363">Name</span></span> | <span data-ttu-id="086d8-364">Описание</span><span class="sxs-lookup"><span data-stu-id="086d8-364">Description</span></span> | <span data-ttu-id="086d8-365">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="086d8-365">Optional (Y/N)</span></span> |
|--|--|--|
|<span data-ttu-id="086d8-366">-Identity</span><span class="sxs-lookup"><span data-stu-id="086d8-366">-Identity</span></span>|<span data-ttu-id="086d8-367">Указывает политику шифрования данных, сведения о которую необходимо у вас получить.</span><span class="sxs-lookup"><span data-stu-id="086d8-367">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="086d8-368">Да</span><span class="sxs-lookup"><span data-stu-id="086d8-368">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="086d8-369">Получить сведения о назначении политики</span><span class="sxs-lookup"><span data-stu-id="086d8-369">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="086d8-370">Описание: этот cmdlet перечисляет политику, которая в настоящее время назначена для клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-370">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="086d8-371">Отключение ключа клиента</span><span class="sxs-lookup"><span data-stu-id="086d8-371">Offboarding from Customer Key</span></span>

<span data-ttu-id="086d8-372">Если вам нужно вернуться к ключам, управляемым Майкрософт, вы можете.</span><span class="sxs-lookup"><span data-stu-id="086d8-372">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="086d8-373">При отключении ваши данные повторно шифруются с использованием шифрования по умолчанию, поддерживаемого каждой отдельной рабочей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="086d8-373">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="086d8-374">Например, Exchange Online поддерживает шифрование по умолчанию с помощью ключей, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="086d8-374">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="086d8-375">Если вы решили отключить клиент от ключа клиента на уровне клиента, отправьте корпорации Майкрософт запрос по электронной почте, чтобы "отключить" службу для клиента по [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="086d8-375">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to “disable” the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="086d8-376">Отключение — это не то же самое, что очистка данных.</span><span class="sxs-lookup"><span data-stu-id="086d8-376">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="086d8-377">При очистке данных окончательно криптографическая очистка удаляет данные вашей организации из Microsoft 365, отключение не происходит.</span><span class="sxs-lookup"><span data-stu-id="086d8-377">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="086d8-378">Вы не можете выполнить очистку данных для политики на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="086d8-378">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="086d8-379">Сведения о пути очистки данных см. в переочистке ключей и начале процесса [очистки данных.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)</span><span class="sxs-lookup"><span data-stu-id="086d8-379">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="086d8-380">О ключе доступности</span><span class="sxs-lookup"><span data-stu-id="086d8-380">About the availability key</span></span>

<span data-ttu-id="086d8-381">Сведения о ключе доступности см. в сведениях [о ключе доступности.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="086d8-381">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="086d8-382">Поворот клавиш</span><span class="sxs-lookup"><span data-stu-id="086d8-382">Key rotation</span></span>

<span data-ttu-id="086d8-383">Сведения о вращении или вращении ключей, используемых с ключом клиента, см. в подкатеголи или повороте ключа клиента или [ключа доступности.](customer-key-availability-key-roll.md)</span><span class="sxs-lookup"><span data-stu-id="086d8-383">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="086d8-384">При обновлении DEP для использования новой версии ключей будет запускаться Set-M365DataAtRestEncryptionPolicy, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="086d8-384">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="086d8-385">Связанные статьи:</span><span class="sxs-lookup"><span data-stu-id="086d8-385">Related articles:</span></span>

- [<span data-ttu-id="086d8-386">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="086d8-386">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="086d8-387">Смена или ротация ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="086d8-387">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="086d8-388">Узнайте о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="086d8-388">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="086d8-389">Шифрование службы</span><span class="sxs-lookup"><span data-stu-id="086d8-389">Service Encryption</span></span>](office-365-service-encryption.md)
