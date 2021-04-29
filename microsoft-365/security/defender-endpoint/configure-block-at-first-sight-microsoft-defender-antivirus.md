---
title: Включить блок с первого взгляда для обнаружения вредоносных программ в секундах
description: Включив блок с первого взгляда, чтобы обнаружить и заблокировать вредоносные программы в течение нескольких секунд.
keywords: сканирование, блокировка с первого взгляда, вредоносные программы, с первого взгляда, облако, защитник, антивирус
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 04/28/2021
ms.technology: mde
ms.openlocfilehash: d4db3549d04e5883f02ba263c06371371d385022
ms.sourcegitcommit: 8c89bc1d106b4716b07a1977d57e4d9ef98aecb3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/29/2021
ms.locfileid: "52079207"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="d2209-104">Включить блокировку при первом появлении</span><span class="sxs-lookup"><span data-stu-id="d2209-104">Turn on block at first sight</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="d2209-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d2209-105">**Applies to:**</span></span>

- [<span data-ttu-id="d2209-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d2209-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d2209-107">В этой статье описывается функция антивирусного и антивирусного обеспечения, известная как "блок с первого взгляда", и описывается, как включить блокировку с первого взгляда для организации.</span><span class="sxs-lookup"><span data-stu-id="d2209-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="d2209-108">Эта статья предназначена для корпоративных администраторов и ИТ-специалистов, которые управляют настройками безопасности для организаций.</span><span class="sxs-lookup"><span data-stu-id="d2209-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="d2209-109">Если вы не администратор enteprise или ИТ-профессионал, но у вас есть вопросы о блоке на первый взгляд, см. не администратор предприятия [или ИТ-профессионал?](#not-an-enterprise-admin-or-it-pro).</span><span class="sxs-lookup"><span data-stu-id="d2209-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro).</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="d2209-110">Что такое "блок с первого взгляда"?</span><span class="sxs-lookup"><span data-stu-id="d2209-110">What is "block at first sight"?</span></span>

<span data-ttu-id="d2209-111">Блок на первый взгляд — это функция защиты от угроз следующего поколения, которая обнаруживает новые вредоносные программы и блокирует их в течение нескольких секунд.</span><span class="sxs-lookup"><span data-stu-id="d2209-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="d2209-112">Блок с первого взгляда включен при включении определенных параметров безопасности.</span><span class="sxs-lookup"><span data-stu-id="d2209-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="d2209-113">В эти параметры входят:</span><span class="sxs-lookup"><span data-stu-id="d2209-113">These settings include:</span></span>

- <span data-ttu-id="d2209-114">Защита с облачным доставкой;</span><span class="sxs-lookup"><span data-stu-id="d2209-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="d2209-115">Указанный пример времени отправки (например, 50 секунд); и</span><span class="sxs-lookup"><span data-stu-id="d2209-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="d2209-116">Высокий уровень блокировки файлов.</span><span class="sxs-lookup"><span data-stu-id="d2209-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="d2209-117">В большинстве корпоративных организаций параметры, необходимые для обеспечения блокировки на первый взгляд, настраиваются с помощью развертывания антивирусных программ Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d2209-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="d2209-118">Как это работает</span><span class="sxs-lookup"><span data-stu-id="d2209-118">How it works</span></span>

<span data-ttu-id="d2209-119">Когда антивирус Microsoft Defender сталкивается с подозрительным, но незащищенным файлом, он запрашивает наш запас облачной защиты.</span><span class="sxs-lookup"><span data-stu-id="d2209-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="d2209-120">В облачной папке применяется юристика, машинное обучение и автоматический анализ файла, чтобы определить, являются ли файлы вредоносными или нет угрозой.</span><span class="sxs-lookup"><span data-stu-id="d2209-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="d2209-121">Антивирус Microsoft Defender использует несколько технологий обнаружения и предотвращения для обеспечения точной, интеллектуальной и защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="d2209-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Список av-двигателей Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="d2209-123">Дополнительные новости см. в этом блоге. Узнайте о передовых технологиях в центре [защиты Microsoft Defender для endpoint следующего поколения.](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/)</span><span class="sxs-lookup"><span data-stu-id="d2209-123">To learn more, see this blog: [Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="d2209-124">Несколько вещей, которые нужно знать о блоке с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="d2209-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="d2209-125">В Windows 10 версии 1803 или более поздней версии блокировка на первый взгляд может блокировать не переносимые исполняемые файлы (такие как JS, VBS или макрос) и исполняемые файлы.</span><span class="sxs-lookup"><span data-stu-id="d2209-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="d2209-126">Блок на первый взгляд использует только архивирование облачной защиты для исполняемых файлов и не переносимых исполняемых файлов, скачанных из Интернета или которые происходят из зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="d2209-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="d2209-127">Значение hash файла .exe проверяется с помощью облачной задней части, чтобы определить, является ли файл ранее незащищенным.</span><span class="sxs-lookup"><span data-stu-id="d2209-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="d2209-128">Если в облачной папке не удается определиться, антивирус Microsoft Defender блокирует файл и загружает копию в облако.</span><span class="sxs-lookup"><span data-stu-id="d2209-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="d2209-129">Облако выполняет дополнительный анализ для достижения определения, прежде чем оно либо позволяет файлу запускать, либо блокирует его во всех будущих встречах, в зависимости от того, определяет ли он файл как вредоносный или не представляет угрозы.</span><span class="sxs-lookup"><span data-stu-id="d2209-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="d2209-130">Во многих случаях этот процесс позволяет сократить время отклика на новые вредоносные программы с нескольких часов до секунд.</span><span class="sxs-lookup"><span data-stu-id="d2209-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="d2209-131">Можно [указать, как](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) долго должен быть предотвращен запуск файла, пока облачная служба защиты анализирует файл.</span><span class="sxs-lookup"><span data-stu-id="d2209-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="d2209-132">При [блокировке](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) файла можно настроить сообщение, отображаемую на рабочих столах пользователей.</span><span class="sxs-lookup"><span data-stu-id="d2209-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="d2209-133">Вы можете изменить имя компании, контактные данные и URL-адрес сообщений.</span><span class="sxs-lookup"><span data-stu-id="d2209-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="d2209-134">Включив блок с первого взгляда с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d2209-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="d2209-135">Microsoft Intune теперь входит в состав Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="d2209-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="d2209-136">В центре администрирования microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) (), перейдите к профилям   >  **конфигурации устройств.**</span><span class="sxs-lookup"><span data-stu-id="d2209-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="d2209-137">Выберите или создайте профиль с помощью типа **профилей ограничений** устройства.</span><span class="sxs-lookup"><span data-stu-id="d2209-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="d2209-138">В **параметрах Конфигурация** для профиля ограничений устройства установите или подтвердить следующие параметры в **антивирусе Microsoft Defender:**</span><span class="sxs-lookup"><span data-stu-id="d2209-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="d2209-139">**Защита от облачной доставки:** включена</span><span class="sxs-lookup"><span data-stu-id="d2209-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="d2209-140">**Уровень блокировки файлов:** высокий</span><span class="sxs-lookup"><span data-stu-id="d2209-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="d2209-141">**Расширение времени для сканирования файлов облаком:** 50</span><span class="sxs-lookup"><span data-stu-id="d2209-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="d2209-142">**Запрос пользователей перед отправкой** примера: Отправка всех данных без запроса</span><span class="sxs-lookup"><span data-stu-id="d2209-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   ![Config Intune](images/defender/intune-block-at-first-sight.png)

4. <span data-ttu-id="d2209-144">Сохраните параметры.</span><span class="sxs-lookup"><span data-stu-id="d2209-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="d2209-145">Настройка уровня блокировки файлов **до уровня High** применяет высокий уровень обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d2209-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="d2209-146">В маловероятном случае, если блокировка файлов вызывает ложное срабатывающее обнаружение законных файлов, группа операций безопасности может восстановить [карантинные файлы.](./restore-quarantined-files-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="d2209-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="d2209-147">Дополнительные сведения о настройке ограничений антивирусных устройств Microsoft Defender в Intune см. в дополнительных сведениях о настройке параметров ограничения устройств [в Microsoft Intune.](/intune/device-restrictions-configure)</span><span class="sxs-lookup"><span data-stu-id="d2209-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="d2209-148">Список ограничений антивирусных устройств Microsoft Defender в Intune см. в списке ограничений устройств для [параметров Windows 10 (и более новых) в Intune.](/intune/device-restrictions-windows-10#microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="d2209-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="d2209-149">Включив блок с первого взгляда с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2209-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="d2209-150">Если вы ищете Microsoft Endpoint Configuration Manager, он теперь является частью Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="d2209-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="d2209-151">В Microsoft Endpoint Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () перейдите к **антивирусу безопасности**  >  **конечных точек**.</span><span class="sxs-lookup"><span data-stu-id="d2209-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="d2209-152">Выберите существующую политику или создайте новую политику с помощью типа антивирусного профиля **Microsoft Defender.**</span><span class="sxs-lookup"><span data-stu-id="d2209-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="d2209-153">Установите или подтвердит следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="d2209-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="d2209-154">**Включаем облачную защиту:** Да.</span><span class="sxs-lookup"><span data-stu-id="d2209-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="d2209-155">**Уровень защиты с облачной доставкой:** высокий</span><span class="sxs-lookup"><span data-stu-id="d2209-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="d2209-156">**Расширенное время растянутой разгона Defender** Cloud в секундах : 50</span><span class="sxs-lookup"><span data-stu-id="d2209-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Блокировка параметров с первого взгляда в диспетчере конечных точек":::

4. <span data-ttu-id="d2209-158">Применить антивирусный профиль Microsoft Defender к группе, например всем **пользователям,** всем устройствам или всем пользователям **и устройствам.**</span><span class="sxs-lookup"><span data-stu-id="d2209-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="d2209-159">Включив блок с первого взгляда с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="d2209-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="d2209-160">Рекомендуется использовать Intune или Microsoft Endpoint Manager для включения блокировки с первого взгляда.</span><span class="sxs-lookup"><span data-stu-id="d2209-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="d2209-161">На компьютере управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d2209-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="d2209-162">С помощью **редактора управления групповой политикой** перейдите к **шаблонам** администрирования конфигурации  >    >  **компьютеров Windows Components**  >  **Microsoft Defender Antivirus**  >  **MAPS.**</span><span class="sxs-lookup"><span data-stu-id="d2209-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="d2209-163">В разделе MAPS дважды щелкните Настройка функции **"Блок** с первого взгляда" и установите ее **включенной,** а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d2209-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d2209-164">Параметр Always **prompt (0)** снижает состояние защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="d2209-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="d2209-165">Параметр Никогда **не отправлять (2)** означает, что блок с первого взгляда не будет работать.</span><span class="sxs-lookup"><span data-stu-id="d2209-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="d2209-166">В разделе MAPS дважды щелкните **Отправить** образцы файлов при необходимости дальнейшего анализа и установите его на **включенную**.</span><span class="sxs-lookup"><span data-stu-id="d2209-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="d2209-167">В **статье Отправка образцов файлов при** необходимости дополнительного анализа выберите **Отправить** все образцы, а затем выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="d2209-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="d2209-168">Передиплойте объект групповой политики в сети, как обычно.</span><span class="sxs-lookup"><span data-stu-id="d2209-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="d2209-169">Подтверждение включения блока с первого взгляда на отдельных клиентских устройствах</span><span class="sxs-lookup"><span data-stu-id="d2209-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="d2209-170">Вы можете подтвердить, что блокировка с первого взгляда включена на отдельных клиентских устройствах с помощью приложения Windows Security.</span><span class="sxs-lookup"><span data-stu-id="d2209-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="d2209-171">Блок с первого взгляда автоматически включен  до тех  пор, пока включена защита от облачной доставки и автоматическая отправка образцов.</span><span class="sxs-lookup"><span data-stu-id="d2209-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="d2209-172">Откройте приложение Windows Security.</span><span class="sxs-lookup"><span data-stu-id="d2209-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="d2209-173">Выберите **защиту &** вирусов, а затем в & параметров защиты от угроз выберите Управление  **настройками.**</span><span class="sxs-lookup"><span data-stu-id="d2209-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   ![Снимок экрана метки & защиты от угроз в приложении Windows Security](images/defender/wdav-protection-settings-wdsc.png)

3. <span data-ttu-id="d2209-175">**Подтвердим, что** защита от облачной доставки и **автоматическая отправка** образцов включены.</span><span class="sxs-lookup"><span data-stu-id="d2209-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="d2209-176">Если необходимые параметры настроены и развернуты с помощью групповой политики, описанные в этом разделе параметры будут серыми и недоступны для использования в отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="d2209-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="d2209-177">Изменения, внесенные с помощью объекта групповой политики, сначала должны быть развернуты в отдельных конечных точках, прежде чем параметр будет обновлен в параметрах Windows.</span><span class="sxs-lookup"><span data-stu-id="d2209-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="d2209-178">Проверка блока на первый взгляд работает</span><span class="sxs-lookup"><span data-stu-id="d2209-178">Validate block at first sight is working</span></span>

<span data-ttu-id="d2209-179">Чтобы проверить, работает ли функция, следуйте указаниям в "Проверка подключений между сетью [и облаком".](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)</span><span class="sxs-lookup"><span data-stu-id="d2209-179">To validate that the feature is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span>

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="d2209-180">Отключите блок с первого взгляда</span><span class="sxs-lookup"><span data-stu-id="d2209-180">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="d2209-181">Отключение блока на первый взгляд снижает состояние защиты устройства и сети.</span><span class="sxs-lookup"><span data-stu-id="d2209-181">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="d2209-182">Вы можете отключить блокировку с первого взгляда, если вы хотите сохранить необходимые параметры без использования блокировки с первого взгляда.</span><span class="sxs-lookup"><span data-stu-id="d2209-182">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="d2209-183">Вы можете временно отключить блокировку с первого взгляда, чтобы узнать, как эта функция влияет на сеть.</span><span class="sxs-lookup"><span data-stu-id="d2209-183">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="d2209-184">Однако мы не рекомендуем отключать блок с первого взгляда навсегда.</span><span class="sxs-lookup"><span data-stu-id="d2209-184">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="d2209-185">Отключите блок с первого взгляда с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2209-185">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="d2209-186">Перейдите в Центр администрирования конечной точки Microsoft Manager [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () и войдите.</span><span class="sxs-lookup"><span data-stu-id="d2209-186">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="d2209-187">Перейдите к **антивирусу безопасности**  >  **Endpoint,** а затем выберите политику антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d2209-187">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="d2209-188">В **статье Управление** выберите **свойства**.</span><span class="sxs-lookup"><span data-stu-id="d2209-188">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="d2209-189">Рядом с **настройками конфигурации** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d2209-189">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="d2209-190">Измените один или несколько следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d2209-190">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="d2209-191">Установите **включив облачную защиту,** **чтобы не** настроить или не **настроить.**</span><span class="sxs-lookup"><span data-stu-id="d2209-191">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="d2209-192">Установите **уровень защиты с облачной доставкой,** чтобы не **настраиваться.**</span><span class="sxs-lookup"><span data-stu-id="d2209-192">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="d2209-193">Очистка контрольного окна для расширенного растянутой растянутой минуты Defender **Cloud в секундах.**</span><span class="sxs-lookup"><span data-stu-id="d2209-193">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="d2209-194">Просмотр и сохранение параметров.</span><span class="sxs-lookup"><span data-stu-id="d2209-194">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="d2209-195">Отключите блок с первого взгляда с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="d2209-195">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="d2209-196">На компьютере управления групповой [](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))политикой откройте консоль управления групповой политикой, щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d2209-196">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="d2209-197">С помощью **редактора управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="d2209-197">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="d2209-198">Расширение дерева с помощью **компонентов Windows** Microsoft  >  **Defender Antivirus**  >  **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="d2209-198">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="d2209-199">Дважды **щелкните Настройка функции "Блок** с первого взгляда" и установите параметр **Отключен.**</span><span class="sxs-lookup"><span data-stu-id="d2209-199">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2209-200">Отключение блока на первый взгляд не отключит и не изменит обязательные групповые политики.</span><span class="sxs-lookup"><span data-stu-id="d2209-200">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="d2209-201">Не администратор предприятия или ИТ-профессионал?</span><span class="sxs-lookup"><span data-stu-id="d2209-201">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="d2209-202">Если вы не администратор предприятия или ИТ-профессионал, но у вас есть вопросы о блокировке на первый взгляд, этот раздел для вас.</span><span class="sxs-lookup"><span data-stu-id="d2209-202">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="d2209-203">Блок на первый взгляд — это функция защиты от угроз, которая обнаруживает и блокирует вредоносные программы в течение нескольких секунд.</span><span class="sxs-lookup"><span data-stu-id="d2209-203">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="d2209-204">Несмотря на то, что не существует определенного параметра под названием "Блок с первого взгляда", функция включена при настройке определенных параметров на устройстве.</span><span class="sxs-lookup"><span data-stu-id="d2209-204">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="d2209-205">Управление блоком с первого взгляда на собственном устройстве или выключение</span><span class="sxs-lookup"><span data-stu-id="d2209-205">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="d2209-206">Если у вас есть личное устройство, которое не управляется организацией, вам может быть интересно, как включить блокировку с первого взгляда или отключить.</span><span class="sxs-lookup"><span data-stu-id="d2209-206">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="d2209-207">С помощью приложения Windows Security можно управлять блоком с первого взгляда.</span><span class="sxs-lookup"><span data-stu-id="d2209-207">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="d2209-208">На компьютере Windows 10 откройте приложение Windows Security.</span><span class="sxs-lookup"><span data-stu-id="d2209-208">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="d2209-209">Выберите **защиту & вирусов.**</span><span class="sxs-lookup"><span data-stu-id="d2209-209">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="d2209-210">В **соответствии с & параметров** защиты от угроз выберите **Параметры Управления**.</span><span class="sxs-lookup"><span data-stu-id="d2209-210">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="d2209-211">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d2209-211">Take one of the following steps:</span></span>

   - <span data-ttu-id="d2209-212">Чтобы включить блок на первый взгляд, убедитесь, что **обе** системы защиты с облачной доставкой и **автоматическая** отправка образцов будут включены.</span><span class="sxs-lookup"><span data-stu-id="d2209-212">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="d2209-213">Чтобы отключить блокировку на первый взгляд, **отключите** облачную защиту или **автоматическую отправку образца.**</span><span class="sxs-lookup"><span data-stu-id="d2209-213">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="d2209-214">Отключение блока с первого взгляда снижает уровень защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="d2209-214">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="d2209-215">Мы не рекомендуем навсегда отключить блок с первого взгляда.</span><span class="sxs-lookup"><span data-stu-id="d2209-215">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="d2209-216">См. также</span><span class="sxs-lookup"><span data-stu-id="d2209-216">See also</span></span>

- [<span data-ttu-id="d2209-217">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="d2209-217">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d2209-218">Включить облачную защиту</span><span class="sxs-lookup"><span data-stu-id="d2209-218">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d2209-219">Безопасность Windows защищена</span><span class="sxs-lookup"><span data-stu-id="d2209-219">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)