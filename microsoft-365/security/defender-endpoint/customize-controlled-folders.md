---
title: Настройка управляемого доступа к папкам
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
ms.date: 03/24/2021
ms.technology: mde
ms.topic: how-to
ms.openlocfilehash: 0962913df63e6837664cdb8ff79710d66e66977c
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199921"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="266b4-104">Настройка управляемого доступа к папкам</span><span class="sxs-lookup"><span data-stu-id="266b4-104">Customize controlled folder access</span></span>

<span data-ttu-id="266b4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="266b4-105">**Applies to:**</span></span>
- [<span data-ttu-id="266b4-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="266b4-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="266b4-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="266b4-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="266b4-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="266b4-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="266b4-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="266b4-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="266b4-110">Управляемый доступ к папкам помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей.</span><span class="sxs-lookup"><span data-stu-id="266b4-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="266b4-111">Управляемый доступ к папкам поддерживается в клиентах Windows Server 2019 и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="266b4-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="266b4-112">В этой статье описывается настройка возможностей доступа к управляемым папкам и содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="266b4-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="266b4-113">Защита дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="266b4-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="266b4-114">Добавление приложений, которые должны быть разрешены для доступа к защищенным папок</span><span class="sxs-lookup"><span data-stu-id="266b4-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="266b4-115">Разрешить подписанным исполняемым файлам доступ к защищенным папкам</span><span class="sxs-lookup"><span data-stu-id="266b4-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="266b4-116">Настройка уведомления</span><span class="sxs-lookup"><span data-stu-id="266b4-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="266b4-117">Контролируемый доступ к папкам отслеживает приложения для действий, которые обнаруживаются как вредоносные.</span><span class="sxs-lookup"><span data-stu-id="266b4-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="266b4-118">Иногда законным приложениям блокируется внесение изменений в файлы.</span><span class="sxs-lookup"><span data-stu-id="266b4-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="266b4-119">Если управляемый доступ к папкам влияет на производительность организации, можно рассмотреть возможность запуска этой функции в режиме аудита, чтобы полностью оценить последствия. [](audit-windows-defender.md)</span><span class="sxs-lookup"><span data-stu-id="266b4-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="266b4-120">Защита дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="266b4-120">Protect additional folders</span></span>

<span data-ttu-id="266b4-121">Управляемый доступ к папкам применяется ко многим папкам системы и расположениям по умолчанию, включая такие папки, как **Documents,** **Pictures** и **Movies.**</span><span class="sxs-lookup"><span data-stu-id="266b4-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="266b4-122">Вы можете добавить дополнительные папки, которые необходимо защитить, но вы не можете удалить папки по умолчанию в списке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="266b4-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="266b4-123">Добавление других папок к управляемому доступу к папкам может быть полезно для случаев, когда вы не сохраняете файлы в библиотеках Windows по умолчанию или вы изменили расположение библиотек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="266b4-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="266b4-124">Вы также можете указать сетевые акции и составить карту дисков.</span><span class="sxs-lookup"><span data-stu-id="266b4-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="266b4-125">Поддерживаются переменные среды и подкарды.</span><span class="sxs-lookup"><span data-stu-id="266b4-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="266b4-126">Сведения об использовании подмастерьев см. в материалах [Use wildcards in the file name and folder path or extension exclusion lists.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="266b4-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="266b4-127">Для добавления и удаления дополнительных защищенных папок можно использовать приложение Windows Security, групповую политику, команды PowerShell или поставщики служб конфигурации управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="266b4-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="266b4-128">Используйте приложение Windows Security для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="266b4-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="266b4-129">Откройте приложение Безопасности Windows, выбрав значок щита в панели задач или нажав меню пусков для **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="266b4-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="266b4-130">Выберите **защиту & вирусов,** а затем прокрутите его в раздел **Защита вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="266b4-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="266b4-131">Выберите **Управление защитой вымогателей,** чтобы открыть области защиты вымогателей. </span><span class="sxs-lookup"><span data-stu-id="266b4-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="266b4-132">В разделе **Управляемый доступ к папкам** выберите **защищенные папки.**</span><span class="sxs-lookup"><span data-stu-id="266b4-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="266b4-133">Выберите **Да** в **запросе Управления доступом пользователей.**</span><span class="sxs-lookup"><span data-stu-id="266b4-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="266b4-134">Экраны **области защищенных** папок.</span><span class="sxs-lookup"><span data-stu-id="266b4-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="266b4-135">Выберите **Добавить защищенную папку** и следуйте подсказкам для добавления папок.</span><span class="sxs-lookup"><span data-stu-id="266b4-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="266b4-136">Использование групповой политики для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="266b4-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="266b4-137">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="266b4-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="266b4-138">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="266b4-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="266b4-139">Расширь дерево до **компонентов**  >  **антивируса Microsoft Defender Защитник Windows**  >  **с**  >  управляемым доступом к папкам.</span><span class="sxs-lookup"><span data-stu-id="266b4-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="266b4-140">Дважды **щелкните Настроенные защищенные папки и** установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="266b4-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="266b4-141">Выберите **Показать и** ввести каждую папку.</span><span class="sxs-lookup"><span data-stu-id="266b4-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="266b4-142">Использование PowerShell для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="266b4-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="266b4-143">Введите **PowerShell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="266b4-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="266b4-144">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="266b4-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="266b4-145">Повторите шаг 2, пока не добавите все папки, которые необходимо защитить.</span><span class="sxs-lookup"><span data-stu-id="266b4-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="266b4-146">Добавленные папки видны в приложении Windows Security.</span><span class="sxs-lookup"><span data-stu-id="266b4-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![Снимок экрана окна PowerShell с вступитым выше cmdlet](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="266b4-148">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="266b4-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="266b4-149">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="266b4-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="266b4-150">Использование CSPs MDM для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="266b4-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="266b4-151">Используйте [поставщик служб конфигурации ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.</span><span class="sxs-lookup"><span data-stu-id="266b4-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="266b4-152">Разрешить определенным приложениям вносить изменения в управляемые папки</span><span class="sxs-lookup"><span data-stu-id="266b4-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="266b4-153">Можно указать, считаются ли некоторые приложения безопасными, и предоставить доступ к файлам в защищенных папках.</span><span class="sxs-lookup"><span data-stu-id="266b4-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="266b4-154">Разрешение приложений может быть полезным, если определенное приложение, которое вы знаете и доверяете, блокируется функцией доступа к управляемой папке.</span><span class="sxs-lookup"><span data-stu-id="266b4-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="266b4-155">По умолчанию Windows добавляет приложения, которые считаются удобными для разрешенного списка.</span><span class="sxs-lookup"><span data-stu-id="266b4-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="266b4-156">Такие приложения, которые добавляются автоматически, не записываются в список, показанный в приложении Безопасности Windows или с помощью связанных с ними cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="266b4-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="266b4-157">Не нужно добавлять большинство приложений.</span><span class="sxs-lookup"><span data-stu-id="266b4-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="266b4-158">Добавляйте приложения только в том случае, если они заблокированы, и вы можете проверить их надежность.</span><span class="sxs-lookup"><span data-stu-id="266b4-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="266b4-159">При добавлении приложения необходимо указать расположение приложения.</span><span class="sxs-lookup"><span data-stu-id="266b4-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="266b4-160">Только приложению в этом расположении будет разрешен доступ к защищенным папкам.</span><span class="sxs-lookup"><span data-stu-id="266b4-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="266b4-161">Если приложение (с тем же именем) находится в другом расположении, оно не будет добавлено в список допустимых и может быть заблокировано управляемым доступом к папке.</span><span class="sxs-lookup"><span data-stu-id="266b4-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="266b4-162">Разрешенное приложение или служба имеет доступ к управляемой папке только после ее начала.</span><span class="sxs-lookup"><span data-stu-id="266b4-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="266b4-163">Например, служба обновления будет продолжать запускать события после ее разрешения, пока она не будет остановлена и перезапущена.</span><span class="sxs-lookup"><span data-stu-id="266b4-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="266b4-164">Используйте приложение Защитник Windows безопасности, чтобы разрешить определенные приложения</span><span class="sxs-lookup"><span data-stu-id="266b4-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="266b4-165">Откройте приложение Windows Security, ища меню пуск для **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="266b4-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="266b4-166">Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем выберите управление защитой **вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="266b4-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="266b4-167">В разделе **Управляемый доступ к папке** выберите Разрешить приложение с помощью управляемого доступа **к папке**</span><span class="sxs-lookup"><span data-stu-id="266b4-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="266b4-168">Выберите **Добавление разрешенного приложения** и следуйте подсказкам для добавления приложений.</span><span class="sxs-lookup"><span data-stu-id="266b4-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

   :::image type="content" source="images/cfa-allow-app.png" alt-text="Добавление разрешенной кнопки приложения":::

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="266b4-170">Использование групповой политики для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="266b4-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="266b4-171">На устройстве управления групповой политикой откройте консоль управления групповой политикой [правой](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="266b4-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="266b4-172">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="266b4-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="266b4-173">Расширь дерево до **компонентов**  >  **антивируса Microsoft Defender Защитник Windows**  >  **с**  >  управляемым доступом к папкам.</span><span class="sxs-lookup"><span data-stu-id="266b4-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="266b4-174">Дважды щелкните **параметр Настройка разрешенных приложений** и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="266b4-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="266b4-175">Выберите **Показать** и ввести каждое приложение.</span><span class="sxs-lookup"><span data-stu-id="266b4-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="266b4-176">Использование PowerShell для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="266b4-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="266b4-177">Введите **PowerShell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="266b4-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="266b4-178">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="266b4-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="266b4-179">Например, чтобы добавить исполняемыйtest.exe, расположенный в папке *C:\apps,* этот комлет будет следующим образом: </span><span class="sxs-lookup"><span data-stu-id="266b4-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="266b4-180">Продолжайте использовать `Add-MpPreference -ControlledFolderAccessAllowedApplications` для добавления дополнительных приложений в список.</span><span class="sxs-lookup"><span data-stu-id="266b4-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="266b4-181">Приложения, добавленные с помощью этого комлета, будут отображаться в приложении Безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="266b4-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

   :::image type="content" source="images/cfa-allow-app-ps.png" alt-text="Cmdlet PowerShell, чтобы разрешить приложение":::

> [!IMPORTANT]
> <span data-ttu-id="266b4-183">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="266b4-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="266b4-184">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="266b4-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="266b4-185">Использование CSPs MDM для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="266b4-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="266b4-186">Используйте [поставщик услуг конфигурации ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.</span><span class="sxs-lookup"><span data-stu-id="266b4-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="266b4-187">Разрешить подписанным исполняемым файлам доступ к защищенным папкам</span><span class="sxs-lookup"><span data-stu-id="266b4-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="266b4-188">Индикаторы сертификата и файлов Microsoft Defender для конечной точки могут разрешить подписанным исполняемым файлам доступ к защищенным папкам.</span><span class="sxs-lookup"><span data-stu-id="266b4-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="266b4-189">Дополнительные сведения о реализации см. [в материале Create indicators based on certificates.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="266b4-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="266b4-190">Это не относится к сценариям, включая Powershell</span><span class="sxs-lookup"><span data-stu-id="266b4-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="266b4-191">Настройка уведомления</span><span class="sxs-lookup"><span data-stu-id="266b4-191">Customize the notification</span></span>

<span data-ttu-id="266b4-192">Дополнительные сведения о настройке уведомления при запуске правила и блокировке приложения или файла см. в статью Настройка уведомлений оповещения в [Microsoft Defender для конечной точки.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)</span><span class="sxs-lookup"><span data-stu-id="266b4-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="266b4-193">См. также</span><span class="sxs-lookup"><span data-stu-id="266b4-193">See also</span></span>

- [<span data-ttu-id="266b4-194">Защита важных папок с управляемым доступом к папкам</span><span class="sxs-lookup"><span data-stu-id="266b4-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="266b4-195">Включить управляемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="266b4-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="266b4-196">Оценка правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="266b4-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
