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
ms.openlocfilehash: a6dec9473ee632b74bb79e50156cedff53a3cba3
ms.sourcegitcommit: fa26da0be667d4be0121c52b05488dc76c5d626c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/29/2020
ms.locfileid: "48795121"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="f0e14-104">Устранение проблем, обнаруженных средством оценки готовности</span><span class="sxs-lookup"><span data-stu-id="f0e14-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="f0e14-105">Для каждой проверки средство сообщит один из четырех возможных результатов:</span><span class="sxs-lookup"><span data-stu-id="f0e14-105">For each check, the tool will report one of four possible results:</span></span>


|<span data-ttu-id="f0e14-106">Результат</span><span class="sxs-lookup"><span data-stu-id="f0e14-106">Result</span></span>  |<span data-ttu-id="f0e14-107">Смысл</span><span class="sxs-lookup"><span data-stu-id="f0e14-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="f0e14-108">Ready</span><span class="sxs-lookup"><span data-stu-id="f0e14-108">Ready</span></span>     | <span data-ttu-id="f0e14-109">Перед регистрацией не требуются никакие действия.</span><span class="sxs-lookup"><span data-stu-id="f0e14-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="f0e14-110">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="f0e14-110">Advisory</span></span>    | <span data-ttu-id="f0e14-111">Выполните действия, описанные в этом инструменте, или в этой статье, чтобы получить лучшие сведения о возможностях регистрации и для пользователей.</span><span class="sxs-lookup"><span data-stu-id="f0e14-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="f0e14-112">Вы *можете* выполнить регистрацию, но вам необходимо устранить эти проблемы перед развертыванием первого устройства.</span><span class="sxs-lookup"><span data-stu-id="f0e14-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="f0e14-113">Не готов</span><span class="sxs-lookup"><span data-stu-id="f0e14-113">Not ready</span></span> | <span data-ttu-id="f0e14-114">*Если вы не устраните эти проблемы, регистрация завершится с ошибками.*</span><span class="sxs-lookup"><span data-stu-id="f0e14-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="f0e14-115">Выполните действия, описанные в этом инструменте, или в этой статье, чтобы устранить их.</span><span class="sxs-lookup"><span data-stu-id="f0e14-115">Follow the steps in the tool or this article to resolve them.</span></span>        |
|<span data-ttu-id="f0e14-116">Error</span><span class="sxs-lookup"><span data-stu-id="f0e14-116">Error</span></span> | <span data-ttu-id="f0e14-117">Используемая роль Azure Active Directory (AD) не обладает разрешениями, достаточными для запуска этой проверки.</span><span class="sxs-lookup"><span data-stu-id="f0e14-117">The Azure Active Director (AD) role you're using doesn't have sufficient permission to run this check.</span></span> |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="f0e14-118">Параметры Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="f0e14-118">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="f0e14-119">Профиль развертывания для автопилота</span><span class="sxs-lookup"><span data-stu-id="f0e14-119">Autopilot deployment profile</span></span>

<span data-ttu-id="f0e14-120">Вы не должны иметь существующие профили автопилота, которые нацелены на назначенные или динамические группы, используемые Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f0e14-120">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0e14-121">На рабочем столе Майкрософт используется Автопилот для подготовки новых устройств.</span><span class="sxs-lookup"><span data-stu-id="f0e14-121">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="f0e14-122">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-122">**Not ready**</span></span>

<span data-ttu-id="f0e14-123">У вас есть профиль автопилота, назначаемый всем устройствам.</span><span class="sxs-lookup"><span data-stu-id="f0e14-123">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="f0e14-124">Для получения инструкций обратитесь к разделу [Регистрация устройств Windows в Intune с помощью Windows автопилота](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="f0e14-124">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="f0e14-125">После регистрации на рабочем столе, управляемой Майкрософт, настройте политику автопилота, чтобы исключить **все современные устройства — все** группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0e14-125">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="f0e14-126">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-126">**Advisory**</span></span>

<span data-ttu-id="f0e14-127">Убедитесь, что профили автопилота нацелены на назначенную или динамическую группу Azure AD, которая не включает устройства, управляемые Майкрософт для настольных компьютеров, которые будут созданы при регистрации.</span><span class="sxs-lookup"><span data-stu-id="f0e14-127">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="f0e14-128">Для получения инструкций обратитесь к разделу [Регистрация устройств Windows в Intune с помощью Windows автопилота](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="f0e14-128">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="f0e14-129">После регистрации на рабочем столе, управляемой Майкрософт, настройте политику автопилота, чтобы исключить **все современные устройства — все** группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0e14-129">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="f0e14-130">Соединители сертификатов</span><span class="sxs-lookup"><span data-stu-id="f0e14-130">Certificate connectors</span></span>

<span data-ttu-id="f0e14-131">При наличии соединителей сертификатов, используемых устройствами, которые вы хотите зарегистрировать на компьютере, управляемом Майкрософт, соединители не могут содержать ошибок.</span><span class="sxs-lookup"><span data-stu-id="f0e14-131">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="f0e14-132">В вашу ситуацию будет применен только один из следующих рекомендаций, поэтому следует тщательно проверять их.</span><span class="sxs-lookup"><span data-stu-id="f0e14-132">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="f0e14-133">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-133">**Advisory**</span></span>

<span data-ttu-id="f0e14-134">Нет соединителей сертификатов.</span><span class="sxs-lookup"><span data-stu-id="f0e14-134">No certificate connectors are present.</span></span> <span data-ttu-id="f0e14-135">Возможно, вам не потребуются соединители, но необходимо оценить, требуются ли для сетевого подключения к управляемым устройствам Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="f0e14-135">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0e14-136">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="f0e14-136">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="f0e14-137">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-137">**Advisory**</span></span>

<span data-ttu-id="f0e14-138">По крайней мере один соединитель сертификатов содержит ошибку.</span><span class="sxs-lookup"><span data-stu-id="f0e14-138">At least one certificate connector has an error.</span></span> <span data-ttu-id="f0e14-139">Если этот соединитель необходим для подключения к настольным устройствам, управляемым корпорацией Майкрософт, необходимо устранить эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="f0e14-139">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="f0e14-140">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="f0e14-140">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="f0e14-141">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-141">**Advisory**</span></span>

<span data-ttu-id="f0e14-142">У вас есть по крайней мере один соединитель сертификатов, и при этом не сообщается об ошибках.</span><span class="sxs-lookup"><span data-stu-id="f0e14-142">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="f0e14-143">Тем не менее, может потребоваться создать профиль для повторного использования соединителя для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-143">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0e14-144">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="f0e14-144">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="f0e14-145">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="f0e14-145">Conditional access policies</span></span>

<span data-ttu-id="f0e14-146">Политики условного доступа в Организации Azure AD не должны быть нацелены на управление пользователями настольных систем Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-146">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="f0e14-147">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-147">**Not ready**</span></span>

<span data-ttu-id="f0e14-148">У вас есть по крайней мере одна политика условного доступа, предназначенная для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="f0e14-148">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="f0e14-149">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает группу Azure AD управляемых учетных записей служб рабочего стола Майкрософт, которые будут создаваться при регистрации.</span><span class="sxs-lookup"><span data-stu-id="f0e14-149">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="f0e14-150">Для получения инструкций обратитесь [к разделу условный доступ: пользователи и группы](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="f0e14-150">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="f0e14-151">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-151">**Advisory**</span></span>

<span data-ttu-id="f0e14-152">Убедитесь, что все политики условного доступа исключены из группы Azure AD " **учетные записи служб современного рабочего места** ".</span><span class="sxs-lookup"><span data-stu-id="f0e14-152">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="f0e14-153">Инструкции по [настройке условного доступа](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="f0e14-153">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="f0e14-154">Группа Azure AD " **учетные записи служб современного рабочего места** " — это динамическая группа, которая создается для службы при регистрации.</span><span class="sxs-lookup"><span data-stu-id="f0e14-154">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="f0e14-155">После регистрации вам потребуется вернуться к исключению этой группы.</span><span class="sxs-lookup"><span data-stu-id="f0e14-155">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="f0e14-156">Для получения дополнительных сведений об этих учетных записях служб ознакомьтесь со статьями [стандартные рабочие процедуры](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="f0e14-156">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>

<span data-ttu-id="f0e14-157">**Error**</span><span class="sxs-lookup"><span data-stu-id="f0e14-157">**Error**</span></span>

<span data-ttu-id="f0e14-158">Роль администратора Intune не имеет достаточных разрешений для этой проверки.</span><span class="sxs-lookup"><span data-stu-id="f0e14-158">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="f0e14-159">Кроме того, для выполнения этой проверки потребуются все назначенные роли Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0e14-159">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="f0e14-160">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-160">Security Reader</span></span>
- <span data-ttu-id="f0e14-161">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-161">Security Administrator</span></span>
- <span data-ttu-id="f0e14-162">Администратор условного доступа</span><span class="sxs-lookup"><span data-stu-id="f0e14-162">Conditional Access Administrator</span></span>
- <span data-ttu-id="f0e14-163">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="f0e14-163">Global Reader</span></span>
- <span data-ttu-id="f0e14-164">Администратор устройств</span><span class="sxs-lookup"><span data-stu-id="f0e14-164">Devices Administrator</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="f0e14-165">Политики соответствия требованиям устройств</span><span class="sxs-lookup"><span data-stu-id="f0e14-165">Device Compliance policies</span></span>

<span data-ttu-id="f0e14-166">Политики соответствия требованиям устройств Intune в Организации Azure AD не должны быть нацелены на пользователей, управляемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-166">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="f0e14-167">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-167">**Not ready**</span></span>

<span data-ttu-id="f0e14-168">У вас есть по крайней мере одна политика соответствия требованиям, которая нацелена на всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="f0e14-168">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="f0e14-169">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает пользователей, настольных под управлением Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f0e14-169">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="f0e14-170">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="f0e14-170">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="f0e14-171">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-171">**Advisory**</span></span>

<span data-ttu-id="f0e14-172">Убедитесь, что все политики соответствия требованиям не включают пользователей, настольных под управлением Microsoft.</span><span class="sxs-lookup"><span data-stu-id="f0e14-172">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="f0e14-173">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="f0e14-173">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="f0e14-174">Политики конфигурации устройств</span><span class="sxs-lookup"><span data-stu-id="f0e14-174">Device Configuration policies</span></span>

<span data-ttu-id="f0e14-175">Политики конфигурации устройств Intune в Организации Azure AD не должны быть предназначены для управления устройствами и пользователями настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-175">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="f0e14-176">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-176">**Not ready**</span></span>

<span data-ttu-id="f0e14-177">У вас есть по крайней мере одна политика конфигурации, которая нацелена на всех пользователей, все устройства или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="f0e14-177">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="f0e14-178">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает в себя компьютеры, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-178">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0e14-179">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="f0e14-179">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="f0e14-180">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-180">**Advisory**</span></span>

<span data-ttu-id="f0e14-181">Убедитесь, что все политики соответствия требованиям не входят в состав компьютеров, управляемых пользователями.</span><span class="sxs-lookup"><span data-stu-id="f0e14-181">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="f0e14-182">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="f0e14-182">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="f0e14-183">Ограничения на типы устройств</span><span class="sxs-lookup"><span data-stu-id="f0e14-183">Device type restrictions</span></span>

<span data-ttu-id="f0e14-184">На настольных устройствах, управляемых Майкрософт, должно быть разрешено регистрироваться в Intune.</span><span class="sxs-lookup"><span data-stu-id="f0e14-184">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="f0e14-185">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-185">**Not ready**</span></span>

<span data-ttu-id="f0e14-186">Выполните действия, описанные в статье Set **Reallows** [Set](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) , чтобы изменить значение параметра на Allow.</span><span class="sxs-lookup"><span data-stu-id="f0e14-186">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow** .</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="f0e14-187">Страница состояния регистрации</span><span class="sxs-lookup"><span data-stu-id="f0e14-187">Enrollment Status Page</span></span>

<span data-ttu-id="f0e14-188">В настоящее время включена страница состояния регистрации (ESP).</span><span class="sxs-lookup"><span data-stu-id="f0e14-188">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="f0e14-189">Если вы участвуете в общедоступной предварительной версии этой функции, вы можете пропустить этот элемент.</span><span class="sxs-lookup"><span data-stu-id="f0e14-189">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="f0e14-190">Для получения дополнительных сведений обратитесь к разделу [First-Run with автопилот и странице Состояние регистрации](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="f0e14-190">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="f0e14-191">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-191">**Not ready**</span></span>

<span data-ttu-id="f0e14-192">Установленный по умолчанию профиль ESP позволяет **Показать ход выполнения настройки приложений и профилей** .</span><span class="sxs-lookup"><span data-stu-id="f0e14-192">You have the ESP default profile set to **Show app and profile configuration progress** .</span></span> <span data-ttu-id="f0e14-193">Отключите этот параметр, выполнив действия, описанные в разделе [Настройка страницы состояния регистрации](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="f0e14-193">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="f0e14-194">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-194">**Advisory**</span></span>

<span data-ttu-id="f0e14-195">Убедитесь, что все профили с параметром " **Показать ход выполнения настройки приложения и профиля** " не назначены какой бы то ни было группе Azure AD, включающей в себя системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-195">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0e14-196">Дополнительные сведения можно найти [в разделе Настройка страницы состояния регистрации](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="f0e14-196">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="f0e14-197">Регистрация в Intune</span><span class="sxs-lookup"><span data-stu-id="f0e14-197">Intune enrollment</span></span>

<span data-ttu-id="f0e14-198">Устройства с Windows 10 в Организации Azure AD должны автоматически регистрироваться в Intune.</span><span class="sxs-lookup"><span data-stu-id="f0e14-198">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="f0e14-199">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-199">**Not ready**</span></span>

<span data-ttu-id="f0e14-200">Пользователи в Организации Azure AD не регистрируются в Microsoft Intune автоматически.</span><span class="sxs-lookup"><span data-stu-id="f0e14-200">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="f0e14-201">Замените область пользователя MDM на **некоторые** или **все** .</span><span class="sxs-lookup"><span data-stu-id="f0e14-201">Change the MDM User scope to **Some** or **All** .</span></span> <span data-ttu-id="f0e14-202">Если вы выберете **некоторые** из них, вернитесь обратно после регистрации и выберите в разделе " **современная Рабочая** область" все группы Azure AD для **групп** .</span><span class="sxs-lookup"><span data-stu-id="f0e14-202">If you choose **Some** , come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups** .</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="f0e14-203">Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f0e14-203">Microsoft Store for Business</span></span>

<span data-ttu-id="f0e14-204">Мы используем Microsoft Store для бизнеса, чтобы вы могли скачать корпоративный портал, чтобы развернуть некоторые приложения, такие как Microsoft Project и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="f0e14-204">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="f0e14-205">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-205">**Not ready**</span></span>

<span data-ttu-id="f0e14-206">Microsoft Store для бизнеса либо не включен, либо не синхронизирован с Intune.</span><span class="sxs-lookup"><span data-stu-id="f0e14-206">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="f0e14-207">Для получения дополнительных сведений Узнайте, [как управлять корпоративными приобретенными приложениями из Microsoft Store для бизнеса с помощью Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) и [установить портал компании Intune на устройствах](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="f0e14-207">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="f0e14-208">Многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="f0e14-208">Multi-factor authentication</span></span>

<span data-ttu-id="f0e14-209">Многофакторная проверка подлинности не должна быть случайно применена к управляемым учетным записям служб рабочих столов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-209">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="f0e14-210">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-210">**Not ready**</span></span>

<span data-ttu-id="f0e14-211">Некоторые политики многофакторной проверки подлинности (MFA) устанавливаются как обязательные для политик условного доступа, назначенных всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="f0e14-211">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="f0e14-212">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="f0e14-212">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0e14-213">Дополнительные сведения см. в статье [политики условного доступа](#conditional-access-policies) и [Условный доступ: требовать MFA для всех пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="f0e14-213">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="f0e14-214">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-214">**Advisory**</span></span>

<span data-ttu-id="f0e14-215">Убедитесь, что все политики условного доступа, требующие MFA, не включают в себя всю группу Azure AD в **современном рабочем месте** .</span><span class="sxs-lookup"><span data-stu-id="f0e14-215">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="f0e14-216">Дополнительные сведения см. в статье [политики условного доступа](#conditional-access-policies) и [Условный доступ: требовать MFA для всех пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="f0e14-216">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="f0e14-217">**Современная Рабочая область — все** группы Azure AD — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="f0e14-217">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>

<span data-ttu-id="f0e14-218">**Error**</span><span class="sxs-lookup"><span data-stu-id="f0e14-218">**Error**</span></span>

<span data-ttu-id="f0e14-219">Роль администратора Intune не имеет достаточных разрешений для этой проверки.</span><span class="sxs-lookup"><span data-stu-id="f0e14-219">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="f0e14-220">Кроме того, для выполнения этой проверки потребуются все назначенные роли Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0e14-220">You'll also need any of these Azure AD roles assigned to run this check:</span></span>

- <span data-ttu-id="f0e14-221">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-221">Security Reader</span></span>
- <span data-ttu-id="f0e14-222">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-222">Security Administrator</span></span>
- <span data-ttu-id="f0e14-223">Администратор условного доступа</span><span class="sxs-lookup"><span data-stu-id="f0e14-223">Conditional Access Administrator</span></span>
- <span data-ttu-id="f0e14-224">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="f0e14-224">Global Reader</span></span>
- <span data-ttu-id="f0e14-225">Администратор устройств</span><span class="sxs-lookup"><span data-stu-id="f0e14-225">Devices Administrator</span></span>


### <a name="powershell-scripts"></a><span data-ttu-id="f0e14-226">Сценарии PowerShell</span><span class="sxs-lookup"><span data-stu-id="f0e14-226">PowerShell scripts</span></span>

<span data-ttu-id="f0e14-227">Сценарии Windows PowerShell не могут назначаться таким образом, чтобы направлять устройства, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-227">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="f0e14-228">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-228">**Advisory**</span></span>

<span data-ttu-id="f0e14-229">Убедитесь, что сценарии Windows PowerShell в Организации Azure AD не предназначены для управления устройствами и пользователями настольных компьютеров корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-229">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="f0e14-230">Дополнительные сведения см. в статье [использование скриптов PowerShell для устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="f0e14-230">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="f0e14-231">Регион</span><span class="sxs-lookup"><span data-stu-id="f0e14-231">Region</span></span>

<span data-ttu-id="f0e14-232">Ваш регион должен поддерживаться на настольном компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-232">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f0e14-233">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-233">**Not ready**</span></span>

<span data-ttu-id="f0e14-234">В настоящее время область организации Azure AD не поддерживается на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-234">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0e14-235">Для получения дополнительных [сведений см.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="f0e14-235">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="f0e14-236">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-236">**Advisory**</span></span>

<span data-ttu-id="f0e14-237">Одна или несколько стран, в которых находится ваша организация Azure AD, не поддерживаются на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-237">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0e14-238">Для получения дополнительных [сведений см.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="f0e14-238">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="f0e14-239">Базовые показатели безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-239">Security baselines</span></span>

<span data-ttu-id="f0e14-240">Базовые политики безопасности не должны ориентироваться на компьютеры, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-240">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="f0e14-241">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-241">**Not ready**</span></span>

<span data-ttu-id="f0e14-242">У вас есть базовый профиль безопасности, который предназначен для всех пользователей, всех устройств или и того, и другое.</span><span class="sxs-lookup"><span data-stu-id="f0e14-242">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="f0e14-243">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="f0e14-243">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0e14-244">В разделе [Использование базовых показателей безопасности для настройки устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="f0e14-244">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="f0e14-245">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-245">**Advisory**</span></span>

<span data-ttu-id="f0e14-246">Убедитесь, что все базовые политики безопасности исключают системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-246">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0e14-247">В разделе [Использование базовых показателей безопасности для настройки устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="f0e14-247">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="f0e14-248">" **Современные рабочие устройства — все** группы Azure AD" — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="f0e14-248">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="f0e14-249">Приложения для Windows</span><span class="sxs-lookup"><span data-stu-id="f0e14-249">Windows apps</span></span>

<span data-ttu-id="f0e14-250">Просмотрите приложения, которые должны иметь пользователи, управляемые Майкрософт для настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="f0e14-250">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="f0e14-251">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-251">**Advisory**</span></span>

<span data-ttu-id="f0e14-252">Необходимо подготовить список приложений, которые должны иметь пользователи, управляемые Майкрософт для настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="f0e14-252">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="f0e14-253">Убедитесь, что эти приложения можно развернуть с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="f0e14-253">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="f0e14-254">Дополнительные сведения содержатся [в статье приложения на компьютере, управляемом Майкрософт](apps.md).</span><span class="sxs-lookup"><span data-stu-id="f0e14-254">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="f0e14-255">Вы можете попросить своего представителя учетной записи Майкрософт выполнить запрос в диспетчере конфигурации конечных точек Майкрософт, чтобы определить, какие приложения готовы для переноса в Intune или нуждаются в корректировке.</span><span class="sxs-lookup"><span data-stu-id="f0e14-255">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="f0e14-256">Windows Hello для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f0e14-256">Windows Hello for Business</span></span>

<span data-ttu-id="f0e14-257">Для рабочего стола, управляемого Майкрософт, требуется включить функцию Windows Hello для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="f0e14-257">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="f0e14-258">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-258">**Not ready**</span></span>

<span data-ttu-id="f0e14-259">Windows Hello для бизнеса отключена.</span><span class="sxs-lookup"><span data-stu-id="f0e14-259">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="f0e14-260">Включите его, выполнив действия, описанные в разделе [Создание политики Windows Hello для бизнеса](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="f0e14-260">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="f0e14-261">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-261">**Advisory**</span></span>

<span data-ttu-id="f0e14-262">Windows Hello для бизнеса не настроена.</span><span class="sxs-lookup"><span data-stu-id="f0e14-262">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="f0e14-263">Включите его, выполнив действия, описанные в разделе [Создание политики Windows Hello для бизнеса](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="f0e14-263">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="f0e14-264">Звонки обновления Windows 10</span><span class="sxs-lookup"><span data-stu-id="f0e14-264">Windows 10 update rings</span></span>

<span data-ttu-id="f0e14-265">Политика "Windows 10 Update Ring Ring" в Intune не должна быть нацелена на настольные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-265">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="f0e14-266">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-266">**Not ready**</span></span>

<span data-ttu-id="f0e14-267">У вас есть политика "обновление звонка", предназначенная для всех устройств, всех пользователей или и тех, и других.</span><span class="sxs-lookup"><span data-stu-id="f0e14-267">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="f0e14-268">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="f0e14-268">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f0e14-269">Дополнительные сведения: [Управление обновлениями программного обеспечения Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="f0e14-269">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="f0e14-270">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-270">**Advisory**</span></span>

<span data-ttu-id="f0e14-271">Убедитесь, что все политики обновления звонков не исключают всю группу Azure AD в **современном рабочем месте** .</span><span class="sxs-lookup"><span data-stu-id="f0e14-271">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="f0e14-272">Дополнительные сведения: [Управление обновлениями программного обеспечения Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="f0e14-272">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="f0e14-273">" **Современные рабочие устройства — все** группы Azure AD" — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="f0e14-273">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="f0e14-274">Параметры Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f0e14-274">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="f0e14-275">Подписки на ad hoc</span><span class="sxs-lookup"><span data-stu-id="f0e14-275">Ad hoc subscriptions</span></span>

<span data-ttu-id="f0e14-276">Показывает, как проверить, что параметр, для которого задано значение "false"), может препятствовать правильной работе перемещения корпоративных состояний.</span><span class="sxs-lookup"><span data-stu-id="f0e14-276">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="f0e14-277">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-277">**Advisory**</span></span>

<span data-ttu-id="f0e14-278">Убедитесь, что для параметра **алловадхоксубскриптионс** задано **значение true** .</span><span class="sxs-lookup"><span data-stu-id="f0e14-278">Ensure that **AllowAdHocSubscriptions** is set to **True** .</span></span> <span data-ttu-id="f0e14-279">В противном случае роуминг состояния предприятия может не работать.</span><span class="sxs-lookup"><span data-stu-id="f0e14-279">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="f0e14-280">Дополнительные сведения см. в статье [Set – мсолкомпанисеттингс](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="f0e14-280">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="f0e14-281">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="f0e14-281">Enterprise State Roaming</span></span>

<span data-ttu-id="f0e14-282">Роуминг состояния предприятия должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="f0e14-282">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="f0e14-283">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-283">**Advisory**</span></span>

<span data-ttu-id="f0e14-284">Убедитесь, что роуминг состояния предприятия включен для **всех** или для **выбранных** групп.</span><span class="sxs-lookup"><span data-stu-id="f0e14-284">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="f0e14-285">Дополнительные сведения см в статье [Enable Enterprise State роуминг в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="f0e14-285">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="f0e14-286">Лицензии</span><span class="sxs-lookup"><span data-stu-id="f0e14-286">Licenses</span></span>

<span data-ttu-id="f0e14-287">Для использования настольного компьютера, управляемого Майкрософт, требуется несколько лицензий.</span><span class="sxs-lookup"><span data-stu-id="f0e14-287">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f0e14-288">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-288">**Not Ready**</span></span>

<span data-ttu-id="f0e14-289">У вас нет лицензий, необходимых для использования компьютера, управляемого корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-289">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0e14-290">Дополнительные сведения можно найти в [статье управляемые технологии для настольных ПК Майкрософт](../intro/technologies.md) и [Дополнительные сведения о лицензиях](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="f0e14-290">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="f0e14-291">Имена учетных записей безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-291">Security account names</span></span>

<span data-ttu-id="f0e14-292">Некоторые имена учетных записей безопасности могут конфликтовать с настольными компьютерами, созданными корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-292">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f0e14-293">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-293">**Not ready**</span></span>

<span data-ttu-id="f0e14-294">У вас есть по крайней мере одно имя учетной записи, которое будет конфликтовать с рабочим столом, созданным корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-294">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0e14-295">Работайте с представителем учетной записи Майкрософт, чтобы исключить эти имена учетных записей.</span><span class="sxs-lookup"><span data-stu-id="f0e14-295">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="f0e14-296">Роли администраторов безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-296">Security administrator roles</span></span>

<span data-ttu-id="f0e14-297">Пользователям с определенными ролями безопасности должны быть назначены в защитнике Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f0e14-297">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="f0e14-298">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-298">**Advisory**</span></span>

<span data-ttu-id="f0e14-299">Если в вашей организации Azure AD назначена любая из этих ролей, убедитесь, что они также назначены в защитнике Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f0e14-299">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f0e14-300">В противном случае администраторы с этими ролями не смогут получить доступ к порталу администрирования.</span><span class="sxs-lookup"><span data-stu-id="f0e14-300">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="f0e14-301">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-301">Security Reader</span></span>
- <span data-ttu-id="f0e14-302">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-302">Security Operator</span></span>
- <span data-ttu-id="f0e14-303">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="f0e14-303">Global Reader</span></span>

<span data-ttu-id="f0e14-304">Дополнительные сведения см. в статье [Создание ролей и управление ими для управления доступом на основе ролей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="f0e14-304">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="f0e14-305">По умолчанию для безопасности</span><span class="sxs-lookup"><span data-stu-id="f0e14-305">Security default</span></span>

<span data-ttu-id="f0e14-306">Параметры безопасности по умолчанию в Azure Active Directory не допускают управления устройствами с помощью Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="f0e14-306">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="f0e14-307">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-307">**Not ready**</span></span>

<span data-ttu-id="f0e14-308">Параметры безопасности по умолчанию включены.</span><span class="sxs-lookup"><span data-stu-id="f0e14-308">You have Security defaults turned on.</span></span> <span data-ttu-id="f0e14-309">Отключите параметры безопасности по умолчанию и настройте политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="f0e14-309">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="f0e14-310">Более подробную информацию можно узнать в статье [Общие политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="f0e14-310">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="f0e14-311">Самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="f0e14-311">Self-service Password Reset</span></span>

<span data-ttu-id="f0e14-312">Необходимо включить функцию самостоятельного сброса паролей (SSPR).</span><span class="sxs-lookup"><span data-stu-id="f0e14-312">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="f0e14-313">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="f0e14-313">**Not ready**</span></span>

<span data-ttu-id="f0e14-314">SSPR должен быть включен для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="f0e14-314">SSPR must be enabled for all users.</span></span> <span data-ttu-id="f0e14-315">В противном случае учетные записи службы для рабочих столов, управляемой Майкрософт, работать не могут.</span><span class="sxs-lookup"><span data-stu-id="f0e14-315">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="f0e14-316">Дополнительные сведения см. [в разделе Tutorial: разрешить пользователям разблокировать свою учетную запись или сбросить пароли с помощью функции самообслуживания Azure Active Directory для самостоятельного сброса пароля](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="f0e14-316">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="f0e14-317">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-317">**Advisory**</span></span>

<span data-ttu-id="f0e14-318">Убедитесь, что **выбранный** параметр SSPR включает в себя системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-318">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="f0e14-319">**Error**</span><span class="sxs-lookup"><span data-stu-id="f0e14-319">**Error**</span></span>

<span data-ttu-id="f0e14-320">Роль администратора Intune не имеет достаточных разрешений для этой проверки.</span><span class="sxs-lookup"><span data-stu-id="f0e14-320">The Intune Administrator role doesn't have sufficient permissions for this check.</span></span> <span data-ttu-id="f0e14-321">Кроме того, для выполнения этой проверки потребуется назначить роль читателя отчетов Azure AD.</span><span class="sxs-lookup"><span data-stu-id="f0e14-321">You'll also need the Reports Reader Azure AD role assigned to run this check.</span></span>


### <a name="standard-user-role"></a><span data-ttu-id="f0e14-322">Роль обычного пользователя</span><span class="sxs-lookup"><span data-stu-id="f0e14-322">Standard user role</span></span>

<span data-ttu-id="f0e14-323">Пользователи настольного компьютера, управляемые корпорацией Майкрософт, должны быть стандартными пользователями без прав локального администратора.</span><span class="sxs-lookup"><span data-stu-id="f0e14-323">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="f0e14-324">При запуске настольного компьютера, управляемого Майкрософт, им будет назначена роль стандартного пользователя.</span><span class="sxs-lookup"><span data-stu-id="f0e14-324">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="f0e14-325">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-325">**Advisory**</span></span>

<span data-ttu-id="f0e14-326">Пользователи настольных систем, управляемых Майкрософт, не должны иметь права локального администратора перед регистрацией.</span><span class="sxs-lookup"><span data-stu-id="f0e14-326">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="f0e14-327">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="f0e14-327">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="f0e14-328">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="f0e14-328">OneDrive for Business</span></span>

<span data-ttu-id="f0e14-329">Параметр **Разрешить синхронизацию только на компьютерах, присоединенных к определенным доменам** , будет конфликтовать с управляемым рабочим столом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-329">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="f0e14-330">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="f0e14-330">**Advisory**</span></span>

<span data-ttu-id="f0e14-331">Вы используете параметр **Разрешить синхронизацию только на компьютерах, присоединенных к определенным доменам** .</span><span class="sxs-lookup"><span data-stu-id="f0e14-331">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="f0e14-332">Этот параметр не будет работать с настольным компьютером, управляемым Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="f0e14-332">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="f0e14-333">Отключите этот параметр, а затем настройте OneDrive для бизнеса для использования политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="f0e14-333">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="f0e14-334">Ознакомьтесь с разкрывающимся [планом развертывания условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) для получения справки.</span><span class="sxs-lookup"><span data-stu-id="f0e14-334">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

