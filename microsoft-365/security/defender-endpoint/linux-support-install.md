---
title: Проблемы с установкой неполадок для Microsoft Defender для конечной точки в Linux
ms.reviewer: ''
description: Проблемы с установкой неполадок для Microsoft Defender для конечной точки в Linux
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, installation
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
ms.openlocfilehash: dc1e8707dc0810c0986698674a64e969792b5fb8
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311236"
---
# <a name="troubleshoot-installation-issues-for-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="01fc9-104">Проблемы с установкой неполадок для Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="01fc9-104">Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="01fc9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="01fc9-105">**Applies to:**</span></span>
- [<span data-ttu-id="01fc9-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="01fc9-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="01fc9-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="01fc9-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="01fc9-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="01fc9-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="01fc9-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="01fc9-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

## <a name="verify-if-installation-succeeded"></a><span data-ttu-id="01fc9-110">Проверка успешной установки</span><span class="sxs-lookup"><span data-stu-id="01fc9-110">Verify if installation succeeded</span></span>

<span data-ttu-id="01fc9-111">Ошибка при установке может привести или не привести к содержательному сообщению об ошибке диспетчером пакетов.</span><span class="sxs-lookup"><span data-stu-id="01fc9-111">An error in installation may or may not result in a meaningful error message by the package manager.</span></span> <span data-ttu-id="01fc9-112">Чтобы проверить, удалось ли установить установку, получите и проверьте журналы установки с помощью:</span><span class="sxs-lookup"><span data-stu-id="01fc9-112">To verify if the installation succeeded, obtain and check the installation logs using:</span></span>

```bash
 sudo journalctl --no-pager | grep 'microsoft-mdatp' > installation.log
```

```bash
 grep 'postinstall end' installation.log
```

```Output
 microsoft-mdatp-installer[102243]: postinstall end [2020-03-26 07:04:43OURCE +0000] 102216
```

<span data-ttu-id="01fc9-113">Выход из предыдущей команды с правильной датой и временем установки указывает на успех.</span><span class="sxs-lookup"><span data-stu-id="01fc9-113">An output from the previous command with correct date and time of installation indicates success.</span></span>

<span data-ttu-id="01fc9-114">Кроме того, [проверьте конфигурацию клиента,](linux-install-manually.md#client-configuration) чтобы проверить состояние продукта и обнаружить текстовый файл EICAR.</span><span class="sxs-lookup"><span data-stu-id="01fc9-114">Also check the [Client configuration](linux-install-manually.md#client-configuration) to verify the health of the product and detect the EICAR text file.</span></span>

## <a name="make-sure-you-have-the-correct-package"></a><span data-ttu-id="01fc9-115">Убедитесь, что у вас есть правильный пакет</span><span class="sxs-lookup"><span data-stu-id="01fc9-115">Make sure you have the correct package</span></span>

<span data-ttu-id="01fc9-116">Обратите внимание, что пакет, который вы устанавливаете, соответствует распределению и версии хостов.</span><span class="sxs-lookup"><span data-stu-id="01fc9-116">Please mind that the package you are installing is matching the host distribution and version.</span></span>

| <span data-ttu-id="01fc9-117">package</span><span class="sxs-lookup"><span data-stu-id="01fc9-117">package</span></span>                       | <span data-ttu-id="01fc9-118">распространение</span><span class="sxs-lookup"><span data-stu-id="01fc9-118">distribution</span></span>                             |
|-------------------------------|------------------------------------------|
| <span data-ttu-id="01fc9-119">mdatp-rhel8. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="01fc9-119">mdatp-rhel8.Linux.x86_64.rpm</span></span>  | <span data-ttu-id="01fc9-120">Oracle, RHEL и CentOS 8.x</span><span class="sxs-lookup"><span data-stu-id="01fc9-120">Oracle, RHEL and CentOS 8.x</span></span>              |
| <span data-ttu-id="01fc9-121">mdatp-sles12. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="01fc9-121">mdatp-sles12.Linux.x86_64.rpm</span></span> | <span data-ttu-id="01fc9-122">SuSE Linux Enterprise Server 12.x</span><span class="sxs-lookup"><span data-stu-id="01fc9-122">SuSE Linux Enterprise Server 12.x</span></span>        |
| <span data-ttu-id="01fc9-123">mdatp-sles15. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="01fc9-123">mdatp-sles15.Linux.x86_64.rpm</span></span> | <span data-ttu-id="01fc9-124">SuSE Linux Enterprise Server 15.x</span><span class="sxs-lookup"><span data-stu-id="01fc9-124">SuSE Linux Enterprise Server 15.x</span></span>        |
| <span data-ttu-id="01fc9-125">mdatp. Linux.x86_64.rpm</span><span class="sxs-lookup"><span data-stu-id="01fc9-125">mdatp.Linux.x86_64.rpm</span></span>        | <span data-ttu-id="01fc9-126">Oracle, RHEL и CentOS 7.x</span><span class="sxs-lookup"><span data-stu-id="01fc9-126">Oracle, RHEL and CentOS 7.x</span></span>              |
| <span data-ttu-id="01fc9-127">mdatp. Linux.x86_64.deb</span><span class="sxs-lookup"><span data-stu-id="01fc9-127">mdatp.Linux.x86_64.deb</span></span>        | <span data-ttu-id="01fc9-128">Debian и Ubuntu 16.04, 18.04 и 20.04</span><span class="sxs-lookup"><span data-stu-id="01fc9-128">Debian and Ubuntu 16.04, 18.04 and 20.04</span></span> |

<span data-ttu-id="01fc9-129">Для [ручного развертывания](linux-install-manually.md)убедитесь, что выбран правильный дистро и версия.</span><span class="sxs-lookup"><span data-stu-id="01fc9-129">For [manual deployment](linux-install-manually.md), make sure the correct distro and version had been chosen.</span></span>

## <a name="installation-failed"></a><span data-ttu-id="01fc9-130">Сбой установки</span><span class="sxs-lookup"><span data-stu-id="01fc9-130">Installation failed</span></span>

<span data-ttu-id="01fc9-131">Проверьте, запущена ли служба mdatp:</span><span class="sxs-lookup"><span data-stu-id="01fc9-131">Check if the mdatp service is running:</span></span>

```bash
systemctl status mdatp
```

```Output
 ● mdatp.service - Microsoft Defender for Endpoint
   Loaded: loaded (/lib/systemd/system/mdatp.service; enabled; vendor preset: enabled)
   Active: active (running) since Thu 2020-03-26 10:37:30 IST; 23h ago
 Main PID: 1966 (wdavdaemon)
    Tasks: 105 (limit: 4915)
   CGroup: /system.slice/mdatp.service
           ├─1966 /opt/microsoft/mdatp/sbin/wdavdaemon
           ├─1967 /opt/microsoft/mdatp/sbin/wdavdaemon
           └─1968 /opt/microsoft/mdatp/sbin/wdavdaemon
 ```

## <a name="steps-to-troubleshoot-if-mdatp-service-isnt-running"></a><span data-ttu-id="01fc9-132">Действия по устранению неполадок, если служба mdatp не запущена</span><span class="sxs-lookup"><span data-stu-id="01fc9-132">Steps to troubleshoot if mdatp service isn't running</span></span>

1. <span data-ttu-id="01fc9-133">Проверьте, существует ли пользователь "mdatp":</span><span class="sxs-lookup"><span data-stu-id="01fc9-133">Check if "mdatp" user exists:</span></span>

    ```bash
    id "mdatp"
    ```

    <span data-ttu-id="01fc9-134">Если нет вывода, запустите</span><span class="sxs-lookup"><span data-stu-id="01fc9-134">If there’s no output, run</span></span>

    ```bash
    sudo useradd --system --no-create-home --user-group --shell /usr/sbin/nologin mdatp
    ```

2. <span data-ttu-id="01fc9-135">Попробуйте включить и перезапустить службу с помощью:</span><span class="sxs-lookup"><span data-stu-id="01fc9-135">Try enabling and restarting the service using:</span></span>

    ```bash
    sudo systemctl enable mdatp
    ```

    ```bash
    sudo systemctl restart mdatp
    ```

3. <span data-ttu-id="01fc9-136">Если mdatp.service не найден при запуске предыдущей команды, запустите:</span><span class="sxs-lookup"><span data-stu-id="01fc9-136">If mdatp.service isn't found upon running the previous command, run:</span></span>

    ```bash
    sudo cp /opt/microsoft/mdatp/conf/mdatp.service <systemd_path>
    ```

    <span data-ttu-id="01fc9-137">где `<systemd_path>` для `/lib/systemd/system` дистрибутивов Ubuntu и Debian, а также для `/usr/lib/systemd/system` Rhel, CentOS, Oracle и SLES.</span><span class="sxs-lookup"><span data-stu-id="01fc9-137">where `<systemd_path>` is `/lib/systemd/system` for Ubuntu and Debian distributions and `/usr/lib/systemd/system` for Rhel, CentOS, Oracle and SLES.</span></span>
   <span data-ttu-id="01fc9-138">Затем повторно повторяем шаг 2.</span><span class="sxs-lookup"><span data-stu-id="01fc9-138">Then rerun step 2.</span></span>

4. <span data-ttu-id="01fc9-139">Если вышеперечисленные действия не работают, проверьте, установлен ли SELinux в режиме принудительного действия.</span><span class="sxs-lookup"><span data-stu-id="01fc9-139">If the above steps don’t work, check if SELinux is installed and in enforcing mode.</span></span> <span data-ttu-id="01fc9-140">Если это так, попробуйте установить его в разрешительном (предпочтительно) или отключенном режиме.</span><span class="sxs-lookup"><span data-stu-id="01fc9-140">If so, try setting it to permissive (preferably) or disabled mode.</span></span> <span data-ttu-id="01fc9-141">Это можно сделать, задав параметр `SELINUX` "допустимый" или "отключенный" в файле, а затем `/etc/selinux/config` перезагружается.</span><span class="sxs-lookup"><span data-stu-id="01fc9-141">It can be done by setting the parameter `SELINUX` to "permissive" or "disabled" in `/etc/selinux/config` file, followed by reboot.</span></span> <span data-ttu-id="01fc9-142">Дополнительные сведения ознакомьтесь с man-page selinux.</span><span class="sxs-lookup"><span data-stu-id="01fc9-142">Check the man-page of selinux for more details.</span></span>
<span data-ttu-id="01fc9-143">Теперь попробуйте перезапустить службу mdatp с помощью шага 2.</span><span class="sxs-lookup"><span data-stu-id="01fc9-143">Now try restarting the mdatp service using step 2.</span></span> <span data-ttu-id="01fc9-144">Немедленно измените конфигурацию, хотя по соображениям безопасности после ее перезагрузки и перезагрузки.</span><span class="sxs-lookup"><span data-stu-id="01fc9-144">Revert the configuration change immediately though for security reasons after trying it and reboot.</span></span>

5. <span data-ttu-id="01fc9-145">Если `/opt` каталог является символической ссылкой, создайте крепление привязки `/opt/microsoft` для .</span><span class="sxs-lookup"><span data-stu-id="01fc9-145">If `/opt` directory is a symbolic link, create a bind mount for `/opt/microsoft`.</span></span>

6. <span data-ttu-id="01fc9-146">Убедитесь, что у деймона есть исполняемое разрешение.</span><span class="sxs-lookup"><span data-stu-id="01fc9-146">Ensure that the daemon has executable permission.</span></span>

    ```bash
    ls -l /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    ```Output
    -rwxr-xr-x 2 root root 15502160 Mar  3 04:47 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="01fc9-147">Если у деймона нет исполняемых разрешений, сделайте его исполняемым с помощью:</span><span class="sxs-lookup"><span data-stu-id="01fc9-147">If the daemon doesn't have executable permissions, make it executable using:</span></span>

    ```bash
    sudo chmod 0755 /opt/microsoft/mdatp/sbin/wdavdaemon
    ```

    <span data-ttu-id="01fc9-148">и повторное запуск шага 2.</span><span class="sxs-lookup"><span data-stu-id="01fc9-148">and retry running step 2.</span></span>

7. <span data-ttu-id="01fc9-149">Убедитесь, что файловая система, содержащая wdavdaemon, не установлена с помощью "noexec".</span><span class="sxs-lookup"><span data-stu-id="01fc9-149">Ensure that the file system containing wdavdaemon isn't mounted with "noexec".</span></span>

## <a name="if-mdatp-service-is-running-but-eicar-text-file-detection-doesnt-work"></a><span data-ttu-id="01fc9-150">Если служба mdatp запущена, но обнаружение текстовых файлов EICAR не работает</span><span class="sxs-lookup"><span data-stu-id="01fc9-150">If mdatp service is running, but EICAR text file detection doesn't work</span></span>

1. <span data-ttu-id="01fc9-151">Проверьте тип файловой системы с помощью:</span><span class="sxs-lookup"><span data-stu-id="01fc9-151">Check the file system type using:</span></span>

    ```bash
    findmnt -T <path_of_EICAR_file>
    ```

    <span data-ttu-id="01fc9-152">В настоящее время поддерживаемые файловые системы для действий в доступе перечислены [здесь.](microsoft-defender-endpoint-linux.md#system-requirements)</span><span class="sxs-lookup"><span data-stu-id="01fc9-152">Currently supported file systems for on-access activity are listed [here](microsoft-defender-endpoint-linux.md#system-requirements).</span></span> <span data-ttu-id="01fc9-153">Любые файлы вне этих файлов не будут отсканированы.</span><span class="sxs-lookup"><span data-stu-id="01fc9-153">Any files outside these file systems won't be scanned.</span></span>

## <a name="command-line-tool-mdatp-isnt-working"></a><span data-ttu-id="01fc9-154">Средство командной строки "mdatp" не работает</span><span class="sxs-lookup"><span data-stu-id="01fc9-154">Command-line tool “mdatp” isn't working</span></span>

1. <span data-ttu-id="01fc9-155">Если при запуске средства командной `mdatp` строки будет допущена `command not found` ошибка, запустите следующую команду:</span><span class="sxs-lookup"><span data-stu-id="01fc9-155">If running the command-line tool `mdatp` gives an error `command not found`, run the following command:</span></span>

    ```bash
    sudo ln -sf /opt/microsoft/mdatp/sbin/wdavdaemonclient /usr/bin/mdatp
    ```

    <span data-ttu-id="01fc9-156">и попробуйте еще раз.</span><span class="sxs-lookup"><span data-stu-id="01fc9-156">and try again.</span></span>

    <span data-ttu-id="01fc9-157">Если ни один из вышеуказанных действий не поможет, соберйте диагностические журналы:</span><span class="sxs-lookup"><span data-stu-id="01fc9-157">If none of the above steps help, collect the diagnostic logs:</span></span>

    ```bash
    sudo mdatp diagnostic create
    ```

    ```Output
    Diagnostic file created: <path to file>
    ```

    <span data-ttu-id="01fc9-158">Путь к почтовому файлу, содержащий журналы, будет отображаться в качестве вывода.</span><span class="sxs-lookup"><span data-stu-id="01fc9-158">Path to a zip file that contains the logs will be displayed as an output.</span></span> <span data-ttu-id="01fc9-159">С помощью этих журналов можно связаться с нашими службами поддержки клиентов.</span><span class="sxs-lookup"><span data-stu-id="01fc9-159">Reach out to our customer support with these logs.</span></span>
