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
ms.openlocfilehash: 2c9638dc7b8c6d095b87cf81114f3812c8362597
ms.sourcegitcommit: 3b1bd8aa1430bc9565743a446bbc27b199f30f73
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/22/2020
ms.locfileid: "48656155"
---
# <a name="fix-issues-found-by-the-readiness-assessment-tool"></a><span data-ttu-id="bb694-104">Устранение проблем, обнаруженных средством оценки готовности</span><span class="sxs-lookup"><span data-stu-id="bb694-104">Fix issues found by the readiness assessment tool</span></span>

<span data-ttu-id="bb694-105">Для каждой проверки средство сообщит один из трех возможных результатов:</span><span class="sxs-lookup"><span data-stu-id="bb694-105">For each check, the tool will report one of three possible results:</span></span>


|<span data-ttu-id="bb694-106">Результат</span><span class="sxs-lookup"><span data-stu-id="bb694-106">Result</span></span>  |<span data-ttu-id="bb694-107">Смысл</span><span class="sxs-lookup"><span data-stu-id="bb694-107">Meaning</span></span>  |
|---------|---------|
|<span data-ttu-id="bb694-108">Ready</span><span class="sxs-lookup"><span data-stu-id="bb694-108">Ready</span></span>     | <span data-ttu-id="bb694-109">Перед регистрацией не требуются никакие действия.</span><span class="sxs-lookup"><span data-stu-id="bb694-109">No action is required before completing enrollment.</span></span>        |
|<span data-ttu-id="bb694-110">Рекомендация</span><span class="sxs-lookup"><span data-stu-id="bb694-110">Advisory</span></span>    | <span data-ttu-id="bb694-111">Выполните действия, описанные в этом инструменте, или в этой статье, чтобы получить лучшие сведения о возможностях регистрации и для пользователей.</span><span class="sxs-lookup"><span data-stu-id="bb694-111">Follow the steps in the tool or this article for the best experience with enrollment and for users.</span></span> <span data-ttu-id="bb694-112">Вы *можете* выполнить регистрацию, но вам необходимо устранить эти проблемы перед развертыванием первого устройства.</span><span class="sxs-lookup"><span data-stu-id="bb694-112">You *can* complete enrollment, but you must fix these issues before you deploy your first device.</span></span>        |
|<span data-ttu-id="bb694-113">Не готов</span><span class="sxs-lookup"><span data-stu-id="bb694-113">Not ready</span></span> | <span data-ttu-id="bb694-114">*Если вы не устраните эти проблемы, регистрация завершится с ошибками.*</span><span class="sxs-lookup"><span data-stu-id="bb694-114">*Enrollment will fail if you don't fix these issues.*</span></span> <span data-ttu-id="bb694-115">Выполните действия, описанные в этом инструменте, или в этой статье, чтобы устранить их.</span><span class="sxs-lookup"><span data-stu-id="bb694-115">Follow the steps in the tool or this article to resolve them.</span></span>        |

## <a name="microsoft-intune-settings"></a><span data-ttu-id="bb694-116">Параметры Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="bb694-116">Microsoft Intune settings</span></span>

### <a name="autopilot-deployment-profile"></a><span data-ttu-id="bb694-117">Профиль развертывания для автопилота</span><span class="sxs-lookup"><span data-stu-id="bb694-117">Autopilot deployment profile</span></span>

<span data-ttu-id="bb694-118">Вы не должны иметь существующие профили автопилота, которые нацелены на назначенные или динамические группы, используемые Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bb694-118">You shouldn't have any existing Autopilot profiles that target assigned or dynamic groups used by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bb694-119">На рабочем столе Майкрософт используется Автопилот для подготовки новых устройств.</span><span class="sxs-lookup"><span data-stu-id="bb694-119">Microsoft Managed Desktop uses Autopilot to provision new devices.</span></span>

<span data-ttu-id="bb694-120">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-120">**Not ready**</span></span>

<span data-ttu-id="bb694-121">У вас есть профиль автопилота, назначаемый всем устройствам.</span><span class="sxs-lookup"><span data-stu-id="bb694-121">You have an Autopilot profile that is assigned to all devices.</span></span> <span data-ttu-id="bb694-122">Для получения инструкций обратитесь к разделу [Регистрация устройств Windows в Intune с помощью Windows автопилота](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="bb694-122">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="bb694-123">После регистрации на рабочем столе, управляемой Майкрософт, настройте политику автопилота, чтобы исключить **все современные устройства — все** группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb694-123">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>

<span data-ttu-id="bb694-124">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-124">**Advisory**</span></span>

<span data-ttu-id="bb694-125">Убедитесь, что профили автопилота нацелены на назначенную или динамическую группу Azure AD, которая не включает устройства, управляемые Майкрософт для настольных компьютеров, которые будут созданы при регистрации.</span><span class="sxs-lookup"><span data-stu-id="bb694-125">Make sure that your Autopilot profiles target an assigned or dynamic Azure AD group that doesn't include Microsoft Managed Desktop devices that will be created at enrollment.</span></span> <span data-ttu-id="bb694-126">Для получения инструкций обратитесь к разделу [Регистрация устройств Windows в Intune с помощью Windows автопилота](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span><span class="sxs-lookup"><span data-stu-id="bb694-126">For steps, see [Enroll Windows devices in Intune by using Windows Autopilot](https://docs.microsoft.com/mem/autopilot/enrollment-autopilot).</span></span> <span data-ttu-id="bb694-127">После регистрации на рабочем столе, управляемой Майкрософт, настройте политику автопилота, чтобы исключить **все современные устройства — все** группы Azure AD.</span><span class="sxs-lookup"><span data-stu-id="bb694-127">After Microsoft Managed Desktop enrollment, set your Autopilot policy to exclude the **Modern Workplace Devices -All** Azure AD group.</span></span>


### <a name="certificate-connectors"></a><span data-ttu-id="bb694-128">Соединители сертификатов</span><span class="sxs-lookup"><span data-stu-id="bb694-128">Certificate connectors</span></span>

<span data-ttu-id="bb694-129">При наличии соединителей сертификатов, используемых устройствами, которые вы хотите зарегистрировать на компьютере, управляемом Майкрософт, соединители не могут содержать ошибок.</span><span class="sxs-lookup"><span data-stu-id="bb694-129">If you have any certificate connectors used by the devices you want to enroll in Microsoft Managed Desktop, the connectors cannot have any errors.</span></span> <span data-ttu-id="bb694-130">В вашу ситуацию будет применен только один из следующих рекомендаций, поэтому следует тщательно проверять их.</span><span class="sxs-lookup"><span data-stu-id="bb694-130">Only one of the following advisories will apply to your situation, so check them carefully.</span></span>

<span data-ttu-id="bb694-131">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-131">**Advisory**</span></span>

<span data-ttu-id="bb694-132">Нет соединителей сертификатов.</span><span class="sxs-lookup"><span data-stu-id="bb694-132">No certificate connectors are present.</span></span> <span data-ttu-id="bb694-133">Возможно, вам не потребуются соединители, но необходимо оценить, требуются ли для сетевого подключения к управляемым устройствам Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="bb694-133">It's possible you don't need any connectors, but you should evaluate whether you might need some for network connectivity to Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bb694-134">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="bb694-134">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>

<span data-ttu-id="bb694-135">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-135">**Advisory**</span></span>

<span data-ttu-id="bb694-136">По крайней мере один соединитель сертификатов содержит ошибку.</span><span class="sxs-lookup"><span data-stu-id="bb694-136">At least one certificate connector has an error.</span></span> <span data-ttu-id="bb694-137">Если этот соединитель необходим для подключения к настольным устройствам, управляемым корпорацией Майкрософт, необходимо устранить эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="bb694-137">If you need this connector for connectivity to Microsoft Managed Desktop devices, you must resolve the error.</span></span> <span data-ttu-id="bb694-138">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="bb694-138">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


<span data-ttu-id="bb694-139">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-139">**Advisory**</span></span>

<span data-ttu-id="bb694-140">У вас есть по крайней мере один соединитель сертификатов, и при этом не сообщается об ошибках.</span><span class="sxs-lookup"><span data-stu-id="bb694-140">You have at least one certificate connector and no errors are reported.</span></span> <span data-ttu-id="bb694-141">Тем не менее, может потребоваться создать профиль для повторного использования соединителя для настольных устройств, управляемых Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-141">However, you might need to create a profile to reuse the connector for Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bb694-142">Дополнительные сведения можно найти в разделе [Prepare Certificate and Network Profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span><span class="sxs-lookup"><span data-stu-id="bb694-142">For more information, see [Prepare certificates and network profiles for Microsoft Managed Desktop](certs-wifi-lan.md).</span></span>


### <a name="conditional-access-policies"></a><span data-ttu-id="bb694-143">Политики условного доступа</span><span class="sxs-lookup"><span data-stu-id="bb694-143">Conditional access policies</span></span>

<span data-ttu-id="bb694-144">Политики условного доступа в Организации Azure AD не должны быть нацелены на управление пользователями настольных систем Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-144">Conditional access policies in your Azure AD organization must not target any Microsoft Manage Desktop users.</span></span>

<span data-ttu-id="bb694-145">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-145">**Not ready**</span></span>

<span data-ttu-id="bb694-146">У вас есть по крайней мере одна политика условного доступа, предназначенная для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="bb694-146">You have at least one conditional access policy that targets all users.</span></span> <span data-ttu-id="bb694-147">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает группу Azure AD управляемых учетных записей служб рабочего стола Майкрософт, которые будут создаваться при регистрации.</span><span class="sxs-lookup"><span data-stu-id="bb694-147">Reset the policy to target a specific Azure AD group that does not include the Azure AD group of Microsoft Managed Desktop service accounts that will be created at enrollment.</span></span> <span data-ttu-id="bb694-148">Для получения инструкций обратитесь [к разделу условный доступ: пользователи и группы](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span><span class="sxs-lookup"><span data-stu-id="bb694-148">For steps, see [Conditional Access: Users and groups](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-users-groups).</span></span>

<span data-ttu-id="bb694-149">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-149">**Advisory**</span></span>

<span data-ttu-id="bb694-150">Убедитесь, что все политики условного доступа исключены из группы Azure AD " **учетные записи служб современного рабочего места** ".</span><span class="sxs-lookup"><span data-stu-id="bb694-150">Make sure that any conditional access policies you have exclude the **Modern Workplace Service Accounts** Azure AD group.</span></span> <span data-ttu-id="bb694-151">Инструкции по [настройке условного доступа](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span><span class="sxs-lookup"><span data-stu-id="bb694-151">For steps, see [Adjust conditional access](https://docs.microsoft.com/microsoft-365/managed-desktop/get-started/conditional-access).</span></span> <span data-ttu-id="bb694-152">Группа Azure AD " **учетные записи служб современного рабочего места** " — это динамическая группа, которая создается для службы при регистрации.</span><span class="sxs-lookup"><span data-stu-id="bb694-152">The **Modern Workplace Service Accounts** Azure AD group is a dynamic group that we create for the service when you enroll.</span></span> <span data-ttu-id="bb694-153">После регистрации вам потребуется вернуться к исключению этой группы.</span><span class="sxs-lookup"><span data-stu-id="bb694-153">You'll have to come back to exclude this group after enrollment.</span></span> <span data-ttu-id="bb694-154">Для получения дополнительных сведений об этих учетных записях служб ознакомьтесь со статьями [стандартные рабочие процедуры](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span><span class="sxs-lookup"><span data-stu-id="bb694-154">For more about these service accounts, see [Standard operating procedures](../service-description/operations-and-monitoring.md#standard-operating-procedures).</span></span>


### <a name="device-compliance-policies"></a><span data-ttu-id="bb694-155">Политики соответствия требованиям устройств</span><span class="sxs-lookup"><span data-stu-id="bb694-155">Device Compliance policies</span></span>

<span data-ttu-id="bb694-156">Политики соответствия требованиям устройств Intune в Организации Azure AD не должны быть нацелены на пользователей, управляемых корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-156">Intune Device Compliance policies in your Azure AD organization must not target any Microsoft Managed Desktop users.</span></span>

<span data-ttu-id="bb694-157">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-157">**Not ready**</span></span>

<span data-ttu-id="bb694-158">У вас есть по крайней мере одна политика соответствия требованиям, которая нацелена на всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="bb694-158">You have at least one compliance policy that targets all users.</span></span> <span data-ttu-id="bb694-159">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает пользователей, настольных под управлением Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb694-159">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="bb694-160">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="bb694-160">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>

<span data-ttu-id="bb694-161">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-161">**Advisory**</span></span>

<span data-ttu-id="bb694-162">Убедитесь, что все политики соответствия требованиям не включают пользователей, настольных под управлением Microsoft.</span><span class="sxs-lookup"><span data-stu-id="bb694-162">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop users.</span></span> <span data-ttu-id="bb694-163">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span><span class="sxs-lookup"><span data-stu-id="bb694-163">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/protect/create-compliance-policy).</span></span>



### <a name="device-configuration-policies"></a><span data-ttu-id="bb694-164">Политики конфигурации устройств</span><span class="sxs-lookup"><span data-stu-id="bb694-164">Device Configuration policies</span></span>

<span data-ttu-id="bb694-165">Политики конфигурации устройств Intune в Организации Azure AD не должны быть предназначены для управления устройствами и пользователями настольных компьютеров Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-165">Intune Device Configuration policies in your Azure AD organization must not target any Microsoft Manage Desktop devices or users.</span></span>

<span data-ttu-id="bb694-166">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-166">**Not ready**</span></span>

<span data-ttu-id="bb694-167">У вас есть по крайней мере одна политика конфигурации, которая нацелена на всех пользователей, все устройства или и то, и другое.</span><span class="sxs-lookup"><span data-stu-id="bb694-167">You have at least one configuration policy that targets all users, all devices, or both.</span></span> <span data-ttu-id="bb694-168">Сбросьте политику, чтобы она была ориентирована на определенную группу Azure AD, которая не включает в себя компьютеры, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-168">Reset the policy to target a specific Azure AD group that does not include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bb694-169">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="bb694-169">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>

<span data-ttu-id="bb694-170">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-170">**Advisory**</span></span>

<span data-ttu-id="bb694-171">Убедитесь, что все политики соответствия требованиям не входят в состав компьютеров, управляемых пользователями.</span><span class="sxs-lookup"><span data-stu-id="bb694-171">Make sure that any compliance policies you have don't include any Microsoft Managed Desktop devices or users.</span></span> <span data-ttu-id="bb694-172">Инструкции по [созданию политики соответствия требованиям в Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span><span class="sxs-lookup"><span data-stu-id="bb694-172">For steps, see [Create a compliance policy in Microsoft Intune](https://docs.microsoft.com/mem/intune/configuration/custom-settings-configure).</span></span>



### <a name="device-type-restrictions"></a><span data-ttu-id="bb694-173">Ограничения на типы устройств</span><span class="sxs-lookup"><span data-stu-id="bb694-173">Device type restrictions</span></span>

<span data-ttu-id="bb694-174">На настольных устройствах, управляемых Майкрософт, должно быть разрешено регистрироваться в Intune.</span><span class="sxs-lookup"><span data-stu-id="bb694-174">Microsoft Managed Desktop devices must be allowed to enroll in Intune.</span></span>

<span data-ttu-id="bb694-175">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-175">**Not ready**</span></span>

<span data-ttu-id="bb694-176">Выполните действия, описанные в статье Set **Reallows** [Set](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) , чтобы изменить значение параметра на Allow.</span><span class="sxs-lookup"><span data-stu-id="bb694-176">Follow the steps in [Set enrollment restrictions](https://docs.microsoft.com/mem/intune/enrollment/enrollment-restrictions-set) to change the setting to **Allow**.</span></span>


### <a name="enrollment-status-page"></a><span data-ttu-id="bb694-177">Страница состояния регистрации</span><span class="sxs-lookup"><span data-stu-id="bb694-177">Enrollment Status Page</span></span>

<span data-ttu-id="bb694-178">В настоящее время включена страница состояния регистрации (ESP).</span><span class="sxs-lookup"><span data-stu-id="bb694-178">You currently have the Enrollment Status Page (ESP) enabled.</span></span> <span data-ttu-id="bb694-179">Если вы участвуете в общедоступной предварительной версии этой функции, вы можете пропустить этот элемент.</span><span class="sxs-lookup"><span data-stu-id="bb694-179">If you are participating in the public preview of this feature, you can ignore this item.</span></span> <span data-ttu-id="bb694-180">Для получения дополнительных сведений обратитесь к разделу [First-Run with автопилот и странице Состояние регистрации](../get-started/esp-first-run.md).</span><span class="sxs-lookup"><span data-stu-id="bb694-180">For more information, see [First-run experience with Autopilot and the Enrollment Status Page](../get-started/esp-first-run.md).</span></span>

<span data-ttu-id="bb694-181">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-181">**Not ready**</span></span>

<span data-ttu-id="bb694-182">Установленный по умолчанию профиль ESP позволяет **Показать ход выполнения настройки приложений и профилей**.</span><span class="sxs-lookup"><span data-stu-id="bb694-182">You have the ESP default profile set to **Show app and profile configuration progress**.</span></span> <span data-ttu-id="bb694-183">Отключите этот параметр, выполнив действия, описанные в разделе [Настройка страницы состояния регистрации](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="bb694-183">Disable this setting by following the steps in [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

<span data-ttu-id="bb694-184">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-184">**Advisory**</span></span>

<span data-ttu-id="bb694-185">Убедитесь, что все профили с параметром " **Показать ход выполнения настройки приложения и профиля** " не назначены какой бы то ни было группе Azure AD, включающей в себя системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-185">Make sure that any profiles that have the **Show app and profile configuration progress** setting are not assigned to any Azure AD group that includes Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bb694-186">Дополнительные сведения можно найти [в разделе Настройка страницы состояния регистрации](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span><span class="sxs-lookup"><span data-stu-id="bb694-186">For more information, see [Set up the Enrollment Status Page](https://docs.microsoft.com/mem/intune/enrollment/windows-enrollment-status).</span></span>

### <a name="intune-enrollment"></a><span data-ttu-id="bb694-187">Регистрация в Intune</span><span class="sxs-lookup"><span data-stu-id="bb694-187">Intune enrollment</span></span>

<span data-ttu-id="bb694-188">Устройства с Windows 10 в Организации Azure AD должны автоматически регистрироваться в Intune.</span><span class="sxs-lookup"><span data-stu-id="bb694-188">Windows 10 devices in your Azure AD organization must be automatically enrolled in Intune.</span></span>

<span data-ttu-id="bb694-189">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-189">**Not ready**</span></span>

<span data-ttu-id="bb694-190">Пользователи в Организации Azure AD не регистрируются в Microsoft Intune автоматически.</span><span class="sxs-lookup"><span data-stu-id="bb694-190">Users in your Azure AD organization aren't automatically enrolled in Microsoft Intune.</span></span> <span data-ttu-id="bb694-191">Замените область пользователя MDM на **некоторые** или **все**.</span><span class="sxs-lookup"><span data-stu-id="bb694-191">Change the MDM User scope to **Some** or **All**.</span></span> <span data-ttu-id="bb694-192">Если вы выбрали.</span><span class="sxs-lookup"><span data-stu-id="bb694-192">If you choose.</span></span> <span data-ttu-id="bb694-193">Некоторые \* \* вернитесь обратно после регистрации и выберите в разделе " **современная Рабочая** область" все группы Azure AD для **групп**.</span><span class="sxs-lookup"><span data-stu-id="bb694-193">Some\*\*, come back after enrollment and select the **Modern Workplace -All** Azure AD group for **Groups**.</span></span>


### <a name="microsoft-store-for-business"></a><span data-ttu-id="bb694-194">Microsoft Store для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bb694-194">Microsoft Store for Business</span></span>

<span data-ttu-id="bb694-195">Мы используем Microsoft Store для бизнеса, чтобы вы могли скачать корпоративный портал, чтобы развернуть некоторые приложения, такие как Microsoft Project и Microsoft Visio.</span><span class="sxs-lookup"><span data-stu-id="bb694-195">We use Microsoft Store for Business so that you can download Company Portal to deploy some apps, such as Microsoft Project and Microsoft Visio.</span></span>

<span data-ttu-id="bb694-196">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-196">**Not ready**</span></span>

<span data-ttu-id="bb694-197">Microsoft Store для бизнеса либо не включен, либо не синхронизирован с Intune.</span><span class="sxs-lookup"><span data-stu-id="bb694-197">Microsoft Store for Business either isn't enabled or isn't synced with Intune.</span></span> <span data-ttu-id="bb694-198">Для получения дополнительных сведений Узнайте, [как управлять корпоративными приобретенными приложениями из Microsoft Store для бизнеса с помощью Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) и [установить портал компании Intune на устройствах](../get-started/company-portal.md).</span><span class="sxs-lookup"><span data-stu-id="bb694-198">For more information, see [How to manage volume purchased apps from the Microsoft Store for Business with Microsoft Intune](https://docs.microsoft.com/mem/intune/apps/windows-store-for-business) and [Install Intune Company Portal on on devices](../get-started/company-portal.md).</span></span>

### <a name="multi-factor-authentication"></a><span data-ttu-id="bb694-199">Многофакторная проверка подлинности</span><span class="sxs-lookup"><span data-stu-id="bb694-199">Multi-factor authentication</span></span>

<span data-ttu-id="bb694-200">Многофакторная проверка подлинности не должна быть случайно применена к управляемым учетным записям служб рабочих столов Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-200">Multi-factor authentication must not accidentally be applied to Microsoft Managed Desktop service accounts.</span></span>


<span data-ttu-id="bb694-201">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-201">**Not ready**</span></span>

<span data-ttu-id="bb694-202">Некоторые политики многофакторной проверки подлинности (MFA) устанавливаются как обязательные для политик условного доступа, назначенных всем пользователям.</span><span class="sxs-lookup"><span data-stu-id="bb694-202">You have some multi-factor authentication (MFA) policies set as "required" for conditional access policies that are assigned to all users.</span></span> <span data-ttu-id="bb694-203">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="bb694-203">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bb694-204">Дополнительные сведения см. в статье [политики условного доступа](#conditional-access-policies) и [Условный доступ: требовать MFA для всех пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="bb694-204">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span>

<span data-ttu-id="bb694-205">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-205">**Advisory**</span></span>

<span data-ttu-id="bb694-206">Убедитесь, что все политики условного доступа, требующие MFA, не включают в себя всю группу Azure AD в **современном рабочем месте** .</span><span class="sxs-lookup"><span data-stu-id="bb694-206">Make sure that any conditional access policies that require MFA exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="bb694-207">Дополнительные сведения см. в статье [политики условного доступа](#conditional-access-policies) и [Условный доступ: требовать MFA для всех пользователей](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span><span class="sxs-lookup"><span data-stu-id="bb694-207">For more information, see [Conditional access policies](#conditional-access-policies) and [Conditional Access: Require MFA for all users](https://docs.microsoft.com/azure/active-directory/conditional-access/howto-conditional-access-policy-all-users-mfa).</span></span> <span data-ttu-id="bb694-208">**Современная Рабочая область — все** группы Azure AD — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="bb694-208">The **Modern Workplace -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>



### <a name="powershell-scripts"></a><span data-ttu-id="bb694-209">Сценарии PowerShell</span><span class="sxs-lookup"><span data-stu-id="bb694-209">PowerShell scripts</span></span>

<span data-ttu-id="bb694-210">Сценарии Windows PowerShell не могут назначаться таким образом, чтобы направлять устройства, управляемые Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-210">Windows PowerShell scripts can't be assigned in a way that would target Microsoft Managed Desktop devices.</span></span>  

<span data-ttu-id="bb694-211">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-211">**Advisory**</span></span>

<span data-ttu-id="bb694-212">Убедитесь, что сценарии Windows PowerShell в Организации Azure AD не предназначены для управления устройствами и пользователями настольных компьютеров корпорации Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-212">Make sure that Windows PowerShell scripts in your Azure AD organization don't target any Microsoft Manage Desktop devices or users.</span></span> <span data-ttu-id="bb694-213">Дополнительные сведения см. в статье [использование скриптов PowerShell для устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span><span class="sxs-lookup"><span data-stu-id="bb694-213">For more information, see [Use PowerShell scripts on Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/apps/intune-management-extension).</span></span>

### <a name="region"></a><span data-ttu-id="bb694-214">Регион</span><span class="sxs-lookup"><span data-stu-id="bb694-214">Region</span></span>

<span data-ttu-id="bb694-215">Ваш регион должен поддерживаться на настольном компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-215">Your region must be supported by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bb694-216">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-216">**Not ready**</span></span>

<span data-ttu-id="bb694-217">В настоящее время область организации Azure AD не поддерживается на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-217">Your Azure AD organization region isn't currently supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bb694-218">Для получения дополнительных [сведений см.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="bb694-218">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>

<span data-ttu-id="bb694-219">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-219">**Advisory**</span></span>

<span data-ttu-id="bb694-220">Одна или несколько стран, в которых находится ваша организация Azure AD, не поддерживаются на компьютере, управляемом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-220">One or more of the countries where your Azure AD organization is located isn't supported by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bb694-221">Для получения дополнительных [сведений см.](../service-description/regions-languages.md)</span><span class="sxs-lookup"><span data-stu-id="bb694-221">For more information, see [Microsoft Managed Desktop supported regions and languages](../service-description/regions-languages.md).</span></span>


### <a name="security-baselines"></a><span data-ttu-id="bb694-222">Базовые показатели безопасности</span><span class="sxs-lookup"><span data-stu-id="bb694-222">Security baselines</span></span>

<span data-ttu-id="bb694-223">Базовые политики безопасности не должны ориентироваться на компьютеры, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-223">Security baseline policies should not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="bb694-224">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-224">**Not ready**</span></span>

<span data-ttu-id="bb694-225">У вас есть базовый профиль безопасности, который предназначен для всех пользователей, всех устройств или и того, и другое.</span><span class="sxs-lookup"><span data-stu-id="bb694-225">You have a security baseline profile that targets all users, all devices or both.</span></span> <span data-ttu-id="bb694-226">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="bb694-226">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bb694-227">В разделе [Использование базовых показателей безопасности для настройки устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="bb694-227">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span>

<span data-ttu-id="bb694-228">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-228">**Advisory**</span></span>

<span data-ttu-id="bb694-229">Убедитесь, что все базовые политики безопасности исключают системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-229">Make sure that any security baseline policies you have exclude Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bb694-230">В разделе [Использование базовых показателей безопасности для настройки устройств с Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span><span class="sxs-lookup"><span data-stu-id="bb694-230">For steps, see [Use security baselines to configure Windows 10 devices in Intune](https://docs.microsoft.com/mem/intune/protect/security-baselines).</span></span> <span data-ttu-id="bb694-231">" **Современные рабочие устройства — все** группы Azure AD" — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="bb694-231">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


### <a name="windows-apps"></a><span data-ttu-id="bb694-232">Приложения для Windows</span><span class="sxs-lookup"><span data-stu-id="bb694-232">Windows apps</span></span>

<span data-ttu-id="bb694-233">Просмотрите приложения, которые должны иметь пользователи, управляемые Майкрософт для настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bb694-233">Review apps you want your Microsoft Managed Desktop users to have.</span></span>

<span data-ttu-id="bb694-234">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-234">**Advisory**</span></span>

<span data-ttu-id="bb694-235">Необходимо подготовить список приложений, которые должны иметь пользователи, управляемые Майкрософт для настольных компьютеров.</span><span class="sxs-lookup"><span data-stu-id="bb694-235">You should prepare an inventory of the apps that you want your Microsoft Managed Desktop users to have.</span></span> <span data-ttu-id="bb694-236">Убедитесь, что эти приложения можно развернуть с помощью Intune.</span><span class="sxs-lookup"><span data-stu-id="bb694-236">Make sure these apps can be deployed by Intune.</span></span> <span data-ttu-id="bb694-237">Дополнительные сведения содержатся [в статье приложения на компьютере, управляемом Майкрософт](apps.md).</span><span class="sxs-lookup"><span data-stu-id="bb694-237">For more information, see [Apps in Microsoft Managed Desktop](apps.md).</span></span>

<span data-ttu-id="bb694-238">Вы можете попросить своего представителя учетной записи Майкрософт выполнить запрос в диспетчере конфигурации конечных точек Майкрософт, чтобы определить, какие приложения готовы для переноса в Intune или нуждаются в корректировке.</span><span class="sxs-lookup"><span data-stu-id="bb694-238">You can ask your Microsoft account representative for a query in Microsoft Endpoint Configuration Manager to identify those apps that are ready to migrate to Intune or need adjustment.</span></span>


### <a name="windows-hello-for-business"></a><span data-ttu-id="bb694-239">Windows Hello для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bb694-239">Windows Hello for Business</span></span>

<span data-ttu-id="bb694-240">Для рабочего стола, управляемого Майкрософт, требуется включить функцию Windows Hello для бизнеса.</span><span class="sxs-lookup"><span data-stu-id="bb694-240">Microsoft Managed Desktop requires Windows Hello for Business to be enabled.</span></span>

<span data-ttu-id="bb694-241">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-241">**Not ready**</span></span>

<span data-ttu-id="bb694-242">Windows Hello для бизнеса отключена.</span><span class="sxs-lookup"><span data-stu-id="bb694-242">Windows Hello for Business is disabled.</span></span> <span data-ttu-id="bb694-243">Включите его, выполнив действия, описанные в разделе [Создание политики Windows Hello для бизнеса](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span><span class="sxs-lookup"><span data-stu-id="bb694-243">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy)</span></span>

<span data-ttu-id="bb694-244">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-244">**Advisory**</span></span>

<span data-ttu-id="bb694-245">Windows Hello для бизнеса не настроена.</span><span class="sxs-lookup"><span data-stu-id="bb694-245">Windows Hello for Business is not set up.</span></span> <span data-ttu-id="bb694-246">Включите его, выполнив действия, описанные в разделе [Создание политики Windows Hello для бизнеса](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span><span class="sxs-lookup"><span data-stu-id="bb694-246">Enable it by following the steps in [Create a Windows Hello for Business policy](https://docs.microsoft.com/mem/intune/protect/windows-hello#create-a-windows-hello-for-business-policy).</span></span>


### <a name="windows-10-update-rings"></a><span data-ttu-id="bb694-247">Звонки обновления Windows 10</span><span class="sxs-lookup"><span data-stu-id="bb694-247">Windows 10 update rings</span></span>

<span data-ttu-id="bb694-248">Политика "Windows 10 Update Ring Ring" в Intune не должна быть нацелена на настольные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-248">Your "Windows 10 update ring" policy in Intune must not target any Microsoft Managed Desktop devices.</span></span>

<span data-ttu-id="bb694-249">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-249">**Not ready**</span></span>

<span data-ttu-id="bb694-250">У вас есть политика "обновление звонка", предназначенная для всех устройств, всех пользователей или и тех, и других.</span><span class="sxs-lookup"><span data-stu-id="bb694-250">You have an "update ring" policy that targets all devices, all users, or both.</span></span> <span data-ttu-id="bb694-251">Измените политику, чтобы она использовала назначение, предназначенное для определенной группы Azure AD, не включающей устройства, управляемые Майкрософт для настольных ПК.</span><span class="sxs-lookup"><span data-stu-id="bb694-251">Change the policy to use an Assignment that targets a specific Azure AD group that doesn't include any Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="bb694-252">Дополнительные сведения: [Управление обновлениями программного обеспечения Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="bb694-252">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span>

<span data-ttu-id="bb694-253">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-253">**Advisory**</span></span>

<span data-ttu-id="bb694-254">Убедитесь, что все политики обновления звонков не исключают всю группу Azure AD в **современном рабочем месте** .</span><span class="sxs-lookup"><span data-stu-id="bb694-254">Make sure that any update ring policies you have exclude the **Modern Workplace -All** Azure AD group.</span></span> <span data-ttu-id="bb694-255">Дополнительные сведения: [Управление обновлениями программного обеспечения Windows 10 в Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span><span class="sxs-lookup"><span data-stu-id="bb694-255">For steps, see [Manage Windows 10 software updates in Intune](https://docs.microsoft.com/mem/intune/protect/windows-update-for-business-configure).</span></span> <span data-ttu-id="bb694-256">" **Современные рабочие устройства — все** группы Azure AD" — это динамическая группа, которая создается при регистрации на настольном компьютере, управляемом Майкрософт, поэтому необходимо вернуться к исключению этой группы после регистрации.</span><span class="sxs-lookup"><span data-stu-id="bb694-256">The **Modern Workplace Devices -All** Azure AD group is a dynamic group that we create when you enroll in Microsoft Managed Desktop, so you'll have to come back to exclude this group after enrollment.</span></span>


## <a name="azure-active-directory-settings"></a><span data-ttu-id="bb694-257">Параметры Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="bb694-257">Azure Active Directory settings</span></span>


### <a name="ad-hoc-subscriptions"></a><span data-ttu-id="bb694-258">Подписки на ad hoc</span><span class="sxs-lookup"><span data-stu-id="bb694-258">Ad hoc subscriptions</span></span>

<span data-ttu-id="bb694-259">Показывает, как проверить, что параметр, для которого задано значение "false"), может препятствовать правильной работе перемещения корпоративных состояний.</span><span class="sxs-lookup"><span data-stu-id="bb694-259">Advises how to check a setting that (if set to "false") might prevent Enterprise State Roaming from working correctly.</span></span>

<span data-ttu-id="bb694-260">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-260">**Advisory**</span></span>

<span data-ttu-id="bb694-261">Убедитесь, что для параметра **алловадхоксубскриптионс** задано **значение true**.</span><span class="sxs-lookup"><span data-stu-id="bb694-261">Ensure that **AllowAdHocSubscriptions** is set to **True**.</span></span> <span data-ttu-id="bb694-262">В противном случае роуминг состояния предприятия может не работать.</span><span class="sxs-lookup"><span data-stu-id="bb694-262">Otherwise, Enterprise State Roaming might not work.</span></span> <span data-ttu-id="bb694-263">Дополнительные сведения см. в статье [Set – мсолкомпанисеттингс](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span><span class="sxs-lookup"><span data-stu-id="bb694-263">For more information, see [Set-MsolCompanySettings](https://docs.microsoft.com/powershell/module/msonline/set-msolcompanysettings?view=azureadps-1.0).</span></span>


### <a name="enterprise-state-roaming"></a><span data-ttu-id="bb694-264">Enterprise State Roaming</span><span class="sxs-lookup"><span data-stu-id="bb694-264">Enterprise State Roaming</span></span>

<span data-ttu-id="bb694-265">Роуминг состояния предприятия должен быть включен.</span><span class="sxs-lookup"><span data-stu-id="bb694-265">Enterprise State Roaming should be enabled.</span></span>

<span data-ttu-id="bb694-266">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-266">**Advisory**</span></span>

<span data-ttu-id="bb694-267">Убедитесь, что роуминг состояния предприятия включен для **всех** или для **выбранных** групп.</span><span class="sxs-lookup"><span data-stu-id="bb694-267">Make sure that Enterprise State Roaming is enabled for **All** or for **Selected** groups.</span></span> <span data-ttu-id="bb694-268">Дополнительные сведения см в статье [Enable Enterprise State роуминг в Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span><span class="sxs-lookup"><span data-stu-id="bb694-268">For more information, see [Enable Enterprise State Roaming in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/devices/enterprise-state-roaming-enable).</span></span>

### <a name="licenses"></a><span data-ttu-id="bb694-269">Лицензии</span><span class="sxs-lookup"><span data-stu-id="bb694-269">Licenses</span></span>

<span data-ttu-id="bb694-270">Для использования настольного компьютера, управляемого Майкрософт, требуется несколько лицензий.</span><span class="sxs-lookup"><span data-stu-id="bb694-270">A number of licenses are required to use Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bb694-271">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-271">**Not Ready**</span></span>

<span data-ttu-id="bb694-272">У вас нет лицензий, необходимых для использования компьютера, управляемого корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-272">You don't have all the licenses you need to use Microsoft Managed Desktop.</span></span> <span data-ttu-id="bb694-273">Дополнительные сведения можно найти в [статье управляемые технологии для настольных ПК Майкрософт](../intro/technologies.md) и [Дополнительные сведения о лицензиях](prerequisites.md#more-about-licenses).</span><span class="sxs-lookup"><span data-stu-id="bb694-273">For more information, see [Microsoft Managed Desktop technologies](../intro/technologies.md) and [More about licenses](prerequisites.md#more-about-licenses).</span></span>


### <a name="security-account-names"></a><span data-ttu-id="bb694-274">Имена учетных записей безопасности</span><span class="sxs-lookup"><span data-stu-id="bb694-274">Security account names</span></span>

<span data-ttu-id="bb694-275">Некоторые имена учетных записей безопасности могут конфликтовать с настольными компьютерами, созданными корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-275">Certain security account names could conflict with ones created by Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bb694-276">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-276">**Not ready**</span></span>

<span data-ttu-id="bb694-277">У вас есть по крайней мере одно имя учетной записи, которое будет конфликтовать с рабочим столом, созданным корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-277">You have at least one account name that will conflict with ones created by Microsoft Managed Desktop.</span></span> <span data-ttu-id="bb694-278">Работайте с представителем учетной записи Майкрософт, чтобы исключить эти имена учетных записей.</span><span class="sxs-lookup"><span data-stu-id="bb694-278">Work with your Microsoft account representative to exclude these account names.</span></span>


### <a name="security-administrator-roles"></a><span data-ttu-id="bb694-279">Роли администраторов безопасности</span><span class="sxs-lookup"><span data-stu-id="bb694-279">Security administrator roles</span></span>

<span data-ttu-id="bb694-280">Пользователям с определенными ролями безопасности должны быть назначены в защитнике Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bb694-280">Users with certain security roles must have those assigned in Microsoft Defender for Endpoint.</span></span>

<span data-ttu-id="bb694-281">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-281">**Advisory**</span></span>

<span data-ttu-id="bb694-282">Если в вашей организации Azure AD назначена любая из этих ролей, убедитесь, что они также назначены в защитнике Майкрософт для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="bb694-282">If you have any of these roles assigned in your Azure AD organization, make sure they also have these roles assigned in Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="bb694-283">В противном случае администраторы с этими ролями не смогут получить доступ к порталу администрирования.</span><span class="sxs-lookup"><span data-stu-id="bb694-283">Otherwise, administrators with these roles won't be able to access the Admin portal.</span></span>

- <span data-ttu-id="bb694-284">Читатель сведений о безопасности</span><span class="sxs-lookup"><span data-stu-id="bb694-284">Security Reader</span></span>
- <span data-ttu-id="bb694-285">Оператор безопасности</span><span class="sxs-lookup"><span data-stu-id="bb694-285">Security Operator</span></span>
- <span data-ttu-id="bb694-286">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="bb694-286">Global Reader</span></span>

<span data-ttu-id="bb694-287">Дополнительные сведения см. в статье [Создание ролей и управление ими для управления доступом на основе ролей](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span><span class="sxs-lookup"><span data-stu-id="bb694-287">For more information, see [Create and manage roles for role-based access control](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/user-roles).</span></span>


### <a name="security-default"></a><span data-ttu-id="bb694-288">По умолчанию для безопасности</span><span class="sxs-lookup"><span data-stu-id="bb694-288">Security default</span></span>

<span data-ttu-id="bb694-289">Параметры безопасности по умолчанию в Azure Active Directory не допускают управления устройствами с помощью Microsoft Managed Desktop.</span><span class="sxs-lookup"><span data-stu-id="bb694-289">Security defaults in Azure Active Directory will prevent Microsoft Managed Desktop from managing your devices.</span></span>

<span data-ttu-id="bb694-290">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-290">**Not ready**</span></span>

<span data-ttu-id="bb694-291">Параметры безопасности по умолчанию включены.</span><span class="sxs-lookup"><span data-stu-id="bb694-291">You have Security defaults turned on.</span></span> <span data-ttu-id="bb694-292">Отключите параметры безопасности по умолчанию и настройте политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="bb694-292">Turn off Security defaults and set up conditional access policies.</span></span> <span data-ttu-id="bb694-293">Более подробную информацию можно узнать в статье [Общие политики условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span><span class="sxs-lookup"><span data-stu-id="bb694-293">For more information, see [Common Conditional Access policies](https://docs.microsoft.com/azure/active-directory/conditional-access/concept-conditional-access-policy-common).</span></span>

### <a name="self-service-password-reset"></a><span data-ttu-id="bb694-294">Самостоятельный сброс пароля</span><span class="sxs-lookup"><span data-stu-id="bb694-294">Self-service Password Reset</span></span>

<span data-ttu-id="bb694-295">Необходимо включить функцию самостоятельного сброса паролей (SSPR).</span><span class="sxs-lookup"><span data-stu-id="bb694-295">Self-service Password Reset (SSPR) must be enabled.</span></span>

<span data-ttu-id="bb694-296">**Не готов**</span><span class="sxs-lookup"><span data-stu-id="bb694-296">**Not ready**</span></span>

<span data-ttu-id="bb694-297">SSPR должен быть включен для всех пользователей.</span><span class="sxs-lookup"><span data-stu-id="bb694-297">SSPR must be enabled for all users.</span></span> <span data-ttu-id="bb694-298">В противном случае учетные записи службы для рабочих столов, управляемой Майкрософт, работать не могут.</span><span class="sxs-lookup"><span data-stu-id="bb694-298">If it isn't, the Microsoft Managed Desktop service accounts can't work.</span></span> <span data-ttu-id="bb694-299">Дополнительные сведения см. [в разделе Tutorial: разрешить пользователям разблокировать свою учетную запись или сбросить пароли с помощью функции самообслуживания Azure Active Directory для самостоятельного сброса пароля](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span><span class="sxs-lookup"><span data-stu-id="bb694-299">For more information, see [Tutorial: Enable users to unlock their account or reset passwords using Azure Active Directory self-service password reset](https://docs.microsoft.com/azure/active-directory/authentication/tutorial-enable-sspr).</span></span>

<span data-ttu-id="bb694-300">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-300">**Advisory**</span></span>

<span data-ttu-id="bb694-301">Убедитесь, что **выбранный** параметр SSPR включает в себя системные устройства, управляемые корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-301">Make sure that the SSPR **Selected** setting includes Microsoft Managed Desktop devices.</span></span>

### <a name="standard-user-role"></a><span data-ttu-id="bb694-302">Роль обычного пользователя</span><span class="sxs-lookup"><span data-stu-id="bb694-302">Standard user role</span></span>

<span data-ttu-id="bb694-303">Пользователи настольного компьютера, управляемые корпорацией Майкрософт, должны быть стандартными пользователями без прав локального администратора.</span><span class="sxs-lookup"><span data-stu-id="bb694-303">Microsoft Managed Desktop users should be standard users without local administrator privileges.</span></span> <span data-ttu-id="bb694-304">При запуске настольного компьютера, управляемого Майкрософт, им будет назначена роль стандартного пользователя.</span><span class="sxs-lookup"><span data-stu-id="bb694-304">They'll be assigned a standard user role when they start their Microsoft Managed Desktop device.</span></span>

<span data-ttu-id="bb694-305">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-305">**Advisory**</span></span>

<span data-ttu-id="bb694-306">Пользователи настольных систем, управляемых Майкрософт, не должны иметь права локального администратора перед регистрацией.</span><span class="sxs-lookup"><span data-stu-id="bb694-306">Microsoft Managed Desktop users shouldn't have local administrator privileges prior to enrolling.</span></span>

## <a name="microsoft-365-apps-for-enterprise"></a><span data-ttu-id="bb694-307">Приложения Microsoft 365 для предприятий</span><span class="sxs-lookup"><span data-stu-id="bb694-307">Microsoft 365 Apps for enterprise</span></span>

### <a name="onedrive-for-business"></a><span data-ttu-id="bb694-308">OneDrive для бизнеса</span><span class="sxs-lookup"><span data-stu-id="bb694-308">OneDrive for Business</span></span>

<span data-ttu-id="bb694-309">Параметр **Разрешить синхронизацию только на компьютерах, присоединенных к определенным доменам** , будет конфликтовать с управляемым рабочим столом Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-309">The **Allow syncing only on PCs joined to specific domains** setting will conflict with Microsoft Managed Desktop.</span></span>

<span data-ttu-id="bb694-310">**Рекомендация**</span><span class="sxs-lookup"><span data-stu-id="bb694-310">**Advisory**</span></span>

<span data-ttu-id="bb694-311">Вы используете параметр **Разрешить синхронизацию только на компьютерах, присоединенных к определенным доменам** .</span><span class="sxs-lookup"><span data-stu-id="bb694-311">You're using the **Allow syncing only on PCs joined to specific domains** setting.</span></span> <span data-ttu-id="bb694-312">Этот параметр не будет работать с настольным компьютером, управляемым Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="bb694-312">This setting won't work with Microsoft Managed Desktop.</span></span> <span data-ttu-id="bb694-313">Отключите этот параметр, а затем настройте OneDrive для бизнеса для использования политики условного доступа.</span><span class="sxs-lookup"><span data-stu-id="bb694-313">Disable this setting, and instead set up OneDrive for Business to use a conditional access policy.</span></span> <span data-ttu-id="bb694-314">Ознакомьтесь с разкрывающимся [планом развертывания условного доступа](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) для получения справки.</span><span class="sxs-lookup"><span data-stu-id="bb694-314">See [Plan a Conditional Access deployment](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access) for help.</span></span>

