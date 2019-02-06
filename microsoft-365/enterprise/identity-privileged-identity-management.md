---
title: Шаг 3. Настройка роли глобального администратора, используемой по требованию
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этом разделе рассказывается, как настроить Azure AD Privileged Identity Management.
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870630"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a><span data-ttu-id="659c2-103">Шаг 3. Настройка роли глобального администратора, используемой по требованию</span><span class="sxs-lookup"><span data-stu-id="659c2-103">Step 3: Set up on-demand global administrators</span></span>

<span data-ttu-id="659c2-104">*Этот шаг необязательный; он применяется только к плану E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="659c2-104">*This step is optional and applies only to the E5 version of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="659c2-p101">На этом шаге потребуется настроить Azure AD Privileged Identity Management (PIM), чтобы сократить количество времени, на протяжении которого ваши учетные записи глобального администратора будут уязвимы для атак злоумышленников. PIM позволят своевременно назначать роль глобального администратора, когда в этом возникает необходимость.</span><span class="sxs-lookup"><span data-stu-id="659c2-p101">In this step, you'll set up Azure AD Privileged Identity Management (PIM) to reduce the amount of time that your global administrator accounts are vulnerable to attack by malicious users. PIM provides on-demand, just-in-time assignment of the global administrator role when needed.</span></span>  

<span data-ttu-id="659c2-p102">Вместо присвоения вашим учетным записям глобального администратора статуса администратора на бессрочной основе, им присваивается статус администратора, наделенного соответствующими полномочиями. Роль глобального администратора будет неактивной, пока она кому-либо не потребуется. Затем необходимо выполнить процесс активации, чтобы добавить роль глобального администратора в учетную запись глобального администратора на определенный период времени. По истечении такого периода PIM удаляет роль глобального администратора из учетной записи глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="659c2-p102">Instead of your global administrator accounts being a permanent admin, they become eligible admins. The global administrator role is inactive until someone needs it. You'll then complete an activation process to add the global administrator role to the global administrator account for a specific amount of time. When the time expires, PIM removes the global administrator role from the global administrator account.</span></span>

<span data-ttu-id="659c2-p103">Функция Privileged Identity Management доступна с лицензией на Azure Active Directory Premium P2, которая входит в план Microsoft 365 корпоративный E5. Кроме того, вы можете приобрести отдельные лицензии на Azure Active Directory Premium P2 для ваших учетных записей глобального администратора.</span><span class="sxs-lookup"><span data-stu-id="659c2-p103">PIM is available with Azure Active Directory Premium P2, which is included with Microsoft 365 Enterprise E5. Alternately, you can purchase individual Azure Active Directory Premium P2 licenses for your global administrator accounts.</span></span>

<span data-ttu-id="659c2-113">Чтобы включить Azure PIM для вашего клиента Azure AD и учетных записей глобального администратора, см. [указания по настройке PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span><span class="sxs-lookup"><span data-stu-id="659c2-113">To enable Azure PIM for your Azure AD tenant and global administrator accounts, see the [steps to configure PIM](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure).</span></span>

<span data-ttu-id="659c2-114">Чтобы разработать комплексный стратегический план защиты привилегированного доступа от кибератак, см. статью [Защита привилегированного доступа для гибридных и облачных развертываний в Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span><span class="sxs-lookup"><span data-stu-id="659c2-114">To develop a comprehensive roadmap to secure privileged access against cyber attackers, see [Securing privileged access for hybrid and cloud deployments in Azure AD](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices).</span></span>

<span data-ttu-id="659c2-115">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-pim), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="659c2-115">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-pim) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="659c2-116">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="659c2-116">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [<span data-ttu-id="659c2-117">Упрощение процедуры сброса паролей</span><span class="sxs-lookup"><span data-stu-id="659c2-117">Simplify password resets</span></span>](identity-password-reset.md) |

