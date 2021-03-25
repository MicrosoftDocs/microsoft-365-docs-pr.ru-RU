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
ms.date: 01/06/2021
ms.technology: mde
ms.openlocfilehash: 64f96544361a672881c590716adea80f40777c6e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51163343"
---
# <a name="customize-controlled-folder-access"></a><span data-ttu-id="5e136-104">Настройка управляемого доступа к папкам</span><span class="sxs-lookup"><span data-stu-id="5e136-104">Customize controlled folder access</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="5e136-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5e136-105">**Applies to:**</span></span>
- [<span data-ttu-id="5e136-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5e136-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5e136-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5e136-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5e136-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5e136-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5e136-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5e136-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)


<span data-ttu-id="5e136-110">Управляемый доступ к папкам помогает защитить ценные данные от вредоносных приложений и угроз, таких как вымогателей.</span><span class="sxs-lookup"><span data-stu-id="5e136-110">Controlled folder access helps you protect valuable data from malicious apps and threats, such as ransomware.</span></span> <span data-ttu-id="5e136-111">Управляемый доступ к папкам поддерживается в клиентах Windows Server 2019 и Windows 10.</span><span class="sxs-lookup"><span data-stu-id="5e136-111">Controlled folder access is supported on Windows Server 2019 and Windows 10 clients.</span></span>

<span data-ttu-id="5e136-112">В этой статье описывается настройка возможностей доступа к управляемым папкам и содержатся следующие разделы:</span><span class="sxs-lookup"><span data-stu-id="5e136-112">This article describes how to customize controlled folder access capabilities, and includes the following sections:</span></span>

- [<span data-ttu-id="5e136-113">Защита дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="5e136-113">Protect additional folders</span></span>](#protect-additional-folders)
- [<span data-ttu-id="5e136-114">Добавление приложений, которые должны быть разрешены для доступа к защищенным папок</span><span class="sxs-lookup"><span data-stu-id="5e136-114">Add apps that should be allowed to access protected folders</span></span>](#allow-specific-apps-to-make-changes-to-controlled-folders)
- [<span data-ttu-id="5e136-115">Разрешить подписанным исполняемым файлам доступ к защищенным папкам</span><span class="sxs-lookup"><span data-stu-id="5e136-115">Allow signed executable files to access protected folders</span></span>](#allow-signed-executable-files-to-access-protected-folders)
- [<span data-ttu-id="5e136-116">Настройка уведомления</span><span class="sxs-lookup"><span data-stu-id="5e136-116">Customize the notification</span></span>](#customize-the-notification)

> [!IMPORTANT]
> <span data-ttu-id="5e136-117">Контролируемый доступ к папкам отслеживает приложения для действий, которые обнаруживаются как вредоносные.</span><span class="sxs-lookup"><span data-stu-id="5e136-117">Controlled folder access monitors apps for activities that are detected as malicious.</span></span> <span data-ttu-id="5e136-118">Иногда законным приложениям блокируется внесение изменений в файлы.</span><span class="sxs-lookup"><span data-stu-id="5e136-118">Sometimes, legitimate apps are blocked from making changes to your files.</span></span> <span data-ttu-id="5e136-119">Если управляемый доступ к папкам влияет на производительность организации, можно рассмотреть возможность запуска этой функции в режиме аудита, чтобы полностью оценить последствия. [](audit-windows-defender.md)</span><span class="sxs-lookup"><span data-stu-id="5e136-119">If controlled folder access impacts your organization's productivity, you might consider running this feature in [audit mode](audit-windows-defender.md) to fully assess the impact.</span></span>

## <a name="protect-additional-folders"></a><span data-ttu-id="5e136-120">Защита дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="5e136-120">Protect additional folders</span></span>

<span data-ttu-id="5e136-121">Управляемый доступ к папкам применяется ко многим папкам системы и расположениям по умолчанию, включая такие папки, как **Documents,** **Pictures** и **Movies.**</span><span class="sxs-lookup"><span data-stu-id="5e136-121">Controlled folder access applies to many system folders and default locations, including folders such as **Documents**, **Pictures**, and **Movies**.</span></span> <span data-ttu-id="5e136-122">Вы можете добавить дополнительные папки, которые необходимо защитить, но вы не можете удалить папки по умолчанию в списке по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e136-122">You can add additional folders to be protected, but you cannot remove the default folders in the default list.</span></span>

<span data-ttu-id="5e136-123">Добавление других папок к управляемому доступу к папкам может быть полезно для случаев, когда вы не сохраняете файлы в библиотеках Windows по умолчанию или вы изменили расположение библиотек по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="5e136-123">Adding other folders to controlled folder access can be helpful for cases when you don't store files in the default Windows libraries, or you've changed the default location of your libraries.</span></span>

<span data-ttu-id="5e136-124">Вы также можете указать сетевые акции и составить карту дисков.</span><span class="sxs-lookup"><span data-stu-id="5e136-124">You can also specify network shares and mapped drives.</span></span> <span data-ttu-id="5e136-125">Поддерживаются переменные среды и подкарды.</span><span class="sxs-lookup"><span data-stu-id="5e136-125">Environment variables and wildcards are supported.</span></span> <span data-ttu-id="5e136-126">Сведения об использовании подмастерьев см. в материалах [Use wildcards in the file name and folder path or extension exclusion lists.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists)</span><span class="sxs-lookup"><span data-stu-id="5e136-126">For information about using wildcards, see [Use wildcards in the file name and folder path or extension exclusion lists](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-extension-file-exclusions-microsoft-defender-antivirus#use-wildcards-in-the-file-name-and-folder-path-or-extension-exclusion-lists).</span></span>

<span data-ttu-id="5e136-127">Для добавления и удаления дополнительных защищенных папок можно использовать приложение Windows Security, групповую политику, команды PowerShell или поставщики служб конфигурации управления мобильными устройствами.</span><span class="sxs-lookup"><span data-stu-id="5e136-127">You can use the Windows Security app, Group Policy, PowerShell cmdlets, or mobile device management configuration service providers to add and remove additional protected folders.</span></span>

### <a name="use-the-windows-security-app-to-protect-additional-folders"></a><span data-ttu-id="5e136-128">Используйте приложение Windows Security для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="5e136-128">Use the Windows Security app to protect additional folders</span></span>

1. <span data-ttu-id="5e136-129">Откройте приложение Безопасности Windows, выбрав значок щита в панели задач или нажав меню пусков для **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="5e136-129">Open the Windows Security app by selecting the shield icon in the task bar or searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="5e136-130">Выберите **защиту & вирусов,** а затем прокрутите его в раздел **Защита вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="5e136-130">Select **Virus & threat protection**, and then scroll down to the **Ransomware protection** section.</span></span>

3. <span data-ttu-id="5e136-131">Выберите **Управление защитой вымогателей,** чтобы открыть области защиты вымогателей. </span><span class="sxs-lookup"><span data-stu-id="5e136-131">Select **Manage ransomware protection** to open the **Ransomware protection** pane.</span></span>

4. <span data-ttu-id="5e136-132">В разделе **Управляемый доступ к папкам** выберите **защищенные папки.**</span><span class="sxs-lookup"><span data-stu-id="5e136-132">Under the **Controlled folder access** section, select **Protected folders**.</span></span>

5. <span data-ttu-id="5e136-133">Выберите **Да** в **запросе Управления доступом пользователей.**</span><span class="sxs-lookup"><span data-stu-id="5e136-133">Choose **Yes** on the **User Access Control** prompt.</span></span> <span data-ttu-id="5e136-134">Экраны **области защищенных** папок.</span><span class="sxs-lookup"><span data-stu-id="5e136-134">The **Protected folders** pane displays.</span></span>

4. <span data-ttu-id="5e136-135">Выберите **Добавить защищенную папку** и следуйте подсказкам для добавления папок.</span><span class="sxs-lookup"><span data-stu-id="5e136-135">Select **Add a protected folder** and follow the prompts to add folders.</span></span>

### <a name="use-group-policy-to-protect-additional-folders"></a><span data-ttu-id="5e136-136">Использование групповой политики для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="5e136-136">Use Group Policy to protect additional folders</span></span>

1. <span data-ttu-id="5e136-137">На компьютере управления групповой политикой откройте консоль управления групповой политикой [,](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)щелкните правой кнопкой мыши объект групповой политики, который необходимо настроить, а затем выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5e136-137">On your Group Policy management computer, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure, and then and select **Edit**.</span></span>

2. <span data-ttu-id="5e136-138">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="5e136-138">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="5e136-139">Расширь дерево до **компонентов**  >  **антивируса Microsoft Defender Защитник Windows**  >  **с**  >  управляемым доступом к папкам.</span><span class="sxs-lookup"><span data-stu-id="5e136-139">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="5e136-140">Дважды **щелкните Настроенные защищенные папки и** установите параметр **Включено**.</span><span class="sxs-lookup"><span data-stu-id="5e136-140">Double-click **Configured protected folders** and set the option to **Enabled**.</span></span> <span data-ttu-id="5e136-141">Выберите **Показать и** ввести каждую папку.</span><span class="sxs-lookup"><span data-stu-id="5e136-141">Select **Show** and enter each folder.</span></span>

### <a name="use-powershell-to-protect-additional-folders"></a><span data-ttu-id="5e136-142">Использование PowerShell для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="5e136-142">Use PowerShell to protect additional folders</span></span>

1. <span data-ttu-id="5e136-143">Введите **PowerShell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="5e136-143">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>

2. <span data-ttu-id="5e136-144">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5e136-144">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessProtectedFolders "<the folder to be protected>"
    ```
3. <span data-ttu-id="5e136-145">Повторите шаг 2, пока не добавите все папки, которые необходимо защитить.</span><span class="sxs-lookup"><span data-stu-id="5e136-145">Repeat step 2 until you have added all the folders you want to protect.</span></span> <span data-ttu-id="5e136-146">Добавленные папки видны в приложении Windows Security.</span><span class="sxs-lookup"><span data-stu-id="5e136-146">Folders that are added are visible in the Windows Security app.</span></span>

   ![Снимок экрана окна PowerShell с вступитым выше cmdlet](/microsoft-365/security/defender-endpoint/images/cfa-allow-folder-ps)

> [!IMPORTANT]
> <span data-ttu-id="5e136-148">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="5e136-148">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="5e136-149">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="5e136-149">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-protect-additional-folders"></a><span data-ttu-id="5e136-150">Использование CSPs MDM для защиты дополнительных папок</span><span class="sxs-lookup"><span data-stu-id="5e136-150">Use MDM CSPs to protect additional folders</span></span>

<span data-ttu-id="5e136-151">Используйте [поставщик служб конфигурации ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.</span><span class="sxs-lookup"><span data-stu-id="5e136-151">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersList](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfolderslist) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-specific-apps-to-make-changes-to-controlled-folders"></a><span data-ttu-id="5e136-152">Разрешить определенным приложениям вносить изменения в управляемые папки</span><span class="sxs-lookup"><span data-stu-id="5e136-152">Allow specific apps to make changes to controlled folders</span></span>

<span data-ttu-id="5e136-153">Можно указать, считаются ли некоторые приложения безопасными, и предоставить доступ к файлам в защищенных папках.</span><span class="sxs-lookup"><span data-stu-id="5e136-153">You can specify if certain apps are always considered safe and give write access to files in protected folders.</span></span> <span data-ttu-id="5e136-154">Разрешение приложений может быть полезным, если определенное приложение, которое вы знаете и доверяете, блокируется функцией доступа к управляемой папке.</span><span class="sxs-lookup"><span data-stu-id="5e136-154">Allowing apps can be useful if a particular app you know and trust is being blocked by the controlled folder access feature.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5e136-155">По умолчанию Windows добавляет приложения, которые считаются удобными для разрешенного списка.</span><span class="sxs-lookup"><span data-stu-id="5e136-155">By default, Windows adds apps that are considered friendly to the allowed list.</span></span> <span data-ttu-id="5e136-156">Такие приложения, которые добавляются автоматически, не записываются в список, показанный в приложении Безопасности Windows или с помощью связанных с ними cmdlets PowerShell.</span><span class="sxs-lookup"><span data-stu-id="5e136-156">Such apps that are added automatically are not recorded in the list shown in the Windows Security app or by using the associated PowerShell cmdlets.</span></span> <span data-ttu-id="5e136-157">Не нужно добавлять большинство приложений.</span><span class="sxs-lookup"><span data-stu-id="5e136-157">You shouldn't need to add most apps.</span></span> <span data-ttu-id="5e136-158">Добавляйте приложения только в том случае, если они заблокированы, и вы можете проверить их надежность.</span><span class="sxs-lookup"><span data-stu-id="5e136-158">Only add apps if they are being blocked and you can verify their trustworthiness.</span></span>

<span data-ttu-id="5e136-159">При добавлении приложения необходимо указать расположение приложения.</span><span class="sxs-lookup"><span data-stu-id="5e136-159">When you add an app, you have to specify the app's location.</span></span> <span data-ttu-id="5e136-160">Только приложению в этом расположении будет разрешен доступ к защищенным папкам.</span><span class="sxs-lookup"><span data-stu-id="5e136-160">Only the app in that location will be permitted access to the protected folders.</span></span> <span data-ttu-id="5e136-161">Если приложение (с тем же именем) находится в другом расположении, оно не будет добавлено в список допустимых и может быть заблокировано управляемым доступом к папке.</span><span class="sxs-lookup"><span data-stu-id="5e136-161">If the app (with the same name) is in a different location, it will not be added to the allow list and may be blocked by controlled folder access.</span></span>

<span data-ttu-id="5e136-162">Разрешенное приложение или служба имеет доступ к управляемой папке только после ее начала.</span><span class="sxs-lookup"><span data-stu-id="5e136-162">An allowed application or service only has write access to a controlled folder after it starts.</span></span> <span data-ttu-id="5e136-163">Например, служба обновления будет продолжать запускать события после ее разрешения, пока она не будет остановлена и перезапущена.</span><span class="sxs-lookup"><span data-stu-id="5e136-163">For example, an update service will continue to trigger events after it's allowed until it is stopped and restarted.</span></span>

### <a name="use-the-windows-defender-security-app-to-allow-specific-apps"></a><span data-ttu-id="5e136-164">Используйте приложение Защитник Windows безопасности, чтобы разрешить определенные приложения</span><span class="sxs-lookup"><span data-stu-id="5e136-164">Use the Windows Defender Security app to allow specific apps</span></span>

1. <span data-ttu-id="5e136-165">Откройте приложение Windows Security, ища меню пуск для **безопасности.**</span><span class="sxs-lookup"><span data-stu-id="5e136-165">Open the Windows Security app by searching the start menu for **Security**.</span></span>

2. <span data-ttu-id="5e136-166">Выберите **плитку защиты &** вирусов (или значок щита в левой панели меню), а затем выберите управление защитой **вымогателей.**</span><span class="sxs-lookup"><span data-stu-id="5e136-166">Select the **Virus & threat protection** tile (or the shield icon on the left menu bar) and then select **Manage ransomware protection**.</span></span>

3. <span data-ttu-id="5e136-167">В разделе **Управляемый доступ к папке** выберите Разрешить приложение с помощью управляемого доступа **к папке**</span><span class="sxs-lookup"><span data-stu-id="5e136-167">Under the **Controlled folder access** section, select **Allow an app through Controlled folder access**</span></span>

4. <span data-ttu-id="5e136-168">Выберите **Добавление разрешенного приложения** и следуйте подсказкам для добавления приложений.</span><span class="sxs-lookup"><span data-stu-id="5e136-168">Select **Add an allowed app** and follow the prompts to add apps.</span></span>

    ![Снимок экрана, как добавить разрешенную кнопку приложения](/microsoft-365/security/defender-endpoint/images/cfa-allow-app)

### <a name="use-group-policy-to-allow-specific-apps"></a><span data-ttu-id="5e136-170">Использование групповой политики для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="5e136-170">Use Group Policy to allow specific apps</span></span>

1. <span data-ttu-id="5e136-171">На устройстве управления групповой политикой откройте консоль управления групповой политикой [правой](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true)кнопкой мыши объект групповой политики, который необходимо настроить, и выберите **Изменить**.</span><span class="sxs-lookup"><span data-stu-id="5e136-171">On your Group Policy management device, open the [Group Policy Management Console](https://docs.microsoft.com/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11)?preserve=true), right-click the Group Policy Object you want to configure and select **Edit**.</span></span>

2. <span data-ttu-id="5e136-172">В **редакторе управления групповой политикой** перейдите к **конфигурации компьютера** и выберите **административные шаблоны.**</span><span class="sxs-lookup"><span data-stu-id="5e136-172">In the **Group Policy Management Editor**, go to **Computer configuration** and select **Administrative templates**.</span></span>

3. <span data-ttu-id="5e136-173">Расширь дерево до **компонентов**  >  **антивируса Microsoft Defender Защитник Windows**  >  **с**  >  управляемым доступом к папкам.</span><span class="sxs-lookup"><span data-stu-id="5e136-173">Expand the tree to **Windows components** > **Microsoft Defender Antivirus** > **Windows Defender Exploit Guard** > **Controlled folder access**.</span></span>

4. <span data-ttu-id="5e136-174">Дважды щелкните **параметр Настройка разрешенных приложений** и установите параметр **Включено.**</span><span class="sxs-lookup"><span data-stu-id="5e136-174">Double-click the **Configure allowed applications** setting and set the option to **Enabled**.</span></span> <span data-ttu-id="5e136-175">Выберите **Показать** и ввести каждое приложение.</span><span class="sxs-lookup"><span data-stu-id="5e136-175">Select **Show** and enter each app.</span></span>

### <a name="use-powershell-to-allow-specific-apps"></a><span data-ttu-id="5e136-176">Использование PowerShell для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="5e136-176">Use PowerShell to allow specific apps</span></span>

1. <span data-ttu-id="5e136-177">Введите **PowerShell** в меню Пуск, щелкните правой кнопкой мыши **Windows PowerShell** выберите **Выполнить в качестве администратора**</span><span class="sxs-lookup"><span data-stu-id="5e136-177">Type **PowerShell** in the Start menu, right-click **Windows PowerShell** and select **Run as administrator**</span></span>
2. <span data-ttu-id="5e136-178">Введите следующий cmdlet:</span><span class="sxs-lookup"><span data-stu-id="5e136-178">Enter the following cmdlet:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "<the app that should be allowed, including the path>"
    ```

    <span data-ttu-id="5e136-179">Например, чтобы добавить исполняемыйtest.exe, расположенный в папке *C:\apps,* этот комлет будет следующим образом: </span><span class="sxs-lookup"><span data-stu-id="5e136-179">For example, to add the executable *test.exe* located in the folder *C:\apps*, the cmdlet would be as follows:</span></span>

    ```PowerShell
    Add-MpPreference -ControlledFolderAccessAllowedApplications "c:\apps\test.exe"
    ```

   <span data-ttu-id="5e136-180">Продолжайте использовать `Add-MpPreference -ControlledFolderAccessAllowedApplications` для добавления дополнительных приложений в список.</span><span class="sxs-lookup"><span data-stu-id="5e136-180">Continue to use `Add-MpPreference -ControlledFolderAccessAllowedApplications` to add more apps to the list.</span></span> <span data-ttu-id="5e136-181">Приложения, добавленные с помощью этого комлета, будут отображаться в приложении Безопасности Windows.</span><span class="sxs-lookup"><span data-stu-id="5e136-181">Apps added using this cmdlet will appear in the Windows Security app.</span></span>

![Снимок экрана окна PowerShell с вписаным выше cmdlet](/microsoft-365/security/defender-endpoint/images/cfa-allow-app-ps)

> [!IMPORTANT]
> <span data-ttu-id="5e136-183">Используйте `Add-MpPreference` для добавления или добавления приложений в список.</span><span class="sxs-lookup"><span data-stu-id="5e136-183">Use `Add-MpPreference` to append or add apps to the list.</span></span> <span data-ttu-id="5e136-184">С помощью `Set-MpPreference` этого комлета будет переописывать существующий список.</span><span class="sxs-lookup"><span data-stu-id="5e136-184">Using the `Set-MpPreference` cmdlet will overwrite the existing list.</span></span>

### <a name="use-mdm-csps-to-allow-specific-apps"></a><span data-ttu-id="5e136-185">Использование CSPs MDM для допуска определенных приложений</span><span class="sxs-lookup"><span data-stu-id="5e136-185">Use MDM CSPs to allow specific apps</span></span>

<span data-ttu-id="5e136-186">Используйте [поставщик услуг конфигурации ./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) (CSP), чтобы разрешить приложениям вносить изменения в защищенные папки.</span><span class="sxs-lookup"><span data-stu-id="5e136-186">Use the [./Vendor/MSFT/Policy/Config/Defender/GuardedFoldersAllowedApplications](https://docs.microsoft.com/windows/client-management/mdm/policy-csp-defender#defender-guardedfoldersallowedapplications) configuration service provider (CSP) to allow apps to make changes to protected folders.</span></span>

## <a name="allow-signed-executable-files-to-access-protected-folders"></a><span data-ttu-id="5e136-187">Разрешить подписанным исполняемым файлам доступ к защищенным папкам</span><span class="sxs-lookup"><span data-stu-id="5e136-187">Allow signed executable files to access protected folders</span></span>

<span data-ttu-id="5e136-188">Индикаторы сертификата и файлов Microsoft Defender для конечной точки могут разрешить подписанным исполняемым файлам доступ к защищенным папкам.</span><span class="sxs-lookup"><span data-stu-id="5e136-188">Microsoft Defender for Endpoint certificate and file indicators can allow signed executable files to access protected folders.</span></span> <span data-ttu-id="5e136-189">Дополнительные сведения о реализации см. [в материале Create indicators based on certificates.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates)</span><span class="sxs-lookup"><span data-stu-id="5e136-189">For implementation details, see [Create indicators based on certificates](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/indicator-certificates).</span></span>

> [!Note]
> <span data-ttu-id="5e136-190">Это не относится к сценариям, включая Powershell</span><span class="sxs-lookup"><span data-stu-id="5e136-190">This does no apply to scripting engines, including Powershell</span></span>

## <a name="customize-the-notification"></a><span data-ttu-id="5e136-191">Настройка уведомления</span><span class="sxs-lookup"><span data-stu-id="5e136-191">Customize the notification</span></span>

<span data-ttu-id="5e136-192">Дополнительные сведения о настройке уведомления при запуске правила и блокировке приложения или файла см. в статью Настройка уведомлений оповещения в [Microsoft Defender для конечной точки.](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications)</span><span class="sxs-lookup"><span data-stu-id="5e136-192">For more information about customizing the notification when a rule is triggered and blocks an app or file, see [Configure alert notifications in Microsoft Defender for Endpoint](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-email-notifications).</span></span>

## <a name="see-also"></a><span data-ttu-id="5e136-193">См. также</span><span class="sxs-lookup"><span data-stu-id="5e136-193">See also</span></span>

- [<span data-ttu-id="5e136-194">Защита важных папок с управляемым доступом к папкам</span><span class="sxs-lookup"><span data-stu-id="5e136-194">Protect important folders with controlled folder access</span></span>](controlled-folders.md)
- [<span data-ttu-id="5e136-195">Включить управляемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="5e136-195">Enable controlled folder access</span></span>](enable-controlled-folders.md)
- [<span data-ttu-id="5e136-196">Оценка правил уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="5e136-196">Evaluate attack surface reduction rules</span></span>](evaluate-attack-surface-reduction.md)
