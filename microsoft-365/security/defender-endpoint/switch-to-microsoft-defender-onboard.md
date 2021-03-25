---
title: Переключиться на Microsoft Defender для конечной точки — на борту
description: Это этап 3, на борту, для переноса из решения, не от Microsoft, в Microsoft Defender для конечной точки.
keywords: миграция, защита от угроз защитника Windows, atp, edr
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-migratetomdatp
ms.custom: migrationguides
ms.topic: article
ms.date: 03/03/2021
ms.reviewer: jesquive, chventou, jonix, chriggs, owtho
ms.openlocfilehash: afc3590bb3ad57a63868bb8218612ae69956186c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185543"
---
# <a name="switch-to-microsoft-defender-for-endpoint---phase-3-onboard"></a><span data-ttu-id="34734-104">Переход на Microsoft Defender для конечной точки — этап 3. На борту</span><span class="sxs-lookup"><span data-stu-id="34734-104">Switch to Microsoft Defender for Endpoint - Phase 3: Onboard</span></span>

<span data-ttu-id="34734-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="34734-105">**Applies to:**</span></span>
- [<span data-ttu-id="34734-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="34734-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="34734-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="34734-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

| <span data-ttu-id="34734-108">[![Этап 1. Подготовка3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)</span><span class="sxs-lookup"><span data-stu-id="34734-108">[![Phase 1: Prepare3](images/phase-diagrams/prepare.png)](switch-to-microsoft-defender-prepare.md)</span></span><br/>[<span data-ttu-id="34734-109">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="34734-109">Phase 1: Prepare</span></span>](switch-to-microsoft-defender-prepare.md) | <span data-ttu-id="34734-110">[![Этап 2. Настройка](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)</span><span class="sxs-lookup"><span data-stu-id="34734-110">[![Phase 2: Set up](images/phase-diagrams/setup.png)](switch-to-microsoft-defender-setup.md)</span></span><br/>[<span data-ttu-id="34734-111">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="34734-111">Phase 2: Set up</span></span>](switch-to-microsoft-defender-setup.md) | ![Этап 3. На борту](images/phase-diagrams/onboard.png)<br/><span data-ttu-id="34734-113">Этап 3. На борту</span><span class="sxs-lookup"><span data-stu-id="34734-113">Phase 3: Onboard</span></span> |
|--|--|--|
|| |<span data-ttu-id="34734-114">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="34734-114">*You are here!*</span></span> |


<span data-ttu-id="34734-115">**Добро пожаловать в фазу 3 перехода на [Microsoft Defender для конечной точки.](switch-to-microsoft-defender-migration.md#the-migration-process)**</span><span class="sxs-lookup"><span data-stu-id="34734-115">**Welcome to Phase 3 of [switching to Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)**.</span></span> <span data-ttu-id="34734-116">Этот этап миграции включает следующие действия:</span><span class="sxs-lookup"><span data-stu-id="34734-116">This migration phase includes the following steps:</span></span>

1. <span data-ttu-id="34734-117">[Onboard devices to Microsoft Defender for Endpoint.](#onboard-devices-to-microsoft-defender-for-endpoint)</span><span class="sxs-lookup"><span data-stu-id="34734-117">[Onboard devices to Microsoft Defender for Endpoint](#onboard-devices-to-microsoft-defender-for-endpoint).</span></span>
2. <span data-ttu-id="34734-118">[Запустите тест обнаружения](#run-a-detection-test).</span><span class="sxs-lookup"><span data-stu-id="34734-118">[Run a detection test](#run-a-detection-test).</span></span>
3. <span data-ttu-id="34734-119">[Удалить решение, не в microsoft.](#uninstall-your-non-microsoft-solution)</span><span class="sxs-lookup"><span data-stu-id="34734-119">[Uninstall your non-Microsoft solution](#uninstall-your-non-microsoft-solution).</span></span>
4. <span data-ttu-id="34734-120">[Убедитесь, что Microsoft Defender для конечной точки находится в активном режиме.](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode)</span><span class="sxs-lookup"><span data-stu-id="34734-120">[Make sure Microsoft Defender for Endpoint is in active mode](#make-sure-microsoft-defender-for-endpoint-is-in-active-mode).</span></span>

## <a name="onboard-devices-to-microsoft-defender-for-endpoint"></a><span data-ttu-id="34734-121">Onboard devices to Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="34734-121">Onboard devices to Microsoft Defender for Endpoint</span></span>

1. <span data-ttu-id="34734-122">Перейдите в Центр безопасности защитника Майкрософт [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="34734-122">Go to the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)) and sign in.</span></span>
2. <span data-ttu-id="34734-123">Выбор   >  onboarding **управления**  >  **устройствами параметров.**</span><span class="sxs-lookup"><span data-stu-id="34734-123">Choose **Settings** > **Device management** > **Onboarding**.</span></span> 
3. <span data-ttu-id="34734-124">В **списке Выберите операционную систему для** запуска списка процессов бортового управления выберите операционную систему.</span><span class="sxs-lookup"><span data-stu-id="34734-124">In the **Select operating system to start onboarding process** list, select an operating system.</span></span> 
4. <span data-ttu-id="34734-125">В **методе Развертывания** выберите параметр.</span><span class="sxs-lookup"><span data-stu-id="34734-125">Under **Deployment method**, select an option.</span></span> <span data-ttu-id="34734-126">Следуйте ссылкам и подсказкам на устройствах организации.</span><span class="sxs-lookup"><span data-stu-id="34734-126">Follow the links and prompts to onboard your organization's devices.</span></span> <span data-ttu-id="34734-127">Нужна помощь?</span><span class="sxs-lookup"><span data-stu-id="34734-127">Need help?</span></span> <span data-ttu-id="34734-128">См. [методы onboarding](#onboarding-methods) (в этой статье).</span><span class="sxs-lookup"><span data-stu-id="34734-128">See [Onboarding methods](#onboarding-methods) (in this article).</span></span>

### <a name="onboarding-methods"></a><span data-ttu-id="34734-129">Методы onboarding</span><span class="sxs-lookup"><span data-stu-id="34734-129">Onboarding methods</span></span>
 
<span data-ttu-id="34734-130">Методы развертывания различаются в зависимости от выбранной операционной системы.</span><span class="sxs-lookup"><span data-stu-id="34734-130">Deployment methods vary, depending on which operating system is selected.</span></span> <span data-ttu-id="34734-131">Обратитесь к ресурсам, перечисленным в таблице ниже, чтобы получить помощь в включении.</span><span class="sxs-lookup"><span data-stu-id="34734-131">Refer to the resources listed in the table below to get help with onboarding.</span></span>

|<span data-ttu-id="34734-132">Операционная система</span><span class="sxs-lookup"><span data-stu-id="34734-132">Operating system</span></span>  |<span data-ttu-id="34734-133">Метод</span><span class="sxs-lookup"><span data-stu-id="34734-133">Method</span></span>  |
|---------|---------|
|<span data-ttu-id="34734-134">Windows 10</span><span class="sxs-lookup"><span data-stu-id="34734-134">Windows 10</span></span>     |<span data-ttu-id="34734-135">- [Групповой политики](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)</span><span class="sxs-lookup"><span data-stu-id="34734-135">- [Group Policy](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)</span></span><br/><span data-ttu-id="34734-136">- [Диспетчер конфигурации](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span><span class="sxs-lookup"><span data-stu-id="34734-136">- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span></span><br/><span data-ttu-id="34734-137">- [Управление мобильными устройствами (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)</span><span class="sxs-lookup"><span data-stu-id="34734-137">- [Mobile Device Management (Intune)](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-mdm)</span></span><br/><span data-ttu-id="34734-138">- [Локальный скрипт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script)</span><span class="sxs-lookup"><span data-stu-id="34734-138">- [Local script](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script)</span></span> <br/><br/><span data-ttu-id="34734-139">**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства.</span><span class="sxs-lookup"><span data-stu-id="34734-139">**NOTE**: A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="34734-140">Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.</span><span class="sxs-lookup"><span data-stu-id="34734-140">For a production deployment, we recommend using Group Policy, Microsoft Endpoint Configuration Manager, or Intune.</span></span>         |
|<span data-ttu-id="34734-141">- Windows 8.1 Корпоративная</span><span class="sxs-lookup"><span data-stu-id="34734-141">- Windows 8.1 Enterprise</span></span> <br/><span data-ttu-id="34734-142">- Windows 8.1 Pro</span><span class="sxs-lookup"><span data-stu-id="34734-142">- Windows 8.1 Pro</span></span> <br/><span data-ttu-id="34734-143">- Windows 7 SP1 Enterprise</span><span class="sxs-lookup"><span data-stu-id="34734-143">- Windows 7 SP1 Enterprise</span></span> <br/><span data-ttu-id="34734-144">- Windows 7 SP1 Pro</span><span class="sxs-lookup"><span data-stu-id="34734-144">- Windows 7 SP1 Pro</span></span>     | [<span data-ttu-id="34734-145">Агент мониторинга Майкрософт</span><span class="sxs-lookup"><span data-stu-id="34734-145">Microsoft Monitoring Agent</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-downlevel#install-and-configure-microsoft-monitoring-agent-mma-to-report-sensor-data-to-microsoft-defender-atp)<br/><br/><span data-ttu-id="34734-146">**ПРИМЕЧАНИЕ.** Агент мониторинга Майкрософт теперь является агентом Аналитики журналов Azure.</span><span class="sxs-lookup"><span data-stu-id="34734-146">**NOTE**: Microsoft Monitoring Agent is now Azure Log Analytics agent.</span></span> <span data-ttu-id="34734-147">Дополнительные сведения см. в обзоре агента [log Analytics.](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="34734-147">To learn more, see [Log Analytics agent overview](https://docs.microsoft.com/azure/azure-monitor/platform/log-analytics-agent).</span></span>        |
|<span data-ttu-id="34734-148">- Windows Server 2019 и более поздний</span><span class="sxs-lookup"><span data-stu-id="34734-148">- Windows Server 2019 and later</span></span> <br/><span data-ttu-id="34734-149">- Основное издание Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="34734-149">- Windows Server 2019 core edition</span></span> <br/><span data-ttu-id="34734-150">- Windows Server версии 1803 и более поздней версии</span><span class="sxs-lookup"><span data-stu-id="34734-150">- Windows Server version 1803 and later</span></span> |<span data-ttu-id="34734-151">- [Локальный скрипт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script)</span><span class="sxs-lookup"><span data-stu-id="34734-151">- [Local script](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-script)</span></span> <br/><span data-ttu-id="34734-152">- [Групповой политики](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)</span><span class="sxs-lookup"><span data-stu-id="34734-152">- [Group Policy](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-gp)</span></span> <br/><span data-ttu-id="34734-153">- [Диспетчер конфигурации](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span><span class="sxs-lookup"><span data-stu-id="34734-153">- [Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm)</span></span> <br/><span data-ttu-id="34734-154">- [Диспетчер конфигурации центра системы](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager)</span><span class="sxs-lookup"><span data-stu-id="34734-154">- [System Center Configuration Manager](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-sccm#onboard-windows-10-devices-using-earlier-versions-of-system-center-configuration-manager)</span></span> <br/><span data-ttu-id="34734-155">- [Скрипты на борту VDI для нестандартных устройств](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi)</span><span class="sxs-lookup"><span data-stu-id="34734-155">- [VDI onboarding scripts for non-persistent devices](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-vdi)</span></span> <br/><br/><span data-ttu-id="34734-156">**ПРИМЕЧАНИЕ.** Локальный сценарий подходит для доказательства концепции, но не должен использоваться для развертывания производства.</span><span class="sxs-lookup"><span data-stu-id="34734-156">**NOTE**: A local script is suitable for a proof of concept but should not be used for production deployment.</span></span> <span data-ttu-id="34734-157">Для развертывания производства рекомендуется использовать групповую политику, Microsoft Endpoint Configuration Manager или Intune.</span><span class="sxs-lookup"><span data-stu-id="34734-157">For a production deployment, we recommend using Group Policy, Microsoft Endpoint Configuration Manager, or Intune.</span></span>    |
|<span data-ttu-id="34734-158">- Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="34734-158">- Windows Server 2016</span></span> <br/><span data-ttu-id="34734-159">- Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="34734-159">- Windows Server 2012 R2</span></span> <br/><span data-ttu-id="34734-160">- Windows Server 2008 R2 SP1</span><span class="sxs-lookup"><span data-stu-id="34734-160">- Windows Server 2008 R2 SP1</span></span>  |<span data-ttu-id="34734-161">- [Центр безопасности Защитника Майкрософт](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)</span><span class="sxs-lookup"><span data-stu-id="34734-161">- [Microsoft Defender Security Center](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-server-endpoints#option-1-onboard-servers-through-microsoft-defender-security-center)</span></span><br/><span data-ttu-id="34734-162">- [Центр безопасности Azure](https://docs.microsoft.com/azure/security-center/security-center-wdatp)</span><span class="sxs-lookup"><span data-stu-id="34734-162">- [Azure Security Center](https://docs.microsoft.com/azure/security-center/security-center-wdatp)</span></span> |
|<span data-ttu-id="34734-163">macOS</span><span class="sxs-lookup"><span data-stu-id="34734-163">macOS</span></span><br/><span data-ttu-id="34734-164">- 10.15 (Каталина)</span><span class="sxs-lookup"><span data-stu-id="34734-164">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="34734-165">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="34734-165">- 10.14 (Mojave)</span></span><br/><span data-ttu-id="34734-166">- 10.13 (Высокая сьерра)</span><span class="sxs-lookup"><span data-stu-id="34734-166">- 10.13 (High Sierra)</span></span><br/><br/><span data-ttu-id="34734-167">iOS</span><span class="sxs-lookup"><span data-stu-id="34734-167">iOS</span></span><br/><br/><span data-ttu-id="34734-168">Linux:</span><span class="sxs-lookup"><span data-stu-id="34734-168">Linux:</span></span><br/><span data-ttu-id="34734-169">- RHEL 7.2+</span><span class="sxs-lookup"><span data-stu-id="34734-169">- RHEL 7.2+</span></span><br/><span data-ttu-id="34734-170">- CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="34734-170">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="34734-171">- Ubuntu 16 LTS или более высокий LTS</span><span class="sxs-lookup"><span data-stu-id="34734-171">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="34734-172">- SLES 12+</span><span class="sxs-lookup"><span data-stu-id="34734-172">- SLES 12+</span></span><br/><span data-ttu-id="34734-173">- Debian 9+</span><span class="sxs-lookup"><span data-stu-id="34734-173">- Debian 9+</span></span><br/><span data-ttu-id="34734-174">- Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="34734-174">- Oracle Linux 7.2</span></span> |[<span data-ttu-id="34734-175">Onboard non-Windows devices</span><span class="sxs-lookup"><span data-stu-id="34734-175">Onboard non-Windows devices</span></span>](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-endpoints-non-windows)  |

## <a name="run-a-detection-test"></a><span data-ttu-id="34734-176">Выполнить тест обнаружения</span><span class="sxs-lookup"><span data-stu-id="34734-176">Run a detection test</span></span>

<span data-ttu-id="34734-177">Чтобы убедиться, что бортовые устройства подключены должным образом к Microsoft Defender для конечной точки, можно выполнить тест обнаружения.</span><span class="sxs-lookup"><span data-stu-id="34734-177">To verify that your onboarded devices are properly connected to Microsoft Defender for Endpoint, you can run a detection test.</span></span>

|<span data-ttu-id="34734-178">Операционная система</span><span class="sxs-lookup"><span data-stu-id="34734-178">Operating system</span></span>  |<span data-ttu-id="34734-179">Рекомендации</span><span class="sxs-lookup"><span data-stu-id="34734-179">Guidance</span></span>  |
|---------|---------|
|<span data-ttu-id="34734-180">- Windows 10</span><span class="sxs-lookup"><span data-stu-id="34734-180">- Windows 10</span></span> <br/><span data-ttu-id="34734-181">- Windows Server 2019</span><span class="sxs-lookup"><span data-stu-id="34734-181">- Windows Server 2019</span></span> <br/><span data-ttu-id="34734-182">- Windows Server, версия 1803</span><span class="sxs-lookup"><span data-stu-id="34734-182">- Windows Server, version 1803</span></span> <br/><span data-ttu-id="34734-183">- Windows Server 2016</span><span class="sxs-lookup"><span data-stu-id="34734-183">- Windows Server 2016</span></span> <br/><span data-ttu-id="34734-184">- Windows Server 2012 R2</span><span class="sxs-lookup"><span data-stu-id="34734-184">- Windows Server 2012 R2</span></span>     |<span data-ttu-id="34734-185">См. [тест run a detection](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test).</span><span class="sxs-lookup"><span data-stu-id="34734-185">See [Run a detection test](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/run-detection-test).</span></span> <br/><br/><span data-ttu-id="34734-186">Посетите сайт демонстрационных сценариев Microsoft Defender for Endpoint () и попробуйте один или [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) несколько сценариев.</span><span class="sxs-lookup"><span data-stu-id="34734-186">Visit the Microsoft Defender for Endpoint demo scenarios site ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)) and try one or more of the scenarios.</span></span> <span data-ttu-id="34734-187">Например, попробуйте демонстрационный сценарий **облачной** защиты.</span><span class="sxs-lookup"><span data-stu-id="34734-187">For example, try the **Cloud-delivered protection** demo scenario.</span></span>         |
|<span data-ttu-id="34734-188">macOS</span><span class="sxs-lookup"><span data-stu-id="34734-188">macOS</span></span><br/><span data-ttu-id="34734-189">- 10.15 (Каталина)</span><span class="sxs-lookup"><span data-stu-id="34734-189">- 10.15 (Catalina)</span></span><br/><span data-ttu-id="34734-190">- 10.14 (Mojave)</span><span class="sxs-lookup"><span data-stu-id="34734-190">- 10.14 (Mojave)</span></span><br/><span data-ttu-id="34734-191">- 10.13 (Высокая сьерра)</span><span class="sxs-lookup"><span data-stu-id="34734-191">- 10.13 (High Sierra)</span></span>     |<span data-ttu-id="34734-192">Скачайте и используйте приложение DIY по [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy) ссылке .</span><span class="sxs-lookup"><span data-stu-id="34734-192">Download and use the DIY app at [https://aka.ms/mdatpmacosdiy](https://aka.ms/mdatpmacosdiy).</span></span> <br/><br/><span data-ttu-id="34734-193">Дополнительные сведения см. [в веб-сайте Microsoft Defender для конечной точки для Mac.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac)</span><span class="sxs-lookup"><span data-stu-id="34734-193">For more information, see [Microsoft Defender for Endpoint for Mac](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-mac).</span></span>        |
|<span data-ttu-id="34734-194">Linux:</span><span class="sxs-lookup"><span data-stu-id="34734-194">Linux:</span></span><br/><span data-ttu-id="34734-195">- RHEL 7.2+</span><span class="sxs-lookup"><span data-stu-id="34734-195">- RHEL 7.2+</span></span><br/><span data-ttu-id="34734-196">- CentOS Linux 7.2+</span><span class="sxs-lookup"><span data-stu-id="34734-196">- CentOS Linux 7.2+</span></span><br/><span data-ttu-id="34734-197">- Ubuntu 16 LTS или более высокий LTS</span><span class="sxs-lookup"><span data-stu-id="34734-197">- Ubuntu 16 LTS, or higher LTS</span></span><br/><span data-ttu-id="34734-198">- SLES 12+</span><span class="sxs-lookup"><span data-stu-id="34734-198">- SLES 12+</span></span><br/><span data-ttu-id="34734-199">- Debian 9+</span><span class="sxs-lookup"><span data-stu-id="34734-199">- Debian 9+</span></span><br/><span data-ttu-id="34734-200">- Oracle Linux 7.2</span><span class="sxs-lookup"><span data-stu-id="34734-200">- Oracle Linux 7.2</span></span> |<span data-ttu-id="34734-201">1. Выполнить следующую команду и искать результат **1**:</span><span class="sxs-lookup"><span data-stu-id="34734-201">1. Run the following command, and look for a result of **1**:</span></span> <br/><span data-ttu-id="34734-202">`mdatp health --field real_time_protection_enabled`.</span><span class="sxs-lookup"><span data-stu-id="34734-202">`mdatp health --field real_time_protection_enabled`.</span></span> <br/><br/><span data-ttu-id="34734-203">2. Откройте окно терминала и запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="34734-203">2. Open a Terminal window, and run the following command:</span></span> <br/><span data-ttu-id="34734-204">`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`.</span><span class="sxs-lookup"><span data-stu-id="34734-204">`curl -o ~/Downloads/eicar.com.txt https://www.eicar.org/download/eicar.com.txt`.</span></span> <br/><br/><span data-ttu-id="34734-205">3. Запустите следующую команду, чтобы перечислить все обнаруженные угрозы:</span><span class="sxs-lookup"><span data-stu-id="34734-205">3. Run the following command to list any detected threats:</span></span> <br/><span data-ttu-id="34734-206">`mdatp threat list`.</span><span class="sxs-lookup"><span data-stu-id="34734-206">`mdatp threat list`.</span></span> <br/><br/><span data-ttu-id="34734-207">Дополнительные сведения см. в [веб-сайте ATP Microsoft Defender для Linux.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux)</span><span class="sxs-lookup"><span data-stu-id="34734-207">For more information, see [Microsoft Defender ATP for Linux](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/microsoft-defender-atp-linux).</span></span> |

## <a name="uninstall-your-non-microsoft-solution"></a><span data-ttu-id="34734-208">Отостановка решения, не влияемого на Корпорацию Майкрософт</span><span class="sxs-lookup"><span data-stu-id="34734-208">Uninstall your non-Microsoft solution</span></span>

<span data-ttu-id="34734-209">Теперь, когда вы перенастроили устройства организации в Microsoft Defender для конечной точки, следующим шагом будет удалить решение по защите конечных точек, не в microsoft.</span><span class="sxs-lookup"><span data-stu-id="34734-209">Now that you have onboarded your organization's devices to Microsoft Defender for Endpoint, your next step is to uninstall your non-Microsoft endpoint protection solution.</span></span>

<span data-ttu-id="34734-210">Чтобы получить помощь на этом шаге, протянуть службу технической поддержки поставщика решений.</span><span class="sxs-lookup"><span data-stu-id="34734-210">To get help with this step, reach out to your solution provider's technical support team.</span></span>

## <a name="make-sure-microsoft-defender-for-endpoint-is-in-active-mode"></a><span data-ttu-id="34734-211">Убедитесь, что Microsoft Defender для конечной точки находится в активном режиме</span><span class="sxs-lookup"><span data-stu-id="34734-211">Make sure Microsoft Defender for Endpoint is in active mode</span></span>

<span data-ttu-id="34734-212">Теперь, когда вы отключили решение по защите конечной точки, не от Microsoft, следующим шагом будет обеспечение включения антивируса Microsoft Defender и Microsoft Defender для конечной точки в активном режиме.</span><span class="sxs-lookup"><span data-stu-id="34734-212">Now that you have uninstalled your non-Microsoft endpoint protection solution, your next step is to make sure that Microsoft Defender Antivirus and Microsoft Defender for Endpoint are enabled and in active mode.</span></span>

<span data-ttu-id="34734-213">Для этого посетите веб-сайт демонстрационных сценариев Microsoft Defender for Endpoint [https://demo.wd.microsoft.com](https://demo.wd.microsoft.com) ().</span><span class="sxs-lookup"><span data-stu-id="34734-213">To do this, visit the Microsoft Defender for Endpoint demo scenarios site ([https://demo.wd.microsoft.com](https://demo.wd.microsoft.com)).</span></span> <span data-ttu-id="34734-214">Попробуйте один или несколько демонстрационных сценариев на этой странице, включая по крайней мере следующие:</span><span class="sxs-lookup"><span data-stu-id="34734-214">Try one or more of the demo scenarios on that page, including at least the following:</span></span>
- <span data-ttu-id="34734-215">Защита с облачным доставкой</span><span class="sxs-lookup"><span data-stu-id="34734-215">Cloud-delivered protection</span></span>
- <span data-ttu-id="34734-216">Потенциально нежелательные приложения (PUA)</span><span class="sxs-lookup"><span data-stu-id="34734-216">Potentially Unwanted Applications (PUA)</span></span>
- <span data-ttu-id="34734-217">Защита сети (NP)</span><span class="sxs-lookup"><span data-stu-id="34734-217">Network Protection (NP)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="34734-218">Если вы используете Windows Server 2016, вам может потребоваться запустить антивирус Microsoft Defender вручную.</span><span class="sxs-lookup"><span data-stu-id="34734-218">If you are using Windows Server 2016, you might have to start Microsoft Defender Antivirus manually.</span></span> <span data-ttu-id="34734-219">Это можно сделать с помощью cmdlet PowerShell `mpcmdrun.exe -wdenable` на устройстве.</span><span class="sxs-lookup"><span data-stu-id="34734-219">You can do this by using the PowerShell cmdlet `mpcmdrun.exe -wdenable` on the device.</span></span>

## <a name="next-steps"></a><span data-ttu-id="34734-220">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="34734-220">Next steps</span></span>

<span data-ttu-id="34734-221">**Поздравляем!**</span><span class="sxs-lookup"><span data-stu-id="34734-221">**Congratulations**!</span></span> <span data-ttu-id="34734-222">Вы завершили [миграцию в Microsoft Defender для конечной точки!](switch-to-microsoft-defender-migration.md#the-migration-process)</span><span class="sxs-lookup"><span data-stu-id="34734-222">You have completed your [migration to Microsoft Defender for Endpoint](switch-to-microsoft-defender-migration.md#the-migration-process)!</span></span> 

- <span data-ttu-id="34734-223">[Посетите панель мониторинга операций безопасности](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) в Центре безопасности Защитника Майкрософт [https://aka.ms/MDATPportal](https://aka.ms/MDATPportal) ().</span><span class="sxs-lookup"><span data-stu-id="34734-223">[Visit your security operations dashboard](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/security-operations-dashboard) in the Microsoft Defender Security Center ([https://aka.ms/MDATPportal](https://aka.ms/MDATPportal)).</span></span> 
- <span data-ttu-id="34734-224">[Управление Microsoft Defender для конечной точки, после миграции.](manage-atp-post-migration.md)</span><span class="sxs-lookup"><span data-stu-id="34734-224">[Manage Microsoft Defender for Endpoint, post migration](manage-atp-post-migration.md).</span></span>