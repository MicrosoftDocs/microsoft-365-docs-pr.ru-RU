---
title: Настройка и проверка исключений для ATP Защитника Майкрософт для Linux
description: Предоставление и проверка исключений для ATP Microsoft Defender для Linux. Исключения могут быть установлены для файлов, папок и процессов.
keywords: Microsoft, defender, atp, linux, exclusions, scans, antivirus
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
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
ms.technology: mde
ms.openlocfilehash: fa2d643936b8358649bf59eec3ab9570cb561419
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072301"
---
# <a name="configure-and-validate-exclusions-for-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="c12c1-105">Настройка и проверка исключений для Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="c12c1-105">Configure and validate exclusions for Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c12c1-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c12c1-106">**Applies to:**</span></span>
- [<span data-ttu-id="c12c1-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c12c1-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="c12c1-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c12c1-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="c12c1-109">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c12c1-109">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c12c1-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c12c1-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

<span data-ttu-id="c12c1-111">В этой статье данная статья содержит сведения о том, как определить исключения, применимые к проверкам по запросу, а также защиту и мониторинг в режиме реального времени.</span><span class="sxs-lookup"><span data-stu-id="c12c1-111">This article provides information on how to define exclusions that apply to on-demand scans, and real-time protection and monitoring.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="c12c1-112">Исключения, описанные в этой статье, не применяются к другим возможностям Defender for Endpoint для Linux, включая обнаружение конечной точки и ответ (EDR).</span><span class="sxs-lookup"><span data-stu-id="c12c1-112">The exclusions described in this article don't apply to other Defender for Endpoint for Linux capabilities, including endpoint detection and response (EDR).</span></span> <span data-ttu-id="c12c1-113">Файлы, исключаемые с помощью методов, описанных в этой статье, по-прежнему могут вызывать оповещения EDR и другие обнаружения.</span><span class="sxs-lookup"><span data-stu-id="c12c1-113">Files that you exclude using the methods described in this article can still trigger EDR alerts and other detections.</span></span>

<span data-ttu-id="c12c1-114">Вы можете исключить определенные файлы, папки, процессы и файлы, открытые процессом, из defender for Endpoint для проверки Linux.</span><span class="sxs-lookup"><span data-stu-id="c12c1-114">You can exclude certain files, folders, processes, and process-opened files from Defender for Endpoint for Linux scans.</span></span>

<span data-ttu-id="c12c1-115">Исключения могут быть полезны, чтобы избежать неправильных обнаружений в файлах или программном обеспечении, уникальных или настраиваемых для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="c12c1-115">Exclusions can be useful to avoid incorrect detections on files or software that are unique or customized to your organization.</span></span> <span data-ttu-id="c12c1-116">Они также могут быть полезны для смягчения проблем с производительностью, вызванных Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="c12c1-116">They can also be useful for mitigating performance issues caused by Defender for Endpoint for Linux.</span></span>

> [!WARNING]
> <span data-ttu-id="c12c1-117">Определение исключений снижает защиту, предложенную Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="c12c1-117">Defining exclusions lowers the protection offered by Defender for Endpoint for Linux.</span></span> <span data-ttu-id="c12c1-118">Всегда следует оценивать риски, связанные с реализацией исключений, и следует исключить только те файлы, которые, как вы уверены, не являются вредоносными.</span><span class="sxs-lookup"><span data-stu-id="c12c1-118">You should always evaluate the risks that are associated with implementing exclusions, and you should only exclude files that you are confident are not malicious.</span></span>

## <a name="supported-exclusion-types"></a><span data-ttu-id="c12c1-119">Поддерживаемые типы исключений</span><span class="sxs-lookup"><span data-stu-id="c12c1-119">Supported exclusion types</span></span>

<span data-ttu-id="c12c1-120">В таблице ниже показаны типы исключений, поддерживаемые Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="c12c1-120">The follow table shows the exclusion types supported by Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="c12c1-121">Исключения</span><span class="sxs-lookup"><span data-stu-id="c12c1-121">Exclusion</span></span> | <span data-ttu-id="c12c1-122">Определение</span><span class="sxs-lookup"><span data-stu-id="c12c1-122">Definition</span></span> | <span data-ttu-id="c12c1-123">Примеры</span><span class="sxs-lookup"><span data-stu-id="c12c1-123">Examples</span></span>
---|---|---
<span data-ttu-id="c12c1-124">Расширение файла</span><span class="sxs-lookup"><span data-stu-id="c12c1-124">File extension</span></span> | <span data-ttu-id="c12c1-125">Все файлы с расширением в любом месте на устройстве</span><span class="sxs-lookup"><span data-stu-id="c12c1-125">All files with the extension, anywhere on the device</span></span> | `.test`
<span data-ttu-id="c12c1-126">Файл</span><span class="sxs-lookup"><span data-stu-id="c12c1-126">File</span></span> | <span data-ttu-id="c12c1-127">Определенный файл, определенный по полному пути</span><span class="sxs-lookup"><span data-stu-id="c12c1-127">A specific file identified by the full path</span></span> | `/var/log/test.log`<br/>`/var/log/*.log`<br/>`/var/log/install.?.log`
<span data-ttu-id="c12c1-128">Folder</span><span class="sxs-lookup"><span data-stu-id="c12c1-128">Folder</span></span> | <span data-ttu-id="c12c1-129">Все файлы в указанной папке (повторно)</span><span class="sxs-lookup"><span data-stu-id="c12c1-129">All files under the specified folder (recursively)</span></span> | `/var/log/`<br/>`/var/*/`
<span data-ttu-id="c12c1-130">Процесс</span><span class="sxs-lookup"><span data-stu-id="c12c1-130">Process</span></span> | <span data-ttu-id="c12c1-131">Определенный процесс (указанный полным путем или именем файла) и все файлы, открытые в нем.</span><span class="sxs-lookup"><span data-stu-id="c12c1-131">A specific process (specified either by the full path or file name) and all files opened by it</span></span> | `/bin/cat`<br/>`cat`<br/>`c?t`

> [!IMPORTANT]
> <span data-ttu-id="c12c1-132">Для успешного исключения из нее должны быть жесткие ссылки, а не символические.</span><span class="sxs-lookup"><span data-stu-id="c12c1-132">The paths above must be hard links, not symbolic links, in order to be successfully excluded.</span></span> <span data-ttu-id="c12c1-133">Вы можете проверить, является ли путь символической ссылкой при `file <path-name>` запуске.</span><span class="sxs-lookup"><span data-stu-id="c12c1-133">You can check if a path is a symbolic link by running `file <path-name>`.</span></span>

<span data-ttu-id="c12c1-134">Исключения файлов, папок и процессов поддерживают следующие подкарды:</span><span class="sxs-lookup"><span data-stu-id="c12c1-134">File, folder, and process exclusions support the following wildcards:</span></span>

<span data-ttu-id="c12c1-135">Подстановочный знак</span><span class="sxs-lookup"><span data-stu-id="c12c1-135">Wildcard</span></span> | <span data-ttu-id="c12c1-136">Описание</span><span class="sxs-lookup"><span data-stu-id="c12c1-136">Description</span></span> | <span data-ttu-id="c12c1-137">Пример</span><span class="sxs-lookup"><span data-stu-id="c12c1-137">Example</span></span> | <span data-ttu-id="c12c1-138">Совпадения</span><span class="sxs-lookup"><span data-stu-id="c12c1-138">Matches</span></span> | <span data-ttu-id="c12c1-139">Не совпадает</span><span class="sxs-lookup"><span data-stu-id="c12c1-139">Does not match</span></span>
---|---|---|---|---
\* |    <span data-ttu-id="c12c1-140">Совпадает с любым числом символов, в том числе без них (обратите внимание, что при данной подмастерье используется внутри пути, она заменит только одну папку)</span><span class="sxs-lookup"><span data-stu-id="c12c1-140">Matches any number of any characters including none (note that when this wildcard is used inside a path it will substitute only one folder)</span></span> | `/var/\*/\*.log` | `/var/log/system.log` | `/var/log/nested/system.log`
<span data-ttu-id="c12c1-141">?</span><span class="sxs-lookup"><span data-stu-id="c12c1-141">?</span></span> | <span data-ttu-id="c12c1-142">Соответствует любому отдельному символу</span><span class="sxs-lookup"><span data-stu-id="c12c1-142">Matches any single character</span></span> | `file?.log` | `file1.log`<br/>`file2.log` | `file123.log`

## <a name="how-to-configure-the-list-of-exclusions"></a><span data-ttu-id="c12c1-143">Настройка списка исключений</span><span class="sxs-lookup"><span data-stu-id="c12c1-143">How to configure the list of exclusions</span></span>

### <a name="from-the-management-console"></a><span data-ttu-id="c12c1-144">Из консоли управления</span><span class="sxs-lookup"><span data-stu-id="c12c1-144">From the management console</span></span>

<span data-ttu-id="c12c1-145">Дополнительные сведения о настройке исключений из Puppet, Ansible или другой консоли управления см. в статью Настройка предпочтений [для Defender для конечной](linux-preferences.md)точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="c12c1-145">For more information on how to configure exclusions from Puppet, Ansible, or another management console, see [Set preferences for Defender for Endpoint for Linux](linux-preferences.md).</span></span>

### <a name="from-the-command-line"></a><span data-ttu-id="c12c1-146">Из командной строки</span><span class="sxs-lookup"><span data-stu-id="c12c1-146">From the command line</span></span>

<span data-ttu-id="c12c1-147">Запустите следующую команду, чтобы увидеть доступные переключатели для управления исключениями:</span><span class="sxs-lookup"><span data-stu-id="c12c1-147">Run the following command to see the available switches for managing exclusions:</span></span>

```bash
mdatp exclusion
```

> [!TIP]
> <span data-ttu-id="c12c1-148">При настройке исключений с помощью поддиагров заключим параметр в двойные кавычка, чтобы предотвратить globbing.</span><span class="sxs-lookup"><span data-stu-id="c12c1-148">When configuring exclusions with wildcards, enclose the parameter in double-quotes to prevent globbing.</span></span>

<span data-ttu-id="c12c1-149">Примеры:</span><span class="sxs-lookup"><span data-stu-id="c12c1-149">Examples:</span></span>

- <span data-ttu-id="c12c1-150">Добавление исключения для расширения файла:</span><span class="sxs-lookup"><span data-stu-id="c12c1-150">Add an exclusion for a file extension:</span></span>

    ```bash
    mdatp exclusion extension add --name .txt
    ```
    ```Output
    Extension exclusion configured successfully
    ```

- <span data-ttu-id="c12c1-151">Добавление исключения для файла:</span><span class="sxs-lookup"><span data-stu-id="c12c1-151">Add an exclusion for a file:</span></span>

    ```bash
    mdatp exclusion file add --path /var/log/dummy.log
    ```
    ```Output
    File exclusion configured successfully
    ```

- <span data-ttu-id="c12c1-152">Добавление исключения для папки:</span><span class="sxs-lookup"><span data-stu-id="c12c1-152">Add an exclusion for a folder:</span></span>

    ```bash
    mdatp exclusion folder add --path /var/log/
    ```
    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="c12c1-153">Добавьте исключение для папки с подстройки в ней:</span><span class="sxs-lookup"><span data-stu-id="c12c1-153">Add an exclusion for a folder with a wildcard in it:</span></span>

    ```bash
    mdatp exclusion folder add --path "/var/*/"
    ```

    > [!NOTE]
    > <span data-ttu-id="c12c1-154">Это позволит исключить только пути на уровне *ниже /var/,* но не папки, которые более глубоко вложены; например, */var/this-subfolder/but-not-this-subfolder*.</span><span class="sxs-lookup"><span data-stu-id="c12c1-154">This will only exclude paths one level below */var/*, but not folders which are more deeply nested; for example, */var/this-subfolder/but-not-this-subfolder*.</span></span>
    
    ```bash
    mdatp exclusion folder add --path "/var/"
    ```
    > [!NOTE]
    > <span data-ttu-id="c12c1-155">Это исключит все пути, родитель которых */var/*; например, */var/this-subfolder/and-this-subfolder-as-well*.</span><span class="sxs-lookup"><span data-stu-id="c12c1-155">This will exclude all paths whose parent is */var/*; for example, */var/this-subfolder/and-this-subfolder-as-well*.</span></span>

    ```Output
    Folder exclusion configured successfully
    ```

- <span data-ttu-id="c12c1-156">Добавление исключения для процесса:</span><span class="sxs-lookup"><span data-stu-id="c12c1-156">Add an exclusion for a process:</span></span>

    ```bash
    mdatp exclusion process add --name cat
    ```
    ```Output    
    Process exclusion configured successfully
    ```

## <a name="validate-exclusions-lists-with-the-eicar-test-file"></a><span data-ttu-id="c12c1-157">Проверка списков исключений в тестовом файле EICAR</span><span class="sxs-lookup"><span data-stu-id="c12c1-157">Validate exclusions lists with the EICAR test file</span></span>

<span data-ttu-id="c12c1-158">Вы можете проверить, работают ли списки исключений, `curl` скачав тестовый файл.</span><span class="sxs-lookup"><span data-stu-id="c12c1-158">You can validate that your exclusion lists are working by using `curl` to download a test file.</span></span>

<span data-ttu-id="c12c1-159">В следующем фрагменте Bash замените файл, соответствующий `test.txt` правилам исключения.</span><span class="sxs-lookup"><span data-stu-id="c12c1-159">In the following Bash snippet, replace `test.txt` with a file that conforms to your exclusion rules.</span></span> <span data-ttu-id="c12c1-160">Например, если вы исключили `.testing` расширение, замените `test.txt` `test.testing` .</span><span class="sxs-lookup"><span data-stu-id="c12c1-160">For example, if you have excluded the `.testing` extension, replace `test.txt` with `test.testing`.</span></span> <span data-ttu-id="c12c1-161">Если вы тестируете путь, убедитесь, что вы запустите команду в этом пути.</span><span class="sxs-lookup"><span data-stu-id="c12c1-161">If you are testing a path, ensure that you run the command within that path.</span></span>

```bash
curl -o test.txt https://www.eicar.org/download/eicar.com.txt
```

<span data-ttu-id="c12c1-162">Если Defender for Endpoint для Linux сообщает о вредоносных программах, то правило не работает.</span><span class="sxs-lookup"><span data-stu-id="c12c1-162">If Defender for Endpoint for Linux reports malware, then the rule is not working.</span></span> <span data-ttu-id="c12c1-163">Если нет отчета о вредоносных программах, а загруженный файл существует, то исключение работает.</span><span class="sxs-lookup"><span data-stu-id="c12c1-163">If there is no report of malware, and the downloaded file exists, then the exclusion is working.</span></span> <span data-ttu-id="c12c1-164">Вы можете открыть файл, чтобы подтвердить, что содержимое является таким же, как описано на веб-сайте [тестового файла EICAR](http://2016.eicar.org/86-0-Intended-use.html).</span><span class="sxs-lookup"><span data-stu-id="c12c1-164">You can open the file to confirm that the contents are the same as what is described on the [EICAR test file website](http://2016.eicar.org/86-0-Intended-use.html).</span></span>

<span data-ttu-id="c12c1-165">Если у вас нет доступа к Интернету, вы можете создать собственный тестовый файл EICAR.</span><span class="sxs-lookup"><span data-stu-id="c12c1-165">If you do not have Internet access, you can create your own EICAR test file.</span></span> <span data-ttu-id="c12c1-166">Напишите строку EICAR в новый текстовый файл со следующей командой Bash:</span><span class="sxs-lookup"><span data-stu-id="c12c1-166">Write the EICAR string to a new text file with the following Bash command:</span></span>

```bash
echo 'X5O!P%@AP[4\PZX54(P^)7CC)7}$EICAR-STANDARD-ANTIVIRUS-TEST-FILE!$H+H*' > test.txt
```

<span data-ttu-id="c12c1-167">Вы также можете скопировать строку в пустой текстовый файл и попытаться сохранить ее с именем файла или в папке, вы пытаетсяе исключить.</span><span class="sxs-lookup"><span data-stu-id="c12c1-167">You can also copy the string into a blank text file and attempt to save it with the file name or in the folder you are attempting to exclude.</span></span>

## <a name="allow-threats"></a><span data-ttu-id="c12c1-168">Разрешить угрозы</span><span class="sxs-lookup"><span data-stu-id="c12c1-168">Allow threats</span></span>

<span data-ttu-id="c12c1-169">Помимо исключения определенного контента из проверки можно также настроить продукт, чтобы не обнаруживать некоторые классы угроз (определенных именем угрозы).</span><span class="sxs-lookup"><span data-stu-id="c12c1-169">In addition to excluding certain content from being scanned, you can also configure the product not to detect some classes of threats (identified by the threat name).</span></span> <span data-ttu-id="c12c1-170">Вы должны соблюдать осторожность при использовании этой функции, так как она может оставить устройство незащищенным.</span><span class="sxs-lookup"><span data-stu-id="c12c1-170">You should exercise caution when using this functionality, as it can leave your device unprotected.</span></span>

<span data-ttu-id="c12c1-171">Чтобы добавить имя угрозы в разрешенный список, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c12c1-171">To add a threat name to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name [threat-name]
```

<span data-ttu-id="c12c1-172">Имя угрозы, связанное с обнаружением на устройстве, можно получить с помощью следующей команды:</span><span class="sxs-lookup"><span data-stu-id="c12c1-172">The threat name associated with a detection on your device can be obtained using the following command:</span></span>

```bash
mdatp threat list
```

<span data-ttu-id="c12c1-173">Например, чтобы добавить (имя угрозы, связанное с обнаружением EICAR) в разрешенный `EICAR-Test-File (not a virus)` список, выполните следующую команду:</span><span class="sxs-lookup"><span data-stu-id="c12c1-173">For example, to add `EICAR-Test-File (not a virus)` (the threat name associated with the EICAR detection) to the allowed list, execute the following command:</span></span>

```bash
mdatp threat allowed add --name "EICAR-Test-File (not a virus)"
```
