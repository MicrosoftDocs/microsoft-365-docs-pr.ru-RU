---
title: Включите облачную защиту в антивирусная программа в Microsoft Defender
description: Включите облачную защиту, чтобы воспользоваться преимуществами быстрых и продвинутых функций защиты.
keywords: антивирусная программа в Microsoft Defender, антивекав, безопасность, облако, блок с первого взгляда
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/18/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 8c45fb4b60e3c20c2001cc0008ecc8154e854273
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572061"
---
# <a name="turn-on-cloud-delivered-protection"></a><span data-ttu-id="fda75-104">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="fda75-104">Turn on cloud-delivered protection</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="fda75-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="fda75-105">**Applies to:**</span></span>

- [<span data-ttu-id="fda75-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="fda75-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

> [!NOTE]
> <span data-ttu-id="fda75-107">Облачное антивирусная программа в Microsoft Defender является механизмом обеспечения обновленной защиты сети и конечных точек.</span><span class="sxs-lookup"><span data-stu-id="fda75-107">The Microsoft Defender Antivirus cloud service is a mechanism for delivering updated protection to your network and endpoints.</span></span> <span data-ttu-id="fda75-108">Хотя это называется облачным сервисом, это не просто защита файлов, хранящихся в облаке; скорее, он использует распределенные ресурсы и машинное обучение для обеспечения защиты конечных точек со скоростью, которая намного быстрее, чем традиционные обновления разведки безопасности.</span><span class="sxs-lookup"><span data-stu-id="fda75-108">Although it is called a cloud service, it is not simply protection for files stored in the cloud; rather, it uses distributed resources and machine learning to deliver protection to your endpoints at a rate that is far faster than traditional Security intelligence updates.</span></span>

<span data-ttu-id="fda75-109">антивирусная программа в Microsoft Defender использует многочисленные технологии обнаружения и профилактики для обеспечения точной, интеллектуальной защиты в режиме реального времени и интеллектуальной защиты.</span><span class="sxs-lookup"><span data-stu-id="fda75-109">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, real-time, and intelligent protection.</span></span> <span data-ttu-id="fda75-110">[Узнать о передовых технологиях, в основе microsoft Defender для защиты конечного точек следующего поколения.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="fda75-110">[Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

<span data-ttu-id="fda75-111">Вы можете включить антивирусная программа в Microsoft Defender защиту от облачных вычислений или выключить ее несколькими способами:</span><span class="sxs-lookup"><span data-stu-id="fda75-111">You can turn Microsoft Defender Antivirus cloud-delivered protection on or off in several ways:</span></span>

- <span data-ttu-id="fda75-112">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="fda75-112">Microsoft Intune</span></span>
- <span data-ttu-id="fda75-113">Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="fda75-113">Microsoft Endpoint Manager</span></span>
- <span data-ttu-id="fda75-114">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="fda75-114">Group Policy</span></span>
- <span data-ttu-id="fda75-115">PowerShell cmdlets.</span><span class="sxs-lookup"><span data-stu-id="fda75-115">PowerShell cmdlets.</span></span>

 <span data-ttu-id="fda75-116">Вы также можете включить или выключить его в отдельных клиентов с приложением Безопасность Windows приложение.</span><span class="sxs-lookup"><span data-stu-id="fda75-116">You can also turn it on or off in individual clients with the Windows Security app.</span></span>

<span data-ttu-id="fda75-117">[См. Используйте облачную защиту Майкрософт](cloud-protection-microsoft-defender-antivirus.md) для обзора антивирусная программа в Microsoft Defender облачной защиты.</span><span class="sxs-lookup"><span data-stu-id="fda75-117">See [Use Microsoft cloud-delivered protection](cloud-protection-microsoft-defender-antivirus.md) for an overview of Microsoft Defender Antivirus cloud-delivered protection.</span></span>

<span data-ttu-id="fda75-118">Для получения дополнительной информации о конкретных требованиях к сетевому подключению, чтобы обеспечить подключение конечных точек к облачной службе защиты, [см.](configure-network-connections-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="fda75-118">For more information about the specific network-connectivity requirements to ensure your endpoints can connect to the cloud-delivered protection service, see [Configure and validate network connections](configure-network-connections-microsoft-defender-antivirus.md).</span></span>

> [!NOTE]
> <span data-ttu-id="fda75-119">В Windows 10 нет никакой разницы между основными и расширенными **вариантами** **отчетности,** описанными в этой теме.</span><span class="sxs-lookup"><span data-stu-id="fda75-119">In Windows 10, there is no difference between the **Basic** and **Advanced** reporting options described in this topic.</span></span> <span data-ttu-id="fda75-120">Это устаревшее различие, и выбор любой из параметров приведет к одинаковому уровню облачной защиты.</span><span class="sxs-lookup"><span data-stu-id="fda75-120">This is a legacy distinction and choosing either setting will result in the same level of cloud-delivered protection.</span></span> <span data-ttu-id="fda75-121">Нет никакой разницы в типе или объеме общей информации.</span><span class="sxs-lookup"><span data-stu-id="fda75-121">There is no difference in the type or amount of information that is shared.</span></span> <span data-ttu-id="fda75-122">Для получения дополнительной информации о том, что мы собираем, смотрите заявление [о конфиденциальности Майкрософт.](https://go.microsoft.com/fwlink/?linkid=521839)</span><span class="sxs-lookup"><span data-stu-id="fda75-122">For more information on what we collect, see the [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=521839).</span></span>

## <a name="use-intune-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="fda75-123">Используйте Intune для включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="fda75-123">Use Intune to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="fda75-124">Перейти к Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войти в систему.</span><span class="sxs-lookup"><span data-stu-id="fda75-124">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="fda75-125">На **панели Homee** выберите **конфигурацию устройства > профилей.**</span><span class="sxs-lookup"><span data-stu-id="fda75-125">On the **Home** pane, select **Device configuration > Profiles**.</span></span>

3. <span data-ttu-id="fda75-126">Выберите **тип профиля ограничений** устройства, который вы хотите настроить.</span><span class="sxs-lookup"><span data-stu-id="fda75-126">Select the **Device restrictions** profile type you want to configure.</span></span> <span data-ttu-id="fda75-127">Если вам нужно создать новый **тип профиля ограничений** устройства, [см. Настройки параметров ограничения устройства в Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="fda75-127">If you need to create a new **Device restrictions** profile type, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="fda75-128">Параметры **конфигурации**  >  **свойств: Редактировать**  >  **антивирусная программа в Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="fda75-128">Select **Properties** > **Configuration settings: Edit** > **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="fda75-129">В **коммутаторе защиты, поставляемом с** облачным доступом, **выберите Enable**.</span><span class="sxs-lookup"><span data-stu-id="fda75-129">On the **Cloud-delivered protection** switch, select **Enable**.</span></span>

6. <span data-ttu-id="fda75-130">В быстрых **пользователей перед примером представления** падения, выберите **Отправить все данные автоматически**.</span><span class="sxs-lookup"><span data-stu-id="fda75-130">In the **Prompt users before sample submission** dropdown, select **Send all data automatically**.</span></span>

<span data-ttu-id="fda75-131">Для получения дополнительной информации о профилях устройств Intune, включая способы создания и настройки их настроек, [см Microsoft Intune.](/intune/device-profiles)</span><span class="sxs-lookup"><span data-stu-id="fda75-131">For more information about Intune device profiles, including how to create and configure their settings, see [What are Microsoft Intune device profiles?](/intune/device-profiles)</span></span>

## <a name="use-microsoft-endpoint-manager-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="fda75-132">Используйте Microsoft Endpoint Manager для включаемой облачной защиты</span><span class="sxs-lookup"><span data-stu-id="fda75-132">Use Microsoft Endpoint Manager to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="fda75-133">Перейти к Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войти в систему.</span><span class="sxs-lookup"><span data-stu-id="fda75-133">Go to the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and log in.</span></span>

2. <span data-ttu-id="fda75-134">Выберите **Антивирус безопасности**  >  **Конечной точки**.</span><span class="sxs-lookup"><span data-stu-id="fda75-134">Choose **Endpoint security** > **Antivirus**.</span></span>

3. <span data-ttu-id="fda75-135">Выберите антивирусный профиль.</span><span class="sxs-lookup"><span data-stu-id="fda75-135">Select an antivirus profile.</span></span> <span data-ttu-id="fda75-136">(Если у вас его еще нет, или если вы хотите создать новый профиль, [см. Настройку настроек ограничения устройства в Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="fda75-136">(If you don't have one yet, or if you want to create a new profile, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>

4. <span data-ttu-id="fda75-137">Выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="fda75-137">Select **Properties**.</span></span> <span data-ttu-id="fda75-138">Затем, рядом с **настройками конфигурации,** **выберите Редактировать**.</span><span class="sxs-lookup"><span data-stu-id="fda75-138">Then, next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="fda75-139">Расширьте **защиту** облаков, а затем **в списке уровней защиты,** поставляемых в облако, выберите один из следующих:</span><span class="sxs-lookup"><span data-stu-id="fda75-139">Expand **Cloud protection**, and then in the **Cloud-delivered protection level** list, select one of the following:</span></span>
   - <span data-ttu-id="fda75-140">**Высокий**: Применяется высокий уровень обнаружения.</span><span class="sxs-lookup"><span data-stu-id="fda75-140">**High**: Applies a strong level of detection.</span></span>
   - <span data-ttu-id="fda75-141">**Высокий плюс**: Использует **высокий уровень** и применяет дополнительные меры защиты (может повлиять на производительность клиента).</span><span class="sxs-lookup"><span data-stu-id="fda75-141">**High plus**: Uses the **High** level and applies additional protection measures (may impact client performance).</span></span>
   - <span data-ttu-id="fda75-142">**Нулевая толерантность**: Блокирует все неизвестные выполненные.</span><span class="sxs-lookup"><span data-stu-id="fda75-142">**Zero tolerance**: Blocks all unknown executables.</span></span>

6. <span data-ttu-id="fda75-143">Выберите **Обзор и сохранить,** а затем выбрать **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="fda75-143">Select **Review + save**, then choose **Save**.</span></span>

<span data-ttu-id="fda75-144">Для получения дополнительной информации о Microsoft Endpoint Configuration Manager, узнайте, [как создавать и развертывать антивирусные политики: Служба облачной защиты.](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)</span><span class="sxs-lookup"><span data-stu-id="fda75-144">For more information about configuring Microsoft Endpoint Configuration Manager, see [How to create and deploy antimalware policies: Cloud-protection service](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service).</span></span>

## <a name="use-group-policy-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="fda75-145">Использование групповой политики для включив облачную защиту</span><span class="sxs-lookup"><span data-stu-id="fda75-145">Use Group Policy to turn on cloud-delivered protection</span></span>

1. <span data-ttu-id="fda75-146">На устройстве управления групповой политикой откройте консоль [управления групповой политикой, нажмите](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))правой кнопкой мыши на объект групповой политики, который вы хотите настроить и выбрать **Edit.**</span><span class="sxs-lookup"><span data-stu-id="fda75-146">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="fda75-147">В редакторе **управления групповой политикой перейдите** на **компьютерную конфигурацию.**</span><span class="sxs-lookup"><span data-stu-id="fda75-147">In the **Group Policy Management Editor**, go to **Computer configuration**.</span></span>

3. <span data-ttu-id="fda75-148">Выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="fda75-148">Select **Administrative templates**.</span></span>

4. <span data-ttu-id="fda75-149">Расширьте дерево до **Windows компонентов > антивирусная программа в Microsoft Defender > MAPS**</span><span class="sxs-lookup"><span data-stu-id="fda75-149">Expand the tree to **Windows components > Microsoft Defender Antivirus > MAPS**</span></span>

5. <span data-ttu-id="fda75-150">Дважды нажмите **Присоединяйтесь к Microsoft MAPS**.</span><span class="sxs-lookup"><span data-stu-id="fda75-150">Double-click **Join Microsoft MAPS**.</span></span> <span data-ttu-id="fda75-151">Убедитесь, что опция включена и установлена **на Basic MAPS** или Advanced **MAPS.**</span><span class="sxs-lookup"><span data-stu-id="fda75-151">Ensure the option is turned on and set to **Basic MAPS** or **Advanced MAPS**.</span></span> <span data-ttu-id="fda75-152">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fda75-152">Select **OK**.</span></span>

6. <span data-ttu-id="fda75-153">При необходимости **дополнительного анализа отправьте образцы файлов с двойным нажатием кнопки.**</span><span class="sxs-lookup"><span data-stu-id="fda75-153">Double-click **Send file samples when further analysis is required**.</span></span> <span data-ttu-id="fda75-154">Убедитесь, что первый вариант установлен на **Enabled** и что другие параметры настроены либо:</span><span class="sxs-lookup"><span data-stu-id="fda75-154">Ensure that the first option is set to **Enabled** and that the other options are set to either:</span></span>

    1. <span data-ttu-id="fda75-155">**Отправка безопасных образцов** (1)</span><span class="sxs-lookup"><span data-stu-id="fda75-155">**Send safe samples** (1)</span></span>
    2. <span data-ttu-id="fda75-156">**Отправить все образцы** (3)</span><span class="sxs-lookup"><span data-stu-id="fda75-156">**Send all samples** (3)</span></span>

        >[!NOTE]
        > <span data-ttu-id="fda75-157">Опция **Send safe samples** (1) означает, что большинство образцов будут отправлены автоматически.</span><span class="sxs-lookup"><span data-stu-id="fda75-157">The **Send safe samples** (1) option means that most samples will be sent automatically.</span></span> <span data-ttu-id="fda75-158">Файлы, которые могут содержать личную информацию, по-прежнему будут оперативно и требуют дополнительного подтверждения.</span><span class="sxs-lookup"><span data-stu-id="fda75-158">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>
        > <span data-ttu-id="fda75-159">Установка опции **Always Prompt** (0) снизит состояние защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="fda75-159">Setting the option to **Always Prompt** (0) will lower the protection state of the device.</span></span> <span data-ttu-id="fda75-160">Установка его на **Never send** (2) означает, что функция Block at [First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) microsoft Defender for Endpoint не будет работать.</span><span class="sxs-lookup"><span data-stu-id="fda75-160">Setting it to **Never send** (2) means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

7. <span data-ttu-id="fda75-161">Нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="fda75-161">Select **OK**.</span></span>

## <a name="use-powershell-cmdlets-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="fda75-162">Используйте смердлеты PowerShell для включив облачную защиту</span><span class="sxs-lookup"><span data-stu-id="fda75-162">Use PowerShell cmdlets to turn on cloud-delivered protection</span></span>

<span data-ttu-id="fda75-163">Следующие cmdlets могут включить облачную защиту:</span><span class="sxs-lookup"><span data-stu-id="fda75-163">The following cmdlets can turn on cloud-delivered protection:</span></span>

```PowerShell
Set-MpPreference -MAPSReporting Advanced
Set-MpPreference -SubmitSamplesConsent SendAllSamples
```

<span data-ttu-id="fda75-164">Для получения дополнительной информации о том, как использовать PowerShell с антивирусная программа в Microsoft Defender, [смесями Используйте PowerShell](use-powershell-cmdlets-microsoft-defender-antivirus.md) для настройки и антивирусная программа в Microsoft Defender [и Defender cmdlets.](/powershell/module/defender/)</span><span class="sxs-lookup"><span data-stu-id="fda75-164">For more information on how to use PowerShell with Microsoft Defender Antivirus, see [Use PowerShell cmdlets to configure and run Microsoft Defender Antivirus](use-powershell-cmdlets-microsoft-defender-antivirus.md) and [Defender cmdlets](/powershell/module/defender/).</span></span> <span data-ttu-id="fda75-165">[Политика CSP - Защитник](/windows/client-management/mdm/policy-csp-defender) также имеет более подробную информацию конкретно [о -SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span><span class="sxs-lookup"><span data-stu-id="fda75-165">[Policy CSP - Defender](/windows/client-management/mdm/policy-csp-defender) also has more information specifically on [-SubmitSamplesConsent](/windows/client-management/mdm/policy-csp-defender#defender-submitsamplesconsent).</span></span>

>[!NOTE]
> <span data-ttu-id="fda75-166">Вы также можете установить **-SubmitSamplesConsent** `SendSafeSamples` (параметр по умолчанию), `NeverSend` или `AlwaysPrompt` .</span><span class="sxs-lookup"><span data-stu-id="fda75-166">You can also set **-SubmitSamplesConsent** to `SendSafeSamples` (the default setting), `NeverSend`, or `AlwaysPrompt`.</span></span> <span data-ttu-id="fda75-167">Параметр `SendSafeSamples` означает, что большинство образцов будут отправлены автоматически.</span><span class="sxs-lookup"><span data-stu-id="fda75-167">The `SendSafeSamples` setting means that most samples will be sent automatically.</span></span> <span data-ttu-id="fda75-168">Файлы, которые могут содержать личную информацию, по-прежнему будут оперативно и требуют дополнительного подтверждения.</span><span class="sxs-lookup"><span data-stu-id="fda75-168">Files that are likely to contain personal information will still prompt and require additional confirmation.</span></span>

>[!WARNING]
> <span data-ttu-id="fda75-169">Настройка **-SubmitSamplesConsent** `NeverSend` или снизит `AlwaysPrompt` уровень защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="fda75-169">Setting **-SubmitSamplesConsent** to `NeverSend` or `AlwaysPrompt` will lower the protection level of the device.</span></span> <span data-ttu-id="fda75-170">Кроме того, установка `NeverSend` означает, что функция Block at First [Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) Microsoft Defender for Endpoint не будет работать.</span><span class="sxs-lookup"><span data-stu-id="fda75-170">In addition, setting it to `NeverSend` means that the [Block at First Sight](configure-block-at-first-sight-microsoft-defender-antivirus.md) feature of Microsoft Defender for Endpoint won't work.</span></span>

## <a name="use-windows-management-instruction-wmi-to-turn-on-cloud-delivered-protection"></a><span data-ttu-id="fda75-171">Используйте Windows управлению системой (WMI), чтобы включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="fda75-171">Use Windows Management Instruction (WMI) to turn on cloud-delivered protection</span></span>

<span data-ttu-id="fda75-172">Используйте [ **метод** набора **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) класса для следующих свойств:</span><span class="sxs-lookup"><span data-stu-id="fda75-172">Use the [**Set** method of the **MSFT_MpPreference**](/previous-versions/windows/desktop/defender/set-msft-mppreference) class for the following properties:</span></span>

```WMI
MAPSReporting
SubmitSamplesConsent
```

<span data-ttu-id="fda75-173">Более подробную информацию о разрешенных параметрах [можно получить Защитник Windows API WMIv2](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span><span class="sxs-lookup"><span data-stu-id="fda75-173">For more information about allowed parameters, see [Windows Defender WMIv2 APIs](/previous-versions/windows/desktop/defender/windows-defender-wmiv2-apis-portal)</span></span>

## <a name="turn-on-cloud-delivered-protection-on-individual-clients-with-the-windows-security-app"></a><span data-ttu-id="fda75-174">Включите облачную защиту отдельных клиентов с помощью приложения Безопасность Windows</span><span class="sxs-lookup"><span data-stu-id="fda75-174">Turn on cloud-delivered protection on individual clients with the Windows Security app</span></span>

> [!NOTE]
> <span data-ttu-id="fda75-175">Если **настройка локальных параметров для представления отчетов по группе Майкрософт MAPS** установлена для **отключений,** то настройка защиты на основе облака в Windows Параметры году будет высеяна и недоступна. </span><span class="sxs-lookup"><span data-stu-id="fda75-175">If the **Configure local setting override for reporting Microsoft MAPS** Group Policy setting is set to **Disabled**, then the **Cloud-based protection** setting in Windows Settings will be greyed-out and unavailable.</span></span> <span data-ttu-id="fda75-176">Изменения, внесенные с помощью объекта групповой политики, необходимо сначала развернуть на отдельных конечных точках, прежде чем параметр будет обновлен в настройках Windows.</span><span class="sxs-lookup"><span data-stu-id="fda75-176">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

1. <span data-ttu-id="fda75-177">Откройте приложение Безопасность Windows, выбрав значок щита в баре задач или найме меню «Старт» для **Defender.**</span><span class="sxs-lookup"><span data-stu-id="fda75-177">Open the Windows Security app by selecting the shield icon in the task bar, or by searching the start menu for **Defender**.</span></span>

2. <span data-ttu-id="fda75-178">Выберите **плитку & защиты** от угроз (или значок щита на левой планке меню), а **затем метку & virus для защиты** от угроз:</span><span class="sxs-lookup"><span data-stu-id="fda75-178">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then the **Virus & threat protection settings** label:</span></span>

    ![Снимок экрана: метка параметров защиты от вирусов и угроз в приложении "Безопасность Windows"](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="fda75-180">Подтвердите, **что облачная защита** и **автоматическое представление образцов** переключаются на **On**.</span><span class="sxs-lookup"><span data-stu-id="fda75-180">Confirm that **Cloud-based Protection** and **Automatic sample submission** are switched to **On**.</span></span>

> [!NOTE]
> <span data-ttu-id="fda75-181">Если автоматическое представление образца было настроено с групповой политикой, то настройка будет серова и недоступна.</span><span class="sxs-lookup"><span data-stu-id="fda75-181">If automatic sample submission has been configured with Group Policy then the setting will be greyed-out and unavailable.</span></span>

## <a name="related-articles"></a><span data-ttu-id="fda75-182">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="fda75-182">Related articles</span></span>

- [<span data-ttu-id="fda75-183">Настройка времени ожидания блокировки облака</span><span class="sxs-lookup"><span data-stu-id="fda75-183">Configure the cloud block timeout period</span></span>](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fda75-184">Настройка блока с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="fda75-184">Configure block at first sight</span></span>](configure-block-at-first-sight-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fda75-185">Использование командлетов PowerShell для управления антивирусной программой в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fda75-185">Use PowerShell cmdlets to manage Microsoft Defender Antivirus</span></span>](use-powershell-cmdlets-microsoft-defender-antivirus.md)
- <span data-ttu-id="fda75-186">[Помогите обезопасить Windows ПК с Endpoint Protection для Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)</span><span class="sxs-lookup"><span data-stu-id="fda75-186">[Help secure Windows PCs with Endpoint Protection for Microsoft Intune](/intune/deploy-use/help-secure-windows-pcs-with-endpoint-protection-for-microsoft-intune)]</span></span>
- [<span data-ttu-id="fda75-187">Защитник cmdlets</span><span class="sxs-lookup"><span data-stu-id="fda75-187">Defender cmdlets</span></span>](/powershell/module/defender/)
- [<span data-ttu-id="fda75-188">Используйте облачную защиту Майкрософт в антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="fda75-188">Use Microsoft cloud-delivered protection in Microsoft Defender Antivirus</span></span>](cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="fda75-189">Как создавать и развертывать антивирусные политики: Служба облачной защиты</span><span class="sxs-lookup"><span data-stu-id="fda75-189">How to create and deploy antimalware policies: Cloud-protection service</span></span>](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
- [<span data-ttu-id="fda75-190">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="fda75-190">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
