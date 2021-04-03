---
title: Microsoft Defender для конечной точки для Linux
ms.reviewer: ''
description: Описывает установку и использование ATP Microsoft Defender для Linux.
keywords: Microsoft, defender, atp, linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: cc2f5be700395f6d88c05481d74501f4d9d92b76
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/01/2021
ms.locfileid: "51500673"
---
# <a name="microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="94c7b-104">Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="94c7b-104">Microsoft Defender for Endpoint for Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="94c7b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="94c7b-105">**Applies to:**</span></span>
- [<span data-ttu-id="94c7b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="94c7b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="94c7b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="94c7b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="94c7b-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="94c7b-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="94c7b-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="94c7b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="94c7b-110">В этом разделе описывается установка, настройка, обновление и использование Microsoft Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="94c7b-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint for Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="94c7b-111">Запуск других сторонних продуктов защиты конечной точки наряду с Microsoft Defender для конечной точки для Linux может привести к проблемам с производительностью и непредсказуемым побочным эффектам.</span><span class="sxs-lookup"><span data-stu-id="94c7b-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint for Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="94c7b-112">Если защита конечной точки от Microsoft является абсолютным требованием в вашей среде, вы можете безопасно использовать функции Defender для конечной точки для Linux EDR после настройки функции антивируса для запуска в пассивном [режиме.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="94c7b-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint for Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="94c7b-113">Установка Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="94c7b-113">How to install Microsoft Defender for Endpoint for Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="94c7b-114">Необходимые условия</span><span class="sxs-lookup"><span data-stu-id="94c7b-114">Prerequisites</span></span>

- <span data-ttu-id="94c7b-115">Доступ к порталу Центра безопасности Защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="94c7b-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="94c7b-116">Дистрибуция Linux с [помощью системного системного](https://systemd.io/) диспетчера</span><span class="sxs-lookup"><span data-stu-id="94c7b-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="94c7b-117">Опыт начального уровня в скриптах Linux и BASH</span><span class="sxs-lookup"><span data-stu-id="94c7b-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="94c7b-118">Административные привилегии на устройстве (в случае ручного развертывания)</span><span class="sxs-lookup"><span data-stu-id="94c7b-118">Administrative privileges on the device (in case of manual deployment)</span></span>

### <a name="installation-instructions"></a><span data-ttu-id="94c7b-119">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="94c7b-119">Installation instructions</span></span>

<span data-ttu-id="94c7b-120">Существует несколько методов и средств развертывания, которые можно использовать для установки и настройки Microsoft Defender для конечной точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="94c7b-120">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint for Linux.</span></span>

<span data-ttu-id="94c7b-121">В общем, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="94c7b-121">In general you need to take the following steps:</span></span>

- <span data-ttu-id="94c7b-122">Убедитесь, что у вас есть подписка Microsoft Defender для конечной точки и доступ к порталу [Microsoft Defender для конечных точек.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="94c7b-122">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="94c7b-123">Развертывание Microsoft Defender для конечной точки для Linux с помощью одного из следующих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="94c7b-123">Deploy Microsoft Defender for Endpoint for Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="94c7b-124">Средство командной строки:</span><span class="sxs-lookup"><span data-stu-id="94c7b-124">The command-line tool:</span></span>
    - [<span data-ttu-id="94c7b-125">Ручное развертывание</span><span class="sxs-lookup"><span data-stu-id="94c7b-125">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="94c7b-126">Средства управления сторонними средствами управления:</span><span class="sxs-lookup"><span data-stu-id="94c7b-126">Third-party management tools:</span></span>
    - [<span data-ttu-id="94c7b-127">Развертывание с помощью средства управления конфигурацией Puppet</span><span class="sxs-lookup"><span data-stu-id="94c7b-127">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="94c7b-128">Развертывание с помощью средства управления конфигурацией Ansible</span><span class="sxs-lookup"><span data-stu-id="94c7b-128">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="94c7b-129">Если вы испытываете какие-либо сбои в установке, обратитесь к устранению неполадок установки в [Microsoft Defender для конечной точки для Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="94c7b-129">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint for Linux](linux-support-install.md).</span></span>

### <a name="system-requirements"></a><span data-ttu-id="94c7b-130">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="94c7b-130">System requirements</span></span>

- <span data-ttu-id="94c7b-131">Поддерживаемые дистрибутивы и версии серверов Linux:</span><span class="sxs-lookup"><span data-stu-id="94c7b-131">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="94c7b-132">Red Hat Enterprise Linux 7.2 или более</span><span class="sxs-lookup"><span data-stu-id="94c7b-132">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="94c7b-133">CentOS 7.2 или более</span><span class="sxs-lookup"><span data-stu-id="94c7b-133">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="94c7b-134">Ubuntu 16.04 LTS или более высокий LTS</span><span class="sxs-lookup"><span data-stu-id="94c7b-134">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="94c7b-135">Debian 9 или более</span><span class="sxs-lookup"><span data-stu-id="94c7b-135">Debian 9 or higher</span></span>
  - <span data-ttu-id="94c7b-136">SUSE Linux Enterprise Server 12 или более</span><span class="sxs-lookup"><span data-stu-id="94c7b-136">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="94c7b-137">Oracle Linux 7.2 или более</span><span class="sxs-lookup"><span data-stu-id="94c7b-137">Oracle Linux 7.2 or higher</span></span>

- <span data-ttu-id="94c7b-138">Минимальная версия ядра 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="94c7b-138">Minimum kernel version 3.10.0-327</span></span>
- <span data-ttu-id="94c7b-139">Параметр `fanotify` ядра должен быть включен</span><span class="sxs-lookup"><span data-stu-id="94c7b-139">The `fanotify` kernel option must be enabled</span></span>
  > [!CAUTION]
  > <span data-ttu-id="94c7b-140">Запуск Defender для конечной точки для Linux бок о бок с другими решениями безопасности на основе не `fanotify` поддерживается.</span><span class="sxs-lookup"><span data-stu-id="94c7b-140">Running Defender for Endpoint for Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="94c7b-141">Это может привести к непредсказуемым результатам, в том числе к висячим операционной системе.</span><span class="sxs-lookup"><span data-stu-id="94c7b-141">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="94c7b-142">Пространство диска: 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="94c7b-142">Disk space: 1GB</span></span>
- <span data-ttu-id="94c7b-143">/opt/microsoft/mdatp/sbin/wdavdaemon требует исполняемого разрешения.</span><span class="sxs-lookup"><span data-stu-id="94c7b-143">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="94c7b-144">Дополнительные сведения см. в рублях "Убедитесь, что у daemon есть исполняемые разрешения" в выпуске проблем с установкой неполадок для [Microsoft Defender ATP для Linux.](/microsoft-365/security/defender-endpoint/linux-support-install)</span><span class="sxs-lookup"><span data-stu-id="94c7b-144">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender ATP for Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>
- <span data-ttu-id="94c7b-145">Память: 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="94c7b-145">Memory: 1GB</span></span>
    > [!NOTE]
    > <span data-ttu-id="94c7b-146">Убедитесь, что у вас есть свободное пространство диска в /var.</span><span class="sxs-lookup"><span data-stu-id="94c7b-146">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="94c7b-147">В настоящее время решение обеспечивает защиту в режиме реального времени для следующих типов файловой системы:</span><span class="sxs-lookup"><span data-stu-id="94c7b-147">The solution currently provides real-time protection for the following file system types:</span></span>

  - `btrfs`
  - `ecryptfs`
  - `ext2`
  - `ext3`
  - `ext4`
  - `fuse`
  - `fuseblk`
  - `jfs`
  - `nfs`
  - `overlay`
  - `ramfs`
  - `reiserfs`
  - `tmpfs`
  - `udf`
  - `vfat`
  - `xfs`

<span data-ttu-id="94c7b-148">После включения службы может потребоваться настроить сеть или брандмауэр, чтобы разрешить исходящие подключения между ней и конечными точками.</span><span class="sxs-lookup"><span data-stu-id="94c7b-148">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="94c7b-149">Необходимо включить структуру `auditd` аудита ().</span><span class="sxs-lookup"><span data-stu-id="94c7b-149">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="94c7b-150">События системы, запечатленные правилами, добавлены в (s) и могут повлиять на аудит хостов `/etc/audit/rules.d/` `audit.log` и коллекцию upstream.</span><span class="sxs-lookup"><span data-stu-id="94c7b-150">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="94c7b-151">События, добавленные Microsoft Defender для конечной точки для Linux, будут помечены `mdatp` ключом.</span><span class="sxs-lookup"><span data-stu-id="94c7b-151">Events added by Microsoft Defender for Endpoint for Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="94c7b-152">Сетевые соединения.</span><span class="sxs-lookup"><span data-stu-id="94c7b-152">Network connections</span></span>

<span data-ttu-id="94c7b-153">В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть.</span><span class="sxs-lookup"><span data-stu-id="94c7b-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="94c7b-154">Необходимо убедиться, что нет правил фильтрации брандмауэра или сети, которые бы отказывали в доступе к этим URL-адресам.</span><span class="sxs-lookup"><span data-stu-id="94c7b-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="94c7b-155">Если они есть, может потребоваться создать правило разрешить специально для них. </span><span class="sxs-lookup"><span data-stu-id="94c7b-155">If there are, you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="94c7b-156">**Таблица списка доменов**</span><span class="sxs-lookup"><span data-stu-id="94c7b-156">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="94c7b-157">**Описание**</span><span class="sxs-lookup"><span data-stu-id="94c7b-157">**Description**</span></span>|
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | <span data-ttu-id="94c7b-159">Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС.</span><span class="sxs-lookup"><span data-stu-id="94c7b-159">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="94c7b-160">Скачайте таблицу здесь.</span><span class="sxs-lookup"><span data-stu-id="94c7b-160">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="94c7b-161">Более конкретный список URL-адресов см. в [перечне Настройка параметров](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)прокси-сервера и подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="94c7b-161">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="94c7b-162">Defender for Endpoint может открыть прокси-сервер с помощью следующих методов обнаружения:</span><span class="sxs-lookup"><span data-stu-id="94c7b-162">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="94c7b-163">Прозрачный прокси</span><span class="sxs-lookup"><span data-stu-id="94c7b-163">Transparent proxy</span></span>
- <span data-ttu-id="94c7b-164">Ручная статическая конфигурация прокси</span><span class="sxs-lookup"><span data-stu-id="94c7b-164">Manual static proxy configuration</span></span>

<span data-ttu-id="94c7b-165">Если прокси-сервер или брандмауэр блокирует анонимный трафик, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="94c7b-165">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="94c7b-166">Для прозрачных прокси-прокси не требуется дополнительная конфигурация для Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="94c7b-166">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="94c7b-167">Для статического прокси-сервера выполните действия в [ручной статической конфигурации прокси.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="94c7b-167">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="94c7b-168">Прокси-панели PAC, WPAD и прокси-устройства с проверкой подлинности не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="94c7b-168">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="94c7b-169">Убедитесь, что используется только статичный прокси или прозрачный прокси.</span><span class="sxs-lookup"><span data-stu-id="94c7b-169">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="94c7b-170">Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="94c7b-170">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="94c7b-171">Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Defender for Endpoint для Linux в соответствующие URL-адреса без перехвата.</span><span class="sxs-lookup"><span data-stu-id="94c7b-171">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint for Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="94c7b-172">Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.</span><span class="sxs-lookup"><span data-stu-id="94c7b-172">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="94c7b-173">О действиях по устранению неполадок см. в выпуске Устранение неполадок с облачными подключениями [для Microsoft Defender для конечной точки для Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="94c7b-173">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint for Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="94c7b-174">Обновление Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="94c7b-174">How to update Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="94c7b-175">Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.</span><span class="sxs-lookup"><span data-stu-id="94c7b-175">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="94c7b-176">Чтобы обновить Microsoft Defender для конечной точки для Linux, обратитесь к развертыванию обновлений [для Microsoft Defender для конечной](linux-updates.md)точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="94c7b-176">To update Microsoft Defender for Endpoint for Linux, refer to [Deploy updates for Microsoft Defender for Endpoint for Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-for-linux"></a><span data-ttu-id="94c7b-177">Настройка Microsoft Defender для конечной точки для Linux</span><span class="sxs-lookup"><span data-stu-id="94c7b-177">How to configure Microsoft Defender for Endpoint for Linux</span></span>

<span data-ttu-id="94c7b-178">Инструкции по настройке продукта в корпоративных средах доступны в наборе предпочтений [для Microsoft Defender для конечной](linux-preferences.md)точки для Linux.</span><span class="sxs-lookup"><span data-stu-id="94c7b-178">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint for Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="94c7b-179">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="94c7b-179">Resources</span></span>

- <span data-ttu-id="94c7b-180">Дополнительные сведения о журнале, uninstalling или других темах см. в [разделе Ресурсы.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="94c7b-180">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
