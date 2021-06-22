---
title: Начало работы с защитой от потери данных в конечной точке Microsoft 365
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Настройте Защиту от потери данных в конечной точке Microsoft 365 для отслеживания действий с файлами и применения в конечных точках защитных мер для этих файлов.
ms.openlocfilehash: 134c5426e428372670a50c76301a9e9e0c10b343
ms.sourcegitcommit: d34cac68537d6e1c65be757956646e73dea6e1ab
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/22/2021
ms.locfileid: "53061670"
---
# <a name="get-started-with-endpoint-data-loss-prevention"></a><span data-ttu-id="8e400-103">Начало работы с функцией защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="8e400-103">Get started with Endpoint data loss prevention</span></span>

<span data-ttu-id="8e400-104">Защита от потери данных Microsoft Endpoint (DLP конечной точки) является частью набора функций защиты от потери данных Microsoft 365 (DLP), которые можно использовать для обнаружения и защиты конфиденциальных элементов в службах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e400-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="8e400-105">Дополнительные сведения обо всех предложениях Майкрософт по защите от потери данных см. в статье [Сведения о защите от потери данных](dlp-learn-about-dlp.md).</span><span class="sxs-lookup"><span data-stu-id="8e400-105">For more information about all of Microsoft’s DLP offerings, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span> <span data-ttu-id="8e400-106">Дополнительные сведения о защите от потери данных в конечной точке см. в статье [Сведения о защите от потери данных в конечных точках](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="8e400-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="8e400-107">Защита от потери данных Microsoft Endpoint позволяет отслеживать устройства с Windows 10, а также определять, когда используются и распространяются конфиденциальные элементы.</span><span class="sxs-lookup"><span data-stu-id="8e400-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="8e400-108">Это обеспечивает необходимый уровень контроля и видимости для их правильного использования и защиты, а также для предотвращения рискованного поведения, которое может поставить их под угрозу.</span><span class="sxs-lookup"><span data-stu-id="8e400-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="8e400-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="8e400-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="8e400-110">Лицензирование SKU/подписки</span><span class="sxs-lookup"><span data-stu-id="8e400-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="8e400-111">Прежде чем приступить к управлению службой защиты от потери данных в конечной точке, подтвердите [подписку Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) и любые дополнительные надстройки.</span><span class="sxs-lookup"><span data-stu-id="8e400-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="8e400-112">Чтобы использовать функции защиты от потери данных в конечной точке, необходимо иметь одну из этих подписок или надстроек.</span><span class="sxs-lookup"><span data-stu-id="8e400-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="8e400-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8e400-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="8e400-114">Microsoft 365 A5 (для учебных заведений)</span><span class="sxs-lookup"><span data-stu-id="8e400-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="8e400-115">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8e400-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="8e400-116">Соответствие требованиям Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="8e400-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="8e400-117">Защита информации и управление данными в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="8e400-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="8e400-118">Защита информации и управление данными в Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="8e400-118">Microsoft 365 A5 information protection and governance</span></span>


### <a name="permissions"></a><span data-ttu-id="8e400-119">Разрешения</span><span class="sxs-lookup"><span data-stu-id="8e400-119">Permissions</span></span>

<span data-ttu-id="8e400-120">Чтобы включить управление устройствами, используемая учетная запись должна входить в любую из этих ролей:</span><span class="sxs-lookup"><span data-stu-id="8e400-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="8e400-121">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="8e400-121">Global admin</span></span>
- <span data-ttu-id="8e400-122">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="8e400-122">Security admin</span></span>
- <span data-ttu-id="8e400-123">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8e400-123">Compliance admin</span></span>

<span data-ttu-id="8e400-124">Если вы хотите использовать настраиваемую учетную запись для просмотра параметров управления устройствами, она должна иметь одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="8e400-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="8e400-125">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="8e400-125">Global admin</span></span>
- <span data-ttu-id="8e400-126">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8e400-126">Compliance admin</span></span>
- <span data-ttu-id="8e400-127">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8e400-127">Compliance data admin</span></span>
- <span data-ttu-id="8e400-128">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="8e400-128">Global reader</span></span>

<span data-ttu-id="8e400-129">Если вы хотите использовать настраиваемую учетную запись для доступа к страницам подключения или отключения, она должна иметь одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="8e400-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="8e400-130">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="8e400-130">Global admin</span></span>
- <span data-ttu-id="8e400-131">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8e400-131">Compliance admin</span></span>

<span data-ttu-id="8e400-132">Если вы хотите использовать настраиваемую учетную запись для отслеживания включения и отключения устройств, она должна иметь одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="8e400-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="8e400-133">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="8e400-133">Global admin</span></span>
- <span data-ttu-id="8e400-134">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8e400-134">Compliance admin</span></span>

<span data-ttu-id="8e400-135">Данные из службы защиты от потери данных в конечной точке доступны в [Обозревателе действий](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="8e400-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="8e400-136">Существует четыре роли, которые предоставляют разрешения обозревателю действий, учетная запись, которую вы используете для доступа к данным, должна входить в любую из этих ролей:</span><span class="sxs-lookup"><span data-stu-id="8e400-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="8e400-137">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="8e400-137">Global admin</span></span>
- <span data-ttu-id="8e400-138">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8e400-138">Compliance admin</span></span>
- <span data-ttu-id="8e400-139">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="8e400-139">Security admin</span></span>
- <span data-ttu-id="8e400-140">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="8e400-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="8e400-141">Подготовка конечных точек</span><span class="sxs-lookup"><span data-stu-id="8e400-141">Prepare your endpoints</span></span>

<span data-ttu-id="8e400-142">Убедитесь, что устройства с Windows 10, на которых вы планируете развертывание защиты от потери данных в конечных точках, соответствуют следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="8e400-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="8e400-143">Устройство работает под управлением Windows 10 (64-разрядная) сборки 1809 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="8e400-143">Must be running Windows 10 x64 build 1809 or later.</span></span>

2. <span data-ttu-id="8e400-144">Версия клиента антивредоносной программы: 4.18.2009.7 или более поздняя.</span><span class="sxs-lookup"><span data-stu-id="8e400-144">Antimalware Client Version is 4.18.2009.7 or newer.</span></span> <span data-ttu-id="8e400-145">Проверьте свою текущую версию, открыв приложение "Безопасность Windows", щелкнув значок "Параметры" и выбрав "О программе".</span><span class="sxs-lookup"><span data-stu-id="8e400-145">Check your current version by opening Windows Security app, select the Settings icon, and then select About.</span></span> <span data-ttu-id="8e400-146">Номер версии указан в строке "Версия клиента антивредоносной программы".</span><span class="sxs-lookup"><span data-stu-id="8e400-146">The version number is listed under Antimalware Client Version.</span></span> <span data-ttu-id="8e400-147">Перейдите на последнюю версию клиента антивредоносной программы, установив обновление Windows KB4052623.</span><span class="sxs-lookup"><span data-stu-id="8e400-147">Update to the latest Antimalware Client Version by installing Windows Update KB4052623.</span></span> 

   > [!NOTE]
   > <span data-ttu-id="8e400-148">Не требуется запускать никакие компоненты Безопасности Windows. Вы можете запускать DLP в конечной точке независимо от состояния Безопасность Windows, но [защита в реальном времени и монитор поведения](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) должны быть включены.</span><span class="sxs-lookup"><span data-stu-id="8e400-148">None of Windows Security components need to be active, you can run Endpoint DLP independent of Windows Security status, but the [Real-time protection and Behavior monitor](/windows/security/threat-protection/microsoft-defender-antivirus/configure-real-time-protection-microsoft-defender-antivirus)) must be enabled.</span></span>
 
3. <span data-ttu-id="8e400-149">Устанавливаются следующие обновления Windows.</span><span class="sxs-lookup"><span data-stu-id="8e400-149">The following Windows Updates are installed.</span></span> 
 
   > [!NOTE]
   > <span data-ttu-id="8e400-150">Эти обновления не являются необходимым условием для подключения устройства к DLP в конечной точке, однако они содержат важные исправления, поэтому их требуется установить перед использованием продукта.</span><span class="sxs-lookup"><span data-stu-id="8e400-150">These updates are not a pre-requisite to onboard a device to Endpoint DLP, but contain fixes for important issues thus must be installed before using the product.</span></span>

    - <span data-ttu-id="8e400-151">Для Windows 10 версии 1809 — KB4559003, KB4577069, KB4580390</span><span class="sxs-lookup"><span data-stu-id="8e400-151">For Windows 10 1809 - KB4559003, KB4577069, KB4580390</span></span>
    - <span data-ttu-id="8e400-152">Для Windows 10 версии 1903 или 1909 — KB4559004, KB4577062, KB4580386</span><span class="sxs-lookup"><span data-stu-id="8e400-152">For Windows 10 1903 or 1909 - KB4559004, KB4577062, KB4580386</span></span>
    - <span data-ttu-id="8e400-153">Для Windows 10 версии 2004 — KB4568831, KB4577063</span><span class="sxs-lookup"><span data-stu-id="8e400-153">For Windows 10 2004 - KB4568831, KB4577063</span></span>
    - <span data-ttu-id="8e400-154">Для устройств с Office 2016 (но не других версий Office) — KB4577063</span><span class="sxs-lookup"><span data-stu-id="8e400-154">For devices running Office 2016 (and not any other Office version) - KB4577063</span></span> 

4. <span data-ttu-id="8e400-155">Все устройства должны соответствовать одному из таких требований:</span><span class="sxs-lookup"><span data-stu-id="8e400-155">All devices must be one of these:</span></span>
- [<span data-ttu-id="8e400-156">С присоединением к Azure Active Directory (Azure AD)</span><span class="sxs-lookup"><span data-stu-id="8e400-156">Azure Active Directory (Azure AD) joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="8e400-157">С гибридным присоединением к Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e400-157">Hybrid Azure AD joined</span></span>](/azure/active-directory/devices/concept-azure-ad-join-hybrid)
- [<span data-ttu-id="8e400-158">С регистрацией в AAD</span><span class="sxs-lookup"><span data-stu-id="8e400-158">AAD registered</span></span>](/azure/active-directory/user-help/user-help-register-device-on-network)

5. <span data-ttu-id="8e400-159">Установите браузер Microsoft Chromium Edge на устройство конечных точек для применения действия политики к отправке в облако.</span><span class="sxs-lookup"><span data-stu-id="8e400-159">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="8e400-160">См. статью [Загрузка нового браузера Microsoft Edge на основе Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="8e400-160">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

6. <span data-ttu-id="8e400-161">Если вы используете Ежемесячный канал (корпоративный) для Приложений Microsoft 365 версий 2004–2008, в них существует известная проблема с классификацией контента Office функцией защиты от потери данных в конечной точке и вам требуется обновиться до версии 2009 или более поздней.</span><span class="sxs-lookup"><span data-stu-id="8e400-161">If you are on Monthly Enterprise Channel of Microsoft 365 Apps versions 2004-2008, there is a known issue with Endpoint DLP classifying Office content and you need to update to version 2009 or later.</span></span> <span data-ttu-id="8e400-162">Текущие версии см. в [журнале обновлений для Приложений Microsoft 365 (по дате)](/officeupdates/update-history-microsoft365-apps-by-date).</span><span class="sxs-lookup"><span data-stu-id="8e400-162">See [Update history for Microsoft 365 Apps (listed by date)](/officeupdates/update-history-microsoft365-apps-by-date) for current versions.</span></span> <span data-ttu-id="8e400-163">Дополнительные сведения об этой проблеме см. в разделе "Набор Office" [заметок о выпусках Актуального канала в 2020 г.](/officeupdates/current-channel#version-2010-october-27)</span><span class="sxs-lookup"><span data-stu-id="8e400-163">To learn more about this issue, see the Office Suite section of [Release notes for Current Channel releases in 2020](/officeupdates/current-channel#version-2010-october-27).</span></span>

7. <span data-ttu-id="8e400-164">Если у вас есть конечные точки, которые используют прокси-устройство для подключения к Интернету, выполните действия, описанные в разделе [Настройка прокси-сервера и параметров подключения к Интернету для защиты от потери данных в конечной точке](endpoint-dlp-configure-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="8e400-164">If you have endpoints that use a device proxy to connect to the internet, follow the procedures in [Configure device proxy and internet connection settings for Endpoint DLP](endpoint-dlp-configure-proxy.md).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="8e400-165">Интеграция устройств в управление устройствами</span><span class="sxs-lookup"><span data-stu-id="8e400-165">Onboarding devices into device management</span></span>

<span data-ttu-id="8e400-166">Перед тем как отслеживать и защищать конфиденциальные элементы на устройстве, необходимо включить отслеживание устройств и подключить конечные точки.</span><span class="sxs-lookup"><span data-stu-id="8e400-166">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="8e400-167">Это можно сделать на портале соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="8e400-167">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="8e400-168">Если вы хотите подключить устройства, которые еще не были подключены, скачайте соответствующий сценарий и разверните его на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="8e400-168">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="8e400-169">Выполните действия, описанные в разделе [Подключение устройств](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="8e400-169">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="8e400-170">Если у вас уже есть устройства, подключенные к [Microsoft Defender для конечной точки](/windows/security/threat-protection/), они будут отображаться в списке управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="8e400-170">If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="8e400-171">Выполните действия, описанные в разделе [Процедура с устройствами подключенными к Microsoft Defender для конечной точки](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span><span class="sxs-lookup"><span data-stu-id="8e400-171">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](?source=docs&view=o365-worldwide#with-devices-onboarded-into-microsoft-defender-for-endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="8e400-172">Подключение устройств</span><span class="sxs-lookup"><span data-stu-id="8e400-172">Onboarding devices</span></span>

<span data-ttu-id="8e400-173">В этом сценарии развертывания подключаются устройства, которые еще не были подключены, а вам необходимо только отслеживать и защищать конфиденциальные элементы от непреднамеренного распространения на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="8e400-173">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="8e400-174">Откройте [Центр соответствия требованиям Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8e400-174">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="8e400-175">Откройте параметры Центра соответствия требованиям и выберите **Подключение устройств**.</span><span class="sxs-lookup"><span data-stu-id="8e400-175">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e400-176">![включение управления устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="8e400-176">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

   > [!NOTE]
   > <span data-ttu-id="8e400-177">Обычно подключение устройств занимает около 60 секунд, подождите около 30 минут, прежде чем обращаться в службу поддержки Microsoft.</span><span class="sxs-lookup"><span data-stu-id="8e400-177">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="8e400-178">Выберите **Управление устройствами**, чтобы открыть список **Устройства**</span><span class="sxs-lookup"><span data-stu-id="8e400-178">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="8e400-179">Список будет пустым, пока устройства не будут подключены.</span><span class="sxs-lookup"><span data-stu-id="8e400-179">The list will be empty until you onboard devices.</span></span>

4. <span data-ttu-id="8e400-180">Нажмите **Подключение**, чтобы начать процесс.</span><span class="sxs-lookup"><span data-stu-id="8e400-180">Choose **Onboarding** to begin the onboarding process.</span></span>

5. <span data-ttu-id="8e400-181">Выберите способ развертывания для дополнительных устройств в списке **Способ развертывания**, а затем **загрузите пакет**.</span><span class="sxs-lookup"><span data-stu-id="8e400-181">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e400-182">![метод развертывания](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span><span class="sxs-lookup"><span data-stu-id="8e400-182">![deployment method](../media/endpoint-dlp-getting-started-3-deployment-method.png)</span></span>
   
6. <span data-ttu-id="8e400-183">Выполните действия, описанные в разделе [Средства и методы подключения ATP Microsoft Defender для компьютеров с Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="8e400-183">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="8e400-184">Эта ссылка открывает начальную страницу доступа к процедурам Microsoft Defender для конечной точки, соответствующим пакету развертывания, который вы выбрали на этапе 5:</span><span class="sxs-lookup"><span data-stu-id="8e400-184">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="8e400-185">Подключение компьютеров с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="8e400-185">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="8e400-186">Подключение компьютеров с Windows с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8e400-186">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="8e400-187">Подключение компьютеров с Windows 10 с помощью инструментов управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="8e400-187">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="8e400-188">Подключение компьютеров с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="8e400-188">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="8e400-189">Временное подключение компьютеров инфраструктуры виртуальных рабочих столов (VDI) для односеансных сценариев</span><span class="sxs-lookup"><span data-stu-id="8e400-189">Onboard non-persistent virtual desktop infrastructure (VDI) machines in single-session scenarios</span></span>

<span data-ttu-id="8e400-190">После подключения конечная точка будет отображаться в списке устройств, а также начнет отправлять отчеты о действиях аудита в обозреватель действий.</span><span class="sxs-lookup"><span data-stu-id="8e400-190">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="8e400-191">Эта возможность включает принудительное применение лицензий.</span><span class="sxs-lookup"><span data-stu-id="8e400-191">This experience is under license enforcement.</span></span> <span data-ttu-id="8e400-192">Без необходимой лицензии данные не будут видимы или доступны.</span><span class="sxs-lookup"><span data-stu-id="8e400-192">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="8e400-193">Процедура с устройствами подключенными к Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8e400-193">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="8e400-194">В этом случае Microsoft Defender для конечной точки уже развернут, а также присутствуют отчеты о конечных точках.</span><span class="sxs-lookup"><span data-stu-id="8e400-194">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="8e400-195">Все конечные точки будут отображаться в списке управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="8e400-195">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="8e400-196">Вы можете продолжать подключать новые устройства к DLP конечной точки, чтобы расширить охват с помощью [Процедуры подключения устройств](endpoint-dlp-getting-started.md#onboarding-devices)</span><span class="sxs-lookup"><span data-stu-id="8e400-196">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="8e400-197">Откройте [Центр соответствия требованиям Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8e400-197">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>

2. <span data-ttu-id="8e400-198">Откройте параметры Центра соответствия требованиям и выберите **Включить отслеживание устройств**.</span><span class="sxs-lookup"><span data-stu-id="8e400-198">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>

3. <span data-ttu-id="8e400-199">Выберите **Управление устройствами**, чтобы открыть список **Устройства**</span><span class="sxs-lookup"><span data-stu-id="8e400-199">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="8e400-200">Отобразится список устройств, которые уже отправляют отчеты в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8e400-200">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e400-201">![управление устройствами](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="8e400-201">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
   
4. <span data-ttu-id="8e400-202">Чтобы подключить дополнительные устройства, выберите **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="8e400-202">Choose **Onboarding** if you need to onboard additional devices.</span></span>

5. <span data-ttu-id="8e400-203">Выберите способ развертывания для дополнительных устройств в списке **Способ развертывания**, а затем **загрузите пакет**.</span><span class="sxs-lookup"><span data-stu-id="8e400-203">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>

6. <span data-ttu-id="8e400-204">Выполните действия, описанные в разделе [Средства и методы подключения ATP Microsoft Defender для компьютеров с Windows 10](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="8e400-204">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="8e400-205">Эта ссылка открывает начальную страницу доступа к процедурам Microsoft Defender для конечной точки, соответствующим пакету развертывания, который вы выбрали на этапе 5:</span><span class="sxs-lookup"><span data-stu-id="8e400-205">This link takes you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>

    - <span data-ttu-id="8e400-206">Подключение компьютеров с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="8e400-206">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="8e400-207">Подключение компьютеров с Windows с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="8e400-207">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="8e400-208">Подключение компьютеров с Windows 10 с помощью инструментов управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="8e400-208">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="8e400-209">Подключение компьютеров с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="8e400-209">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="8e400-210">Подключение временных компьютеров инфраструктуры виртуальных рабочих столов (VDI).</span><span class="sxs-lookup"><span data-stu-id="8e400-210">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="8e400-211">После подключения конечная точка будет отображаться в таблице **устройств**, а также начнет отправлять отчеты из журнала аудита в **обозреватель действий**.</span><span class="sxs-lookup"><span data-stu-id="8e400-211">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="8e400-212">Эта возможность включает принудительное применение лицензий.</span><span class="sxs-lookup"><span data-stu-id="8e400-212">This experience is under license enforcement.</span></span> <span data-ttu-id="8e400-213">Без необходимой лицензии данные не будут видимы или доступны.</span><span class="sxs-lookup"><span data-stu-id="8e400-213">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-alerts-in-dlp-alerts-management-dashboard"></a><span data-ttu-id="8e400-214">Просмотр оповещений защиты от потери данных в конечной точке на панели управления оповещениями защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="8e400-214">Viewing Endpoint DLP alerts in DLP Alerts Management dashboard</span></span>

1. <span data-ttu-id="8e400-215">Откройте страницу защиты от потери данных в Центре соответствия требованиям Microsoft 365 и выберите "Оповещения".</span><span class="sxs-lookup"><span data-stu-id="8e400-215">Open the Data loss prevention page in the Microsoft 365 Compliance center and choose Alerts.</span></span>

2. <span data-ttu-id="8e400-216">Используйте процедуры из статьи [Настройка и просмотр оповещений для политик защиты от потери данных](dlp-configure-view-alerts-policies.md), чтобы просмотреть оповещения для своих политик защиты от потери данных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="8e400-216">Refer to the procedures in [How to configure and view alerts for your DLP policies](dlp-configure-view-alerts-policies.md) to view alerts for your Endpoint DLP policies.</span></span>


### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="8e400-217">Просмотр данных защиты от потери данных в конечной точке с помощью обозревателя действий</span><span class="sxs-lookup"><span data-stu-id="8e400-217">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="8e400-218">Откройте страницу [классификации данных](https://compliance.microsoft.com/dataclassification?viewid=overview) для своего домена в Центре соответствия требованиям Microsoft 365 и выберите обозреватель действий.</span><span class="sxs-lookup"><span data-stu-id="8e400-218">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>

2. <span data-ttu-id="8e400-219">Выполните действия, описанные в статье [Начало работы с обозревателем действий](data-classification-activity-explorer.md), чтобы получить доступ к данным и отфильтровать их на своих устройствах конечной точки.</span><span class="sxs-lookup"><span data-stu-id="8e400-219">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="8e400-220">![фильтр обозревателя действий для устройств конечных точек](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="8e400-220">![activity explorer filter for endpoint devices](../media/endpoint-dlp-4-getting-started-activity-explorer.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="8e400-221">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="8e400-221">Next steps</span></span>
<span data-ttu-id="8e400-222">После того, как вы подключили устройства, вы можете просмотреть данные об активности в обозревателе действий и перейти к этапу создания политик защиты от потери данных для конфиденциальных элементов.</span><span class="sxs-lookup"><span data-stu-id="8e400-222">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="8e400-223">Использование Защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="8e400-223">Using Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="8e400-224">См. также</span><span class="sxs-lookup"><span data-stu-id="8e400-224">See also</span></span>

- [<span data-ttu-id="8e400-225">Сведения о защите от потери данных в конечной точке </span><span class="sxs-lookup"><span data-stu-id="8e400-225">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="8e400-226">Использование защиты от потери данных в конечной точке </span><span class="sxs-lookup"><span data-stu-id="8e400-226">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="8e400-227">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="8e400-227">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="8e400-228">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="8e400-228">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="8e400-229">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="8e400-229">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="8e400-230">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8e400-230">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="8e400-231">Средства и методы подключения для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="8e400-231">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="8e400-232">Подписка на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="8e400-232">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="8e400-233">Устройства, подключенные к Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e400-233">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="8e400-234">Загрузка нового браузера Microsoft Edge на основе Chromium</span><span class="sxs-lookup"><span data-stu-id="8e400-234">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
