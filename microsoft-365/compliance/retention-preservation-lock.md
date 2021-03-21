---
title: Использование блокировки для сохранения в целях ограничения изменений в политиках хранения и политиках меток хранения.
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: Используйте блокировку для сохранения совместно с политиками хранения и политиками меток хранения, чтобы обеспечить соответствие нормативным требованиям и защититься от недобросовестных администраторов.
ms.openlocfilehash: 72f667b970b4257a3a540fb74a121c620892b56d
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922533"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="e62c2-103">Использование блокировки для сохранения в целях ограничения изменений в политиках хранения и политиках меток хранения.</span><span class="sxs-lookup"><span data-stu-id="e62c2-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="e62c2-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span><span class="sxs-lookup"><span data-stu-id="e62c2-104">*[Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).*</span></span>

<span data-ttu-id="e62c2-105">Функция блокировки для сохранения блокирует политику хранения или политику метки хранения, чтобы никто, в том числе глобальный администратор, не мог отключить политику, удалить ее или сделать менее строгой.</span><span class="sxs-lookup"><span data-stu-id="e62c2-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="e62c2-106">Эта конфигурация может потребоваться для соблюдения нормативных требований и помогает защититься от недобросовестных администраторов.</span><span class="sxs-lookup"><span data-stu-id="e62c2-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="e62c2-107">Когда политика хранения заблокирована:</span><span class="sxs-lookup"><span data-stu-id="e62c2-107">When a retention policy is locked:</span></span>

- <span data-ttu-id="e62c2-108">Никто не может отключить или удалить политику</span><span class="sxs-lookup"><span data-stu-id="e62c2-108">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="e62c2-109">Расположения можно добавлять, но не удалять</span><span class="sxs-lookup"><span data-stu-id="e62c2-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="e62c2-110">Вы можете продлить срок хранения, но не уменьшить его</span><span class="sxs-lookup"><span data-stu-id="e62c2-110">You can extend the retention period but not decrease it</span></span>

<span data-ttu-id="e62c2-111">Когда политика меток хранения заблокирована:</span><span class="sxs-lookup"><span data-stu-id="e62c2-111">When a retention label policy is locked:</span></span>

- <span data-ttu-id="e62c2-112">Никто не может отключить или удалить политику</span><span class="sxs-lookup"><span data-stu-id="e62c2-112">No one can disable the policy or delete it</span></span>
- <span data-ttu-id="e62c2-113">Расположения можно добавлять, но не удалять</span><span class="sxs-lookup"><span data-stu-id="e62c2-113">Locations can be added but not removed</span></span>
- <span data-ttu-id="e62c2-114">Метки можно добавлять, но не удалять</span><span class="sxs-lookup"><span data-stu-id="e62c2-114">Labels can be added but not removed</span></span>

<span data-ttu-id="e62c2-115">Таким образом, действие заблокированной политики может быть продлено или расширено, но его нельзя сократить или отключить.</span><span class="sxs-lookup"><span data-stu-id="e62c2-115">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e62c2-116">Прежде чем заблокировать политику хранения или политику метки хранения, важно обдумать последствия этого действия и подтвердить, что оно необходимо для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="e62c2-116">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="e62c2-117">Например, это может потребоваться для соблюдения нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="e62c2-117">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="e62c2-118">Администраторы не смогут отключить или удалить эти политики после применения блокировки для сохранения.</span><span class="sxs-lookup"><span data-stu-id="e62c2-118">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="e62c2-119">Настройте блокировку для сохранения после создания [политики хранения](create-retention-policies.md) или политики меток хранения, которую вы [публикуете](create-apply-retention-labels.md) или которая [применяется автоматически](apply-retention-labels-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="e62c2-119">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

> [!NOTE]
> <span data-ttu-id="e62c2-120">Блокировка политики меток не запрещает администратору сократить период хранения в метке, включенной в заблокированную политику.</span><span class="sxs-lookup"><span data-stu-id="e62c2-120">Locking a label policy doesn't prevent an administrator from reducing the retention period in a label that is included in the locked policy.</span></span> <span data-ttu-id="e62c2-121">Это требование с другими ограничениями можно выполнить при настройке метки для маркировки элементов в качестве [нормативных записей](records-management.md#records).</span><span class="sxs-lookup"><span data-stu-id="e62c2-121">That requirement, with other restrictions, can be met when you configure a label to mark items as a [regulatory record](records-management.md#records).</span></span>

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="e62c2-122">Порядок блокировки политики хранения или политики метки хранения</span><span class="sxs-lookup"><span data-stu-id="e62c2-122">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="e62c2-123">Если вам нужно применять блокировку для сохранения, необходимо использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e62c2-123">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="e62c2-124">Так как администраторы не могут отключить или удалить политику хранения после применения этой блокировки, ее включение в пользовательском интерфейсе сделано недоступным, чтобы исключить случайную настройку.</span><span class="sxs-lookup"><span data-stu-id="e62c2-124">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="e62c2-125">Все политики хранения с любыми настройками поддерживают блокировку для сохранения.</span><span class="sxs-lookup"><span data-stu-id="e62c2-125">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="e62c2-126">[Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="e62c2-126">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="e62c2-127">Найдите название политики, которую вы хотите заблокировать, выполнив команду [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="e62c2-127">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="e62c2-128">Например:</span><span class="sxs-lookup"><span data-stu-id="e62c2-128">For example:</span></span>
    
   ![Список политик хранения в PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="e62c2-130">Чтобы применить блокировку для сохранения к политике, выполните командлет [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) с именем политики и параметром *RestrictiveRetention*, которому присвоено значение true:</span><span class="sxs-lookup"><span data-stu-id="e62c2-130">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="e62c2-131">Например,</span><span class="sxs-lookup"><span data-stu-id="e62c2-131">For example:</span></span>
    
    ![Параметр RestrictiveRetention в PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="e62c2-133">При появлении запроса прочтите и подтвердите ограничения, связанные с настройкой, путем ввода **Y**:</span><span class="sxs-lookup"><span data-stu-id="e62c2-133">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y**:</span></span>
    
   ![Запрос подтверждения блокировки политики хранения в PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="e62c2-135">Теперь к политике применена блокировка для сохранения.</span><span class="sxs-lookup"><span data-stu-id="e62c2-135">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="e62c2-136">Чтобы подтвердить действие, выполните команду `Get-RetentionCompliancePolicy` еще раз, при этом укажите имя политики и ее параметры.</span><span class="sxs-lookup"><span data-stu-id="e62c2-136">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="e62c2-137">Вы увидите, что параметру **RestrictiveRetention** присвоено значение **True**.</span><span class="sxs-lookup"><span data-stu-id="e62c2-137">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="e62c2-138">Например:</span><span class="sxs-lookup"><span data-stu-id="e62c2-138">For example:</span></span>

![Заблокированная политика с отображением всех параметров в PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="e62c2-140">См. также</span><span class="sxs-lookup"><span data-stu-id="e62c2-140">See also</span></span>

[<span data-ttu-id="e62c2-141">Вспомогательные ресурсы для соблюдения нормативных требований к управлению данными и записями</span><span class="sxs-lookup"><span data-stu-id="e62c2-141">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)