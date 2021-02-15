---
title: Управление привилегированным доступом для тестовой среды Microsoft 365 для предприятий
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
ms.custom: Ent_TLGs
description: Используйте это руководство по лаборатории тестирования, чтобы включить управление привилегированным доступом в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: e9684ebd2aa147049dadfbda9408257ff801aff0
ms.sourcegitcommit: eac5d9f759f290d3c51cafaf335a1a1c43ded927
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/06/2021
ms.locfileid: "50126421"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="718a9-103">Управление привилегированным доступом для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="718a9-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="718a9-104">*Это руководство по лаборатории тестирования можно использовать для тестовых сред Microsoft 365 для предприятий и Office 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="718a9-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="718a9-105">В этой статье описывается настройка управления привилегированным доступом для повышения безопасности в тестовой среде Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="718a9-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="718a9-106">Настройка управления доступом с использованием priviledged состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="718a9-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="718a9-107">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="718a9-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="718a9-108">Этап 2. Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="718a9-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="718a9-109">Этап 3. Проверка необходимости утверждения для задач с повышенными привилегиями</span><span class="sxs-lookup"><span data-stu-id="718a9-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="718a9-111">Чтобы получить визуальную карту всех статей в руководстве по лаборатории тестирования Microsoft 365 для предприятий, перейдите в стек руководств по лаборатории тестирования [Microsoft 365 для предприятий.](../downloads/Microsoft365EnterpriseTLGStack.pdf)</span><span class="sxs-lookup"><span data-stu-id="718a9-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="718a9-112">Этап 1. Создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="718a9-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="718a9-113">Если вы хотите настроить управление привилегированным доступом облегченным способом с минимальными требованиями, следуйте инструкциям в базовой конфигурации [облегченного доступа.](lightweight-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="718a9-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="718a9-114">Если вы хотите настроить управление привилегированным доступом в имитированном предприятии, следуйте инструкциям в сквозной [проверке подлинности.](pass-through-auth-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="718a9-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="718a9-115">Для тестирования управления привилегированным доступом не требуется тестовая среда имитированной организации, которая включает имитированную интрасеть, подключенную к Интернету, и синхронизацию каталогов для леса доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="718a9-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="718a9-116">Он предоставляется здесь в качестве варианта, чтобы вы могли протестировать управление привилегированным доступом и поэкспериментировать с ним в типичной для организации среде.</span><span class="sxs-lookup"><span data-stu-id="718a9-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="718a9-117">Этап 2. Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="718a9-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="718a9-118">На этом этапе настройте группу утвержденных и встроите управление привилегированным доступом для тестовой среды Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="718a9-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="718a9-119">Дополнительные сведения и обзор управления привилегированным доступом см. в руководстве [по управлению привилегированным доступом.](../compliance/privileged-access-management-overview.md)</span><span class="sxs-lookup"><span data-stu-id="718a9-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="718a9-120">Чтобы настроить и использовать привилегированный доступ в организации, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="718a9-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="718a9-121">Шаг 1. Создание группы утвержденного</span><span class="sxs-lookup"><span data-stu-id="718a9-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="718a9-122">Прежде чем приступить к использованию привилегированного доступа, определите, кто будет иметь полномочия на утверждение входящих запросов на доступ к задачам с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="718a9-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="718a9-123">Все пользователи, которые являются частью группы "Утверждение", могут утверждать запросы на доступ.</span><span class="sxs-lookup"><span data-stu-id="718a9-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="718a9-124">Чтобы использовать привилегированный доступ, необходимо создать группу безопасности с включенной поддержкой почты в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="718a9-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="718a9-125">В тестовой среде назовите новую группу безопасности "Privileged Access Approvers" и добавьте "Пользователь 3", ранее созданную на предыдущих шагах руководства по лаборатории тестирования.</span><span class="sxs-lookup"><span data-stu-id="718a9-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="718a9-126">Шаг 2. Включить привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="718a9-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="718a9-127">Привилегированный доступ должен быть явно включен в Microsoft 365 с группой утвержденных по умолчанию и должен включать набор системных учетных записей, которые необходимо исключить из управления привилегированным доступом управления доступом.</span><span class="sxs-lookup"><span data-stu-id="718a9-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="718a9-128">Не забудьте включить привилегированный доступ в организации перед началом этапа 3 этого руководства.</span><span class="sxs-lookup"><span data-stu-id="718a9-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="718a9-129">Этап 3. Проверка необходимости утверждения для задач с повышенными привилегиями</span><span class="sxs-lookup"><span data-stu-id="718a9-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="718a9-130">На этом этапе убедитесь, что политика привилегированного доступа работает и что пользователям требуется утверждение для выполнения определенных задач с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="718a9-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="718a9-131">Проверка возможности выполнения задачи, НЕ определенной в политике привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="718a9-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="718a9-132">Сначала подключите к Exchange Management PowerShell с учетными данными пользователя, настроенного в качестве глобального администратора в тестовой среде, и попытайтесь создать новое правило журнала.</span><span class="sxs-lookup"><span data-stu-id="718a9-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="718a9-133">Задача [New-JournalRule](/powershell/module/exchange/new-journalrule) в настоящее время не определена в политике привилегированного доступа для организации.</span><span class="sxs-lookup"><span data-stu-id="718a9-133">The [New-JournalRule](/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="718a9-134">На локальном компьютере откройте удаленный модуль PowerShell exchange Online и вопишите его в модуль **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell с** помощью учетной записи глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="718a9-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="718a9-135">В Exchange Management PowerShell создайте новое правило журнала для своей организации:</span><span class="sxs-lookup"><span data-stu-id="718a9-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="718a9-136">Вы должны увидеть, что новое правило журнала успешно создано в Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="718a9-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="718a9-137">Создание новой политики привилегированного доступа для New-JournalRule доступа</span><span class="sxs-lookup"><span data-stu-id="718a9-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="718a9-138">Если вы еще не выполнили шаги 1 и 2 из этапа 2 этого руководства, обязательно выполните действия, чтобы создать группу утвержденных с именем "Privilege Access Approvers", чтобы включить привилегированный доступ в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="718a9-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="718a9-139">Во sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span><span class="sxs-lookup"><span data-stu-id="718a9-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="718a9-140">В Центре администрирования перейдите **к** параметрам безопасности  >  **&**  >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="718a9-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="718a9-141">Выберите **"Управление политиками и запросами доступа".**</span><span class="sxs-lookup"><span data-stu-id="718a9-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="718a9-142">Выберите **"Настроить политики",** а затем выберите **"Добавить политику".**</span><span class="sxs-lookup"><span data-stu-id="718a9-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="718a9-143">В полях в выпадаемом поле выберите или введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="718a9-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="718a9-144">**Тип политики**: Задача</span><span class="sxs-lookup"><span data-stu-id="718a9-144">**Policy type**: Task</span></span>

    <span data-ttu-id="718a9-145">**Область политики**: Exchange</span><span class="sxs-lookup"><span data-stu-id="718a9-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="718a9-146">**Имя политики:** новое правило журнала</span><span class="sxs-lookup"><span data-stu-id="718a9-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="718a9-147">**Тип утверждения:** вручную</span><span class="sxs-lookup"><span data-stu-id="718a9-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="718a9-148">**Группа утверждения:**"Утверждение привилегированного доступа"</span><span class="sxs-lookup"><span data-stu-id="718a9-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="718a9-149">Выберите **"Создать"** и **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="718a9-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="718a9-150">Для полной настройки и включения политики может потребоваться несколько минут.</span><span class="sxs-lookup"><span data-stu-id="718a9-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="718a9-151">Убедитесь, что у вас должно быть время для полной включения политики, прежде чем тестировать требование утверждения на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="718a9-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="718a9-152">Требование проверки утверждения для New-JournalRule, определенной в политике привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="718a9-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="718a9-153">На локальном компьютере откройте удаленный модуль PowerShell exchange Online и вопишите его в модуль **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell с** помощью учетной записи глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="718a9-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="718a9-154">В Exchange Management PowerShell создайте новое правило журнала для своей организации:</span><span class="sxs-lookup"><span data-stu-id="718a9-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="718a9-155">Просмотр ошибки "Недостаточно разрешений" в Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="718a9-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="718a9-156">Запрос доступа для создания нового правила журнала с помощью New-JournalRule задачи</span><span class="sxs-lookup"><span data-stu-id="718a9-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="718a9-157">Во sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span><span class="sxs-lookup"><span data-stu-id="718a9-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="718a9-158">В Центре администрирования перейдите **к** параметрам безопасности  >  **&**  >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="718a9-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="718a9-159">Выберите **"Управление политиками и запросами доступа".**</span><span class="sxs-lookup"><span data-stu-id="718a9-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="718a9-160">Выберите **новый запрос.**</span><span class="sxs-lookup"><span data-stu-id="718a9-160">Select **New request**.</span></span> <span data-ttu-id="718a9-161">В полях в выпадаемом поле выберите соответствующие значения для организации:</span><span class="sxs-lookup"><span data-stu-id="718a9-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="718a9-162">**Тип запроса**: Задача</span><span class="sxs-lookup"><span data-stu-id="718a9-162">**Request type**: Task</span></span>

    <span data-ttu-id="718a9-163">**Область запроса**: Exchange</span><span class="sxs-lookup"><span data-stu-id="718a9-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="718a9-164">**Запрос :** новое правило журнала</span><span class="sxs-lookup"><span data-stu-id="718a9-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="718a9-165">**Продолжительность (часы)**: 2</span><span class="sxs-lookup"><span data-stu-id="718a9-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="718a9-166">**Комментарии:** запрос разрешения на создание нового правила журнала</span><span class="sxs-lookup"><span data-stu-id="718a9-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="718a9-167">Выберите **"Сохранить"** и **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="718a9-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="718a9-168">Ваш запрос будет отправлен группе утвержденного по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="718a9-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="718a9-169">Утверждение запроса на привилегированный доступ для создания нового правила журнала</span><span class="sxs-lookup"><span data-stu-id="718a9-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="718a9-170">Во sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span><span class="sxs-lookup"><span data-stu-id="718a9-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="718a9-171">В Центре администрирования перейдите **к** параметрам безопасности  >  **&**  >  **конфиденциальности привилегированного доступа.**</span><span class="sxs-lookup"><span data-stu-id="718a9-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="718a9-172">Выберите **"Управление политиками и запросами доступа".**</span><span class="sxs-lookup"><span data-stu-id="718a9-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="718a9-173">Выберите ожидающее запрос,  а затем выберите "Утвердить", чтобы предоставить доступ к учетной записи глобального администратора для создания нового правила журнала.</span><span class="sxs-lookup"><span data-stu-id="718a9-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="718a9-174">Учетная запись глобального администратора (запрашивающий пользователь) получит по электронной почте подтверждение об утверждении.</span><span class="sxs-lookup"><span data-stu-id="718a9-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="718a9-175">Тестирование создания нового правила журнала с привилегированным доступом, утвержденным для New-JournalRule задачи</span><span class="sxs-lookup"><span data-stu-id="718a9-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="718a9-176">На локальном компьютере откройте удаленный модуль PowerShell exchange Online и вопишите его в модуль **Microsoft Corporation** Microsoft Exchange Online  >  **Remote PowerShell с** помощью учетной записи глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="718a9-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="718a9-177">В Exchange Management PowerShell создайте новое правило журнала для своей организации:</span><span class="sxs-lookup"><span data-stu-id="718a9-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="718a9-178">Вы должны увидеть, что новое правило журнала успешно создано в Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="718a9-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="718a9-179">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="718a9-179">Next step</span></span>

<span data-ttu-id="718a9-180">Изучите [дополнительные функции](m365-enterprise-test-lab-guides.md#information-protection) и возможности защиты информации в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="718a9-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="718a9-181">См. также</span><span class="sxs-lookup"><span data-stu-id="718a9-181">See also</span></span>

[<span data-ttu-id="718a9-182">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="718a9-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="718a9-183">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="718a9-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="718a9-184">Документация по Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="718a9-184">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)
