---
title: Microsoft Defender для конечной точки на Mac — расширения системы (Предварительный просмотр)
description: В этой статье содержатся инструкции по оценке функций расширения системы Microsoft Defender для конечной точки на Mac. Эта функция в настоящее время находится в публичном предварительном просмотре.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, mac, kernel, system, extensions, catalina
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: security
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ROBOTS: noindex,nofollow
ms.technology: mde
ms.openlocfilehash: cc148bcc0b2623eaaa8d31ef50708174264fa3b2
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51934949"
---
# <a name="microsoft-defender-for-endpoint-on-macos---system-extensions-public-preview"></a><span data-ttu-id="dc85e-105">Microsoft Defender для конечной точки на macOS — общедоступный предварительный просмотр расширений системы)</span><span class="sxs-lookup"><span data-stu-id="dc85e-105">Microsoft Defender for Endpoint on macOS - system extensions public preview)</span></span>

<span data-ttu-id="dc85e-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="dc85e-106">**Applies to:**</span></span>
- [<span data-ttu-id="dc85e-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="dc85e-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="dc85e-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="dc85e-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="dc85e-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="dc85e-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="dc85e-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="dc85e-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="dc85e-111">В соответствии с эволюцией macOS мы готовим обновление Defender для endpoint на Mac, которое использует расширения системы вместо расширения ядра.</span><span class="sxs-lookup"><span data-stu-id="dc85e-111">In alignment with macOS evolution, we are preparing a Defender for Endpoint on Mac update that leverages system extensions instead of kernel extensions.</span></span> <span data-ttu-id="dc85e-112">Это обновление будет применяться только к macOS Catalina (10.15.4) и более поздним версиям macOS.</span><span class="sxs-lookup"><span data-stu-id="dc85e-112">This update will only apply to macOS Catalina (10.15.4) and later versions of macOS.</span></span>

<span data-ttu-id="dc85e-113">Эта функция в настоящее время находится в публичном предварительном просмотре.</span><span class="sxs-lookup"><span data-stu-id="dc85e-113">This functionality is currently in public preview.</span></span> <span data-ttu-id="dc85e-114">В этой статье описывается, как включить эту функцию на вашем устройстве.</span><span class="sxs-lookup"><span data-stu-id="dc85e-114">This article describes how to enable this functionality on your device.</span></span> <span data-ttu-id="dc85e-115">Вы можете попробовать эту функцию локально на своем устройстве или настроить ее удаленно с помощью средства управления.</span><span class="sxs-lookup"><span data-stu-id="dc85e-115">You can try out this feature locally on your own device or configure it remotely through a management tool.</span></span>

<span data-ttu-id="dc85e-116">Эти действия предполагают, что на устройстве уже запущен Защитник для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="dc85e-116">These steps assume you already have Defender for Endpoint running on your device.</span></span> <span data-ttu-id="dc85e-117">Дополнительные сведения см. [на этой странице.](microsoft-defender-endpoint-mac.md)</span><span class="sxs-lookup"><span data-stu-id="dc85e-117">For more information, see [this page](microsoft-defender-endpoint-mac.md).</span></span>

## <a name="known-issues"></a><span data-ttu-id="dc85e-118">Известные проблемы</span><span class="sxs-lookup"><span data-stu-id="dc85e-118">Known issues</span></span>

- <span data-ttu-id="dc85e-119">Мы получили сообщения о том, что расширение сети вмешивается в расширение Apple SSO Kerberos.</span><span class="sxs-lookup"><span data-stu-id="dc85e-119">We’ve received reports of the network extension interfering with the Apple SSO Kerberos extension.</span></span>
- <span data-ttu-id="dc85e-120">В текущей версии продукта по-прежнему устанавливается расширение ядра.</span><span class="sxs-lookup"><span data-stu-id="dc85e-120">The current version of the product still installs a kernel extension.</span></span> <span data-ttu-id="dc85e-121">Расширение ядра используется только в качестве механизма отката и будет удалено до того, как эта функция достигнет общего просмотра.</span><span class="sxs-lookup"><span data-stu-id="dc85e-121">The kernel extension is only used as a fallback mechanism and will be removed before this feature reaches public preview.</span></span>
- <span data-ttu-id="dc85e-122">Мы по-прежнему работаем над версией продукта, которая развертывается и функционирует должным образом на macOS 11 Big Sur.</span><span class="sxs-lookup"><span data-stu-id="dc85e-122">We're still working on a product version that deploys and functions properly on macOS 11 Big Sur.</span></span>

## <a name="deployment-prerequisites"></a><span data-ttu-id="dc85e-123">Предпосылки развертывания</span><span class="sxs-lookup"><span data-stu-id="dc85e-123">Deployment prerequisites</span></span>

- <span data-ttu-id="dc85e-124">Минимальная версия операционной системы macOS: **10.15.4**</span><span class="sxs-lookup"><span data-stu-id="dc85e-124">Minimum macOS operating system version: **10.15.4**</span></span>
- <span data-ttu-id="dc85e-125">Минимальная версия продукта: **101.03.73**</span><span class="sxs-lookup"><span data-stu-id="dc85e-125">Minimum product version: **101.03.73**</span></span>
- <span data-ttu-id="dc85e-126">Устройство должно быть в канале быстрого обновления **Insider.**</span><span class="sxs-lookup"><span data-stu-id="dc85e-126">Your device must be in the **Insider Fast update channel**.</span></span> <span data-ttu-id="dc85e-127">Вы можете проверить канал обновления, используя следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc85e-127">You can check the update channel by using the following command:</span></span>

  ```bash
  mdatp health --field release_ring
  ```

  <span data-ttu-id="dc85e-128">Если устройство еще не находится в канале быстрого обновления Insider, выполните следующую команду из терминала.</span><span class="sxs-lookup"><span data-stu-id="dc85e-128">If your device isn't already in the Insider Fast update channel, execute the following command from the Terminal.</span></span> <span data-ttu-id="dc85e-129">Обновление канала вступает в силу при следующем старте продукта (при установке следующего обновления продукта или при перезагрузке устройства).</span><span class="sxs-lookup"><span data-stu-id="dc85e-129">The channel update takes effect the next time the product starts (when the next product update is installed, or when the device is rebooted).</span></span>

  ```bash
  defaults write com.microsoft.autoupdate2 ChannelName -string Beta
  ```

  <span data-ttu-id="dc85e-130">Кроме того, если вы в управляемой среде (JAMF или Intune), вы можете настроить канал обновления удаленно.</span><span class="sxs-lookup"><span data-stu-id="dc85e-130">Alternatively, if you're in a managed environment (JAMF or Intune), you can configure the update channel remotely.</span></span> <span data-ttu-id="dc85e-131">Дополнительные сведения см. в [ссылке Развертывание обновлений для Microsoft Defender для конечной](mac-updates.md#set-the-channel-name)точки на Mac: Установите имя канала.</span><span class="sxs-lookup"><span data-stu-id="dc85e-131">For more information, see [Deploy updates for Microsoft Defender for Endpoint on Mac: Set the channel name](mac-updates.md#set-the-channel-name).</span></span>

## <a name="deployment-steps"></a><span data-ttu-id="dc85e-132">Действия по развертыванию</span><span class="sxs-lookup"><span data-stu-id="dc85e-132">Deployment steps</span></span>

<span data-ttu-id="dc85e-133">Выполните действия развертывания, соответствующие вашей среде, и предпочтительный метод о попробовать эту функцию.</span><span class="sxs-lookup"><span data-stu-id="dc85e-133">Follow the deployment steps that correspond to your environment and your preferred method of trying out this feature.</span></span>

### <a name="manual-deployment"></a><span data-ttu-id="dc85e-134">Ручное развертывание</span><span class="sxs-lookup"><span data-stu-id="dc85e-134">Manual deployment</span></span>

#### <a name="approve-the-system-extensions-and-enable-the-network-extension"></a><span data-ttu-id="dc85e-135">Утверждение расширений системы и расширение сети</span><span class="sxs-lookup"><span data-stu-id="dc85e-135">Approve the system extensions and enable the network extension</span></span>

1. <span data-ttu-id="dc85e-136">После того как все необходимые условия развертывания будут выполнены, перезапустите устройство, чтобы запустить процесс утверждения и активации расширения системы.</span><span class="sxs-lookup"><span data-stu-id="dc85e-136">After all deployment prerequisites are met, restart your device to launch the system extension approval and activation process.</span></span>

   <span data-ttu-id="dc85e-137">Вы увидите серию системных подсказок для утверждения расширений системы Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="dc85e-137">You'll see a series of system prompts to approve the Defender for Endpoint system extensions.</span></span> <span data-ttu-id="dc85e-138">Необходимо утвердить **все** подсказки из серии, так как macOS требует явного утверждения для каждого расширения, которое defender for Endpoint на Mac устанавливает на устройстве.</span><span class="sxs-lookup"><span data-stu-id="dc85e-138">You must approve **all** prompts from the series, because macOS requires an explicit approval for each extension that Defender for Endpoint on Mac installs on the device.</span></span>
   
   <span data-ttu-id="dc85e-139">Для каждого утверждения выберите **параметры Open Security Preferences** и выберите **Разрешить** разрешить запуск расширения системы.</span><span class="sxs-lookup"><span data-stu-id="dc85e-139">For each approval, select **Open Security Preferences** and then select **Allow** to allow the system extension to run.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="dc85e-140">Необходимо закрыть и открыть окно **безопасности системных**  >  **предпочтений & конфиденциальности** между последующими утверждениями.</span><span class="sxs-lookup"><span data-stu-id="dc85e-140">You must close and reopen the **System Preferences** > **Security & Privacy** window between subsequent approvals.</span></span> <span data-ttu-id="dc85e-141">В противном случае macOS не будет отображать следующее утверждение.</span><span class="sxs-lookup"><span data-stu-id="dc85e-141">Otherwise, macOS will not display the next approval.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="dc85e-142">Перед тем, как продукт возвращается к расширению ядра, существует минутное время.</span><span class="sxs-lookup"><span data-stu-id="dc85e-142">There is a one-minute timeout before the product falls back to the kernel extension.</span></span> <span data-ttu-id="dc85e-143">Это гарантирует защиту устройства.</span><span class="sxs-lookup"><span data-stu-id="dc85e-143">This ensures that the device is protected.</span></span>
   >
   > <span data-ttu-id="dc85e-144">Если у вас больше минуты, перезапустите daemon, перезагрузив устройство или снова с помощью запуска `sudo killall -9 wdavdaemon` потока утверждения.</span><span class="sxs-lookup"><span data-stu-id="dc85e-144">If more than one minute elapses, restart the daemon by rebooting the device or by using `sudo killall -9 wdavdaemon` to trigger the approval flow again.</span></span>

   ![Всплывающее всплыв](images/mac-system-extension-approval.png)

   ![Окно утверждения расширения системы](images/mac-system-extension-pref.png)

1. <span data-ttu-id="dc85e-147">После утверждения расширений системы macOS запросит утверждение для фильтрации сетевого трафика.</span><span class="sxs-lookup"><span data-stu-id="dc85e-147">After the system extensions are approved, macOS prompts for an approval to allow network traffic to be filtered.</span></span> <span data-ttu-id="dc85e-148">Нажмите **кнопку Разрешить**.</span><span class="sxs-lookup"><span data-stu-id="dc85e-148">Click **Allow**.</span></span>

   ![Всплывающее всплыв](images/mac-system-extension-filter.png)

#### <a name="grant-full-disk-access-to-the-endpoint-security-system-extension"></a><span data-ttu-id="dc85e-150">Предоставление полного доступа к диску для расширения системы безопасности конечных точек</span><span class="sxs-lookup"><span data-stu-id="dc85e-150">Grant Full Disk Access to the Endpoint Security system extension</span></span>

<span data-ttu-id="dc85e-151">Откройте **вкладку Безопасность** системных  >  **предпочтений & конфиденциальности** и предоставить полный дисковый доступ к расширению безопасности конечной точки  >   Microsoft **Defender.** </span><span class="sxs-lookup"><span data-stu-id="dc85e-151">Open the **System Preferences** > **Security & Privacy** > **Privacy** tab and grant **Full Disk Access** to the **Microsoft Defender Endpoint Security Extension**.</span></span>

![Полный доступ к диску для расширения системы безопасности конечной точки](images/mac-system-extension-fda.png)

#### <a name="reboot-your-device"></a><span data-ttu-id="dc85e-153">Перезагрузка устройства</span><span class="sxs-lookup"><span data-stu-id="dc85e-153">Reboot your device</span></span>

<span data-ttu-id="dc85e-154">Чтобы изменения вступили в силу, необходимо перезагрузать устройство.</span><span class="sxs-lookup"><span data-stu-id="dc85e-154">In order for the changes to take effect, you must reboot your device.</span></span>

#### <a name="verify-that-the-system-extensions-are-running"></a><span data-ttu-id="dc85e-155">Убедитесь, что расширения системы запущены</span><span class="sxs-lookup"><span data-stu-id="dc85e-155">Verify that the system extensions are running</span></span>

<span data-ttu-id="dc85e-156">Из терминала запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc85e-156">From the Terminal, run the following command:</span></span>

```bash
mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="dc85e-157">Вывод `endpoint_security_extension` терминала указывает, что продукт использует функции расширения системы.</span><span class="sxs-lookup"><span data-stu-id="dc85e-157">Terminal output `endpoint_security_extension` indicates the product is using the system extensions functionality.</span></span>

### <a name="managed-deployment"></a><span data-ttu-id="dc85e-158">Управляемое развертывание</span><span class="sxs-lookup"><span data-stu-id="dc85e-158">Managed deployment</span></span>

<span data-ttu-id="dc85e-159">Обратитесь к новым профилям конфигурации [для macOS Catalina](mac-sysext-policies.md#jamf) и более новым версиям macOS: JAMF для новых профилей конфигурации, которые необходимо развернуть для этой новой функции.</span><span class="sxs-lookup"><span data-stu-id="dc85e-159">Refer to [New configuration profiles for macOS Catalina and newer versions of macOS: JAMF](mac-sysext-policies.md#jamf) for the new configuration profiles you must deploy for this new feature.</span></span>

<span data-ttu-id="dc85e-160">В дополнение к этим профилям убедитесь, что целевые устройства должны быть в канале быстрого обновления Insider, как описано в [предпосылках развертывания.](#deployment-prerequisites)</span><span class="sxs-lookup"><span data-stu-id="dc85e-160">In addition to those profiles, make sure to configure the target devices to be in the Insider Fast update channel, as described in [Deployment prerequisites](#deployment-prerequisites).</span></span>

<span data-ttu-id="dc85e-161">На устройстве, где выполнены все необходимые условия и развернуты новые профили конфигурации, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc85e-161">On a device where all prerequisites are met and the new configuration profiles have been deployed, run the following command:</span></span>

```bash
$ mdatp health --field real_time_protection_subsystem
```

<span data-ttu-id="dc85e-162">Если эта команда печатает, `endpoint_security_extension` продукт использует функции расширения системы.</span><span class="sxs-lookup"><span data-stu-id="dc85e-162">If this command prints `endpoint_security_extension`, the product is using the system extensions functionality.</span></span>

## <a name="validate-basic-scenarios"></a><span data-ttu-id="dc85e-163">Проверка базовых сценариев</span><span class="sxs-lookup"><span data-stu-id="dc85e-163">Validate basic scenarios</span></span>

1. <span data-ttu-id="dc85e-164">Тестирование обнаружения европейского института компьютерных антивирусных исследований (EICAR).</span><span class="sxs-lookup"><span data-stu-id="dc85e-164">Test European Institute for Computer Antivirus Research (EICAR) detection.</span></span> <span data-ttu-id="dc85e-165">Из окна терминала запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc85e-165">From a Terminal window, run the following command:</span></span>

   ```bash
   curl -o eicar.txt https://secure.eicar.org/eicar.com.txt
   ```

   <span data-ttu-id="dc85e-166">Убедитесь, что файл EICAR находится на карантине.</span><span class="sxs-lookup"><span data-stu-id="dc85e-166">Verify that the EICAR file is quarantined.</span></span> <span data-ttu-id="dc85e-167">Вы можете проверить состояние файла на странице История защиты в пользовательском интерфейсе или из командной строки с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="dc85e-167">You can verify the file's status on the Protection History page in the user interface, or from a command line by using the following command:</span></span>

    ```bash
    mdatp threat list
    ```

2. <span data-ttu-id="dc85e-168">Проверьте сценарий DIY обнаружения конечных точек и ответов (EDR).</span><span class="sxs-lookup"><span data-stu-id="dc85e-168">Test the Endpoint Detection and Response (EDR) DIY scenario.</span></span> <span data-ttu-id="dc85e-169">Из окна терминала запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="dc85e-169">From a terminal window, run the following command:</span></span>

   ```bash
   curl -o "MDATP MacOS DIY.zip" https://aka.ms/mdatpmacosdiy
   ```

   <span data-ttu-id="dc85e-170">Проверка того, что на портале на странице машины для сценариев EICAR и EDR DIY появились два оповещения.</span><span class="sxs-lookup"><span data-stu-id="dc85e-170">Validate that two alerts popped up in the portal on the machine page for EICAR and EDR DIY scenarios.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="dc85e-171">Вопросы и ответы</span><span class="sxs-lookup"><span data-stu-id="dc85e-171">Frequently asked questions</span></span>

- <span data-ttu-id="dc85e-172">В. Почему я все еще вижу при `kernel_extension` `mdatp health --field real_time_protection_subsystem` запуске?</span><span class="sxs-lookup"><span data-stu-id="dc85e-172">Q: Why am I still seeing `kernel_extension` when I run `mdatp health --field real_time_protection_subsystem`?</span></span>

    <span data-ttu-id="dc85e-173">Ответ: Переназначься в раздел [Предварительные](#deployment-prerequisites) условия развертывания и дважды проверьте, выполнены ли все необходимые условия.</span><span class="sxs-lookup"><span data-stu-id="dc85e-173">A: Refer back to the [Deployment prerequisites](#deployment-prerequisites) section and double-check that all prerequisites are met.</span></span> <span data-ttu-id="dc85e-174">Если все необходимые условия выполнены, перезапустите устройство и повторите проверку.</span><span class="sxs-lookup"><span data-stu-id="dc85e-174">If all prerequisites are met, restart your device and check again.</span></span>

- <span data-ttu-id="dc85e-175">В. Когда будет поддерживаться macOS 11 Big Sur?</span><span class="sxs-lookup"><span data-stu-id="dc85e-175">Q: When will macOS 11 Big Sur be supported?</span></span>

    <span data-ttu-id="dc85e-176">О. Мы активно работаем над добавлением поддержки macOS 11.</span><span class="sxs-lookup"><span data-stu-id="dc85e-176">A: We are actively working on adding support for macOS 11.</span></span> <span data-ttu-id="dc85e-177">Дополнительные сведения мы выложим на новую [страницу What's.](mac-whatsnew.md)</span><span class="sxs-lookup"><span data-stu-id="dc85e-177">We will post more information to the [What's new](mac-whatsnew.md) page.</span></span>
