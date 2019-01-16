---
title: Управление привилегированным доступом для вашей тестовой среды Microsoft 365 корпоративный
ms.author: robmazz
author: robmazz
manager: laurawi
ms.date: 09/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
description: Используйте в этом документе Test Lab Guide позволяет включить управление правами доступа к тестовой среды Microsoft 365 для предприятия.
ms.openlocfilehash: 5f1a416a12171504af110ec62b9a7882143263e6
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/16/2019
ms.locfileid: "26870447"
---
# <a name="privileged-access-management-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="0e91b-103">Управление привилегированным доступом для вашей тестовой среды Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0e91b-103">Privileged access management for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="0e91b-104">Инструкции в этом разделе настроить управление правами доступа для повышения безопасности в тестовой среде Microsoft 365 Enterprise.</span><span class="sxs-lookup"><span data-stu-id="0e91b-104">With the instructions in this article, you configure privileged access management to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Руководства по лаборатории тестирования для облака Майкрософт](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="0e91b-106">Щелкните [здесь](https://aka.ms/m365etlgstack), чтобы просмотреть схему всех статей, относящихся к руководствам по лаборатории тестирования Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="0e91b-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="0e91b-107">Этап 1: Создание масштабирование тестовой среды Microsoft 365 для предприятия</span><span class="sxs-lookup"><span data-stu-id="0e91b-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="0e91b-108">Если необходимо настроить управление правами доступа в облегченный путь с минимальным требованиям, следуйте инструкциям в [упрощенной базовой конфигурации](lightweight-base-configuration-microsoft-365-enterprise.md).</span><span class="sxs-lookup"><span data-stu-id="0e91b-108">If you just want to configure privileged access management in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="0e91b-109">Если вы хотите настроить управление правами доступа имитации enterprise, следуйте инструкциям в [сквозная проверка подлинности](pass-through-auth-m365-ent-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="0e91b-109">If you want to configure privileged access management in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="0e91b-p101">Тестирование управления правами доступа не требуется тестовой среды имитации предприятия, включающая имитации интрасети, подключенных к Интернету и синхронизации каталогов для леса Windows Server AD. Здесь предоставляются как вариант таким образом, вы можете проверить доступ к управлению правами доступа и экспериментировать с его в среде, которая представляет типичное организации.</span><span class="sxs-lookup"><span data-stu-id="0e91b-p101">Testing privileged access management does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test privileged access management and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-privileged-access-management"></a><span data-ttu-id="0e91b-112">Этап 2: Настройка управления правами доступа</span><span class="sxs-lookup"><span data-stu-id="0e91b-112">Phase 2: Configure privileged access management</span></span>

<span data-ttu-id="0e91b-p102">На этом этапе настройки группы обеспечения утверждающие и включить управление правами доступа для тестовой среды Microsoft 365 для предприятия. Для дополнительных сведений о и общие сведения о полномочиями доступ к управлению, см [Управление правами доступа в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="0e91b-p102">In this phase, you configure an approvers group and enable privileged access management for your Microsoft 365 Enterprise test environment. For additional details and an overview of privileged access management, see [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span></span>

<span data-ttu-id="0e91b-115">Выполните следующие действия для установки и использования привилегированной доступа в организации Office 365.</span><span class="sxs-lookup"><span data-stu-id="0e91b-115">Follow these steps to set up and use privileged access in your Office 365 organization:</span></span>

- [<span data-ttu-id="0e91b-116">Шаг 1: Создание группы утверждающий</span><span class="sxs-lookup"><span data-stu-id="0e91b-116">Step 1: Create an approver's group</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-1---create-an-approvers-group)

    <span data-ttu-id="0e91b-p103">Прежде чем начать, с помощью принципу предоставления минимальных прав доступа, определение пользователей, которые будут иметь Центр утверждения для входящих запросов для доступа к задачам с повышенными привилегиями и правами. Любой пользователь, который является частью в группе утверждающих будет иметь возможность утверждать запросы доступа. Этот параметр включен, создав группу безопасности с включенной поддержкой почты в Office 365. Создать новую группу безопасности с именем «Привилегированной утверждающие доступа» в тестовой среде и добавьте «пользователя 3" ранее созданные в предыдущих шагов руководство по лаборатории.</span><span class="sxs-lookup"><span data-stu-id="0e91b-p103">Before you start using privilege access, determine who will have approval authority for incoming requests for access to elevated and privileged tasks. Any user who is part of the Approvers’ group will be able to approve access requests. This is enabled by creating a mail-enabled security group in Office 365. Create a new security group named "Privileged Access Approvers" in your test environment and add the "User 3" previously created in prior test lab guide steps.</span></span>

- [<span data-ttu-id="0e91b-121">Шаг 2: Включение привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="0e91b-121">Step 2: Enable privileged access</span></span>](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration#step-2---enable-privileged-access)

    <span data-ttu-id="0e91b-p104">Привилегированный доступ должен явно включены в Office 365 с помощью группы утверждающий по умолчанию и включая набор системных учетных записей, которые необходимо исключить из управления доступом управления правами доступа. Не забудьте включить привилегированный доступ в организации Office 365, прежде чем начинать этап 3 в этом руководстве.</span><span class="sxs-lookup"><span data-stu-id="0e91b-p104">Privileged access needs to be explicitly turned on in Office 365 with the default approver group and including a set of system accounts that you’d want to be excluded from the privileged access management access control. Be sure to enable privileged access in your Office 365 organization before starting Phase 3 of this guide.</span></span>

## <a name="phase-3-verify-that-approval-is-required-for-elevated-and-privileged-tasks"></a><span data-ttu-id="0e91b-124">Этап 3: Убедитесь, что утверждения, необходимые для выполнения задач с повышенными привилегиями и правами</span><span class="sxs-lookup"><span data-stu-id="0e91b-124">Phase 3: Verify that approval is required for elevated and privileged tasks</span></span>
<span data-ttu-id="0e91b-125">На этом этапе вы убедитесь, что работа политики привилегированный доступ и пользователям требуется утверждение для выполнения определенных задач с повышенными привилегиями и правами.</span><span class="sxs-lookup"><span data-stu-id="0e91b-125">In this phase, you verify that the privileged access policy is working and users require approval to execute defined elevated and privileged tasks.</span></span>

### <a name="test-ability-to-execute-a-task-not-defined-in-a-privileged-access-policy"></a><span data-ttu-id="0e91b-126">Проверка возможности выполнения задач, не определенных в политике привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="0e91b-126">Test ability to execute a task NOT defined in a privileged access policy</span></span>

<span data-ttu-id="0e91b-p105">Во-первых подключение к Exchange управления PowerShell с использованием учетных данных пользователя, настроенных как глобальный администратор в тестовой среде и попытаться создать новое правило журнала. [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) задач в настоящее время не определен в политике привилегированный доступ для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="0e91b-p105">First, connect to Exchange Management PowerShell with the credentials of a user configured as a Global Administrator in your test environment and attempt to create a new Journal rule. The [New-JournalRule](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance/new-journalrule?view=exchange-ps) task is not currently defined in a privileged access policy for your organization.</span></span>

1. <span data-ttu-id="0e91b-129">Откройте на локальном компьютере и войдите в Exchange Online удаленного модуль PowerShell в **Корпорации Майкрософт** > с помощью глобального администратора**Microsoft Exchange Online PowerShell модуля удаленного** учетных записей для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="0e91b-129">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="0e91b-130">В Exchange Powershell управления создайте новое правило журнала для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="0e91b-130">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule1" -Recipient joe@contoso.onmicrosoft.com -JournalEmailAddress barbara@adatum.com -Scope Global -Enabled $true
```
4. <span data-ttu-id="0e91b-131">Представления, что новое правило журнала успешно создан в Exchange PowerShell управления.</span><span class="sxs-lookup"><span data-stu-id="0e91b-131">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

### <a name="create-a-new-privileged-access-policy-for-the-new-journalrule-task"></a><span data-ttu-id="0e91b-132">Создать новую политику привилегированный доступ для задачи New-JournalRule</span><span class="sxs-lookup"><span data-stu-id="0e91b-132">Create a new privileged access policy for the New-JournalRule task</span></span>

> [!NOTE]
> <span data-ttu-id="0e91b-133">Если еще не уже выполнены шаги 1 и 2 из этап 2 в этом руководстве, быть следуя инструкциям для создания группы утверждающий с именем «Утверждающие принципу предоставления минимальных прав доступа» и для включения привилегированный доступ в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="0e91b-133">If you haven't already completed the Steps 1 and 2 from Phase 2 of this guide, be sure follow the steps to create an approver's group named "Privilege Access Approvers" and to enable privileged access in your test environment.</span></span>

1. <span data-ttu-id="0e91b-134">Войдите в [Центр администрирования Microsoft 365](https://portal.office.com) , используя учетные данные учетной записи глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="0e91b-134">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using credentials the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="0e91b-135">В центре администрирования, перейдите в раздел **Параметры** > **безопасности и конфиденциальности** > **правами доступа**.</span><span class="sxs-lookup"><span data-stu-id="0e91b-135">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="0e91b-136">Выберите **Управление политиками доступа и запросов**.</span><span class="sxs-lookup"><span data-stu-id="0e91b-136">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="0e91b-137">Выберите **Настройка политик** , а затем выберите **Добавить политику**.</span><span class="sxs-lookup"><span data-stu-id="0e91b-137">Select **Configure policies** and select **Add a policy**.</span></span>

5. <span data-ttu-id="0e91b-138">Из раскрывающегося списка полей выберите или введите следующие значения:</span><span class="sxs-lookup"><span data-stu-id="0e91b-138">From the drop-down fields, select or enter the following values:</span></span>
    
    <span data-ttu-id="0e91b-139">**Тип политики**: задачи</span><span class="sxs-lookup"><span data-stu-id="0e91b-139">**Policy type**: Task</span></span>

    <span data-ttu-id="0e91b-140">**Область действия политики**: Exchange</span><span class="sxs-lookup"><span data-stu-id="0e91b-140">**Policy scope**: Exchange</span></span>

    <span data-ttu-id="0e91b-141">**Имя политики**: новые правила журнала</span><span class="sxs-lookup"><span data-stu-id="0e91b-141">**Policy name**: New Journal Rule</span></span>

    <span data-ttu-id="0e91b-142">**Тип утверждения**: вручную</span><span class="sxs-lookup"><span data-stu-id="0e91b-142">**Approval type**: Manual</span></span>

    <span data-ttu-id="0e91b-143">**Группа утверждения**: привилегированной утверждающие доступа</span><span class="sxs-lookup"><span data-stu-id="0e91b-143">**Approval group**: Privileged Access Approvers</span></span>

6. <span data-ttu-id="0e91b-p106">Выберите **Создать** и затем **Закрыть**. Может занять несколько минут для политики, чтобы полностью настроить и включить. Обязательно Освободите времени для политики, чтобы полностью включить перед началом тестирования требование утверждения на следующем этапе.</span><span class="sxs-lookup"><span data-stu-id="0e91b-p106">Select **Create** and then **Close**. It may take a few minutes for the policy to be fully configured and enabled. Be sure to allow time for the policy to be fully enabled before testing the approval requirement in the next step.</span></span>

### <a name="test-approval-requirement-for-the-new-journalrule-task-defined-in-a-privileged-access-policy"></a><span data-ttu-id="0e91b-147">Тестирование требование утверждения для задачи New-JournalRule, определенных в политике привилегированный доступ</span><span class="sxs-lookup"><span data-stu-id="0e91b-147">Test approval requirement for the New-JournalRule task defined in a privileged access policy</span></span>

1. <span data-ttu-id="0e91b-148">Откройте на локальном компьютере и войдите в Exchange Online удаленного модуль PowerShell в **Корпорации Майкрософт** > **Microsoft Exchange Online удаленного модуль PowerShell** с помощью глобального администратора в с помощью учетной записи для теста Среда.</span><span class="sxs-lookup"><span data-stu-id="0e91b-148">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using an using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="0e91b-149">В Exchange Powershell управления создайте новое правило журнала для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="0e91b-149">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="0e91b-150">Представление «Insuffient разрешения» ошибка в Exchange PowerShell управления:</span><span class="sxs-lookup"><span data-stu-id="0e91b-150">View "Insuffient permissions" error in Exchange Management PowerShell:</span></span>

```
Insufficient permissions. Please raise an elevated access request for this task.
    + CategoryInfo          : NotSpecified: (:) [], LocalizedException
    + FullyQualifiedErrorId : [Server=CY1PR00MB0220,RequestId=7b8c7470-ddd0-4528-a01e-5e20ecc9bd54,TimeStamp=9/19/2018
    7:38:34 PM] [FailureCategory=Cmdlet-LocalizedException] 882BD051
    + PSComputerName        : outlook.office365.com
```

### <a name="request-access-to-create-a-new-journal-rule-using-the-new-journalrule-task"></a><span data-ttu-id="0e91b-151">Запросить доступ для создания нового правила журнала с помощью New-JournalRule задач</span><span class="sxs-lookup"><span data-stu-id="0e91b-151">Request access to create a new Journal Rule using the New-JournalRule task</span></span>

1. <span data-ttu-id="0e91b-152">Войдите в [Центр администрирования Microsoft 365](https://portal.office.com) , используя учетную запись глобального администратора для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="0e91b-152">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="0e91b-153">В центре администрирования, перейдите в раздел **Параметры** > **безопасности и конфиденциальности** > **правами доступа**.</span><span class="sxs-lookup"><span data-stu-id="0e91b-153">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="0e91b-154">Выберите **Управление политиками доступа и запросов**.</span><span class="sxs-lookup"><span data-stu-id="0e91b-154">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="0e91b-p107">Выберите **Создать запрос**. Из раскрывающегося списка полей выберите соответствующие значения для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="0e91b-p107">Select **New request**. From the drop-down fields, select the appropriate values for your organization:</span></span>

    <span data-ttu-id="0e91b-157">**Тип запроса**: задачи</span><span class="sxs-lookup"><span data-stu-id="0e91b-157">**Request type**: Task</span></span>

    <span data-ttu-id="0e91b-158">**Область запроса**: Exchange</span><span class="sxs-lookup"><span data-stu-id="0e91b-158">**Request scope**: Exchange</span></span>

    <span data-ttu-id="0e91b-159">**Запрос**: новые правила журнала</span><span class="sxs-lookup"><span data-stu-id="0e91b-159">**Request for**: New Journal Rule</span></span>

    <span data-ttu-id="0e91b-160">**Длительность (в часах)**: 2</span><span class="sxs-lookup"><span data-stu-id="0e91b-160">**Duration (hours)**: 2</span></span>

    <span data-ttu-id="0e91b-161">**Комментарии**: запрашивать разрешения, чтобы создать новое правило журнала</span><span class="sxs-lookup"><span data-stu-id="0e91b-161">**Comments**: Request permission to create a new Journal Rule</span></span>

5. <span data-ttu-id="0e91b-p108">Выберите **Сохранить** и **Закрыть**. Запрос будет отправляться группы утверждающий по электронной почте.</span><span class="sxs-lookup"><span data-stu-id="0e91b-p108">Select **Save** and then **Close**. Your request will be sent to the approver's group via email.</span></span>

### <a name="approve-privileged-access-request-for-the-creation-of-a-new-journal-rule"></a><span data-ttu-id="0e91b-164">Утверждение запроса привилегированный доступ для создания нового правила журнала</span><span class="sxs-lookup"><span data-stu-id="0e91b-164">Approve privileged access request for the creation of a new Journal Rule</span></span>

1. <span data-ttu-id="0e91b-165">Войдите в [Центр администрирования Microsoft 365](https://portal.office.com) , используя учетные данные для пользователя 3 в тестовой среде (членство в группе безопасности «Привилегированной утверждающие доступа» в тестовой среде).</span><span class="sxs-lookup"><span data-stu-id="0e91b-165">Sign into the [Microsoft 365 Admin Center](https://portal.office.com) using the credentials for User 3 in your test environment (member of the "Privileged Access Approvers" security group in your test environment).</span></span>

2. <span data-ttu-id="0e91b-166">В центре администрирования, перейдите в раздел **Параметры** > **безопасности и конфиденциальности** > **правами доступа**.</span><span class="sxs-lookup"><span data-stu-id="0e91b-166">In the Admin Center, go to **Settings** > **Security & Privacy** > **Privileged access**.</span></span>

3. <span data-ttu-id="0e91b-167">Выберите **Управление политиками доступа и запросов**.</span><span class="sxs-lookup"><span data-stu-id="0e91b-167">Select **Manage access policies and requests**.</span></span>

4. <span data-ttu-id="0e91b-p109">Выберите ожидающий запрос и **Утвердить** , чтобы предоставить доступ к учетной записи глобального администратора для создания нового правила журнала. По электронной почте уведомление, подтверждающее, предоставления утверждения будет отправлено на учетную запись глобального администратора (запрашивающего пользователя).</span><span class="sxs-lookup"><span data-stu-id="0e91b-p109">Select the pending request and select **Approve** to grant access to the Global Admin account to create a new Journal Rule. An notification email confirming that approval has been granted will be sent to the Global Admin account (the requesting user).</span></span>  

### <a name="test-creating-a-new-journal-rule-with-privileged-access-approved-for-the-new-journalrule-task"></a><span data-ttu-id="0e91b-170">Создание нового правила журнала с помощью привилегированной доступа утверждено для задачи New-JournalRule тестирования</span><span class="sxs-lookup"><span data-stu-id="0e91b-170">Test creating a new Journal Rule with privileged access approved for the New-JournalRule task</span></span>

1. <span data-ttu-id="0e91b-171">Откройте на локальном компьютере и войдите в Exchange Online удаленного модуль PowerShell в **Корпорации Майкрософт** > с помощью глобального администратора**Microsoft Exchange Online PowerShell модуля удаленного** учетных записей для тестовой среды.</span><span class="sxs-lookup"><span data-stu-id="0e91b-171">On your local computer, open and sign into the the Exchange Online Remote PowerShell Module at **Microsoft Corporation** > **Microsoft Exchange Online Remote PowerShell Module** using the Global Admin account for your test environment.</span></span>

2. <span data-ttu-id="0e91b-172">В Exchange Powershell управления создайте новое правило журнала для вашей организации:</span><span class="sxs-lookup"><span data-stu-id="0e91b-172">In Exchange Management Powershell, create a new Journal rule for your organization:</span></span>

```
New-JournalRule -Name "JournalRule2" -Recipient user1@<your subscription domain> -JournalEmailAddress user1@<your subscription domain> -Scope Global -Enabled $true
```
3. <span data-ttu-id="0e91b-173">Представления, что новое правило журнала успешно создан в Exchange PowerShell управления.</span><span class="sxs-lookup"><span data-stu-id="0e91b-173">View that the new Journal Rule was successfully created in Exchange Management PowerShell.</span></span>

## <a name="next-step"></a><span data-ttu-id="0e91b-174">Следующее действие</span><span class="sxs-lookup"><span data-stu-id="0e91b-174">Next step</span></span>

<span data-ttu-id="0e91b-175">Изучите дополнительные [сведения о защите](m365-enterprise-test-lab-guides.md#information-protection) функций и возможностей в тестовой среде.</span><span class="sxs-lookup"><span data-stu-id="0e91b-175">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="0e91b-176">См. также</span><span class="sxs-lookup"><span data-stu-id="0e91b-176">See also</span></span>

[<span data-ttu-id="0e91b-177">Руководства по лаборатории тестирования для Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0e91b-177">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="0e91b-178">Развертывание Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0e91b-178">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0e91b-179">Документация по Microsoft 365 корпоративный</span><span class="sxs-lookup"><span data-stu-id="0e91b-179">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)