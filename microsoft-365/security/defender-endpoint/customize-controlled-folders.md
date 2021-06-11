---
title: Настройка контролируемого доступа к папкам
description: Добавьте другие папки, которые должны быть защищены управляемым доступом к папкам, или разрешить приложениям, которые неправильно блокируют изменения важных файлов.
keywords: Управляемый доступ к папкам, Windows 10, защитник Windows, вымогатели, защита, файлы, папки, настройка, добавление папки, добавление приложения, разрешение, добавление исполняемого
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
audience: ITPro
author: denisebmsft
ms.author: deniseb
ms.reviewer: jcedola, dbodorin, vladiso, nixanm, anvascon
manager: dansimp
ms.date: 05/10/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: e12368b6241a2c79eead66ed77b30b7864af3955
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52326532"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="1b02f-104">Настройка контролируемого доступа к папкам</span><span class="sxs-lookup"><span data-stu-id="1b02f-104">Customize controlled folder access</span></span>

<span data-ttu-id="1b02f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="1b02f-105">**Applies to:**</span></span>
- [<span data-ttu-id="1b02f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="1b02f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="1b02f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1b02f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!TIP]
> <span data-ttu-id="1b02f-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="1b02f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="1b02f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="1b02f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="1b02f-110">Управляемый доступ к папкам помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей.</span><span class="sxs-lookup"><span data-stu-id="1b02f-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="1b02f-111">Управляемый доступ к папкам поддерживается на Windows Server 2019 и Windows 10 клиентах.</span><span class="sxs-lookup"><span data-stu-id="1b02f-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span> <span data-ttu-id="1b02f-112">В этой статье описывается настройка возможностей доступа к управляемым папкам и содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="1b02f-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="1b02f-113">Защита дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="1b02f-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="1b02f-114">Добавление приложений, которые должны быть разрешены для доступа к защищенным папок</span><span class="sxs-lookup"><span data-stu-id="1b02f-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="1b02f-115">Разрешить подписанным исполняемым файлам доступ к защищенным папкам</span><span class="sxs-lookup"><span data-stu-id="1b02f-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="1b02f-116">Настройка уведомления</span><span class="sxs-lookup"><span data-stu-id="1b02f-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="1b02f-117">Контролируемый доступ к папкам отслеживает приложения для действий, которые обнаруживаются как вредоносные.</span><span class="sxs-lookup"><span data-stu-id="1b02f-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="1b02f-118">Иногда законным приложениям блокируется внесение изменений в файлы.</span><span class="sxs-lookup"><span data-stu-id="1b02f-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="1b02f-119">Если управляемый доступ к папкам влияет на производительность организации, можно рассмотреть возможность запуска этой функции в режиме аудита, чтобы полностью оценить последствия. [](audit-windows-defender.md)</span><span class="sxs-lookup"><span data-stu-id="1b02f-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="1b02f-120">Защита дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="1b02f-120">Protect additional folders</span></span>

<span data-ttu-id="1b02f-121">Управляемый доступ к папкам применяется ко многим папкам системы и расположениям по умолчанию, включая такие папки, как **Documents,** **Pictures** и **Movies.**</span><span class="sxs-lookup"><span data-stu-id="1b02f-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="1b02f-122">Можно добавить другие папки, которые необходимо защитить, но нельзя удалить папки по умолчанию в списке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1b02f-122">You can add other folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="1b02f-123">Добавление других папок к управляемому доступу к папкам может быть полезно в тех случаях, когда файлы не хранятся в библиотеках Windows по умолчанию, или вы изменили расположение библиотек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="1b02f-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="1b02f-124">Вы также можете указать сетевые акции и составить карту дисков.</span><span class="sxs-lookup"><span data-stu-id="1b02f-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="1b02f-125">Поддерживаются переменные среды и подкарды.</span><span class="sxs-lookup"><span data-stu-id="1b02f-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="1b02f-126">Сведения об использовании подмастерьев см. в материалах [Use wildcards in the file name and folder path or extension exclusion lists.](configure-extension-file-exclusions-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="1b02f-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](configure-extension-file-exclusions-microsoft-defender-antivirus.md).</span></span>

<span data-ttu-id="1b02f-127">Для добавления и удаления защищенных папок можно использовать приложение Безопасность Windows, групповые политики, команды PowerShell или поставщики служб конфигурации управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="1b02f-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="1b02f-128">Используйте приложение Безопасность Windows для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="1b02f-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="1b02f-129">Откройте приложение Безопасность Windows, выбрав значок щита в панели задач или нажав на безопасность *в* меню Пуск.</span><span class="sxs-lookup"><span data-stu-id="1b02f-129">Open the Windows Security app by selecting the shield icon in the task bar, or by searching for *security* in the Start menu.</span></span>

2. <span data-ttu-id="1b02f-130">Выберите **защиту & вирусов,** а затем прокрутите его в раздел **Защита вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="1b02f-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="1b02f-131">Выберите **Управление защитой вымогателей,** чтобы открыть области защиты вымогателей. </span><span class="sxs-lookup"><span data-stu-id="1b02f-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="1b02f-132">В разделе **Управляемый доступ к папкам** выберите **защищенные папки.**</span><span class="sxs-lookup"><span data-stu-id="1b02f-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="1b02f-133">Выберите **Да** в **запросе Управления доступом пользователей.**</span><span class="sxs-lookup"><span data-stu-id="1b02f-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="1b02f-134">Экраны **области защищенных** папок.</span><span class="sxs-lookup"><span data-stu-id="1b02f-134">The **Protected folders** pane displays.</span></span>

6. <span data-ttu-id="1b02f-135">Выберите **Добавить защищенную папку** и следуйте подсказкам для добавления папок.</span><span class="sxs-lookup"><span data-stu-id="1b02f-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="1b02f-136">Использование групповой политики для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="1b02f-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="1b02f-137">На компьютере управления групповыми политиками откройте [консоль управления групповыми политиками](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span><span class="sxs-lookup"><span data-stu-id="1b02f-137">On your Group Policy management computer, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true).</span></span> 

2. <span data-ttu-id="1b02f-138">Щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1b02f-138">Right-click the Group Policy Object you want to configure, and then select **Edit**.</span></span>

3. <span data-ttu-id="1b02f-139">В **редакторе управления групповой политикой** перейдите к шаблонам **администрирования** политики конфигурации  >    >  **компьютеров.**</span><span class="sxs-lookup"><span data-stu-id="1b02f-139">In your **Group Policy Management Editor**, go to **Computer configuration** > **Policies** > **Administrative templates**.</span></span>

4. <span data-ttu-id="1b02f-140">Расширь **дерево, Windows компоненты антивирусная программа в Microsoft Defender** Защитник Windows доступ к управляемой папке  >    >  **Exploit Guard.**  >  </span><span class="sxs-lookup"><span data-stu-id="1b02f-140">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span> <br/><span data-ttu-id="1b02f-141">**ПРИМЕЧАНИЕ.** В более старых версиях Windows вы можете антивирусная программа **вместо** антивирусная программа в Microsoft Defender **.**</span><span class="sxs-lookup"><span data-stu-id="1b02f-141">**NOTE**: On older versions of Windows, you might see **Windows Defender Antivirus** instead of **Microsoft Defender Antivirus**.</span></span>

5. <span data-ttu-id="1b02f-142">Дважды **щелкните Настроенные защищенные папки,** а затем установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="1b02f-142">Double-click **Configured protected folders**, and then set the option to **Enabled**.</span></span> <span data-ttu-id="1b02f-143">Выберите **Показать** и укажите каждую папку, которую необходимо защитить.</span><span class="sxs-lookup"><span data-stu-id="1b02f-143">Select **Show**, and specify each folder that you want to protect.</span></span>

6. <span data-ttu-id="1b02f-144">Развертывание объекта групповой политики, как обычно.</span><span class="sxs-lookup"><span data-stu-id="1b02f-144">Deploy your Group Policy Object as you usually do.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="1b02f-145">Использование PowerShell для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="1b02f-145">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="1b02f-146">Введите **PowerShell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="1b02f-146">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="1b02f-147">Введите следующий комдлет PowerShell, заменив путь папки `<the folder to be protected>` `"c:\apps\"` (например: :</span><span class="sxs-lookup"><span data-stu-id="1b02f-147">Type the following PowerShell cmdlet, replacing `<the folder to be protected>` with the folder's path (such as `"c:\apps\"`):</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="1b02f-148">Повторите шаг 2 для каждой папки, которую необходимо защитить.</span><span class="sxs-lookup"><span data-stu-id="1b02f-148">Repeat step 2 for each folder that you want to protect.</span></span> <span data-ttu-id="1b02f-149">Защищенные папки видны в приложении Безопасность Windows.</span><span class="sxs-lookup"><span data-stu-id="1b02f-149">Folders that are protected are visible in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-folder-ps.png" alt-text="Окно PowerShell с показанным комлетом":::

> [!IMPORTANT]
> <span data-ttu-id="1b02f-151">Используйте `Add-MpPreference` для добавления или добавления приложений в список, а не `Set-MpPreference` .</span><span class="sxs-lookup"><span data-stu-id="1b02f-151">Use `Add-MpPreference` to append or add apps to the list and not `Set-MpPreference`.</span></span> <span data-ttu-id="1b02f-152">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="1b02f-152">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="1b02f-153">Использование CSPs MDM для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="1b02f-153">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="1b02f-154">Используйте [поставщик служб конфигурации ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.</span><span class="sxs-lookup"><span data-stu-id="1b02f-154">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="1b02f-155">Разрешить определенным приложениям вносить изменения в управляемые папки</span><span class="sxs-lookup"><span data-stu-id="1b02f-155">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="1b02f-156">Можно указать, считаются ли некоторые приложения безопасными, и предоставить доступ к файлам в защищенных папках.</span><span class="sxs-lookup"><span data-stu-id="1b02f-156">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="1b02f-157">Разрешение приложений может быть полезным, если определенное приложение, которое вы знаете и доверяете, блокируется функцией доступа к управляемой папке.</span><span class="sxs-lookup"><span data-stu-id="1b02f-157">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="1b02f-158">По умолчанию Windows приложения, которые считаются удобными для разрешенного списка.</span><span class="sxs-lookup"><span data-stu-id="1b02f-158">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="1b02f-159">Такие приложения, которые добавляются автоматически, не записываются в список, показанный в приложении Безопасность Windows или с помощью связанных с ней cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="1b02f-159">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="1b02f-160">Не нужно добавлять большинство приложений.</span><span class="sxs-lookup"><span data-stu-id="1b02f-160">You shouldn't need to add most apps.</span></span> <span data-ttu-id="1b02f-161">Добавляйте приложения только в том случае, если они заблокированы, и вы можете проверить их надежность.</span><span class="sxs-lookup"><span data-stu-id="1b02f-161">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="1b02f-162">При добавлении приложения необходимо указать расположение приложения.</span><span class="sxs-lookup"><span data-stu-id="1b02f-162">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="1b02f-163">Только приложению в этом расположении будет разрешен доступ к защищенным папкам.</span><span class="sxs-lookup"><span data-stu-id="1b02f-163">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="1b02f-164">Если приложение (с тем же именем) находится в другом расположении, оно не будет добавлено в список допуска и может быть заблокировано управляемым доступом к папке.</span><span class="sxs-lookup"><span data-stu-id="1b02f-164">If the app (with the same name) is in a different location, it will not be added to the allowlist and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="1b02f-165">Разрешенное приложение или служба имеет доступ к управляемой папке только после ее начала.</span><span class="sxs-lookup"><span data-stu-id="1b02f-165">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="1b02f-166">Например, служба обновления будет продолжать запускать события после ее разрешения, пока она не будет остановлена и перезапущена.</span><span class="sxs-lookup"><span data-stu-id="1b02f-166">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="1b02f-167">Используйте приложение Защитник Windows безопасности, чтобы разрешить определенные приложения</span><span class="sxs-lookup"><span data-stu-id="1b02f-167">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="1b02f-168">Откройте приложение Безопасность Windows, ища меню пуск для **безопасности**.</span><span class="sxs-lookup"><span data-stu-id="1b02f-168">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="1b02f-169">Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем выберите управление защитой **вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="1b02f-169">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="1b02f-170">В разделе **Управляемый доступ к папке** выберите Разрешить приложение с помощью управляемого доступа **к папке**</span><span class="sxs-lookup"><span data-stu-id="1b02f-170">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="1b02f-171">Выберите **Добавление разрешенного приложения** и следуйте подсказкам для добавления приложений.</span><span class="sxs-lookup"><span data-stu-id="1b02f-171">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Добавление разрешенной кнопки приложения":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="1b02f-173">Использование групповой политики для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="1b02f-173">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="1b02f-174">На устройстве управления групповой политикой откройте консоль управления групповой политикой [правой](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="1b02f-174">On your Group Policy management device, open the [Group Policy Management Console](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="1b02f-175">В **редакторе управления групповыми политиками** перейдите к **конфигурации компьютера** и выберите **Административные шаблоны**.</span><span class="sxs-lookup"><span data-stu-id="1b02f-175">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="1b02f-176">Расширь **дерево, Windows компоненты антивирусная программа в Microsoft Defender** Защитник Windows доступ к управляемой папке  >    >  **Exploit Guard.**  >  </span><span class="sxs-lookup"><span data-stu-id="1b02f-176">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="1b02f-177">Дважды щелкните **параметр Настройка разрешенных приложений** и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="1b02f-177">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="1b02f-178">Выберите **Показать** и ввести каждое приложение.</span><span class="sxs-lookup"><span data-stu-id="1b02f-178">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="1b02f-179">Использование PowerShell для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="1b02f-179">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="1b02f-180">Введите **PowerShell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="1b02f-180">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="1b02f-181">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="1b02f-181">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="1b02f-182">Например, чтобы добавить исполняемыйtest.exe, расположенный в папке *C:\apps,* этот комлет будет следующим образом: </span><span class="sxs-lookup"><span data-stu-id="1b02f-182">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="1b02f-183">Продолжайте использовать `Add-MpPreference -ControlledFolderAccessAllowedApplications` для добавления дополнительных приложений в список.</span><span class="sxs-lookup"><span data-stu-id="1b02f-183">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="1b02f-184">Приложения, добавленные с помощью этого комлета, будут отображаться в Безопасность Windows приложении.</span><span class="sxs-lookup"><span data-stu-id="1b02f-184">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet PowerShell, чтобы разрешить приложение":::

> [!IMPORTANT]
> <span data-ttu-id="1b02f-186">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="1b02f-186">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="1b02f-187">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="1b02f-187">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="1b02f-188">Использование CSPs MDM для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="1b02f-188">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="1b02f-189">Используйте [поставщик услуг конфигурации ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.</span><span class="sxs-lookup"><span data-stu-id="1b02f-189">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="1b02f-190">Разрешить подписанным исполняемым файлам доступ к защищенным папкам</span><span class="sxs-lookup"><span data-stu-id="1b02f-190">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="1b02f-191">Индикаторы сертификата и файлов Microsoft Defender для конечной точки могут разрешить подписанным исполняемым файлам доступ к защищенным папкам.</span><span class="sxs-lookup"><span data-stu-id="1b02f-191">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="1b02f-192">Дополнительные сведения о реализации см. [в материале Create indicators based on certificates.](indicator-certificates.md)</span><span class="sxs-lookup"><span data-stu-id="1b02f-192">For implementation details, see [Create indicators based on certificates](indicator-certificates.md).</span></span>

> [!Note]
> <span data-ttu-id="1b02f-193">Это не относится к сценариям, включая Powershell</span><span class="sxs-lookup"><span data-stu-id="1b02f-193">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="1b02f-194">Настройка уведомления</span><span class="sxs-lookup"><span data-stu-id="1b02f-194">Customize the notification</span></span>

<span data-ttu-id="1b02f-195">Дополнительные сведения о настройке уведомления при запуске правила и блокировке приложения или файла см. в статью Настройка уведомлений оповещения в [Microsoft Defender для конечной точки.](configure-email-notifications.md)</span><span class="sxs-lookup"><span data-stu-id="1b02f-195">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](configure-email-notifications.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="1b02f-196">См. также</span><span class="sxs-lookup"><span data-stu-id="1b02f-196">See also</span></span>

- [<span data-ttu-id="1b02f-197">Защита важных папок с управляемым доступом к папкам</span><span class="sxs-lookup"><span data-stu-id="1b02f-197">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="1b02f-198">Включить контролируемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="1b02f-198">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="1b02f-199">Оценка правил сокращения направлений атак</span><span class="sxs-lookup"><span data-stu-id="1b02f-199">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
