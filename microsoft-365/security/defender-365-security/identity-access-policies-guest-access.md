---
title: Политики доступа к удостоверениям и устройствам для допуска гостей и внешних пользователей B2B - Microsoft 365 для корпоративных | Документы Майкрософт
description: Описывает рекомендуемые политики условного доступа и связанные политики защиты доступа гостей и внешних пользователей.
ms.prod: m365-security
ms.topic: article
ms.author: josephd
author: JoeDavies-MSFT
manager: Laurawi
f1.keywords:
- NOCSH
ms.reviewer: martincoetzer
ms.custom:
- it-pro
- goldenconfig
ms.collection:
- M365-identity-device-management
- M365-security-compliance
- m365solution-identitydevice
- m365solution-scenario
ms.technology: mdo
ms.openlocfilehash: 9d3a47752efc86c8ced32905bda851b7d8157f82
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51071389"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="e2aad-103">Политики для допуска гостевого доступа и внешнего доступа к пользователю B2B</span><span class="sxs-lookup"><span data-stu-id="e2aad-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="e2aad-104">В этой статье обсуждается корректировка рекомендуемых политик доступа к устройствам и удостоверениям, чтобы разрешить доступ для гостей и внешних пользователей с учетной записью Azure Active Directory (Azure AD) Business-to-Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="e2aad-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="e2aad-105">Это руководство строится на [общих политиках доступа к удостоверениям и устройствам.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e2aad-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="e2aad-106">Эти рекомендации предназначены для применения к **базовому** уровню защиты.</span><span class="sxs-lookup"><span data-stu-id="e2aad-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="e2aad-107">Но вы также можете настроить рекомендации в  зависимости от конкретных потребностей в конфиденциальной и **строго регламентируемой** защите.</span><span class="sxs-lookup"><span data-stu-id="e2aad-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="e2aad-108">Предоставление доступа для учетных записей B2B для проверки подлинности с клиентом Azure AD не предоставляет этим учетным записям доступ ко всей среде.</span><span class="sxs-lookup"><span data-stu-id="e2aad-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="e2aad-109">Пользователи B2B и их учетные записи имеют доступ к службам и ресурсам, например к файлам, общим для них политикой условного доступа.</span><span class="sxs-lookup"><span data-stu-id="e2aad-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="e2aad-110">Обновление общих политик, позволяющих и защищая гостей и внешний доступ пользователей</span><span class="sxs-lookup"><span data-stu-id="e2aad-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="e2aad-111">На этой схеме показано, какие политики для добавления или обновления среди общих политик доступа к удостоверениям и устройствам для гостевого и внешнего доступа пользователей B2B.</span><span class="sxs-lookup"><span data-stu-id="e2aad-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="e2aad-112">[![Сводка обновлений политики для защиты гостевого доступа](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="e2aad-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

<span data-ttu-id="e2aad-113">В следующей таблице перечислены политики, которые необходимо создать и обновить.</span><span class="sxs-lookup"><span data-stu-id="e2aad-113">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="e2aad-114">Общие политики ссылались на связанные инструкции по конфигурации в статье Общие политики доступа к удостоверениям [и устройствам.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e2aad-114">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="e2aad-115">Уровень защиты</span><span class="sxs-lookup"><span data-stu-id="e2aad-115">Protection level</span></span>|<span data-ttu-id="e2aad-116">Политики</span><span class="sxs-lookup"><span data-stu-id="e2aad-116">Policies</span></span>|<span data-ttu-id="e2aad-117">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e2aad-117">More information</span></span>|
|---|---|---|
|<span data-ttu-id="e2aad-118">**Базовый уровень**</span><span class="sxs-lookup"><span data-stu-id="e2aad-118">**Baseline**</span></span>|[<span data-ttu-id="e2aad-119">Обязательное MFA всегда для гостей и внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="e2aad-119">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="e2aad-120">Создайте эту новую политику и настройте:</span><span class="sxs-lookup"><span data-stu-id="e2aad-120">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="e2aad-121">Для **назначений > пользователи** и группы >, выберите Выберите пользователей и группы, а затем выберите всех гостевых и **внешних пользователей.** </span><span class="sxs-lookup"><span data-stu-id="e2aad-121">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="e2aad-122">Для **назначений > условия >** вход, оставьте все параметры без проверки, чтобы всегда применять многофакторную проверку подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="e2aad-122">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="e2aad-123">Требовать MFA, когда риск входов средний *или* *высокий*</span><span class="sxs-lookup"><span data-stu-id="e2aad-123">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="e2aad-124">Измените эту политику, чтобы исключить гостей и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2aad-124">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="e2aad-125">Требовать использования соответствующих политике компьютеров</span><span class="sxs-lookup"><span data-stu-id="e2aad-125">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="e2aad-126">Измените эту политику, чтобы исключить гостей и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2aad-126">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="e2aad-127">Чтобы включить или исключить гостей и внешних пользователей в политики условного доступа, для назначений > пользователи и группы > **Включить** или исключить, проверьте всех гостевых и **внешних пользователей**.</span><span class="sxs-lookup"><span data-stu-id="e2aad-127">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![захват экрана элементов управления для исключения гостей и внешних пользователей](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="e2aad-129">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="e2aad-129">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="e2aad-130">Доступ гостей и внешних пользователей в Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2aad-130">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="e2aad-131">Microsoft Teams определяет следующих пользователей:</span><span class="sxs-lookup"><span data-stu-id="e2aad-131">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="e2aad-132">**В гостевом** доступе используется учетная запись Azure AD B2B, которая может быть добавлена в качестве члена группы и иметь доступ к коммуникациям и ресурсам группы.</span><span class="sxs-lookup"><span data-stu-id="e2aad-132">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="e2aad-133">**Внешний доступ** для внешнего пользователя, у него нет учетной записи B2B.</span><span class="sxs-lookup"><span data-stu-id="e2aad-133">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="e2aad-134">Внешний доступ к пользователю включает приглашения, вызовы, чаты и собрания, но не включает членство в команде и доступ к ресурсам группы.</span><span class="sxs-lookup"><span data-stu-id="e2aad-134">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="e2aad-135">Дополнительные сведения см. в сопоставлении между гостями и внешним доступом пользователей [для команд.](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="e2aad-135">For more information, see the [comparison between guests and external user access for teams](/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="e2aad-136">Дополнительные сведения о защите политик доступа к удостоверениям и устройствам для Teams см. в рекомендациях политики по обеспечению безопасности чатов, групп и [файлов Teams.](teams-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="e2aad-136">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="e2aad-137">Обязательное MFA всегда для гостевых и внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="e2aad-137">Require MFA always for guest and external users</span></span>

<span data-ttu-id="e2aad-138">Эта политика побуждает гостей регистрироваться для MFA в вашем клиенте, независимо от того, зарегистрированы ли они для MFA в домашнем клиенте.</span><span class="sxs-lookup"><span data-stu-id="e2aad-138">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="e2aad-139">При доступе к ресурсам в клиенте гости и внешние пользователи должны использовать MFA для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="e2aad-139">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="e2aad-140">Исключение гостей и внешних пользователей из MFA на основе риска</span><span class="sxs-lookup"><span data-stu-id="e2aad-140">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="e2aad-141">Хотя организации могут применять политики на основе рисков для пользователей B2B с помощью Azure AD Identity Protection, в реализации Azure AD Identity Protection для пользователей совместной работы B2B в каталоге ресурсов существуют ограничения из-за их удостоверений, существующих в их домашнем каталоге.</span><span class="sxs-lookup"><span data-stu-id="e2aad-141">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="e2aad-142">В связи с этими ограничениями Корпорация Майкрософт рекомендует исключить гостей из политик MFA, основанных на рисках, и обязать этих пользователей всегда использовать MFA.</span><span class="sxs-lookup"><span data-stu-id="e2aad-142">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="e2aad-143">Дополнительные сведения см. в дополнительных сведениях об ограничениях [защиты удостоверений для пользователей совместной работы B2B.](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="e2aad-143">For more information, see [Limitations of Identity Protection for B2B collaboration users](/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="e2aad-144">Исключение гостей и внешних пользователей из системы управления устройствами</span><span class="sxs-lookup"><span data-stu-id="e2aad-144">Excluding guests and external users from device management</span></span>

<span data-ttu-id="e2aad-145">Управлять устройством может только одна организация.</span><span class="sxs-lookup"><span data-stu-id="e2aad-145">Only one organization can manage a device.</span></span> <span data-ttu-id="e2aad-146">Если не исключать гостей и внешних пользователей из политик, которые требуют соответствия требованиям устройств, эти политики будут блокировать этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="e2aad-146">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="e2aad-147">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="e2aad-147">Next step</span></span>

![Шаг 4. Политики для облачных приложений Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="e2aad-149">Настройка политик условного доступа для:</span><span class="sxs-lookup"><span data-stu-id="e2aad-149">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="e2aad-150">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="e2aad-150">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="e2aad-151">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="e2aad-151">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="e2aad-152">SharePoint</span><span class="sxs-lookup"><span data-stu-id="e2aad-152">SharePoint</span></span>](sharepoint-file-access-policies.md)