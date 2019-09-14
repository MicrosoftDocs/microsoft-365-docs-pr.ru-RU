---
title: Шаг 1. Планирование пользователей и групп
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: В этой статье рассказывается, как спланировать набор пользователей и групп, которые можно использовать в вашей организации.
ms.openlocfilehash: 05b854c182b6f624cf143ed93920c344391ee416
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981810"
---
# <a name="step-1-plan-for-users-and-groups"></a><span data-ttu-id="6edde-103">Шаг 1. Планирование пользователей и групп</span><span class="sxs-lookup"><span data-stu-id="6edde-103">Step 1: Plan for users and groups</span></span>

<span data-ttu-id="6edde-104">*Этот шаг — обязательный; он применяется к планам E3 и E5 Microsoft 365 корпоративный.*</span><span class="sxs-lookup"><span data-stu-id="6edde-104">*This step is required and applies to both the E3 and E5 versions of Microsoft 365 Enterprise*</span></span>

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

<span data-ttu-id="6edde-p101">На данном шаге вы создадите свою инфраструктуру идентификации, объединяющую пользователей, группы и членство в группах с функциями обеспечения безопасности, с правильной конфигурацией. Благодаря этому вы сможете выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6edde-p101">In this step, you'll create your identity infrastructure that combines users, groups, and group membership with security features in the correct configuration. This allows you to:</span></span>

- <span data-ttu-id="6edde-107">Управлять доступом пользователей к ресурсам в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="6edde-107">Maintain control over who has access to resources in your environment.</span></span>
- <span data-ttu-id="6edde-108">Защищать доступ с помощью элементов управления, надежно гарантирующих подлинность удостоверений (то есть то, что пользователи являются теми, за кого себя выдают) и доступ с безопасных устройств.</span><span class="sxs-lookup"><span data-stu-id="6edde-108">Secure access with controls that ensure strong assurances of identity (users are who they say they are) and access from safe devices.</span></span>
- <span data-ttu-id="6edde-109">Подготавливать ресурсы с соответствующими разрешениями в своей среде, чтобы уменьшить риск ущерба и утечки данных.</span><span class="sxs-lookup"><span data-stu-id="6edde-109">Provision resources in your environment with appropriate permissions to reduce the potential for harm and data leakage.</span></span> 
- <span data-ttu-id="6edde-110">Отслеживать среду, чтобы обнаруживать ненормальное поведение пользователей и автоматически выполнять необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="6edde-110">Monitor your environment for anomalous user behavior and automatically taking action.</span></span>

## <a name="plan-your-primary-identity-provider"></a><span data-ttu-id="6edde-111">Планировать своего основного поставщика удостоверений.</span><span class="sxs-lookup"><span data-stu-id="6edde-111">Plan your primary identity provider</span></span>

<span data-ttu-id="6edde-p102">Чтобы создать свою инфраструктуру идентификации, вы назначите основного поставщика удостоверений. В этой службе хранятся учетные записи пользователей и их атрибуты, группы и членства в них. Кроме того, эта служба поддерживает непрерывное администрирование этих элементов.</span><span class="sxs-lookup"><span data-stu-id="6edde-p102">To create your identity infrastructure, you'll designate a primary identity provider. This service stores user accounts and their attributes, groups and their memberships, and supports their ongoing administration.</span></span>

<span data-ttu-id="6edde-114">Если ваша организация переходит на Microsoft 365 корпоративный, то в качестве основного поставщика удостоверений вы можете использовать одну из указанных ниже служб.</span><span class="sxs-lookup"><span data-stu-id="6edde-114">When your organization adopts Microsoft 365 Enterprise, your primary identity provider is either:</span></span>

- <span data-ttu-id="6edde-115">**Доменные службы Active Directory (AD DS)**. Это поставщик удостоверений интрасети, который размещается на компьютерах с Windows Server.</span><span class="sxs-lookup"><span data-stu-id="6edde-115">**Active Directory Domain Services (AD DS)**, an intranet identity provider hosted on computers running Windows Server.</span></span> <span data-ttu-id="6edde-116">Как правило, эти службы используются в тех организациях, где уже есть локальный поставщик удостоверений.</span><span class="sxs-lookup"><span data-stu-id="6edde-116">This is typically used by organizations that have an existing on-premises identity provider.</span></span>
- <span data-ttu-id="6edde-117">**Azure Active Directory (Azure AD)**. Это облачная служба класса "удостоверение как услуга" (IDaaS), предоставляющая широкие возможности для управления средой и ее защиты.</span><span class="sxs-lookup"><span data-stu-id="6edde-117">**Azure Active Directory (Azure AD)**, a cloud-based Identity as a Service (IDaaS) that provides a broad range of capabilities for managing and protecting your environment.</span></span> <span data-ttu-id="6edde-118">Как правило, эта служба используется в тех организациях, где еще нет локальной инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="6edde-118">This is typically used by organizations that have no existing on-premises infrastructure.</span></span>

<span data-ttu-id="6edde-119">Если у вашей организации есть локальный поставщик удостоверений, вам необходимо синхронизировать свои учетные записи пользователей и группы из доменных служб AD DS в Azure AD, чтобы упростить доступ к облачным службам Microsoft 365 корпоративный.</span><span class="sxs-lookup"><span data-stu-id="6edde-119">If your organization has an existing on-premises identity provider, you need to synchronize your user accounts and groups from AD DS to Azure AD to provide more seamless access to the cloud-based services of Microsoft 365 Enterprise.</span></span> <span data-ttu-id="6edde-120">Кроме того, с помощью Azure AD вы можете создавать группы, существующие только в Microsoft Cloud.</span><span class="sxs-lookup"><span data-stu-id="6edde-120">You can also use Azure AD to create and manage groups that exist only in the Microsoft cloud.</span></span>

<span data-ttu-id="6edde-121">После того как вы создадите пользователей и группы в Azure AD, вы сможете выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6edde-121">After you have your users and groups in Azure AD, you can:</span></span>

- <span data-ttu-id="6edde-122">Управлять всеми учетными записями Azure AD для всех своих облачных приложений.</span><span class="sxs-lookup"><span data-stu-id="6edde-122">Manage all the Azure AD accounts for all your cloud applications.</span></span> 
- <span data-ttu-id="6edde-123">Использовать один и тот же набор элементов управления для защиты приложений в вашей среде.</span><span class="sxs-lookup"><span data-stu-id="6edde-123">Use the same set of controls to protect access to applications across your environment.</span></span>
- <span data-ttu-id="6edde-124">Совместно работать с внешними партнерами.</span><span class="sxs-lookup"><span data-stu-id="6edde-124">Collaborate with external partners.</span></span>
- <span data-ttu-id="6edde-125">Отслеживать ненормальное поведение в учетных записях, например подозрительные попытки входа в систему, и автоматически выполнять необходимые действия.</span><span class="sxs-lookup"><span data-stu-id="6edde-125">Monitor anomalous account behavior, such as suspicious sign-in attempts, and automatically act.</span></span>

<span data-ttu-id="6edde-126">Чтобы спланировать учетные записи и группы, а также реализовать их, выполните инструкции в двух следующих разделах.</span><span class="sxs-lookup"><span data-stu-id="6edde-126">Follow the instructions in the next two sections to plan for and implement your user accounts and groups.</span></span>

## <a name="categorize-your-users"></a><span data-ttu-id="6edde-127">Распределение пользователей по категориям</span><span class="sxs-lookup"><span data-stu-id="6edde-127">Categorize your users</span></span>
<span data-ttu-id="6edde-128">Пользователей в организациях можно классифицировать несколькими способами.</span><span class="sxs-lookup"><span data-stu-id="6edde-128">Users in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="6edde-129">Например, некоторые из них имеют статус постоянных сотрудников.</span><span class="sxs-lookup"><span data-stu-id="6edde-129">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="6edde-130">Некоторые являются поставщиками, подрядчиками или партнерами с временным статусом.</span><span class="sxs-lookup"><span data-stu-id="6edde-130">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="6edde-131">Кроме того, существуют внешние пользователи, у которых нет учетных записей, но которым все равно необходимо предоставить доступ к определенным службам и ресурсам в целях взаимодействия и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="6edde-131">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="6edde-132">Например:</span><span class="sxs-lookup"><span data-stu-id="6edde-132">For example:</span></span>

- <span data-ttu-id="6edde-133">учетные записи клиента представляют пользователей в вашей организации, которым вы предоставляете лицензии на доступ к облачным службам;</span><span class="sxs-lookup"><span data-stu-id="6edde-133">Tenant accounts represent users within your organization that you license for cloud services</span></span>
- <span data-ttu-id="6edde-134">учетные записи типа "бизнес-бизнес" (B2B) представляют пользователей за пределами вашей организации, которых вы приглашаете принять участие в совместной работе.</span><span class="sxs-lookup"><span data-stu-id="6edde-134">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="6edde-135">Рассмотрите типы пользователей в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="6edde-135">Take stock of the types of users to your organization.</span></span> <span data-ttu-id="6edde-136">Как они группируются?</span><span class="sxs-lookup"><span data-stu-id="6edde-136">What are the groupings?</span></span> <span data-ttu-id="6edde-137">Например, вы можете группировать пользователей по ролям высокого уровня или обязанностям в организации.</span><span class="sxs-lookup"><span data-stu-id="6edde-137">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="6edde-138">Кроме того, доступ к некоторым облачным службам можно предоставлять пользователям за пределами организации, у которых нет учетных записей.</span><span class="sxs-lookup"><span data-stu-id="6edde-138">Additionally, some cloud services can be shared with users outside your organization without any user accounts.</span></span> <span data-ttu-id="6edde-139">Вам потребуется определить и эти группы пользователей.</span><span class="sxs-lookup"><span data-stu-id="6edde-139">You'll need to identify these groups of users as well.</span></span>

## <a name="plan-for-ad-ds-and-azure-ad-groups"></a><span data-ttu-id="6edde-140">Планирование групп AD DS и Azure AD</span><span class="sxs-lookup"><span data-stu-id="6edde-140">Plan for AD DS and Azure AD groups</span></span>

<span data-ttu-id="6edde-141">Группы в Azure AD можно использовать для нескольких целей, и это упрощает управление облачной средой.</span><span class="sxs-lookup"><span data-stu-id="6edde-141">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="6edde-142">Например, для групп Azure AD вы можете выполнять указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="6edde-142">For example, for Azure AD groups, you can:</span></span>

- <span data-ttu-id="6edde-143">Используя функцию лицензирования на основе групп, автоматически назначать лицензии учетным записям пользователей при их добавлении в Azure AD или синхронизации из AD DS.</span><span class="sxs-lookup"><span data-stu-id="6edde-143">Use group-based licensing to assign licenses for Office 365 and Enterprise Mobility + Security (EMS) to your user accounts automatically as soon as they are added in Azure AD or synchronized from AD DS.</span></span> 
- <span data-ttu-id="6edde-144">Динамически добавлять учетные записи пользователей в определенные группы на основании атрибутов этих учетных записей, например атрибута "Отдел".</span><span class="sxs-lookup"><span data-stu-id="6edde-144">Add user accounts to specific groups dynamically based on user account attributes, such as department.</span></span>  
- <span data-ttu-id="6edde-145">Автоматически подготавливать пользователей для приложений класса "программное обеспечение как услуга" (SaaS) и защищать доступ к этим приложениям с помощью многофакторной проверки подлинности и других правил условного доступа.</span><span class="sxs-lookup"><span data-stu-id="6edde-145">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication and other conditional access rules.</span></span>
- <span data-ttu-id="6edde-146">Подготавливать разрешения и уровни доступа для сайтов групп SharePoint Online.</span><span class="sxs-lookup"><span data-stu-id="6edde-146">Provision permissions and levels of access for SharePoint Online team sites.</span></span> <span data-ttu-id="6edde-147">Группы Azure AD также можно использовать с метками конфиденциальности или Azure Information Protection для защиты файлов при помощи шифрования и разрешений.</span><span class="sxs-lookup"><span data-stu-id="6edde-147">Azure AD groups can also be used with scoped Azure Information Protection policies to protect files with encryption and permissions.</span></span> 

## <a name="results"></a><span data-ttu-id="6edde-148">Результаты</span><span class="sxs-lookup"><span data-stu-id="6edde-148">Results</span></span>

<span data-ttu-id="6edde-149">Когда вы завершите этот этап, у вас будут указанные ниже элементы.</span><span class="sxs-lookup"><span data-stu-id="6edde-149">When you complete this step, you’ll have:</span></span>

- <span data-ttu-id="6edde-150">Список учетных записей пользователей в Azure AD, соответствующих сотрудникам вашей организации, а также поставщикам, подрядчикам и внешним партнерам, которые работают на вашу организацию или с ней.</span><span class="sxs-lookup"><span data-stu-id="6edde-150">A list of user accounts in Azure AD that correspond to the employees in your organization and the vendors, contractors, and external partners that work for or with your organization.</span></span>
- <span data-ttu-id="6edde-151">Набор групп и членства для них в Azure AD, отражающие логические наборы учетных записей пользователей и другие группы для различных целей, например для автоматического лицензирования или подготовки параметров безопасности для облачных служб (Майкрософт).</span><span class="sxs-lookup"><span data-stu-id="6edde-151">A set of groups and their membership in Azure AD that reflect logical sets of user accounts and other groups for automatic licensing provisioning of security settings for Microsoft cloud services.</span></span>

<span data-ttu-id="6edde-152">Прежде чем переходить к следующему этапу, проверьте [условия](identity-exit-criteria.md#crit-identity-user-groups), при выполнении которых можно считать данный этап завершенным.</span><span class="sxs-lookup"><span data-stu-id="6edde-152">As an interim checkpoint, you can see the [exit criteria](identity-exit-criteria.md#crit-identity-user-groups) for this step.</span></span>

<span data-ttu-id="6edde-153">Создав пользователей и группы в Azure AD, вы можете приступить к назначению лицензий и использованию рабочих нагрузок, например OneDrive для бизнеса или Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="6edde-153">Once your Azure AD users and groups are created, you can start assigning licenses and using Exchange Online.</span></span>

## <a name="next-step"></a><span data-ttu-id="6edde-154">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="6edde-154">Next step</span></span>

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [<span data-ttu-id="6edde-155">Защита привилегированных удостоверений</span><span class="sxs-lookup"><span data-stu-id="6edde-155">Secure your privileged identities</span></span>](identity-designate-protect-admin-accounts.md) |

