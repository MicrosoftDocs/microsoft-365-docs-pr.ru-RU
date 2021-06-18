---
title: Блокировка при первом подозрении для обнаружения вредоносных программ за считанные секунды
description: Включите блокировку при первом подозрении, чтобы обнаруживать и блокировать вредоносные программы за считанные секунды.
keywords: сканирование, блокировка при первом подозрении, вредоносная программа, первое подозрение, облако, защитник, антивирусная программа
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: marcmcc
manager: dansimp
ms.custom: nextgen
ms.date: 06/17/2021
ms.technology: mde
ms.topic: article
ms.openlocfilehash: a6bcc023571e544819ae7f276e6c3af5c1fc1335
ms.sourcegitcommit: bbad1938b6661d4a6bca99f235c44e521b1fb662
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/18/2021
ms.locfileid: "53007405"
---
# <a name="turn-on-block-at-first-sight"></a><span data-ttu-id="d2899-104">Включить блокировку при первом подозрении</span><span class="sxs-lookup"><span data-stu-id="d2899-104">Turn on block at first sight</span></span>

<span data-ttu-id="d2899-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d2899-105">**Applies to:**</span></span>

- [<span data-ttu-id="d2899-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d2899-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="d2899-107">В этой статье описывается функция для борьбы с вирусами и вредоносными программами, известная как "блокировка при первом подозрении". В статье описано включение блокировки при первом подозрении в инфраструктуре вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d2899-107">This article describes an antivirus/antimalware feature known as "block at first sight", and describes how to enable block at first sight for your organization.</span></span> 

> [!TIP]
> <span data-ttu-id="d2899-108">Эта статья предназначена для администраторов предприятий и сотрудников ИТ, управляющих настройками безопасности для организаций.</span><span class="sxs-lookup"><span data-stu-id="d2899-108">This article is intended for enterprise admins and IT Pros who manage security settings for organizations.</span></span> <span data-ttu-id="d2899-109">Если вы не администратор и не сотрудник ИТ, но у вас есть вопросы о блокировке при первом появлении, см. раздел [Не администратор предприятия и не сотрудник ИТ?](#not-an-enterprise-admin-or-it-pro)</span><span class="sxs-lookup"><span data-stu-id="d2899-109">If you are not an enteprise admin or IT Pro but you have questions about block at first sight, see the [Not an enterprise admin or IT Pro?](#not-an-enterprise-admin-or-it-pro) section.</span></span>

## <a name="what-is-block-at-first-sight"></a><span data-ttu-id="d2899-110">Что такое блокировка при первом подозрении?</span><span class="sxs-lookup"><span data-stu-id="d2899-110">What is "block at first sight"?</span></span>

<span data-ttu-id="d2899-111">Блокировка при первом подозрении — это функция нового поколения для защиты от угроз, которая обнаруживает новые вредоносные программы и блокирует их за считанные секунды.</span><span class="sxs-lookup"><span data-stu-id="d2899-111">Block at first sight is a threat protection feature of next-generation protection that detects new malware and blocks it within seconds.</span></span> <span data-ttu-id="d2899-112">Блокировку при первом взгляда подозрении можно активировать, включив определенные параметры безопасности.</span><span class="sxs-lookup"><span data-stu-id="d2899-112">Block at first sight is enabled when certain security settings are enabled.</span></span> <span data-ttu-id="d2899-113">К этим параметрам относятся:</span><span class="sxs-lookup"><span data-stu-id="d2899-113">These settings include:</span></span>

- <span data-ttu-id="d2899-114">облачная защита;</span><span class="sxs-lookup"><span data-stu-id="d2899-114">Cloud-delivered protection;</span></span> 
- <span data-ttu-id="d2899-115">ограничение по времени для ожидания отправки примера (например, 50 секунд);</span><span class="sxs-lookup"><span data-stu-id="d2899-115">A specified sample submission timeout (such as 50 seconds); and</span></span> 
- <span data-ttu-id="d2899-116">значение "высокий" для уровня блокировки файлов.</span><span class="sxs-lookup"><span data-stu-id="d2899-116">A file-blocking level of high.</span></span> 

<span data-ttu-id="d2899-117">В большинстве корпоративных организаций параметры, необходимые для блокировки при первом подозрении, настраиваются при развертывании антивирусной программы в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d2899-117">In most enterprise organizations, the settings needed to enable block at first sight are configured with Microsoft Defender Antivirus deployments.</span></span> 

## <a name="how-it-works"></a><span data-ttu-id="d2899-118">Принципы действия</span><span class="sxs-lookup"><span data-stu-id="d2899-118">How it works</span></span>

<span data-ttu-id="d2899-119">Обнаружив подозрительный, но не обнаруженный ранее файл, антивирусная программа в Microsoft Defender отправляет запрос в нашу тыловую облачную защиту.</span><span class="sxs-lookup"><span data-stu-id="d2899-119">When Microsoft Defender Antivirus encounters a suspicious but undetected file, it queries our cloud protection backend.</span></span> <span data-ttu-id="d2899-120">Тыловая облачная защита применяет эвристические алгоритмы, машинное обучение и автоматический анализ файла, чтобы определить, является ли он вредоносным.</span><span class="sxs-lookup"><span data-stu-id="d2899-120">The cloud backend applies heuristics, machine learning, and automated analysis of the file to determine whether the files are malicious or not a threat.</span></span>

<span data-ttu-id="d2899-121">Антивирусная программа в Microsoft Defender использует несколько технологий обнаружения и предотвращения для обеспечения безошибочной интеллектуальной защиты в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="d2899-121">Microsoft Defender Antivirus uses multiple detection and prevention technologies to deliver accurate, intelligent, and real-time protection.</span></span> 

![Список антивирусных обработчиков в Microsoft Defender](images/microsoft-defender-atp-next-generation-protection-engines.png)  

> [!TIP]
> <span data-ttu-id="d2899-123">Подробности см. в блоге [Узнайте о передовых технологиях, лежащих в основе защиты нового поколения Microsoft Defender для конечной точки](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span><span class="sxs-lookup"><span data-stu-id="d2899-123">To learn more, see [(Blog) Get to know the advanced technologies at the core of Microsoft Defender for Endpoint next-generation protection](https://www.microsoft.com/security/blog/2019/06/24/inside-out-get-to-know-the-advanced-technologies-at-the-core-of-microsoft-defender-atp-next-generation-protection/).</span></span>

## <a name="a-few-things-to-know-about-block-at-first-sight"></a><span data-ttu-id="d2899-124">Вот несколько важных фактов о блокировке при первом подозрении</span><span class="sxs-lookup"><span data-stu-id="d2899-124">A few things to know about block at first sight</span></span>

- <span data-ttu-id="d2899-125">В Windows 10 начиная с версии 1803 блокировка при первом подозрении может срабатывать в отношении непереносимых исполняемых файлов (например, JS, VBS или макросов) и других исполняемых файлов.</span><span class="sxs-lookup"><span data-stu-id="d2899-125">In Windows 10, version 1803 or later, block at first sight can block non-portable executable files (such as JS, VBS, or macros) and executable files.</span></span>

- <span data-ttu-id="d2899-126">Блокировка при первом подозрении использует только тыловую облачную защиту для исполняемых файлов и непереносимых исполняемых файлов, скачанных из Интернета или происходящих из зоны Интернета.</span><span class="sxs-lookup"><span data-stu-id="d2899-126">Block at first sight only uses the cloud protection backend for executable files and non-portable executable files that are downloaded from the Internet, or that originate from the Internet zone.</span></span> <span data-ttu-id="d2899-127">Хэш-значение exe-файла проверяется тыловой облачной защитой, чтобы определить, действительно ли такой файл не обнаруживался ранее.</span><span class="sxs-lookup"><span data-stu-id="d2899-127">A hash value of the .exe file is checked via the cloud backend to determine if the file is a previously undetected file.</span></span>

- <span data-ttu-id="d2899-128">Если тыловой облачной защите не удается определить, вредоносный этот файл или нет, антивирусная программа в Microsoft Defender заблокирует файл и загрузит его копию в облако.</span><span class="sxs-lookup"><span data-stu-id="d2899-128">If the cloud backend is unable to make a determination, Microsoft Defender Antivirus locks the file and uploads a copy to the cloud.</span></span> <span data-ttu-id="d2899-129">В облаке выполняется дальнейший анализ для определения вредоносности файла, прежде чем разрешить его запуск либо блокировать его при обнаружении в будущем — в зависимости от того, определен ли файл как вредоносный или не представляющий угрозы.</span><span class="sxs-lookup"><span data-stu-id="d2899-129">The cloud performs more analysis to reach a determination before it either allows the file to run or blocks it in all future encounters, depending on whether it determines the file to be malicious or not a threat.</span></span>

- <span data-ttu-id="d2899-130">Во многих случаях этот процесс позволяет сократить время реакции на новые вредоносные программы с часов до секунд.</span><span class="sxs-lookup"><span data-stu-id="d2899-130">In many cases, this process can reduce the response time for new malware from hours to seconds.</span></span>

- <span data-ttu-id="d2899-131">Вы можете [указать, как долго файл следует удерживать от запуска](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md), пока облачная служба защиты анализирует его</span><span class="sxs-lookup"><span data-stu-id="d2899-131">You can [specify how long a file should be prevented from running](configure-cloud-block-timeout-period-microsoft-defender-antivirus.md) while the cloud-based protection service analyzes the file.</span></span> <span data-ttu-id="d2899-132">Вы также можете [настроить сообщения, которые будут отправляться на компьютеры пользователей ](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) при блокировке файлов.</span><span class="sxs-lookup"><span data-stu-id="d2899-132">And, you can [customize the message displayed on users' desktops](/windows/security/threat-protection//windows-defender-security-center/wdsc-customize-contact-information.md) when a file is blocked.</span></span> <span data-ttu-id="d2899-133">Вы можете изменить название компании, контактные данные и URL-адрес сообщения.</span><span class="sxs-lookup"><span data-stu-id="d2899-133">You can change the company name, contact information, and message URL.</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-intune"></a><span data-ttu-id="d2899-134">Включение блокировки при первом подозрении с помощью Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="d2899-134">Turn on block at first sight with Microsoft Intune</span></span>

> [!TIP]
> <span data-ttu-id="d2899-135">Microsoft Intune теперь интегрирован с Microsoft Endpoint Manager. </span><span class="sxs-lookup"><span data-stu-id="d2899-135">Microsoft Intune is now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="d2899-136">В Центре администрирования Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) перейдите в раздел **Приложения** > **Профили конфигурации**.</span><span class="sxs-lookup"><span data-stu-id="d2899-136">In the Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), navigate to **Devices** > **Configuration profiles**.</span></span>

2. <span data-ttu-id="d2899-137">Выберите или создайте профиль на основе типа профиля **Ограничения для устройств**.</span><span class="sxs-lookup"><span data-stu-id="d2899-137">Select or create a profile using the **Device restrictions** profile type.</span></span>

3. <span data-ttu-id="d2899-138">В разделе **Параметры конфигурации** для профиля ограничений устройств в разделе **Антивирусная программа в Microsoft Defender** установите или подтвердите следующие параметры.</span><span class="sxs-lookup"><span data-stu-id="d2899-138">In the **Configuration settings** for the Device restrictions profile, set or confirm the following settings under **Microsoft Defender Antivirus**:</span></span>

   - <span data-ttu-id="d2899-139">**Уровень облачной защиты**: включено</span><span class="sxs-lookup"><span data-stu-id="d2899-139">**Cloud-delivered protection**: Enabled</span></span>
   - <span data-ttu-id="d2899-140">**Уровень блокировки файлов**: высокий</span><span class="sxs-lookup"><span data-stu-id="d2899-140">**File Blocking Level**: High</span></span>
   - <span data-ttu-id="d2899-141">**Дополнительное время для сканирования файла в облаке**: 50</span><span class="sxs-lookup"><span data-stu-id="d2899-141">**Time extension for file scanning by the cloud**: 50</span></span>
   - <span data-ttu-id="d2899-142">**Запрашивать пользователей перед отправкой образца**: отправлять все данные без запроса</span><span class="sxs-lookup"><span data-stu-id="d2899-142">**Prompt users before sample submission**: Send all data without prompting</span></span>

   :::image type="content" source="../../media/intune-block-at-first-sight.png" alt-text="Конфигурация Intune для блокировки при первом появлении":::

4. <span data-ttu-id="d2899-144">Сохраните заданные параметры.</span><span class="sxs-lookup"><span data-stu-id="d2899-144">Save your settings.</span></span>

> [!TIP]
> - <span data-ttu-id="d2899-145">При установке уровня блокировки файлов **Высокий** применяется высокий уровень обнаружения.</span><span class="sxs-lookup"><span data-stu-id="d2899-145">Setting the file blocking level to **High** applies a strong level of detection.</span></span> <span data-ttu-id="d2899-146">В маловероятном случае, когда блокировка вызвана ложно-положительным срабатыванием для безобидных файлов, ваши сотрудники отдела безопасности смогут [восстановить файлы из карантина](./restore-quarantined-files-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="d2899-146">In the unlikely event that file blocking causes a false positive detection of legitimate files, your security operations team can [restore quarantined files](./restore-quarantined-files-microsoft-defender-antivirus.md).</span></span>
> - <span data-ttu-id="d2899-147">Дополнительные сведения о настройке параметров ограничения устройств антивирусной программы в Microsoft Defender для Intune см. в статье [Параметры ограничений устройств в Microsoft Intune](/intune/device-restrictions-configure).</span><span class="sxs-lookup"><span data-stu-id="d2899-147">For more information about configuring Microsoft Defender Antivirus device restrictions in Intune, see [Configure device restriction settings in Microsoft Intune](/intune/device-restrictions-configure).</span></span>
> - <span data-ttu-id="d2899-148">Список ограничений для антивирусных устройств в Microsoft Defender в Intune см. в статье [Ограничения для устройств в Windows 10 (и более новых версиях) в Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span><span class="sxs-lookup"><span data-stu-id="d2899-148">For a list of Microsoft Defender Antivirus device restrictions in Intune, see [Device restriction for Windows 10 (and newer) settings in Intune](/intune/device-restrictions-windows-10#microsoft-defender-antivirus).</span></span>

## <a name="turn-on-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="d2899-149">Включение блокировки при первом подозрении с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2899-149">Turn on block at first sight with Microsoft Endpoint Manager</span></span>

> [!TIP]
> <span data-ttu-id="d2899-150">Если вы ищете Microsoft Endpoint Configuration Manager, он теперь входит в состав Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="d2899-150">If you're looking for Microsoft Endpoint Configuration Manager, it's now part of Microsoft Endpoint Manager.</span></span>

1. <span data-ttu-id="d2899-151">В Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) перейдите в раздел **Защита конечной точки** > **Антивирусная программа**.</span><span class="sxs-lookup"><span data-stu-id="d2899-151">In Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)), go to **Endpoint security** > **Antivirus**.</span></span>

2. <span data-ttu-id="d2899-152">Выберите существующую политику или создайте новую на основе типа профиля **Антивирусная программа в Microsoft Defender**.</span><span class="sxs-lookup"><span data-stu-id="d2899-152">Select an existing policy, or create a new policy using the **Microsoft Defender Antivirus** profile type.</span></span>

3. <span data-ttu-id="d2899-153">Установите или подтвердите следующие параметры конфигурации:</span><span class="sxs-lookup"><span data-stu-id="d2899-153">Set or confirm the following configuration settings:</span></span>

   - <span data-ttu-id="d2899-154">**Включить облачную защиту**: да</span><span class="sxs-lookup"><span data-stu-id="d2899-154">**Turn on cloud-delivered protection**: Yes</span></span>
   - <span data-ttu-id="d2899-155">**Уровень облачной защиты**: высокий</span><span class="sxs-lookup"><span data-stu-id="d2899-155">**Cloud-delivered protection level**: High</span></span>
   - <span data-ttu-id="d2899-156">**Дополнительное время (в секундах) обработки файла в облачном Защитнике**: 50</span><span class="sxs-lookup"><span data-stu-id="d2899-156">**Defender Cloud Extended Timeout in Seconds**: 50</span></span>

   :::image type="content" source="images/endpointmgr-antivirus-cloudprotection.png" alt-text="Настройка блокировки в Endpoint Manager при первом подозрении":::

4. <span data-ttu-id="d2899-158">Примените профиль антивирусной программы в Microsoft Defender к группе, например **Все пользователи**, **Все устройства** или **Все пользователи и устройства**.</span><span class="sxs-lookup"><span data-stu-id="d2899-158">Apply the Microsoft Defender Antivirus profile to a group, such as **All users**, **All devices**, or **All users and devices**.</span></span>

## <a name="turn-on-block-at-first-sight-with-group-policy"></a><span data-ttu-id="d2899-159">Включение блокировки при первом подозрении с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="d2899-159">Turn on block at first sight with Group Policy</span></span>

> [!NOTE]
> <span data-ttu-id="d2899-160">Мы рекомендуем включить блокировку при первом подозрении через Intune или Microsoft Endpoint Manager.</span><span class="sxs-lookup"><span data-stu-id="d2899-160">We recommend using Intune or Microsoft Endpoint Manager to turn on block at first sight.</span></span> 

1. <span data-ttu-id="d2899-161">Для этого на компьютере, управляющем групповыми политиками, откройте [Консоль управления групповой политикой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), щелкните правой кнопкой мыши нужный объект групповой политики и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d2899-161">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure and select **Edit**.</span></span> 

2. <span data-ttu-id="d2899-162">С помощью **Редактора управления групповыми политиками** перейдите в **Конфигурация компьютера** > **Административные шаблоны** > **Компоненты Windows** > **Антивирусная программа в Microsoft Defender** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="d2899-162">Using the **Group Policy Management Editor** go to **Computer configuration** > **Administrative templates** > **Windows Components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span> 

3. <span data-ttu-id="d2899-163">В разделе MAPS дважды щелкните **Настроить блокировку при первом подозрении** и установите для этого параметра значение **Включено**, а затем нажмите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d2899-163">In the MAPS section, double-click **Configure the 'Block at First Sight' feature**, and set it to **Enabled**, and then select **OK**.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="d2899-164">Установка параметра **Всегда запрашивать (0)** понизит состояние защиты устройства.</span><span class="sxs-lookup"><span data-stu-id="d2899-164">Setting to **Always prompt (0)** will lower the protection state of the device.</span></span> <span data-ttu-id="d2899-165">Значение **Никогда не отправлять (2)** означает, что блокировка при первом подозрении работать не будет.</span><span class="sxs-lookup"><span data-stu-id="d2899-165">Setting to **Never send (2)** means block at first sight will not function.</span></span>

4. <span data-ttu-id="d2899-166">В разделе MAPS дважды щелкните **Отправлять образцы файлов, если требуется дальнейший анализ** и установите значение **Включено**.</span><span class="sxs-lookup"><span data-stu-id="d2899-166">In the MAPS section, double-click **Send file samples when further analysis is required**, and set it to **Enabled**.</span></span> <span data-ttu-id="d2899-167">Для параметра **Отправка образцов файлов, когда требуется дальнейший анализ**, выберите **Отправлять все образцы**, а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="d2899-167">Under **Send file samples when further analysis is required**, select **Send all samples**, and then select **OK**.</span></span>

5. <span data-ttu-id="d2899-168">Заново разверните объект групповой политики в своей инфраструктуре обычным порядком.</span><span class="sxs-lookup"><span data-stu-id="d2899-168">Redeploy your Group Policy Object across your network as you usually do.</span></span>

## <a name="confirm-block-at-first-sight-is-enabled-on-individual-client-devices"></a><span data-ttu-id="d2899-169">Подтверждение включения блокировки при первом подозрении на отдельных клиентских устройствах</span><span class="sxs-lookup"><span data-stu-id="d2899-169">Confirm block at first sight is enabled on individual client devices</span></span>

<span data-ttu-id="d2899-170">Вы можете подтвердить, что блокировка при первом подозрении включена на отдельных клиентских устройствах, с помощью приложения "Безопасность Windows".</span><span class="sxs-lookup"><span data-stu-id="d2899-170">You can confirm that block at first sight is enabled on individual client devices using the Windows Security app.</span></span> <span data-ttu-id="d2899-171">Блокировка при первом подозрении автоматически включена, если включены оба параметра: **Облачная защита** и **Автоматическая отправка образцов**.</span><span class="sxs-lookup"><span data-stu-id="d2899-171">Block at first sight is automatically enabled as long as **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

1. <span data-ttu-id="d2899-172">Откройте приложение "Безопасность Windows".</span><span class="sxs-lookup"><span data-stu-id="d2899-172">Open the Windows Security app.</span></span>

2. <span data-ttu-id="d2899-173">Выберите **Защита от вирусов и угроз**, а затем в области **Параметры защиты от вирусов и угроз** выберите **Управление параметрами**.</span><span class="sxs-lookup"><span data-stu-id="d2899-173">Select **Virus & threat protection**, and then, under **Virus & threat protection settings**, select **Manage Settings**.</span></span>

   :::image type="content" source="../../media/wdav-protection-settings-wdsc.png" alt-text="Снимок экрана: метка параметров защиты от вирусов и угроз в приложении &quot;Безопасность Windows&quot;":::

3. <span data-ttu-id="d2899-175">Убедитесь, что оба параметра, **Облачная защита** и **Автоматическая отправка образцов**, включены.</span><span class="sxs-lookup"><span data-stu-id="d2899-175">Confirm that **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

> [!NOTE]
> - <span data-ttu-id="d2899-176">Если необходимые параметры настроены и развернуты с помощью групповой политики, элементы управления параметрами, описанными в этом разделе, будут деактивированы и недоступны для использования на отдельных конечных точках.</span><span class="sxs-lookup"><span data-stu-id="d2899-176">If the prerequisite settings are configured and deployed using Group Policy, the settings described in this section will be greyed-out and unavailable for use on individual endpoints.</span></span> 
> - <span data-ttu-id="d2899-177">Изменения, внесенные с помощью объекта групповой политики, необходимо сначала развернуть на отдельных конечных точках, прежде чем параметр будет обновлен в настройках Windows.</span><span class="sxs-lookup"><span data-stu-id="d2899-177">Changes made through a Group Policy Object must first be deployed to individual endpoints before the setting will be updated in Windows Settings.</span></span>

## <a name="validate-block-at-first-sight-is-working"></a><span data-ttu-id="d2899-178">Проверьте, работает ли блокировка при первом подозрении</span><span class="sxs-lookup"><span data-stu-id="d2899-178">Validate block at first sight is working</span></span>

<span data-ttu-id="d2899-179">Чтобы проверить работу функции, скачайте [пример файла блокировки при первом появлении](https://demo.wd.microsoft.com/Page/BAFS).</span><span class="sxs-lookup"><span data-stu-id="d2899-179">To validate that the feature is working, download the [Block at first sight sample file](https://demo.wd.microsoft.com/Page/BAFS).</span></span> <span data-ttu-id="d2899-180">Чтобы скачать файл, вам потребуется учетная запись в Azure AD с назначенной ролью "Администратор безопасности" или "Глобальный администратор".</span><span class="sxs-lookup"><span data-stu-id="d2899-180">To download the file, you will need an account in Azure AD that has either the Security Administrator or Global Administrator role assigned.</span></span>

<span data-ttu-id="d2899-181">Чтобы проверить, работает ли облачная защита, следуйте инструкциям, изложенным в разделе [Проверка подключений между сетью и облаком](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span><span class="sxs-lookup"><span data-stu-id="d2899-181">To validate that cloud-enabled protection is working, follow the guidance in [Validate connections between your network and the cloud](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud).</span></span> 

## <a name="turn-off-block-at-first-sight"></a><span data-ttu-id="d2899-182">Отключение блокировки при первом подозрении</span><span class="sxs-lookup"><span data-stu-id="d2899-182">Turn off block at first sight</span></span>

> [!CAUTION]
> <span data-ttu-id="d2899-183">Отключение блокировки при первом подозрении понизит уровень защиты устройств и сети.</span><span class="sxs-lookup"><span data-stu-id="d2899-183">Turning off block at first sight will lower the protection state of your device(s) and your network.</span></span>

<span data-ttu-id="d2899-184">Вы можете отключить блокировку при первом подозрении, если хотите сохранить те же значения параметров, но без использования блокировки при первом подозрении.</span><span class="sxs-lookup"><span data-stu-id="d2899-184">You might choose to disable block at first sight if you want to retain the prerequisite settings without actually using block at first sight protection.</span></span> <span data-ttu-id="d2899-185">Вы можете временно отключить блокировку при первом подозрении, чтобы посмотреть, как эта функция влияет на работу вашей инфраструктуры.</span><span class="sxs-lookup"><span data-stu-id="d2899-185">You might temporarily turn block at first sight off to see how this feature affects your network.</span></span> <span data-ttu-id="d2899-186">Однако мы не рекомендуем окончательно отключать блокировку при первом подозрении.</span><span class="sxs-lookup"><span data-stu-id="d2899-186">However, we do not recommend disabling block at first sight protection permanently.</span></span>

### <a name="turn-off-block-at-first-sight-with-microsoft-endpoint-manager"></a><span data-ttu-id="d2899-187">Выключение блокировки при первом подозрении с помощью Microsoft Endpoint Manager</span><span class="sxs-lookup"><span data-stu-id="d2899-187">Turn off block at first sight with Microsoft Endpoint Manager</span></span>

1. <span data-ttu-id="d2899-188">Войдите в Центр администрирования Microsoft Endpoint Manager ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) и выполните вход в систему.</span><span class="sxs-lookup"><span data-stu-id="d2899-188">Go to Microsoft Endpoint Manager admin center ([https://endpoint.microsoft.com](https://endpoint.microsoft.com)) and sign in.</span></span>

2. <span data-ttu-id="d2899-189">Перейдите в раздел **Безопасность конечной точки** > **Антивирусная программа**, а затем выберите свою политику антивирусной программы в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="d2899-189">Go to **Endpoint security** > **Antivirus**, and then select your Microsoft Defender Antivirus policy.</span></span>

3. <span data-ttu-id="d2899-190">В разделе **Управление** выберите **Свойства**.</span><span class="sxs-lookup"><span data-stu-id="d2899-190">Under **Manage**, choose **Properties**.</span></span>

4. <span data-ttu-id="d2899-191">Рядом с **Параметры конфигурации** выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d2899-191">Next to **Configuration settings**, choose **Edit**.</span></span>

5. <span data-ttu-id="d2899-192">Измените один или несколько следующих параметров:</span><span class="sxs-lookup"><span data-stu-id="d2899-192">Change one or more of the following settings:</span></span>

   - <span data-ttu-id="d2899-193">Установите для параметра **Включить облачную защиту** значение **Нет** или **Не настроено**.</span><span class="sxs-lookup"><span data-stu-id="d2899-193">Set **Turn on cloud-delivered protection** to **No** or **Not configured**.</span></span>
   - <span data-ttu-id="d2899-194">Установите для параметра **Уровень облачной защиты** значение **Не настроено**.</span><span class="sxs-lookup"><span data-stu-id="d2899-194">Set **Cloud-delivered protection level** to **Not configured**.</span></span>
   - <span data-ttu-id="d2899-195">Снимите флажок с параметра **Дополнительное время (в секундах) обработки файла в облачном Защитнике**.</span><span class="sxs-lookup"><span data-stu-id="d2899-195">Clear the check box for **Defender Cloud Extended Timeout In Seconds**.</span></span>

6. <span data-ttu-id="d2899-196">Проверьте новые значения и сохраните параметры.</span><span class="sxs-lookup"><span data-stu-id="d2899-196">Review and save your settings.</span></span>

### <a name="turn-off-block-at-first-sight-with-group-policy"></a><span data-ttu-id="d2899-197">Отключение блокировки при первом подозрении с помощью групповой политики</span><span class="sxs-lookup"><span data-stu-id="d2899-197">Turn off block at first sight with Group Policy</span></span>

1. <span data-ttu-id="d2899-198">Для этого на компьютере, управляющем групповыми политиками, откройте [Консоль управления групповой политикой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), щелкните правой кнопкой мыши нужный объект групповой политики и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="d2899-198">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)), right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

2. <span data-ttu-id="d2899-199">В **Редакторе управления групповыми политиками** перейдите в раздел **Конфигурация компьютера** и выберите **Административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="d2899-199">Using the **Group Policy Management Editor** go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="d2899-200">Разверните дерево до узла **Компоненты Windows** > **Антивирусная программа в Microsoft Defender** > **MAPS**.</span><span class="sxs-lookup"><span data-stu-id="d2899-200">Expand the tree through **Windows components** > **Microsoft Defender Antivirus** > **MAPS**.</span></span>

4. <span data-ttu-id="d2899-201">Дважды щелкните **Настроить функцию "Блокировать при первом подозрении"** и установить значение **Выключено**.</span><span class="sxs-lookup"><span data-stu-id="d2899-201">Double-click **Configure the 'Block at First Sight' feature** and set the option to **Disabled**.</span></span>

    > [!NOTE]
    > <span data-ttu-id="d2899-202">Отключение блокировки при первом подозрении не отключает или не изменяет необходимые групповые политики.</span><span class="sxs-lookup"><span data-stu-id="d2899-202">Disabling block at first sight does not disable or alter the prerequisite group policies.</span></span>

## <a name="not-an-enterprise-admin-or-it-pro"></a><span data-ttu-id="d2899-203">Не администратор предприятия и не сотрудник ИТ?</span><span class="sxs-lookup"><span data-stu-id="d2899-203">Not an enterprise admin or IT Pro?</span></span>

<span data-ttu-id="d2899-204">Если вы не администратор или ИТ-профессионал, но у вас есть вопросы о блокировке при первом подозрении, см. раздел "Не администратор предприятия и не сотрудник ИТ?"</span><span class="sxs-lookup"><span data-stu-id="d2899-204">If you are not an enterprise admin or IT Pro, but you have questions about block at first sight, this section is for you.</span></span> <span data-ttu-id="d2899-205">Блокировка при первом подозрении обнаруживает новые вредоносные программы и блокирует их за считанные секунды.</span><span class="sxs-lookup"><span data-stu-id="d2899-205">Block at first sight is a threat protection feature that detects and blocks malware within seconds.</span></span> <span data-ttu-id="d2899-206">Хотя параметра "Блокировать при первом подозрении" как такового не существует, функция включена, если на устройстве настроены определенные параметры.</span><span class="sxs-lookup"><span data-stu-id="d2899-206">Although there isn't a specific setting called "Block at first sight," the feature is enabled when certain settings are configured on your device.</span></span>

### <a name="how-to-manage-block-at-first-sight-on-or-off-on-your-own-device"></a><span data-ttu-id="d2899-207">Управление блокировкой при первом подозрении: включение и отключение на личном устройстве</span><span class="sxs-lookup"><span data-stu-id="d2899-207">How to manage block at first sight on or off on your own device</span></span>

<span data-ttu-id="d2899-208">Если у вас есть личное устройство, не управляемое организацией, возможно, вам захочется включить или отключить блокировку при первом подозрении.</span><span class="sxs-lookup"><span data-stu-id="d2899-208">If you have a personal device that is not managed by an organization, you might be wondering how to turn block at first sight on or off.</span></span> <span data-ttu-id="d2899-209">Для управления этой функцией можно использовать приложение "Безопасность Windows"..</span><span class="sxs-lookup"><span data-stu-id="d2899-209">You can use the Windows Security app to manage block at first sight.</span></span>

1. <span data-ttu-id="d2899-210">На компьютере с Windows 10 откройте приложение "Безопасность Windows".</span><span class="sxs-lookup"><span data-stu-id="d2899-210">On your Windows 10 computer, open the Windows Security app.</span></span>

2. <span data-ttu-id="d2899-211">Выберите **Защита от вирусов и угроз**.</span><span class="sxs-lookup"><span data-stu-id="d2899-211">Select **Virus & threat protection**.</span></span>

3. <span data-ttu-id="d2899-212">В разделе **Защита от вирусов и угроз** выберите **Управление параметрами**.</span><span class="sxs-lookup"><span data-stu-id="d2899-212">Under **Virus & threat protection settings**, select **Manage settings**.</span></span>

4. <span data-ttu-id="d2899-213">Выполните одно из следующих действий:</span><span class="sxs-lookup"><span data-stu-id="d2899-213">Take one of the following steps:</span></span>

   - <span data-ttu-id="d2899-214">Чтобы настроить блокировку при первом подозрении, включите оба параметра: **Облачная защита** и **Автоматическая отправка образцов**.</span><span class="sxs-lookup"><span data-stu-id="d2899-214">To enable block at first sight, make sure that both **Cloud-delivered protection** and **Automatic sample submission** are both turned on.</span></span>

   - <span data-ttu-id="d2899-215">Чтобы убрать блокировку при первом подозрении, отключите один из параметров: **Облачная защита** или **Автоматическая отправка образцов**.</span><span class="sxs-lookup"><span data-stu-id="d2899-215">To disable block at first sight, turn off **Cloud-delivered protection** or **Automatic sample submission**.</span></span> <br/>
    
     > [!CAUTION]
     > <span data-ttu-id="d2899-216">Отключение блокировки при первом подозрении снижает уровень защиты вашего устройства.</span><span class="sxs-lookup"><span data-stu-id="d2899-216">Turning off block at first sight lowers the level of protection for your device.</span></span> <span data-ttu-id="d2899-217">Мы не рекомендуем отключать блокировку при первом подозрении насовсем.</span><span class="sxs-lookup"><span data-stu-id="d2899-217">We do not recommend permanently disabling block at first sight.</span></span> 


## <a name="see-also"></a><span data-ttu-id="d2899-218">См. также</span><span class="sxs-lookup"><span data-stu-id="d2899-218">See also</span></span>

- [<span data-ttu-id="d2899-219">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="d2899-219">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="d2899-220">Включение облачной защиты</span><span class="sxs-lookup"><span data-stu-id="d2899-220">Enable cloud-delivered protection</span></span>](enable-cloud-protection-microsoft-defender-antivirus.md)
- [<span data-ttu-id="d2899-221">Защита с помощью системы безопасности Windows</span><span class="sxs-lookup"><span data-stu-id="d2899-221">Stay protected with Windows Security</span></span>](https://support.microsoft.com/windows/stay-protected-with-windows-security-2ae0363d-0ada-c064-8b56-6a39afb6a963)
