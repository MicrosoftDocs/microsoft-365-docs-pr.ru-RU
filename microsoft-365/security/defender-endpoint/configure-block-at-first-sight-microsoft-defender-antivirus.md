---
title: Включить блок с первого взгляда для обнаружения вредоносных программ в секундах
description: Включив блок с первого взгляда, чтобы обнаружить и заблокировать вредоносные программы в течение нескольких секунд.
keywords: сканирование, BAFS, вредоносные программы, впервые замеченные, на первый взгляд, облако, защитник
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.date: 10/22/2020
ms.technology: mde
ms.openlocfilehash: 837b7899368e69b274323125c97169bbe4f823b7
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51691566"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="e3872-104">Включив блок с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="e3872-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e3872-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e3872-105">**Applies to:**</span></span>

- [<span data-ttu-id="e3872-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e3872-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e3872-107">Блок на первый взгляд предоставляет способ обнаружения и блокировки новых вредоносных программ в течение нескольких секунд.</span><span class="sxs-lookup"><span data-stu-id="e3872-107">Block at first sight provides a way to detect and block new malware within seconds.</span></span> <span data-ttu-id="e3872-108">Эта защита включена по умолчанию при включении определенных обязательных параметров.</span><span class="sxs-lookup"><span data-stu-id="e3872-108">This protection is enabled by default when certain prerequisite settings are enabled.</span></span> <span data-ttu-id="e3872-109">Эти параметры включают облачную защиту, заданный пример времени отправки (например, 50 секунд) и высокий уровень блокировки файлов.</span><span class="sxs-lookup"><span data-stu-id="e3872-109">These settings include cloud-delivered protection, a specified sample submission timeout (such as 50 seconds), and a file-blocking level of high.</span></span> <span data-ttu-id="e3872-110">В большинстве корпоративных организаций эти параметры включены по умолчанию с помощью развертывания антивирусных программ Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e3872-110">In most enterprise organizations, these settings are enabled by default with Microsoft Defender Antivirus deployments.</span></span> 

<span data-ttu-id="e3872-111">Можно [указать, как](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) долго должен быть предотвращен запуск файла, пока облачная служба защиты анализирует файл.</span><span class="sxs-lookup"><span data-stu-id="e3872-111">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="e3872-112">При [блокировке](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) файла можно настроить сообщение, отображаемую на рабочих столах пользователей.</span><span class="sxs-lookup"><span data-stu-id="e3872-112">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="e3872-113">Вы можете изменить имя компании, контактные данные и URL-адрес сообщений.</span><span class="sxs-lookup"><span data-stu-id="e3872-113">You can change the company name, contact information, and message URL.</span></span>

>[!TIP]
><span data-ttu-id="e3872-114">Посетите веб-сайт демонстрации Microsoft Defender для конечной точки [в demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить, что функции работают, и узнайте, как они работают.</span><span class="sxs-lookup"><span data-stu-id="e3872-114">Visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the features are working and see how they work.</span></span>

## <a name="how-it-works"></a><span data-ttu-id="e3872-115">Принципы работы</span><span class="sxs-lookup"><span data-stu-id="e3872-115">How it works</span></span>

<span data-ttu-id="e3872-116">Когда антивирус Microsoft Defender сталкивается с подозрительным, но незащищенным файлом, он запрашивает наш запас облачной защиты.</span><span class="sxs-lookup"><span data-stu-id="e3872-116">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="e3872-117">В облачной папке применяется юристика, машинное обучение и автоматический анализ файла, чтобы определить, являются ли файлы вредоносными или нет угрозой.</span><span class="sxs-lookup"><span data-stu-id="e3872-117">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="e3872-118">Антивирус Microsoft Defender использует несколько технологий обнаружения и предотвращения для обеспечения точной, интеллектуальной и защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="e3872-118">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> <span data-ttu-id="e3872-119">Дополнительные новости см. в этом блоге. Узнайте о передовых технологиях в центре [защиты Microsoft Defender для endpoint следующего поколения.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="e3872-119">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>
<span data-ttu-id="e3872-120">![Список av-двигателей Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)</span><span class="sxs-lookup"><span data-stu-id="e3872-120">![List of Microsoft Defender AV engines](images/microsoft-defender-atp-next-generation-protection-engines.png)</span></span>  

<span data-ttu-id="e3872-121">В Windows 10 версии 1803 или более поздней версии блокировка на первый взгляд может блокировать не переносные исполняемые файлы (такие как JS, VBS или макрос), а также исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="e3872-121">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) as well as executable files.</span></span>

<span data-ttu-id="e3872-122">Блок на первый взгляд использует только архивирование облачной защиты для исполняемых файлов и не переносимых исполняемых файлов, скачанных из Интернета или которые происходят из зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="e3872-122">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="e3872-123">Значение hash файла .exe проверяется с помощью облачной задней части, чтобы определить, является ли файл ранее незащищенным.</span><span class="sxs-lookup"><span data-stu-id="e3872-123">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

<span data-ttu-id="e3872-124">Если в облачной папке не удается определиться, антивирус Microsoft Defender блокирует файл и загружает копию в облако.</span><span class="sxs-lookup"><span data-stu-id="e3872-124">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="e3872-125">Облако выполняет дополнительный анализ для достижения определения, прежде чем оно позволяет файлу запускать или блокирует его во всех будущих встречах, в зависимости от того, определяет ли он файл вредоносным или безопасным.</span><span class="sxs-lookup"><span data-stu-id="e3872-125">The cloud performs additional analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or safe.</span></span>

<span data-ttu-id="e3872-126">Во многих случаях этот процесс позволяет сократить время отклика на новые вредоносные программы с нескольких часов до секунд.</span><span class="sxs-lookup"><span data-stu-id="e3872-126">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="e3872-127">Включив блок с первого взгляда с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="e3872-127">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="e3872-128">Microsoft Intune теперь входит в состав Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="e3872-128">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="e3872-129">В центре администрирования microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) (), перейдите к профилям   >  **конфигурации устройств.**</span><span class="sxs-lookup"><span data-stu-id="e3872-129">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="e3872-130">Выберите или создайте профиль с помощью типа **профилей ограничений** устройства.</span><span class="sxs-lookup"><span data-stu-id="e3872-130">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="e3872-131">В **параметрах Конфигурация** для профиля ограничений устройства установите или подтвердить следующие параметры в **антивирусе Microsoft Defender:**</span><span class="sxs-lookup"><span data-stu-id="e3872-131">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="e3872-132">**Защита от облачной доставки:** включена</span><span class="sxs-lookup"><span data-stu-id="e3872-132">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="e3872-133">**Уровень блокировки файлов:** высокий</span><span class="sxs-lookup"><span data-stu-id="e3872-133">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="e3872-134">**Расширение времени для сканирования файлов облаком:** 50</span><span class="sxs-lookup"><span data-stu-id="e3872-134">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="e3872-135">**Запрос пользователей перед отправкой** примера: Отправка всех данных без запроса</span><span class="sxs-lookup"><span data-stu-id="e3872-135">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Config Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="e3872-137">Сохраните параметры.</span><span class="sxs-lookup"><span data-stu-id="e3872-137">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="e3872-138">Настройка уровня блокировки файлов **до уровня High** применяет высокий уровень обнаружения.</span><span class="sxs-lookup"><span data-stu-id="e3872-138">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="e3872-139">В маловероятном случае, если блокировка файлов вызывает ложное срабатывающее обнаружение законных файлов, можно восстановить [карантинные файлы.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="e3872-139">In the unlikely event that file blocking causes a false positive detection of legitimate files, you can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="e3872-140">Дополнительные сведения о настройке ограничений антивирусных устройств Microsoft Defender в Intune см. в дополнительных сведениях о настройке параметров ограничения устройств [в Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="e3872-140">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="e3872-141">Список ограничений антивирусных устройств Microsoft Defender в Intune см. в списке ограничений устройств для [параметров Windows 10 (и более новых) в Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="e3872-141">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="e3872-142">Включив блок с первого взгляда с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e3872-142">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="e3872-143">Если вы ищете Microsoft Endpoint Configuration Manager, он теперь является частью Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="e3872-143">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="e3872-144">В Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () перейдите к **антивирусу безопасности**  >  **конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="e3872-144">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="e3872-145">Выберите существующую политику или создайте новую политику с помощью типа антивирусного профиля **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="e3872-145">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="e3872-146">Установите или подтвердит следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="e3872-146">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="e3872-147">**Включаем облачную защиту:** Да.</span><span class="sxs-lookup"><span data-stu-id="e3872-147">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="e3872-148">**Уровень защиты с облачной доставкой:** высокий</span><span class="sxs-lookup"><span data-stu-id="e3872-148">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="e3872-149">**Расширенное время растянутой разгона Defender** Cloud в секундах : 50</span><span class="sxs-lookup"><span data-stu-id="e3872-149">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Блокировка параметров с первого взгляда в диспетчере конечных точек":::

4. <span data-ttu-id="e3872-151">Применить антивирусный профиль Microsoft Defender к группе, например всем **пользователям,** всем устройствам или всем пользователям **и устройствам.**</span><span class="sxs-lookup"><span data-stu-id="e3872-151">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="e3872-152">Включив блок с первого взгляда с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="e3872-152">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="e3872-153">Рекомендуется использовать Intune или Microsoft Endpoint Manager для включения блокировки с первого взгляда.</span><span class="sxs-lookup"><span data-stu-id="e3872-153">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="e3872-154">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e3872-154">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="e3872-155">С помощью **редактора управления групповой политикой** перейдите к **шаблонам** администрирования конфигурации  >    >  **компьютеров Windows Components**  >  **Microsoft Defender Antivirus**  >  **MAPS.**</span><span class="sxs-lookup"><span data-stu-id="e3872-155">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="e3872-156">В разделе MAPS дважды щелкните Настройка функции **"Блок** с первого взгляда" и установите ее **включенной,** а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3872-156">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="e3872-157">Параметр Always **prompt (0)** снижает состояние защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="e3872-157">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="e3872-158">Параметр Никогда **не отправлять (2)** означает, что блок с первого взгляда не будет работать.</span><span class="sxs-lookup"><span data-stu-id="e3872-158">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="e3872-159">В разделе MAPS дважды щелкните **Отправить** образцы файлов при необходимости дальнейшего анализа и установите его на **включенную**.</span><span class="sxs-lookup"><span data-stu-id="e3872-159">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="e3872-160">В **статье Отправка образцов файлов при** необходимости дальнейшего анализа выберите **Отправить** все образцы, а затем нажмите **кнопку ОК**.</span><span class="sxs-lookup"><span data-stu-id="e3872-160">Under **Send file samples when further analysis is required**, select **Send all samples**, and then click **OK**.</span></span>

5. <span data-ttu-id="e3872-161">Если вы изменили какие-либо параметры, переназначите объект групповой политики по всей сети, чтобы обеспечить охват всех конечных точек.</span><span class="sxs-lookup"><span data-stu-id="e3872-161">If you changed any settings, redeploy the Group Policy Object across your network to ensure all endpoints are covered.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-clients"></a><span data-ttu-id="e3872-162">Подтверждение того, что блок с первого взгляда включен для отдельных клиентов</span><span class="sxs-lookup"><span data-stu-id="e3872-162">Confirm block at first sight is enabled on individual clients</span></span>

<span data-ttu-id="e3872-163">Вы можете подтвердить, что блокировка с первого взгляда включена для отдельных клиентов с помощью параметров безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="e3872-163">You can confirm that block at first sight is enabled on individual clients using Windows security settings.</span></span>

<span data-ttu-id="e3872-164">Блок с первого взгляда автоматически включен  до тех  пор, пока включена защита от облачной доставки и автоматическая отправка образцов.</span><span class="sxs-lookup"><span data-stu-id="e3872-164">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="e3872-165">Откройте приложение Windows Security.</span><span class="sxs-lookup"><span data-stu-id="e3872-165">Open the Windows Security app.</span></span>

2. <span data-ttu-id="e3872-166">Выберите **защиту &** вирусов, а затем в & параметров защиты от угроз выберите Управление  **настройками.**</span><span class="sxs-lookup"><span data-stu-id="e3872-166">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Снимок экрана метки & защиты от угроз в приложении Windows Security](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="e3872-168">**Подтвердим, что** защита от облачной доставки и **автоматическая отправка** образцов включены.</span><span class="sxs-lookup"><span data-stu-id="e3872-168">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="e3872-169">Если необходимые параметры настроены и развернуты с помощью групповой политики, описанные в этом разделе параметры будут серыми и недоступны для использования в отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="e3872-169">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="e3872-170">Изменения, внесенные с помощью объекта групповой политики, сначала должны быть развернуты в отдельных конечных точках, прежде чем параметр будет обновлен в параметрах Windows.</span><span class="sxs-lookup"><span data-stu-id="e3872-170">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="e3872-171">Проверка блока на первый взгляд работает</span><span class="sxs-lookup"><span data-stu-id="e3872-171">Validate block at first sight is working</span></span>

<span data-ttu-id="e3872-172">Чтобы проверить, работает ли функция, следуйте указаниям в "Проверка подключений между сетью [и облаком".](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="e3872-172">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="e3872-173">Отключите блок с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="e3872-173">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="e3872-174">Отключение блока на первый взгляд снижает состояние защиты устройства и сети.</span><span class="sxs-lookup"><span data-stu-id="e3872-174">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="e3872-175">Вы можете отключить блокировку с первого взгляда, если вы хотите сохранить необходимые параметры без использования блокировки с первого взгляда.</span><span class="sxs-lookup"><span data-stu-id="e3872-175">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="e3872-176">Вы можете временно отключить блокировку с первого взгляда, если возникли проблемы с задержкой или вы хотите проверить влияние функции на сеть.</span><span class="sxs-lookup"><span data-stu-id="e3872-176">You might do temporarily turn block at first sight off if you are experiencing latency issues or you want to test the feature's impact on your network.</span></span> <span data-ttu-id="e3872-177">Однако мы не рекомендуем отключать блок с первого взгляда навсегда.</span><span class="sxs-lookup"><span data-stu-id="e3872-177">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="e3872-178">Отключите блок с первого взгляда с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="e3872-178">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="e3872-179">Перейдите в Центр администрирования конечной точки Microsoft Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="e3872-179">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="e3872-180">Перейдите к **антивирусу безопасности**  >  **Endpoint,** а затем выберите политику антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e3872-180">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="e3872-181">В **статье Управление** выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="e3872-181">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="e3872-182">Рядом с **настройками конфигурации** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e3872-182">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="e3872-183">Измените один или несколько следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="e3872-183">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="e3872-184">Установите **включив облачную защиту,** **чтобы не** настроить или не **настроить.**</span><span class="sxs-lookup"><span data-stu-id="e3872-184">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="e3872-185">Установите **уровень защиты с облачной доставкой,** чтобы не **настраиваться.**</span><span class="sxs-lookup"><span data-stu-id="e3872-185">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="e3872-186">Очистка **расширенного растянутой разгона защитника в поле Seconds.**</span><span class="sxs-lookup"><span data-stu-id="e3872-186">Clear the **Defender Cloud Extended Timeout In Seconds** box.</span></span>

6. <span data-ttu-id="e3872-187">Просмотр и сохранение параметров.</span><span class="sxs-lookup"><span data-stu-id="e3872-187">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="e3872-188">Отключите блок с первого взгляда с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="e3872-188">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="e3872-189">На компьютере управления групповой [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))политикой откройте консоль управления групповой политикой, щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем нажмите **кнопку Изменить**.</span><span class="sxs-lookup"><span data-stu-id="e3872-189">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then click **Edit**.</span></span>

2. <span data-ttu-id="e3872-190">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера** и щелкните **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="e3872-190">Using the **Group Policy Management Editor** go to **Computer configuration** and click **Administrative templates**.</span></span>

3. <span data-ttu-id="e3872-191">Расширение дерева с помощью **компонентов Windows** Microsoft  >  **Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="e3872-191">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="e3872-192">Дважды **щелкните Настройка функции "Блок** с первого взгляда" и установите параметр **Отключен.**</span><span class="sxs-lookup"><span data-stu-id="e3872-192">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="e3872-193">Отключение блока на первый взгляд не отключит и не изменит обязательные групповые политики.</span><span class="sxs-lookup"><span data-stu-id="e3872-193">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="see-also"></a><span data-ttu-id="e3872-194">См. также</span><span class="sxs-lookup"><span data-stu-id="e3872-194">See also</span></span>

- [<span data-ttu-id="e3872-195">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="e3872-195">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)

- [<span data-ttu-id="e3872-196">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="e3872-196">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)