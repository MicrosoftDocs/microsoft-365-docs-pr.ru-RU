---
title: 'Шаг 7: Настройка управления привилегированным доступом'
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
ms.custom: ''
description: Общие сведения и Настройка управления привилегированным доступом.
ms.openlocfilehash: 4fed4daacc17a34563825bf0575880ce06ec6ebd
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2020
ms.locfileid: "43636992"
---
# <a name="step-7-configure-privileged-access-management"></a><span data-ttu-id="a6b3f-103">Шаг 7: Настройка управления привилегированным доступом</span><span class="sxs-lookup"><span data-stu-id="a6b3f-103">Step 7: Configure privileged access management</span></span>

<span data-ttu-id="a6b3f-104">*Этот шаг необязательный; он применяется только к планам E5 и Advanced Compliance Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="a6b3f-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Этап 6. Защита данных](../media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="a6b3f-106">Управление привилегированным доступом включается путем настройки политик, указывающих на доступ по требованию для действий на основе задач в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a6b3f-106">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your tenant.</span></span> <span data-ttu-id="a6b3f-107">Это поможет защитить организацию от нарушений, которые могут использовать существующие учетные записи привилегированного администратора с ограниченным доступом к конфиденциальным данным или к важнейшим параметрам конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a6b3f-107">It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings.</span></span> <span data-ttu-id="a6b3f-108">Например, можно настроить привилегированную политику управления доступом, которая требует явного утверждения для доступа и изменения параметров почтовых ящиков организации в клиенте.</span><span class="sxs-lookup"><span data-stu-id="a6b3f-108">For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your tenant.</span></span>

<span data-ttu-id="a6b3f-109">На этом этапе вы включаете управление привилегированным доступом в клиенте и настраиваете политики привилегированного доступа, обеспечивающие дополнительную защиту доступа на основе задач к данным и параметрам конфигурации для Организации.</span><span class="sxs-lookup"><span data-stu-id="a6b3f-109">In this step, you'll enable privileged access management in your tenant and configure privileged access policies that provide additional security for task-based access to data and configuration settings for your organization.</span></span> <span data-ttu-id="a6b3f-110">Начало работы с привилегированным доступом в Организации состоит из трех основных этапов:</span><span class="sxs-lookup"><span data-stu-id="a6b3f-110">There are three basic steps to get started with privileged access in your organization:</span></span>
- <span data-ttu-id="a6b3f-111">создание группы утверждающего;</span><span class="sxs-lookup"><span data-stu-id="a6b3f-111">Creating an approver's group</span></span>
- <span data-ttu-id="a6b3f-112">включение привилегированного доступа;</span><span class="sxs-lookup"><span data-stu-id="a6b3f-112">Enabling privileged access</span></span>
- <span data-ttu-id="a6b3f-113">создание политик утверждения.</span><span class="sxs-lookup"><span data-stu-id="a6b3f-113">Creating approval policies</span></span>

<span data-ttu-id="a6b3f-p103">Настройка управления привилегированным доступом позволит вашей организации работать без постоянного привилегированного доступа и обеспечить уровень защиты от уязвимостей, связанных с таким постоянным административным доступом. Привилегированный доступ требует утверждения выполнения любой задачи, для которой установлена соответствующая политика утверждения. Пользователи, которым необходимо выполнить задачи, регулируемые политикой утверждения, должны запросить и получить утверждение доступа, чтобы иметь разрешения, необходимые для выполнения определенных в политике задач.</span><span class="sxs-lookup"><span data-stu-id="a6b3f-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="a6b3f-117">Чтобы включить управление привилегированным доступом, ознакомьтесь с разделом [Настройка управления привилегированным доступом](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) .</span><span class="sxs-lookup"><span data-stu-id="a6b3f-117">To enable privileged access management, see the [Configure privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="a6b3f-118">Для получения дополнительных сведений см раздел [Управление привилегированным доступом](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) .</span><span class="sxs-lookup"><span data-stu-id="a6b3f-118">For more information, see the [Privileged access management](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="a6b3f-120">Сведения о том, как можно испытать эту конфигурацию в среде лаборатории тестирования см. в статье [Управление привилегированным доступом: руководство по лаборатории тестирования](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="a6b3f-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="a6b3f-121">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step7), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="a6b3f-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="a6b3f-122">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="a6b3f-122">Next Step</span></span>

[<span data-ttu-id="a6b3f-123">Условия, при выполнении которых можно считать защиту информации настроенной</span><span class="sxs-lookup"><span data-stu-id="a6b3f-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
