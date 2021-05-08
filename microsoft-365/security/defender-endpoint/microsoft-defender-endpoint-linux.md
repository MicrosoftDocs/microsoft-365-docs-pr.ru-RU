---
title: Microsoft Defender для конечной точки в Linux
ms.reviewer: ''
description: Описывает, как установить и использовать Microsoft Defender для конечной точки на Linux.
keywords: Microsoft, defender, Microsoft Defender for Endpoint, Linux, installation, deploy, uninstallation, puppet, ansible, linux, redhat, ubuntu, debian, sles, suse, centos
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
ms.openlocfilehash: 0e09a313b512135785050abd5aa61bb9576ce1d8
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274944"
---
# <a name="microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="b09c2-104">Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="b09c2-104">Microsoft Defender for Endpoint on Linux</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b09c2-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b09c2-105">**Applies to:**</span></span>
- [<span data-ttu-id="b09c2-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b09c2-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b09c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b09c2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b09c2-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b09c2-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b09c2-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b09c2-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b09c2-110">В этом разделе описывается установка, настройка, обновление и использование Microsoft Defender для конечной точки в Linux.</span><span class="sxs-lookup"><span data-stu-id="b09c2-110">This topic describes how to install, configure, update, and use Microsoft Defender for Endpoint on Linux.</span></span>

> [!CAUTION]
> <span data-ttu-id="b09c2-111">Запуск других сторонних продуктов защиты конечной точки наряду с Microsoft Defender для конечной точки на Linux может привести к проблемам с производительностью и непредсказуемым побочным эффектам.</span><span class="sxs-lookup"><span data-stu-id="b09c2-111">Running other third-party endpoint protection products alongside Microsoft Defender for Endpoint on Linux is likely to lead to performance problems and unpredictable side effects.</span></span> <span data-ttu-id="b09c2-112">Если защита конечной точки не microsoft является абсолютным требованием в вашей среде, вы можете безопасно использовать функции Defender для конечной точки на Linux EDR после настройки функции антивируса для запуска в пассивном [режиме.](linux-preferences.md#enable--disable-passive-mode)</span><span class="sxs-lookup"><span data-stu-id="b09c2-112">If non-Microsoft endpoint protection is an absolute requirement in your environment, you can still safely take advantage of Defender for Endpoint on Linux EDR functionality after configuring the antivirus functionality to run in [Passive mode](linux-preferences.md#enable--disable-passive-mode).</span></span>

## <a name="how-to-install-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="b09c2-113">Установка Microsoft Defender для конечной точки на Linux</span><span class="sxs-lookup"><span data-stu-id="b09c2-113">How to install Microsoft Defender for Endpoint on Linux</span></span>

### <a name="prerequisites"></a><span data-ttu-id="b09c2-114">Предварительные условия</span><span class="sxs-lookup"><span data-stu-id="b09c2-114">Prerequisites</span></span>

- <span data-ttu-id="b09c2-115">Доступ к порталу Центр безопасности в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b09c2-115">Access to the Microsoft Defender Security Center portal</span></span>
- <span data-ttu-id="b09c2-116">Дистрибуция Linux с [помощью системного системного](https://systemd.io/) диспетчера</span><span class="sxs-lookup"><span data-stu-id="b09c2-116">Linux distribution using the [systemd](https://systemd.io/) system manager</span></span>
- <span data-ttu-id="b09c2-117">Опыт начального уровня в скриптах Linux и BASH</span><span class="sxs-lookup"><span data-stu-id="b09c2-117">Beginner-level experience in Linux and BASH scripting</span></span>
- <span data-ttu-id="b09c2-118">Административные привилегии на устройстве (в случае ручного развертывания)</span><span class="sxs-lookup"><span data-stu-id="b09c2-118">Administrative privileges on the device (in case of manual deployment)</span></span>

> [!NOTE]
>  <span data-ttu-id="b09c2-119">Microsoft Defender для конечной точки на агенте Linux не зависит от [агента OMS.](/azure/azure-monitor/agents/agents-overview#log-analytics-agent)</span><span class="sxs-lookup"><span data-stu-id="b09c2-119">Microsoft Defender for Endpoint on Linux agent is independent from [OMS agent](/azure/azure-monitor/agents/agents-overview#log-analytics-agent).</span></span> <span data-ttu-id="b09c2-120">Microsoft Defender для Конечной точки использует собственный независимый конвейер телеметрии.</span><span class="sxs-lookup"><span data-stu-id="b09c2-120">Microsoft Defender for Endpoint relies on its own independent telemetry pipeline.</span></span>
> 
> <span data-ttu-id="b09c2-121">Microsoft Defender для конечной точки в Linux еще не интегрирована в Центр безопасности Azure.</span><span class="sxs-lookup"><span data-stu-id="b09c2-121">Microsoft Defender for Endpoint on Linux is not yet integrated into Azure Security Center.</span></span>



### <a name="installation-instructions"></a><span data-ttu-id="b09c2-122">Инструкции по установке</span><span class="sxs-lookup"><span data-stu-id="b09c2-122">Installation instructions</span></span>

<span data-ttu-id="b09c2-123">Существует несколько методов и средств развертывания, которые можно использовать для установки и настройки Microsoft Defender для конечной точки на Linux.</span><span class="sxs-lookup"><span data-stu-id="b09c2-123">There are several methods and deployment tools that you can use to install and configure Microsoft Defender for Endpoint on Linux.</span></span>

<span data-ttu-id="b09c2-124">В общем, необходимо предпринять следующие действия:</span><span class="sxs-lookup"><span data-stu-id="b09c2-124">In general you need to take the following steps:</span></span>

- <span data-ttu-id="b09c2-125">Убедитесь, что у вас есть подписка Microsoft Defender для конечной точки и доступ к порталу [Microsoft Defender для конечных точек.](microsoft-defender-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="b09c2-125">Ensure that you have a Microsoft Defender for Endpoint subscription, and that you have access to the [Microsoft Defender for Endpoint portal](microsoft-defender-security-center.md).</span></span>
- <span data-ttu-id="b09c2-126">Развертывание Microsoft Defender для конечной точки на Linux с помощью одного из следующих методов развертывания:</span><span class="sxs-lookup"><span data-stu-id="b09c2-126">Deploy Microsoft Defender for Endpoint on Linux using one of the following deployment methods:</span></span>
  - <span data-ttu-id="b09c2-127">Средство командной строки:</span><span class="sxs-lookup"><span data-stu-id="b09c2-127">The command-line tool:</span></span>
    - [<span data-ttu-id="b09c2-128">Ручное развертывание</span><span class="sxs-lookup"><span data-stu-id="b09c2-128">Manual deployment</span></span>](linux-install-manually.md)
  - <span data-ttu-id="b09c2-129">Средства управления сторонними средствами управления:</span><span class="sxs-lookup"><span data-stu-id="b09c2-129">Third-party management tools:</span></span>
    - [<span data-ttu-id="b09c2-130">Развертывание с помощью средства управления конфигурацией Puppet</span><span class="sxs-lookup"><span data-stu-id="b09c2-130">Deploy using Puppet configuration management tool</span></span>](linux-install-with-puppet.md)
    - [<span data-ttu-id="b09c2-131">Развертывание с помощью средства управления конфигурацией Ansible</span><span class="sxs-lookup"><span data-stu-id="b09c2-131">Deploy using Ansible configuration management tool</span></span>](linux-install-with-ansible.md)

<span data-ttu-id="b09c2-132">Если вы испытываете какие-либо сбои в установке, обратитесь к устранению неполадок установки в [Microsoft Defender для конечной точки на Linux](linux-support-install.md).</span><span class="sxs-lookup"><span data-stu-id="b09c2-132">If you experience any installation failures, refer to [Troubleshooting installation failures in Microsoft Defender for Endpoint on Linux](linux-support-install.md).</span></span>



### <a name="system-requirements"></a><span data-ttu-id="b09c2-133">Требования к системе</span><span class="sxs-lookup"><span data-stu-id="b09c2-133">System requirements</span></span>

- <span data-ttu-id="b09c2-134">Поддерживаемые дистрибутивы и версии серверов Linux:</span><span class="sxs-lookup"><span data-stu-id="b09c2-134">Supported Linux server distributions and versions:</span></span>

  - <span data-ttu-id="b09c2-135">Red Hat Enterprise Linux 7.2 или более</span><span class="sxs-lookup"><span data-stu-id="b09c2-135">Red Hat Enterprise Linux 7.2 or higher</span></span>
  - <span data-ttu-id="b09c2-136">CentOS 7.2 или более</span><span class="sxs-lookup"><span data-stu-id="b09c2-136">CentOS 7.2 or higher</span></span>
  - <span data-ttu-id="b09c2-137">Ubuntu 16.04 LTS или более высокий LTS</span><span class="sxs-lookup"><span data-stu-id="b09c2-137">Ubuntu 16.04 LTS or higher LTS</span></span>
  - <span data-ttu-id="b09c2-138">Debian 9 или более</span><span class="sxs-lookup"><span data-stu-id="b09c2-138">Debian 9 or higher</span></span>
  - <span data-ttu-id="b09c2-139">SUSE Linux Enterprise Server 12 или более</span><span class="sxs-lookup"><span data-stu-id="b09c2-139">SUSE Linux Enterprise Server 12 or higher</span></span>
  - <span data-ttu-id="b09c2-140">Oracle Linux 7.2 или более</span><span class="sxs-lookup"><span data-stu-id="b09c2-140">Oracle Linux 7.2 or higher</span></span>

    > [!NOTE]
    > <span data-ttu-id="b09c2-141">Дистрибутивы и версии, не указанные в явном списке, не поддерживаются (даже если они получены из официально поддерживаемых дистрибутивов).</span><span class="sxs-lookup"><span data-stu-id="b09c2-141">Distributions and version that are not explicitly listed are unsupported (even if they are derived from the officially supported distributions).</span></span>


- <span data-ttu-id="b09c2-142">Минимальная версия ядра 3.10.0-327</span><span class="sxs-lookup"><span data-stu-id="b09c2-142">Minimum kernel version 3.10.0-327</span></span>

- <span data-ttu-id="b09c2-143">Параметр `fanotify` ядра должен быть включен</span><span class="sxs-lookup"><span data-stu-id="b09c2-143">The `fanotify` kernel option must be enabled</span></span>

  > [!CAUTION]
  > <span data-ttu-id="b09c2-144">Запуск Defender для конечной точки на Linux бок о бок с другими решениями безопасности на основе данных `fanotify` не поддерживается.</span><span class="sxs-lookup"><span data-stu-id="b09c2-144">Running Defender for Endpoint on Linux side by side with other `fanotify`-based security solutions is not supported.</span></span> <span data-ttu-id="b09c2-145">Это может привести к непредсказуемым результатам, в том числе к висячим операционной системе.</span><span class="sxs-lookup"><span data-stu-id="b09c2-145">It can lead to unpredictable results, including hanging the operating system.</span></span>

- <span data-ttu-id="b09c2-146">Пространство диска: 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="b09c2-146">Disk space: 1 GB</span></span>

- <span data-ttu-id="b09c2-147">/opt/microsoft/mdatp/sbin/wdavdaemon требует исполняемого разрешения.</span><span class="sxs-lookup"><span data-stu-id="b09c2-147">/opt/microsoft/mdatp/sbin/wdavdaemon requires executable permission.</span></span> <span data-ttu-id="b09c2-148">Дополнительные сведения см. в рублях "Убедитесь, что у daemon есть исполняемые разрешения" в проблемах с установкой неполадок для [Microsoft Defender для конечной](/microsoft-365/security/defender-endpoint/linux-support-install)точки в Linux.</span><span class="sxs-lookup"><span data-stu-id="b09c2-148">For more information, see "Ensure that the daemon has executable permission" in [Troubleshoot installation issues for Microsoft Defender for Endpoint on Linux](/microsoft-365/security/defender-endpoint/linux-support-install).</span></span>

- <span data-ttu-id="b09c2-149">Память: 1 ГБ</span><span class="sxs-lookup"><span data-stu-id="b09c2-149">Memory: 1 GB</span></span>

    > [!NOTE]
    > <span data-ttu-id="b09c2-150">Убедитесь, что у вас есть свободное пространство диска в /var.</span><span class="sxs-lookup"><span data-stu-id="b09c2-150">Please make sure that you have free disk space in /var.</span></span>

- <span data-ttu-id="b09c2-151">В настоящее время решение обеспечивает защиту в режиме реального времени для следующих типов файловой системы:</span><span class="sxs-lookup"><span data-stu-id="b09c2-151">The solution currently provides real-time protection for the following file system types:</span></span>

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

<span data-ttu-id="b09c2-152">После включения службы может потребоваться настроить сеть или брандмауэр, чтобы разрешить исходящие подключения между ней и конечными точками.</span><span class="sxs-lookup"><span data-stu-id="b09c2-152">After you've enabled the service, you may need to configure your network or firewall to allow outbound connections between it and your endpoints.</span></span>

- <span data-ttu-id="b09c2-153">Необходимо включить структуру `auditd` аудита ().</span><span class="sxs-lookup"><span data-stu-id="b09c2-153">Audit framework (`auditd`) must be enabled.</span></span>
  > [!NOTE]
  > <span data-ttu-id="b09c2-154">События системы, запечатленные правилами, добавлены в (s) и могут повлиять на аудит хостов `/etc/audit/rules.d/` `audit.log` и коллекцию upstream.</span><span class="sxs-lookup"><span data-stu-id="b09c2-154">System events captured by rules added to `/etc/audit/rules.d/` will add to `audit.log`(s) and might affect host auditing and upstream collection.</span></span> <span data-ttu-id="b09c2-155">События, добавленные Microsoft Defender для конечной точки в Linux, будут помечены `mdatp` ключом.</span><span class="sxs-lookup"><span data-stu-id="b09c2-155">Events added by Microsoft Defender for Endpoint on Linux will be tagged with `mdatp` key.</span></span>

### <a name="network-connections"></a><span data-ttu-id="b09c2-156">Сетевые соединения.</span><span class="sxs-lookup"><span data-stu-id="b09c2-156">Network connections</span></span>

<span data-ttu-id="b09c2-157">В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть.</span><span class="sxs-lookup"><span data-stu-id="b09c2-157">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="b09c2-158">Необходимо убедиться, что нет правил фильтрации брандмауэра или сети, которые бы отказывали в доступе к этим URL-адресам.</span><span class="sxs-lookup"><span data-stu-id="b09c2-158">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs.</span></span> <span data-ttu-id="b09c2-159">Если они есть, может потребоваться создать правило разрешить специально для них. </span><span class="sxs-lookup"><span data-stu-id="b09c2-159">If there are, you may need to create an *allow* rule specifically for them.</span></span>

| <span data-ttu-id="b09c2-160">Таблица списка доменов</span><span class="sxs-lookup"><span data-stu-id="b09c2-160">Spreadsheet of domains list</span></span> | <span data-ttu-id="b09c2-161">Описание</span><span class="sxs-lookup"><span data-stu-id="b09c2-161">Description</span></span> |
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | <span data-ttu-id="b09c2-163">Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС.</span><span class="sxs-lookup"><span data-stu-id="b09c2-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="b09c2-164">Скачайте таблицу здесь.</span><span class="sxs-lookup"><span data-stu-id="b09c2-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)

> [!NOTE]
> <span data-ttu-id="b09c2-165">Более конкретный список URL-адресов см. в [перечне Настройка параметров](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server)прокси-сервера и подключения к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b09c2-165">For a more specific URL list, see [Configure proxy and internet connectivity settings](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-proxy-internet#enable-access-to-microsoft-defender-atp-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="b09c2-166">Defender for Endpoint может открыть прокси-сервер с помощью следующих методов обнаружения:</span><span class="sxs-lookup"><span data-stu-id="b09c2-166">Defender for Endpoint can discover a proxy server by using the following discovery methods:</span></span>
- <span data-ttu-id="b09c2-167">Прозрачный прокси</span><span class="sxs-lookup"><span data-stu-id="b09c2-167">Transparent proxy</span></span>
- <span data-ttu-id="b09c2-168">Ручная статическая конфигурация прокси</span><span class="sxs-lookup"><span data-stu-id="b09c2-168">Manual static proxy configuration</span></span>

<span data-ttu-id="b09c2-169">Если прокси-сервер или брандмауэр блокирует анонимный трафик, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="b09c2-169">If a proxy or firewall is blocking anonymous traffic, make sure that anonymous traffic is permitted in the previously listed URLs.</span></span> <span data-ttu-id="b09c2-170">Для прозрачных прокси-прокси не требуется дополнительная конфигурация для Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b09c2-170">For transparent proxies, no additional configuration is needed for Defender for Endpoint.</span></span> <span data-ttu-id="b09c2-171">Для статического прокси-сервера выполните действия в [ручной статической конфигурации прокси.](linux-static-proxy-configuration.md)</span><span class="sxs-lookup"><span data-stu-id="b09c2-171">For static proxy, follow the steps in [Manual Static Proxy Configuration](linux-static-proxy-configuration.md).</span></span>

> [!WARNING]
> <span data-ttu-id="b09c2-172">Прокси-панели PAC, WPAD и прокси-устройства с проверкой подлинности не поддерживаются.</span><span class="sxs-lookup"><span data-stu-id="b09c2-172">PAC, WPAD, and authenticated proxies are not supported.</span></span> <span data-ttu-id="b09c2-173">Убедитесь, что используется только статичный прокси или прозрачный прокси.</span><span class="sxs-lookup"><span data-stu-id="b09c2-173">Ensure that only a static proxy or transparent proxy is being used.</span></span>
>
> <span data-ttu-id="b09c2-174">Проверка SSL и перехват прокси также не поддерживаются по соображениям безопасности.</span><span class="sxs-lookup"><span data-stu-id="b09c2-174">SSL inspection and intercepting proxies are also not supported for security reasons.</span></span> <span data-ttu-id="b09c2-175">Настройте исключение для проверки SSL и прокси-сервера, чтобы напрямую передавать данные из Defender для конечной точки на Linux в соответствующие URL-адреса без перехвата.</span><span class="sxs-lookup"><span data-stu-id="b09c2-175">Configure an exception for SSL inspection and your proxy server to directly pass through data from Defender for Endpoint on Linux to the relevant URLs without interception.</span></span> <span data-ttu-id="b09c2-176">Добавление сертификата перехвата в глобальный магазин не позволяет перехватывать.</span><span class="sxs-lookup"><span data-stu-id="b09c2-176">Adding your interception certificate to the global store will not allow for interception.</span></span>

<span data-ttu-id="b09c2-177">О действиях по устранению неполадок см. в выпуске Устранение неполадок с облачными подключениями [для Microsoft Defender для конечной точки в Linux.](linux-support-connectivity.md)</span><span class="sxs-lookup"><span data-stu-id="b09c2-177">For troubleshooting steps, see [Troubleshoot cloud connectivity issues for Microsoft Defender for Endpoint on Linux](linux-support-connectivity.md).</span></span>

## <a name="how-to-update-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="b09c2-178">Обновление Microsoft Defender для конечной точки в Linux</span><span class="sxs-lookup"><span data-stu-id="b09c2-178">How to update Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="b09c2-179">Корпорация Майкрософт регулярно публикует обновления программного обеспечения для повышения производительности, безопасности и предоставления новых функций.</span><span class="sxs-lookup"><span data-stu-id="b09c2-179">Microsoft regularly publishes software updates to improve performance, security, and to deliver new features.</span></span> <span data-ttu-id="b09c2-180">Чтобы обновить Microsoft Defender для конечной точки в Linux, обратитесь к развертыванию обновлений [для Microsoft Defender для конечной точки в Linux.](linux-updates.md)</span><span class="sxs-lookup"><span data-stu-id="b09c2-180">To update Microsoft Defender for Endpoint on Linux, refer to [Deploy updates for Microsoft Defender for Endpoint on Linux](linux-updates.md).</span></span>

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-linux"></a><span data-ttu-id="b09c2-181">Настройка Microsoft Defender для конечной точки на Linux</span><span class="sxs-lookup"><span data-stu-id="b09c2-181">How to configure Microsoft Defender for Endpoint on Linux</span></span>

<span data-ttu-id="b09c2-182">Инструкции по настройке продукта в корпоративных средах доступны в [set preferences for Microsoft Defender for Endpoint на Linux.](linux-preferences.md)</span><span class="sxs-lookup"><span data-stu-id="b09c2-182">Guidance for how to configure the product in enterprise environments is available in [Set preferences for Microsoft Defender for Endpoint on Linux](linux-preferences.md).</span></span>

## <a name="resources"></a><span data-ttu-id="b09c2-183">Ресурсы</span><span class="sxs-lookup"><span data-stu-id="b09c2-183">Resources</span></span>

- <span data-ttu-id="b09c2-184">Дополнительные сведения о журнале, uninstalling или других темах см. в [разделе Ресурсы.](linux-resources.md)</span><span class="sxs-lookup"><span data-stu-id="b09c2-184">For more information about logging, uninstalling, or other topics, see [Resources](linux-resources.md).</span></span>
