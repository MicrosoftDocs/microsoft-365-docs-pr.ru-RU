---
title: Ключ клиента для Microsoft 365 на уровне клиента (общедоступная предварительная версия)
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 2/17/2021
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
ms.openlocfilehash: f50986b4e72808d4a1cd4dc8ee0182eb9c0a2455
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922693"
---
# <a name="overview-of-customer-key-for-microsoft-365-at-the-tenant-level-public-preview"></a><span data-ttu-id="450b2-103">Обзор ключа клиента для Microsoft 365 на уровне клиента (общедоступный предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="450b2-103">Overview of Customer Key for Microsoft 365 at the tenant level (public preview)</span></span>

<span data-ttu-id="450b2-104">Используя ключи, которые вы предоставляете, можно создать политику шифрования данных (DEP) и назначить ее клиенту.</span><span class="sxs-lookup"><span data-stu-id="450b2-104">Using keys you provide, you can create a data encryption policy (DEP) and assign it to the tenant.</span></span> <span data-ttu-id="450b2-105">DeP шифрует данные в клиенте для этих рабочих нагрузок:</span><span class="sxs-lookup"><span data-stu-id="450b2-105">The DEP encrypts data across the tenant for these workloads:</span></span>

- <span data-ttu-id="450b2-106">Командные сообщения чата (1:1 чаты, групповые чаты, чаты собраний и беседы на канале)</span><span class="sxs-lookup"><span data-stu-id="450b2-106">Teams chat messages (1:1 chats, group chats, meeting chats and channel conversations)</span></span>
- <span data-ttu-id="450b2-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span><span class="sxs-lookup"><span data-stu-id="450b2-107">Teams media messages (images, code snippets, video messages, audio messages, wiki images)</span></span>
- <span data-ttu-id="450b2-108">Записи вызовов и собраний teams, хранимые в хранилище Teams</span><span class="sxs-lookup"><span data-stu-id="450b2-108">Teams call and meeting recordings stored in Teams storage</span></span>
- <span data-ttu-id="450b2-109">Уведомления чата teams</span><span class="sxs-lookup"><span data-stu-id="450b2-109">Teams chat notifications</span></span>
- <span data-ttu-id="450b2-110">Предложения чата teams от Cortana</span><span class="sxs-lookup"><span data-stu-id="450b2-110">Teams chat suggestions by Cortana</span></span>
- <span data-ttu-id="450b2-111">Сообщения о состоянии команд</span><span class="sxs-lookup"><span data-stu-id="450b2-111">Teams status messages</span></span>
- <span data-ttu-id="450b2-112">Сведения о пользователях и сигналах для Exchange Online</span><span class="sxs-lookup"><span data-stu-id="450b2-112">User and signal information for Exchange Online</span></span>
- <span data-ttu-id="450b2-113">Почтовые ящики Exchange Online, которые еще не зашифрованы dePs ключа клиента на уровне приложения</span><span class="sxs-lookup"><span data-stu-id="450b2-113">Exchange Online mailboxes that aren't already encrypted Customer Key DEPs at the application level</span></span>

<span data-ttu-id="450b2-114">Для Microsoft Teams ключ клиента на уровне клиента шифрует новые данные с того времени, как deP назначен клиенту.</span><span class="sxs-lookup"><span data-stu-id="450b2-114">For Microsoft Teams, Customer Key at the tenant level encrypts new data from the time the DEP is assigned to the tenant.</span></span> <span data-ttu-id="450b2-115">Общедоступный предварительный просмотр не поддерживает шифрование прошлых данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-115">Public preview does not support encrypting past data.</span></span> <span data-ttu-id="450b2-116">Для Exchange Online ключ клиента шифрует все существующие и новые данные.</span><span class="sxs-lookup"><span data-stu-id="450b2-116">For Exchange Online, Customer Key encrypts all existing and new data.</span></span>

<span data-ttu-id="450b2-117">Можно создать несколько DEP на клиента, но в любой момент можно назначить только один deP.</span><span class="sxs-lookup"><span data-stu-id="450b2-117">You can create multiple DEPs per tenant but can only assign one DEP at any point in time.</span></span> <span data-ttu-id="450b2-118">При назначении deP шифрование начинается автоматически, но может занять некоторое время в зависимости от размера клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-118">When you assign the DEP, encryption begins automatically but can take some time to complete depending on the size of your tenant.</span></span>

## <a name="tenant-level-policies-add-broader-control-to-customer-key-for-microsoft-365"></a><span data-ttu-id="450b2-119">Политики уровня клиента добавляют более широкий контроль в ключ клиента для Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="450b2-119">Tenant level policies add broader control to Customer Key for Microsoft 365</span></span>

<span data-ttu-id="450b2-120">Если у вас уже есть клиентский ключ для Exchange Online и Sharepoint Online, вот как вписывается новый общедоступный предварительный просмотр на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-120">If you already have Customer Key set up for Exchange Online and Sharepoint Online, here's how the new tenant-level public preview fits in.</span></span>

<span data-ttu-id="450b2-121">Политика шифрования на уровне клиента, которая создается, шифрует все данные для рабочих нагрузок Microsoft Teams и Exchange Online в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="450b2-121">The tenant-level encryption policy you create encrypts all data for the Microsoft Teams and Exchange Online workloads in Microsoft 365.</span></span> <span data-ttu-id="450b2-122">Однако для Exchange Online, если для отдельных почтовых ящиков уже назначены DEP-адреса ключей клиента, политика уровня клиента не переопределит эти dePs.</span><span class="sxs-lookup"><span data-stu-id="450b2-122">However, for Exchange Online, if you have already assigned Customer Key DEPs to individual mailboxes, the tenant-level policy won't override those DEPs.</span></span> <span data-ttu-id="450b2-123">Политика уровня клиента шифрует только почтовые ящики, которые уже не назначены deP клиентского ключа уровня почтовых ящиков.</span><span class="sxs-lookup"><span data-stu-id="450b2-123">The tenant-level policy will only encrypt mailboxes that aren't assigned a mailbox level Customer Key DEP already.</span></span>

<span data-ttu-id="450b2-124">Например, файлы Microsoft Teams и некоторые записи вызовов и собраний Teams, сохраненные в OneDrive для бизнеса и SharePoint, шифруются deP SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="450b2-124">For example, Microsoft Teams files and some Teams call and meeting recordings that are saved in OneDrive for Business and SharePoint are encrypted by a SharePoint Online DEP.</span></span> <span data-ttu-id="450b2-125">Один DEP SharePoint Online шифрует контент в одном гео.</span><span class="sxs-lookup"><span data-stu-id="450b2-125">A single SharePoint Online DEP encrypts content within a single geo.</span></span>

## <a name="set-up-customer-key-at-the-tenant-level-public-preview"></a><span data-ttu-id="450b2-126">Настройка ключа клиента на уровне клиента (общедоступный предварительный просмотр)</span><span class="sxs-lookup"><span data-stu-id="450b2-126">Set up Customer Key at the tenant level (public preview)</span></span>

<span data-ttu-id="450b2-127">Эти действия аналогичны, но не совпадают с действиями по настройке клиентского ключа на уровне приложения.</span><span class="sxs-lookup"><span data-stu-id="450b2-127">These steps are similar but not identical to the steps for setting up Customer Key at the application level.</span></span> <span data-ttu-id="450b2-128">Этот общедоступный предварительный просмотр следует использовать только с тест-данными в тестовых клиентах.</span><span class="sxs-lookup"><span data-stu-id="450b2-128">You should only use this public preview with test data in test tenants.</span></span> <span data-ttu-id="450b2-129">Не используйте этот выпуск с производственными данными или в производственной среде.</span><span class="sxs-lookup"><span data-stu-id="450b2-129">Do not use this release with production data or in your production environment.</span></span> <span data-ttu-id="450b2-130">Если у вас уже есть производственное развертывание клиентского ключа, используйте эти действия, чтобы настроить клиентский ключ на уровне клиента в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="450b2-130">If you already have a production deployment of Customer Key, use these steps to set up Customer Key at the tenant level in a test environment.</span></span> <span data-ttu-id="450b2-131">После присвоения клиенту deP уровня клиента вы можете начать процесс проверки и связаться с m365ck@microsoft.com вопросами или вопросами.</span><span class="sxs-lookup"><span data-stu-id="450b2-131">Once you have assigned a tenant level DEP to your tenant, you can start the validation process and reach out to m365ck@microsoft.com with any questions or concerns.</span></span> <span data-ttu-id="450b2-132">Вы также можете найти документированные шаги проверки в общедоступный предварительный просмотр инструкций проверки для шифрования данных на отдыхе [для Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation).</span><span class="sxs-lookup"><span data-stu-id="450b2-132">You can also find documented validation steps in the public preview of [Validation Instructions for Data-at-rest Encryption for Microsoft 365](https://aka.ms/CustomerKey/PublicPreviewValidation).</span></span>

<span data-ttu-id="450b2-133">Большинство этих задач можно выполнить, удаленно подключившись к Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="450b2-133">You'll complete most of these tasks by remotely connecting to Azure PowerShell.</span></span> <span data-ttu-id="450b2-134">Для наилучших результатов используйте версию 4.4.0 или более поздней версии Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="450b2-134">For best results, use version 4.4.0 or later of Azure PowerShell.</span></span>

<span data-ttu-id="450b2-135">Перед началом работы убедитесь в следующем:</span><span class="sxs-lookup"><span data-stu-id="450b2-135">Before you get started, make sure of the following:</span></span>

- <span data-ttu-id="450b2-136">Чтобы настроить клиентский ключ на уровне клиента, необходимо использовать учетную запись для работы или учебной учетной записи, которая имеет роль администратора соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="450b2-136">You'll need to use a work or school account that has the compliance admin role to set up Customer Key at the tenant level.</span></span>
- <span data-ttu-id="450b2-137">Убедитесь, что у вас есть соответствующее лицензирование для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="450b2-137">Ensure that you have the appropriate licensing for your organization.</span></span> <span data-ttu-id="450b2-138">Используйте платную подписку Azure с Соглашение Enterprise или поставщика облачных служб.</span><span class="sxs-lookup"><span data-stu-id="450b2-138">Use a paid, invoiced Azure Subscription using either an Enterprise Agreement or a Cloud Service Provider.</span></span> <span data-ttu-id="450b2-139">Подписки Azure, приобретенные с помощью планов Pay As You Go или с помощью кредитной карты, не поддерживаются для ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-139">Azure Subscriptions purchased using Pay As You Go plans or using a credit card aren't supported for Customer Key.</span></span> <span data-ttu-id="450b2-140">С 1 апреля 2020 г. ключ клиента в Office 365 предлагается в Office 365 E5, M365 E5, M365 E5 Compliance и M365 E5 Information Protection & Governance SKUs.</span><span class="sxs-lookup"><span data-stu-id="450b2-140">Starting April 1, 2020, Customer Key in Office 365 is offered in Office 365 E5, M365 E5, M365 E5 Compliance, and M365 E5 Information Protection & Governance SKUs.</span></span> <span data-ttu-id="450b2-141">Office 365 Advanced Compliance SKU больше не доступен для получения новых лицензий.</span><span class="sxs-lookup"><span data-stu-id="450b2-141">Office 365 Advanced Compliance SKU is no longer available for procuring new licenses.</span></span> <span data-ttu-id="450b2-142">Существующие лицензии на расширенный соответствие Office 365 будут по-прежнему поддерживаться.</span><span class="sxs-lookup"><span data-stu-id="450b2-142">Existing Office 365 Advanced Compliance licenses will continue to be supported.</span></span> <span data-ttu-id="450b2-143">Хотя служба может быть включена с как минимум одной лицензией под клиентом, который имеет соответствующую лицензию, необходимо убедиться, что все пользователи, пользующиеся услугами службы, имеют соответствующие лицензии.</span><span class="sxs-lookup"><span data-stu-id="450b2-143">While the service can be enabled with a minimum of one license under the tenant having the appropriate license, you should still make sure all users that benefit from the service have appropriate licenses.</span></span>

### <a name="create-two-new-azure-subscriptions"></a><span data-ttu-id="450b2-144">Создание двух новых подписок Azure</span><span class="sxs-lookup"><span data-stu-id="450b2-144">Create two new Azure subscriptions</span></span>

<span data-ttu-id="450b2-145">Ключ клиента требует двух ключей для каждой политики шифрования данных (DEP).</span><span class="sxs-lookup"><span data-stu-id="450b2-145">Customer Key requires two keys for each data encryption policy (DEP).</span></span> <span data-ttu-id="450b2-146">Для этого необходимо создать две подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="450b2-146">To achieve this, you must create two Azure subscriptions.</span></span> <span data-ttu-id="450b2-147">В качестве наилучшей практики Корпорация Майкрософт рекомендует, чтобы отдельные члены организации настраивали один ключ в каждой подписке.</span><span class="sxs-lookup"><span data-stu-id="450b2-147">As a best practice, Microsoft recommends that you have separate members of your organization configure one key in each subscription.</span></span> <span data-ttu-id="450b2-148">Используйте эти подписки Azure только для администрирования ключей шифрования для Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="450b2-148">Only use these Azure subscriptions to administer encryption keys for Microsoft 365.</span></span> <span data-ttu-id="450b2-149">Это защищает организацию, если один из операторов случайно, намеренно или злонамеренно удаляет или иным образом неправильно передает ключи, за которые они несут ответственность.</span><span class="sxs-lookup"><span data-stu-id="450b2-149">This protects your organization in case one of your operators accidentally, intentionally, or maliciously deletes or otherwise mismanages the keys for which they are responsible.</span></span>

<span data-ttu-id="450b2-150">Практические ограничения на количество подписок Azure, которые можно создать для вашей организации, не ограничиваются.</span><span class="sxs-lookup"><span data-stu-id="450b2-150">There is no practical limit to the number of Azure subscriptions that you can create for your organization.</span></span> <span data-ttu-id="450b2-151">Следуя этой наилучшей практике, можно свести к минимуму влияние человеческой ошибки, помогая управлять ресурсами, используемыми клиентской клавишей.</span><span class="sxs-lookup"><span data-stu-id="450b2-151">Following this best practice helps minimize the impact of human error while helping to manage the resources used by Customer Key.</span></span>

### <a name="register-azure-subscriptions-to-use-a-mandatory-retention-period"></a><span data-ttu-id="450b2-152">Регистрация подписки Azure для использования обязательного периода хранения</span><span class="sxs-lookup"><span data-stu-id="450b2-152">Register Azure subscriptions to use a mandatory retention period</span></span>

<span data-ttu-id="450b2-153">Временная или постоянная потеря ключей корневого шифрования может привести к нарушению работы службы или даже к катастрофическим последствиям, что может привести к потере данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-153">The temporary or permanent loss of root encryption keys can be disruptive or even catastrophic to service operation and can result in data loss.</span></span> <span data-ttu-id="450b2-154">По этой причине ресурсы, используемые с ключом клиента, требуют сильной защиты.</span><span class="sxs-lookup"><span data-stu-id="450b2-154">For this reason, the resources used with Customer Key require strong protection.</span></span> <span data-ttu-id="450b2-155">Все ресурсы Azure, используемые с помощью ключа клиента, предлагают механизмы защиты за пределами конфигурации по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="450b2-155">All the Azure resources that are used with Customer Key offer protection mechanisms beyond the default configuration.</span></span> <span data-ttu-id="450b2-156">Подписки Azure могут быть помечены или зарегистрированы таким образом, чтобы предотвратить немедленную и невозвратную отмену.</span><span class="sxs-lookup"><span data-stu-id="450b2-156">Azure subscriptions can be tagged or registered in a way that will prevent immediate and irrevocable cancellation.</span></span> <span data-ttu-id="450b2-157">Это называется регистрацией на обязательный период хранения.</span><span class="sxs-lookup"><span data-stu-id="450b2-157">This is referred to as registering for a mandatory retention period.</span></span> <span data-ttu-id="450b2-158">Действия, необходимые для регистрации подписки Azure на обязательный период хранения, требуют совместной работы с Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="450b2-158">The steps required to register Azure subscriptions for a mandatory retention period require collaboration with the Microsoft.</span></span> <span data-ttu-id="450b2-159">Этот процесс может занять до пяти бизнес-дней.</span><span class="sxs-lookup"><span data-stu-id="450b2-159">This process can take up to five business days.</span></span> <span data-ttu-id="450b2-160">Ранее это иногда называлось "Не отменять".</span><span class="sxs-lookup"><span data-stu-id="450b2-160">Previously, this was sometimes referred to as "Do Not Cancel".</span></span>
  
<span data-ttu-id="450b2-161">Прежде чем связаться с командой Microsoft 365, необходимо выполнить следующие действия для каждой подписки Azure, используемой с помощью клиентского ключа.</span><span class="sxs-lookup"><span data-stu-id="450b2-161">Before contacting the Microsoft 365 team, you must perform the following steps for each Azure subscription that you use with Customer Key.</span></span> <span data-ttu-id="450b2-162">Убедитесь, что перед запуском установлен модуль [Azure PowerShell Az.](/powershell/azure/new-azureps-module-az)</span><span class="sxs-lookup"><span data-stu-id="450b2-162">Ensure that you have the [Azure PowerShell Az](/powershell/azure/new-azureps-module-az) module installed before you start.</span></span>

1. <span data-ttu-id="450b2-163">Во входе в Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="450b2-163">Sign in with Azure PowerShell.</span></span> <span data-ttu-id="450b2-164">Инструкции см. в [документе Вход с Azure PowerShell.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="450b2-164">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="450b2-165">Запустите Register-AzProviderFeature для регистрации подписок, чтобы использовать обязательный период хранения.</span><span class="sxs-lookup"><span data-stu-id="450b2-165">Run the Register-AzProviderFeature cmdlet to register your subscriptions to use a mandatory retention period.</span></span> <span data-ttu-id="450b2-166">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="450b2-166">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzProviderFeature -FeatureName mandatoryRetentionPeriodEnabled -ProviderNamespace Microsoft.Resources
   ```

3. <span data-ttu-id="450b2-167">Свяжитесь с Корпорацией Майкрософт, чтобы завершить процесс в [m365ck@microsoft.com.](mailto:m365ck@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="450b2-167">Contact Microsoft to have the process finalized at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span> <span data-ttu-id="450b2-168">Включите в электронную почту следующее:</span><span class="sxs-lookup"><span data-stu-id="450b2-168">Include the following in your email:</span></span>

   <span data-ttu-id="450b2-169">**Тема:** Ключ клиента для \<*Your tenant's fully-qualified domain name*\></span><span class="sxs-lookup"><span data-stu-id="450b2-169">**Subject**: Customer Key for \<*Your tenant's fully-qualified domain name*\></span></span>

   <span data-ttu-id="450b2-170">**Body:** Подписные ID, для которых необходимо завершить обязательный период хранения.</span><span class="sxs-lookup"><span data-stu-id="450b2-170">**Body**: Subscription IDs for which you want to have the mandatory retention period finalized.</span></span>
   <span data-ttu-id="450b2-171">Выход Get-AzProviderFeature для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="450b2-171">The output of Get-AzProviderFeature for each subscription.</span></span>

   <span data-ttu-id="450b2-172">Соглашение об уровне обслуживания (SLA) для завершения этого процесса составляет пять бизнес-дней после уведомления (и проверки) Корпорации Майкрософт о том, что вы зарегистрировали подписки для использования обязательного периода хранения.</span><span class="sxs-lookup"><span data-stu-id="450b2-172">The Service Level Agreement (SLA) for completion of this process is five business days once Microsoft has been notified (and verified) that you have registered your subscriptions to use a mandatory retention period.</span></span>

4. <span data-ttu-id="450b2-173">После получения уведомления от Корпорации Майкрософт о том, что регистрация завершена, проверьте состояние вашей регистрации, Get-AzProviderFeature команду следующим образом.</span><span class="sxs-lookup"><span data-stu-id="450b2-173">Once you receive notification from Microsoft that registration is complete, verify the status of your registration by running the Get-AzProviderFeature command as follows.</span></span> <span data-ttu-id="450b2-174">В случае проверки Get-AzProviderFeature возвращает значение **Registered** for the **Registration State** property.</span><span class="sxs-lookup"><span data-stu-id="450b2-174">If verified, the Get-AzProviderFeature command returns a value of **Registered** for the **Registration State** property.</span></span> <span data-ttu-id="450b2-175">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="450b2-175">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Get-AzProviderFeature -ProviderNamespace Microsoft.Resources -FeatureName mandatoryRetentionPeriodEnabled
   ```

5. <span data-ttu-id="450b2-176">Чтобы завершить процесс, выполните команду Register-AzResourceProvider.</span><span class="sxs-lookup"><span data-stu-id="450b2-176">To complete the process, run the Register-AzResourceProvider command.</span></span> <span data-ttu-id="450b2-177">Выполните это действие для каждой подписки.</span><span class="sxs-lookup"><span data-stu-id="450b2-177">Perform this action for each subscription.</span></span>

   ```powershell
   Set-AzContext -SubscriptionId <SubscriptionId>
   Register-AzResourceProvider -ProviderNamespace Microsoft.KeyVault
   ```

### <a name="create-a-premium-azure-key-vault-in-each-subscription"></a><span data-ttu-id="450b2-178">Создание хранилища ключей Azure премиум класса в каждой подписке</span><span class="sxs-lookup"><span data-stu-id="450b2-178">Create a premium Azure Key Vault in each subscription</span></span>

<span data-ttu-id="450b2-179">Действия по созданию хранилища ключей описаны в журнале [Getting Started with Azure Key Vault,](/azure/key-vault/general/overview)который поможет вам установить и запустить Azure PowerShell, подключиться к подписке Azure, создать группу ресурсов и создать хранилище ключей в этой группе ресурсов.</span><span class="sxs-lookup"><span data-stu-id="450b2-179">The steps to create a key vault are documented in [Getting Started with Azure Key Vault](/azure/key-vault/general/overview), which guides you through installing and launching Azure PowerShell, connecting to your Azure subscription, creating a resource group, and creating a key vault in that resource group.</span></span>
  
<span data-ttu-id="450b2-180">При создании хранилища ключей необходимо выбрать SKU: standard или Premium.</span><span class="sxs-lookup"><span data-stu-id="450b2-180">When you create a key vault, you must choose a SKU: either Standard or Premium.</span></span> <span data-ttu-id="450b2-181">Стандартный SKU позволяет защищать ключи хранилища ключей Azure с помощью программного обеспечения , не существует защиты ключей модуля безопасности оборудования (HSM), а SKU Premium позволяет использовать HSM для защиты ключей хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="450b2-181">The Standard SKU allows Azure Key Vault keys to be protected with software - there is no Hardware Security Module (HSM) key protection - and the Premium SKU allows the use of HSMs for protection of Key Vault keys.</span></span> <span data-ttu-id="450b2-182">Ключ клиента принимает ключевые хранилища, которые используют либо SKU, но Корпорация Майкрософт настоятельно рекомендует использовать только SKU Premium.</span><span class="sxs-lookup"><span data-stu-id="450b2-182">Customer Key accepts key vaults that use either SKU, though Microsoft strongly recommends that you use only the Premium SKU.</span></span> <span data-ttu-id="450b2-183">Стоимость операций с ключами обоих типов одна и та же, поэтому единственной разницей в стоимости является стоимость в месяц для каждого ключа, защищенного HSM.</span><span class="sxs-lookup"><span data-stu-id="450b2-183">The cost of operations with keys of either type is the same, so the only difference in cost is the cost per month for each HSM-protected key.</span></span> <span data-ttu-id="450b2-184">Подробные [сведения см. в расценки Key Vault.](https://azure.microsoft.com/pricing/details/key-vault/)</span><span class="sxs-lookup"><span data-stu-id="450b2-184">See [Key Vault pricing](https://azure.microsoft.com/pricing/details/key-vault/) for details.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="450b2-185">Используйте хранилища ключей Премиум SKU и защищенные HSM-ключи для производственных данных и используйте только хранилища и ключи ключей standard SKU для тестирования и проверки.</span><span class="sxs-lookup"><span data-stu-id="450b2-185">Use the Premium SKU key vaults and HSM-protected keys for production data, and only use Standard SKU key vaults and keys for testing and validation purposes.</span></span>

<span data-ttu-id="450b2-186">Используйте общий префикс для ключевых сводов и включаем аббревиатура использования и области ключей и свода ключей.</span><span class="sxs-lookup"><span data-stu-id="450b2-186">Use a common prefix for key vaults and include an abbreviation of the use and scope of the key vault and keys.</span></span> <span data-ttu-id="450b2-187">Например, для службы Contoso, где хранилища будут располагаться в Северной Америке, возможной парой имен являются Contoso-O365-NA-VaultA1 и Contoso-O365-NA-VaultA2.</span><span class="sxs-lookup"><span data-stu-id="450b2-187">For example, for the Contoso service where the vaults will be located in North America, a possible pair of names is Contoso-O365-NA-VaultA1 and Contoso-O365-NA-VaultA2.</span></span> <span data-ttu-id="450b2-188">Имена Vault — это уникальные строки в Azure, поэтому вам может потребоваться попробовать варианты желаемых имен, если нужные имена уже заявлены другими клиентами Azure.</span><span class="sxs-lookup"><span data-stu-id="450b2-188">Vault names are globally unique strings within Azure, so you may need to try variations of your desired names in case the desired names are already claimed by other Azure customers.</span></span> <span data-ttu-id="450b2-189">После настройки имена хранилища не могут быть изменены, поэтому лучше всего иметь письменный план установки и использовать второго человека для проверки правильного выполнения плана.</span><span class="sxs-lookup"><span data-stu-id="450b2-189">Once configured, vault names cannot be changed, so the best practice is to have a written plan for setup and use a second person to verify the plan is executed correctly.</span></span>

<span data-ttu-id="450b2-190">По возможности создайте хранилища в непарных регионах.</span><span class="sxs-lookup"><span data-stu-id="450b2-190">If possible, create your vaults in non-paired regions.</span></span> <span data-ttu-id="450b2-191">В парных регионах Azure обеспечивается высокая доступность для доменов сбоя службы.</span><span class="sxs-lookup"><span data-stu-id="450b2-191">Paired Azure regions provide high availability across service failure domains.</span></span> <span data-ttu-id="450b2-192">Поэтому региональные пары можно использовать как область резервного копирования друг друга.</span><span class="sxs-lookup"><span data-stu-id="450b2-192">Therefore, regional pairs can be thought of as each other's backup region.</span></span> <span data-ttu-id="450b2-193">Это означает, что ресурс Azure, размещенный в одном регионе, автоматически получает переносимость ошибок через спаривную область.</span><span class="sxs-lookup"><span data-stu-id="450b2-193">This means that an Azure resource that is placed in one region is automatically gaining fault tolerance through the paired region.</span></span> <span data-ttu-id="450b2-194">По этой причине выбор регионов для двух сводов, используемых в политике шифрования данных, где регионы сопряжены, означает, что используется только два региона доступности.</span><span class="sxs-lookup"><span data-stu-id="450b2-194">For this reason, choosing regions for two vaults used in a data encryption policy where the regions are paired means that only a total of two regions of availability are in use.</span></span> <span data-ttu-id="450b2-195">В большинстве географических регионов только два региона, поэтому выбрать непарные регионы пока невозможно.</span><span class="sxs-lookup"><span data-stu-id="450b2-195">Most geographies only have two regions, so it's not yet possible to select non-paired regions.</span></span> <span data-ttu-id="450b2-196">По возможности выберите два непарных региона для двух сводов, используемых с политикой шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-196">If possible, choose two non-paired regions for the two vaults used with a data encryption policy.</span></span> <span data-ttu-id="450b2-197">Это дает в общей сложности четыре региона доступности.</span><span class="sxs-lookup"><span data-stu-id="450b2-197">This benefits from a total of four regions of availability.</span></span> <span data-ttu-id="450b2-198">Дополнительные сведения см. в дополнительных сведениях о непрерывности бизнеса и аварийном восстановлении [(BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) для текущего списка региональных пар.</span><span class="sxs-lookup"><span data-stu-id="450b2-198">For more information, see [Business continuity and disaster recovery (BCDR): Azure Paired Regions](/azure/best-practices-availability-paired-regions) for a current list of regional pairs.</span></span>

### <a name="assign-permissions-to-each-key-vault"></a><span data-ttu-id="450b2-199">Назначение разрешений для каждого хранилища ключей</span><span class="sxs-lookup"><span data-stu-id="450b2-199">Assign permissions to each key vault</span></span>

<span data-ttu-id="450b2-200">Для каждого хранилища ключей необходимо определить три отдельных набора разрешений для ключа клиента в зависимости от вашей реализации.</span><span class="sxs-lookup"><span data-stu-id="450b2-200">For each key vault, you will need to define three separate sets of permissions for Customer Key, depending on your implementation.</span></span> <span data-ttu-id="450b2-201">Например, необходимо определить один набор разрешений для каждого из следующих ниже.</span><span class="sxs-lookup"><span data-stu-id="450b2-201">For example, you will need to define one set of permissions for each of the following:</span></span>
  
- <span data-ttu-id="450b2-202">**Администраторы ключей** хранилища, которые будут выполнять ежедневное управление вашим хранилищем ключей для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="450b2-202">**Key vault administrators** that will perform day-to-day management of your key vault for your organization.</span></span> <span data-ttu-id="450b2-203">Эти задачи включают резервное копирование, создание, получения, импорт, список и восстановление.</span><span class="sxs-lookup"><span data-stu-id="450b2-203">These tasks include backup, create, get, import, list, and restore.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="450b2-204">Набор разрешений, присвоенных администраторам ключей хранилища, не включает разрешение на удаление ключей.</span><span class="sxs-lookup"><span data-stu-id="450b2-204">The set of permissions assigned to key vault administrators does not include the permission to delete keys.</span></span> <span data-ttu-id="450b2-205">Это является преднамеренной и важной практикой.</span><span class="sxs-lookup"><span data-stu-id="450b2-205">This is intentional and an important practice.</span></span> <span data-ttu-id="450b2-206">Удаление ключей шифрования обычно не делается, так как это постоянно уничтожает данные.</span><span class="sxs-lookup"><span data-stu-id="450b2-206">Deleting encryption keys is not typically done, since doing so permanently destroys data.</span></span> <span data-ttu-id="450b2-207">В качестве наилучшей практики не предоставлять это разрешение администраторам хранилища по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="450b2-207">As a best practice, do not grant this permission to key vault administrators by default.</span></span> <span data-ttu-id="450b2-208">Вместо этого зарезервировать это для ключевых участников хранилища и назначить его администратору только на краткосрочной основе после четкого понимания последствий.</span><span class="sxs-lookup"><span data-stu-id="450b2-208">Instead, reserve this for key vault contributors and only assign it to an administrator on a short term basis once a clear understanding of the consequences is understood.</span></span>
  
  <span data-ttu-id="450b2-209">Чтобы назначить эти разрешения пользователю в организации, войдите в подписку Azure с помощью Azure PowerShell.</span><span class="sxs-lookup"><span data-stu-id="450b2-209">To assign these permissions to a user in your organization, log in to your Azure subscription with Azure PowerShell.</span></span> <span data-ttu-id="450b2-210">Инструкции см. в [документе Вход с Azure PowerShell.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="450b2-210">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

   <span data-ttu-id="450b2-211">Запустите Set-AzKeyVaultAccessPolicy, чтобы назначить необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="450b2-211">Run the Set-AzKeyVaultAccessPolicy cmdlet to assign the necessary permissions.</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -UserPrincipalName <UPN of user> -PermissionsToKeys create,import,list,get,backup,restore
   ```

   <span data-ttu-id="450b2-212">Пример:</span><span class="sxs-lookup"><span data-stu-id="450b2-212">For example:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -UserPrincipalName alice@contoso.com -PermissionsToKeys create,import,list,get,backup,restore
   ```

- <span data-ttu-id="450b2-213">**Ключевые вкладчики хранилища,** которые могут изменять разрешения в самом хранилище ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="450b2-213">**Key vault contributors** that can change permissions on the Azure Key Vault itself.</span></span> <span data-ttu-id="450b2-214">Вам потребуется изменить эти разрешения по мере того, как сотрудники покидают или присоединяются к вашей команде, или в редких ситуациях, когда администраторам ключей хранилища на законных основаниях требуется разрешение на удаление или восстановление ключа.</span><span class="sxs-lookup"><span data-stu-id="450b2-214">You'll need to change these permissions as employees leave or join your team, or in the rare situation that the key vault administrators legitimately need permission to delete or restore a key.</span></span> <span data-ttu-id="450b2-215">Этот набор ключевых участников хранилища должен быть предоставлен роль Contributor в вашем хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="450b2-215">This set of key vault contributors needs to be granted the Contributor role on your key vault.</span></span> <span data-ttu-id="450b2-216">Эту роль можно назначить с помощью Azure Resource Manager.</span><span class="sxs-lookup"><span data-stu-id="450b2-216">You can assign this role by using Azure Resource Manager.</span></span> <span data-ttu-id="450b2-217">Подробные действия см. в [Role-Based Управление](/azure/active-directory/role-based-access-control-configure) доступом для управления доступом к ресурсам подписки Azure.</span><span class="sxs-lookup"><span data-stu-id="450b2-217">For detailed steps, see [Use Role-Based Access Control](/azure/active-directory/role-based-access-control-configure) to manage access to your Azure subscription resources.</span></span> <span data-ttu-id="450b2-218">Администратор, создавший подписку, имеет этот доступ по умолчанию и возможность назначать другим администраторам роль Автора.</span><span class="sxs-lookup"><span data-stu-id="450b2-218">The administrator who creates a subscription has this access by default, and the ability to assign other administrators to the Contributor role.</span></span>

- <span data-ttu-id="450b2-219">**Данные Microsoft 365 в службе шифрования** покоя, которая работает с ключом клиента на уровне клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-219">**Microsoft 365 data at rest encryption service** that does the work of Customer Key at the tenant level.</span></span> <span data-ttu-id="450b2-220">Чтобы дать разрешение Microsoft 365, запустите кодлет **Set-AzKeyVaultAccessPolicy** с помощью следующего синтаксиса:</span><span class="sxs-lookup"><span data-stu-id="450b2-220">To give permission to Microsoft 365, run the **Set-AzKeyVaultAccessPolicy** cmdlet using the following syntax:</span></span>

   ```powershell
   Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
   ```

  <span data-ttu-id="450b2-221">Где:</span><span class="sxs-lookup"><span data-stu-id="450b2-221">Where:</span></span>

  - <span data-ttu-id="450b2-222">*имя хранилища* — это имя созданного хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="450b2-222">*vault name* is the name of the key vault you created.</span></span>

  <span data-ttu-id="450b2-223">Пример: Для службы шифрования данных Microsoft 365 замените *приложение Microsoft 365 на*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="450b2-223">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

### <a name="enable-and-then-confirm-soft-delete-on-your-key-vaults"></a><span data-ttu-id="450b2-224">Включить и затем подтвердить мягкое удаление в хранилищах ключей</span><span class="sxs-lookup"><span data-stu-id="450b2-224">Enable and then confirm soft delete on your key vaults</span></span>

<span data-ttu-id="450b2-225">При быстром восстановлении ключей вероятность отключения расширенной службы будет меньше из-за случайного или злонамеренного удаления ключей.</span><span class="sxs-lookup"><span data-stu-id="450b2-225">When you can quickly recover your keys, you are less likely to experience an extended service outage due to accidentally or maliciously deleted keys.</span></span> <span data-ttu-id="450b2-226">Включить эту конфигурацию, именуемую soft Delete, прежде чем использовать ключи с ключом клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-226">Enable this configuration, referred to as Soft Delete, before you can use your keys with Customer Key.</span></span> <span data-ttu-id="450b2-227">Включение soft Delete позволяет восстановить ключи или хранилища в течение 90 дней после удаления, не восстанавливая их из резервного копирования.</span><span class="sxs-lookup"><span data-stu-id="450b2-227">Enabling Soft Delete allows you to recover keys or vaults within 90 days of deletion without having to restore them from backup.</span></span>
  
<span data-ttu-id="450b2-228">Чтобы включить soft Delete в хранилищах ключей, выполните следующие действия:</span><span class="sxs-lookup"><span data-stu-id="450b2-228">To enable Soft Delete on your key vaults, complete these steps:</span></span>
  
1. <span data-ttu-id="450b2-229">Вопишите свою подписку Azure с помощью Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="450b2-229">Sign in to your Azure subscription with Windows PowerShell.</span></span> <span data-ttu-id="450b2-230">Инструкции см. в [документе Вход с Azure PowerShell.](/powershell/azure/authenticate-azureps)</span><span class="sxs-lookup"><span data-stu-id="450b2-230">For instructions, see [Sign in with Azure PowerShell](/powershell/azure/authenticate-azureps).</span></span>

2. <span data-ttu-id="450b2-231">Запустите [кодлет Get-AzKeyVault.](/powershell/module/az.keyvault/get-azkeyvault)</span><span class="sxs-lookup"><span data-stu-id="450b2-231">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet.</span></span> <span data-ttu-id="450b2-232">В этом примере *имя хранилища* — это имя хранилища ключей, для которого вы позволяете мягко удалять:</span><span class="sxs-lookup"><span data-stu-id="450b2-232">In this example, *vault name* is the name of the key vault for which you are enabling soft delete:</span></span>

   ```powershell
   $v = Get-AzKeyVault -VaultName <vault name>
   $r = Get-AzResource -ResourceId $v.ResourceId
   $r.Properties | Add-Member -MemberType NoteProperty -Name enableSoftDelete -Value 'True'
   Set-AzResource -ResourceId $r.ResourceId -Properties $r.Properties
   ```

3. <span data-ttu-id="450b2-233">Подтвердите, что мягкое удаление настроено для хранилища ключей с помощью **cmdlet Get-AzKeyVault.**</span><span class="sxs-lookup"><span data-stu-id="450b2-233">Confirm soft delete is configured for the key vault by running the **Get-AzKeyVault** cmdlet.</span></span> <span data-ttu-id="450b2-234">Если мягкое удаление настроено правильно для хранилища ключей, свойство _Soft Delete Enabled_ возвращает значение **True:**</span><span class="sxs-lookup"><span data-stu-id="450b2-234">If soft delete is configured properly for the key vault, then the _Soft Delete Enabled_ property returns a value of **True**:</span></span>

   ```powershell
   Get-AzKeyVault -VaultName <vault name> | fl
   ```

### <a name="add-a-key-to-each-key-vault-either-by-creating-or-importing-a-key"></a><span data-ttu-id="450b2-235">Добавление ключа в каждый хранилище ключей путем создания или импорта ключа</span><span class="sxs-lookup"><span data-stu-id="450b2-235">Add a key to each key vault either by creating or importing a key</span></span>

<span data-ttu-id="450b2-236">Существует два способа добавления ключей в хранилище ключей Azure; вы можете создать ключ непосредственно в Key Vault или импортировать ключ.</span><span class="sxs-lookup"><span data-stu-id="450b2-236">There are two ways to add keys to an Azure Key Vault; you can create a key directly in Key Vault, or you can import a key.</span></span> <span data-ttu-id="450b2-237">Создание ключа непосредственно в Key Vault — это менее сложный метод, а импорт ключа обеспечивает полный контроль над тем, как создается ключ.</span><span class="sxs-lookup"><span data-stu-id="450b2-237">Creating a key directly in Key Vault is the less complicated method, while importing a key provides total control over how the key is generated.</span></span> <span data-ttu-id="450b2-238">Используйте клавиши RSA.</span><span class="sxs-lookup"><span data-stu-id="450b2-238">Use the RSA keys.</span></span> <span data-ttu-id="450b2-239">Хранилище ключей Azure не поддерживает упаковку и разверивание с помощью ключей эллиптической кривой.</span><span class="sxs-lookup"><span data-stu-id="450b2-239">Azure Key Vault doesn't support wrapping and unwrapping with elliptical curve keys.</span></span>
  
<span data-ttu-id="450b2-240">Чтобы создать ключ непосредственно в хранилище ключей, выполните [кодлет Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="450b2-240">To create a key directly in your key vault, run the [Add-AzKeyVaultKey](/powershell/module/az.keyvault/add-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Destination <HSM|Software> -KeyOps wrapKey,unwrapKey
```

<span data-ttu-id="450b2-241">Где:</span><span class="sxs-lookup"><span data-stu-id="450b2-241">Where:</span></span>

- <span data-ttu-id="450b2-242">*имя хранилища* — это имя хранилища ключей, в котором необходимо создать ключ.</span><span class="sxs-lookup"><span data-stu-id="450b2-242">*vault name* is the name of the key vault in which you want to create the key.</span></span>

- <span data-ttu-id="450b2-243">*ключевое* имя — это имя, которое необходимо дать новому ключу.</span><span class="sxs-lookup"><span data-stu-id="450b2-243">*key name* is the name you want to give the new key.</span></span>

  > [!TIP]
  > <span data-ttu-id="450b2-244">Клавиши имен, использующие аналогичную конвенцию именования, как описано выше, для ключевых сводов.</span><span class="sxs-lookup"><span data-stu-id="450b2-244">Name keys using a similar naming convention as described above for key vaults.</span></span> <span data-ttu-id="450b2-245">Таким образом, в средствах, которые показывают только имя ключа, строка самоохвативна.</span><span class="sxs-lookup"><span data-stu-id="450b2-245">This way, in tools that show only the key name, the string is self-describing.</span></span>
  
<span data-ttu-id="450b2-246">Если вы собираетесь защищать ключ с помощью HSM, убедитесь, что вы указываете **HSM** как значение параметра _Destination,_ в противном случае укажите **программное обеспечение.**</span><span class="sxs-lookup"><span data-stu-id="450b2-246">If you intend to protect the key with an HSM, ensure that you specify **HSM** as the value of the _Destination_ parameter, otherwise, specify **Software**.</span></span>

<span data-ttu-id="450b2-247">Пример.</span><span class="sxs-lookup"><span data-stu-id="450b2-247">For example,</span></span>
  
```powershell
Add-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -Destination HSM -KeyOps wrapKey,unwrapKey
```

### <a name="check-the-recovery-level-of-your-keys"></a><span data-ttu-id="450b2-248">Проверьте уровень восстановления ключей</span><span class="sxs-lookup"><span data-stu-id="450b2-248">Check the recovery level of your keys</span></span>

<span data-ttu-id="450b2-249">Microsoft 365 требует, чтобы подписка На хранилище ключей Azure была установлена подписка "Не отменяйте", а ключи, используемые клиентской клавишей, имеют возможность мягкого удаления.</span><span class="sxs-lookup"><span data-stu-id="450b2-249">Microsoft 365 requires that the Azure Key Vault subscription is set to Do Not Cancel and that the keys used by Customer Key have soft delete enabled.</span></span> <span data-ttu-id="450b2-250">Вы можете подтвердить это, посмотрев на уровень восстановления на клавишах.</span><span class="sxs-lookup"><span data-stu-id="450b2-250">You can confirm this by looking at the recovery level on your keys.</span></span>
  
<span data-ttu-id="450b2-251">Чтобы проверить уровень восстановления ключа, в Azure PowerShell выполните Get-AzKeyVaultKey следующим образом:</span><span class="sxs-lookup"><span data-stu-id="450b2-251">To check the recovery level of a key, in Azure PowerShell, run the Get-AzKeyVaultKey cmdlet as follows:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes
```

<span data-ttu-id="450b2-252">Если свойство _Уровня_ восстановления возвращает что-либо, кроме значения **Recoverable+ProtectedSubscription,** вам потребуется просмотреть эту статью и убедиться, что вы следовали всем шагам, чтобы поместить подписку в список "Не отменять", и чтобы вы включили "мягкое удаление" на каждом из ключевых сводов.</span><span class="sxs-lookup"><span data-stu-id="450b2-252">If the _Recovery Level_ property returns anything other than a value of **Recoverable+ProtectedSubscription**, you will need to review this article and ensure that you have followed all of the steps to put the subscription on the Do Not Cancel list and that you enabled "soft delete" on each of your key vaults.</span></span> <span data-ttu-id="450b2-253">Далее отправьте скриншот вывода электронной почты в `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` m365ck@microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="450b2-253">Next, send a screenshot of the output of `(Get-AzKeyVaultKey -VaultName <vault name> -Name <key name>).Attributes` in email to m365ck@microsoft.com.</span></span>

### <a name="back-up-azure-key-vault"></a><span data-ttu-id="450b2-254">Back up Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="450b2-254">Back up Azure Key Vault</span></span>

<span data-ttu-id="450b2-255">Сразу после создания или изменения клавиши выполните резервное копирование и храните копии резервного копирования как в Интернете, так и в автономном режиме.</span><span class="sxs-lookup"><span data-stu-id="450b2-255">Immediately following creation or any change to a key, perform a backup and store copies of the backup, both online and offline.</span></span> <span data-ttu-id="450b2-256">Не подключайте автономные копии к какой-либо сети.</span><span class="sxs-lookup"><span data-stu-id="450b2-256">Don't connect offline copies to any network.</span></span> <span data-ttu-id="450b2-257">Вместо этого храните их в физическом безопасном или коммерческом хранилище.</span><span class="sxs-lookup"><span data-stu-id="450b2-257">Instead, store them in a physical safe or commercial storage facility.</span></span> <span data-ttu-id="450b2-258">По крайней мере одна копия резервного копирования должна храниться в месте, которое будет доступно в случае аварии.</span><span class="sxs-lookup"><span data-stu-id="450b2-258">At least one copy of the backup should be stored in a location that will be accessible if a disaster happens.</span></span> <span data-ttu-id="450b2-259">Blobs резервного копирования являются единственным средством восстановления ключевого материала в случае, если ключ Key Vault будет окончательно уничтожен или иным образом неоперабельным.</span><span class="sxs-lookup"><span data-stu-id="450b2-259">The backup blobs are the sole means of restoring key material should a Key Vault key be permanently destroyed or otherwise rendered inoperable.</span></span> <span data-ttu-id="450b2-260">Ключи, внешние для хранилища ключей Azure и импортируемые в Хранилище ключей Azure, не имеют права на резервное копирование, так как метаданные, необходимые для использования ключа клиента, не существуют с внешним ключом.</span><span class="sxs-lookup"><span data-stu-id="450b2-260">Keys that are external to Azure Key Vault and were imported to Azure Key Vault do not qualify as a backup because the metadata necessary for Customer Key to use the key does not exist with the external key.</span></span> <span data-ttu-id="450b2-261">Только резервная копия, взятая из хранилища ключей Azure, может использоваться для восстановления операций с ключом клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-261">Only a backup taken from Azure Key Vault can be used for restore operations with Customer Key.</span></span> <span data-ttu-id="450b2-262">Поэтому необходимо создать резервную копию хранилища ключей Azure после отправки или создания ключа.</span><span class="sxs-lookup"><span data-stu-id="450b2-262">Therefore, it is essential that you make a backup of Azure Key Vault once a key is uploaded or created.</span></span>
  
<span data-ttu-id="450b2-263">Чтобы создать резервную копию ключа Azure Key Vault, выполните кодлет [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="450b2-263">To create a backup of an Azure Key Vault key, run the [Backup-AzKeyVaultKey](/powershell/module/az.keyvault/backup-azkeyvaultkey) cmdlet as follows:</span></span>

```powershell
Backup-AzKeyVaultKey -VaultName <vault name> -Name <key name>
-OutputFile <filename.backup>
```

<span data-ttu-id="450b2-264">Убедитесь, что в файле вывода используется `.backup` суффикс.</span><span class="sxs-lookup"><span data-stu-id="450b2-264">Ensure that your output file uses the suffix `.backup`.</span></span>
  
<span data-ttu-id="450b2-265">Файл вывода, выдающийся из этого комлета, шифруется и не может использоваться за пределами хранилища ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="450b2-265">The output file resulting from this cmdlet is encrypted and cannot be used outside of Azure Key Vault.</span></span> <span data-ttu-id="450b2-266">Резервное копирование может быть восстановлено только в подписке Azure, из которой была взята резервная копия.</span><span class="sxs-lookup"><span data-stu-id="450b2-266">The backup can be restored only to the Azure subscription from which the backup was taken.</span></span>
  
<span data-ttu-id="450b2-267">Пример:</span><span class="sxs-lookup"><span data-stu-id="450b2-267">For example:</span></span>
  
```powershell
Backup-AzKeyVaultKey -VaultName Contoso-O365EX-NA-VaultA1 -Name Contoso-O365EX-NA-VaultA1-Key001 -OutputFile Contoso-O365EX-NA-VaultA1-Key001-Backup-20170802.backup
```

### <a name="validate-azure-key-vault-configuration-settings"></a><span data-ttu-id="450b2-268">Проверка параметров конфигурации хранилища ключей Azure</span><span class="sxs-lookup"><span data-stu-id="450b2-268">Validate Azure Key Vault configuration settings</span></span>

<span data-ttu-id="450b2-269">Выполнение проверки перед использованием ключей в DEP является необязательным, но настоятельно рекомендуется.</span><span class="sxs-lookup"><span data-stu-id="450b2-269">Performing validation before using keys in a DEP is optional, but highly recommended.</span></span> <span data-ttu-id="450b2-270">В частности, при настройке ключей и сводов, помимо описанных в этой теме, необходимо проверить состояние ресурсов Хранилища ключей Azure перед настройкой ключа клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-270">In particular, if you use steps to set up your keys and vaults other than the ones described in this topic, you should validate the health of your Azure Key Vault resources before you configure Customer Key.</span></span>
  
<span data-ttu-id="450b2-271">Чтобы убедиться, что ваши ключи получили, wrapKey и unwrapKey операции включены:</span><span class="sxs-lookup"><span data-stu-id="450b2-271">To verify that your keys have get, wrapKey, and unwrapKey operations enabled:</span></span>
  
<span data-ttu-id="450b2-272">Выполните [этот кодлет Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="450b2-272">Run the [Get-AzKeyVault](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVault -VaultName <vault name>
```

<span data-ttu-id="450b2-273">В выходной записи см. соответствующую политику доступа и ID приложения Microsoft 365 (GUID).</span><span class="sxs-lookup"><span data-stu-id="450b2-273">In the output, look for the Access Policy and for the Microsoft 365 app ID (GUID) as appropriate.</span></span> <span data-ttu-id="450b2-274">Все три операции, get, wrapKey и unwrapKey, должны быть показаны в статье Permissions to Keys.</span><span class="sxs-lookup"><span data-stu-id="450b2-274">All three operations, get, wrapKey, and unwrapKey, must be shown under Permissions to Keys.</span></span>
  
<span data-ttu-id="450b2-275">Если конфигурация политики доступа неверна, выполните Set-AzKeyVaultAccessPolicy следующим образом:</span><span class="sxs-lookup"><span data-stu-id="450b2-275">If the access policy configuration is incorrect, run the Set-AzKeyVaultAccessPolicy cmdlet as follows:</span></span>
  
```powershell
Set-AzKeyVaultAccessPolicy -VaultName <vault name> -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName <Microsoft 365 appID>
```

<span data-ttu-id="450b2-276">Пример: Для службы шифрования данных Microsoft 365 замените *приложение Microsoft 365 на*`c066d759-24ae-40e7-a56f-027002b5d3e4`</span><span class="sxs-lookup"><span data-stu-id="450b2-276">Example: For the Microsoft 365 Data at Rest Encryption service, replace  *Microsoft 365 appID* with `c066d759-24ae-40e7-a56f-027002b5d3e4`</span></span>

  ```powershell
  Set-AzKeyVaultAccessPolicy -VaultName Contoso-O365EX-NA-VaultA1 -PermissionsToKeys wrapKey,unwrapKey,get -ServicePrincipalName c066d759-24ae-40e7-a56f-027002b5d3e4
  ```

<span data-ttu-id="450b2-277">Чтобы убедиться в том, что срок действия ключей не установлен, выполните кодлет [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="450b2-277">To verify that an expiration date is not set for your keys, run the [Get-AzKeyVaultKey](/powershell/module/az.keyvault/get-azkeyvault) cmdlet as follows:</span></span>
  
```powershell
Get-AzKeyVaultKey -VaultName <vault name>
```

<span data-ttu-id="450b2-278">Ключ с истекшим сроком действия не может использоваться ключом клиента, и операции с истекшим ключом сбой и, возможно, приведет к сбой в работе службы.</span><span class="sxs-lookup"><span data-stu-id="450b2-278">An expired key cannot be used by Customer Key and operations attempted with an expired key will fail and possibly result in a service outage.</span></span> <span data-ttu-id="450b2-279">Настоятельно рекомендуется, чтобы у ключей клиента не было срока действия.</span><span class="sxs-lookup"><span data-stu-id="450b2-279">We strongly recommend that keys used with Customer Key do not have an expiration date.</span></span> <span data-ttu-id="450b2-280">Дата истечения срока действия после набора не может быть удалена, но может быть изменена на другую дату.</span><span class="sxs-lookup"><span data-stu-id="450b2-280">An expiration date, once set, cannot be removed, but can be changed to a different date.</span></span> <span data-ttu-id="450b2-281">Если необходимо использовать ключ с набором сроков действия, измените значение срока действия на 12/31/9999.</span><span class="sxs-lookup"><span data-stu-id="450b2-281">If a key must be used that has an expiration date set, change the expiration value to 12/31/9999.</span></span> <span data-ttu-id="450b2-282">Ключи с истечением срока действия, задав дату, за исключением 12/31/9999, не будут проходить проверку Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="450b2-282">Keys with an expiration date set to a date other than 12/31/9999 won't pass Microsoft 365 validation.</span></span>
  
<span data-ttu-id="450b2-283">Чтобы изменить срок действия, установленный для любого значения, кроме 12/31/9999, выполните кодлет [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) следующим образом:</span><span class="sxs-lookup"><span data-stu-id="450b2-283">To change an expiration date that has been set to any value other than 12/31/9999, run the [Update-AzKeyVaultKey](/powershell/module/az.keyvault/update-azkeyvaultkey) cmdlet as follows:</span></span>
  
```powershell
Update-AzKeyVaultKey -VaultName <vault name> -Name <key name> -Expires (Get-Date -Date "12/31/9999")
```

### <a name="obtain-the-uri-for-each-azure-key-vault-key"></a><span data-ttu-id="450b2-284">Получение URI для каждого ключа Azure Key Vault</span><span class="sxs-lookup"><span data-stu-id="450b2-284">Obtain the URI for each Azure Key Vault key</span></span>

<span data-ttu-id="450b2-285">После завершения всех действий в Azure, чтобы настроить хранилища ключей и добавить ключи, запустите следующую команду, чтобы получить URI для ключа в каждом хранилище ключей.</span><span class="sxs-lookup"><span data-stu-id="450b2-285">Once you've completed all the steps in Azure to set up your key vaults and added your keys, run the following command to get the URI for the key in each key vault.</span></span> <span data-ttu-id="450b2-286">Эти URL-адреса необходимо использовать при создании и назначении каждого deP позже, поэтому сохраните эти сведения в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="450b2-286">You will need to use these URIs when you create and assign each DEP later, so save this information in a safe place.</span></span> <span data-ttu-id="450b2-287">Не забудьте выполнить эту команду один раз для каждого хранилища ключей.</span><span class="sxs-lookup"><span data-stu-id="450b2-287">Remember to run this command once for each key vault.</span></span>
  
<span data-ttu-id="450b2-288">В Azure PowerShell:</span><span class="sxs-lookup"><span data-stu-id="450b2-288">In Azure PowerShell:</span></span>
  
```powershell
(Get-AzKeyVaultKey -VaultName <vault name>).Id
```

## <a name="set-up-the-customer-key-encryption-policy-for-your-tenant"></a><span data-ttu-id="450b2-289">Настройка политики шифрования ключа клиента для клиента</span><span class="sxs-lookup"><span data-stu-id="450b2-289">Set up the Customer Key encryption policy for your tenant</span></span>

<span data-ttu-id="450b2-290">Для запуска этих кодлетов необходимо получить соответствующие разрешения.</span><span class="sxs-lookup"><span data-stu-id="450b2-290">You need to be assigned permissions before you can run these cmdlets.</span></span> <span data-ttu-id="450b2-291">Хотя в этой статье перечислены все параметры для этих параметров, вы можете не иметь доступа к некоторым параметрам, если они не включены в назначенное вам разрешение.</span><span class="sxs-lookup"><span data-stu-id="450b2-291">Although this article lists all parameters for the cmdlets, you may not have access to some parameters if they're not included in the permissions assigned to you.</span></span> <span data-ttu-id="450b2-292">Сведения о необходимых разрешениях для запуска командлетов и использования параметров в организации см. в статье [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span><span class="sxs-lookup"><span data-stu-id="450b2-292">To find the permissions required to run any cmdlet or parameter in your organization, see [Find the permissions required to run any Exchange cmdlet](/powershell/exchange/exchange-server/find-exchange-cmdlet-permissions).</span></span>

### <a name="create-policy"></a><span data-ttu-id="450b2-293">Создание политики</span><span class="sxs-lookup"><span data-stu-id="450b2-293">Create policy</span></span>

```powershell
   New-M365DataAtRestEncryptionPolicy [-Name] <String> -AzureKeyIDs <MultiValuedProperty> [-Description <String>]
```

<span data-ttu-id="450b2-294">Описание. Включить администратора соответствия требованиям для создания новой политики шифрования данных (DEP) с помощью двух корневых ключей AKV.</span><span class="sxs-lookup"><span data-stu-id="450b2-294">Description: Enable compliance admin to create a new data encryption policy (DEP) using two AKV root keys.</span></span> <span data-ttu-id="450b2-295">После создания политика может быть назначена с помощью Set-M365DataAtRestEncryptionPolicyAssignment.</span><span class="sxs-lookup"><span data-stu-id="450b2-295">Once created, a policy can then be assigned using Set-M365DataAtRestEncryptionPolicyAssignment cmdlet.</span></span> <span data-ttu-id="450b2-296">При первом назначении ключей или после поворота клавиш может занять до 24 часов, чтобы новые ключи вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="450b2-296">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="450b2-297">Если новый deP вступает в силу более 24 часов, обратитесь в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="450b2-297">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="450b2-298">Пример.</span><span class="sxs-lookup"><span data-stu-id="450b2-298">Example:</span></span>

```powershell
New-M365DataAtRestEncryptionPolicy -Name "Default_Policy" -AzureKeyIDs "https://contosoWestUSvault01.vault.azure.net/keys/Key_01","https://contosoEastUSvault01.vault.azure.net/keys/Key_02" -Description "Tenant default policy"
```

<span data-ttu-id="450b2-299">Параметры:</span><span class="sxs-lookup"><span data-stu-id="450b2-299">Parameters:</span></span>

| <span data-ttu-id="450b2-300">Имя</span><span class="sxs-lookup"><span data-stu-id="450b2-300">Name</span></span> | <span data-ttu-id="450b2-301">Описание</span><span class="sxs-lookup"><span data-stu-id="450b2-301">Description</span></span> | <span data-ttu-id="450b2-302">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="450b2-302">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="450b2-303">Имя</span><span class="sxs-lookup"><span data-stu-id="450b2-303">Name</span></span>|<span data-ttu-id="450b2-304">Удобное имя политики шифрования данных</span><span class="sxs-lookup"><span data-stu-id="450b2-304">Friendly name of the data encryption policy</span></span>|<span data-ttu-id="450b2-305">N</span><span class="sxs-lookup"><span data-stu-id="450b2-305">N</span></span>|
|<span data-ttu-id="450b2-306">AzureKeyIDs</span><span class="sxs-lookup"><span data-stu-id="450b2-306">AzureKeyIDs</span></span>|<span data-ttu-id="450b2-307">Указывает два значения URI ключей хранилища Azure, разделенных запятой, для связи с политикой шифрования данных</span><span class="sxs-lookup"><span data-stu-id="450b2-307">Specifies two URI values of the Azure Key Vault keys, separated by a comma, to associate with the data encryption policy</span></span>|<span data-ttu-id="450b2-308">N</span><span class="sxs-lookup"><span data-stu-id="450b2-308">N</span></span>|
|<span data-ttu-id="450b2-309">Описание</span><span class="sxs-lookup"><span data-stu-id="450b2-309">Description</span></span>|<span data-ttu-id="450b2-310">Описание политики шифрования данных</span><span class="sxs-lookup"><span data-stu-id="450b2-310">Description of the data encryption policy</span></span>|<span data-ttu-id="450b2-311">N</span><span class="sxs-lookup"><span data-stu-id="450b2-311">N</span></span>|

### <a name="assign-policy"></a><span data-ttu-id="450b2-312">Назначение политики</span><span class="sxs-lookup"><span data-stu-id="450b2-312">Assign policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "<Default_PolicyName or Default_PolicyID>"
```

<span data-ttu-id="450b2-313">Описание. Этот комлет используется для настройки политики шифрования данных по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="450b2-313">Description: This cmdlet is used for configuring default Data Encryption Policy.</span></span> <span data-ttu-id="450b2-314">Эта политика будет использоваться для шифрования данных во всех рабочих нагрузках поддержки.</span><span class="sxs-lookup"><span data-stu-id="450b2-314">This policy will be used to then encrypt data across all support workloads.</span></span> 

<span data-ttu-id="450b2-315">Пример.</span><span class="sxs-lookup"><span data-stu-id="450b2-315">Example:</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicyAssignment -DataEncryptionPolicy "Default_PolicyName"
```

<span data-ttu-id="450b2-316">Параметры:</span><span class="sxs-lookup"><span data-stu-id="450b2-316">Parameters:</span></span>

| <span data-ttu-id="450b2-317">Имя</span><span class="sxs-lookup"><span data-stu-id="450b2-317">Name</span></span> | <span data-ttu-id="450b2-318">Описание</span><span class="sxs-lookup"><span data-stu-id="450b2-318">Description</span></span> | <span data-ttu-id="450b2-319">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="450b2-319">Optional (Y/N)</span></span> |
|----------|----------|---------|
<span data-ttu-id="450b2-320">-DataEncryptionPolicy</span><span class="sxs-lookup"><span data-stu-id="450b2-320">-DataEncryptionPolicy</span></span>|<span data-ttu-id="450b2-321">Указывает политику шифрования данных, которая должна быть назначена; укажите имя политики или ИД политики.</span><span class="sxs-lookup"><span data-stu-id="450b2-321">Specifies the data encryption policy that needs to be assigned; specify either the Policy Name or the Policy ID.</span></span>|<span data-ttu-id="450b2-322">N</span><span class="sxs-lookup"><span data-stu-id="450b2-322">N</span></span>|

### <a name="modify-or-refresh-policy"></a><span data-ttu-id="450b2-323">Изменение или обновление политики</span><span class="sxs-lookup"><span data-stu-id="450b2-323">Modify or Refresh policy</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter> -Refresh [-Enabled <Boolean>] [-Name <String>] [-Description <String>]
```

<span data-ttu-id="450b2-324">Описание. Этот комлет можно использовать для изменения или обновления существующей политики.</span><span class="sxs-lookup"><span data-stu-id="450b2-324">Description: The cmdlet can be used either to modify or refresh an existing policy.</span></span> <span data-ttu-id="450b2-325">Он также может использоваться для включить или отключить политику.</span><span class="sxs-lookup"><span data-stu-id="450b2-325">It can also be used to enable or disable a policy.</span></span> <span data-ttu-id="450b2-326">При первом назначении ключей или после поворота клавиш может занять до 24 часов, чтобы новые ключи вступили в силу.</span><span class="sxs-lookup"><span data-stu-id="450b2-326">Upon first assignment of keys or after you rotate keys, it can take up to 24 hours for the new keys to take effect.</span></span> <span data-ttu-id="450b2-327">Если новый deP вступает в силу более 24 часов, обратитесь в Корпорацию Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="450b2-327">If the new DEP takes more than 24 hours to take effect, contact Microsoft.</span></span>

<span data-ttu-id="450b2-328">Примеры:</span><span class="sxs-lookup"><span data-stu-id="450b2-328">Examples:</span></span>

<span data-ttu-id="450b2-329">Отключить политику шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-329">Disable a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "NAM Policy" -Enabled $false
```

<span data-ttu-id="450b2-330">Обновление политики шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-330">Refresh a data encryption policy.</span></span>

```powershell
Set-M365DataAtRestEncryptionPolicy -Identity "EUR Policy" -Refresh
```

<span data-ttu-id="450b2-331">Параметры:</span><span class="sxs-lookup"><span data-stu-id="450b2-331">Parameters:</span></span>

| <span data-ttu-id="450b2-332">Имя</span><span class="sxs-lookup"><span data-stu-id="450b2-332">Name</span></span> | <span data-ttu-id="450b2-333">Описание</span><span class="sxs-lookup"><span data-stu-id="450b2-333">Description</span></span> | <span data-ttu-id="450b2-334">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="450b2-334">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="450b2-335">-Identity</span><span class="sxs-lookup"><span data-stu-id="450b2-335">-Identity</span></span>|<span data-ttu-id="450b2-336">Указывает политику шифрования данных, которую необходимо изменить.</span><span class="sxs-lookup"><span data-stu-id="450b2-336">Specifies the data encryption policy that you want to modify.</span></span>|<span data-ttu-id="450b2-337">N</span><span class="sxs-lookup"><span data-stu-id="450b2-337">N</span></span>|
|<span data-ttu-id="450b2-338">-Обновление</span><span class="sxs-lookup"><span data-stu-id="450b2-338">-Refresh</span></span>|<span data-ttu-id="450b2-339">Используйте переключатель "Обновление", чтобы обновить политику шифрования данных после поворота всех связанных ключей в хранилище ключей Azure.</span><span class="sxs-lookup"><span data-stu-id="450b2-339">Use the Refresh switch to update the data encryption policy after you rotate any of the associated keys in the Azure Key Vault.</span></span> <span data-ttu-id="450b2-340">С этим параметром не нужно указывать значение.</span><span class="sxs-lookup"><span data-stu-id="450b2-340">You don't need to specify a value with this switch.</span></span>|<span data-ttu-id="450b2-341">Да</span><span class="sxs-lookup"><span data-stu-id="450b2-341">Y</span></span>|
|<span data-ttu-id="450b2-342">-Enabled</span><span class="sxs-lookup"><span data-stu-id="450b2-342">-Enabled</span></span>|<span data-ttu-id="450b2-343">Параметр Включен включает или отключит политику шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-343">The Enabled parameter enables or disable the data encryption policy.</span></span> <span data-ttu-id="450b2-344">Перед отключением политики необходимо отогнать ее от клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-344">Before you disable a policy, you must unassign it from your tenant.</span></span> <span data-ttu-id="450b2-345">Допустимые значения:</span><span class="sxs-lookup"><span data-stu-id="450b2-345">Valid values are:</span></span></br > <span data-ttu-id="450b2-346">$true: политика включена</span><span class="sxs-lookup"><span data-stu-id="450b2-346">$true: The policy is enabled</span></span></br > <span data-ttu-id="450b2-347">$true. Политика включена. Это значение задается по умолчанию.
</span><span class="sxs-lookup"><span data-stu-id="450b2-347">$false: The policy is disabled.</span></span>|<span data-ttu-id="450b2-348">Да</span><span class="sxs-lookup"><span data-stu-id="450b2-348">Y</span></span>|
|<span data-ttu-id="450b2-349">– Name</span><span class="sxs-lookup"><span data-stu-id="450b2-349">-Name</span></span>|<span data-ttu-id="450b2-350">Параметр Name задает уникальное имя политики шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-350">The Name parameter specifies the unique name for the data encryption policy.</span></span>|<span data-ttu-id="450b2-351">Да</span><span class="sxs-lookup"><span data-stu-id="450b2-351">Y</span></span>|
|<span data-ttu-id="450b2-352">-Description</span><span class="sxs-lookup"><span data-stu-id="450b2-352">-Description</span></span>|<span data-ttu-id="450b2-353">Параметр Description задает необязательное описание политики шифрования данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-353">The Description parameter specifies an optional description for the data encryption policy.</span></span>|<span data-ttu-id="450b2-354">Да</span><span class="sxs-lookup"><span data-stu-id="450b2-354">Y</span></span>|

### <a name="get-policy-details"></a><span data-ttu-id="450b2-355">Сведения о политике</span><span class="sxs-lookup"><span data-stu-id="450b2-355">Get policy details</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy [-Identity] <M365DataAtRestEncryptionPolicy DataEncryptionPolicyIdParameter>
```

<span data-ttu-id="450b2-356">Описание. В этом списке перечислены все политики шифрования M365DataAtRest, созданные для клиента, или сведения о конкретной политике.</span><span class="sxs-lookup"><span data-stu-id="450b2-356">Description: This cmdlet lists all of M365DataAtRest encryption policies that are created for the tenant or details about a specific policy.</span></span>

<span data-ttu-id="450b2-357">Примеры:</span><span class="sxs-lookup"><span data-stu-id="450b2-357">Examples:</span></span>

<span data-ttu-id="450b2-358">В этом примере возвращается сводный список политик шифрования M365DatAtRest в организации.</span><span class="sxs-lookup"><span data-stu-id="450b2-358">This example returns a summary list of M365DatAtRest Encryption policies in the organization.</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy
```

<span data-ttu-id="450b2-359">В этом примере возвращается подробная информация для политики шифрования данных с именем "Политика NAM".</span><span class="sxs-lookup"><span data-stu-id="450b2-359">This example returns detailed information for the data encryption policy named "NAM Policy".</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicy -Identity "NAM Policy"
```

<span data-ttu-id="450b2-360">Параметры:</span><span class="sxs-lookup"><span data-stu-id="450b2-360">Parameters:</span></span>

| <span data-ttu-id="450b2-361">Имя</span><span class="sxs-lookup"><span data-stu-id="450b2-361">Name</span></span> | <span data-ttu-id="450b2-362">Описание</span><span class="sxs-lookup"><span data-stu-id="450b2-362">Description</span></span> | <span data-ttu-id="450b2-363">Необязательный (Y/N)</span><span class="sxs-lookup"><span data-stu-id="450b2-363">Optional (Y/N)</span></span> |
|----------|----------|---------|
|<span data-ttu-id="450b2-364">-Identity</span><span class="sxs-lookup"><span data-stu-id="450b2-364">-Identity</span></span>|<span data-ttu-id="450b2-365">Указывает политику шифрования данных, для которую необходимо перечислить сведения.</span><span class="sxs-lookup"><span data-stu-id="450b2-365">Specifies the data encryption policy that you want to list the details for.</span></span>|<span data-ttu-id="450b2-366">Да</span><span class="sxs-lookup"><span data-stu-id="450b2-366">Y</span></span>|

### <a name="get-policy-assignment-info"></a><span data-ttu-id="450b2-367">Сведения о назначении политики</span><span class="sxs-lookup"><span data-stu-id="450b2-367">Get policy assignment info</span></span>

```powershell
Get-M365DataAtRestEncryptionPolicyAssignment
```

<span data-ttu-id="450b2-368">Описание. В этом списке указана политика, назначенная в настоящее время клиенту.</span><span class="sxs-lookup"><span data-stu-id="450b2-368">Description: This cmdlet lists the policy that’s currently assigned to the tenant.</span></span>

## <a name="offboarding-from-customer-key"></a><span data-ttu-id="450b2-369">Отключение от ключа клиента</span><span class="sxs-lookup"><span data-stu-id="450b2-369">Offboarding from Customer Key</span></span>

<span data-ttu-id="450b2-370">Если вам нужно вернуться к клавишам с управлением Майкрософт, вы можете.</span><span class="sxs-lookup"><span data-stu-id="450b2-370">If you need to revert back to Microsoft-managed keys, you can.</span></span> <span data-ttu-id="450b2-371">При отключении данные повторно шифруются с помощью шифрования по умолчанию, поддерживаемого каждой отдельной рабочей нагрузкой.</span><span class="sxs-lookup"><span data-stu-id="450b2-371">When you offboard, your data is re-encrypted using default encryption supported by each individual workload.</span></span> <span data-ttu-id="450b2-372">Например, Exchange Online поддерживает шифрование по умолчанию с помощью ключей, управляемых Корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="450b2-372">For example, Exchange Online supports default encryption using Microsoft-managed keys.</span></span>

<span data-ttu-id="450b2-373">Если вы решили отключить клиента из клиентского ключа на уровне клиента, обратись в Корпорацию Майкрософт с просьбой по электронной почте "отключить" службу для клиента в [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="450b2-373">If you decided to offboard your tenant from Customer Key at the tenant level, reach out to Microsoft with a request through email to "disable" the service for the tenant at [m365ck@microsoft.com](mailto:m365ck@microsoft.com).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="450b2-374">Offboarding — это не то же самое, что очистка данных.</span><span class="sxs-lookup"><span data-stu-id="450b2-374">Offboarding is not the same as a data purge.</span></span> <span data-ttu-id="450b2-375">Очистка данных навсегда удаляет данные вашей организации из Microsoft 365, отключение не происходит.</span><span class="sxs-lookup"><span data-stu-id="450b2-375">A data purge permanently crypto-deletes your organization's data from Microsoft 365, offboarding does not.</span></span> <span data-ttu-id="450b2-376">Вы не можете выполнить очистку данных для политики уровня клиента.</span><span class="sxs-lookup"><span data-stu-id="450b2-376">You can't perform a data purge for a tenant-level policy.</span></span> <span data-ttu-id="450b2-377">Сведения о пути очистки данных см. в ссылке [Revoke your keys and start the data purge path process.](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process)</span><span class="sxs-lookup"><span data-stu-id="450b2-377">For information about data purge path, see [Revoke your keys and start the data purge path process](customer-key-manage.md#revoke-your-keys-and-start-the-data-purge-path-process).</span></span>

## <a name="about-the-availability-key"></a><span data-ttu-id="450b2-378">О ключе доступности</span><span class="sxs-lookup"><span data-stu-id="450b2-378">About the availability key</span></span>

<span data-ttu-id="450b2-379">Сведения о ключе доступности см. в [сведениях о ключе доступности.](customer-key-availability-key-understand.md)</span><span class="sxs-lookup"><span data-stu-id="450b2-379">For information about the availability key, see [Learn about the availability key](customer-key-availability-key-understand.md).</span></span>

## <a name="key-rotation"></a><span data-ttu-id="450b2-380">Поворот ключей</span><span class="sxs-lookup"><span data-stu-id="450b2-380">Key rotation</span></span>

<span data-ttu-id="450b2-381">Сведения о вращающихся или прокатных клавишах, используемых с ключом клиента, см. в журнале [Roll or rotate a Customer Key or an availability key.](customer-key-availability-key-roll.md)</span><span class="sxs-lookup"><span data-stu-id="450b2-381">For information about rotating or rolling keys used with Customer Key, see [Roll or rotate a Customer Key or an availability key](customer-key-availability-key-roll.md).</span></span> <span data-ttu-id="450b2-382">При обновлении deP для использования новой версии ключей вы запустите Set-M365DataAtRestEncryptionPolicy, как описано выше в этой статье.</span><span class="sxs-lookup"><span data-stu-id="450b2-382">When you update the DEP to use the new version of the keys, you'll run the Set-M365DataAtRestEncryptionPolicy cmdlet as described earlier in this article.</span></span>

## <a name="related-articles"></a><span data-ttu-id="450b2-383">Связанные статьи:</span><span class="sxs-lookup"><span data-stu-id="450b2-383">Related articles:</span></span>

- [<span data-ttu-id="450b2-384">Шифрование службы с помощью ключа клиента</span><span class="sxs-lookup"><span data-stu-id="450b2-384">Service encryption with Customer Key</span></span>](customer-key-overview.md)

- [<span data-ttu-id="450b2-385">Смена или ротация ключа клиента или ключа доступности</span><span class="sxs-lookup"><span data-stu-id="450b2-385">Roll or rotate a Customer Key or an availability key</span></span>](customer-key-availability-key-roll.md)

- [<span data-ttu-id="450b2-386">Узнайте о ключе доступности</span><span class="sxs-lookup"><span data-stu-id="450b2-386">Learn about the availability key</span></span>](customer-key-availability-key-understand.md)

- [<span data-ttu-id="450b2-387">Шифрование служб</span><span class="sxs-lookup"><span data-stu-id="450b2-387">Service Encryption</span></span>](office-365-service-encryption.md)