---
title: Управление привилегированным доступом для вашей тестовой среды Microsoft 365 корпоративный
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
description: Используйте это руководство по лаборатории тестирования для включения привилегированного управления доступом в тестовой среде Microsoft 365 корпоративный.
ms.openlocfilehash: df3a2138de105b45f472ff0a862af2afe6dd2a34
ms.sourcegitcommit: 64a21c59d31a283ccbe87d16f0a174998e3aeba8
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/26/2019
ms.locfileid: "37733428"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1dd55-103">Управление привилегированным доступом для вашей тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="1dd55-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1dd55-104">С помощью инструкций, описанных в этой статье, вы настраиваете управление привилегированным доступом для повышения безопасности в тестовой среде Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="1dd55-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="1dd55-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="1dd55-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="1dd55-107">Этап 1: создание тестовой среды Microsoft 365 Enterprise</span><span class="sxs-lookup"><span data-stu-id="1dd55-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="1dd55-108">Если вы хотите просто настроить управление привилегированным доступом в упрощенной среде с минимальными требованиями, следуйте инструкциям в разделе [облегченная настройка конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="1dd55-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="1dd55-109">Если необходимо настроить управление привилегированным доступом на имитируемой предприятии, следуйте инструкциям в [сквозной проверке подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="1dd55-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="1dd55-110">Для тестирования привилегированного управления доступом не требуется имитация тестовой среды предприятия, которая включает имитируемую интрасеть, подключенную к Интернету и синхронизацию каталогов для леса AD DS.</span><span class="sxs-lookup"><span data-stu-id="1dd55-110">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an AD DS forest.</span></span> <span data-ttu-id="1dd55-111">Он предоставляется в качестве варианта, чтобы можно было тестировать управление привилегированным доступом и поэкспериментировать с ним в среде, представляющей типичную организацию.</span><span class="sxs-lookup"><span data-stu-id="1dd55-111">It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="1dd55-112">Этап 2: Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="1dd55-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="1dd55-113">На этом этапе настраивается группа утверждающих и включается управление привилегированным доступом для тестовой среды Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="1dd55-113">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="1dd55-114">Дополнительные сведения и общие сведения об управлении привилегированным доступом см [в статье Управление привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="1dd55-114">For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="1dd55-115">Выполните следующие действия, чтобы настроить и использовать привилегированный доступ в организации Office 365:</span><span class="sxs-lookup"><span data-stu-id="1dd55-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="1dd55-116">Шаг 1: создание группы утверждающего</span><span class="sxs-lookup"><span data-stu-id="1dd55-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="1dd55-117">Прежде чем приступить к работе с правами на доступ к данным, определите, кто будет иметь право на утверждение входящих запросов на доступ к задачам с повышенными правами и привилегированным пользователям.</span><span class="sxs-lookup"><span data-stu-id="1dd55-117">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks.</span></span> <span data-ttu-id="1dd55-118">Любой пользователь, являющийся участником группы утверждающих, сможет утверждать запросы на доступ.</span><span class="sxs-lookup"><span data-stu-id="1dd55-118">Any user who is part of the Approvers’ group will be able to approve access requests.</span></span> <span data-ttu-id="1dd55-119">Эта возможность включена путем создания группы безопасности с включенной поддержкой почты в Office 365.</span><span class="sxs-lookup"><span data-stu-id="1dd55-119">This is enabled by creating a mail-enabled security group in Office 365.</span></span> <span data-ttu-id="1dd55-120">Создайте в тестовой среде новую группу безопасности с именем "User-утверждающие права доступа" и добавьте "пользователь 3", созданный ранее в ходе предыдущего руководства по лаборатории тестирования.</span><span class="sxs-lookup"><span data-stu-id="1dd55-120">Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="1dd55-121">Шаг 2: включение привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="1dd55-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="1dd55-122">Привилегированный доступ должен быть явно включен в Office 365 с группой утверждающих по умолчанию и включать набор системных учетных записей, которые необходимо исключить из управления доступом для управления привилегированным доступом.</span><span class="sxs-lookup"><span data-stu-id="1dd55-122">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control.</span></span> <span data-ttu-id="1dd55-123">Обязательно включите привилегированный доступ в организации Office 365, прежде чем запускать 3 этапа этого руководства.</span><span class="sxs-lookup"><span data-stu-id="1dd55-123">Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="1dd55-124">Этап 3: Проверка необходимости утверждения для повышенных и привилегированных задач</span><span class="sxs-lookup"><span data-stu-id="1dd55-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="1dd55-125">На этом этапе проверяется работоспособность политики привилегированного доступа, и пользователям требуется утверждение для выполнения определенных повышенных и привилегированных задач.</span><span class="sxs-lookup"><span data-stu-id="1dd55-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="1dd55-126">Возможность тестирования для выполнения задачи, не определенной в привилегированной политике доступа</span><span class="sxs-lookup"><span data-stu-id="1dd55-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="1dd55-127">Сначала подключитесь к PowerShell с помощью консоли управления Exchange, указав учетные данные пользователя, настроенного в качестве глобального администратора в тестовой среде, и попытайтесь создать новое правило журнала.</span><span class="sxs-lookup"><span data-stu-id="1dd55-127">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule.</span></span> <span data-ttu-id="1dd55-128">В настоящее время задача [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) не определена в политике привилегированного доступа для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="1dd55-128">The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="1dd55-129">На локальном компьютере откройте и войдите в модуль удаленного PowerShell Exchange **Online в** > **удаленном** модуле PowerShell Microsoft Exchange Online с помощью учетной записи глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="1dd55-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="1dd55-130">В PowerShell Management PowerShell создайте новое правило журнала для своей организации.</span><span class="sxs-lookup"><span data-stu-id="1dd55-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="1dd55-131">Просмотр того, что новое правило журнала успешно создано в Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dd55-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="1dd55-132">Создание новой политики привилегированного доступа для новой задачи JournalRule</span><span class="sxs-lookup"><span data-stu-id="1dd55-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="1dd55-133">Если вы еще не выполнили шаги 1 и 2 из этапа 2 данного руководства, выполните действия, чтобы создать группу утверждающего с именем "утверждающие права доступа" и включить привилегированный доступ в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="1dd55-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="1dd55-134">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя учетные данные глобального администратора тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="1dd55-134">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="1dd55-135">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="1dd55-136">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="1dd55-137">Выберите пункт **Настройка политик** и нажмите кнопку **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="1dd55-138">В раскрывающихся полях выберите или введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="1dd55-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="1dd55-139">**Тип политики**: задача</span><span class="sxs-lookup"><span data-stu-id="1dd55-139">**Policy type**: Task</span></span>

    <span data-ttu-id="1dd55-140">**Область действия политики**: Exchange</span><span class="sxs-lookup"><span data-stu-id="1dd55-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="1dd55-141">**Имя политики**: новое правило журнала</span><span class="sxs-lookup"><span data-stu-id="1dd55-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="1dd55-142">**Тип утверждения**: вручную</span><span class="sxs-lookup"><span data-stu-id="1dd55-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="1dd55-143">**Группа утверждения**: "утверждающие лица привилегированного доступа"</span><span class="sxs-lookup"><span data-stu-id="1dd55-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="1dd55-144">Выберите **создать** , а затем **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-144">Select **Create** and then **Close**.</span></span> <span data-ttu-id="1dd55-145">Полная настройка и включение политики может занять несколько минут.</span><span class="sxs-lookup"><span data-stu-id="1dd55-145">It may take a few minutes for the policy to be fully configured and enabled.</span></span> <span data-ttu-id="1dd55-146">Убедитесь, что политика будет полностью включена, прежде чем проверять требования к утверждению на следующем шаге.</span><span class="sxs-lookup"><span data-stu-id="1dd55-146">Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="1dd55-147">Проверка требования утверждения для новой задачи JournalRule, определенной в политике привилегированного доступа</span><span class="sxs-lookup"><span data-stu-id="1dd55-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="1dd55-148">На локальном компьютере откройте и войдите в модуль удаленного PowerShell Exchange **Online в** > **удаленном** модуле PowerShell Microsoft Exchange Online с помощью учетной записи глобального администратора для тестирования. Environment.</span><span class="sxs-lookup"><span data-stu-id="1dd55-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="1dd55-149">В PowerShell Management PowerShell создайте новое правило журнала для своей организации.</span><span class="sxs-lookup"><span data-stu-id="1dd55-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="1dd55-150">В консоли управления Exchange PowerShell появляется сообщение об ошибке "Инсуффиент Permissions":</span><span class="sxs-lookup"><span data-stu-id="1dd55-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="1dd55-151">Запрос доступа на создание нового правила журнала с помощью задачи New – JournalRule</span><span class="sxs-lookup"><span data-stu-id="1dd55-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="1dd55-152">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя учетную запись глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="1dd55-152">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="1dd55-153">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="1dd55-154">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="1dd55-155">Выберите пункт **создать запрос**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-155">Select **New request**.</span></span> <span data-ttu-id="1dd55-156">В раскрывающихся полях выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="1dd55-156">From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="1dd55-157">**Тип запроса**: задача</span><span class="sxs-lookup"><span data-stu-id="1dd55-157">**Request type**: Task</span></span>

    <span data-ttu-id="1dd55-158">**Область запроса**: Exchange</span><span class="sxs-lookup"><span data-stu-id="1dd55-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="1dd55-159">**Запрос для**: новое правило журнала</span><span class="sxs-lookup"><span data-stu-id="1dd55-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="1dd55-160">**Продолжительность (часы)**: 2</span><span class="sxs-lookup"><span data-stu-id="1dd55-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="1dd55-161">**Комментарии**: запрос разрешения на создание нового правила журнала</span><span class="sxs-lookup"><span data-stu-id="1dd55-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="1dd55-162">Нажмите кнопку **сохранить** , а затем кнопку **Закрыть**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-162">Select **Save** and then **Close**.</span></span> <span data-ttu-id="1dd55-163">Ваш запрос будет отправлен в группу утверждающего через электронную почту.</span><span class="sxs-lookup"><span data-stu-id="1dd55-163">Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="1dd55-164">Утверждение запроса на привилегированный доступ для создания нового правила журнала</span><span class="sxs-lookup"><span data-stu-id="1dd55-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="1dd55-165">Войдите в [центр администрирования Microsoft 365](https://admin.microsoft.com) , используя учетные данные пользователя 3 в тестовой среде (член группы безопасности "привилегированный доступ" в тестовой среде).</span><span class="sxs-lookup"><span data-stu-id="1dd55-165">Sign into the [Microsoft 365 admin center](https://admin.microsoft.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="1dd55-166">В центре администрирования **перейдите к** > разделу**Безопасность &** > безопасность с**правами на доступ к данным**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="1dd55-167">Выберите **Управление политиками доступа и запросами**.</span><span class="sxs-lookup"><span data-stu-id="1dd55-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="1dd55-168">Выберите ожидающий запрос и нажмите кнопку **одобрить** , чтобы предоставить учетной записи глобального администратора доступ к новому правилу журнала.</span><span class="sxs-lookup"><span data-stu-id="1dd55-168">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule.</span></span> <span data-ttu-id="1dd55-169">Электронная почта уведомления, подтверждающая, что утверждение предоставлено, будет отправлено в учетную запись глобального администратора (запрашивающего пользователя).</span><span class="sxs-lookup"><span data-stu-id="1dd55-169">An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="1dd55-170">Тестирование создания нового правила журнала с привилегированным доступом, утвержденным для задачи New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="1dd55-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="1dd55-171">На локальном компьютере откройте и войдите в модуль удаленного PowerShell Exchange **Online в** > **удаленном** модуле PowerShell Microsoft Exchange Online с помощью учетной записи глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="1dd55-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="1dd55-172">В PowerShell Management PowerShell создайте новое правило журнала для своей организации.</span><span class="sxs-lookup"><span data-stu-id="1dd55-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="1dd55-173">Просмотр того, что новое правило журнала успешно создано в Exchange Management PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1dd55-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="1dd55-174">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="1dd55-174">Next step</span></span>

<span data-ttu-id="1dd55-175">Узнайте о дополнительных возможностях и возможностях [защиты информации](m365-enterprise-test-lab-guides.md#information-protection) в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="1dd55-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="1dd55-176">См. также</span><span class="sxs-lookup"><span data-stu-id="1dd55-176">See also</span></span>

[<span data-ttu-id="1dd55-177">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="1dd55-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="1dd55-178">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="1dd55-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="1dd55-179">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="1dd55-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)