---
title: Защита от потери данных Microsoft 365 Endpoint (предварительная версия)
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
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
description: Настройте защиту от потери данных Microsoft 365 Endpoint для отслеживания действий с файлами и внедрения защитных действий для конечных точек этих файлов.
ms.openlocfilehash: c579d0bbfdc72e56d99558ffa7e6812d00098c0d
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430684"
---
# <a name="get-started-with-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="5aa9a-103">Начало работы с функцией защиты от потери данных в конечной точке (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-103">Get started with Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="5aa9a-104">Защита от потери данных Microsoft Endpoint (DLP конечной точки) является частью набора функций защиты от потери данных Microsoft 365 (DLP), которые можно использовать для обнаружения и защиты конфиденциальных элементов в службах Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-104">Microsoft Endpoint data loss prevention (Endpoint DLP) is part of the Microsoft 365 data loss prevention (DLP) suite of features you can use to discover and protect sensitive items across Microsoft 365 services.</span></span> <span data-ttu-id="5aa9a-105">Дополнительные сведения обо всех предложениях защиты от потери данных Microsoft см. в статье [Обзор политик защиты от потери данных](data-loss-prevention-policies.md).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-105">For more information about all of Microsoft’s DLP offerings, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span> <span data-ttu-id="5aa9a-106">Дополнительные сведения о защите от потери данных в конечной точке см. в статье [Сведения о защите от потери данных в конечных точках (предварительная версия)](endpoint-dlp-learn-about.md)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-106">To learn more about Endpoint DLP, see [Learn about Endpoint data loss prevention (preview)](endpoint-dlp-learn-about.md)</span></span>

<span data-ttu-id="5aa9a-107">Защита от потери данных Microsoft Endpoint позволяет отслеживать устройства с Windows 10, а также определять, когда используются и распространяются конфиденциальные элементы.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-107">Microsoft Endpoint DLP allows you to monitor Windows 10 devices and detect when sensitive items are used and shared.</span></span> <span data-ttu-id="5aa9a-108">Это обеспечивает необходимый уровень контроля и видимости для их правильного использования и защиты, а также для предотвращения рискованного поведения, которое может поставить их под угрозу.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-108">This gives you the visibility and control you need to ensure that they are used and protected properly, and to help prevent risky behavior that might compromise them.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="5aa9a-109">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="5aa9a-109">Before you begin</span></span>

### <a name="skusubscriptions-licensing"></a><span data-ttu-id="5aa9a-110">Лицензирование SKU/подписки</span><span class="sxs-lookup"><span data-stu-id="5aa9a-110">SKU/subscriptions licensing</span></span>

<span data-ttu-id="5aa9a-111">Прежде чем приступить к управлению службой защиты от потери данных в конечной точке, подтвердите [подписку Microsoft 365](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) и любые дополнительные надстройки.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-111">Before you get started with Endpoint DLP, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1) and any add-ons.</span></span> <span data-ttu-id="5aa9a-112">Чтобы использовать функции защиты от потери данных в конечной точке, необходимо иметь одну из этих подписок или надстроек.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-112">To access and use Endpoint DLP functionality, you must have one of these subscriptions or add-ons.</span></span>

- <span data-ttu-id="5aa9a-113">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5aa9a-113">Microsoft 365 E5</span></span>
- <span data-ttu-id="5aa9a-114">Microsoft 365 A5 (для учебных заведений)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-114">Microsoft 365 A5 (EDU)</span></span>
- <span data-ttu-id="5aa9a-115">Соответствие требованиям Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5aa9a-115">Microsoft 365 E5 compliance</span></span>
- <span data-ttu-id="5aa9a-116">Соответствие требованиям Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="5aa9a-116">Microsoft 365 A5 compliance</span></span>
- <span data-ttu-id="5aa9a-117">Защита информации и управление данными в Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="5aa9a-117">Microsoft 365 E5 information protection and governance</span></span>
- <span data-ttu-id="5aa9a-118">Защита информации и управление данными в Microsoft 365 A5</span><span class="sxs-lookup"><span data-stu-id="5aa9a-118">Microsoft 365 A5 information protection and governance</span></span>

### <a name="permissions"></a><span data-ttu-id="5aa9a-119">Разрешения</span><span class="sxs-lookup"><span data-stu-id="5aa9a-119">Permissions</span></span>

<span data-ttu-id="5aa9a-120">Чтобы включить управление устройствами, используемая учетная запись должна входить в любую из этих ролей:</span><span class="sxs-lookup"><span data-stu-id="5aa9a-120">To enable device management, the account you use must be a member of any one of these roles:</span></span>

- <span data-ttu-id="5aa9a-121">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="5aa9a-121">Global admin</span></span>
- <span data-ttu-id="5aa9a-122">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="5aa9a-122">Security admin</span></span>
- <span data-ttu-id="5aa9a-123">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5aa9a-123">Compliance admin</span></span>

<span data-ttu-id="5aa9a-124">Если вы хотите использовать настраиваемую учетную запись для просмотра параметров управления устройствами, она должна иметь одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="5aa9a-124">If you want to use a custom account to view the device management settings, it must be in one of these roles:</span></span>

- <span data-ttu-id="5aa9a-125">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="5aa9a-125">Global admin</span></span>
- <span data-ttu-id="5aa9a-126">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5aa9a-126">Compliance admin</span></span>
- <span data-ttu-id="5aa9a-127">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5aa9a-127">Compliance data admin</span></span>
- <span data-ttu-id="5aa9a-128">Глобальный читатель</span><span class="sxs-lookup"><span data-stu-id="5aa9a-128">Global reader</span></span>

<span data-ttu-id="5aa9a-129">Если вы хотите использовать настраиваемую учетную запись для доступа к страницам подключения или отключения, она должна иметь одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="5aa9a-129">If you want to use a custom account to access the onboarding/offboarding page, it must be in one of these roles:</span></span>

- <span data-ttu-id="5aa9a-130">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="5aa9a-130">Global admin</span></span>
- <span data-ttu-id="5aa9a-131">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5aa9a-131">Compliance admin</span></span>

<span data-ttu-id="5aa9a-132">Если вы хотите использовать настраиваемую учетную запись для отслеживания включения и отключения устройств, она должна иметь одну из следующих ролей:</span><span class="sxs-lookup"><span data-stu-id="5aa9a-132">If you want to use a custom account to turn on/off device monitoring, it must be in one of these roles:</span></span>

- <span data-ttu-id="5aa9a-133">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="5aa9a-133">Global admin</span></span>
- <span data-ttu-id="5aa9a-134">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5aa9a-134">Compliance admin</span></span>

<span data-ttu-id="5aa9a-135">Данные из службы защиты от потери данных в конечной точке доступны в [Обозревателе действий](data-classification-activity-explorer.md).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-135">Data from Endpoint DLP can be viewed in [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="5aa9a-136">Существует четыре роли, которые предоставляют разрешения обозревателю действий, учетная запись, которую вы используете для доступа к данным, должна входить в любую из этих ролей:</span><span class="sxs-lookup"><span data-stu-id="5aa9a-136">There are four roles that grant permission to activity explorer, the account you use for accessing the data must be a member of any one of them.</span></span>

- <span data-ttu-id="5aa9a-137">Глобальный администратор</span><span class="sxs-lookup"><span data-stu-id="5aa9a-137">Global admin</span></span>
- <span data-ttu-id="5aa9a-138">Администратор соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5aa9a-138">Compliance admin</span></span>
- <span data-ttu-id="5aa9a-139">Администратор безопасности</span><span class="sxs-lookup"><span data-stu-id="5aa9a-139">Security admin</span></span>
- <span data-ttu-id="5aa9a-140">Администратор данных соответствия требованиям</span><span class="sxs-lookup"><span data-stu-id="5aa9a-140">Compliance data admin</span></span>

### <a name="prepare-your-endpoints"></a><span data-ttu-id="5aa9a-141">Подготовка конечных точек</span><span class="sxs-lookup"><span data-stu-id="5aa9a-141">Prepare your endpoints</span></span>

<span data-ttu-id="5aa9a-142">Убедитесь, что устройства с Windows 10, на которых вы планируете развертывание защиты от потери данных в конечных точках, соответствуют следующим требованиям.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-142">Make sure that the Windows 10 devices that you plan on deploying Endpoint DLP to meet these requirements.</span></span>

1. <span data-ttu-id="5aa9a-143">Устройство работает под управлением Windows 10 (64-разрядная) сборки 1809 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-143">Must be running Windows 10 x64 build 1809 or later.</span></span>
2. <span data-ttu-id="5aa9a-144">Все устройства должны быть подключены к [Azure Active Directory (AAD)](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join) или иметь гибридное присоединение к Azure AD.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-144">All devices must be [Azure Active Directory (AAD) joined](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join), or Hybrid Azure AD joined.</span></span>
3. <span data-ttu-id="5aa9a-145">Установите браузер Microsoft Chromium Edge на устройство конечных точек для применения действия политики к отправке в облако.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-145">Install Microsoft Chromium Edge browser on the endpoint device to enforce policy actions for the upload to cloud activity.</span></span> <span data-ttu-id="5aa9a-146">См. статью [Загрузка нового браузера Microsoft Edge на основе Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-146">See, [Download the new Microsoft Edge based on Chromium](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium).</span></span>

## <a name="onboarding-devices-into-device-management"></a><span data-ttu-id="5aa9a-147">Интеграция устройств в управление устройствами</span><span class="sxs-lookup"><span data-stu-id="5aa9a-147">Onboarding devices into device management</span></span>

 <span data-ttu-id="5aa9a-148">Перед тем как отслеживать и защищать конфиденциальные элементы на устройстве, необходимо включить отслеживание устройств и подключить конечные точки.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-148">You must enable device monitoring and onboard your endpoints before you can monitor and protect sensitive items on a device.</span></span> <span data-ttu-id="5aa9a-149">Это можно сделать на портале соответствия требованиям Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-149">Both of these actions are done in the Microsoft 365 Compliance portal.</span></span>

<span data-ttu-id="5aa9a-150">Если вы хотите подключить устройства, которые еще не были подключены, скачайте соответствующий сценарий и разверните его на этих устройствах.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-150">When you want to onboard devices that haven't been onboarded yet, you'll download the appropriate script and deploy it to those devices.</span></span> <span data-ttu-id="5aa9a-151">Выполните действия, описанные в разделе [Подключение устройств](endpoint-dlp-getting-started.md#onboarding-devices).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-151">Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

<span data-ttu-id="5aa9a-152">Если у вас уже есть устройства, подключенные к [Microsoft Defender для конечной точки](https://docs.microsoft.com/windows/security/threat-protection/), они будут отображаться в списке управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-152">If you already have devices onboarded into [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), they will already appear in the managed devices list.</span></span> <span data-ttu-id="5aa9a-153">Выполните действия, описанные в разделе [Процедура с устройствами подключенными к Microsoft Defender для конечной точки](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-153">Follow the [With devices onboarded into Microsoft Defender for Endpoint procedure](endpoint-dlp-getting-started.md#with-devices-onboarded-into-microsoft-defender-for- endpoint).</span></span>

### <a name="onboarding-devices"></a><span data-ttu-id="5aa9a-154">Подключение устройств</span><span class="sxs-lookup"><span data-stu-id="5aa9a-154">Onboarding devices</span></span>

<span data-ttu-id="5aa9a-155">В этом сценарии развертывания подключаются устройства, которые еще не были подключены, а вам необходимо только отслеживать и защищать конфиденциальные элементы от непреднамеренного распространения на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-155">In this deployment scenario, you'll onboard devices that have not been onboarded yet, and you just want to monitor and protect sensitive items from unintentional sharing on Windows 10 devices.</span></span>

1. <span data-ttu-id="5aa9a-156">Откройте [Центр соответствия требованиям Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-156">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="5aa9a-157">Откройте параметры Центра соответствия требованиям и выберите **Подключение устройств**.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-157">Open the Compliance Center settings page and choose **Onboard devices**.</span></span> 

   ![включите управление устройствами](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

   > [!NOTE]
   > <span data-ttu-id="5aa9a-159">Обычно подключение устройств занимает около 60 секунд, подождите около 30 минут, прежде чем обращаться в службу поддержки Microsoft.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-159">While it usually takes about 60 seconds for device onboarding to be enabled, please allow up to 30 minutes before engaging with Microsoft support.</span></span>

3. <span data-ttu-id="5aa9a-160">Выберите **Управление устройствами**, чтобы открыть список **Устройства**</span><span class="sxs-lookup"><span data-stu-id="5aa9a-160">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="5aa9a-161">Список будет пустым, пока устройства не будут подключены.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-161">The list will be empty until you onboard devices.</span></span>
4. <span data-ttu-id="5aa9a-162">Нажмите **Подключение**, чтобы начать процесс.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-162">Choose **Onboarding** to begin the onboarding process.</span></span>
5. <span data-ttu-id="5aa9a-163">Выберите способ развертывания для дополнительных устройств в списке **Способ развертывания**, а затем **загрузите пакет**.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-163">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **download package**.</span></span>

   ![метод развертывания](../media/endpoint-dlp-getting-started-3-deployment-method.png)
6. <span data-ttu-id="5aa9a-165">Выполните действия, описанные в разделе [Средства и методы подключения ATP Microsoft Defender для компьютеров с Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-165">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="5aa9a-166">Эта ссылка открывает страницу доступа к процедурам с Microsoft Defender для конечной точки, соответствующим пакету развертывания, который вы выбрали на этапе 5:</span><span class="sxs-lookup"><span data-stu-id="5aa9a-166">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="5aa9a-167">Подключение компьютеров с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5aa9a-167">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="5aa9a-168">Подключение компьютеров с Windows с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5aa9a-168">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="5aa9a-169">Подключение компьютеров с Windows 10 с помощью инструментов управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="5aa9a-169">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="5aa9a-170">Подключение компьютеров с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="5aa9a-170">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="5aa9a-171">Подключение временных компьютеров инфраструктуры виртуальных рабочих столов (VDI).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-171">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="5aa9a-172">После подключения конечная точка будет отображаться в списке устройств, а также начнет отправлять отчеты о действиях аудита в обозреватель действий.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-172">Once done and endpoint is onboarded, it should be visible in the devices list and also start reporting audit activity logs to Activity explorer.</span></span>

> [!NOTE]
> <span data-ttu-id="5aa9a-173">Эта возможность включает принудительное применение лицензий.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-173">This experience is under license enforcement.</span></span> <span data-ttu-id="5aa9a-174">Без необходимой лицензии данные не будут видимы или доступны.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-174">Without the required license, data will not be visible or accessible.</span></span>

### <a name="with-devices-onboarded-into-microsoft-defender-for-endpoint"></a><span data-ttu-id="5aa9a-175">Процедура с устройствами подключенными к Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5aa9a-175">With devices onboarded into Microsoft Defender for Endpoint</span></span>

<span data-ttu-id="5aa9a-176">В этом случае Microsoft Defender для конечной точки уже развернут, а также присутствуют отчеты о конечных точках.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-176">In this scenario, Microsoft Defender for Endpoint is already deployed and there are endpoints reporting in.</span></span> <span data-ttu-id="5aa9a-177">Все конечные точки будут отображаться в списке управляемых устройств.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-177">All these endpoints will appear in the managed devices list.</span></span> <span data-ttu-id="5aa9a-178">Вы можете продолжать подключать новые устройства к DLP конечной точки, чтобы расширить охват с помощью [Процедуры подключения устройств](endpoint-dlp-getting-started.md#onboarding-devices)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-178">You can continue to onboard new devices into Endpoint DLP to expand coverage by using the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).</span></span>

1. <span data-ttu-id="5aa9a-179">Откройте [Центр соответствия требованиям Microsoft](https://compliance.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-179">Open the [Microsoft compliance center](https://compliance.microsoft.com).</span></span>
2. <span data-ttu-id="5aa9a-180">Откройте параметры Центра соответствия требованиям и выберите **Включить отслеживание устройств**.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-180">Open the Compliance Center settings page and choose **Enable device monitoring**.</span></span>
3. <span data-ttu-id="5aa9a-181">Выберите **Управление устройствами**, чтобы открыть список **Устройства**</span><span class="sxs-lookup"><span data-stu-id="5aa9a-181">Choose **Device management** to open the **Devices** list.</span></span> <span data-ttu-id="5aa9a-182">Отобразится список устройств, которые уже отправляют отчеты в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-182">You should see the list of devices that are already reporting in to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="5aa9a-183">![управление устройствами](../media/endpoint-dlp-getting-started-2-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-183">![device management](../media/endpoint-dlp-getting-started-2-device-management.png)</span></span>
4. <span data-ttu-id="5aa9a-184">Чтобы подключить дополнительные устройства, выберите **Подключение**.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-184">Choose **Onboarding** if you need to onboard additional devices.</span></span>
5. <span data-ttu-id="5aa9a-185">Выберите способ развертывания для дополнительных устройств в списке **Способ развертывания**, а затем **загрузите пакет**.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-185">Choose the way you want to deploy to these additional devices from the **Deployment method** list and then **Download package**.</span></span>
6. <span data-ttu-id="5aa9a-186">Выполните действия, описанные в разделе [Средства и методы подключения ATP Microsoft Defender для компьютеров с Windows 10](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-186">Follow the appropriate procedures in [Onboarding tools and methods for Windows 10 machines](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints).</span></span> <span data-ttu-id="5aa9a-187">Эта ссылка открывает страницу доступа к процедурам с Microsoft Defender для конечной точки, соответствующим пакету развертывания, который вы выбрали на этапе 5:</span><span class="sxs-lookup"><span data-stu-id="5aa9a-187">This link take you to a landing page where you can access Microsoft Defender for Endpoint procedures that match the deployment package you selected in step 5:</span></span>
    - <span data-ttu-id="5aa9a-188">Подключение компьютеров с Windows 10 с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="5aa9a-188">Onboard Windows 10 machines using Group Policy</span></span>
    - <span data-ttu-id="5aa9a-189">Подключение компьютеров с Windows с помощью Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5aa9a-189">Onboard Windows machines using Microsoft Endpoint Configuration Manager</span></span>
    - <span data-ttu-id="5aa9a-190">Подключение компьютеров с Windows 10 с помощью инструментов управления мобильными устройствами</span><span class="sxs-lookup"><span data-stu-id="5aa9a-190">Onboard Windows 10 machines using Mobile Device Management tools</span></span>
    - <span data-ttu-id="5aa9a-191">Подключение компьютеров с Windows 10 с помощью локального сценария</span><span class="sxs-lookup"><span data-stu-id="5aa9a-191">Onboard Windows 10 machines using a local script</span></span>
    - <span data-ttu-id="5aa9a-192">Подключение временных компьютеров инфраструктуры виртуальных рабочих столов (VDI).</span><span class="sxs-lookup"><span data-stu-id="5aa9a-192">Onboard non-persistent virtual desktop infrastructure (VDI) machines.</span></span>

<span data-ttu-id="5aa9a-193">После подключения конечная точка будет отображаться в таблице **устройств**, а также начнет отправлять отчеты из журнала аудита в **обозреватель действий**.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-193">Once done and endpoint is onboarded, it should be visible under the **Devices** table and also start reporting audit logs to the **Activity Explorer**.</span></span>

> [!NOTE]
><span data-ttu-id="5aa9a-194">Эта возможность включает принудительное применение лицензий.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-194">This experience is under license enforcement.</span></span> <span data-ttu-id="5aa9a-195">Без необходимой лицензии данные не будут видимы или доступны.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-195">Without the required license, data will not be visible or accessible.</span></span>

### <a name="viewing-endpoint-dlp-data-in-activity-explorer"></a><span data-ttu-id="5aa9a-196">Просмотр данных защиты от потери данных в конечной точке с помощью обозревателя действий</span><span class="sxs-lookup"><span data-stu-id="5aa9a-196">Viewing Endpoint DLP data in activity explorer</span></span>

1. <span data-ttu-id="5aa9a-197">Откройте страницу [классификации данных](https://compliance.microsoft.com/dataclassification?viewid=overview) для своего домена в Центре соответствия требованиям Microsoft 365 и выберите обозреватель действий.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-197">Open the [Data classification page](https://compliance.microsoft.com/dataclassification?viewid=overview) for your domain in the Microsoft 365 Compliance center and choose Activity explorer.</span></span>
2. <span data-ttu-id="5aa9a-198">Выполните действия, описанные в статье [Начало работы с обозревателем действий](data-classification-activity-explorer.md), чтобы получить доступ к данным и отфильтровать их на своих устройствах конечной точки.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-198">Refer to the procedures in [Get started with Activity explorer](data-classification-activity-explorer.md) to access and filter all the data for your Endpoint devices.</span></span>

![фильтр обозревателя действий для устройств конечных точек](../media/endpoint-dlp-4-getting-started-activity-explorer.png)

## <a name="next-steps"></a><span data-ttu-id="5aa9a-200">Следующие шаги</span><span class="sxs-lookup"><span data-stu-id="5aa9a-200">Next steps</span></span>
<span data-ttu-id="5aa9a-201">После того, как вы подключили устройства, вы можете просмотреть данные об активности в обозревателе действий и перейти к этапу создания политик защиты от потери данных для конфиденциальных элементов.</span><span class="sxs-lookup"><span data-stu-id="5aa9a-201">Now that you have onboarded devices and can view the activity data in Activity explorer, you are ready to move on to your next step where you create DLP policies that protect your sensitive items.</span></span>

- [<span data-ttu-id="5aa9a-202">Использование функции защиты от потери данных в конечной точке (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-202">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="5aa9a-203">См. также</span><span class="sxs-lookup"><span data-stu-id="5aa9a-203">See also</span></span>

- [<span data-ttu-id="5aa9a-204">Сведения о защите от потери данных в конечной точке (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-204">Learn about Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="5aa9a-205">Использование функции защиты от потери данных в конечной точке (предварительная версия)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-205">Using Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="5aa9a-206">Общие сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="5aa9a-206">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="5aa9a-207">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="5aa9a-207">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="5aa9a-208">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="5aa9a-208">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="5aa9a-209">Microsoft Defender Advanced Threat Protection (ATP в Microsoft Defender)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-209">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="5aa9a-210">Средства и методы подключения для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="5aa9a-210">Onboarding tools and methods for Windows 10 machines</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="5aa9a-211">Подписка на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="5aa9a-211">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="5aa9a-212">Подключено к Azure Active Directory (AAD)</span><span class="sxs-lookup"><span data-stu-id="5aa9a-212">Azure Active Directory (AAD) joined</span></span>](https://docs.microsoft.com/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="5aa9a-213">Загрузка нового браузера Microsoft Edge на основе Chromium</span><span class="sxs-lookup"><span data-stu-id="5aa9a-213">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)
