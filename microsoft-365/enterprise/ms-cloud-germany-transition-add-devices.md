---
title: Дополнительные сведения об устройстве для миграции из Microsoft Cloud Deutschland
ms.author: andyber
author: andybergen
manager: laurawi
ms.date: 12/01/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- CSH
ms.custom:
- Ent_TLGs
description: Сводка. Дополнительные сведения об службах устройств при переходе из Microsoft Cloud Germany (Microsoft Cloud Deutschland) в Office 365 службы в новом немецком регионе центра обработки данных.
ms.openlocfilehash: 684af01b2d90f44b2cda1cf050d1e4db70f92915
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/03/2021
ms.locfileid: "53289443"
---
# <a name="additional-device-information-for-the-migration-from-microsoft-cloud-deutschland"></a><span data-ttu-id="73ad2-103">Дополнительные сведения об устройстве для миграции из Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="73ad2-103">Additional device information for the migration from Microsoft Cloud Deutschland</span></span>

<span data-ttu-id="73ad2-104">Подключенные и зарегистрированные устройства Azure AD, подключенные к Microsoft Cloud Deutschland, должны быть перенесены после 9-го этапа и до 10-го этапа.</span><span class="sxs-lookup"><span data-stu-id="73ad2-104">Azure AD joined and registered devices connected to Microsoft Cloud Deutschland must be migrated after phase 9 and before phase 10.</span></span> <span data-ttu-id="73ad2-105">Миграция устройства зависит от типа устройств, операционной системы и отношения Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73ad2-105">The migration of a device depends on the devices type, operating system and Azure AD relation.</span></span>

## <a name="azure-ad-joined-windows-10-devices"></a><span data-ttu-id="73ad2-106">Устройства Azure AD Windows 10</span><span class="sxs-lookup"><span data-stu-id="73ad2-106">Azure AD Joined Windows 10 devices</span></span>
<span data-ttu-id="73ad2-107">Если Windows 10 подключено Azure AD, оно должно быть отключено от Azure AD и должно быть подключено снова.</span><span class="sxs-lookup"><span data-stu-id="73ad2-107">If a Windows 10 device is Azure AD joined, it must be disconnected from Azure AD and must be connected again.</span></span>

<span data-ttu-id="73ad2-108">[![Устройство Azure AD ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="73ad2-108">[ ![Azure AD Device Re-Join Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>


<span data-ttu-id="73ad2-109">Если пользователь является администратором на устройстве Windows 10, пользователь может оторегистрить устройство из Azure AD и повторно присоединиться к нему в течение трех шагов.</span><span class="sxs-lookup"><span data-stu-id="73ad2-109">If the user is an administrator on the Windows 10 device, the user can unregister the device from Azure AD and re-join it again in three steps.</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-joined"></a><span data-ttu-id="73ad2-110">Шаг 1. Определите, присоединилось ли устройство к Azure ID</span><span class="sxs-lookup"><span data-stu-id="73ad2-110">Step 1: Determine if the device is Azure ID joined</span></span>

1. <span data-ttu-id="73ad2-111">Войдите в службу с помощью рабочей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="73ad2-111">Sign in with your work account.</span></span>
2. <span data-ttu-id="73ad2-112">Перейдите **в Параметры**  >  **Учетные**  >  **записи Доступ к работе или школе**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-112">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="73ad2-113">Найми учетную запись в списке с **подключением к [...]' s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-113">Look for an account in the list with **connected to […]‘s Azure AD**.</span></span>
4. <span data-ttu-id="73ad2-114">Если подключенная учетная запись существует, приступить к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="73ad2-114">If a connected account exists, proceed with Step 2.</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="73ad2-115">Шаг 2. Отключение устройства от Azure AD</span><span class="sxs-lookup"><span data-stu-id="73ad2-115">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="73ad2-116">Щелкните **Отключение** на подключенной работе или учетной записи школы.</span><span class="sxs-lookup"><span data-stu-id="73ad2-116">Click **Disconnect** on the connected work or School Account.</span></span>
2. <span data-ttu-id="73ad2-117">Дважды подтвердите отключение.</span><span class="sxs-lookup"><span data-stu-id="73ad2-117">Confirm the disconnect twice.</span></span>
3. <span data-ttu-id="73ad2-118">Введите имя пользователя и пароль местного администратора.</span><span class="sxs-lookup"><span data-stu-id="73ad2-118">Enter a local administrator username and password.</span></span> <span data-ttu-id="73ad2-119">Устройство отключено.</span><span class="sxs-lookup"><span data-stu-id="73ad2-119">The device is disconnected.</span></span>
4. <span data-ttu-id="73ad2-120">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="73ad2-120">Restart the device.</span></span>

### <a name="step-3-join-the-device-to-azure-ad"></a><span data-ttu-id="73ad2-121">Шаг 3. Присоединиться к устройству в Azure AD</span><span class="sxs-lookup"><span data-stu-id="73ad2-121">Step 3: Join the device to Azure AD</span></span>

1. <span data-ttu-id="73ad2-122">Вопишитесь с учетными данными местного администратора.</span><span class="sxs-lookup"><span data-stu-id="73ad2-122">Sign in with the credentials of the local administrator.</span></span>
2. <span data-ttu-id="73ad2-123">Перейдите **в Параметры**  >  **Учетные**  >  **записи Доступ к работе или школе**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-123">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="73ad2-124">Нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-124">Click **Connect**.</span></span>
4. <span data-ttu-id="73ad2-125">**ВАЖНО:** **Нажмите кнопку Присоединиться к Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-125">**IMPORTANT**: Click **Join to Azure AD**.</span></span>
5. <span data-ttu-id="73ad2-126">Введите адрес электронной почты и пароль вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="73ad2-126">Enter the e-mail address and password of your work account.</span></span> <span data-ttu-id="73ad2-127">Устройство подключено.</span><span class="sxs-lookup"><span data-stu-id="73ad2-127">The device is connected.</span></span>
6. <span data-ttu-id="73ad2-128">Перезапустите устройство.</span><span class="sxs-lookup"><span data-stu-id="73ad2-128">Restart the device.</span></span>
7. <span data-ttu-id="73ad2-129">Войте вход с адресом электронной почты и паролем вашей учетной записи.</span><span class="sxs-lookup"><span data-stu-id="73ad2-129">Sign in with the email address and password of your work account.</span></span>

<span data-ttu-id="73ad2-130">Если пользователь не является администратором устройства, глобальный администратор Azure AD может создать учетную запись локального администратора на устройстве по этому пути настройки и отсоединить устройство:</span><span class="sxs-lookup"><span data-stu-id="73ad2-130">If the user is not an administrator of the device, an Azure AD global administrator can create the local administrator account on the device following this configuration path and unjoin the device:</span></span>

<span data-ttu-id="73ad2-131">*Параметры > учетные записи > другие учетные записи > учетные данные неизвестные > Добавить пользователя без Microsoft-Account*</span><span class="sxs-lookup"><span data-stu-id="73ad2-131">*Settings > Accounts > Other Accounts > Credentials unknown > Add user without Microsoft-Account*</span></span>

<span data-ttu-id="73ad2-132">Для повторного присоединения на этом шаге можно использовать учетные данные любой учетной записи вашей организации.</span><span class="sxs-lookup"><span data-stu-id="73ad2-132">For re-joining, the credentials of any work account from your organization can be used in this step.</span></span>

<span data-ttu-id="73ad2-133">Обратите внимание на то, что учетная запись, используемая для работы с устройством, будет автоматически повышена в качестве администратора устройства.</span><span class="sxs-lookup"><span data-stu-id="73ad2-133">Please consider that the work account used to join the device will be automatically promoted as an Administrator of the device.</span></span>
<span data-ttu-id="73ad2-134">Любая другая учетная запись в организации может войти на устройство, но не имеет прав администратора.</span><span class="sxs-lookup"><span data-stu-id="73ad2-134">Any other work account from the organization can sign in to the device, but has no administrator privileges.</span></span>

## <a name="azure-ad-registered-workplace-joined-windows-10-devices"></a><span data-ttu-id="73ad2-135">Зарегистрированные устройства Azure AD (с Windows 10 рабочими устройствами)</span><span class="sxs-lookup"><span data-stu-id="73ad2-135">Azure AD registered (workplace-joined) Windows 10 devices</span></span>

<span data-ttu-id="73ad2-136">Если Windows 10 зарегистрирован Azure AD, его необходимо отключить от Azure AD и снова подключать.</span><span class="sxs-lookup"><span data-stu-id="73ad2-136">If a Windows 10 device is Azure AD registered, it needs to be disconnected from the Azure AD and connected again.</span></span>

<span data-ttu-id="73ad2-137">[![Устройство Azure AD ](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) Re-Registration Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="73ad2-137">[ ![Azure AD Device Re-Registration Flow](../media/ms-cloud-germany-migration-opt-in/AAD-ReRegistration-flow.png) ](../media/ms-cloud-germany-migration-opt-in/AAD-ReJoin-flow.png#lightbox)</span></span>

### <a name="step-1-determine-if-the-device-is-azure-id-registered"></a><span data-ttu-id="73ad2-138">Шаг 1. Определите, зарегистрировано ли устройство в Azure ID</span><span class="sxs-lookup"><span data-stu-id="73ad2-138">Step 1: Determine if the device is Azure ID registered</span></span>

1. <span data-ttu-id="73ad2-139">Вход с пользователем.</span><span class="sxs-lookup"><span data-stu-id="73ad2-139">Sign in with your user.</span></span>
2. <span data-ttu-id="73ad2-140">Перейдите **в Параметры**  >  **Учетные**  >  **записи Доступ к работе или школе**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-140">Go to **Settings** > **Accounts** > **Access Work Or School**.</span></span>
3. <span data-ttu-id="73ad2-141">Откройте свою учетную запись в списке и проверьте, подключена ли она **к [...]» s Azure AD**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-141">Discover your work account in the list and check if it is **connected to […]‘s Azure AD**.</span></span>

    <span data-ttu-id="73ad2-142">Если ваша учетная запись находится в списке, но не подключена к Azure AD, приступить к шагу 2.</span><span class="sxs-lookup"><span data-stu-id="73ad2-142">If your work account is in the list but NOT connected to an Azure AD, proceed with step 2.</span></span>

    <span data-ttu-id="73ad2-143">В противном случае устройство является устройством, присоединимой к Azure AD, и вам необходимо обратиться к устройствам [Azure AD Windows 10.](#azure-ad-joined-windows-10-devices)</span><span class="sxs-lookup"><span data-stu-id="73ad2-143">Otherwise, your device is an Azure AD joined device and you have to refer to [Azure AD Joined Windows 10 devices](#azure-ad-joined-windows-10-devices).</span></span>

### <a name="step-2-disconnect-the-device-from-azure-ad"></a><span data-ttu-id="73ad2-144">Шаг 2. Отключение устройства от Azure AD</span><span class="sxs-lookup"><span data-stu-id="73ad2-144">Step 2: Disconnect the device from Azure AD</span></span>

1. <span data-ttu-id="73ad2-145">Щелкните свою учетную запись.</span><span class="sxs-lookup"><span data-stu-id="73ad2-145">Click on your work account.</span></span> <span data-ttu-id="73ad2-146">Отображаются кнопки *Info* и *Disconnect.*</span><span class="sxs-lookup"><span data-stu-id="73ad2-146">The buttons *Info* and *Disconnect* appear.</span></span>
2. <span data-ttu-id="73ad2-147">Щелкните **Отключение**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-147">Click **Disconnect**.</span></span>
3. <span data-ttu-id="73ad2-148">Подтверждение удаления учетной записи с устройства, нажав **кнопку Да**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-148">Confirm account removal from the device by clicking **Yes**.</span></span>

### <a name="step-3-connect-the-device-to-azure-ad"></a><span data-ttu-id="73ad2-149">Шаг 3. Подключение устройство в Azure AD</span><span class="sxs-lookup"><span data-stu-id="73ad2-149">Step 3: Connect the device to Azure AD</span></span>

1. <span data-ttu-id="73ad2-150">Нажмите кнопку **Подключить**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-150">Click **Connect**.</span></span>
2. <span data-ttu-id="73ad2-151">Введите адрес электронной почты вашей учетной записи и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-151">Enter the email address of your work account and click **Next**.</span></span>
3. <span data-ttu-id="73ad2-152">Введите пароль вашей учетной записи и нажмите **кнопку Вход**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-152">Enter the password of your work account and click **Sign in**.</span></span>
4. <span data-ttu-id="73ad2-153">Подтвердив, нажав **кнопку Готово**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-153">Confirm by clicking **Done**.</span></span> <span data-ttu-id="73ad2-154">Ваша учетная запись снова указана.</span><span class="sxs-lookup"><span data-stu-id="73ad2-154">Your work account is listed again.</span></span>

## <a name="android"></a><span data-ttu-id="73ad2-155">Android</span><span class="sxs-lookup"><span data-stu-id="73ad2-155">Android</span></span>

<span data-ttu-id="73ad2-156">Для Android пользователям потребуется оторегистрируйте и перерегистрируйте свои устройства.</span><span class="sxs-lookup"><span data-stu-id="73ad2-156">For Android, users will need to unregister and re-register their devices.</span></span> <span data-ttu-id="73ad2-157">Это можно сделать с помощью Microsoft Authenticator или Корпоративный портал приложения.</span><span class="sxs-lookup"><span data-stu-id="73ad2-157">This can be done via the Microsoft Authenticator app or the Company Portal app.</span></span>

- <span data-ttu-id="73ad2-158">В приложении Microsoft Authenticator пользователи могут перейти к Параметры > **регистрации устройств.**</span><span class="sxs-lookup"><span data-stu-id="73ad2-158">From the Microsoft Authenticator app, users can go to **Settings > Device Registration**.</span></span> <span data-ttu-id="73ad2-159">Оттуда пользователи могут отрегистрируйте и перерегистрируйте свое устройство.</span><span class="sxs-lookup"><span data-stu-id="73ad2-159">From there users can unregister and re-register their device.</span></span>

- <span data-ttu-id="73ad2-160">С Корпоративный портал пользователи могут перейти на вкладку **Devices** и удалить устройство.</span><span class="sxs-lookup"><span data-stu-id="73ad2-160">From the Company Portal, users can go to **Devices** tab and remove the device.</span></span> <span data-ttu-id="73ad2-161">После этого повторно зарегистрив устройство с помощью Корпоративный портал.</span><span class="sxs-lookup"><span data-stu-id="73ad2-161">After that, re-enroll the device by using Company Portal.</span></span>

- <span data-ttu-id="73ad2-162">Пользователи также могут отрегистрируйтесь и перерегистрируйтесь, удалив учетную запись со страницы параметров учетной записи, а затем повторно добавив учетную запись.</span><span class="sxs-lookup"><span data-stu-id="73ad2-162">Users can also unregister and re-register by removing the account from the account settings page and then re-adding the work account.</span></span>

<span data-ttu-id="73ad2-163">Для регистрации и перерегистрации устройства на Android с помощью Microsoft Authenticator приложения:</span><span class="sxs-lookup"><span data-stu-id="73ad2-163">To unregister and re-register the device on Android by using the Microsoft Authenticator app:</span></span>

1. <span data-ttu-id="73ad2-164">Откройте приложение Microsoft Authenticator и перейдите **в Параметры**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-164">Open the Microsoft Authenticator app and go to **Settings**.</span></span>
2. <span data-ttu-id="73ad2-165">Выберите **регистрацию устройства.**</span><span class="sxs-lookup"><span data-stu-id="73ad2-165">Select **Device registration**.</span></span>
3. <span data-ttu-id="73ad2-166">Незарегистрированное устройство, выбрав **Unregister**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-166">Unregister the device by selecting **Unregister**.</span></span>
4. <span data-ttu-id="73ad2-167">Для **регистрации устройства** перерегистрируйте устройство, введя адрес электронной почты, а затем выберите **Register**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-167">For **Device registration**, re-register the device by typing your email address, and then select **Register**.</span></span>

<span data-ttu-id="73ad2-168">Для регистрации и перерегистрации устройства Android на странице Android Параметры:</span><span class="sxs-lookup"><span data-stu-id="73ad2-168">To unregister and re-register an Android device with the Android Settings page:</span></span>

1. <span data-ttu-id="73ad2-169">Откройте **устройство Параметры** и перейдите к **учетным записям.**</span><span class="sxs-lookup"><span data-stu-id="73ad2-169">Open **Device Settings** and go to **Accounts**.</span></span>
2. <span data-ttu-id="73ad2-170">Выберите учетную запись работы, которую необходимо перерегистрируйте, и выберите **учетную запись Remove.**</span><span class="sxs-lookup"><span data-stu-id="73ad2-170">Select the work account that you want to re-register and select **Remove account**.</span></span>
3. <span data-ttu-id="73ad2-171">После удаления учетной записи со страницы **Учетные** записи выберите учетную запись **Add Account > work account.**</span><span class="sxs-lookup"><span data-stu-id="73ad2-171">After the account is removed, from the **Accounts** page, select **Add Account > Work account**.</span></span>
4. <span data-ttu-id="73ad2-172">Для **workplace Join** введите адрес электронной почты и выберите **Присоединиться,** чтобы завершить регистрацию устройства.</span><span class="sxs-lookup"><span data-stu-id="73ad2-172">For **Workplace Join**, type your email address and select **Join** to complete registering the device.</span></span>

<span data-ttu-id="73ad2-173">Для регистрации и перерегистрации устройства на Android с Корпоративный портал:</span><span class="sxs-lookup"><span data-stu-id="73ad2-173">To unregister and re-register the device on Android from Company Portal:</span></span>

1. <span data-ttu-id="73ad2-174">Запустите Корпоративный портал и перейдите на **вкладку Devices.**</span><span class="sxs-lookup"><span data-stu-id="73ad2-174">Launch Company Portal and go to **Devices** tab.</span></span>
2. <span data-ttu-id="73ad2-175">Выберите устройство, чтобы увидеть сведения об устройстве.</span><span class="sxs-lookup"><span data-stu-id="73ad2-175">Select the device to see the device details.</span></span>
3. <span data-ttu-id="73ad2-176">Из меню эллипсов (три точки) выберите **Remove Device** и выполните удаление, подтвердив в диалоговом окантовке.</span><span class="sxs-lookup"><span data-stu-id="73ad2-176">From the ellipses (three dots) menu, select **Remove Device**, and complete the removal by confirming in the dialog.</span></span>
4. <span data-ttu-id="73ad2-177">Теперь вы должны войти в систему из Корпоративный портал приложения.</span><span class="sxs-lookup"><span data-stu-id="73ad2-177">You should now be logged out of the Company Portal app.</span></span> <span data-ttu-id="73ad2-178">Выберите **вход для** повторной регистрации устройства.</span><span class="sxs-lookup"><span data-stu-id="73ad2-178">Select **Sign in** to re-register the device.</span></span>

<span data-ttu-id="73ad2-179">Дополнительные сведения о любых действиях, необходимых на этапе миграции этой рабочей нагрузки или воздействии на администрирование или использование, см. в Azure Active Directory (Azure AD) в дополнительных сведениях Azure AD для миграции из [Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span><span class="sxs-lookup"><span data-stu-id="73ad2-179">For more information about any actions required during the migration phase of this workload, or impact to administration or usage, review the information about Azure Active Directory (Azure AD) in [Additional Azure AD information for the migration from Microsoft Cloud Deutschland](ms-cloud-germany-transition-azure-ad.md).</span></span>

## <a name="ios"></a><span data-ttu-id="73ad2-180">iOS</span><span class="sxs-lookup"><span data-stu-id="73ad2-180">iOS</span></span>

<span data-ttu-id="73ad2-181">На устройствах iOS пользователю необходимо вручную удалить все кэшированные учетные записи из Microsoft Authenticator, отрегистрить устройство и выйти из любых родных приложений на устройстве.</span><span class="sxs-lookup"><span data-stu-id="73ad2-181">On iOS devices, a user will need to manually remove any cached accounts from the Microsoft Authenticator, unregister the device, and sign out from any native apps on the device.</span></span>

### <a name="step-1-if-present-remove-the-account-from-the-microsoft-authenticator-app"></a><span data-ttu-id="73ad2-182">Шаг 1. Если она присутствует, удалите учетную запись из Microsoft Authenticator приложения</span><span class="sxs-lookup"><span data-stu-id="73ad2-182">Step 1: If present, remove the account from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="73ad2-183">Нажмите на учетную запись в Microsoft Authenticator приложении.</span><span class="sxs-lookup"><span data-stu-id="73ad2-183">Tap the account in the Microsoft Authenticator app.</span></span>
2. <span data-ttu-id="73ad2-184">Нажмите **значок Параметры** в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="73ad2-184">Tap the **Settings** icon in the top-right corner.</span></span> <span data-ttu-id="73ad2-185">Если вы не видите значок **Параметры,** возможно, вы не используете последнюю версию Microsoft Authenticator.</span><span class="sxs-lookup"><span data-stu-id="73ad2-185">If you don't see the **Settings** icon, you might not be using the latest version of Microsoft Authenticator.</span></span>
3. <span data-ttu-id="73ad2-186">Нажмите **кнопку Удалить учетную запись.**</span><span class="sxs-lookup"><span data-stu-id="73ad2-186">Tap the **Remove account** button.</span></span>
4. <span data-ttu-id="73ad2-187">Нажмите **кнопку Все приложения на этом устройстве**.</span><span class="sxs-lookup"><span data-stu-id="73ad2-187">Tap **All apps on this device**.</span></span>

### <a name="step-2-unregister-the-device-from-the-microsoft-authenticator-app"></a><span data-ttu-id="73ad2-188">Шаг 2. Незарегистрированное устройство из Microsoft Authenticator приложения</span><span class="sxs-lookup"><span data-stu-id="73ad2-188">Step 2: Unregister the device from the Microsoft Authenticator app</span></span>

1. <span data-ttu-id="73ad2-189">Нажмите значок меню в правом верхнем углу.</span><span class="sxs-lookup"><span data-stu-id="73ad2-189">Tap the menu icon in the top-right corner.</span></span>
2. <span data-ttu-id="73ad2-190">Нажмите **кнопку Параметры,** а затем **регистрация устройств.**</span><span class="sxs-lookup"><span data-stu-id="73ad2-190">Tap **Settings** and then **Device Registration**.</span></span>
3. <span data-ttu-id="73ad2-191">Если учетная запись отображается, нажмите **кнопку Незарегистрированное устройство** **и продолжайте** в диалоговом окте.</span><span class="sxs-lookup"><span data-stu-id="73ad2-191">If your account is shown, tap **Unregister device** and **Continue** in the dialog.</span></span> <span data-ttu-id="73ad2-192">После этого вы не должны видеть учетную запись.</span><span class="sxs-lookup"><span data-stu-id="73ad2-192">You should see no account after that.</span></span>

### <a name="step-3-sign-out-from-individual-apps-if-necessary"></a><span data-ttu-id="73ad2-193">Шаг 3. При необходимости выпишитесь из отдельных приложений</span><span class="sxs-lookup"><span data-stu-id="73ad2-193">Step 3: Sign out from individual apps if necessary</span></span>

<span data-ttu-id="73ad2-194">Пользователи могут перейти к отдельным приложениям, Outlook, Teams и OneDrive, а также удалить учетные записи из этих приложений.</span><span class="sxs-lookup"><span data-stu-id="73ad2-194">Users can go to individual apps like Outlook, Teams, and OneDrive, and remove accounts from those apps.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="73ad2-195">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="73ad2-195">Frequently asked questions</span></span>

<span data-ttu-id="73ad2-196">**Как узнать, затронута ли моя организация?**</span><span class="sxs-lookup"><span data-stu-id="73ad2-196">**How can I tell if my organization is affected?**</span></span>

<span data-ttu-id="73ad2-197">Администраторы должны проверить, есть ли у них зарегистрированные `https://portal.microsoftazure.de` устройства Azure AD или Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73ad2-197">Administrators should check `https://portal.microsoftazure.de` to determine if they have any Azure AD registered or Azure AD joined devices.</span></span> <span data-ttu-id="73ad2-198">Если в вашей организации зарегистрированы устройства Azure AD или к Azure AD присоединились, организация должна следовать инструкциям на этой странице.</span><span class="sxs-lookup"><span data-stu-id="73ad2-198">If your organization has Azure AD registered or Azure AD joined devices, your organization has to follow the instructions on this page.</span></span>

<span data-ttu-id="73ad2-199">**Когда пользователи перерегистрируют свои устройства?**</span><span class="sxs-lookup"><span data-stu-id="73ad2-199">**When do my users re-register their devices?**</span></span>

<span data-ttu-id="73ad2-200">Важно, чтобы после завершения [9-го](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) этапа вы регистрируете и перерегистрируете устройства.</span><span class="sxs-lookup"><span data-stu-id="73ad2-200">It's critical to your success that you only unregister and re-register your devices after [phase 9](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization) has been completed.</span></span> <span data-ttu-id="73ad2-201">Перед началом 10-го этапа необходимо завершить перерегистрацию, в противном случае вы можете потерять доступ к устройству.</span><span class="sxs-lookup"><span data-stu-id="73ad2-201">You must finish the re-registration before phase 10 starts, otherwise you could lose access to your device.</span></span>

<span data-ttu-id="73ad2-202">**Как узнать, что все мои устройства зарегистрированы в общедоступных облаках?**</span><span class="sxs-lookup"><span data-stu-id="73ad2-202">**How do I know that all my devices are registered in the public cloud?**</span></span>

<span data-ttu-id="73ad2-203">Чтобы проверить, зарегистрированы ли устройства в общеобязуемом облаке, необходимо экспортировать и загружать список устройств с портала Azure AD в Excel таблицу.</span><span class="sxs-lookup"><span data-stu-id="73ad2-203">To check whether your devices are registered in the public cloud, you should export and download the list of devices from the Azure AD portal to an Excel spreadsheet.</span></span> <span data-ttu-id="73ad2-204">Затем фильтруйте устройства, зарегистрированные (с помощью столбца _registeredTime)_ после даты, когда ваша организация прошла [этап 9 процесса миграции.](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization)</span><span class="sxs-lookup"><span data-stu-id="73ad2-204">Then, filter the devices that are registered (by using the _registeredTime_ column) after the date when your organization has passed [phase 9 of the migration process](ms-cloud-germany-transition-phases.md#phase-9--10-azure-ad-finalization).</span></span>

## <a name="additional-considerations"></a><span data-ttu-id="73ad2-205">Дополнительные рекомендации</span><span class="sxs-lookup"><span data-stu-id="73ad2-205">Additional considerations</span></span>

> [!IMPORTANT]
> <span data-ttu-id="73ad2-206">Руководитель службы Intune будет включен после [3-го](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer)этапа процесса миграции, что подразумевает активацию регистрации устройств Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73ad2-206">The Intune service principal will be enabled after [phase 3 of the migration process](ms-cloud-germany-transition-phases.md#phase-3-subscription-transfer), which implies the activation of Azure AD Device Registration.</span></span> <span data-ttu-id="73ad2-207">Если вы заблокировали регистрацию устройств Azure AD перед миграцией, необходимо отключить главу службы Intune с PowerShell, чтобы снова отключить регистрацию устройств Azure AD на портале Azure AD.</span><span class="sxs-lookup"><span data-stu-id="73ad2-207">If you blocked Azure AD Device Registration before migration, you must disable the Intune service principal with PowerShell to disable Azure AD Device Registration with the Azure AD portal again.</span></span> <span data-ttu-id="73ad2-208">Вы можете отключить главу службы Intune с этой командой в Azure Active Directory PowerShell для Graph модуля.</span><span class="sxs-lookup"><span data-stu-id="73ad2-208">You can disable the Intune service principal with this command in the Azure Active Directory PowerShell for Graph module.</span></span>

```powershell
Get-AzureADServicePrincipal -All:$true |Where-object -Property AppId -eq "0000000a-0000-0000-c000-000000000000" | Set-AzureADServicePrincipal -AccountEnabled:$false
```

## <a name="more-information"></a><span data-ttu-id="73ad2-209">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="73ad2-209">More information</span></span>

<span data-ttu-id="73ad2-210">Начало работы:</span><span class="sxs-lookup"><span data-stu-id="73ad2-210">Getting started:</span></span>

- [<span data-ttu-id="73ad2-211">Миграция из Microsoft Cloud Deutschland в Office 365 службы в новых немецких регионах центра обработки данных</span><span class="sxs-lookup"><span data-stu-id="73ad2-211">Migration from Microsoft Cloud Deutschland to Office 365 services in the new German datacenter regions</span></span>](ms-cloud-germany-transition.md)
- [<span data-ttu-id="73ad2-212">Помощь по миграции Microsoft Cloud Deutschland</span><span class="sxs-lookup"><span data-stu-id="73ad2-212">Microsoft Cloud Deutschland Migration Assistance</span></span>](https://aka.ms/germanymigrateassist)
- [<span data-ttu-id="73ad2-213">Как принять участие в миграции</span><span class="sxs-lookup"><span data-stu-id="73ad2-213">How to opt-in for migration</span></span>](ms-cloud-germany-migration-opt-in.md)
- [<span data-ttu-id="73ad2-214">Опыт работы с клиентами во время миграции</span><span class="sxs-lookup"><span data-stu-id="73ad2-214">Customer experience during the migration</span></span>](ms-cloud-germany-transition-experience.md)

<span data-ttu-id="73ad2-215">Перемещение по переходу:</span><span class="sxs-lookup"><span data-stu-id="73ad2-215">Moving through the transition:</span></span>

- [<span data-ttu-id="73ad2-216">Действия и влияние этапов миграции</span><span class="sxs-lookup"><span data-stu-id="73ad2-216">Migration phases actions and impacts</span></span>](ms-cloud-germany-transition-phases.md)
- [<span data-ttu-id="73ad2-217">Дополнительная предварительная работа</span><span class="sxs-lookup"><span data-stu-id="73ad2-217">Additional pre-work</span></span>](ms-cloud-germany-transition-add-pre-work.md)
- <span data-ttu-id="73ad2-218">Дополнительные сведения [для Azure AD,](ms-cloud-germany-transition-azure-ad.md) [устройств,](ms-cloud-germany-transition-add-devices.md) [опытом](ms-cloud-germany-transition-add-experience.md)и [AD FS.](ms-cloud-germany-transition-add-adfs.md)</span><span class="sxs-lookup"><span data-stu-id="73ad2-218">Additional information for [Azure AD](ms-cloud-germany-transition-azure-ad.md), [devices](ms-cloud-germany-transition-add-devices.md), [experiences](ms-cloud-germany-transition-add-experience.md), and [AD FS](ms-cloud-germany-transition-add-adfs.md).</span></span>

<span data-ttu-id="73ad2-219">Облачные приложения:</span><span class="sxs-lookup"><span data-stu-id="73ad2-219">Cloud apps:</span></span>

- [<span data-ttu-id="73ad2-220">Сведения о программе миграции Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="73ad2-220">Dynamics 365 migration program information</span></span>](/dynamics365/get-started/migrate-data-german-region)
- [<span data-ttu-id="73ad2-221">Сведения о программе миграции Power BI</span><span class="sxs-lookup"><span data-stu-id="73ad2-221">Power BI migration program information</span></span>](/power-bi/admin/service-admin-migrate-data-germany)
- [<span data-ttu-id="73ad2-222">Начало перехода на Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="73ad2-222">Getting started with your Microsoft Teams upgrade</span></span>](/microsoftteams/upgrade-start-here)
