---
title: Шаг 12. Настройка автоматического лицензирования
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается о лицензировании на основе групп для групп Azure AD и о том, как его настроить.
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870421"
---
# <a name="step-12-set-up-automatic-licensing"></a><span data-ttu-id="7b024-103">Шаг 12. Настройка автоматического лицензирования</span><span class="sxs-lookup"><span data-stu-id="7b024-103">Step 12: Set up automatic licensing</span></span>

<span data-ttu-id="7b024-104">*Этот шаг — необязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="7b024-104">*This step is optional and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="7b024-p101">На этом шаге вы настроите группы безопасности в Azure AD для автоматического назначения лицензий из набора подписок всем участникам группы. Эта возможность называется *лицензированием на основе групп*. При добавлении учетной записи пользователя в группу или удалении ее из группы происходит автоматическое назначение или удаление лицензий на подписки группы для учетной записи пользователя.</span><span class="sxs-lookup"><span data-stu-id="7b024-p101">In Step 11, you'll configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group. This is known as *group-based licensing*. If a user account is added to or removed from the group, the licenses for the group’s subscriptions will be automatically assigned or removed from the user account.</span></span>

<span data-ttu-id="7b024-108">Вы настроите группы безопасности Azure AD для Microsoft 365 корпоративный, чтобы можно было назначать обе указанные ниже лицензии.</span><span class="sxs-lookup"><span data-stu-id="7b024-108">For Microsoft 365 Enterprise, you'll configure Azure AD security groups to assign both of these licenses:</span></span>

- <span data-ttu-id="7b024-109">Office 365 корпоративный, план E3 или E5</span><span class="sxs-lookup"><span data-stu-id="7b024-109">Office 365 Enterprise E3 or E5</span></span>
- <span data-ttu-id="7b024-110">Enterprise Mobility + Security (EMS), план E3 или E5.</span><span class="sxs-lookup"><span data-stu-id="7b024-110">Enterprise Mobility + Security (EMS) E3 or E5</span></span>

<span data-ttu-id="7b024-p102">Среди групп, которые вы определили на шаге 2, найдите группы, содержащие список учетных записей, в котором все пользователи группы обязаны иметь обе лицензии: и на Office 365, и на EMS. Убедитесь, что у вас достаточно лицензий для всех участников группы. Если у вас закончатся лицензии, то вам не удастся назначить лицензии новым пользователям, пока у вас не появится необходимое количество лицензий.</span><span class="sxs-lookup"><span data-stu-id="7b024-p102">Using the groups you identified in Step 2, look for groups that contain a list of accounts where all users in that group must have both Office 365 and EMS licenses. Make sure you have enough licenses for all the group members. If you run out of licenses, new users won’t be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="7b024-114">Не следует настраивать *лицензирование на основе групп* для групп, содержащих учетные записи типа "бизнес-бизнес" (B2B) в Azure.</span><span class="sxs-lookup"><span data-stu-id="7b024-114">You should not configure *group-based licensing* for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="7b024-115">См. дополнительные сведения в статье [Основы группового лицензирования в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="7b024-115">See additional information on [Group-based licensing basics in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal).</span></span>

<span data-ttu-id="7b024-116">См. статью с описанием [действий по настройке лицензирования на основе групп для группы безопасности Azure](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span><span class="sxs-lookup"><span data-stu-id="7b024-116">See the [steps to configure group-based licensing for an Azure security group](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal).</span></span>

<span data-ttu-id="7b024-117">Ниже перечислены результаты, которые вы получите после выполнения данного шага.</span><span class="sxs-lookup"><span data-stu-id="7b024-117">The results of this step are:</span></span>

- <span data-ttu-id="7b024-118">Вы определили группы безопасности, подходящие для лицензирования на основе групп.</span><span class="sxs-lookup"><span data-stu-id="7b024-118">You've identified which security groups are appropriate for group-based licensing.</span></span>
- <span data-ttu-id="7b024-119">Вы настроили эти группы для лицензирования на основе групп.</span><span class="sxs-lookup"><span data-stu-id="7b024-119">You've configured these groups for group-based licensing.</span></span>

|||
|:-------|:-----|
|![Руководства по лаборатории тестирования для Microsoft Cloud](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [<span data-ttu-id="7b024-121">Руководства по лаборатории тестирования: автоматизация лицензий и членства в группах</span><span class="sxs-lookup"><span data-stu-id="7b024-121">Test Lab Guide: Automate licenses and group membership</span></span>](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

<span data-ttu-id="7b024-122">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-group-license), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="7b024-122">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-group-license) for this step.</span></span>

## <a name="next-step"></a><span data-ttu-id="7b024-123">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="7b024-123">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [<span data-ttu-id="7b024-124">Отслеживание действий в клиенте и при входе в систему</span><span class="sxs-lookup"><span data-stu-id="7b024-124">Monitor tenant and sign-in activity</span></span>](identity-azure-ad-access-usage-reporting.md) |

