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
description: Используйте это руководство по лаборатории тестирования для включения привилегированного управления доступом в тестовой среде Microsoft 365 для предприятий.
ms.openlocfilehash: 24ca7a6408a4290c54dd2bcd7c3f6061eb8f6c05
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487592"
---
# <a name="privileged-access-management-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="23fab-103">Управление привилегированным доступом для тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="23fab-103">Privileged access management for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="23fab-104">*Это руководство по лаборатории тестирования можно использовать как для Microsoft 365 Enterprise, так и для корпоративных тестовых сред Office 365.*</span><span class="sxs-lookup"><span data-stu-id="23fab-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="23fab-105">В этой статье описывается настройка управления привилегированным доступом для повышения безопасности в тестовой среде Microsoft 365 для предприятий.</span><span class="sxs-lookup"><span data-stu-id="23fab-105">This article describes how to configure privileged access management to increase security in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="23fab-106">Настройка управления доступом привиледжед состоит из трех этапов:</span><span class="sxs-lookup"><span data-stu-id="23fab-106">Configuring priviledged access management involves three phases:</span></span>
- [<span data-ttu-id="23fab-107">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="23fab-107">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="23fab-108">Этап 2: Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="23fab-108">Phase 2: Configure privileged access management</span></span>](#phase-2-configure-privileged-access-management)
- [<span data-ttu-id="23fab-109">Этап 3: Проверка необходимости утверждения для повышенных и привилегированных задач</span><span class="sxs-lookup"><span data-stu-id="23fab-109">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>](#phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks)

![Руководства по лаборатории тестирования для облака Майкрософт](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="23fab-111">Для отображения всех статей, посвященных руководству по лаборатории тестирования Microsoft 365 для предприятий, перейдите к разделу [руководство по лаборатории тестирования microsoft 365 для предприятия](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span><span class="sxs-lookup"><span data-stu-id="23fab-111">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="23fab-112">Этап 1: создание тестовой среды Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="23fab-112">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="23fab-113">Если необходимо настроить управление привилегированным доступом в упрощенной среде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="23fab-113">If you want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="23fab-114">Если необходимо настроить управление привилегированным доступом на имитируемой предприятии, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="23fab-114">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
>[!NOTE]
><span data-ttu-id="23fab-115">Для тестирования привилегированного управления доступом не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов для леса доменных служб Active Directory.</span><span class="sxs-lookup"><span data-stu-id="23fab-115">Testing privileged access management doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services forest.</span></span> <span data-ttu-id="23fab-116">Он предоставляется в качестве варианта, чтобы можно было тестировать управление привилегированным доступом и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="23fab-116">It's provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span>

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="23fab-117">Этап 2: Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="23fab-117">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="23fab-118">На этом этапе Настройте группу утверждающих и включите управление привилегированным доступом для тестовой среды Microsoft 365 для предприятия.</span><span class="sxs-lookup"><span data-stu-id="23fab-118">In this phase, configure an approvers group and enable privileged access management for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="23fab-119">Дополнительные сведения и общие сведения об управлении привилегированным доступом можно найти в статье [Управление привилегированным доступом](../compliance/privileged-access-management-overview.md).</span><span class="sxs-lookup"><span data-stu-id="23fab-119">For additional details and an overview of privileged access management, see [Privileged access management](../compliance/privileged-access-management-overview.md).</span></span>

<span data-ttu-id="23fab-120">Чтобы настроить и использовать привилегированный доступ в Организации, выполните указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="23fab-120">To set up and use privileged access in your organization, perform the following steps.</span></span>

#### <a name="step-1-create-an-approvers-group"></a>[<span data-ttu-id="23fab-121">Шаг 1: создание группы утверждающего</span><span class="sxs-lookup"><span data-stu-id="23fab-121">Step 1: Create an approver's group</span></span>](../compliance/privileged-access-management-configuration.md#step-1-create-an-approvers-group)

<span data-ttu-id="23fab-122">Прежде чем приступить к работе с привилегированным доступом, определите, кто будет иметь право на утверждение входящих запросов на доступ к задачам с повышенными привилегиями.</span><span class="sxs-lookup"><span data-stu-id="23fab-122">Before you start using privileged access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="23fab-123">Все пользователи, являющиеся частью группы утверждающих, могут утверждать запросы на доступ.</span><span class="sxs-lookup"><span data-stu-id="23fab-123">All users who are part of the Approvers’ group can approve access requests.</span></span> <span data-ttu-id="23fab-124">Чтобы использовать привилегированный доступ, необходимо создать группу безопасности с поддержкой электронной почты в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="23fab-124">To use privileged access, you must create a mail-enabled security group in Microsoft 365.</span></span> <span data-ttu-id="23fab-125">В тестовой среде Назовите новую группу безопасности "утверждающие права доступа" и добавьте "пользователь 3", который ранее был создан в предыдущих шагах по лаборатории тестирования.</span><span class="sxs-lookup"><span data-stu-id="23fab-125">In your test environment, name the new security group "Privileged Access Approvers" and add the "User 3" that was previously created in previous test lab guide steps.</span></span>

#### <a name="step-2-enable-privileged-access"></a>[<span data-ttu-id="23fab-126">Шаг 2: включение привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="23fab-126">Step 2: Enable privileged access</span></span>](../compliance/privileged-access-management-configuration.md#step-2-enable-privileged-access)

<span data-ttu-id="23fab-127">Привилегированный доступ должен быть явно включен в Microsoft 365 с группой утверждающего по умолчанию и включать в себя набор системных учетных записей, которые необходимо исключить из управления доступом привилегированного управления доступом.</span><span class="sxs-lookup"><span data-stu-id="23fab-127">Privileged access needs to be explicitly turned on in Microsoft 365 with the default approver group, and it must include a set of system accounts that you want excluded from the privileged access management access control.</span></span> <span data-ttu-id="23fab-128">Обязательно включите привилегированный доступ в Организации до начала 3 этапа этого руководства.</span><span class="sxs-lookup"><span data-stu-id="23fab-128">Be sure to enable privileged access in your organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="23fab-129">Этап 3: Проверка необходимости утверждения для повышенных и привилегированных задач</span><span class="sxs-lookup"><span data-stu-id="23fab-129">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>

<span data-ttu-id="23fab-130">На этом этапе убедитесь, что политика привилегированного доступа работает и что пользователям требуется утверждение для выполнения определенных повышенных и привилегированных задач.</span><span class="sxs-lookup"><span data-stu-id="23fab-130">In this phase, verify that the privileged access policy is working and that users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-the-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="23fab-131">Проверка возможности выполнения задачи, не определенной в привилегированной политике доступа</span><span class="sxs-lookup"><span data-stu-id="23fab-131">Test the ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="23fab-132">Сначала подключитесь к PowerShell с помощью консоли управления Exchange, указав учетные данные пользователя, настроенного в качестве глобального администратора в тестовой среде, и попытайтесь создать новое правило журнала.</span><span class="sxs-lookup"><span data-stu-id="23fab-132">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="23fab-133">В настоящее время задача [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) не определена в политике привилегированного доступа для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="23fab-133">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/new-journalrule) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="23fab-134">На локальном компьютере откройте и войдите в удаленный модуль PowerShell Exchange Online на удаленном модуле PowerShell **Microsoft**  >  **Exchange Online** , используя учетную запись глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="23fab-134">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="23fab-135">В PowerShell Management PowerShell создайте новое правило журнала для своей организации.</span><span class="sxs-lookup"><span data-stu-id="23fab-135">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="23fab-136">Просмотр того, что новое правило журнала успешно создано в Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23fab-136">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="23fab-137">Создание новой политики привилегированного доступа для задачи New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="23fab-137">Create a new privileged access policy for the New-JournalRule task</span></span>

>[!NOTE]
><span data-ttu-id="23fab-138">Если вы еще не выполнили шаги 1 и 2 из этапа 2 данного руководства, выполните действия, чтобы создать группу утверждающего с именем "утверждающие права доступа", чтобы включить привилегированный доступ в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="23fab-138">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="23fab-139">Войдите в [центр администрирования майкрософт 365](https://admin.microsoft.com) , используя учетные данные глобального администратора тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="23fab-139">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="23fab-140">В центре администрирования перейдите к разделу **Settings**  >  **Безопасность & безопасность**с  >  **правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="23fab-140">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23fab-141">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="23fab-141">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="23fab-142">Выберите пункт **Настройка политик**, а затем нажмите кнопку **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="23fab-142">Select **Configure policies**, and then select **Add a policy**.</span></span>

5. <span data-ttu-id="23fab-143">В раскрывающихся полях выберите или введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="23fab-143">From the drop-down fields, select or enter the following values:</span></span>

    <span data-ttu-id="23fab-144">**Тип политики**: задача</span><span class="sxs-lookup"><span data-stu-id="23fab-144">**Policy type**: Task</span></span>

    <span data-ttu-id="23fab-145">**Область действия политики**: Exchange</span><span class="sxs-lookup"><span data-stu-id="23fab-145">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="23fab-146">**Имя политики**: новое правило журнала</span><span class="sxs-lookup"><span data-stu-id="23fab-146">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="23fab-147">**Тип утверждения**: вручную</span><span class="sxs-lookup"><span data-stu-id="23fab-147">**Approval type**: Manual</span></span>

    <span data-ttu-id="23fab-148">**Группа утверждения**: "утверждающие лица привилегированного доступа"</span><span class="sxs-lookup"><span data-stu-id="23fab-148">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="23fab-149">Выберите **создать**, а затем нажмите кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="23fab-149">Select **Create**, and then select **Close**.</span></span> <span data-ttu-id="23fab-150">Полная настройка и включение политики может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="23fab-150">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="23fab-151">Убедитесь, что политика будет полностью включена, прежде чем проверять требования к утверждению на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="23fab-151">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="23fab-152">Проверка требования утверждения для New-JournalRule задачи, определенной в политике привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="23fab-152">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="23fab-153">На локальном компьютере откройте и войдите в удаленный модуль PowerShell Exchange Online на удаленном модуле PowerShell **Microsoft**  >  **Exchange Online** с помощью учетной записи глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="23fab-153">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="23fab-154">В PowerShell Management PowerShell создайте новое правило журнала для своей организации.</span><span class="sxs-lookup"><span data-stu-id="23fab-154">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

3. <span data-ttu-id="23fab-155">Просмотрите сообщение об ошибке "недостаточно разрешений" в Exchange Management PowerShell:</span><span class="sxs-lookup"><span data-stu-id="23fab-155">View the "Insufficient permissions" error in Exchange Management PowerShell:</span></span>

   ```ExchangeManagementPowerShell
   Insufficient permissions. Please raise an elevated access request for this task.
       + CategoryInfo          : NotSpecified: (:) [], LocalizedException
       + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
       7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
       + PSComputerName        : outlook.office365.com
   ```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="23fab-156">Запрос доступа на создание нового правила журнала с помощью задачи New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="23fab-156">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="23fab-157">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя учетную запись глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="23fab-157">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="23fab-158">В центре администрирования перейдите к разделу **Settings**  >  **Безопасность & безопасность**с  >  **правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="23fab-158">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23fab-159">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="23fab-159">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="23fab-160">Выберите пункт **создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="23fab-160">Select **New request**.</span></span> <span data-ttu-id="23fab-161">В раскрывающихся полях выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="23fab-161">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="23fab-162">**Тип запроса**: задача</span><span class="sxs-lookup"><span data-stu-id="23fab-162">**Request type**: Task</span></span>

    <span data-ttu-id="23fab-163">**Область запроса**: Exchange</span><span class="sxs-lookup"><span data-stu-id="23fab-163">**Request scope**: Exchange</span></span>

    <span data-ttu-id="23fab-164">**Запрос для**: новое правило журнала</span><span class="sxs-lookup"><span data-stu-id="23fab-164">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="23fab-165">**Продолжительность (часы)**: 2</span><span class="sxs-lookup"><span data-stu-id="23fab-165">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="23fab-166">**Комментарии**: запрос разрешения на создание нового правила журнала</span><span class="sxs-lookup"><span data-stu-id="23fab-166">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="23fab-167">Нажмите кнопку **сохранить**, а затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="23fab-167">Select **Save**, and then select **Close**.</span></span> <span data-ttu-id="23fab-168">Ваш запрос будет отправлен в группу утверждающего через электронную почту.</span><span class="sxs-lookup"><span data-stu-id="23fab-168">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="23fab-169">Утверждение запроса на привилегированный доступ для создания нового правила журнала</span><span class="sxs-lookup"><span data-stu-id="23fab-169">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="23fab-170">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя учетные данные пользователя 3 в тестовой среде (член группы безопасности "привилегированный доступ" в тестовой среде).</span><span class="sxs-lookup"><span data-stu-id="23fab-170">Sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="23fab-171">В центре администрирования перейдите к разделу **Settings**  >  **Безопасность & безопасность**с  >  **правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="23fab-171">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="23fab-172">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="23fab-172">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="23fab-173">Выберите ожидающий запрос и нажмите кнопку **одобрить** , чтобы предоставить доступ к учетной записи глобального администратора для создания нового правила журнала.</span><span class="sxs-lookup"><span data-stu-id="23fab-173">Select the pending request, and then select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="23fab-174">Учетная запись глобального администратора (запрашивающего пользователя) будет получать подтверждение по электронной почте о предоставлении утверждения.</span><span class="sxs-lookup"><span data-stu-id="23fab-174">The Global Admin account (the requesting user) will receive an email confirmation that approval was granted.</span></span>

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="23fab-175">Тестирование создания нового правила журнала с привилегированным доступом, утвержденным для задачи New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="23fab-175">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="23fab-176">На локальном компьютере откройте и войдите в удаленный модуль PowerShell Exchange Online на удаленном модуле PowerShell **Microsoft**  >  **Exchange Online** , используя учетную запись глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="23fab-176">On your local computer, open and sign in to the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

1. <span data-ttu-id="23fab-177">В PowerShell Management PowerShell создайте новое правило журнала для своей организации.</span><span class="sxs-lookup"><span data-stu-id="23fab-177">In Exchange Management PowerShell, create a new Journal rule for your organization:</span></span>

   ```ExchangeManagementPowerShell
   New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
   ```

1. <span data-ttu-id="23fab-178">Просмотр того, что новое правило журнала успешно создано в Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="23fab-178">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="23fab-179">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="23fab-179">Next step</span></span>

<span data-ttu-id="23fab-180">Узнайте о дополнительных возможностях и возможностях [защиты информации](m365-enterprise-test-lab-guides.md#information-protection) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="23fab-180">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="23fab-181">См. также</span><span class="sxs-lookup"><span data-stu-id="23fab-181">See also</span></span>

[<span data-ttu-id="23fab-182">Руководства по лаборатории тестирования для Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="23fab-182">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="23fab-183">Обзор Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="23fab-183">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="23fab-184">Microsoft 365 для корпоративных документов</span><span class="sxs-lookup"><span data-stu-id="23fab-184">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
