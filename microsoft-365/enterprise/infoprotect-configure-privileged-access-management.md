---
title: Шаг 7. Настройка управления привилегированным доступом для Office 365
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
description: В этой статье рассказывается, как настроить управление привилегированным доступом для Office 365.
ms.openlocfilehash: da047d21094854f15fdb39fc46fd046a1c4605ed
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600966"
---
# <a name="step-7-configure-privileged-access-management-for-office-365"></a><span data-ttu-id="bc0a7-103">Шаг 7. Настройка управления привилегированным доступом для Office 365</span><span class="sxs-lookup"><span data-stu-id="bc0a7-103">Step 7: Configure privileged access management for Office 365</span></span>

<span data-ttu-id="bc0a7-104">*Этот шаг необязательный; он применяется только к планам E5 и Advanced Compliance Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="bc0a7-104">*This step is optional and applies only to the E5 and Advanced Compliance versions of Microsoft 365 Enterprise*</span></span>

![Этап 6. Защита данных](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)

<span data-ttu-id="bc0a7-p101">Управление привилегированным доступом включается посредством настройки политик, определяющих своевременный доступ для действий на основе задач в вашем клиенте Office 365. Вашей организации может понадобиться защита от нарушений с использованием существующих привилегированных учетных записей администратора с постоянным доступом к конфиденциальным данным или доступом к критическим параметрам конфигурации. Например, можно настроить политику управления привилегированным доступом так, чтобы требовалось явное утверждение для доступа к параметрам почтового ящика организации и их изменения в клиенте Office 365.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-p101">Privileged access management is enabled by configuring policies that specify just-in-time access for task-based activities in your Office 365 tenant. It can help protect your organization from breaches that may use existing privileged administrator accounts with standing access to sensitive data or access to critical configuration settings. For example, you could configure a privileged access management policy that requires explicit approval to access and change organization mailbox settings in your Office 365 tenant.</span></span>

<span data-ttu-id="bc0a7-p102">На этом этапе вы включаете управление привилегированным доступом в вашем клиенте Office 365 и настраиваете политики привилегированного доступа, которые обеспечивают дополнительную защиту для доступа на основе задач к данным Office 365 и параметрам конфигурации для вашей организации. Существует три основных этапа настройки управления привилегированным доступом в организации Office 365:</span><span class="sxs-lookup"><span data-stu-id="bc0a7-p102">In this step, you'll enable privileged access management in your Office 365 tenant and configure privileged access policies that provide additional security for task-based access to Office 365 data and configuration settings for your organization. There are three basic steps to get started with privileged access in your Office 365 organization:</span></span>
- <span data-ttu-id="bc0a7-111">создание группы утверждающего;</span><span class="sxs-lookup"><span data-stu-id="bc0a7-111">Creating an approver's group</span></span>
- <span data-ttu-id="bc0a7-112">включение привилегированного доступа;</span><span class="sxs-lookup"><span data-stu-id="bc0a7-112">Enabling privileged access</span></span>
- <span data-ttu-id="bc0a7-113">создание политик утверждения.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-113">Creating approval policies</span></span>

<span data-ttu-id="bc0a7-p103">Настройка управления привилегированным доступом позволит вашей организации работать без постоянного привилегированного доступа и обеспечить уровень защиты от уязвимостей, связанных с таким постоянным административным доступом. Привилегированный доступ требует утверждения выполнения любой задачи, для которой установлена соответствующая политика утверждения. Пользователи, которым необходимо выполнить задачи, регулируемые политикой утверждения, должны запросить и получить утверждение доступа, чтобы иметь разрешения, необходимые для выполнения определенных в политике задач.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-p103">One configured, privileged access management will enable your organization to operate with zero standing privileges and provide a layer of defense against vulnerabilities arising because of such standing administrative access. Privileged access requires approvals for executing any task that has an associated approval policy defined. Users needing to execute tasks included in the an approval policy must request and be granted access approval in order to have permissions necessary to execute tasks defined in the policy.</span></span>

<span data-ttu-id="bc0a7-117">Чтобы включить управление привилегированным доступом в Office 365, см. статью [Настройка управления привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration).</span><span class="sxs-lookup"><span data-stu-id="bc0a7-117">To enable Office 365 privileged access management, see the [Configure privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-configuration) topic.</span></span>

<span data-ttu-id="bc0a7-118">Дополнительные сведения см. в статье [Управление привилегированным доступом в Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview).</span><span class="sxs-lookup"><span data-stu-id="bc0a7-118">For more information, see the [Privileged access management in Office 365](https://docs.microsoft.com/office365/securitycompliance/privileged-access-management-overview) topic.</span></span>


|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)|  <span data-ttu-id="bc0a7-120">Сведения о том, как можно испытать эту конфигурацию в среде лаборатории тестирования см. в статье [Управление привилегированным доступом: руководство по лаборатории тестирования](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span><span class="sxs-lookup"><span data-stu-id="bc0a7-120">To practice this configuration in a test lab environment, see the [Privileged access management Test Lab Guide](privileged-access-microsoft-365-enterprise-dev-test-environment.md).</span></span> |
|||

<span data-ttu-id="bc0a7-121">Прежде чем перейти к следующему шагу, проверьте [условия](infoprotect-exit-criteria.md#crit-infoprotect-step7), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="bc0a7-121">As an interim checkpoint, see the [exit criteria](infoprotect-exit-criteria.md#crit-infoprotect-step7) corresponding to this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="bc0a7-122">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="bc0a7-122">Next Step</span></span>

[<span data-ttu-id="bc0a7-123">Условия, при выполнении которых можно считать защиту информации настроенной</span><span class="sxs-lookup"><span data-stu-id="bc0a7-123">Information protection infrastructure exit criteria</span></span>](infoprotect-exit-criteria.md)
