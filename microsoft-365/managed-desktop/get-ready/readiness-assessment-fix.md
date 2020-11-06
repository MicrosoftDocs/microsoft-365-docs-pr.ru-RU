---
title: Устранение проблем, обнаруженных средством оценки готовности
description: Подробные действия, которые необходимо выполнить для каждой из выпусков, которые обнаруживает средство
keywords: Компьютеры, управляемые Майкрософт, Microsoft 365, служба, документация
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: c28353698dd372e14d5ec51b92eb4c0c051c92a4
ms.sourcegitcommit: 24826e1b61e7aace12fc9e8ae84ae3e760658b50
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/06/2020
ms.locfileid: "48931916"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="a0c9d-104">Устранение проблем, обнаруженных средством оценки готовности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="a0c9d-105">Для каждой проверки средство сообщит один из четырех возможных результатов:</span><span class="sxs-lookup"><span data-stu-id="a0c9d-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="a0c9d-106">Результат</span><span class="sxs-lookup"><span data-stu-id="a0c9d-106">Result</span></span>  |<span data-ttu-id="a0c9d-107">Смысл</span><span class="sxs-lookup"><span data-stu-id="a0c9d-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="a0c9d-108">Ready</span><span class="sxs-lookup"><span data-stu-id="a0c9d-108">Ready</span></span>     | <span data-ttu-id="a0c9d-109">Перед регистрацией не требуются никакие действия.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="a0c9d-110">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="a0c9d-110">Advisory</span></span>    | <span data-ttu-id="a0c9d-111">Выполните действия, описанные в этом инструменте, или в этой статье, чтобы получить лучшие сведения о возможностях регистрации и для пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="a0c9d-112">Вы *можете* выполнить регистрацию, но вам необходимо устранить эти проблемы перед развертыванием первого устройства.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="a0c9d-113">Не готов</span><span class="sxs-lookup"><span data-stu-id="a0c9d-113">Not ready</span></span> | <span data-ttu-id="a0c9d-114">*Если вы не устраните эти проблемы, регистрация завершится с ошибками.*</span><span class="sxs-lookup"><span data-stu-id="a0c9d-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="a0c9d-115">Выполните действия, описанные в этом инструменте, или в этой статье, чтобы устранить их.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="a0c9d-116">Error</span><span class="sxs-lookup"><span data-stu-id="a0c9d-116">Error</span></span> | <span data-ttu-id="a0c9d-117">Используемая роль Azure Active Directory (AD) не обладает разрешениями, достаточными для запуска этой проверки.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="a0c9d-118">Параметры Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="a0c9d-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="a0c9d-119">Профиль развертывания для автопилота</span><span class="sxs-lookup"><span data-stu-id="a0c9d-119">Autopilot deployment profile</span></span>

<span data-ttu-id="a0c9d-120">Вы не должны иметь существующие профили автопилота, которые нацелены на назначенные или динамические группы, используемые Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="a0c9d-121">На рабочем столе Майкрософт используется Автопилот для подготовки новых устройств.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="a0c9d-122">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-122">**Not ready**</span></span>

<span data-ttu-id="a0c9d-123">У вас есть профиль автопилота, назначаемый всем устройствам.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="a0c9d-124">Для получения инструкций обратитесь к разделу [Регистрация устройств Windows в Intune с помощью Windows автопилота](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="a0c9d-125">После регистрации на рабочем столе, управляемой Майкрософт, настройте политику автопилота, чтобы исключить **все современные устройства — все** группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="a0c9d-126">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-126">**Advisory**</span></span>

<span data-ttu-id="a0c9d-127">Убедитесь, что профили автопилота нацелены на назначенную или динамическую группу Azure AD, которая не включает устройства, управляемые Майкрософт для настольных компьютеров, которые будут созданы при регистрации.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="a0c9d-128">Для получения инструкций обратитесь к разделу [Регистрация устройств Windows в Intune с помощью Windows автопилота](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="a0c9d-129">После регистрации на рабочем столе, управляемой Майкрософт, настройте политику автопилота, чтобы исключить **все современные устройства — все** группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="a0c9d-130">Соединители сертификатов</span><span class="sxs-lookup"><span data-stu-id="a0c9d-130">Certificate connectors</span></span>

<span data-ttu-id="a0c9d-131">При наличии соединителей сертификатов, используемых устройствами, которые вы хотите зарегистрировать на компьютере, управляемом Майкрософт, соединители не могут содержать ошибок.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="a0c9d-132">В вашу ситуацию будет применен только один из следующих рекомендаций, поэтому следует тщательно проверять их.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="a0c9d-133">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-133">**Advisory**</span></span>

<span data-ttu-id="a0c9d-134">Нет соединителей сертификатов.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-134">No certificate connectors are present.</span></span> <span data-ttu-id="a0c9d-135">Возможно, вам не потребуются соединители, но необходимо оценить, требуются ли для сетевого подключения к управляемым устройствам Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-136">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="a0c9d-137">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-137">**Advisory**</span></span>

<span data-ttu-id="a0c9d-138">По крайней мере один соединитель сертификатов содержит ошибку.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="a0c9d-139">Если этот соединитель необходим для подключения к настольным устройствам, управляемым корпорацией Майкрософт, необходимо устранить эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="a0c9d-140">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="a0c9d-141">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-141">**Advisory**</span></span>

<span data-ttu-id="a0c9d-142">У вас есть по крайней мере один соединитель сертификатов, и при этом не сообщается об ошибках.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="a0c9d-143">Тем не менее, может потребоваться создать профиль для повторного использования соединителя для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-144">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="a0c9d-145">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="a0c9d-145">Conditional access policies</span></span>

<span data-ttu-id="a0c9d-146">Политики условного доступа в Организации Azure AD не должны быть нацелены на управление пользователями настольных систем Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="a0c9d-147">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-147">**Not ready**</span></span>

<span data-ttu-id="a0c9d-148">У вас есть по крайней мере одна политика условного доступа, предназначенная для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="a0c9d-149">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает группу Azure AD управляемых учетных записей служб рабочего стола Майкрософт, которые будут создаваться при регистрации.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="a0c9d-150">Для получения инструкций обратитесь [к разделу условный доступ: пользователи и группы](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="a0c9d-151">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-151">**Advisory**</span></span>

<span data-ttu-id="a0c9d-152">Убедитесь, что все политики условного доступа исключены из группы Azure AD " **учетные записи служб современного рабочего места** ".</span><span class="sxs-lookup"><span data-stu-id="a0c9d-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="a0c9d-153">Инструкции по [настройке условного доступа](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="a0c9d-154">Группа Azure AD " **учетные записи служб современного рабочего места** " — это динамическая группа, которая создается для службы при регистрации.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="a0c9d-155">После регистрации вам потребуется вернуться к исключению этой группы.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="a0c9d-156">Для получения дополнительных сведений об этих учетных записях служб ознакомьтесь со статьями [стандартные рабочие процедуры](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="a0c9d-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-157">**Error**</span></span>

<span data-ttu-id="a0c9d-158">Роль администратора Intune не имеет достаточных разрешений для этой проверки.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="a0c9d-159">Кроме того, для выполнения этой проверки потребуются все назначенные роли Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="a0c9d-160">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-160">Security Reader</span></span>
- <span data-ttu-id="a0c9d-161">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-161">Security Administrator</span></span>
- <span data-ttu-id="a0c9d-162">Администратор условного доступа</span><span class="sxs-lookup"><span data-stu-id="a0c9d-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="a0c9d-163">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="a0c9d-163">Global Reader</span></span>
- <span data-ttu-id="a0c9d-164">Администратор устройств</span><span class="sxs-lookup"><span data-stu-id="a0c9d-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="a0c9d-165">Политики соответствия требованиям устройств</span><span class="sxs-lookup"><span data-stu-id="a0c9d-165">Device Compliance policies</span></span>

<span data-ttu-id="a0c9d-166">Политики соответствия требованиям устройств Intune в Организации Azure AD не должны быть нацелены на пользователей, управляемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="a0c9d-167">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-167">**Not ready**</span></span>

<span data-ttu-id="a0c9d-168">У вас есть по крайней мере одна политика соответствия требованиям, которая нацелена на всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="a0c9d-169">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает пользователей, настольных под управлением Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="a0c9d-170">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="a0c9d-171">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-171">**Advisory**</span></span>

<span data-ttu-id="a0c9d-172">Убедитесь, что все политики соответствия требованиям не включают пользователей, настольных под управлением Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="a0c9d-173">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="a0c9d-174">Политики конфигурации устройств</span><span class="sxs-lookup"><span data-stu-id="a0c9d-174">Device Configuration policies</span></span>

<span data-ttu-id="a0c9d-175">Политики конфигурации устройств Intune в Организации Azure AD не должны быть предназначены для управления устройствами и пользователями настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="a0c9d-176">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-176">**Not ready**</span></span>

<span data-ttu-id="a0c9d-177">У вас есть по крайней мере одна политика конфигурации, которая нацелена на всех пользователей, все устройства или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="a0c9d-178">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает в себя компьютеры, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-179">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="a0c9d-180">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-180">**Advisory**</span></span>

<span data-ttu-id="a0c9d-181">Убедитесь, что все политики соответствия требованиям не входят в состав компьютеров, управляемых пользователями.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="a0c9d-182">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="a0c9d-183">Ограничения на типы устройств</span><span class="sxs-lookup"><span data-stu-id="a0c9d-183">Device type restrictions</span></span>

<span data-ttu-id="a0c9d-184">На настольных устройствах, управляемых Майкрософт, должно быть разрешено регистрироваться в Intune.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="a0c9d-185">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-185">**Not ready**</span></span>

<span data-ttu-id="a0c9d-186">Выполните действия, описанные в статье Set **Reallows** [Set](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) , чтобы изменить значение параметра на Allow.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="a0c9d-187">Страница состояния регистрации</span><span class="sxs-lookup"><span data-stu-id="a0c9d-187">Enrollment Status Page</span></span>

<span data-ttu-id="a0c9d-188">В настоящее время включена страница состояния регистрации (ESP).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="a0c9d-189">Если вы участвуете в общедоступной предварительной версии этой функции, вы можете пропустить этот элемент.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="a0c9d-190">Для получения дополнительных сведений обратитесь к разделу [First-Run with автопилот и странице Состояние регистрации](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="a0c9d-191">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-191">**Not ready**</span></span>

<span data-ttu-id="a0c9d-192">Установленный по умолчанию профиль ESP позволяет **Показать ход выполнения настройки приложений и профилей**.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-192">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="a0c9d-193">Отключите этот параметр или убедитесь, что назначения для любой группы Azure AD не включают в себя системные устройства, управляемые корпорацией Майкрософт, выполнив действия, описанные в разделе [Настройка страницы состояния регистрации](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-193">Disable this setting or make sure that assignments to any Azure AD group do not include Microsoft Managed Desktop devices by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="a0c9d-194">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-194">**Advisory**</span></span>

<span data-ttu-id="a0c9d-195">Убедитесь, что все профили с параметром " **Показать ход выполнения настройки приложения и профиля** " не назначены какой бы то ни было группе Azure AD, включающей в себя системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-196">Дополнительные сведения можно найти [в разделе Настройка страницы состояния регистрации](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="a0c9d-197">Регистрация в Intune</span><span class="sxs-lookup"><span data-stu-id="a0c9d-197">Intune enrollment</span></span>

<span data-ttu-id="a0c9d-198">Устройства с Windows 10 в Организации Azure AD должны автоматически регистрироваться в Intune.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="a0c9d-199">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-199">**Advisory**</span></span>

<span data-ttu-id="a0c9d-200">Убедитесь, что для области пользователя MDM задано значение **Some** или **ALL** , а не **None**.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-200">Make sure the MDM User scope is set to **Some** or **All** , not **None**.</span></span> <span data-ttu-id="a0c9d-201">Если вы выберете **некоторые** из них, вернитесь обратно после регистрации и выберите в разделе " **современная Рабочая** область" все группы Azure AD для **групп**.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-201">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="a0c9d-202">Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a0c9d-202">Microsoft Store for Business</span></span>

<span data-ttu-id="a0c9d-203">Мы используем Microsoft Store для бизнеса, чтобы вы могли скачать корпоративный портал, чтобы развернуть некоторые приложения, такие как Microsoft Project и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-203">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="a0c9d-204">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-204">**Not ready**</span></span>

<span data-ttu-id="a0c9d-205">Microsoft Store для бизнеса либо не включен, либо не синхронизирован с Intune.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-205">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="a0c9d-206">Для получения дополнительных сведений Узнайте, [как управлять корпоративными приобретенными приложениями из Microsoft Store для бизнеса с помощью Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) и [установить портал компании Intune на устройствах](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-206">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="a0c9d-207">Многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-207">Multi-factor authentication</span></span>

<span data-ttu-id="a0c9d-208">Многофакторная проверка подлинности не должна быть случайно применена к управляемым учетным записям служб рабочих столов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-208">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="a0c9d-209">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-209">**Not ready**</span></span>

<span data-ttu-id="a0c9d-210">Некоторые политики многофакторной проверки подлинности (MFA) устанавливаются как обязательные для политик условного доступа, назначенных всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-210">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="a0c9d-211">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-211">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-212">Дополнительные сведения см. в статье [политики условного доступа](#conditional-access-policies) и [Условный доступ: требовать MFA для всех пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-212">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="a0c9d-213">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-213">**Advisory**</span></span>

<span data-ttu-id="a0c9d-214">Убедитесь, что все политики условного доступа, требующие MFA, не включают в себя всю группу Azure AD в **современном рабочем месте** .</span><span class="sxs-lookup"><span data-stu-id="a0c9d-214">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="a0c9d-215">Дополнительные сведения см. в статье [политики условного доступа](#conditional-access-policies) и [Условный доступ: требовать MFA для всех пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-215">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="a0c9d-216">**Современная Рабочая область — все** группы Azure AD — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-216">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="a0c9d-217">**Error**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-217">**Error**</span></span>

<span data-ttu-id="a0c9d-218">Роль администратора Intune не имеет достаточных разрешений для этой проверки.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-218">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="a0c9d-219">Кроме того, для выполнения этой проверки потребуются все назначенные роли Azure AD.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-219">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="a0c9d-220">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-220">Security Reader</span></span>
- <span data-ttu-id="a0c9d-221">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-221">Security Administrator</span></span>
- <span data-ttu-id="a0c9d-222">Администратор условного доступа</span><span class="sxs-lookup"><span data-stu-id="a0c9d-222">Conditional Access Administrator</span></span>
- <span data-ttu-id="a0c9d-223">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="a0c9d-223">Global Reader</span></span>
- <span data-ttu-id="a0c9d-224">Администратор устройств</span><span class="sxs-lookup"><span data-stu-id="a0c9d-224">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="a0c9d-225">Сценарии PowerShell</span><span class="sxs-lookup"><span data-stu-id="a0c9d-225">PowerShell scripts</span></span>

<span data-ttu-id="a0c9d-226">Сценарии Windows PowerShell не могут назначаться таким образом, чтобы направлять устройства, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-226">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="a0c9d-227">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-227">**Advisory**</span></span>

<span data-ttu-id="a0c9d-228">Убедитесь, что сценарии Windows PowerShell в Организации Azure AD не предназначены для управления устройствами и пользователями настольных компьютеров корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-228">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="a0c9d-229">Не назначайте скрипт PowerShell для всех пользователей, всех устройств или и того, и другое.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-229">Do not assign a PowerShell script to target all users, all devices, or both.</span></span> <span data-ttu-id="a0c9d-230">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-230">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-231">Дополнительные сведения см. в статье [использование скриптов PowerShell для устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-231">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="a0c9d-232">Регион</span><span class="sxs-lookup"><span data-stu-id="a0c9d-232">Region</span></span>

<span data-ttu-id="a0c9d-233">Ваш регион должен поддерживаться на настольном компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-233">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="a0c9d-234">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-234">**Not ready**</span></span>

<span data-ttu-id="a0c9d-235">В настоящее время область организации Azure AD не поддерживается на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-235">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="a0c9d-236">Для получения дополнительных [сведений см.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="a0c9d-236">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="a0c9d-237">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-237">**Advisory**</span></span>

<span data-ttu-id="a0c9d-238">Одна или несколько стран, в которых находится ваша организация Azure AD, не поддерживаются на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-238">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="a0c9d-239">Для получения дополнительных [сведений см.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="a0c9d-239">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="a0c9d-240">Базовые показатели безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-240">Security baselines</span></span>

<span data-ttu-id="a0c9d-241">Базовые политики безопасности не должны ориентироваться на компьютеры, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-241">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="a0c9d-242">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-242">**Not ready**</span></span>

<span data-ttu-id="a0c9d-243">У вас есть базовый профиль безопасности, который предназначен для всех пользователей, всех устройств или и того, и другое.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-243">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="a0c9d-244">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-244">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-245">В разделе [Использование базовых показателей безопасности для настройки устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-245">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="a0c9d-246">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-246">**Advisory**</span></span>

<span data-ttu-id="a0c9d-247">Убедитесь, что все базовые политики безопасности исключают системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-247">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-248">В разделе [Использование базовых показателей безопасности для настройки устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-248">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="a0c9d-249">" **Современные рабочие устройства — все** группы Azure AD" — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-249">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="a0c9d-250">Приложения для Windows</span><span class="sxs-lookup"><span data-stu-id="a0c9d-250">Windows apps</span></span>

<span data-ttu-id="a0c9d-251">Просмотрите приложения, которые должны иметь пользователи, управляемые Майкрософт для настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-251">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="a0c9d-252">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-252">**Advisory**</span></span>

<span data-ttu-id="a0c9d-253">Необходимо подготовить список приложений, которые должны иметь пользователи, управляемые Майкрософт для настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-253">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="a0c9d-254">Убедитесь, что эти приложения можно развернуть с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-254">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="a0c9d-255">Дополнительные сведения содержатся [в статье приложения на компьютере, управляемом Майкрософт](apps.md).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-255">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="a0c9d-256">Вы можете попросить своего представителя учетной записи Майкрософт выполнить запрос в диспетчере конфигурации конечных точек Майкрософт, чтобы определить, какие приложения готовы для переноса в Intune или нуждаются в корректировке.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-256">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="a0c9d-257">Windows Hello для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a0c9d-257">Windows Hello for Business</span></span>

<span data-ttu-id="a0c9d-258">Для рабочего стола, управляемого Майкрософт, требуется включить функцию Windows Hello для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-258">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="a0c9d-259">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-259">**Not ready**</span></span>

<span data-ttu-id="a0c9d-260">Windows Hello для бизнеса отключена.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-260">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="a0c9d-261">Включите его, выполнив действия, описанные в разделе [Создание политики Windows Hello для бизнеса](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="a0c9d-261">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="a0c9d-262">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-262">**Advisory**</span></span>

<span data-ttu-id="a0c9d-263">Windows Hello для бизнеса не настроена.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-263">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="a0c9d-264">Включите его, выполнив действия, описанные в разделе [Создание политики Windows Hello для бизнеса](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-264">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="a0c9d-265">Звонки обновления Windows 10</span><span class="sxs-lookup"><span data-stu-id="a0c9d-265">Windows 10 update rings</span></span>

<span data-ttu-id="a0c9d-266">Политика "Windows 10 Update Ring Ring" в Intune не должна быть нацелена на настольные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-266">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="a0c9d-267">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-267">**Not ready**</span></span>

<span data-ttu-id="a0c9d-268">У вас есть политика "обновление звонка", предназначенная для всех устройств, всех пользователей или и тех, и других.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-268">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="a0c9d-269">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-269">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="a0c9d-270">Дополнительные сведения: [Управление обновлениями программного обеспечения Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-270">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="a0c9d-271">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-271">**Advisory**</span></span>

<span data-ttu-id="a0c9d-272">Убедитесь, что все политики обновления звонков не исключают всю группу Azure AD в **современном рабочем месте** .</span><span class="sxs-lookup"><span data-stu-id="a0c9d-272">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="a0c9d-273">Дополнительные сведения: [Управление обновлениями программного обеспечения Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-273">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="a0c9d-274">" **Современные рабочие устройства — все** группы Azure AD" — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-274">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="a0c9d-275">Параметры Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="a0c9d-275">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="a0c9d-276">Подписки на ad hoc</span><span class="sxs-lookup"><span data-stu-id="a0c9d-276">Ad hoc subscriptions</span></span>

<span data-ttu-id="a0c9d-277">Показывает, как проверить, что параметр, для которого задано значение "false"), может препятствовать правильной работе перемещения корпоративных состояний.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-277">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="a0c9d-278">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-278">**Advisory**</span></span>

<span data-ttu-id="a0c9d-279">Убедитесь, что для параметра **алловадхоксубскриптионс** задано **значение true**.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-279">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="a0c9d-280">В противном случае роуминг состояния предприятия может не работать.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-280">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="a0c9d-281">Дополнительные сведения см. в статье [Set – мсолкомпанисеттингс](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-281">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="a0c9d-282">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="a0c9d-282">Enterprise State Roaming</span></span>

<span data-ttu-id="a0c9d-283">Роуминг состояния предприятия должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-283">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="a0c9d-284">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-284">**Advisory**</span></span>

<span data-ttu-id="a0c9d-285">Убедитесь, что роуминг состояния предприятия включен для **всех** или для **выбранных** групп.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-285">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="a0c9d-286">Дополнительные сведения см в статье [Enable Enterprise State роуминг в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-286">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="a0c9d-287">Лицензии</span><span class="sxs-lookup"><span data-stu-id="a0c9d-287">Licenses</span></span>

<span data-ttu-id="a0c9d-288">Для использования настольного компьютера, управляемого Майкрософт, требуется несколько лицензий.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-288">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="a0c9d-289">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-289">**Not Ready**</span></span>

<span data-ttu-id="a0c9d-290">У вас нет лицензий, необходимых для использования компьютера, управляемого корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-290">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="a0c9d-291">Дополнительные сведения можно найти в [статье управляемые технологии для настольных ПК Майкрософт](../intro/technologies.md) и [Дополнительные сведения о лицензиях](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-291">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="a0c9d-292">Имена учетных записей безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-292">Security account names</span></span>

<span data-ttu-id="a0c9d-293">Некоторые имена учетных записей безопасности могут конфликтовать с настольными компьютерами, созданными корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-293">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="a0c9d-294">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-294">**Not ready**</span></span>

<span data-ttu-id="a0c9d-295">У вас есть по крайней мере одно имя учетной записи, которое будет конфликтовать с рабочим столом, созданным корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-295">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="a0c9d-296">Работайте с представителем учетной записи Майкрософт, чтобы исключить эти имена учетных записей.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-296">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="a0c9d-297">Роли администраторов безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-297">Security administrator roles</span></span>

<span data-ttu-id="a0c9d-298">Пользователям с определенными ролями безопасности должны быть назначены в защитнике Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-298">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="a0c9d-299">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-299">**Advisory**</span></span>

<span data-ttu-id="a0c9d-300">Если в вашей организации Azure AD назначена любая из этих ролей, убедитесь, что они также назначены в защитнике Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-300">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a0c9d-301">В противном случае администраторы с этими ролями не смогут получить доступ к порталу администрирования.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-301">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="a0c9d-302">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-302">Security Reader</span></span>
- <span data-ttu-id="a0c9d-303">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-303">Security Operator</span></span>
- <span data-ttu-id="a0c9d-304">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="a0c9d-304">Global Reader</span></span>

<span data-ttu-id="a0c9d-305">Дополнительные сведения см. в статье [Создание ролей и управление ими для управления доступом на основе ролей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-305">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="a0c9d-306">По умолчанию для безопасности</span><span class="sxs-lookup"><span data-stu-id="a0c9d-306">Security default</span></span>

<span data-ttu-id="a0c9d-307">Параметры безопасности по умолчанию в Azure Active Directory не допускают управления устройствами с помощью Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-307">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="a0c9d-308">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-308">**Not ready**</span></span>

<span data-ttu-id="a0c9d-309">Параметры безопасности по умолчанию включены.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-309">You have Security defaults turned on.</span></span> <span data-ttu-id="a0c9d-310">Отключите параметры безопасности по умолчанию и настройте политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-310">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="a0c9d-311">Более подробную информацию можно узнать в статье [Общие политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-311">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="a0c9d-312">Самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="a0c9d-312">Self-service Password Reset</span></span>

<span data-ttu-id="a0c9d-313">Для всех пользователей необходимо включить функцию самостоятельного сброса паролей (SSPR).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-313">Self-service Password Reset (SSPR) must be enabled for all users.</span></span> <span data-ttu-id="a0c9d-314">В противном случае учетные записи службы для рабочих столов, управляемой Майкрософт, работать не могут.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-314">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="a0c9d-315">Дополнительные сведения см. [в разделе Tutorial: разрешить пользователям разблокировать свою учетную запись или сбросить пароли с помощью функции самообслуживания Azure Active Directory для самостоятельного сброса пароля](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="a0c9d-315">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="a0c9d-316">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-316">**Advisory**</span></span>

<span data-ttu-id="a0c9d-317">Убедитесь, что **выбранный** параметр SSPR включает в себя системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-317">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>


### <a name="standard-user-role"></a><span data-ttu-id="a0c9d-318">Роль обычного пользователя</span><span class="sxs-lookup"><span data-stu-id="a0c9d-318">Standard user role</span></span>

<span data-ttu-id="a0c9d-319">Пользователи настольного компьютера, управляемые корпорацией Майкрософт, должны быть стандартными пользователями без прав локального администратора.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-319">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="a0c9d-320">При запуске настольного компьютера, управляемого Майкрософт, им будет назначена роль стандартного пользователя.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-320">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="a0c9d-321">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-321">**Advisory**</span></span>

<span data-ttu-id="a0c9d-322">Пользователи настольных систем, управляемых Майкрософт, не должны иметь права локального администратора перед регистрацией.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-322">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="a0c9d-323">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="a0c9d-323">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="a0c9d-324">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="a0c9d-324">OneDrive for Business</span></span>

<span data-ttu-id="a0c9d-325">Параметр **Разрешить синхронизацию только на компьютерах, присоединенных к определенным доменам** , будет конфликтовать с управляемым рабочим столом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-325">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="a0c9d-326">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="a0c9d-326">**Advisory**</span></span>

<span data-ttu-id="a0c9d-327">Вы используете параметр **Разрешить синхронизацию только на компьютерах, присоединенных к определенным доменам** .</span><span class="sxs-lookup"><span data-stu-id="a0c9d-327">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="a0c9d-328">Этот параметр не будет работать с настольным компьютером, управляемым Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-328">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="a0c9d-329">Отключите этот параметр, а затем настройте OneDrive для бизнеса для использования политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-329">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="a0c9d-330">Ознакомьтесь с разкрывающимся [планом развертывания условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) для получения справки.</span><span class="sxs-lookup"><span data-stu-id="a0c9d-330">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

