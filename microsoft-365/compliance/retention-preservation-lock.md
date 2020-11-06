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
ms.openlocfilehash: 6f6cfc5bef9b93af08fcc9b703b29facb9a7c576
ms.sourcegitcommit: d7975c391e03eeb96e29c1d02e77d2a1433ea67c
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/05/2020
ms.locfileid: "48920717"
---
# <a name="use-preservation-lock-to-restrict-changes-to-retention-policies-and-retention-label-policies"></a><span data-ttu-id="7d609-103">Использование блокировки для сохранения в целях ограничения изменений в политиках хранения и политиках меток хранения.</span><span class="sxs-lookup"><span data-stu-id="7d609-103">Use Preservation Lock to restrict changes to retention policies and retention label policies</span></span>

><span data-ttu-id="7d609-104">*[Руководство по лицензированию Microsoft 365 для обеспечения безопасности и соответствия требованиям](https://aka.ms/ComplianceSD).*</span><span class="sxs-lookup"><span data-stu-id="7d609-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="7d609-105">Функция блокировки для сохранения блокирует политику хранения или политику метки хранения, чтобы никто, в том числе глобальный администратор, не мог отключить политику, удалить ее или сделать менее строгой.</span><span class="sxs-lookup"><span data-stu-id="7d609-105">Preservation Lock locks a retention policy or retention label policy so that no one—including a global admin—can turn off the policy, delete the policy, or make it less restrictive.</span></span> <span data-ttu-id="7d609-106">Эта конфигурация может потребоваться для соблюдения нормативных требований и помогает защититься от недобросовестных администраторов.</span><span class="sxs-lookup"><span data-stu-id="7d609-106">This configuration might be needed for regulatory requirements and can help safeguard against rogue administrators.</span></span>

<span data-ttu-id="7d609-107">Если политика хранения заблокирована, обеспечивается следующее.</span><span class="sxs-lookup"><span data-stu-id="7d609-107">When a policy for retention is locked:</span></span>

- <span data-ttu-id="7d609-108">Никто не может ее отключить</span><span class="sxs-lookup"><span data-stu-id="7d609-108">No one can turn it off</span></span>
- <span data-ttu-id="7d609-109">Места могут быть добавлены, но не удалены</span><span class="sxs-lookup"><span data-stu-id="7d609-109">Locations can be added but not removed</span></span>
- <span data-ttu-id="7d609-110">Срок хранения может быть продлен, но не сокращен.</span><span class="sxs-lookup"><span data-stu-id="7d609-110">You can extend a retention period but not decrease it</span></span>

<span data-ttu-id="7d609-111">Таким образом, действие заблокированной политики может быть продлено или расширено, но его нельзя сократить или отключить.</span><span class="sxs-lookup"><span data-stu-id="7d609-111">In summary, a locked policy can be increased or extended, but it can't be reduced or turned off.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="7d609-112">Прежде чем заблокировать политику хранения или политику метки хранения, важно обдумать последствия этого действия и подтвердить, что оно необходимо для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="7d609-112">Before you lock a retention policy or retention label policy, it's critical that you understand the impact and confirm whether it's required for your organization.</span></span> <span data-ttu-id="7d609-113">Например, это может потребоваться для соблюдения нормативных требований.</span><span class="sxs-lookup"><span data-stu-id="7d609-113">For example, it might be needed to meet regulatory requirements.</span></span> <span data-ttu-id="7d609-114">Администраторы не смогут отключить или удалить эти политики после применения блокировки для сохранения.</span><span class="sxs-lookup"><span data-stu-id="7d609-114">Administrators won't be able to disable or delete these policies after the preservation lock is applied.</span></span>

<span data-ttu-id="7d609-115">Настройте блокировку для сохранения после создания [политики хранения](create-retention-policies.md) или политики меток хранения, которую вы [публикуете](create-apply-retention-labels.md) или которая [применяется автоматически](apply-retention-labels-automatically.md).</span><span class="sxs-lookup"><span data-stu-id="7d609-115">Configure Preservation Lock after you've created a [retention policy](create-retention-policies.md), or a retention label policy that you [publish](create-apply-retention-labels.md) or [auto-apply](apply-retention-labels-automatically.md).</span></span> 

## <a name="how-to-lock-a-retention-policy-or-retention-label-policy"></a><span data-ttu-id="7d609-116">Порядок блокировки политики хранения или политики метки хранения</span><span class="sxs-lookup"><span data-stu-id="7d609-116">How to lock a retention policy or retention label policy</span></span>

<span data-ttu-id="7d609-117">Если вам нужно применять блокировку для сохранения, необходимо использовать Windows PowerShell.</span><span class="sxs-lookup"><span data-stu-id="7d609-117">You must use PowerShell if you need to use Preservation Lock.</span></span> <span data-ttu-id="7d609-118">Так как администраторы не могут отключить или удалить политику хранения после применения этой блокировки, ее включение в пользовательском интерфейсе сделано недоступным, чтобы исключить случайную настройку.</span><span class="sxs-lookup"><span data-stu-id="7d609-118">Because administrators can't disable or delete a policy for retention after this lock is applied, enabling this feature is not available in the UI to safeguard against accidental configuration.</span></span>

<span data-ttu-id="7d609-119">Все политики хранения с любыми настройками поддерживают блокировку для сохранения.</span><span class="sxs-lookup"><span data-stu-id="7d609-119">All policies for retention and with any configuration support Preservation Lock.</span></span>

1. <span data-ttu-id="7d609-120">[Подключение к Центру безопасности и соответствия требованиям Windows PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span><span class="sxs-lookup"><span data-stu-id="7d609-120">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="7d609-121">Найдите название политики, которую вы хотите заблокировать, выполнив команду [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span><span class="sxs-lookup"><span data-stu-id="7d609-121">Find the name of the policy that you want to lock by running [Get-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/get-retentioncompliancepolicy).</span></span> <span data-ttu-id="7d609-122">Например:</span><span class="sxs-lookup"><span data-stu-id="7d609-122">For example:</span></span>
    
   ![Список политик хранения в PowerShell](../media/retention-policy-preservation-lock-get-retentioncompliancepolicy.PNG)

3. <span data-ttu-id="7d609-124">Чтобы применить блокировку для сохранения к политике, выполните командлет [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) с именем политики и параметром *RestrictiveRetention* , которому присвоено значение true:</span><span class="sxs-lookup"><span data-stu-id="7d609-124">To place a Preservation Lock on your policy, run the [Set-RetentionCompliancePolicy](https://docs.microsoft.com/powershell/module/exchange/set-retentioncompliancepolicy) cmdlet with the name of the policy, and the *RestrictiveRetention* parameter set to true:</span></span>
    
    ```powershell
    Set-RetentionCompliancePolicy -Identity "<Name of Policy>" –RestrictiveRetention $true
    ```
    
    <span data-ttu-id="7d609-125">Например:</span><span class="sxs-lookup"><span data-stu-id="7d609-125">For example:</span></span>
    
    ![Параметр RestrictiveRetention в PowerShell](../media/retention-policy-preservation-lock-restrictiveretention.PNG)
    
     <span data-ttu-id="7d609-127">При появлении запроса прочтите и подтвердите ограничения, связанные с настройкой, путем ввода **Y** :</span><span class="sxs-lookup"><span data-stu-id="7d609-127">When prompted, read and acknowledge the restrictions that come with this configuration by entering **Y** :</span></span>
    
   ![Запрос подтверждения блокировки политики хранения в PowerShell](../media/retention-policy-preservation-lock-confirmation-prompt.PNG)

<span data-ttu-id="7d609-129">Теперь к политике применена блокировка для сохранения.</span><span class="sxs-lookup"><span data-stu-id="7d609-129">A Preservation Lock is now placed on the policy.</span></span> <span data-ttu-id="7d609-130">Чтобы подтвердить действие, выполните команду `Get-RetentionCompliancePolicy` еще раз, при этом укажите имя политики и ее параметры.</span><span class="sxs-lookup"><span data-stu-id="7d609-130">To confirm, run `Get-RetentionCompliancePolicy` again, but specify the policy name and display the policy parameters:</span></span>

```powershell
Get-RetentionCompliancePolicy -Identity "<Name of Policy>" |Fl
```

<span data-ttu-id="7d609-131">Вы увидите, что параметру **RestrictiveRetention** присвоено значение **True**.</span><span class="sxs-lookup"><span data-stu-id="7d609-131">You should see **RestrictiveRetention** is set to **True**.</span></span> <span data-ttu-id="7d609-132">Например:</span><span class="sxs-lookup"><span data-stu-id="7d609-132">For example:</span></span>

![Заблокированная политика с отображением всех параметров в PowerShell](../media/retention-policy-preservation-lock-locked-policy.PNG)

## <a name="see-also"></a><span data-ttu-id="7d609-134">См. также</span><span class="sxs-lookup"><span data-stu-id="7d609-134">See also</span></span>

[<span data-ttu-id="7d609-135">Вспомогательные ресурсы для соблюдения нормативных требований к управлению данными и записями</span><span class="sxs-lookup"><span data-stu-id="7d609-135">Resources to help you meet regulatory requirements for information governance and records management</span></span>](retention-regulatory-requirements.md)
