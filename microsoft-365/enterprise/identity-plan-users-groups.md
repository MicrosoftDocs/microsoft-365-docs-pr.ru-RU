---
title: Шаг 1. Планирование пользователей и групп
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
description: В этой статье рассказывается, как спланировать набор пользователей и групп, которые можно использовать в вашей организации.
ms.openlocfilehash: 8062cc2b681f0ae45a8114a6d827f5d1ece2fe3e
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/28/2018
ms.locfileid: "26870431"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="79edd-103">Шаг 1. Планирование пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="79edd-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="79edd-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="79edd-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="79edd-p101">На данном шаге вы создадите свою инфраструктуру идентификации, объединяющую пользователей, группы и членство в группах с функциями обеспечения безопасности, с правильной конфигурацией. Благодаря этому вы сможете выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="79edd-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="79edd-107">Управлять доступом пользователей к ресурсам в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="79edd-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="79edd-108">Защищать доступ с помощью элементов управления, надежно гарантирующих подлинность удостоверений (то есть то, что пользователи являются теми, за кого себя выдают) и доступ с безопасных устройств.</span><span class="sxs-lookup"><span data-stu-id="79edd-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="79edd-109">Подготавливать ресурсы с соответствующими разрешениями в своей среде, чтобы уменьшить риск ущерба и утечки данных.</span><span class="sxs-lookup"><span data-stu-id="79edd-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="79edd-110">Отслеживать среду, чтобы обнаруживать ненормальное поведение пользователей и автоматически выполнять необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="79edd-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="79edd-111">Планировать своего основного поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="79edd-111">Plan your primary identity provider</span></span>

<span data-ttu-id="79edd-p102">Чтобы создать свою инфраструктуру идентификации, вы назначите основного поставщика удостоверений. В этой службе хранятся учетные записи пользователей и их атрибуты, группы и членства в них. Кроме того, эта служба поддерживает непрерывное администрирование этих элементов.</span><span class="sxs-lookup"><span data-stu-id="79edd-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="79edd-114">Если ваша организация переходит на Microsoft 365 корпоративный, то в качестве основного поставщика удостоверений вы можете использовать одну из указанных ниже служб.</span><span class="sxs-lookup"><span data-stu-id="79edd-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="79edd-p103">**Windows Server Active Directory (AD)**. Это поставщик удостоверений интрасети, размещаемый на компьютерах с Windows Server. Обычно эту службу используют организации, у которых имеется локальный поставщик удостоверений.</span><span class="sxs-lookup"><span data-stu-id="79edd-p103">**Windows Server Active Directory (AD)**, an intranet identity provider hosted on computers running Windows Server. This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="79edd-p104">**Azure Active Directory (Azure AD**). Это облачная служба класса "Удостоверение как услуга" (Identity as a Service, IDaaS). Она предоставляет широкие возможности для управления вашей средой и для ее защиты. Обычно эту службу используют организации, у которых нет локальной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="79edd-p104">**Azure Active Directory (Azure AD**), a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment. This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="79edd-p105">Если у вашей организации имеется локальный поставщик удостоверений, вам необходимо синхронизировать свои учетные записи пользователей и группы из Windows Server AD в Azure AD, чтобы упростить доступ к облачным службам Microsoft 365 корпоративный. Кроме того, с помощью Azure AD вы можете создавать группы, существующие только в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="79edd-p105">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from Windows Server AD to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise. You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="79edd-121">После того как вы создадите пользователей и группы в Azure AD, вы сможете выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="79edd-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="79edd-122">Управлять всеми учетными записями Azure AD для всех своих облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="79edd-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="79edd-123">Использовать один и тот же набор элементов управления для защиты приложений в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="79edd-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="79edd-124">Совместно работать с внешними партнерами.</span><span class="sxs-lookup"><span data-stu-id="79edd-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="79edd-125">Отслеживать ненормальное поведение в учетных записях, например подозрительные попытки входа в систему, и автоматически выполнять необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="79edd-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="79edd-126">Чтобы спланировать учетные записи и группы, а также реализовать их, выполните инструкции в двух следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="79edd-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="79edd-127">Распределение пользователей по категориям</span><span class="sxs-lookup"><span data-stu-id="79edd-127">Categorize your users</span></span>
<span data-ttu-id="79edd-p106">Распределить пользователей организации по категориям можно несколькими способами. Например, некоторые пользователи являются сотрудниками и имеют постоянный статус. Некоторые — поставщиками, подрядчиками или партнерами со временным статусом. Другие — внешними пользователями, у которых нет учетных записей пользователей, но при этом необходимо предоставить им доступ к определенным службам и ресурсам для взаимодействия и совместной работы. Ниже приведено несколько примеров.</span><span class="sxs-lookup"><span data-stu-id="79edd-p106">Users in organizations can be categorized in a number of ways. For example, some are employees and have a permanent status. Some are vendors, contractors, or partners that have a temporary status. Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration. For example:</span></span>

- <span data-ttu-id="79edd-133">Учетные записи клиента представляют пользователей в вашей организации, которым вы предоставляете лицензии на доступ к облачным службам.</span><span class="sxs-lookup"><span data-stu-id="79edd-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="79edd-134">Учетные записи типа "бизнес-бизнес" (B2B) представляют пользователей за пределами вашей организации, которых вы приглашаете принять участие в совместной работе.</span><span class="sxs-lookup"><span data-stu-id="79edd-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="79edd-p107">Проведите инвентаризацию типов пользователей в вашей организации. Подумайте, как можно разбить пользователей на группы. Например, вы можете сделать это на основе функций высокого уровня, выполняемых пользователями, или назначении пользователей в организации.</span><span class="sxs-lookup"><span data-stu-id="79edd-p107">Take stock of the types of users to your organization. What are the groupings? For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="79edd-p108">Кроме того, возможно, что к некоторым облачным службам предоставлен доступ пользователям, не входящим в вашу организацию и не имеющим учетных записей пользователей. Вам потребуется обнаружить такие группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="79edd-p108">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-windows-server-ad-and-azure-ad-groups"></a><span data-ttu-id="79edd-140">Планирование групп Windows Server AD и Azure AD</span><span class="sxs-lookup"><span data-stu-id="79edd-140">Plan for Windows Server AD and Azure AD groups</span></span>

<span data-ttu-id="79edd-p109">Группы в Azure AD можно использовать для нескольких целей, и это упрощает управление облачной средой. Например, для групп Azure AD вы можете выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="79edd-p109">You can use groups in Azure AD for several purposes that simplify management of your cloud environment. For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="79edd-143">С помощью функции лицензирования на основе групп автоматически назначать лицензии на Office 365 и Enterprise Mobility + Security (EMS) вашим учетным записям пользователей при их добавлении в Azure AD или синхронизации из Windows Server AD.</span><span class="sxs-lookup"><span data-stu-id="79edd-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from Windows Server AD.</span></span> 
- <span data-ttu-id="79edd-144">Динамически добавлять учетные записи пользователей в определенные группы на основании атрибутов этих учетных записей, например атрибута "Отдел".</span><span class="sxs-lookup"><span data-stu-id="79edd-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="79edd-145">Автоматически подготавливать пользователей для приложений класса "Программное обеспечение как услуга" (Software as a Service, SaaS) и защищать доступ к этим приложениям с помощью многофакторной проверки подлинности и других правил условного доступа.</span><span class="sxs-lookup"><span data-stu-id="79edd-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="79edd-p110">Подготавливать разрешения и уровни доступа для сайтов групп SharePoint Online. Группы Azure AD также можно использовать с политиками Azure Information Protection с заданными областями для защиты файлов с помощью шифрования и разрешений.</span><span class="sxs-lookup"><span data-stu-id="79edd-p110">Provision permissions and levels of access for SharePoint Online team sites. Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="79edd-148">Результаты</span><span class="sxs-lookup"><span data-stu-id="79edd-148">Results</span></span>

<span data-ttu-id="79edd-149">Когда вы завершите этот этап, у вас будут указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="79edd-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="79edd-150">Список учетных записей пользователей в Azure AD, соответствующих сотрудникам вашей организации, а также поставщикам, подрядчикам и внешним партнерам, которые работают на вашу организацию или с ней.</span><span class="sxs-lookup"><span data-stu-id="79edd-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="79edd-151">Набор групп и членства для них в Azure AD, отражающие логические наборы учетных записей пользователей и другие группы для различных целей, например для автоматического лицензирования или подготовки параметров безопасности для облачных служб (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="79edd-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="79edd-152">Прежде чем перейти к следующему шагу, проверьте [условия](identity-exit-criteria.md#crit-identity-user-groups), при выполнении которых можно считать данный шаг завершенным.</span><span class="sxs-lookup"><span data-stu-id="79edd-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>


## <a name="next-step"></a><span data-ttu-id="79edd-153">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="79edd-153">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="79edd-154">Защита учетных записей глобальных администраторов</span><span class="sxs-lookup"><span data-stu-id="79edd-154">Protect global administrator accounts</span></span>](identity-designate-protect-admin-accounts.md) |

