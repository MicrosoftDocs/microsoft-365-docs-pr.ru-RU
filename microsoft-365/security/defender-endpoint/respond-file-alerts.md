---
title: Действия реагирования на файл в Microsoft Defender для конечной точки
description: Принимайте меры реагирования на оповещения, связанные с файлами, останавливая и карантин файл или блокируя файл и проверяя сведения о действиях.
keywords: ответ, остановка и карантин, блок-файл, глубокий анализ
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 1f189956d65e6d08d8e00272ba0d8db3ba59f6d4
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52844086"
---
# <a name="take-response-actions-on-a-file"></a><span data-ttu-id="dd5f0-104">Выполнение действий ответов в файле</span><span class="sxs-lookup"><span data-stu-id="dd5f0-104">Take response actions on a file</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="dd5f0-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="dd5f0-105">**Applies to:**</span></span>
- [<span data-ttu-id="dd5f0-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="dd5f0-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

> <span data-ttu-id="dd5f0-107">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="dd5f0-107">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="dd5f0-108">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-108">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-responddile-abovefoldlink)

<span data-ttu-id="dd5f0-109">Быстро реагируйте на обнаруженные атаки, останавливая и карантиновая файлы или блокируя файл.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-109">Quickly respond to detected attacks by stopping and quarantining files or blocking a file.</span></span> <span data-ttu-id="dd5f0-110">После принятия действий по файлам можно проверить сведения о действиях в центре действий.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-110">After taking action on files, you can check activity details in the Action center.</span></span>

<span data-ttu-id="dd5f0-111">Действия реагирования доступны на странице подробный профиль файла.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-111">Response actions are available on a file's detailed profile page.</span></span> <span data-ttu-id="dd5f0-112">Оказавшись на этой странице, вы можете переключаться между макетами новых и старых страниц, переключая новую страницу **File.**</span><span class="sxs-lookup"><span data-stu-id="dd5f0-112">Once on this page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="dd5f0-113">В остальной части этой статьи описывается более новая схема страницы.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-113">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="dd5f0-114">Действия реагирования, которые запускают по верхней части страницы файла, включают в себя:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-114">Response actions run along the top of the file page, and include:</span></span>

- <span data-ttu-id="dd5f0-115">Файл Стоп и Карантин</span><span class="sxs-lookup"><span data-stu-id="dd5f0-115">Stop and Quarantine File</span></span>
- <span data-ttu-id="dd5f0-116">Добавление индикатора</span><span class="sxs-lookup"><span data-stu-id="dd5f0-116">Add Indicator</span></span>
- <span data-ttu-id="dd5f0-117">Скачивание файла</span><span class="sxs-lookup"><span data-stu-id="dd5f0-117">Download file</span></span>
- <span data-ttu-id="dd5f0-118">Обратитесь к эксперту по угрозам</span><span class="sxs-lookup"><span data-stu-id="dd5f0-118">Consult a threat expert</span></span>
- <span data-ttu-id="dd5f0-119">Центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="dd5f0-119">Action center</span></span>

<span data-ttu-id="dd5f0-120">Вы также можете отправить файлы для глубокого анализа, чтобы запустить файл в безопасной облачной песочнице.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-120">You can also submit files for deep analysis, to run the file in a secure cloud sandbox.</span></span> <span data-ttu-id="dd5f0-121">По завершению анализа вы получите подробный отчет, который содержит сведения о поведении файла.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-121">When the analysis is complete, you'll get a detailed report that provides information about the behavior of the file.</span></span> <span data-ttu-id="dd5f0-122">Вы можете отправить файлы для глубокого анализа и прочитать прошлые отчеты, выбрав вкладку **Глубокий** анализ. Он расположен ниже карт данных файлов.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-122">You can submit files for deep analysis and read past reports by selecting the **Deep analysis** tab. It's located below the file information cards.</span></span>

<span data-ttu-id="dd5f0-123">Некоторые действия требуют определенных разрешений.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-123">Some actions require certain permissions.</span></span> <span data-ttu-id="dd5f0-124">В следующей таблице описывается, какие действия могут принимать определенные разрешения для переносных исполняемых (PE) и не pe-файлов:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-124">The following table describes what action certain permissions can take on portable executable (PE) and non-PE files:</span></span>

| <span data-ttu-id="dd5f0-125">Разрешение</span><span class="sxs-lookup"><span data-stu-id="dd5f0-125">Permission</span></span>             | <span data-ttu-id="dd5f0-126">ФАЙЛЫ PE</span><span class="sxs-lookup"><span data-stu-id="dd5f0-126">PE files</span></span> | <span data-ttu-id="dd5f0-127">Файлы non-PE</span><span class="sxs-lookup"><span data-stu-id="dd5f0-127">Non-PE files</span></span> |
| :--------------------- | :------: | :----------: |
| <span data-ttu-id="dd5f0-128">Просмотр данных</span><span class="sxs-lookup"><span data-stu-id="dd5f0-128">View data</span></span>              |     <span data-ttu-id="dd5f0-129">X</span><span class="sxs-lookup"><span data-stu-id="dd5f0-129">X</span></span>    |       <span data-ttu-id="dd5f0-130">X</span><span class="sxs-lookup"><span data-stu-id="dd5f0-130">X</span></span>      |
| <span data-ttu-id="dd5f0-131">Расследование оповещений</span><span class="sxs-lookup"><span data-stu-id="dd5f0-131">Alerts investigation</span></span>   | <span data-ttu-id="dd5f0-132">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="dd5f0-132">&#x2611;</span></span> |       <span data-ttu-id="dd5f0-133">X</span><span class="sxs-lookup"><span data-stu-id="dd5f0-133">X</span></span>      |
| <span data-ttu-id="dd5f0-134">Основной ответ в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="dd5f0-134">Live response basic</span></span>    |     <span data-ttu-id="dd5f0-135">X</span><span class="sxs-lookup"><span data-stu-id="dd5f0-135">X</span></span>    |       <span data-ttu-id="dd5f0-136">X</span><span class="sxs-lookup"><span data-stu-id="dd5f0-136">X</span></span>      |
| <span data-ttu-id="dd5f0-137">Расширенный ответ в прямом эфире</span><span class="sxs-lookup"><span data-stu-id="dd5f0-137">Live response advanced</span></span> | <span data-ttu-id="dd5f0-138">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="dd5f0-138">&#x2611;</span></span> |   <span data-ttu-id="dd5f0-139">&#x2611;</span><span class="sxs-lookup"><span data-stu-id="dd5f0-139">&#x2611;</span></span>   |

<span data-ttu-id="dd5f0-140">Дополнительные сведения о ролях см. в дополнительных сведениях о создании и управлении ролями для управления [доступом на](user-roles.md)основе ролей.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-140">For more information on roles, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="stop-and-quarantine-files-in-your-network"></a><span data-ttu-id="dd5f0-141">Остановка и помещение на карантин файлов в сети</span><span class="sxs-lookup"><span data-stu-id="dd5f0-141">Stop and quarantine files in your network</span></span>

<span data-ttu-id="dd5f0-142">Вы можете содержать атаку в организации, останавливая вредоносный процесс и карантин файла, в котором он был замечен.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-142">You can contain an attack in your organization by stopping the malicious process and quarantining the file where it was observed.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd5f0-143">Вы можете принять это действие только в том случае, если:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-143">You can only take this action if:</span></span>
>
> - <span data-ttu-id="dd5f0-144">Устройство, на которое вы принимаете действие, работает Windows 10 версии 1703 или более поздней версии</span><span class="sxs-lookup"><span data-stu-id="dd5f0-144">The device you're taking the action on is running Windows 10, version 1703 or later</span></span>
> - <span data-ttu-id="dd5f0-145">Файл не принадлежит доверенным сторонним издателям или не подписан Корпорацией Майкрософт</span><span class="sxs-lookup"><span data-stu-id="dd5f0-145">The file does not belong to trusted third-party publishers or not signed by Microsoft</span></span>
> - <span data-ttu-id="dd5f0-146">антивирусная программа в Microsoft Defender по крайней мере должен работать в пассивном режиме.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-146">Microsoft Defender Antivirus must at least be running on Passive mode.</span></span> <span data-ttu-id="dd5f0-147">Дополнительные сведения см. [в антивирусная программа в Microsoft Defender совместимости.](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)</span><span class="sxs-lookup"><span data-stu-id="dd5f0-147">For more information, see [Microsoft Defender Antivirus compatibility](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility).</span></span>

<span data-ttu-id="dd5f0-148">Действие **Stop and Quarantine File** включает остановку запущенных процессов, карантин файлов и удаление сохраняющихся данных, таких как ключи реестра.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-148">The **Stop and Quarantine File** action includes stopping running processes, quarantining the files, and deleting persistent data such as registry keys.</span></span>

<span data-ttu-id="dd5f0-149">Это действие действует на устройствах Windows 10 версии 1703 или более поздней версии, где файл был замечен в течение последних 30 дней.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-149">This action takes effect on devices with Windows 10, version 1703 or later, where the file was observed in the last 30 days.</span></span>

> [!NOTE]
> <span data-ttu-id="dd5f0-150">Вы сможете восстановить файл из карантина в любое время.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-150">You’ll be able to restore the file from quarantine at any time.</span></span>

### <a name="stop-and-quarantine-files"></a><span data-ttu-id="dd5f0-151">Файлы остановки и карантина</span><span class="sxs-lookup"><span data-stu-id="dd5f0-151">Stop and quarantine files</span></span>

1. <span data-ttu-id="dd5f0-152">Выберите файл, который необходимо остановить, и карантин.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-152">Select the file you want to stop and quarantine.</span></span> <span data-ttu-id="dd5f0-153">Вы можете выбрать файл из любого из следующих представлений или использовать поле Поиска:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-153">You can select a file from any of the following views or use the Search box:</span></span>

   - <span data-ttu-id="dd5f0-154">**Оповещений** — щелкните соответствующие ссылки из описания или подробных сведений в временной шкале Артефакт</span><span class="sxs-lookup"><span data-stu-id="dd5f0-154">**Alerts** - click the corresponding links from the Description or Details in the Artifact timeline</span></span>
   - <span data-ttu-id="dd5f0-155">**Поле поиска** — выберите **Файл** из выпадаемого меню и введите имя файла</span><span class="sxs-lookup"><span data-stu-id="dd5f0-155">**Search box** - select **File** from the drop–down menu and enter the file name</span></span>

   > [!NOTE]
   > <span data-ttu-id="dd5f0-156">Действие файла стопа и карантина ограничено не более 1000 устройств.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-156">The stop and quarantine file action is limited to a maximum of 1000 devices.</span></span> <span data-ttu-id="dd5f0-157">Чтобы остановить файл на большом количестве устройств, см. в добавлении индикатора [для блокировки или допуска файла.](#add-indicator-to-block-or-allow-a-file)</span><span class="sxs-lookup"><span data-stu-id="dd5f0-157">To stop a file on a larger number of devices, see [Add indicator to block or allow file](#add-indicator-to-block-or-allow-a-file).</span></span>

2. <span data-ttu-id="dd5f0-158">Перейдите в верхнюю планку и выберите **файл Стоп и Карантин.**</span><span class="sxs-lookup"><span data-stu-id="dd5f0-158">Go to the top bar and select **Stop and Quarantine File**.</span></span>

   ![Изображение действия стоп-файла и карантина](images/atp-stop-quarantine-file.png)

3. <span data-ttu-id="dd5f0-160">Укажите причину, а затем выберите **Подтверждение**.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-160">Specify a reason, then select **Confirm**.</span></span>

   ![Изображение окна модуля стоп-файла и карантина](images/atp-stop-quarantine.png)

   <span data-ttu-id="dd5f0-162">Центр действий показывает сведения о отправке:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-162">The Action center shows the submission information:</span></span>
   
   ![Изображение центра действий стоп-файлов и карантина](images/atp-stopnquarantine-file.png)

   - <span data-ttu-id="dd5f0-164">**Время отправки** — показывает, когда было отправлено действие.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-164">**Submission time** - Shows when the action was submitted.</span></span>
   - <span data-ttu-id="dd5f0-165">**Успех** — показывает количество устройств, на которых был остановлен файл и введен карантин.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-165">**Success** - Shows the number of devices where the file has been stopped and quarantined.</span></span>
   - <span data-ttu-id="dd5f0-166">**Сбой** — показывает количество устройств, на которых не удалось действие, и сведения о сбое.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-166">**Failed** - Shows the number of devices where the action failed and details about the failure.</span></span>
   - <span data-ttu-id="dd5f0-167">**Ожидание** — показывает количество устройств, с которых файл еще не остановлен и отложен на карантин.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-167">**Pending** - Shows the number of devices where the file is yet to be stopped and quarantined from.</span></span> <span data-ttu-id="dd5f0-168">Это может занять время для случаев, когда устройство отключено или не подключено к сети.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-168">This can take time for cases when the device is offline or not connected to the network.</span></span>

4. <span data-ttu-id="dd5f0-169">Выберите любой из индикаторов состояния, чтобы просмотреть дополнительные сведения о действии.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-169">Select any of the status indicators to view more information about the action.</span></span> <span data-ttu-id="dd5f0-170">Например, выберите **Не удалось увидеть,** где действие не удалось.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-170">For example, select **Failed** to see where the action failed.</span></span>

<span data-ttu-id="dd5f0-171">**Уведомление пользователя устройства:**</span><span class="sxs-lookup"><span data-stu-id="dd5f0-171">**Notification on device user**:</span></span></br>
<span data-ttu-id="dd5f0-172">При удалении файла с устройства отображается следующее уведомление:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-172">When the file is being removed from a device, the following notification is shown:</span></span>

![Изображение уведомления пользователя устройства](images/atp-notification-file.png)

<span data-ttu-id="dd5f0-174">В временной шкале устройства для каждого устройства, где файл был остановлен и карантин, добавляется новое событие.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-174">In the device timeline, a new event is added for each device where a file was stopped and quarantined.</span></span>

<span data-ttu-id="dd5f0-175">Перед реализацией действия для файлов, широко используемых в организации, отображается предупреждение.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-175">A warning is shown before the action is implemented for files widely used throughout an organization.</span></span> <span data-ttu-id="dd5f0-176">Это проверка того, что операция предназначена.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-176">It's to validate that the operation is intended.</span></span>

## <a name="restore-file-from-quarantine"></a><span data-ttu-id="dd5f0-177">Восстановление файла из карантина</span><span class="sxs-lookup"><span data-stu-id="dd5f0-177">Restore file from quarantine</span></span>

<span data-ttu-id="dd5f0-178">Вы можете откатить и удалить файл из карантина, если вы определили, что он чист после расследования.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-178">You can roll back and remove a file from quarantine if you’ve determined that it’s clean after an investigation.</span></span> <span data-ttu-id="dd5f0-179">Запустите следующую команду на каждом устройстве, где файл был карантин.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-179">Run the following command on each device where the file was quarantined.</span></span>

1. <span data-ttu-id="dd5f0-180">Откройте на устройстве повышенную командную строку:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-180">Open an elevated command–line prompt on the device:</span></span>

   1. <span data-ttu-id="dd5f0-181">В меню **Пуск** введите _cmd_.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-181">Go to **Start** and type _cmd_.</span></span>

   1. <span data-ttu-id="dd5f0-182">Щелкните правой **кнопкой мыши командную подсказку** и выберите **Выполнить в качестве администратора.**</span><span class="sxs-lookup"><span data-stu-id="dd5f0-182">Right–click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="dd5f0-183">Введите следующую команду и нажмите **кнопку Ввод:**</span><span class="sxs-lookup"><span data-stu-id="dd5f0-183">Enter the following command, and press **Enter**:</span></span>

   ```powershell
   “%ProgramFiles%\Windows Defender\MpCmdRun.exe” –Restore –Name EUS:Win32/CustomEnterpriseBlock –All
   ```

> [!NOTE]
> <span data-ttu-id="dd5f0-184">В некоторых сценариях **имя угрозы может** отображаться как: EUS:Win32/CustomEnterpriseBlock!cl.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-184">In some scenarios, the **ThreatName** may appear as: EUS:Win32/CustomEnterpriseBlock!cl.</span></span>
>
> <span data-ttu-id="dd5f0-185">Defender for Endpoint восстановит все настраиваемые заблокированные файлы, которые были на карантине на этом устройстве за последние 30 дней.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-185">Defender for Endpoint will restore all custom blocked files that were quarantined on this device in the last 30 days.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd5f0-186">Файл, который был на карантине в качестве потенциальной сетевой угрозы, может не быть восстановлен.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-186">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="dd5f0-187">Если пользователь пытается восстановить файл после карантина, этот файл может быть недоступным.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-187">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="dd5f0-188">Это может быть связано с тем, что система больше не имеет сетевых учетных данных для доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-188">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="dd5f0-189">Как правило, это результат временного входа в систему или общую папку, а срок действия маркеров доступа истек.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-189">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="download-or-collect-file"></a><span data-ttu-id="dd5f0-190">Скачивание или сбор файла</span><span class="sxs-lookup"><span data-stu-id="dd5f0-190">Download or collect file</span></span>

<span data-ttu-id="dd5f0-191">Выбор файла **Загрузка** из ответных действий позволяет скачать локальный архив, защищенный паролем, .zip файл.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-191">Selecting **Download file** from the response actions allows you to download a local, password-protected .zip archive containing your file.</span></span> <span data-ttu-id="dd5f0-192">Появится вылет, в котором можно записать причину загрузки файла и установить пароль.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-192">A flyout will appear where you can record a reason for downloading the file, and set a password.</span></span>

<span data-ttu-id="dd5f0-193">По умолчанию вы не сможете скачивать файлы, которые находятся в карантине.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-193">By default, you will not be able to download files that are in quarantine.</span></span>

![Изображение действия файла загрузки](images/atp-download-file-action.png)

### <a name="collect-files"></a><span data-ttu-id="dd5f0-195">Сбор файлов</span><span class="sxs-lookup"><span data-stu-id="dd5f0-195">Collect files</span></span>

<span data-ttu-id="dd5f0-196">Если файл еще не хранится в Microsoft Defender для конечной точки, его нельзя скачать.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-196">If a file is not already stored by Microsoft Defender for Endpoint, you can't download it.</span></span> <span data-ttu-id="dd5f0-197">Вместо этого вы увидите кнопку **Сбор файлов** в том же расположении.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-197">Instead, you'll see a **Collect file** button in the same location.</span></span> <span data-ttu-id="dd5f0-198">Если файл не был замечен в организации за последние 30 дней, **файл Collect** будет отключен.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-198">If a file hasn't been seen in the organization in the past 30 days, **Collect file** will be disabled.</span></span>
> [!Important]
> <span data-ttu-id="dd5f0-199">Файл, который был на карантине в качестве потенциальной сетевой угрозы, может не быть восстановлен.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-199">A file that was quarantined as a potential network threat might not be recoverable.</span></span> <span data-ttu-id="dd5f0-200">Если пользователь пытается восстановить файл после карантина, этот файл может быть недоступным.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-200">If a user attempts to restore the file after quarantine, that file might not be accessible.</span></span> <span data-ttu-id="dd5f0-201">Это может быть связано с тем, что система больше не имеет сетевых учетных данных для доступа к файлу.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-201">This can be due to the system no longer having network credentials to access the file.</span></span> <span data-ttu-id="dd5f0-202">Как правило, это результат временного входа в систему или общую папку, а срок действия маркеров доступа истек.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-202">Typically, this is a result of a temporary log on to a system or shared folder and the access tokens expired.</span></span>

## <a name="add-indicator-to-block-or-allow-a-file"></a><span data-ttu-id="dd5f0-203">Добавление индикатора для блокировки или допуска файла</span><span class="sxs-lookup"><span data-stu-id="dd5f0-203">Add indicator to block or allow a file</span></span>

<span data-ttu-id="dd5f0-204">Предотвращение дальнейшего распространения атаки в организации, запретив потенциально вредоносные файлы или подозрительные вредоносные программы.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-204">Prevent further propagation of an attack in your organization by banning potentially malicious files or suspected malware.</span></span> <span data-ttu-id="dd5f0-205">Если вы знаете потенциально вредоносный переносной файл(PE), его можно заблокировать.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-205">If you know a potentially malicious portable executable (PE) file, you can block it.</span></span> <span data-ttu-id="dd5f0-206">Эта операция предотвратит чтение, написание или выполнение на устройствах в организации.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-206">This operation will prevent it from being read, written, or executed on devices in your organization.</span></span>

> [!IMPORTANT]
>
> - <span data-ttu-id="dd5f0-207">Эта функция доступна, если в организации используется антивирусная программа в Microsoft Defender и включена защита от облачной доставки.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-207">This feature is available if your organization uses Microsoft Defender Antivirus and Cloud–delivered protection is enabled.</span></span> <span data-ttu-id="dd5f0-208">Дополнительные сведения см. в [сведениях Manage cloud-delivered protection.](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="dd5f0-208">For more information, see [Manage cloud–delivered protection](/windows/security/threat-protection/microsoft-defender-antivirus/deploy-manage-report-microsoft-defender-antivirus).</span></span>
>
> - <span data-ttu-id="dd5f0-209">Клиентская версия antimalware должна быть 4.18.1901.x или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-209">The Antimalware client version must be 4.18.1901.x or later.</span></span>
> - <span data-ttu-id="dd5f0-210">Эта функция предназначена для предотвращения скачивания из Интернета подозрительных вредоносных программ (или потенциально вредоносных файлов).</span><span class="sxs-lookup"><span data-stu-id="dd5f0-210">This feature is designed to prevent suspected malware (or potentially malicious files) from being downloaded from the web.</span></span> <span data-ttu-id="dd5f0-211">В настоящее время он поддерживает переносные исполняемые (PE) файлы, включая _.exe_ _и.dllфайлы._</span><span class="sxs-lookup"><span data-stu-id="dd5f0-211">It currently supports portable executable (PE) files, including _.exe_ and _.dll_ files.</span></span> <span data-ttu-id="dd5f0-212">Со временем охват будет расширен.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-212">The coverage will be extended over time.</span></span>
> - <span data-ttu-id="dd5f0-213">Это действие отклика доступно для устройств на Windows 10 версии 1703 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-213">This response action is available for devices on Windows 10, version 1703 or later.</span></span>
> - <span data-ttu-id="dd5f0-214">Функция разрешить или заблокировать не может быть сделана в файлах, если классификация файла существует в кэше устройства до действия разрешить или заблокировать.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-214">The allow or block function cannot be done on files if the file's classification exists on the device's cache prior to the allow or block action.</span></span>

> [!NOTE]
> <span data-ttu-id="dd5f0-215">Файл PE должен быть в временной шкале устройства, чтобы вы могли принять это действие.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-215">The PE file needs to be in the device timeline for you to be able to take this action.</span></span>
>
> <span data-ttu-id="dd5f0-216">Между временем действия и фактическим заблокированным файлом может потребоваться несколько минут задержки.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-216">There may be a couple of minutes of latency between the time the action is taken and the actual file being blocked.</span></span>

### <a name="enable-the-block-file-feature"></a><span data-ttu-id="dd5f0-217">Включить функцию файла блока</span><span class="sxs-lookup"><span data-stu-id="dd5f0-217">Enable the block file feature</span></span>

<span data-ttu-id="dd5f0-218">Чтобы начать блокировать файлы, [  ](advanced-features.md) сначала необходимо включить блок или включить функцию Параметры.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-218">To start blocking files, you first need to [turn the **Block or allow** feature on](advanced-features.md) in Settings.</span></span>
### <a name="allow-or-block-file"></a><span data-ttu-id="dd5f0-219">Разрешить или заблокировать файл</span><span class="sxs-lookup"><span data-stu-id="dd5f0-219">Allow or block file</span></span>

<span data-ttu-id="dd5f0-220">При добавлении hash индикатора для файла можно поднять оповещение и заблокировать файл всякий раз, когда устройство в организации пытается запустить его.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-220">When you add an indicator hash for a file, you can choose to raise an alert and block the file whenever a device in your organization attempts to run it.</span></span>

<span data-ttu-id="dd5f0-221">Файлы, автоматически заблокированные индикатором, не будут показываться в центре действий файла, но оповещения по-прежнему будут видны в очереди Оповещения.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-221">Files automatically blocked by an indicator won't show up in the file's Action center, but the alerts will still be visible in the Alerts queue.</span></span>

<span data-ttu-id="dd5f0-222">Дополнительные [сведения о блокировке](manage-indicators.md) и поднятии оповещений по файлам см. в материале "Управление индикаторами".</span><span class="sxs-lookup"><span data-stu-id="dd5f0-222">See [manage indicators](manage-indicators.md) for more details on blocking and raising alerts on files.</span></span>

<span data-ttu-id="dd5f0-223">Чтобы остановить блокировку файла, удалите индикатор.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-223">To stop blocking a file, remove the indicator.</span></span> <span data-ttu-id="dd5f0-224">Это можно сделать с помощью действия **Edit Indicator** на странице профиля файла.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-224">You can do so via the **Edit Indicator** action on the file's profile page.</span></span> <span data-ttu-id="dd5f0-225">Это действие будет видно в том же положении, что и действие **Add Indicator** перед добавлением индикатора.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-225">This action will be visible in the same position as the **Add Indicator** action, before you added the indicator.</span></span>

<span data-ttu-id="dd5f0-226">Вы также можете изменить индикаторы со **страницы Параметры,** в статье **Индикаторы**  >  **правил**.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-226">You can also edit indicators from  the **Settings** page, under **Rules** > **Indicators**.</span></span> <span data-ttu-id="dd5f0-227">Индикаторы перечислены в этой области по hash их файла.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-227">Indicators are listed in this area by their file's hash.</span></span>

## <a name="consult-a-threat-expert"></a><span data-ttu-id="dd5f0-228">Обратитесь к эксперту по угрозам</span><span class="sxs-lookup"><span data-stu-id="dd5f0-228">Consult a threat expert</span></span>

<span data-ttu-id="dd5f0-229">Дополнительные сведения о потенциально скомпрометированном устройстве или уже скомпрометированном устройстве обратитесь к эксперту по угрозам Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-229">Consult a Microsoft threat expert for more insights on a potentially compromised device, or already compromised devices.</span></span> <span data-ttu-id="dd5f0-230">эксперты Майкрософт по угрозам непосредственно изнутри Центр безопасности в Microsoft Defender для быстрого и точного ответа.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-230">Microsoft Threat Experts are engaged directly from within the Microsoft Defender Security Center for timely and accurate response.</span></span> <span data-ttu-id="dd5f0-231">Эксперты предоставляют сведения о потенциально скомпрометированном устройстве и помогают разобраться в сложных угрозах и целевых уведомлениях об атаке.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-231">Experts provide insights on a potentially compromised device and help you understand complex threats and targeted attack notifications.</span></span> <span data-ttu-id="dd5f0-232">Они также могут предоставлять сведения о оповещениях или контексте разведки угроз, которые вы видите на панели мониторинга портала.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-232">They can also provide information about the alerts or a threat intelligence context that you see on your portal dashboard.</span></span>

<span data-ttu-id="dd5f0-233">Подробные [сведения см. в материале Consult a Microsoft Threat Expert.](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization)</span><span class="sxs-lookup"><span data-stu-id="dd5f0-233">See [Consult a Microsoft Threat Expert](/microsoft-365/security/defender-endpoint/configure-microsoft-threat-experts#consult-a-microsoft-threat-expert-about-suspicious-cybersecurity-activities-in-your-organization) for details.</span></span>

## <a name="check-activity-details-in-action-center"></a><span data-ttu-id="dd5f0-234">Проверка сведений о действиях в центре действий</span><span class="sxs-lookup"><span data-stu-id="dd5f0-234">Check activity details in Action center</span></span>

<span data-ttu-id="dd5f0-235">Центр **действий** предоставляет сведения о действиях, принятых на устройстве или файле.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-235">The **Action center** provides information on actions that were taken on a device or file.</span></span> <span data-ttu-id="dd5f0-236">Вы можете просмотреть следующие сведения:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-236">You can view the following details:</span></span>

- <span data-ttu-id="dd5f0-237">Коллекция пакетов исследований</span><span class="sxs-lookup"><span data-stu-id="dd5f0-237">Investigation package collection</span></span>
- <span data-ttu-id="dd5f0-238">Антивирусное сканирование</span><span class="sxs-lookup"><span data-stu-id="dd5f0-238">Antivirus scan</span></span>
- <span data-ttu-id="dd5f0-239">Ограничение приложения</span><span class="sxs-lookup"><span data-stu-id="dd5f0-239">App restriction</span></span>
- <span data-ttu-id="dd5f0-240">Изоляция устройств</span><span class="sxs-lookup"><span data-stu-id="dd5f0-240">Device isolation</span></span>

<span data-ttu-id="dd5f0-241">Также показаны все другие связанные сведения, такие как дата отправки/время, отправка пользователя, а также успешное действие или сбой.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-241">All other related details are also shown, such as submission date/time, submitting user, and if the action succeeded or failed.</span></span>

![Изображение центра действий с информацией](images/action-center-details.png)

## <a name="deep-analysis"></a><span data-ttu-id="dd5f0-243">Подробный анализ</span><span class="sxs-lookup"><span data-stu-id="dd5f0-243">Deep analysis</span></span>

<span data-ttu-id="dd5f0-244">Расследования кибербезопасности обычно вызываются оповещением.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-244">Cyber security investigations are typically triggered by an alert.</span></span> <span data-ttu-id="dd5f0-245">Оповещения связаны с одним или более наблюдаемым файлом, которые часто являются новыми или неизвестными.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-245">Alerts are related to one or more observed files that are often new or unknown.</span></span> <span data-ttu-id="dd5f0-246">При выборе файла вы сможете просмотреть метаданные файла.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-246">Selecting a file takes you to the file view where you can see the file's metadata.</span></span> <span data-ttu-id="dd5f0-247">Чтобы обогатить данные, связанные с файлом, вы можете отправить файл для глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-247">To enrich the data related to the file, you can submit the file for deep analysis.</span></span>

<span data-ttu-id="dd5f0-248">Функция Глубокого анализа выполняет файл в безопасной, полностью оборудованной облачной среде.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-248">The Deep analysis feature executes a file in a secure, fully instrumented cloud environment.</span></span> <span data-ttu-id="dd5f0-249">Результаты глубокого анализа показывают действия файла, наблюдаемое поведение и связанные артефакты, такие как отброшенные файлы, изменения реестра и связь с ИП.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-249">Deep analysis results show the file's activities, observed behaviors, and associated artifacts, such as dropped files, registry modifications, and communication with IPs.</span></span>
<span data-ttu-id="dd5f0-250">Глубокий анализ в настоящее время поддерживает обширный анализ переносных исполняемых (PE) файлов _(в_ том числе.exe _и.dllфайлов)._</span><span class="sxs-lookup"><span data-stu-id="dd5f0-250">Deep analysis currently supports extensive analysis of portable executable (PE) files (including _.exe_ and _.dll_ files).</span></span>

<span data-ttu-id="dd5f0-251">Глубокий анализ файла занимает несколько минут.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-251">Deep analysis of a file takes several minutes.</span></span> <span data-ttu-id="dd5f0-252">После завершения анализа файлов вкладка Deep Analysis будет обновляться, чтобы отобразить сводку и дату и время последних доступных результатов.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-252">Once the file analysis is complete, the Deep Analysis tab will update to display a summary and the date and time of the latest available results.</span></span>

<span data-ttu-id="dd5f0-253">В сводке глубокого анализа содержится список наблюдаемых действий, некоторые из которых могут указывать на вредоносную активность, а также наблюдаемые, включая контактируемые IPs и файлы, созданные на диске. </span><span class="sxs-lookup"><span data-stu-id="dd5f0-253">The deep analysis summary includes a list of observed *behaviors*, some of which can indicate malicious activity, and *observables*, including contacted IPs and files created on the disk.</span></span> <span data-ttu-id="dd5f0-254">Если ничего не найдено, в этих разделах будет отображаться краткое сообщение.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-254">If nothing was found, these sections will display a brief message.</span></span>

<span data-ttu-id="dd5f0-255">Результаты глубокого анализа соответствуют сведениям об угрозах, и любые совпадения будут создавать соответствующие оповещения.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-255">Results of deep analysis are matched against threat intelligence and any matches will generate appropriate alerts.</span></span>

<span data-ttu-id="dd5f0-256">Используйте функцию глубокого анализа для изучения сведений о любом файле, как правило, во время расследования оповещения или по любой другой причине, по которой вы подозреваете вредоносное поведение.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-256">Use the deep analysis feature to investigate the details of any file, usually during an investigation of an alert or for any other reason where you suspect malicious behavior.</span></span> <span data-ttu-id="dd5f0-257">Эта функция доступна в **вкладке Глубокий** анализ на странице профиля файла.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-257">This feature is available within the **Deep analysis** tab, on the file's profile page.</span></span><br/>
<br/>

> [!VIDEO https://www.microsoft.com/en-us/videoplayer/embed/RE4aAYy?rel=0]

<span data-ttu-id="dd5f0-258">**Отправка** для глубокого анализа включена, когда файл доступен в коллекции backend Defender для конечной точки, или если он был замечен на устройстве Windows 10, которое поддерживает отправку на глубокий анализ.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-258">**Submit for deep analysis** is enabled when the file is available in the Defender for Endpoint backend sample collection, or if it was observed on a Windows 10 device that supports submitting to deep analysis.</span></span>

> [!NOTE]
> <span data-ttu-id="dd5f0-259">Автоматически можно Windows 10 файлы из других стран.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-259">Only files from Windows 10 can be automatically collected.</span></span>

<span data-ttu-id="dd5f0-260">Вы также можете отправить [](https://www.microsoft.com/security/portal/submission/submit.aspx) образец через портал Центра безопасности Майкрософт, если файл не был замечен на устройстве Windows 10, и подождать, пока кнопка **Отправка** глубокого анализа станет доступной.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-260">You can also submit a sample through the [Microsoft Security Center Portal](https://www.microsoft.com/security/portal/submission/submit.aspx) if the file wasn't observed on a Windows 10 device, and wait for **Submit for deep analysis** button to become available.</span></span>

> [!NOTE]
> <span data-ttu-id="dd5f0-261">Из-за потоков обработки backend на портале Центра безопасности Майкрософт может быть до 10 минут задержки между отправкой файлов и доступностью функции глубокого анализа в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-261">Due to backend processing flows in the Microsoft Security Center Portal, there could be up to 10 minutes of latency between file submission and availability of the deep analysis feature in Defender for Endpoint.</span></span>

<span data-ttu-id="dd5f0-262">Когда образец собран, Defender for Endpoint запускает файл в безопасной среде.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-262">When the sample is collected, Defender for Endpoint runs the file in a secure environment.</span></span> <span data-ttu-id="dd5f0-263">Затем создается подробный отчет о наблюдаемых поведениях и связанных с ними артефактах, таких как файлы, сброшенные на устройства, связь с ИП и изменения реестра.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-263">It then creates a detailed report of observed behaviors and associated artifacts, such as files dropped on devices, communication to IPs, and registry modifications.</span></span>

### <a name="submit-files-for-deep-analysis"></a><span data-ttu-id="dd5f0-264">Отправка файлов для глубокого анализа</span><span class="sxs-lookup"><span data-stu-id="dd5f0-264">Submit files for deep analysis</span></span>

1. <span data-ttu-id="dd5f0-265">Выберите файл, который необходимо отправить для глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-265">Select the file that you want to submit for deep analysis.</span></span> <span data-ttu-id="dd5f0-266">Вы можете выбрать или поискать файл из любого из следующих представлений:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-266">You can select or search a file from any of the following views:</span></span>

    - <span data-ttu-id="dd5f0-267">Оповещений — выберите ссылки на файл из **Описания** или **Сведения** в временной шкале Артефакт</span><span class="sxs-lookup"><span data-stu-id="dd5f0-267">Alerts - select the file links from the **Description** or **Details** in the Artifact timeline</span></span>
    - <span data-ttu-id="dd5f0-268">**Список устройств** — выберите ссылки на файл из **раздела Описание** **или** Сведения в разделе Устройство **в организации**</span><span class="sxs-lookup"><span data-stu-id="dd5f0-268">**Devices list** - select the file links from the **Description** or **Details** in the **Device in organization** section</span></span>
    - <span data-ttu-id="dd5f0-269">Поле поиска — выберите **Файл** из выпадаемого меню и введите имя файла</span><span class="sxs-lookup"><span data-stu-id="dd5f0-269">Search box - select **File** from the drop–down menu and enter the file name</span></span>

2. <span data-ttu-id="dd5f0-270">В **вкладке Глубокий анализ** представления файла выберите **Отправить**.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-270">In the **Deep analysis** tab of the file view, select **Submit**.</span></span>

   ![Отправлять pe-файлы можно только в разделе сведения о файлах.](images/submit-file.png)

   > [!NOTE]
   > <span data-ttu-id="dd5f0-272">Поддерживаются только файлы PE, в том числе _.exe_ _и.dll_ файлы.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-272">Only PE files are supported, including _.exe_ and _.dll_ files.</span></span>

<span data-ttu-id="dd5f0-273">Отображается планка прогресса и предоставляет сведения о различных этапах анализа.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-273">A progress bar is displayed and provides information on the different stages of the analysis.</span></span> <span data-ttu-id="dd5f0-274">Затем можно просмотреть отчет, когда будет проведен анализ.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-274">You can then view the report when the analysis is done.</span></span>

> [!NOTE]
> <span data-ttu-id="dd5f0-275">В зависимости от доступности устройства время сбора образцов может отличаться.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-275">Depending on device availability, sample collection time can vary.</span></span> <span data-ttu-id="dd5f0-276">Существует 3-часовой период времени для коллекции образцов.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-276">There is a 3–hour timeout for sample collection.</span></span> <span data-ttu-id="dd5f0-277">Коллекция не работает, и операция прервается, если в Windows 10 нет отчетов об устройстве.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-277">The collection will fail and the operation will abort if there is no online Windows 10 device reporting at that time.</span></span> <span data-ttu-id="dd5f0-278">Вы можете повторно отправить файлы для глубокого анализа, чтобы получить свежие данные в файле.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-278">You can re–submit files for deep analysis to get fresh data on the file.</span></span>

### <a name="view-deep-analysis-reports"></a><span data-ttu-id="dd5f0-279">Просмотр отчетов о глубоком анализе</span><span class="sxs-lookup"><span data-stu-id="dd5f0-279">View deep analysis reports</span></span>

<span data-ttu-id="dd5f0-280">Просмотр предоставленного отчета глубокого анализа, чтобы просмотреть более глубокие сведения о файле, который вы отправили.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-280">View the provided deep analysis report to see more in-depth insights on the file you submitted.</span></span> <span data-ttu-id="dd5f0-281">Эта функция доступна в контексте представления файлов.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-281">This feature is available in the file view context.</span></span>

<span data-ttu-id="dd5f0-282">Вы можете просмотреть полный отчет, в который приводится подробная информация по следующим разделам:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-282">You can view the comprehensive report that provides details on the following sections:</span></span>

- <span data-ttu-id="dd5f0-283">Behaviors</span><span class="sxs-lookup"><span data-stu-id="dd5f0-283">Behaviors</span></span>
- <span data-ttu-id="dd5f0-284">Observables</span><span class="sxs-lookup"><span data-stu-id="dd5f0-284">Observables</span></span>

<span data-ttu-id="dd5f0-285">Предоставленные сведения помогут вам разобраться, есть ли признаки потенциальной атаки.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-285">The details provided can help you investigate if there are indications of a potential attack.</span></span>

1. <span data-ttu-id="dd5f0-286">Выберите файл, который вы отправили для глубокого анализа.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-286">Select the file you submitted for deep analysis.</span></span>
2. <span data-ttu-id="dd5f0-287">Выберите **вкладку Глубокий** анализ. Если есть какие-либо предыдущие отчеты, на этой вкладке появится сводка отчета.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-287">Select the **Deep analysis** tab. If there are any previous reports, the report summary will appear in this tab.</span></span>

    ![В отчете глубокого анализа показаны подробные сведения по ряду категорий](images/analysis-results-nothing500.png)

#### <a name="troubleshoot-deep-analysis"></a><span data-ttu-id="dd5f0-289">Устранение неполадок при глубоком анализе</span><span class="sxs-lookup"><span data-stu-id="dd5f0-289">Troubleshoot deep analysis</span></span>

<span data-ttu-id="dd5f0-290">Если при попытке отправки файла возникла проблема, попробуйте каждый из следующих действий по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-290">If you come across a problem when trying to submit a file, try each of the following troubleshooting steps.</span></span>

1. <span data-ttu-id="dd5f0-291">Убедитесь, что этот файл является файлом PE.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-291">Ensure that the file in question is a PE file.</span></span> <span data-ttu-id="dd5f0-292">Файлы PE обычно имеют _.exe_ _или.dll_ расширения (исполняемые программы или приложения).</span><span class="sxs-lookup"><span data-stu-id="dd5f0-292">PE files typically have _.exe_ or _.dll_ extensions (executable programs or applications).</span></span>
2. <span data-ttu-id="dd5f0-293">Убедитесь, что служба имеет доступ к файлу, который все еще существует и не был поврежден или изменен.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-293">Ensure the service has access to the file, that it still exists, and hasn't been corrupted or modified.</span></span>
3. <span data-ttu-id="dd5f0-294">Подождите некоторое время и попробуйте отправить файл еще раз.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-294">Wait a short while and try to submit the file again.</span></span> <span data-ttu-id="dd5f0-295">Очередь может быть заполнена, или была временная ошибка подключения или связи.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-295">The queue may be full, or there was a temporary connection or communication error.</span></span>
4. <span data-ttu-id="dd5f0-296">Если политика сбора образцов не настроена, по умолчанию необходимо разрешить коллекцию образцов.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-296">If the sample collection policy isn't configured, then the default behavior is to allow sample collection.</span></span> <span data-ttu-id="dd5f0-297">Если он настроен, убедитесь, что параметр политики позволяет пример коллекции перед отправкой файла снова.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-297">If it's configured, then verify the policy setting allows sample collection before submitting the file again.</span></span> <span data-ttu-id="dd5f0-298">При настройке коллекции образцов проверьте следующее значение реестра:</span><span class="sxs-lookup"><span data-stu-id="dd5f0-298">When sample collection is configured, then check the following registry value:</span></span>

    ```powershell
    Path: HKLM\SOFTWARE\Policies\Microsoft\Windows Advanced Threat Protection
    Name: AllowSampleCollection
    Type: DWORD
    Hexadecimal value :
      Value = 0 – block sample collection
      Value = 1 – allow sample collection
    ```

1. <span data-ttu-id="dd5f0-299">Изменение организационного подразделения с помощью групповой политики.</span><span class="sxs-lookup"><span data-stu-id="dd5f0-299">Change the organizational unit through the Group Policy.</span></span> <span data-ttu-id="dd5f0-300">Дополнительные сведения см. в [перенастройке с групповой политикой.](configure-endpoints-gp.md)</span><span class="sxs-lookup"><span data-stu-id="dd5f0-300">For more information, see [Configure with Group Policy](configure-endpoints-gp.md).</span></span>
1. <span data-ttu-id="dd5f0-301">Если эти действия не устраняют проблему, свяжитесь [с](mailto:winatp@microsoft.com)winatp@microsoft.com .</span><span class="sxs-lookup"><span data-stu-id="dd5f0-301">If these steps do not resolve the issue, contact [winatp@microsoft.com](mailto:winatp@microsoft.com).</span></span>

## <a name="related-topics"></a><span data-ttu-id="dd5f0-302">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="dd5f0-302">Related topics</span></span>

- [<span data-ttu-id="dd5f0-303">Выполнение действий ответов на устройстве</span><span class="sxs-lookup"><span data-stu-id="dd5f0-303">Take response actions on a device</span></span>](respond-machine-alerts.md)
- [<span data-ttu-id="dd5f0-304">Исследование файлов</span><span class="sxs-lookup"><span data-stu-id="dd5f0-304">Investigate files</span></span>](investigate-files.md)
