---
title: Политики доступа к удостоверениям и устройствам, разрешающие гостевому и внешнему пользователю доступ к B2B — Microsoft 365 для предприятий | Документы Майкрософт
description: Описывает рекомендуемый условный доступ и связанные политики для защиты доступа гостей и внешних пользователей.
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: 4ee6cb93e5c943d704950e28ba4dc70a246429a6
ms.sourcegitcommit: 89097fb648987567b9493b9d94c85c5990562874
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/13/2021
ms.locfileid: "49845099"
---
# <a name="policies-for-allowing-guest-access-and-b2b-external-user-access"></a><span data-ttu-id="84eba-103">Политики, разрешающие гостевой доступ и доступ внешних пользователей B2B</span><span class="sxs-lookup"><span data-stu-id="84eba-103">Policies for allowing guest access and B2B external user access</span></span>

<span data-ttu-id="84eba-104">В этой статье обсуждается настройка рекомендуемых политик доступа к устройствам и удостоверениям, чтобы разрешить доступ гостям и внешним пользователям с учетной записью Azure Active Directory (Azure AD) business-to-Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="84eba-104">This article discusses adjusting the recommended device and identity access policies to allow access for guests and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="84eba-105">Это руководство построено на [общих политиках доступа к удостоверениям и устройствам.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="84eba-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="84eba-106">Эти рекомендации предназначены для применения к **базовому** уровню защиты.</span><span class="sxs-lookup"><span data-stu-id="84eba-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="84eba-107">Однако вы также можете скорректировать рекомендации в зависимости от конкретных потребностей в конфиденциальной **и** **строго регулируемой** защите.</span><span class="sxs-lookup"><span data-stu-id="84eba-107">But you can also adjust the recommendations based on your specific needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="84eba-108">Если предоставить учетным записям B2B путь для проверки подлинности в клиенте Azure AD, эти учетные записи не будут иметь доступ ко всей среде.</span><span class="sxs-lookup"><span data-stu-id="84eba-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="84eba-109">Пользователи B2B и их учетные записи имеют доступ к службам и ресурсам, например файлам, доступ к ним делиться политикой условного доступа.</span><span class="sxs-lookup"><span data-stu-id="84eba-109">B2B users and their accounts have access to services and resources, like files, shared with them by Conditional Access policy.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guests-and-external-user-access"></a><span data-ttu-id="84eba-110">Обновление общих политик для поддержки и защиты гостей и доступа внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="84eba-110">Updating the common policies to allow and protect guests and external user access</span></span>

<span data-ttu-id="84eba-111">На этой схеме показано, какие политики необходимо добавить или обновить среди общих политик доступа к удостоверениям и устройствам для гостевого и внешнего доступа пользователей B2B.</span><span class="sxs-lookup"><span data-stu-id="84eba-111">This diagram shows which policies to add or update among the common identity and device access policies, for B2B guest and external user access.</span></span>

<span data-ttu-id="84eba-112">[![Сводка обновлений политики для защиты гостевого доступа](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="84eba-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="84eba-113">См. более крупную версию этого изображения</span><span class="sxs-lookup"><span data-stu-id="84eba-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="84eba-114">В следующей таблице перечислены политики, которые необходимо создать и обновить.</span><span class="sxs-lookup"><span data-stu-id="84eba-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="84eba-115">Общие политики ссылались на связанные инструкции по настройке в статье "Общие политики доступа к удостоверениям [и устройствам".](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="84eba-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="84eba-116">Уровень защиты</span><span class="sxs-lookup"><span data-stu-id="84eba-116">Protection level</span></span>|<span data-ttu-id="84eba-117">Политики</span><span class="sxs-lookup"><span data-stu-id="84eba-117">Policies</span></span>|<span data-ttu-id="84eba-118">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="84eba-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="84eba-119">**Базовый уровень**</span><span class="sxs-lookup"><span data-stu-id="84eba-119">**Baseline**</span></span>|[<span data-ttu-id="84eba-120">Всегда требовать многофаксную многофаксную раз для гостей и внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="84eba-120">Require MFA always for guests and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="84eba-121">Создайте эту новую политику и настройте:</span><span class="sxs-lookup"><span data-stu-id="84eba-121">Create this new policy and configure:</span></span> <ul><li><span data-ttu-id="84eba-122">For **Assignments > Users and groups > Include, choose** **Select users and groups**, and then select All guest and **external users**.</span><span class="sxs-lookup"><span data-stu-id="84eba-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span></li><li><span data-ttu-id="84eba-123">Для **заданий > условий > входе** оставьте все параметры невызванными, чтобы всегда применять многофакторную проверку подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="84eba-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li></ul>|
||[<span data-ttu-id="84eba-124">Требовать многофаксную оценку, если риск при входе средний *или* *высокий*</span><span class="sxs-lookup"><span data-stu-id="84eba-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="84eba-125">Измените эту политику, чтобы исключить гостей и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="84eba-125">Modify this policy to exclude guests and external users.</span></span>|
||[<span data-ttu-id="84eba-126">Требовать использования соответствующих политике компьютеров</span><span class="sxs-lookup"><span data-stu-id="84eba-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="84eba-127">Измените эту политику, чтобы исключить гостей и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="84eba-127">Modify this policy to exclude guests and external users.</span></span>|

<span data-ttu-id="84eba-128">Чтобы включить или исключить гостей и внешних пользователей в политиках условного доступа, для > пользователей и групп **> Включить** или исключить **всех** гостевых и **внешних пользователей.**</span><span class="sxs-lookup"><span data-stu-id="84eba-128">To include or exclude guests and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![снимок экрана элементов управления для исключения гостей и внешних пользователей](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="84eba-130">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="84eba-130">More information</span></span>

### <a name="guests-and-external-user-access-with-microsoft-teams"></a><span data-ttu-id="84eba-131">Гостевой доступ и доступ внешних пользователей с помощью Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84eba-131">Guests and external user access with Microsoft Teams</span></span>

<span data-ttu-id="84eba-132">Microsoft Teams определяет следующих пользователей:</span><span class="sxs-lookup"><span data-stu-id="84eba-132">Microsoft Teams defines the following users:</span></span>

- <span data-ttu-id="84eba-133">**Гостевой** доступ использует учетную запись Azure AD B2B, которую можно добавить в качестве участника команды и получить доступ к коммуникациям и ресурсам команды.</span><span class="sxs-lookup"><span data-stu-id="84eba-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have access to the communications and resources of the team.</span></span>

- <span data-ttu-id="84eba-134">**Внешний доступ** для внешнего пользователя без учетной записи B2B.</span><span class="sxs-lookup"><span data-stu-id="84eba-134">**External access** is for an external user that doesn't have a B2B account.</span></span> <span data-ttu-id="84eba-135">Доступ внешних пользователей включает приглашения, звонки, чаты и собрания, но не включает членство в команде и доступ к ресурсам команды.</span><span class="sxs-lookup"><span data-stu-id="84eba-135">External user access includes invitations, calls, chats, and meetings, but doesn't include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="84eba-136">Дополнительные сведения см. в [сравнении гостевых и внешних пользователей с доступом к командам.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="84eba-136">For more information, see the [comparison between guests and external user access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="84eba-137">Дополнительные сведения о защите политик доступа к удостоверениям и устройствам для Teams см. в рекомендациях политики для защиты чатов, групп [и файлов Teams.](teams-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="84eba-137">For more information on securing identity and device access policies for Teams, see [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md).</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="84eba-138">Требовать многофаксную многофайловую многофайловую раз для гостевых и внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="84eba-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="84eba-139">Эта политика побуждает гостей зарегистрироваться для MFA в клиенте независимо от того, зарегистрированы ли они для MFA в домашнем клиенте.</span><span class="sxs-lookup"><span data-stu-id="84eba-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="84eba-140">При доступе к ресурсам в клиенте гости и внешние пользователи должны использовать MFA для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="84eba-140">When accessing resources in your tenant, guests and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guests-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="84eba-141">Исключение гостей и внешних пользователей из MFA с учетом рисков</span><span class="sxs-lookup"><span data-stu-id="84eba-141">Excluding guests and external users from risk-based MFA</span></span>

<span data-ttu-id="84eba-142">Хотя организации могут применять политики на основе рисков для пользователей B2B с помощью защиты идентификации Azure AD, существуют ограничения в реализации защиты идентификации Azure AD для пользователей совместной работы B2B в каталоге ресурсов из-за их удостоверений, существующих в их домашнем каталоге.</span><span class="sxs-lookup"><span data-stu-id="84eba-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="84eba-143">Из-за этих ограничений Корпорация Майкрософт рекомендует исключить гостей из политик MFA на основе рисков и требовать от этих пользователей всегда использовать многофаксную.</span><span class="sxs-lookup"><span data-stu-id="84eba-143">Due to these limitations, Microsoft recommends you exclude guests from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="84eba-144">Дополнительные сведения см. в сведениях об ограничениях [защиты идентификации для пользователей совместной работы B2B.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="84eba-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guests-and-external-users-from-device-management"></a><span data-ttu-id="84eba-145">Исключение гостей и внешних пользователей из системы управления устройствами</span><span class="sxs-lookup"><span data-stu-id="84eba-145">Excluding guests and external users from device management</span></span>

<span data-ttu-id="84eba-146">Управлять устройством может только одна организация.</span><span class="sxs-lookup"><span data-stu-id="84eba-146">Only one organization can manage a device.</span></span> <span data-ttu-id="84eba-147">Если вы не исключите гостей и внешних пользователей из политик, которые требуют соответствия устройств требованиям, эти политики заблокируют этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="84eba-147">If you don't exclude guests and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="84eba-148">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="84eba-148">Next step</span></span>

![Шаг 4. Политики для облачных приложений Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="84eba-150">Настройте политики условного доступа для:</span><span class="sxs-lookup"><span data-stu-id="84eba-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="84eba-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="84eba-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="84eba-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="84eba-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="84eba-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="84eba-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
