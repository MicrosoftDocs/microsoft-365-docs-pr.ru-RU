---
title: Политики доступа к удостоверениям и устройствам для обеспечения гостевого и внешнего доступа B2B — Microsoft 365 для предприятий | Документы Майкрософт
description: Описывает рекомендуемый условный доступ и связанные политики защиты доступа гостевых и внешних пользователей.
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
ms.openlocfilehash: c2c01278831433c02e5c869dba83f223eea57d27
ms.sourcegitcommit: 29eb89b8ba0628fbef350e8995d2c38369a4ffa2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/15/2020
ms.locfileid: "49683239"
---
# <a name="policies-for-allowing-guest-and-external-b2b-access"></a><span data-ttu-id="98b6a-103">Политики, разрешающие гостевой и внешний доступ к B2B</span><span class="sxs-lookup"><span data-stu-id="98b6a-103">Policies for allowing guest and external B2B access</span></span>

<span data-ttu-id="98b6a-104">В этой статье описывается, как настроить рекомендуемые общие политики доступа к удостоверениям и устройствам, чтобы разрешить доступ гостевых и внешних пользователей с учетной записью Azure Active Directory (Azure AD) business-to-Business (B2B).</span><span class="sxs-lookup"><span data-stu-id="98b6a-104">This article describes how to adjust the recommended common identity and device access policies to allow access for guest and external users that have an Azure Active Directory (Azure AD) Business-to-Business (B2B) account.</span></span> <span data-ttu-id="98b6a-105">Это руководство построено на [общих политиках доступа к удостоверениям и устройствам.](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="98b6a-105">This guidance builds on the [common identity and device access policies](identity-access-policies.md).</span></span>

<span data-ttu-id="98b6a-106">Эти рекомендации предназначены для применения к **базовому уровню** защиты.</span><span class="sxs-lookup"><span data-stu-id="98b6a-106">These recommendations are designed to apply to the **baseline** tier of protection.</span></span> <span data-ttu-id="98b6a-107">Однако вы также можете скорректировать рекомендации в зависимости от  степени детализации ваших потребностей в конфиденциальной и **строго регулируемой** защите.</span><span class="sxs-lookup"><span data-stu-id="98b6a-107">However, you can also adjust the recommendations based on the granularity of your needs for **sensitive** and **highly regulated** protection.</span></span>

<span data-ttu-id="98b6a-108">Если предоставить учетным записям B2B путь для проверки подлинности в клиенте Azure AD, эти учетные записи не будут иметь доступ ко всей среде.</span><span class="sxs-lookup"><span data-stu-id="98b6a-108">Providing a path for B2B accounts to authenticate with your Azure AD tenant doesn't give these accounts access to your entire environment.</span></span> <span data-ttu-id="98b6a-109">Пользователи B2B и их учетные записи имеют доступ только к ресурсам, к ним (например, к файлам) в службах, предоставленных политиками условного доступа.</span><span class="sxs-lookup"><span data-stu-id="98b6a-109">B2B users and their accounts only have access to resources that are shared with them (such as files) within the services granted in Conditional Access policies.</span></span>

## <a name="updating-the-common-policies-to-allow-and-protect-guest-and-external-access"></a><span data-ttu-id="98b6a-110">Обновление общих политик для поддержки и защиты гостевого и внешнего доступа</span><span class="sxs-lookup"><span data-stu-id="98b6a-110">Updating the common policies to allow and protect guest and external access</span></span>

<span data-ttu-id="98b6a-111">Чтобы защитить гостевой и внешний доступ с помощью учетных записей Azure AD B2B, на следующей схеме показано, какие политики следует добавлять или обновлять из общих политик доступа к удостоверениям и устройствам.</span><span class="sxs-lookup"><span data-stu-id="98b6a-111">To protect guest and external access with Azure AD B2B accounts, the following diagram illustrates which policies to add or update from the the common identity and device access policies.</span></span>

<span data-ttu-id="98b6a-112">[![Сводка обновлений политики для защиты гостевого доступа](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span><span class="sxs-lookup"><span data-stu-id="98b6a-112">[![Summary of policy updates for protecting guest access](../../media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)</span></span>

[<span data-ttu-id="98b6a-113">См. более крупную версию этого изображения</span><span class="sxs-lookup"><span data-stu-id="98b6a-113">See a larger version of this image</span></span>](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/media/microsoft-365-policies-configurations/identity-access-ruleset-guest.png)

<span data-ttu-id="98b6a-114">В следующей таблице перечислены политики, которые необходимо создать и обновить.</span><span class="sxs-lookup"><span data-stu-id="98b6a-114">The following table lists the policies you either need to create and update.</span></span> <span data-ttu-id="98b6a-115">Общие политики ссылались на связанные инструкции по настройке в статье "Общие политики доступа к удостоверениям [и устройствам".](identity-access-policies.md)</span><span class="sxs-lookup"><span data-stu-id="98b6a-115">The common policies link to the associated configuration instructions in the [Common identity and device access policies](identity-access-policies.md) article.</span></span>

|<span data-ttu-id="98b6a-116">Уровень защиты</span><span class="sxs-lookup"><span data-stu-id="98b6a-116">Protection level</span></span>|<span data-ttu-id="98b6a-117">Политики</span><span class="sxs-lookup"><span data-stu-id="98b6a-117">Policies</span></span>|<span data-ttu-id="98b6a-118">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="98b6a-118">More information</span></span>|
|---|---|---|
|<span data-ttu-id="98b6a-119">**Базовый уровень**</span><span class="sxs-lookup"><span data-stu-id="98b6a-119">**Baseline**</span></span>|[<span data-ttu-id="98b6a-120">Требовать многофаксную многофайловую многофайловую раз для гостевых и внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="98b6a-120">Require MFA always for guest and external users</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="98b6a-121">Создайте эту новую политику и настройте:</span><span class="sxs-lookup"><span data-stu-id="98b6a-121">Create this new policy and configure:</span></span> <ul><li> <span data-ttu-id="98b6a-122">For **Assignments > Users and groups > Include,** choose **Select users and groups,** and then select All guest and external **users**.</span><span class="sxs-lookup"><span data-stu-id="98b6a-122">For **Assignments > Users and groups > Include**, choose **Select users and groups**, and then select **All guest and external users**.</span></span> </li><li> <span data-ttu-id="98b6a-123">Для **заданий > условий > входе** оставьте все параметры невызванными, чтобы всегда применять многофакторную проверку подлинности (MFA).</span><span class="sxs-lookup"><span data-stu-id="98b6a-123">For **Assignments > Conditions > Sign-in**, leave all options unchecked to always enforce multi-factor authentication (MFA).</span></span></li>|
||[<span data-ttu-id="98b6a-124">Требовать многофаксную оценку, если риск при входе средний *или* *высокий*</span><span class="sxs-lookup"><span data-stu-id="98b6a-124">Require MFA when sign-in risk is *medium* or *high*</span></span>](identity-access-policies.md#require-mfa-based-on-sign-in-risk)|<span data-ttu-id="98b6a-125">Измените эту политику, чтобы исключить гостевых и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="98b6a-125">Modify this policy to exclude guest and external users.</span></span>|
||[<span data-ttu-id="98b6a-126">Требовать использования соответствующих политике компьютеров</span><span class="sxs-lookup"><span data-stu-id="98b6a-126">Require compliant PCs</span></span>](identity-access-policies.md#require-compliant-pcs-but-not-compliant-phones-and-tablets)|<span data-ttu-id="98b6a-127">Измените эту политику, чтобы исключить гостевых и внешних пользователей.</span><span class="sxs-lookup"><span data-stu-id="98b6a-127">Modify this policy to exclude guest and external users.</span></span>|

<span data-ttu-id="98b6a-128">Чтобы включить или исключить гостевых и внешних пользователей в политиках **условного** доступа, для > Пользователей и групп > Включить или исключить, проверьте всех гостевых и **внешних пользователей.**</span><span class="sxs-lookup"><span data-stu-id="98b6a-128">To include or exclude guest and external users in Conditional Access policies, for **Assignments > Users and groups > Include** or **Exclude**, check **All guest and external users**.</span></span>

![снимок экрана элементов управления для исключения гостевых и внешних пользователей](../../media/microsoft-365-policies-configurations/identity-access-exclude-guests-ui.png)

## <a name="more-information"></a><span data-ttu-id="98b6a-130">Дополнительная информация</span><span class="sxs-lookup"><span data-stu-id="98b6a-130">More information</span></span>

### <a name="guest-and-external-access-with-microsoft-teams"></a><span data-ttu-id="98b6a-131">Гостевой и внешний доступ с помощью Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98b6a-131">Guest and external access with Microsoft Teams</span></span>

<span data-ttu-id="98b6a-132">Microsoft Teams определяет следующее:</span><span class="sxs-lookup"><span data-stu-id="98b6a-132">Microsoft Teams defines the following:</span></span>

- <span data-ttu-id="98b6a-133">**Гостевой доступ** использует учетную запись Azure AD B2B, которую можно добавить в качестве участника команды и получить все разрешения на доступ к коммуникациям и ресурсам команды.</span><span class="sxs-lookup"><span data-stu-id="98b6a-133">**Guest access** uses an Azure AD B2B account that can be added as a member of a team and have all permissioned access to the communications and resources of the team.</span></span>

- <span data-ttu-id="98b6a-134">**Внешний доступ** для внешнего пользователя без учетной записи B2B.</span><span class="sxs-lookup"><span data-stu-id="98b6a-134">**External access** is for an external user that does not have a B2B account.</span></span> <span data-ttu-id="98b6a-135">Внешний доступ может включать приглашения и участие в звонках, чатах и собраниях, но не включает членство в команде и доступ к ресурсам команды.</span><span class="sxs-lookup"><span data-stu-id="98b6a-135">External access can include invitations and participation in calls, chats, and meetings, but does not include team membership and access to the resources of the team.</span></span>

<span data-ttu-id="98b6a-136">Дополнительные сведения см. в сравнении гостевого и [внешнего доступа для команд.](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access)</span><span class="sxs-lookup"><span data-stu-id="98b6a-136">For more information, see the [comparison between guest and external access for teams](https://docs.microsoft.com/microsoftteams/communicate-with-users-from-other-organizations#compare-external-and-guest-access).</span></span>

<span data-ttu-id="98b6a-137">Дополнительные сведения о защите политик доступа к удостоверениям и устройствам для Teams см. в рекомендациях по защите [чатов,](teams-access-policies.md) групп и файлов Teams.</span><span class="sxs-lookup"><span data-stu-id="98b6a-137">See [Policy recommendations for securing Teams chats, groups, and files](teams-access-policies.md) for more information about securing identity and device access policies for Teams.</span></span>

### <a name="require-mfa-always-for-guest-and-external-users"></a><span data-ttu-id="98b6a-138">Требовать многофаксную многофайловую многофайловую раз для гостевых и внешних пользователей</span><span class="sxs-lookup"><span data-stu-id="98b6a-138">Require MFA always for guest and external users</span></span>

<span data-ttu-id="98b6a-139">Эта политика побуждает гостей зарегистрироваться для MFA в клиенте независимо от того, зарегистрированы ли они для MFA в домашнем клиенте.</span><span class="sxs-lookup"><span data-stu-id="98b6a-139">This policy prompts guests to register for MFA in your tenant, regardless of whether they're registered for MFA in their home tenant.</span></span> <span data-ttu-id="98b6a-140">При доступе к ресурсам в клиенте гостевых и внешних пользователей необходимо использовать MFA для каждого запроса.</span><span class="sxs-lookup"><span data-stu-id="98b6a-140">When accessing resources in your tenant, guest and external users are required to use MFA for every request.</span></span>

### <a name="excluding-guest-and-external-users-from-risk-based-mfa"></a><span data-ttu-id="98b6a-141">Исключение гостевых и внешних пользователей из MFA с учетом рисков</span><span class="sxs-lookup"><span data-stu-id="98b6a-141">Excluding guest and external users from risk-based MFA</span></span>

<span data-ttu-id="98b6a-142">Хотя организации могут применять политики на основе рисков для пользователей B2B с помощью защиты идентификации Azure AD, существуют ограничения в реализации защиты идентификации Azure AD для пользователей совместной работы B2B в каталоге ресурсов из-за их удостоверений, существующих в их домашнем каталоге.</span><span class="sxs-lookup"><span data-stu-id="98b6a-142">While organizations can enforce risk-based policies for B2B users using Azure AD Identity Protection, there are limitations in the implementation of Azure AD Identity Protection for B2B collaboration users in a resource directory due to their identity existing in their home directory.</span></span> <span data-ttu-id="98b6a-143">Из-за этих ограничений Корпорация Майкрософт рекомендует исключить гостевых пользователей из политик MFA на основе рисков и требовать от них всегда использовать многофаксную многофаксную многофаксную.</span><span class="sxs-lookup"><span data-stu-id="98b6a-143">Due to these limitations, Microsoft recommends you exclude guest users from risk-based MFA policies and require these users to always use MFA.</span></span>

<span data-ttu-id="98b6a-144">Дополнительные сведения см. в сведениях об ограничениях [защиты идентификации для пользователей совместной работы B2B.](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users)</span><span class="sxs-lookup"><span data-stu-id="98b6a-144">For more information, see [Limitations of Identity Protection for B2B collaboration users](https://docs.microsoft.com/azure/active-directory/identity-protection/concept-identity-protection-b2b#limitations-of-identity-protection-for-b2b-collaboration-users).</span></span>

### <a name="excluding-guest-and-external-users-from-device-management"></a><span data-ttu-id="98b6a-145">Исключение гостевых и внешних пользователей из системы управления устройствами</span><span class="sxs-lookup"><span data-stu-id="98b6a-145">Excluding guest and external users from device management</span></span>

<span data-ttu-id="98b6a-146">Управлять устройством может только одна организация.</span><span class="sxs-lookup"><span data-stu-id="98b6a-146">Only one organization can manage a device.</span></span> <span data-ttu-id="98b6a-147">Если вы не исключите гостевых и внешних пользователей из политик, которые требуют соответствия устройств требованиям, эти политики заблокируют этих пользователей.</span><span class="sxs-lookup"><span data-stu-id="98b6a-147">If you don't exclude guest and external users from policies that require device compliance, these policies will block these users.</span></span>

## <a name="next-step"></a><span data-ttu-id="98b6a-148">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="98b6a-148">Next step</span></span>

![Шаг 4. Политики для облачных приложений Microsoft 365](../../media/microsoft-365-policies-configurations/identity-device-access-steps-next-step-4.png)

<span data-ttu-id="98b6a-150">Настройте политики условного доступа для:</span><span class="sxs-lookup"><span data-stu-id="98b6a-150">Configure Conditional Access policies for:</span></span>

- [<span data-ttu-id="98b6a-151">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="98b6a-151">Microsoft Teams</span></span>](teams-access-policies.md)
- [<span data-ttu-id="98b6a-152">Exchange Online</span><span class="sxs-lookup"><span data-stu-id="98b6a-152">Exchange Online</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="98b6a-153">SharePoint</span><span class="sxs-lookup"><span data-stu-id="98b6a-153">SharePoint</span></span>](sharepoint-file-access-policies.md)
