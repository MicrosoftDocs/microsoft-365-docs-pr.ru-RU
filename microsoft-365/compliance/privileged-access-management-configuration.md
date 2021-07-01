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
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: ''
description: В этой статье вы узнаете больше о впуске и настройке управления привилегированным доступом в Office 365.
ms.openlocfilehash: 13b600c60e1b9c88285ee58efcf80a7ff5ea17fe
ms.sourcegitcommit: 48195345b21b409b175d68acdc25d9f2fc4fc5f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/30/2021
ms.locfileid: "53226123"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="a62f6-103">Начало работы с управлением привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="a62f6-103">Get started with privileged access management</span></span>

<span data-ttu-id="a62f6-104">В этом разделе вы сможете настроить и настроить управление привилегированным доступом в организации.</span><span class="sxs-lookup"><span data-stu-id="a62f6-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="a62f6-105">Вы можете использовать Центр администрирования Microsoft 365 или Exchange PowerShell для управления и использования привилегированного доступа.</span><span class="sxs-lookup"><span data-stu-id="a62f6-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="a62f6-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="a62f6-106">Before you begin</span></span>

<span data-ttu-id="a62f6-107">Перед началом работы с управлением привилегированным доступом необходимо подтвердить Microsoft 365 [подписку](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) и все надстройки.</span><span class="sxs-lookup"><span data-stu-id="a62f6-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="a62f6-108">Чтобы получить доступ к управлению привилегированным доступом и использовать его, организация должна иметь одну из следующих подписок или надстройок:</span><span class="sxs-lookup"><span data-stu-id="a62f6-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="a62f6-109">Microsoft 365 E5 подписки (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="a62f6-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="a62f6-110">Microsoft 365 E3 подписка (Office 365 E3 подписка + Enterprise мобильность и безопасность E3) + Соответствие требованиям Microsoft 365 E5 надстройка</span><span class="sxs-lookup"><span data-stu-id="a62f6-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="a62f6-111">Любая Microsoft 365, Office 365, Exchange, SharePoint или подписка OneDrive для бизнеса + надстройка управления рисками Microsoft 365 E5 инсайдерской системы управления рисками</span><span class="sxs-lookup"><span data-stu-id="a62f6-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="a62f6-112">Microsoft 365 A5 подписки (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="a62f6-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="a62f6-113">Microsoft 365 A3 подписка (или Office 365 A3 подписка + Enterprise мобильность и безопасность A3) + надстройка microsoft A5 Compliance</span><span class="sxs-lookup"><span data-stu-id="a62f6-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="a62f6-114">Любая Microsoft 365, Office 365, Exchange, SharePoint или OneDrive подписки на образование + надстройка Microsoft 365 A5 управления рисками для инсайдеров</span><span class="sxs-lookup"><span data-stu-id="a62f6-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="a62f6-115">Office 365 корпоративный Подписка на E5 (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="a62f6-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="a62f6-116">Office 365 корпоративный Подписка на E3 + Office 365 Advanced Compliance надстройка (больше недоступна для новых подписок, см. примечание)</span><span class="sxs-lookup"><span data-stu-id="a62f6-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="a62f6-117">Пользователи, отдающие и реагирующие на запросы управления привилегированным доступом, должны быть назначены одной из вышеуказанных лицензий.</span><span class="sxs-lookup"><span data-stu-id="a62f6-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="a62f6-118">Office 365 Advanced Compliance больше не продается в качестве независимой подписки.</span><span class="sxs-lookup"><span data-stu-id="a62f6-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="a62f6-119">По истечении срока действия текущих подписок клиенты должны перейти к одной из вышеуказанных подписок, которые содержат те же или дополнительные функции соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a62f6-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="a62f6-120">Если у вас нет существующего плана Office 365 корпоративный E5 и вы хотите попробовать [](/office365/admin/try-or-buy-microsoft-365) управление привилегированным доступом, вы можете добавить [](https://www.microsoft.com/microsoft-365/enterprise) Microsoft 365 к существующей подписке Office 365 или зарегистрироваться на пробную Microsoft 365 корпоративный E5.</span><span class="sxs-lookup"><span data-stu-id="a62f6-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="a62f6-121">Включить и настроить управление привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="a62f6-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="a62f6-122">Выполните следующие действия, чтобы настроить и использовать привилегированный доступ в организации:</span><span class="sxs-lookup"><span data-stu-id="a62f6-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="a62f6-123">Шаг 1. Создание группы утверждения</span><span class="sxs-lookup"><span data-stu-id="a62f6-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="a62f6-124">Прежде чем начать использовать привилегированный доступ, определите, кому необходимы полномочия утверждать входящие запросы на доступ к задачам с повышенными правами и к привилегированным задачам.</span><span class="sxs-lookup"><span data-stu-id="a62f6-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="a62f6-125">Любой пользователь, входящий в группу “Утверждающие”, сможет утверждать запросы на доступ.</span><span class="sxs-lookup"><span data-stu-id="a62f6-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="a62f6-126">Эта группа включена путем создания группы безопасности с поддержкой почты в Office 365.</span><span class="sxs-lookup"><span data-stu-id="a62f6-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="a62f6-127">Шаг 2. Включить привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="a62f6-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="a62f6-128">Необходимо явно включить привилегированный доступ в Office 365 с использованием стандартной группы утверждающих, а также указать набор системных учетных записей, которые требуется исключить из системы управления привилегированным доступом.</span><span class="sxs-lookup"><span data-stu-id="a62f6-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="a62f6-129">Шаг 3. Создание политики доступа</span><span class="sxs-lookup"><span data-stu-id="a62f6-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="a62f6-130">Создав политику утверждения, вы сможете настраивать конкретные требования к утверждению доступа для отдельных задач.</span><span class="sxs-lookup"><span data-stu-id="a62f6-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="a62f6-131">Доступны следующие типы утверждения: **Автоматически** и **Вручную**.</span><span class="sxs-lookup"><span data-stu-id="a62f6-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="a62f6-132">Шаг 4. Отправка и утверждение запросов на привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="a62f6-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="a62f6-133">После включения привилегированного доступа требуется утверждение любой задачи, с которой связана определенная политика утверждения.</span><span class="sxs-lookup"><span data-stu-id="a62f6-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="a62f6-134">Для выполнения задач, включенных в политику утверждения, пользователям необходимо запросить и получить доступ, чтобы у них были разрешения, необходимые для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="a62f6-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="a62f6-135">После утверждения отправитель запроса может выполнить нужную задачу, а привилегированный доступ одобрит и выполнит задачу от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="a62f6-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="a62f6-136">Утверждение действует в течение запрошенного времени (по умолчанию — 4 часа). В этот период отправитель запроса может выполнить нужную задачу несколько раз.</span><span class="sxs-lookup"><span data-stu-id="a62f6-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="a62f6-137">Каждый случай выполнения заносится в журнал и становится доступен для аудита безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="a62f6-137">All such executions are logged and made available for security and compliance auditing.</span></span>

> [!NOTE]
> <span data-ttu-id="a62f6-138">Если вы хотите использовать Exchange PowerShell, чтобы включить и настроить привилегированный доступ, выполните действия в Подключение до [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) с помощью многофакторной проверки подлинности для подключения к Exchange Online PowerShell с учетными данными Office 365.</span><span class="sxs-lookup"><span data-stu-id="a62f6-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="a62f6-139">Не требуется включить многофакторную проверку подлинности для организации, чтобы использовать действия, чтобы включить привилегированный доступ при подключении к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="a62f6-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="a62f6-140">Подключение к многофакторной проверке подлинности создает маркер OAuth, который используется привилегированным доступом для подписания запросов.</span><span class="sxs-lookup"><span data-stu-id="a62f6-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="a62f6-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="a62f6-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="a62f6-142">Шаг 1. Создание группы утверждения</span><span class="sxs-lookup"><span data-stu-id="a62f6-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="a62f6-143">Вопишите [Центр администрирования Microsoft 365](https://admin.microsoft.com) учетные данные для учетной записи администратора в организации.</span><span class="sxs-lookup"><span data-stu-id="a62f6-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="a62f6-144">В Центре администрирования перейдите в **группы**  >  **Добавить группу.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="a62f6-145">Выберите **группу безопасности с** поддержкой почты, а затем выполните **полей "Имя",** **"Групповой** адрес электронной почты" и **"Описание"** для новой группы.</span><span class="sxs-lookup"><span data-stu-id="a62f6-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="a62f6-146">Сохраните группу.</span><span class="sxs-lookup"><span data-stu-id="a62f6-146">Save the group.</span></span> <span data-ttu-id="a62f6-147">Полная настройка группы и ее отображение в центре администрирования Microsoft 365 может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="a62f6-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="a62f6-148">Выберите группу нового утвержденного и выберите **правки,** чтобы добавить пользователей в группу.</span><span class="sxs-lookup"><span data-stu-id="a62f6-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="a62f6-149">Сохраните группу.</span><span class="sxs-lookup"><span data-stu-id="a62f6-149">Save the group.</span></span>

<span data-ttu-id="a62f6-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="a62f6-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="a62f6-151">Шаг 2. Включить привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="a62f6-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="a62f6-152">В центре Microsoft 365 Admin</span><span class="sxs-lookup"><span data-stu-id="a62f6-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="a62f6-153">Вопишитесь [в центр Microsoft 365 Admin с](https://admin.microsoft.com) помощью учетных данных для учетной записи администратора в организации.</span><span class="sxs-lookup"><span data-stu-id="a62f6-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="a62f6-154">В Центре администрирования перейдите в **Параметры**  >  **Org Параметры** безопасности &  >    >  **конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a62f6-155">**Внося необходимые утверждения для управления привилегированных задач.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="a62f6-156">Назначьте группу одобрения, созданную в шаге 1 в качестве группы **одобрений** по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a62f6-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="a62f6-157">**Сохранить** и **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a62f6-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="a62f6-158">В Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a62f6-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="a62f6-159">Чтобы включить привилегированный доступ и назначить группу одобрения, запустите следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a62f6-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="a62f6-160">Пример.</span><span class="sxs-lookup"><span data-stu-id="a62f6-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

> [!NOTE]
> <span data-ttu-id="a62f6-161">Функция системных учетных записей доступна для обеспечения того, чтобы определенные автоматизации в организациях могли работать без зависимости от привилегированного доступа, однако рекомендуется, чтобы такие исключения были исключительными и разрешенные должны регулярно утверждаться и проверяться.</span><span class="sxs-lookup"><span data-stu-id="a62f6-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="a62f6-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="a62f6-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="a62f6-163">Шаг 3. Создание политики доступа</span><span class="sxs-lookup"><span data-stu-id="a62f6-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="a62f6-164">Вы можете создать и настроить до 30 политик привилегированного доступа для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="a62f6-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="a62f6-165">В центре Microsoft 365 Admin</span><span class="sxs-lookup"><span data-stu-id="a62f6-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="a62f6-166">Вопишитесь [в центр Microsoft 365 Admin с](https://admin.microsoft.com) помощью учетных данных для учетной записи администратора в организации.</span><span class="sxs-lookup"><span data-stu-id="a62f6-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="a62f6-167">В Центре администрирования перейдите в **Параметры**  >  **Org Параметры** безопасности &  >    >  **конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a62f6-168">Выберите **Управление политиками и запросами доступа.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a62f6-169">Выберите **Настройка политик и** выберите Добавить **политику.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="a62f6-170">Из выпадаемого поля выберите соответствующие значения для организации:</span><span class="sxs-lookup"><span data-stu-id="a62f6-170">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="a62f6-171">**Тип политики**: задача, роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="a62f6-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="a62f6-172">**Область действия политики**: Exchange</span><span class="sxs-lookup"><span data-stu-id="a62f6-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="a62f6-173">**Имя политики**: выберите из доступных политик</span><span class="sxs-lookup"><span data-stu-id="a62f6-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="a62f6-174">**Тип утверждения**: вручную или автоматически</span><span class="sxs-lookup"><span data-stu-id="a62f6-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="a62f6-175">**Группа утверждения**: выберите группу утверждающих, созданную на шаге 1</span><span class="sxs-lookup"><span data-stu-id="a62f6-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="a62f6-176">Выберите **Создать и** **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a62f6-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="a62f6-177">Для полной настройки и включения политики может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="a62f6-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="a62f6-178">В Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a62f6-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="a62f6-179">Чтобы создать и определить политику утверждения, запустите следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a62f6-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="a62f6-180">Пример.</span><span class="sxs-lookup"><span data-stu-id="a62f6-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="a62f6-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="a62f6-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="a62f6-182">Шаг 4. Отправка и утверждение запросов на привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="a62f6-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="a62f6-183">Запрос разрешения на повышение прав для выполнения привилегированных задач</span><span class="sxs-lookup"><span data-stu-id="a62f6-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="a62f6-184">Запросы на привилегированный доступ действительны в течение 24 часов после отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="a62f6-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="a62f6-185">Если не утверждено или отклонено, срок действия запросов истекает, а доступ не утверждается.</span><span class="sxs-lookup"><span data-stu-id="a62f6-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="a62f6-186">В центре Microsoft 365 Admin</span><span class="sxs-lookup"><span data-stu-id="a62f6-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="a62f6-187">Вопишитесь [в центр Microsoft 365 Admin с](https://admin.microsoft.com) помощью учетных данных.</span><span class="sxs-lookup"><span data-stu-id="a62f6-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="a62f6-188">В Центре администрирования перейдите в **Параметры**  >  **Org Параметры** безопасности &  >    >  **конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a62f6-189">Выберите **Управление политиками и запросами доступа.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a62f6-190">Выберите **новый запрос**.</span><span class="sxs-lookup"><span data-stu-id="a62f6-190">Select **New request**.</span></span> <span data-ttu-id="a62f6-191">Из выпадаемого поля выберите соответствующие значения для организации:</span><span class="sxs-lookup"><span data-stu-id="a62f6-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="a62f6-192">**Тип запроса**: задача, роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="a62f6-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="a62f6-193">**Область действия запроса**: Exchange</span><span class="sxs-lookup"><span data-stu-id="a62f6-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="a62f6-194">**Запрос на**: выберите из доступных политик</span><span class="sxs-lookup"><span data-stu-id="a62f6-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="a62f6-195">**Продолжительность (часы)**: количество часов запрошенного доступа.</span><span class="sxs-lookup"><span data-stu-id="a62f6-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="a62f6-196">Количество часов, которые можно запросить, не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="a62f6-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="a62f6-197">**Комментарии.** Текстовое поле для комментариев, связанных с запросом на доступ</span><span class="sxs-lookup"><span data-stu-id="a62f6-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="a62f6-198">Выберите **Сохранить и** **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a62f6-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="a62f6-199">Ваш запрос будет отправлен группе одобрения по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="a62f6-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="a62f6-200">В Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a62f6-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="a62f6-201">Запустите следующую команду в Exchange Online PowerShell, чтобы создать и отправить запрос на утверждение в группу одобрения:</span><span class="sxs-lookup"><span data-stu-id="a62f6-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="a62f6-202">Пример.</span><span class="sxs-lookup"><span data-stu-id="a62f6-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="a62f6-203">Проверка статуса запросов на повышение прав</span><span class="sxs-lookup"><span data-stu-id="a62f6-203">View status of elevation requests</span></span>

<span data-ttu-id="a62f6-204">После создания запроса на утверждение состояние запроса на повышение можно просмотреть в центре администрирования или в Exchange PowerShell с помощью связанного с ИД запроса.</span><span class="sxs-lookup"><span data-stu-id="a62f6-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="a62f6-205">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a62f6-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a62f6-206">Вопишите [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными.</span><span class="sxs-lookup"><span data-stu-id="a62f6-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="a62f6-207">В центре администрирования перейдите в **Параметры**  >  **Org Параметры** безопасности &  >    >  **конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a62f6-208">Выберите **Управление политиками и запросами доступа.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a62f6-209">Выберите **Представление** для фильтрации отправленных запросов путем **отложенных,** **утвержденных,** **отклоненных** или **клиентского состояния lockbox.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="a62f6-210">В Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a62f6-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="a62f6-211">Запустите следующую команду в Exchange Online PowerShell, чтобы просмотреть состояние запроса на утверждение для определенного ID запроса:</span><span class="sxs-lookup"><span data-stu-id="a62f6-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="a62f6-212">Пример.</span><span class="sxs-lookup"><span data-stu-id="a62f6-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="a62f6-213">Утверждение запроса на авторизацию высоты</span><span class="sxs-lookup"><span data-stu-id="a62f6-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="a62f6-214">Когда создается запрос на утверждение, члены соответствующей группы утверждений получают уведомление по электронной почте и могут утверждать запрос, связанный с ИД запроса.</span><span class="sxs-lookup"><span data-stu-id="a62f6-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="a62f6-215">Запрашивающая сторона получает уведомление об утверждении или отклонении запроса по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="a62f6-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="a62f6-216">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a62f6-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a62f6-217">Вопишите [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными.</span><span class="sxs-lookup"><span data-stu-id="a62f6-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="a62f6-218">В центре администрирования перейдите в **Параметры**  >  **Org Параметры** безопасности &  >    >  **конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a62f6-219">Выберите **Управление политиками и запросами доступа.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a62f6-220">Выберите указанный запрос, чтобы просмотреть сведения и принять меры по запросу.</span><span class="sxs-lookup"><span data-stu-id="a62f6-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="a62f6-221">Выберите **Утверждение** для утверждения запроса или выберите **Отказ** для отказа в запросе.</span><span class="sxs-lookup"><span data-stu-id="a62f6-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="a62f6-222">Ранее утвержденные запросы могут иметь доступ отозван, выбрав **Revoke**.</span><span class="sxs-lookup"><span data-stu-id="a62f6-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="a62f6-223">В Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a62f6-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="a62f6-224">Чтобы утвердить запрос на авторизацию высоты, запустите следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a62f6-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="a62f6-225">Пример.</span><span class="sxs-lookup"><span data-stu-id="a62f6-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="a62f6-226">Чтобы отказать в запросе на авторизацию высоты, запустите следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="a62f6-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="a62f6-227">Пример.</span><span class="sxs-lookup"><span data-stu-id="a62f6-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="a62f6-228">Удаление политики привилегированного доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="a62f6-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="a62f6-229">Если она больше не требуется в организации, можно удалить политику привилегированного доступа.</span><span class="sxs-lookup"><span data-stu-id="a62f6-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="a62f6-230">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a62f6-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a62f6-231">Вопишите [Центр администрирования Microsoft 365](https://admin.microsoft.com) учетные данные для учетной записи администратора в организации.</span><span class="sxs-lookup"><span data-stu-id="a62f6-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="a62f6-232">В центре администрирования перейдите в **Параметры**  >  **Org Параметры** безопасности &  >    >  **конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a62f6-233">Выберите **Управление политиками и запросами доступа.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="a62f6-234">Выберите **Настройка политик**.</span><span class="sxs-lookup"><span data-stu-id="a62f6-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="a62f6-235">Выберите политику, которая необходимо удалить, а затем выберите **Политику удаления.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="a62f6-236">Нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="a62f6-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="a62f6-237">В Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a62f6-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="a62f6-238">Чтобы удалить политику привилегированного доступа, запустите следующую команду в Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="a62f6-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="a62f6-239">Отключение привилегированного доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="a62f6-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="a62f6-240">При необходимости можно отключить управление привилегированным доступом для организации.</span><span class="sxs-lookup"><span data-stu-id="a62f6-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="a62f6-241">Отключение привилегированного доступа не удаляет связанные политики утверждения или группы утверждений.</span><span class="sxs-lookup"><span data-stu-id="a62f6-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="a62f6-242">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a62f6-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="a62f6-243">Вопишите [Центр администрирования Microsoft 365](https://admin.microsoft.com) с учетными данными для учетной записи администратора в организации.</span><span class="sxs-lookup"><span data-stu-id="a62f6-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="a62f6-244">В Центре администрирования перейдите в **Параметры**  >  **Org Параметры** безопасности &  >    >  **конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="a62f6-245">Включить **необходимые утверждения для управления привилегированным доступом.**</span><span class="sxs-lookup"><span data-stu-id="a62f6-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="a62f6-246">В Exchange PowerShell</span><span class="sxs-lookup"><span data-stu-id="a62f6-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="a62f6-247">Чтобы отключить привилегированный доступ, запустите следующую команду в Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="a62f6-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
