---
title: Включим облачную защиту в антивирусе Microsoft Defender
description: Включаем облачную защиту, чтобы воспользоваться возможностями быстрой и продвинутой защиты.
keywords: Антивирус Microsoft Defender, антивирусные программы, безопасность, облако, блок с первого взгляда
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 11/13/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: cfaf4563e96568ae26bd990678462836b9202656
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691477"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="e8b14-104">Включаем облачную защиту</span><span class="sxs-lookup"><span data-stu-id="e8b14-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="e8b14-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e8b14-105">**Applies to:**</span></span>

- [<span data-ttu-id="e8b14-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e8b14-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="e8b14-107">Облачная служба антивирусной защиты Microsoft Defender — это механизм доставки обновленной защиты в сеть и конечные точки.</span><span class="sxs-lookup"><span data-stu-id="e8b14-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="e8b14-108">Хотя это называется облачной службой, это не просто защита файлов, хранимых в облаке; вместо этого он использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, значительно более быстрой, чем традиционные обновления службы безопасности.</span><span class="sxs-lookup"><span data-stu-id="e8b14-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="e8b14-109">Антивирус Microsoft Defender использует несколько технологий обнаружения и предотвращения для обеспечения точной и интеллектуальной защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="e8b14-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="e8b14-110">[Узнать о передовых технологиях в центре защиты Microsoft Defender для endpoint следующего поколения.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="e8b14-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="e8b14-111">![Список av-двигателей Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="e8b14-111">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="e8b14-112">Можно включить или отключить облачную защиту антивирусного антивируса Microsoft Defender несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="e8b14-112">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="e8b14-113">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e8b14-113">Microsoft Intune</span></span>
- <span data-ttu-id="e8b14-114">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="e8b14-114">Microsoft Endpoint Configuration Manager</span></span>
- <span data-ttu-id="e8b14-115">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="e8b14-115">Group Policy</span></span>
- <span data-ttu-id="e8b14-116">Cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="e8b14-116">PowerShell cmdlets.</span></span>

 <span data-ttu-id="e8b14-117">Вы также можете включить его или отключить в отдельных клиентах с помощью приложения Windows Security.</span><span class="sxs-lookup"><span data-stu-id="e8b14-117">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="e8b14-118">См. [в обзоре](cloud-protection-microsoft-defender-antivirus.md) облачной защиты антивирусной защиты Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e8b14-118">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="e8b14-119">Дополнительные сведения о конкретных требованиях к сетевому подключению, чтобы конечные точки могли подключаться к службе защиты с облачной доставкой, см. в статью Настройка и проверка [сетевых подключений.](configure-network-connections-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e8b14-119">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="e8b14-120">В Windows 10 нет разницы  между  основными и расширенными вариантами отчетности, описанными в этом разделе.</span><span class="sxs-lookup"><span data-stu-id="e8b14-120">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="e8b14-121">Это устаревшее различие, и выбор любого параметра приведет к такому же уровню облачной защиты.</span><span class="sxs-lookup"><span data-stu-id="e8b14-121">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="e8b14-122">Нет разницы в типе или количестве общих сведений.</span><span class="sxs-lookup"><span data-stu-id="e8b14-122">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="e8b14-123">Дополнительные сведения о том, что мы собираем, см. в [заявлении о конфиденциальности Майкрософт.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="e8b14-123">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e8b14-124">Использование Intune для включаемой облачной защиты</span><span class="sxs-lookup"><span data-stu-id="e8b14-124">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="e8b14-125">Перейдите в центр администрирования диспетчера конечных точек Майкрософт () и [https://endpoint.microsoft.com](https://endpoint.microsoft.com) войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="e8b14-125">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="e8b14-126">На **домашней области** выберите **конфигурацию устройства > профилей.**</span><span class="sxs-lookup"><span data-stu-id="e8b14-126">On the **Home** pane, select **Device configuration > Profiles**.</span></span>
3. <span data-ttu-id="e8b14-127">Выберите тип **профиля ограничений** устройства, который необходимо настроить.</span><span class="sxs-lookup"><span data-stu-id="e8b14-127">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="e8b14-128">Если требуется создать новый **тип** профилей ограничений устройств, см. в странице Настройка параметров ограничения устройств [в Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="e8b14-128">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="e8b14-129">Выберите **параметры**  >  **конфигурации свойств: изменить** антивирус Microsoft  >  **Defender.**</span><span class="sxs-lookup"><span data-stu-id="e8b14-129">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>
5. <span data-ttu-id="e8b14-130">В **облачном коммутаторе защиты** выберите **Включить**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-130">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>
6. <span data-ttu-id="e8b14-131">В **запросе пользователей перед отсевом** образца отправки выберите **отправить все данные автоматически.**</span><span class="sxs-lookup"><span data-stu-id="e8b14-131">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="e8b14-132">Дополнительные сведения о профилях устройств Intune, в том числе о создании и настройке параметров, см. в странице [What are Microsoft Intune device profiles?](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="e8b14-132">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e8b14-133">Используйте Microsoft Endpoint Manager, чтобы включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="e8b14-133">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="e8b14-134">Перейдите в центр администрирования диспетчера конечных точек Майкрософт () и [https://endpoint.microsoft.com](https://endpoint.microsoft.com) войдите в систему.</span><span class="sxs-lookup"><span data-stu-id="e8b14-134">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>
2. <span data-ttu-id="e8b14-135">Выберите **антивирус безопасности**  >  **конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-135">Choose **Endpoint security** > **Antivirus**.</span></span>
3. <span data-ttu-id="e8b14-136">Выберите антивирусный профиль.</span><span class="sxs-lookup"><span data-stu-id="e8b14-136">Select an antivirus profile.</span></span> <span data-ttu-id="e8b14-137">(Если у вас еще нет его или вы хотите создать новый профиль, см. параметры ограничения устройств в [Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="e8b14-137">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
4. <span data-ttu-id="e8b14-138">Выбор **свойств**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-138">Select **Properties**.</span></span> <span data-ttu-id="e8b14-139">Затем, рядом с **настройками конфигурации,** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-139">Then, next to **Configuration settings**, choose **Edit**.</span></span>
5. <span data-ttu-id="e8b14-140">**Расширив** защиту облака, а затем в **списке** уровней защиты с доставкой в облаке выберите один из следующих:</span><span class="sxs-lookup"><span data-stu-id="e8b14-140">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
    1. <span data-ttu-id="e8b14-141">**High**: применяет высокий уровень обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e8b14-141">**High**: Applies a strong level of detection.</span></span>
    2. <span data-ttu-id="e8b14-142">**Высокий плюс:** использует **высокий** уровень и применяет дополнительные меры защиты (может повлиять на производительность клиента).</span><span class="sxs-lookup"><span data-stu-id="e8b14-142">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
    3. <span data-ttu-id="e8b14-143">**Нулевая толерантность.** Блокирует все неизвестные исполняемые.</span><span class="sxs-lookup"><span data-stu-id="e8b14-143">**Zero tolerance**: Blocks all unknown executables.</span></span>
6. <span data-ttu-id="e8b14-144">Выберите **Обзор + сохранить,** а **затем** сохранить .</span><span class="sxs-lookup"><span data-stu-id="e8b14-144">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="e8b14-145">Дополнительные сведения о настройке Microsoft Endpoint Configuration Manager см. в дополнительных сведениях о создании и развертывании политик противомалярийных [программ: служба облачной защиты.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)</span><span class="sxs-lookup"><span data-stu-id="e8b14-145">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e8b14-146">Использование групповой политики для включаемой облачной защиты</span><span class="sxs-lookup"><span data-stu-id="e8b14-146">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="e8b14-147">На устройстве управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-147">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="e8b14-148">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера.**</span><span class="sxs-lookup"><span data-stu-id="e8b14-148">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="e8b14-149">Выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="e8b14-149">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="e8b14-150">Расширь дерево до **компонентов Windows и > Microsoft Defender > MAPS**</span><span class="sxs-lookup"><span data-stu-id="e8b14-150">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="e8b14-151">Дважды щелкните **Присоединиться к Microsoft MAPS**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-151">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="e8b14-152">Убедитесь, что параметр включен и задарен **базовым картам или** **расширенным КАРТАм.**</span><span class="sxs-lookup"><span data-stu-id="e8b14-152">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="e8b14-153">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-153">Select **OK**.</span></span>

6. <span data-ttu-id="e8b14-154">Дважды **щелкните Отправить образцы файлов при необходимости дополнительного анализа.**</span><span class="sxs-lookup"><span data-stu-id="e8b14-154">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="e8b14-155">Убедитесь, что для первого параметра установлен параметр **Включен,** а остальные параметры заме-</span><span class="sxs-lookup"><span data-stu-id="e8b14-155">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="e8b14-156">**Отправка безопасных образцов** (1)</span><span class="sxs-lookup"><span data-stu-id="e8b14-156">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="e8b14-157">**Отправка всех образцов** (3)</span><span class="sxs-lookup"><span data-stu-id="e8b14-157">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="e8b14-158">Параметр **Отправка безопасных образцов** (1) означает, что большинство образцов будут отправлены автоматически.</span><span class="sxs-lookup"><span data-stu-id="e8b14-158">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="e8b14-159">Файлы, в которых могут содержаться персональные данные, будут по-прежнему подсказок и требуют дополнительного подтверждения.</span><span class="sxs-lookup"><span data-stu-id="e8b14-159">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

        > [!WARNING]
        > <span data-ttu-id="e8b14-160">Настройка параметра **Always Prompt** (0) снижает состояние защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="e8b14-160">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="e8b14-161">Настройка функции **Никогда** не отправлять (2) означает, что функция [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) Microsoft Defender для конечной точки не будет работать.</span><span class="sxs-lookup"><span data-stu-id="e8b14-161">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="e8b14-162">Нажмите кнопку **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-162">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e8b14-163">Чтобы включить облачную защиту, используйте cmdlets PowerShell</span><span class="sxs-lookup"><span data-stu-id="e8b14-163">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="e8b14-164">Следующие cmdlets могут включить облачную защиту:</span><span class="sxs-lookup"><span data-stu-id="e8b14-164">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="e8b14-165">Дополнительные сведения о том, как использовать PowerShell с антивирусной программой Microsoft Defender, см. в см. в рублях Use [PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="e8b14-165">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="e8b14-166">[Политика CSP - Defender](/windows/client-management/mdm/policy-csp-defender) также имеет больше сведений конкретно о [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="e8b14-166">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="e8b14-167">Вы также можете **установить -SubmitSamplesConsent** `SendSafeSamples` (параметр по умолчанию), `NeverSend` или `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="e8b14-167">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="e8b14-168">Параметр `SendSafeSamples` означает, что большинство образцов будут отправлены автоматически.</span><span class="sxs-lookup"><span data-stu-id="e8b14-168">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="e8b14-169">Файлы, в которых могут содержаться персональные данные, будут по-прежнему подсказок и требуют дополнительного подтверждения.</span><span class="sxs-lookup"><span data-stu-id="e8b14-169">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="e8b14-170">Параметр **-SubmitSamplesConsent** или понизит уровень `NeverSend` защиты `AlwaysPrompt` устройства.</span><span class="sxs-lookup"><span data-stu-id="e8b14-170">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="e8b14-171">Кроме того, настройка этого параметра означает, что функция Block at First Sight Microsoft Defender для конечной точки не `NeverSend` будет работать. [](configure-block-at-first-sight-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e8b14-171">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="e8b14-172">Используйте инструкцию по управлению Windows (WMI), чтобы включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="e8b14-172">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="e8b14-173">Используйте метод [ **Set** класса **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="e8b14-173">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="e8b14-174">Дополнительные сведения о разрешенных параметрах см. в Защитник Windows [API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="e8b14-174">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="e8b14-175">Включив облачную защиту для отдельных клиентов с помощью приложения Windows Security</span><span class="sxs-lookup"><span data-stu-id="e8b14-175">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="e8b14-176">Если для настройки локального параметра переопределения для отчетов о  параметре **групповой** политики Microsoft MAPS задан параметр **Отключен,** параметр облачной защиты в параметрах Windows будет серым и недоступным.</span><span class="sxs-lookup"><span data-stu-id="e8b14-176">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="e8b14-177">Изменения, внесенные с помощью объекта групповой политики, сначала должны быть развернуты в отдельных конечных точках, прежде чем параметр будет обновлен в параметрах Windows.</span><span class="sxs-lookup"><span data-stu-id="e8b14-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="e8b14-178">Откройте приложение Windows Security, выбрав значок щита в панели задач или нажав меню пусков для **Defender.**</span><span class="sxs-lookup"><span data-stu-id="e8b14-178">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="e8b14-179">Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем **метку** параметров защиты & вирусов:</span><span class="sxs-lookup"><span data-stu-id="e8b14-179">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Снимок экрана метки & защиты от угроз в приложении Windows Security](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="e8b14-181">**Подтвердим, что** облачные средства защиты **и** автоматическая отправка образцов переключаются на **On**.</span><span class="sxs-lookup"><span data-stu-id="e8b14-181">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="e8b14-182">Если автоматическая отправка образца настроена с помощью групповой политики, параметр будет серым и недоступным.</span><span class="sxs-lookup"><span data-stu-id="e8b14-182">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="e8b14-183">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e8b14-183">Related articles</span></span>

- [<span data-ttu-id="e8b14-184">Настройка периода ожидания облачного блока</span><span class="sxs-lookup"><span data-stu-id="e8b14-184">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e8b14-185">Настройка блока с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="e8b14-185">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e8b14-186">Используйте cmdlets PowerShell для управления антивирусной программой Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8b14-186">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="e8b14-187">[Помощь в обеспечении безопасности компьютеров Windows с помощью защиты конечных точек для Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span><span class="sxs-lookup"><span data-stu-id="e8b14-187">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="e8b14-188">Cmdlets Defender</span><span class="sxs-lookup"><span data-stu-id="e8b14-188">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="e8b14-189">Использование облачной защиты Microsoft в антивирусе Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e8b14-189">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="e8b14-190">Создание и развертывание политик противомалярийных программ: служба облачной защиты</span><span class="sxs-lookup"><span data-stu-id="e8b14-190">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="e8b14-191">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="e8b14-191">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)