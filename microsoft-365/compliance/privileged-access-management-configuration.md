---
title: Начало работы с управлением привилегированным доступом
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
ms.custom: Ent_Solutions
ms.assetid: ''
description: Используйте этот раздел для получения дополнительных сведений о настройке управления привилегированным доступом.
ms.openlocfilehash: 196685eda6818b399c778363ee458f6f2792a33a
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626515"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="d29e4-103">Начало работы с управлением привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="d29e4-103">Get started with privileged access management</span></span>

<span data-ttu-id="d29e4-104">В этом разделе описывается включение и Настройка управления привилегированным доступом в Организации.</span><span class="sxs-lookup"><span data-stu-id="d29e4-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="d29e4-105">Для управления привилегированным доступом можно использовать центр администрирования Microsoft 365 или PowerShell управления Exchange.</span><span class="sxs-lookup"><span data-stu-id="d29e4-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="d29e4-106">Перед началом работы</span><span class="sxs-lookup"><span data-stu-id="d29e4-106">Before you begin</span></span>

<span data-ttu-id="d29e4-107">Прежде чем приступить к управлению привилегированным доступом, необходимо подтвердить вашу [подписку на Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) и любую надстройку.</span><span class="sxs-lookup"><span data-stu-id="d29e4-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="d29e4-108">Чтобы получить доступ к управлению привилегированным доступом и использовать ее, ваша организация должна иметь одну из следующих подписок или надстроек:</span><span class="sxs-lookup"><span data-stu-id="d29e4-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="d29e4-109">Подписка на Microsoft 365 (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="d29e4-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="d29e4-110">Подписка на Microsoft 365 E3 (или подписка на Office 365 E3 и подписка на корпоративную мобильную систему и безопасность E3) + надстройка Майкрософт для обеспечения соответствия клавишам Майкрософт 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="d29e4-111">Любая подписка на Microsoft 365, Office 365, Exchange, SharePoint или OneDrive для бизнеса и надстройка "Управление рисками Майкрософт для участников программы предварительной оценки Майкрософт для Майкрософт 365"</span><span class="sxs-lookup"><span data-stu-id="d29e4-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="d29e4-112">Подписка на Microsoft 365 A5 (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="d29e4-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="d29e4-113">Подписка на Microsoft 365 A3 (или подписка на Office 365 a3 + корпоративный Mobility and Security a3) + надстройка Microsoft A5 для обеспечения соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="d29e4-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="d29e4-114">Все подписки Microsoft 365, Office 365, Exchange, SharePoint и OneDrive для образования и надстройка "Управление рисками для Майкрософт 365 A5"</span><span class="sxs-lookup"><span data-stu-id="d29e4-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="d29e4-115">Подписка на Office 365 корпоративный (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="d29e4-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="d29e4-116">Подписка на Office 365 корпоративный E3 + расширенное соответствие требованиям Office 365 (для новых подписок больше недоступна. Примечание)</span><span class="sxs-lookup"><span data-stu-id="d29e4-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="d29e4-117">Пользователям, отправляемым и отвечающим на запросы управления привилегированным доступом, должна быть назначена одна из указанных выше лицензий.</span><span class="sxs-lookup"><span data-stu-id="d29e4-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d29e4-118">Расширенное соответствие требованиям Office 365 больше не продается в виде автономной подписки.</span><span class="sxs-lookup"><span data-stu-id="d29e4-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="d29e4-119">При истечении срока действия текущих подписок клиенты должны переходить на одну из упомянутых выше подписок, которые содержат одинаковые или дополнительные функции соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d29e4-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="d29e4-120">Если у вас нет существующего плана Office 365 корпоративный, а вы хотите испытать возможности управления привилегированным доступом, вы можете [Добавить Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) в существующую подписку на Office 365 или [зарегистрировать пробную](https://www.microsoft.com/microsoft-365/enterprise) версию Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="d29e4-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="d29e4-121">Включение и Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="d29e4-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="d29e4-122">Чтобы настроить и использовать привилегированный доступ в Организации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="d29e4-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="d29e4-123">Шаг 1: создание группы утверждающего</span><span class="sxs-lookup"><span data-stu-id="d29e4-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="d29e4-124">Прежде чем приступить к работе с правами на доступ к данным, определите, кому требуется центр утверждений для входящих запросов на доступ к привилегированным и привилегированным задачам.</span><span class="sxs-lookup"><span data-stu-id="d29e4-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="d29e4-125">Любой пользователь, являющийся участником группы утверждающих, может утверждать запросы на доступ.</span><span class="sxs-lookup"><span data-stu-id="d29e4-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="d29e4-126">Эта группа включена путем создания группы безопасности с включенной поддержкой почты в Office 365.</span><span class="sxs-lookup"><span data-stu-id="d29e4-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="d29e4-127">Шаг 2: включение привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="d29e4-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="d29e4-128">Привилегированный доступ должен быть явно включен в Office 365 с группой утверждающих по умолчанию, в том числе набором системных учетных записей, которые необходимо исключить из управления доступом для привилегированного управления доступом.</span><span class="sxs-lookup"><span data-stu-id="d29e4-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="d29e4-129">Шаг 3: Создание политики доступа</span><span class="sxs-lookup"><span data-stu-id="d29e4-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="d29e4-130">Создание политики утверждения позволяет определять конкретные требования к утверждению в рамках отдельных задач.</span><span class="sxs-lookup"><span data-stu-id="d29e4-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="d29e4-131">Возможные варианты типа утверждения: **Auto** или **вручную**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="d29e4-132">Шаг 4: передача и утверждение привилегированных запросов доступа</span><span class="sxs-lookup"><span data-stu-id="d29e4-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="d29e4-133">После включения привилегированный доступ требует утверждения для любой задачи, для которой определена соответствующая политика утверждения.</span><span class="sxs-lookup"><span data-stu-id="d29e4-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="d29e4-134">Для задач, включенных в политику утверждения, пользователям необходимо запросить утверждение доступа, чтобы иметь разрешения, необходимые для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="d29e4-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="d29e4-135">После предоставления утверждения пользователь, выполняющий запрос, может выполнить предполагаемую задачу, а привилегированный доступ будет авторизовать и выполнить задачу от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="d29e4-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="d29e4-136">Утверждение остается действительным в течение запрошенного периода (длительность по умолчанию составляет 4 часа), в течение которого инициатор запроса может выполнить нужную задачу несколько раз.</span><span class="sxs-lookup"><span data-stu-id="d29e4-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="d29e4-137">Все подобные выполнения записываются в журнал и становятся доступны для аудита безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d29e4-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="d29e4-138">Если вы хотите включить и настроить привилегированный доступ с помощью PowerShell для управления Exchange, выполните действия, описанные в статье [Подключение к Exchange Online PowerShell с использованием многофакторной проверки подлинности](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) для подключения к Exchange Online PowerShell с помощью учетных данных Office 365.</span><span class="sxs-lookup"><span data-stu-id="d29e4-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/mfa-connect-to-exchange-online-powershell?view=exchange-ps) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="d29e4-139">В Организации не требуется включать многофакторную проверку подлинности для включения привилегированного доступа при подключении к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="d29e4-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="d29e4-140">При подключении с многофакторной проверкой подлинности создается маркер OAuth, используемый привилегированным доступом для подписи запросов.</span><span class="sxs-lookup"><span data-stu-id="d29e4-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="d29e4-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="d29e4-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="d29e4-142">Шаг 1: создание группы утверждающего</span><span class="sxs-lookup"><span data-stu-id="d29e4-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="d29e4-143">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="d29e4-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d29e4-144">В центре администрирования последовательно выберите пункты **группы** > **Добавить группу**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="d29e4-145">Выберите пункт **Группа безопасности с включенной поддержкой почты** и заполните поля **имя**, **адрес электронной почты группы**и **Описание** для новой группы.</span><span class="sxs-lookup"><span data-stu-id="d29e4-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="d29e4-146">Сохраните группу.</span><span class="sxs-lookup"><span data-stu-id="d29e4-146">Save the group.</span></span> <span data-ttu-id="d29e4-147">Для полной настройки группы и ее отображения в центре администрирования Microsoft 365 может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="d29e4-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="d29e4-148">Выберите новую группу утверждающего и нажмите кнопку **изменить** , чтобы добавить пользователей в группу.</span><span class="sxs-lookup"><span data-stu-id="d29e4-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="d29e4-149">Сохраните группу.</span><span class="sxs-lookup"><span data-stu-id="d29e4-149">Save the group.</span></span>

<span data-ttu-id="d29e4-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="d29e4-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="d29e4-151">Шаг 2: включение привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="d29e4-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="d29e4-152">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d29e4-153">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="d29e4-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d29e4-154">В центре администрирования перейдите к разделу **Параметры > параметры > безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-154">In the Admin Center, go to **Settings > Settings > Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d29e4-155">Включите элемент управления " **требовать утверждения для привилегированных задач** ".</span><span class="sxs-lookup"><span data-stu-id="d29e4-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="d29e4-156">Назначьте группу утверждающих, созданную на шаге 1, в качестве **группы утверждающих по умолчанию**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="d29e4-157">**Сохраните** и **закройте диалоговое окно**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="d29e4-158">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="d29e4-159">Чтобы включить привилегированный доступ и назначить группу утверждающего, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d29e4-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="d29e4-160">Пример:</span><span class="sxs-lookup"><span data-stu-id="d29e4-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="d29e4-161">Функция "системные учетные записи" доступна, чтобы гарантировать, что определенные автоматизации в организациях могут работать без зависимости от привилегированного доступа, однако рекомендуется, чтобы такие исключения были исключительными и их можно было утверждать и регулярно проверять.</span><span class="sxs-lookup"><span data-stu-id="d29e4-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="d29e4-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="d29e4-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="d29e4-163">Шаг 3: Создание политики доступа</span><span class="sxs-lookup"><span data-stu-id="d29e4-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="d29e4-164">Вы можете создать и настроить до 30 политик доступа для Организации.</span><span class="sxs-lookup"><span data-stu-id="d29e4-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="d29e4-165">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d29e4-166">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="d29e4-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d29e4-167">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-167">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d29e4-168">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d29e4-169">Выберите пункт **Настройка политик** и нажмите кнопку **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="d29e4-170">В раскрывающихся полях выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="d29e4-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="d29e4-171">**Тип политики**: задача, роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="d29e4-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="d29e4-172">**Область действия политики**: Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="d29e4-173">**Имя политики**: выберите из доступных политик</span><span class="sxs-lookup"><span data-stu-id="d29e4-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="d29e4-174">**Тип утверждения**: вручную или автоматически</span><span class="sxs-lookup"><span data-stu-id="d29e4-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="d29e4-175">**Группа утверждения**: выберите группу утверждающих, созданную на шаге 1.</span><span class="sxs-lookup"><span data-stu-id="d29e4-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="d29e4-176">Выберите **создать** , а затем **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="d29e4-177">Полная настройка и включение политики может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="d29e4-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="d29e4-178">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="d29e4-179">Чтобы создать и определить политику утверждения, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d29e4-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="d29e4-180">Пример:</span><span class="sxs-lookup"><span data-stu-id="d29e4-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="d29e4-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="d29e4-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="d29e4-182">Шаг 4: передача и утверждение привилегированных запросов доступа</span><span class="sxs-lookup"><span data-stu-id="d29e4-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="d29e4-183">Запрос разрешения на повышение прав для выполнения привилегированных задач</span><span class="sxs-lookup"><span data-stu-id="d29e4-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="d29e4-184">Запросы для привилегированного доступа действительны в течение 24 часов после отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="d29e4-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="d29e4-185">Если оно не утверждено или отклонено, срок действия запросов истечет и доступ не утверждается.</span><span class="sxs-lookup"><span data-stu-id="d29e4-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="d29e4-186">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="d29e4-187">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя свои учетные данные.</span><span class="sxs-lookup"><span data-stu-id="d29e4-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="d29e4-188">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-188">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d29e4-189">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d29e4-190">Выберите пункт **создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-190">Select **New request**.</span></span> <span data-ttu-id="d29e4-191">В раскрывающихся полях выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="d29e4-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="d29e4-192">**Тип запроса**: задача, роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="d29e4-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="d29e4-193">**Область запроса**: Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="d29e4-194">**Запрос для**: выберите из доступных политик</span><span class="sxs-lookup"><span data-stu-id="d29e4-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="d29e4-195">**Продолжительность (часы)**: количество часов запрошенного доступа.</span><span class="sxs-lookup"><span data-stu-id="d29e4-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="d29e4-196">Количество часов, которые можно запросить, не ограничено.</span><span class="sxs-lookup"><span data-stu-id="d29e4-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="d29e4-197">**Comments**: текстовое поле для комментариев, связанных с вашим запросом на доступ</span><span class="sxs-lookup"><span data-stu-id="d29e4-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="d29e4-198">Нажмите кнопку **сохранить** , а затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="d29e4-199">Ваш запрос будет отправлен в группу утверждающего через электронную почту.</span><span class="sxs-lookup"><span data-stu-id="d29e4-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="d29e4-200">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="d29e4-201">Выполните следующую команду в Exchange Online PowerShell, чтобы создать и отправить запрос на утверждение группе утверждающего.</span><span class="sxs-lookup"><span data-stu-id="d29e4-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="d29e4-202">Пример:</span><span class="sxs-lookup"><span data-stu-id="d29e4-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="d29e4-203">Просмотр состояния запросов на повышение прав</span><span class="sxs-lookup"><span data-stu-id="d29e4-203">View status of elevation requests</span></span>

<span data-ttu-id="d29e4-204">После создания запроса на утверждение состояние запроса на повышение прав можно просмотреть в центре администрирования или в Exchange Management PowerShell с помощью соответствующего идентификатора запроса.</span><span class="sxs-lookup"><span data-stu-id="d29e4-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="d29e4-205">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="d29e4-206">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с вашими учетными данными.</span><span class="sxs-lookup"><span data-stu-id="d29e4-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="d29e4-207">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-207">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d29e4-208">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d29e4-209">Выберите **представление** , чтобы отфильтровать отправленные запросы по **очереди**, **утверждению**, **отклонению**или статусу **защищенного хранилища клиента** .</span><span class="sxs-lookup"><span data-stu-id="d29e4-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="d29e4-210">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="d29e4-211">Выполните следующую команду в Exchange Online PowerShell, чтобы просмотреть состояние запроса на утверждение для определенного идентификатора запроса:</span><span class="sxs-lookup"><span data-stu-id="d29e4-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="d29e4-212">Пример:</span><span class="sxs-lookup"><span data-stu-id="d29e4-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="d29e4-213">Утверждение запроса на повышение прав на авторизацию</span><span class="sxs-lookup"><span data-stu-id="d29e4-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="d29e4-214">При создании запроса на утверждение участники группы "Утверждающие" получают уведомления по электронной почте и могут утверждать запрос, связанный с ИДЕНТИФИКАТОРом запроса.</span><span class="sxs-lookup"><span data-stu-id="d29e4-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="d29e4-215">Запрашивающий уведомляет об утверждении или отказе от запроса через сообщение электронной почты.</span><span class="sxs-lookup"><span data-stu-id="d29e4-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="d29e4-216">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="d29e4-217">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с вашими учетными данными.</span><span class="sxs-lookup"><span data-stu-id="d29e4-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="d29e4-218">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-218">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d29e4-219">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d29e4-220">Выберите указанный запрос для просмотра сведений и выполнения действий по запросу.</span><span class="sxs-lookup"><span data-stu-id="d29e4-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="d29e4-221">Выберите **утвердить** , чтобы утвердить запрос, или выберите **запретить** , чтобы отклонить запрос.</span><span class="sxs-lookup"><span data-stu-id="d29e4-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="d29e4-222">Чтобы получить доступ к ранее утвержденным запросам, нажмите кнопку **отозвать**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="d29e4-223">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="d29e4-224">Чтобы утвердить запрос на повышение прав на авторизацию, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d29e4-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="d29e4-225">Пример:</span><span class="sxs-lookup"><span data-stu-id="d29e4-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="d29e4-226">Чтобы запретить запрос на повышение прав на авторизацию, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d29e4-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="d29e4-227">Пример:</span><span class="sxs-lookup"><span data-stu-id="d29e4-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="d29e4-228">Удаление политики привилегированного доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="d29e4-229">Если в вашей организации больше нет необходимости, можно удалить политику привилегированного доступа.</span><span class="sxs-lookup"><span data-stu-id="d29e4-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="d29e4-230">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="d29e4-231">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) с помощью учетных данных для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="d29e4-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d29e4-232">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-232">In the admin center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d29e4-233">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="d29e4-234">Выберите пункт **Настройка политик**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="d29e4-235">Выберите политику, которую нужно удалить, а затем нажмите кнопку **удалить политику**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="d29e4-236">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="d29e4-237">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="d29e4-238">Чтобы удалить политику привилегированного доступа, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d29e4-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="d29e4-239">Отключение привилегированного доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="d29e4-240">При необходимости вы можете отключить управление привилегированным доступом для своей организации.</span><span class="sxs-lookup"><span data-stu-id="d29e4-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="d29e4-241">При отключении привилегированного доступа не удаляются все связанные с ним политики утверждения или группы утверждающих.</span><span class="sxs-lookup"><span data-stu-id="d29e4-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="d29e4-242">В центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d29e4-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="d29e4-243">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя учетные данные для учетной записи администратора в Организации.</span><span class="sxs-lookup"><span data-stu-id="d29e4-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="d29e4-244">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="d29e4-244">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="d29e4-245">Включите разрешение " **требовать утверждения для контроля привилегированного доступа** ".</span><span class="sxs-lookup"><span data-stu-id="d29e4-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="d29e4-246">В PowerShell для управления Exchange</span><span class="sxs-lookup"><span data-stu-id="d29e4-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="d29e4-247">Чтобы отключить привилегированный доступ, выполните следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="d29e4-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
