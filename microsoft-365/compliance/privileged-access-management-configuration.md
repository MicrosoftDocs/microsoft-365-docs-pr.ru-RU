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
description: В этой статье вы узнаете, как активировать и настроить управление привилегированным доступом в Office 365.
ms.openlocfilehash: 0b8d79c3012ecd321d7b00c1566aa557077d55f1
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126536"
---
# <a name="get-started-with-privileged-access-management"></a><span data-ttu-id="69d3f-103">Начало работы с управлением привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="69d3f-103">Get started with privileged access management</span></span>

<span data-ttu-id="69d3f-104">В этом разделе вы можете включить и настроить управление привилегированным доступом в организации.</span><span class="sxs-lookup"><span data-stu-id="69d3f-104">This topic guides you through enabling and configuring privileged access management in your organization.</span></span> <span data-ttu-id="69d3f-105">Для управления привилегированным доступом и использования его можно использовать Центр администрирования Microsoft 365 или Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="69d3f-105">You can use either the Microsoft 365 admin center or Exchange Management PowerShell to manage and use privileged access.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="69d3f-106">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="69d3f-106">Before you begin</span></span>

<span data-ttu-id="69d3f-107">Перед началом работы с управлением привилегированным доступом необходимо подтвердить подписку [на Microsoft 365](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) и все надстройки.</span><span class="sxs-lookup"><span data-stu-id="69d3f-107">Before you get started with privileged access management, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="69d3f-108">Чтобы получить доступ к управлению привилегированным доступом и использовать его, в организации должна быть одна из следующих подписок или надстройки:</span><span class="sxs-lookup"><span data-stu-id="69d3f-108">To access and use privileged access management, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="69d3f-109">Подписка Microsoft 365 E5 (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="69d3f-109">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="69d3f-110">Подписка Microsoft 365 E3 (или подписка на Office 365 E3 + Enterprise Mobility and Security E3) + надстройка соответствия требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="69d3f-110">Microsoft 365 E3 subscription (or Office 365 E3 subscription + Enterprise Mobility and Security E3 subscription) + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="69d3f-111">Любая подписка на Microsoft 365, Office 365, Exchange, SharePoint или OneDrive для бизнеса + надстройка Microsoft 365 E5 Insider Risk Management</span><span class="sxs-lookup"><span data-stu-id="69d3f-111">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Business subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>  
- <span data-ttu-id="69d3f-112">Подписка на Microsoft 365 A5 (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="69d3f-112">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="69d3f-113">Подписка на Microsoft 365 A3 (или подписка на Office 365 A3 + Enterprise Mobility and Security A3) + надстройка соответствия Требованиям Microsoft A5</span><span class="sxs-lookup"><span data-stu-id="69d3f-113">Microsoft 365 A3 subscription (or Office 365 A3 subscription + Enterprise Mobility and Security A3 subscription) + the Microsoft A5 Compliance add-on</span></span>
- <span data-ttu-id="69d3f-114">Любая подписка на Microsoft 365, Office 365, Exchange, SharePoint или OneDrive для образования + надстройка Microsoft 365 A5 Insider Risk Management</span><span class="sxs-lookup"><span data-stu-id="69d3f-114">Any Microsoft 365, Office 365, Exchange, SharePoint, or OneDrive for Education subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="69d3f-115">Подписка на Office 365 корпоративный E5 (платная или пробная версия)</span><span class="sxs-lookup"><span data-stu-id="69d3f-115">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="69d3f-116">Подписка на Office 365 корпоративный E3 + надстройка Office 365 Advanced Compliance (больше недоступна для новых подписок, см. примечание)</span><span class="sxs-lookup"><span data-stu-id="69d3f-116">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="69d3f-117">Пользователям, которые отправили запросы на управление привилегированным доступом и отвечали на них, должна быть назначена одна из вышеуказанных лицензий.</span><span class="sxs-lookup"><span data-stu-id="69d3f-117">Users submitting and responding to privileged access management requests must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="69d3f-118">Office 365 Advanced Compliance больше не продается в качестве автономных подписок.</span><span class="sxs-lookup"><span data-stu-id="69d3f-118">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="69d3f-119">По истечении срока действия текущих подписок клиенты должны перейти на одну из вышеперечисленной подписки, которая содержит те же или дополнительные функции соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="69d3f-119">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="69d3f-120">Если у вас нет плана Office 365 корпоративный E5 и вы хотите попробовать управление привилегированным доступом, вы можете [](https://www.microsoft.com/microsoft-365/enterprise) добавить [Microsoft 365](/office365/admin/try-or-buy-microsoft-365) к существующей подписке на Office 365 или зарегистрироваться для получения пробной подписки на Microsoft 365 корпоративный E5.</span><span class="sxs-lookup"><span data-stu-id="69d3f-120">If you don't have an existing Office 365 Enterprise E5 plan and want to try privileged access management, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing Office 365 subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Microsoft 365 Enterprise E5.</span></span>

## <a name="enable-and-configure-privileged-access-management"></a><span data-ttu-id="69d3f-121">Включить и настроить управление привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="69d3f-121">Enable and configure privileged access management</span></span>

<span data-ttu-id="69d3f-122">Чтобы настроить и использовать привилегированный доступ в организации, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="69d3f-122">Follow these steps to set up and use privileged access in your organization:</span></span>

- [<span data-ttu-id="69d3f-123">Шаг 1. Создание группы утвержденного</span><span class="sxs-lookup"><span data-stu-id="69d3f-123">Step 1: Create an approver's group</span></span>](privileged-access-management-configuration.md#step1)

    <span data-ttu-id="69d3f-124">Прежде чем начать использовать привилегированный доступ, определите, кому требуется разрешение для входящих запросов на доступ к задачам с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="69d3f-124">Before you start using privilege access, determine who needs approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="69d3f-125">Любой пользователь, в который входит группа "Утверждение", может утверждать запросы на доступ.</span><span class="sxs-lookup"><span data-stu-id="69d3f-125">Any user who is part of the Approvers' group is able to approve access requests.</span></span> <span data-ttu-id="69d3f-126">Эта группа включена путем создания группы безопасности с включенной поддержкой почты в Office 365.</span><span class="sxs-lookup"><span data-stu-id="69d3f-126">This group is enabled by creating a mail-enabled security group in Office 365.</span></span>

- [<span data-ttu-id="69d3f-127">Шаг 2. Включить привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="69d3f-127">Step 2: Enable privileged access</span></span>](privileged-access-management-configuration.md#step2)

    <span data-ttu-id="69d3f-128">Привилегированный доступ должен быть явно включен в Office 365 с группой утвержденных по умолчанию, включая набор системных учетных записей, которые необходимо исключить из управления привилегированным доступом управления доступом.</span><span class="sxs-lookup"><span data-stu-id="69d3f-128">Privileged access must be explicitly enabled in Office 365 with the default approver group, including a set of system accounts that you want excluded from the privileged access management access control.</span></span>

- [<span data-ttu-id="69d3f-129">Шаг 3. Создание политики доступа</span><span class="sxs-lookup"><span data-stu-id="69d3f-129">Step 3: Create an access policy</span></span>](privileged-access-management-configuration.md#step3)

    <span data-ttu-id="69d3f-130">Создание политики утверждения позволяет определить конкретные требования утверждения, определенные для отдельных задач.</span><span class="sxs-lookup"><span data-stu-id="69d3f-130">Creating an approval policy allows you to define the specific approval requirements scoped at individual tasks.</span></span> <span data-ttu-id="69d3f-131">Возможные типы утверждения: **Auto** или **Manual**.</span><span class="sxs-lookup"><span data-stu-id="69d3f-131">The approval type options are **Auto** or **Manual**.</span></span>

- [<span data-ttu-id="69d3f-132">Шаг 4. Отправка и утверждение запросов на привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="69d3f-132">Step 4: Submit/approve privileged access requests</span></span>](privileged-access-management-configuration.md#step4)

    <span data-ttu-id="69d3f-133">После включения привилегированный доступ требует утверждения для любой задачи, для задачи с определенной политикой утверждения.</span><span class="sxs-lookup"><span data-stu-id="69d3f-133">Once enabled, privileged access requires approvals for any task that has an associated approval policy defined.</span></span> <span data-ttu-id="69d3f-134">Для задач, включенных в политику утверждения, пользователи должны запрашивать и получать разрешение на доступ, чтобы иметь разрешения, необходимые для выполнения задачи.</span><span class="sxs-lookup"><span data-stu-id="69d3f-134">For tasks included in an approval policy, users must request and be granted access approval to have permissions necessary to execute the task.</span></span>

<span data-ttu-id="69d3f-135">После утверждения запрашивающий пользователь может выполнить предполагаемую задачу, а привилегированный доступ разрешит и выполнит задачу от имени пользователя.</span><span class="sxs-lookup"><span data-stu-id="69d3f-135">After approval is granted, the requesting user can execute the intended task and privileged access will authorize and execute the task on behalf of the user.</span></span> <span data-ttu-id="69d3f-136">Утверждение остается действительным в течение запрашиваемой длительности (по умолчанию — 4 часа), в течение которого запрашивающая может выполнить предполагаемую задачу несколько раз.</span><span class="sxs-lookup"><span data-stu-id="69d3f-136">The approval remains valid for the requested duration (default duration is 4 hours), during which the requester can execute the intended task multiple times.</span></span> <span data-ttu-id="69d3f-137">Все такие исполняемые данные регистрируются в журнале и доступны для аудита безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="69d3f-137">All such executions are logged and made available for security and compliance auditing.</span></span> 

>[!NOTE]
><span data-ttu-id="69d3f-138">Если вы хотите включить и настроить привилегированный доступ с помощью Exchange Management PowerShell, выполните действия, которые необходимо предпринять при подключении к [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) с помощью многофакторной проверки подлинности, чтобы подключиться к Exchange Online PowerShell с помощью учетных данных Office 365.</span><span class="sxs-lookup"><span data-stu-id="69d3f-138">If you want to use Exchange Management PowerShell to enable and configure privileged access, follow the steps in [Connect to Exchange Online PowerShell using Multi-Factor authentication](/powershell/exchange/connect-to-exchange-online-powershell#connect-to-exchange-online-powershell-using-mfa) to connect to Exchange Online PowerShell with your Office 365 credentials.</span></span> <span data-ttu-id="69d3f-139">Чтобы включить привилегированный доступ при подключении к Exchange Online PowerShell, не требуется включить многофакторную проверку подлинности для организации.</span><span class="sxs-lookup"><span data-stu-id="69d3f-139">You do not need to enable multi-factor authentication for your organization to use the steps to enable privileged access while connecting to Exchange Online PowerShell.</span></span> <span data-ttu-id="69d3f-140">При подключении с многофакторной проверкой подлинности создается маркер OAuth, используемый привилегированным доступом для подписи запросов.</span><span class="sxs-lookup"><span data-stu-id="69d3f-140">Connecting with multi-factor authentication creates an OAuth token that is used by privileged access for signing your requests.</span></span>

<span data-ttu-id="69d3f-141"><a name="step1"> </a></span><span class="sxs-lookup"><span data-stu-id="69d3f-141"><a name="step1"> </a></span></span>

## <a name="step-1-create-an-approvers-group"></a><span data-ttu-id="69d3f-142">Шаг 1. Создание группы утвержденного</span><span class="sxs-lookup"><span data-stu-id="69d3f-142">Step 1: Create an approver's group</span></span>

1. <span data-ttu-id="69d3f-143">Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span><span class="sxs-lookup"><span data-stu-id="69d3f-143">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="69d3f-144">В Центре администрирования перейдите в **группу**  >  **"Добавить группу".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-144">In the Admin Center, go to **Groups** > **Add a group**.</span></span>

3. <span data-ttu-id="69d3f-145">Выберите **группу безопасности** с включенной поддержкой почты  и заполнив поля **"Имя",** **"Адрес** электронной почты группы" и "Описание" для новой группы.</span><span class="sxs-lookup"><span data-stu-id="69d3f-145">Select **mail-enabled security group** and then complete the **Name**, **Group email address**, and **Description** fields for the new group.</span></span>

4. <span data-ttu-id="69d3f-146">Сохраните группу.</span><span class="sxs-lookup"><span data-stu-id="69d3f-146">Save the group.</span></span> <span data-ttu-id="69d3f-147">Для полной настройки группы и ее появления в Центре администрирования Microsoft 365 может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="69d3f-147">It may take a few minutes for the group to be fully configured and to appear in the Microsoft 365 admin center.</span></span>

5. <span data-ttu-id="69d3f-148">Выберите группу нового утвержденного и выберите **"Изменить",** чтобы добавить пользователей в группу.</span><span class="sxs-lookup"><span data-stu-id="69d3f-148">Select the new approver's group and select **edit** to add users to the group.</span></span>

6. <span data-ttu-id="69d3f-149">Сохраните группу.</span><span class="sxs-lookup"><span data-stu-id="69d3f-149">Save the group.</span></span>

<span data-ttu-id="69d3f-150"><a name="step2"> </a></span><span class="sxs-lookup"><span data-stu-id="69d3f-150"><a name="step2"> </a></span></span>

## <a name="step-2-enable-privileged-access"></a><span data-ttu-id="69d3f-151">Шаг 2. Включить привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="69d3f-151">Step 2: Enable privileged access</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="69d3f-152">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-152">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="69d3f-153">Во sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span><span class="sxs-lookup"><span data-stu-id="69d3f-153">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="69d3f-154">В Центре администрирования перейдите **к** параметрам безопасности  >  **параметров** организации &  >    >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-154">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="69d3f-155">Включить утверждение **"Требовать" для управления привилегированными задачами.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-155">Enable the **Require approvals for privileged tasks** control.</span></span>

4. <span data-ttu-id="69d3f-156">Назначьте группу утвержденного, созданную на шаге 1, в качестве группы "По **умолчанию".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-156">Assign the approver's group you created in Step 1 as the **Default approvers group**.</span></span>

5. <span data-ttu-id="69d3f-157">**Сохранить** и **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="69d3f-157">**Save** and **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="69d3f-158">В Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d3f-158">In Exchange Management PowerShell</span></span>

<span data-ttu-id="69d3f-159">Чтобы включить привилегированный доступ и назначить группу утвержденного, в Exchange Online PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="69d3f-159">To enable privileged access and to assign the approver's group, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup '<default approver group>' -SystemAccounts @('<systemAccountUPN1>','<systemAccountUPN2>')
```

<span data-ttu-id="69d3f-160">Пример.</span><span class="sxs-lookup"><span data-stu-id="69d3f-160">Example:</span></span>

```PowerShell
Enable-ElevatedAccessControl -AdminGroup 'pamapprovers@fabrikam.onmicrosoft.com' -SystemAccounts @('sys1@fabrikamorg.onmicrosoft.com', 'sys2@fabrikamorg.onmicrosoft.com')
```

>[!NOTE]
><span data-ttu-id="69d3f-161">Функция системных учетных записей обеспечивает работу определенных автоматизаций в организациях без зависимости от привилегированного доступа, однако рекомендуется, чтобы такие исключения были исключительными и их следует утверждать и регулярно проверять.</span><span class="sxs-lookup"><span data-stu-id="69d3f-161">System accounts feature is made available to ensure certain automations within your organizations can work without dependency on privileged access, however it is recommended that such exclusions be exceptional and those allowed should be approved and audited regularly.</span></span>

<span data-ttu-id="69d3f-162"><a name="step3"> </a></span><span class="sxs-lookup"><span data-stu-id="69d3f-162"><a name="step3"> </a></span></span>

## <a name="step-3-create-an-access-policy"></a><span data-ttu-id="69d3f-163">Шаг 3. Создание политики доступа</span><span class="sxs-lookup"><span data-stu-id="69d3f-163">Step 3: Create an access policy</span></span>

<span data-ttu-id="69d3f-164">В организации можно создать и настроить до 30 политик привилегированного доступа.</span><span class="sxs-lookup"><span data-stu-id="69d3f-164">You can create and configure up to 30 privileged access policies for your organization.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="69d3f-165">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-165">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="69d3f-166">Во sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span><span class="sxs-lookup"><span data-stu-id="69d3f-166">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="69d3f-167">В Центре администрирования перейдите **к** параметрам безопасности  >  **параметров** организации &  >    >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-167">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="69d3f-168">Выберите **"Управление политиками и запросами доступа".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-168">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="69d3f-169">Выберите **"Настроить политики" и** **"Добавить политику".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-169">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="69d3f-170">В полях в выпадаемом поле выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="69d3f-170">From the drop-down fields, select the appropriate values for your organization:</span></span>
    
    <span data-ttu-id="69d3f-171">**Тип политики:** задача, роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="69d3f-171">**Policy type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="69d3f-172">**Область политики**: Exchange</span><span class="sxs-lookup"><span data-stu-id="69d3f-172">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="69d3f-173">**Имя политики:** Выберите из доступных политик</span><span class="sxs-lookup"><span data-stu-id="69d3f-173">**Policy name**: Select from the available policies</span></span>

    <span data-ttu-id="69d3f-174">**Тип утверждения:** ручной или автоматический</span><span class="sxs-lookup"><span data-stu-id="69d3f-174">**Approval type**: Manual or Auto</span></span>

    <span data-ttu-id="69d3f-175">**Группа утверждения:** выберите группу утвержденных, созданную на шаге 1</span><span class="sxs-lookup"><span data-stu-id="69d3f-175">**Approval group**: Select the approvers group created in Step 1</span></span>

6. <span data-ttu-id="69d3f-176">Выберите **"Создать",** а затем **закройте.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-176">Select **Create** and then **Close**.</span></span> <span data-ttu-id="69d3f-177">Для полной настройки и включения политики может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="69d3f-177">It may take a few minutes for the policy to be fully configured and enabled.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="69d3f-178">В Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d3f-178">In Exchange Management PowerShell</span></span>

<span data-ttu-id="69d3f-179">Чтобы создать и определить политику утверждения, в Exchange Online PowerShell запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="69d3f-179">To create and define an approval policy, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\<exchange management cmdlet name>' -ApprovalType <Manual, Auto> -ApproverGroup '<default/custom approver group>'
```

<span data-ttu-id="69d3f-180">Пример.</span><span class="sxs-lookup"><span data-stu-id="69d3f-180">Example:</span></span>

```PowerShell
New-ElevatedAccessApprovalPolicy -Task 'Exchange\New-MoveRequest' -ApprovalType Manual -ApproverGroup 'mbmanagers@fabrikamorg.onmicrosoft.com'
```

<span data-ttu-id="69d3f-181"><a name="step4"> </a></span><span class="sxs-lookup"><span data-stu-id="69d3f-181"><a name="step4"> </a></span></span>

## <a name="step-4-submitapprove-privileged-access-requests"></a><span data-ttu-id="69d3f-182">Шаг 4. Отправка и утверждение запросов на привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="69d3f-182">Step 4: Submit/approve privileged access requests</span></span>

### <a name="requesting-elevation-authorization-to-execute-privileged-tasks"></a><span data-ttu-id="69d3f-183">Запрос авторизации повышения прав для выполнения привилегированных задач</span><span class="sxs-lookup"><span data-stu-id="69d3f-183">Requesting elevation authorization to execute privileged tasks</span></span>

<span data-ttu-id="69d3f-184">Запросы на привилегированный доступ действительны в течение 24 часов после отправки запроса.</span><span class="sxs-lookup"><span data-stu-id="69d3f-184">Requests for privileged access are valid for up to 24 hours after the request is submitted.</span></span> <span data-ttu-id="69d3f-185">Если запросы не утверждены или отклонены, срок действия запросов истекает, а доступ не утверждается.</span><span class="sxs-lookup"><span data-stu-id="69d3f-185">If not approved or denied, the requests expire and access is not approved.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="69d3f-186">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-186">In the Microsoft 365 Admin Center</span></span>

1. <span data-ttu-id="69d3f-187">Во sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span><span class="sxs-lookup"><span data-stu-id="69d3f-187">Sign into the [Microsoft 365 Admin Center](https://admin.microsoft.com) using your credentials.</span></span>

2. <span data-ttu-id="69d3f-188">В Центре администрирования перейдите к параметрам безопасности параметров  >    >  **организации &**  >  **конфиденциальности.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-188">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="69d3f-189">Выберите **"Управление политиками и запросами доступа".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-189">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="69d3f-190">Выберите **новый запрос.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-190">Select **New request**.</span></span> <span data-ttu-id="69d3f-191">В полях в выпадаемом поле выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="69d3f-191">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="69d3f-192">**Тип запроса:** задача, роль или группа ролей</span><span class="sxs-lookup"><span data-stu-id="69d3f-192">**Request type**: Task, Role, or Role Group</span></span>

    <span data-ttu-id="69d3f-193">**Область запроса**: Exchange</span><span class="sxs-lookup"><span data-stu-id="69d3f-193">**Request scope**: Exchange</span></span>

    <span data-ttu-id="69d3f-194">**Запрос :** выберите из доступных политик</span><span class="sxs-lookup"><span data-stu-id="69d3f-194">**Request for**: Select from the available policies</span></span>

    <span data-ttu-id="69d3f-195">**Продолжительность (часы)**: количество часов запрашиваемого доступа.</span><span class="sxs-lookup"><span data-stu-id="69d3f-195">**Duration (hours)**: Number of hours of requested access.</span></span> <span data-ttu-id="69d3f-196">Количество часов, которое можно запросить, не ограничивается.</span><span class="sxs-lookup"><span data-stu-id="69d3f-196">There isn't a limit on the number of hours that can be requested.</span></span>

    <span data-ttu-id="69d3f-197">**Комментарии:** текстовое поле для комментариев, связанных с вашим запросом на доступ</span><span class="sxs-lookup"><span data-stu-id="69d3f-197">**Comments**: Text field for comments related to your access request</span></span>

5. <span data-ttu-id="69d3f-198">Выберите **"Сохранить"** и **"Закрыть"**</span><span class="sxs-lookup"><span data-stu-id="69d3f-198">Select **Save** and then **Close**.</span></span> <span data-ttu-id="69d3f-199">Ваш запрос будет отправлен группе утвержденного по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="69d3f-199">Your request will be sent to the approver's group via email.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="69d3f-200">В Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d3f-200">In Exchange Management PowerShell</span></span>

<span data-ttu-id="69d3f-201">Запустите следующую команду в Exchange Online PowerShell, чтобы создать и отправить запрос на утверждение группе утверждаю стороны:</span><span class="sxs-lookup"><span data-stu-id="69d3f-201">Run the following command in Exchange Online PowerShell to create and submit an approval request to the approver's group:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\<exchange management cmdlet name>' -Reason '<appropriate reason>' -DurationHours <duration in hours>
```

<span data-ttu-id="69d3f-202">Пример.</span><span class="sxs-lookup"><span data-stu-id="69d3f-202">Example:</span></span>

```PowerShell
New-ElevatedAccessRequest -Task 'Exchange\New-MoveRequest' -Reason 'Attempting to fix the user mailbox error' -DurationHours 4
```

### <a name="view-status-of-elevation-requests"></a><span data-ttu-id="69d3f-203">Просмотр состояния запросов на повышение прав</span><span class="sxs-lookup"><span data-stu-id="69d3f-203">View status of elevation requests</span></span>

<span data-ttu-id="69d3f-204">После создания запроса на утверждение состояние запроса на повышение прав можно просмотреть в Центре администрирования или в PowerShell управления Exchange с помощью связанного с ИД запроса.</span><span class="sxs-lookup"><span data-stu-id="69d3f-204">After an approval request is created, elevation request status can be reviewed in the admin center or in Exchange Management PowerShell using the associated with request ID.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="69d3f-205">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-205">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="69d3f-206">Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span><span class="sxs-lookup"><span data-stu-id="69d3f-206">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="69d3f-207">В Центре администрирования перейдите к параметрам безопасности  >  **параметров**  >  **организации &**  >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-207">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="69d3f-208">Выберите **"Управление политиками и запросами доступа".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-208">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="69d3f-209">Выберите **"Представление",** чтобы отфильтровать отправленные запросы по состояниям "Ожидание", **"Утверждено",**"Отклонено" или "Блокировка **клиента".**  </span><span class="sxs-lookup"><span data-stu-id="69d3f-209">Select **View** to filter submitted requests by **Pending**, **Approved**, **Denied**, or **Customer Lockbox** status.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="69d3f-210">В Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d3f-210">In Exchange Management PowerShell</span></span>

<span data-ttu-id="69d3f-211">Чтобы просмотреть состояние запроса на утверждение для определенного ИД запроса, запустите следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="69d3f-211">Run the following command in Exchange Online PowerShell to view an approval request status for a specific request ID:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity <request ID> | select RequestStatus
```

<span data-ttu-id="69d3f-212">Пример.</span><span class="sxs-lookup"><span data-stu-id="69d3f-212">Example:</span></span>

```PowerShell
Get-ElevatedAccessRequest -Identity 28560ed0-419d-4cc3-8f5b-603911cbd450 | select RequestStatus
```

### <a name="approving-an-elevation-authorization-request"></a><span data-ttu-id="69d3f-213">Утверждение запроса на авторизацию повышения прав</span><span class="sxs-lookup"><span data-stu-id="69d3f-213">Approving an elevation authorization request</span></span>

<span data-ttu-id="69d3f-214">После создания запроса на утверждение члены соответствующей группы утверждения получают уведомление по электронной почте и могут утвердить запрос, связанный с ИД запроса.</span><span class="sxs-lookup"><span data-stu-id="69d3f-214">When an approval request is created, members of the relevant approver group receive an email notification and can approve the request associated with the request ID.</span></span> <span data-ttu-id="69d3f-215">Запросиватель уведомлен об утверждении или отказе в запросе по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="69d3f-215">The requestor is notified of the request approval or denial via email message.</span></span>

#### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="69d3f-216">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-216">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="69d3f-217">Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span><span class="sxs-lookup"><span data-stu-id="69d3f-217">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with your credentials.</span></span>

2. <span data-ttu-id="69d3f-218">В Центре администрирования перейдите к параметрам безопасности  >  **параметров**  >  **организации &**  >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-218">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="69d3f-219">Выберите **"Управление политиками и запросами доступа".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-219">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="69d3f-220">Выберите указанный запрос, чтобы просмотреть сведения и принять меры по запросу.</span><span class="sxs-lookup"><span data-stu-id="69d3f-220">Select a listed request to view the details and to take action on the request.</span></span>

5. <span data-ttu-id="69d3f-221">Выберите **"Утвердить",** чтобы утвердить запрос, или выберите **"Запретить"** для отказа в запросе.</span><span class="sxs-lookup"><span data-stu-id="69d3f-221">Select **Approve** to approve the request or select **Deny** to deny the request.</span></span> <span data-ttu-id="69d3f-222">Ранее утвержденные запросы могут иметь доступ отозван, выбрав **"Отзыв".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-222">Previously approved requests can have access revoked by selecting **Revoke**.</span></span>

#### <a name="in-exchange-management-powershell"></a><span data-ttu-id="69d3f-223">В Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d3f-223">In Exchange Management PowerShell</span></span>

<span data-ttu-id="69d3f-224">Чтобы утвердить запрос на повышение прав, запустите следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="69d3f-224">To approve an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId <request id> -Comment '<approval comment>'
```

<span data-ttu-id="69d3f-225">Пример.</span><span class="sxs-lookup"><span data-stu-id="69d3f-225">Example:</span></span>

```PowerShell
Approve-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<approval comment>'
```

<span data-ttu-id="69d3f-226">Чтобы запретить запрос на повышение прав, запустите следующую команду в Exchange Online PowerShell:</span><span class="sxs-lookup"><span data-stu-id="69d3f-226">To deny an elevation authorization request, run the following command in Exchange Online PowerShell:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId <request id> -Comment '<denial comment>'
```

<span data-ttu-id="69d3f-227">Пример.</span><span class="sxs-lookup"><span data-stu-id="69d3f-227">Example:</span></span>

```PowerShell
Deny-ElevatedAccessRequest -RequestId a4bc1bdf-00a1-42b4-be65-b6c63d6be279 -Comment '<denial comment>'
```

## <a name="delete-a-privileged-access-policy-in-office-365"></a><span data-ttu-id="69d3f-228">Удаление политики привилегированного доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-228">Delete a privileged access policy in Office 365</span></span>

<span data-ttu-id="69d3f-229">Если она больше не требуется в вашей организации, вы можете удалить политику привилегированного доступа.</span><span class="sxs-lookup"><span data-stu-id="69d3f-229">If it is no longer needed in your organization, you can delete a privileged access policy.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="69d3f-230">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-230">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="69d3f-231">Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span><span class="sxs-lookup"><span data-stu-id="69d3f-231">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="69d3f-232">В Центре администрирования перейдите к параметрам безопасности параметров организации  >    >  **&**  >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-232">In the admin center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="69d3f-233">Выберите **"Управление политиками и запросами доступа".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-233">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="69d3f-234">Выберите **"Настроить политики".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-234">Select **Configure policies**.</span></span>

5. <span data-ttu-id="69d3f-235">Выберите политику, которая нужно удалить, а затем выберите **"Удалить политику".**</span><span class="sxs-lookup"><span data-stu-id="69d3f-235">Select the policy you want to delete, then select **Remove Policy**.</span></span>

6. <span data-ttu-id="69d3f-236">Нажмите **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="69d3f-236">Select **Close**.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="69d3f-237">В Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d3f-237">In Exchange Management PowerShell</span></span>

<span data-ttu-id="69d3f-238">Чтобы удалить политику привилегированного доступа, запустите следующую команду в Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="69d3f-238">To delete a privileged access policy, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Remove-ElevatedAccessApprovalPolicy -Identity <identity GUID of the policy you want to delete>
```

## <a name="disable-privileged-access-in-office-365"></a><span data-ttu-id="69d3f-239">Отключение привилегированного доступа в Office 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-239">Disable privileged access in Office 365</span></span>

<span data-ttu-id="69d3f-240">При необходимости вы можете отключить управление привилегированным доступом в организации.</span><span class="sxs-lookup"><span data-stu-id="69d3f-240">If needed, you can disable privileged access management for your organization.</span></span> <span data-ttu-id="69d3f-241">Отключение привилегированного доступа не удаляет связанные политики утверждения или группы утверждения.</span><span class="sxs-lookup"><span data-stu-id="69d3f-241">Disabling privileged access does not delete any associated approval policies or approver groups.</span></span>

### <a name="in-the-microsoft-365-admin-center"></a><span data-ttu-id="69d3f-242">В Центре администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="69d3f-242">In the Microsoft 365 admin center</span></span>

1. <span data-ttu-id="69d3f-243">Во sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span><span class="sxs-lookup"><span data-stu-id="69d3f-243">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) with credentials for an admin account in your organization.</span></span>

2. <span data-ttu-id="69d3f-244">В Центре администрирования перейдите **к** параметрам безопасности  >  **параметров** организации &  >    >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-244">In the Admin Center, go to **Settings** > **Org Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="69d3f-245">Включить утверждение **"Требовать" для управления привилегированным доступом.**</span><span class="sxs-lookup"><span data-stu-id="69d3f-245">Enable the **Require approvals for privileged access** control.</span></span>

### <a name="in-exchange-management-powershell"></a><span data-ttu-id="69d3f-246">В Exchange Management PowerShell</span><span class="sxs-lookup"><span data-stu-id="69d3f-246">In Exchange Management PowerShell</span></span>

<span data-ttu-id="69d3f-247">Чтобы отключить привилегированный доступ, запустите следующую команду в Exchange Online Powershell:</span><span class="sxs-lookup"><span data-stu-id="69d3f-247">To disable privileged access, run the following command in Exchange Online Powershell:</span></span>

```PowerShell
Disable-ElevatedAccessControl
```
