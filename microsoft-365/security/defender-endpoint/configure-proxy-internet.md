---
title: Настройка параметров прокси-сервера устройства и подключения к Интернету
description: Настройте прокси-сервер Microsoft Defender для прокси-серверов и параметров Интернета, чтобы включить связь с облачной службой.
keywords: настройка, прокси,интернет, подключение к Интернету, параметры, параметры прокси, netsh, winhttp, прокси-сервер
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
ms.collection:
- m365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a3885a462265368bc42c758ee5a8fd1c673ec08c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51932803"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="19f12-104">Настройка параметров прокси-сервера устройства и подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="19f12-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="19f12-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="19f12-105">**Applies to:**</span></span>
- [<span data-ttu-id="19f12-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="19f12-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="19f12-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="19f12-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="19f12-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="19f12-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="19f12-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="19f12-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="19f12-110">Датчик Defender для конечной точки требует от Microsoft Windows HTTP (WinHTTP) отчета о данных датчиков и связи со службой Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="19f12-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="19f12-111">Встроенный датчик Defender for Endpoint работает в системном контексте с помощью учетной записи LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="19f12-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="19f12-112">Датчик использует службы MICROSOFT Windows HTTP (WinHTTP), чтобы включить связь с облачной службой Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="19f12-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="19f12-113">В организациях, в которых прокси-серверы переадресации используются в качестве шлюза в Интернет, можно использовать защиту сети для изучения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="19f12-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="19f12-114">Дополнительные сведения см. в статье [Исследование событий подключения, происходящих за прокси-серверами переадресации](investigate-behind-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="19f12-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="19f12-115">Параметр конфигурации WinHTTP не зависит от параметров прокси-сервера Для просмотра прокси-серверов Windows Internet (WinINet) и может открыть прокси-сервер только с помощью следующих методов обнаружения:</span><span class="sxs-lookup"><span data-stu-id="19f12-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="19f12-116">Методы автоматического обнаружения:</span><span class="sxs-lookup"><span data-stu-id="19f12-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="19f12-117">Прозрачный прокси</span><span class="sxs-lookup"><span data-stu-id="19f12-117">Transparent proxy</span></span>
  - <span data-ttu-id="19f12-118">Протокол автоматического обнаружения веб-прокси (WPAD)</span><span class="sxs-lookup"><span data-stu-id="19f12-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="19f12-119">Если вы используете прозрачный прокси или WPAD в сетевой топологии, вам не нужны специальные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="19f12-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="19f12-120">Дополнительные сведения об исключениях URL-адресов Defender для конечной точки в прокси-сервере см. в ссылке Включить доступ к URL-адресам службы Defender для конечных точек на [прокси-сервере.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="19f12-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="19f12-121">Конфигурация статического прокси вручную:</span><span class="sxs-lookup"><span data-stu-id="19f12-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="19f12-122">Конфигурация на основе реестра</span><span class="sxs-lookup"><span data-stu-id="19f12-122">Registry based configuration</span></span>
  - <span data-ttu-id="19f12-123">WinHTTP, настроенный с помощью команды netsh, подходит только для настольных компьютеров в стабильной топологии (например: настольный компьютер в корпоративной сети за тем же прокси-сервером)</span><span class="sxs-lookup"><span data-stu-id="19f12-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="19f12-124">Настройка прокси-сервера вручную с использованием статического прокси-сервера на основе реестра</span><span class="sxs-lookup"><span data-stu-id="19f12-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="19f12-125">Настройка статического прокси-сервера на основе реестра, чтобы позволить только датчику Defender для конечных точек сообщать диагностические данные и общаться с службами Defender для конечных точек, если компьютеру не разрешено подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="19f12-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

> [!NOTE]
> - <span data-ttu-id="19f12-126">При использовании этого параметра в Windows 10 или Windows Server 2019 рекомендуется использовать следующие (или более поздние) сборки и накопительные обновления:</span><span class="sxs-lookup"><span data-stu-id="19f12-126">When using this option on Windows 10 or Windows Server 2019, it is recommended to have the following (or later) build and cumulative update rollup:</span></span></br>
> <span data-ttu-id="19f12-127">Windows 10, версия 1909 — https://support.microsoft.com/kb/4601380</span><span class="sxs-lookup"><span data-stu-id="19f12-127">Windows 10, version 1909 - https://support.microsoft.com/kb/4601380</span></span></br>
> <span data-ttu-id="19f12-128">Windows 10, версия 2004 — https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="19f12-128">Windows 10, version 2004 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="19f12-129">Windows 10, версия 20H2 — https://support.microsoft.com/kb/4601382</span><span class="sxs-lookup"><span data-stu-id="19f12-129">Windows 10, version 20H2 - https://support.microsoft.com/kb/4601382</span></span></br>
> <span data-ttu-id="19f12-130">Эти обновления улучшают подключение и надежность канала CnC (Command and Control).</span><span class="sxs-lookup"><span data-stu-id="19f12-130">These updates improve the connectivity and reliability of the CnC (Command and Control) channel.</span></span></br>

<span data-ttu-id="19f12-131">Статический прокси-сервер можно настроить с помощью групповой политики (GP).</span><span class="sxs-lookup"><span data-stu-id="19f12-131">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="19f12-132">Групповые политики можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="19f12-132">The group policy can be found under:</span></span>

- <span data-ttu-id="19f12-133">Административные шаблоны > компоненты Windows > сбор данных и сборки предварительного просмотра > Настройка использования аутентификации прокси для службы подключенных пользователей и телеметрии</span><span class="sxs-lookup"><span data-stu-id="19f12-133">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="19f12-134">Установите его для **включения и** выбора **отключения использования** прокси-сервера с проверкой подлинности: ![ изображение параметра групповой политики1](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="19f12-134">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="19f12-135">**Административные шаблоны > компоненты Windows >** сбор данных и предварительные сборки > настройка подключенных пользовательских интерфейсов и телеметрии:</span><span class="sxs-lookup"><span data-stu-id="19f12-135">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="19f12-136">Настройка прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="19f12-136">Configure the proxy:</span></span><br>
    <span data-ttu-id="19f12-137">![Изображение параметра групповой политики2](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="19f12-137">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="19f12-138">Политика устанавливает два значения реестра: `TelemetryProxyServer` как REG_SZ и `DisableEnterpriseAuthProxy` как REG_DWORD в разделе реестра `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="19f12-138">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="19f12-139">Значение реестра принимает `TelemetryProxyServer` следующий формат строки:</span><span class="sxs-lookup"><span data-stu-id="19f12-139">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="19f12-140">Например, 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="19f12-140">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="19f12-141">Следует назначить значение реестра `DisableEnterpriseAuthProxy` — 1.</span><span class="sxs-lookup"><span data-stu-id="19f12-141">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="19f12-142">Настройка прокси-сервера вручную с помощью команды netsh</span><span class="sxs-lookup"><span data-stu-id="19f12-142">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="19f12-143">Используйте команду netsh для настройки статического прокси на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="19f12-143">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="19f12-144">Это повлияет на все приложения, в том числе службы Windows, которые используют WinHTTP с прокси по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="19f12-144">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="19f12-145">Ноутбуки, которые меняют топологию (например, из офиса в дом), будут неисправными с сеткой.</span><span class="sxs-lookup"><span data-stu-id="19f12-145">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="19f12-146">Используйте настройку статических прокси-серверов на основе реестра.</span><span class="sxs-lookup"><span data-stu-id="19f12-146">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="19f12-147">Откройте командную строку с повышенными правами:</span><span class="sxs-lookup"><span data-stu-id="19f12-147">Open an elevated command-line:</span></span>

    <span data-ttu-id="19f12-148">а.</span><span class="sxs-lookup"><span data-stu-id="19f12-148">a.</span></span> <span data-ttu-id="19f12-149">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="19f12-149">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="19f12-150">б.</span><span class="sxs-lookup"><span data-stu-id="19f12-150">b.</span></span> <span data-ttu-id="19f12-151">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="19f12-151">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="19f12-152">Введите следующую команду и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="19f12-152">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="19f12-153">Например, netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="19f12-153">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="19f12-154">Чтобы сбросить прокси winhttp, введите следующую команду и нажмите **кнопку Ввод**</span><span class="sxs-lookup"><span data-stu-id="19f12-154">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="19f12-155">Дополнительные сведения см. в статье [Синтаксис команд, контексты и форматирование Netsh](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="19f12-155">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="19f12-156">Включить доступ к URL-адресам службы "Защитник Майкрософт для конечных точек" на прокси-сервере</span><span class="sxs-lookup"><span data-stu-id="19f12-156">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="19f12-157">Если прокси-сервер или брандмауэр блокирует весь трафик по умолчанию и пропускает только определенные домены, добавьте домены, перечисленные в загружаемой электронной таблице, в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="19f12-157">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="19f12-158">В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть.</span><span class="sxs-lookup"><span data-stu-id="19f12-158">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="19f12-159">Необходимо убедиться, что нет правил фильтрации брандмауэра или сети, которые бы  отказывали в доступе к этим URL-адресам, или вам может потребоваться создать правило разрешить специально для них.</span><span class="sxs-lookup"><span data-stu-id="19f12-159">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="19f12-160">**Таблица списка доменов**</span><span class="sxs-lookup"><span data-stu-id="19f12-160">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="19f12-161">**Описание**</span><span class="sxs-lookup"><span data-stu-id="19f12-161">**Description**</span></span>|
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | <span data-ttu-id="19f12-163">Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС.</span><span class="sxs-lookup"><span data-stu-id="19f12-163">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="19f12-164">Скачайте таблицу здесь.</span><span class="sxs-lookup"><span data-stu-id="19f12-164">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="19f12-165">Если на прокси-сервере или брандмауэре включено сканирование HTTPS (проверка SSL), исключите домены, перечисленные в приведенной выше таблице, из сканирования HTTPS.</span><span class="sxs-lookup"><span data-stu-id="19f12-165">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="19f12-166">settings-win.data.microsoft.com требуется только в том случае, если у вас есть устройства с Windows 10 с версией 1803 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="19f12-166">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="19f12-167">URL-адреса, которые включают в них v20, необходимы только в том случае, если у вас есть устройства с Windows 10 с версией 1803 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="19f12-167">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="19f12-168">Например, необходимо для устройства с Windows 10 с версией 1803 или более поздней версии и с бортовой версией в регион хранения ```us-v20.events.data.microsoft.com``` данных США.</span><span class="sxs-lookup"><span data-stu-id="19f12-168">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="19f12-169">Если вы используете антивирус Microsoft Defender в своей среде, см. в руб. Настройка сетевых подключений к облачной службе антивирусных программ [Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="19f12-169">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="19f12-170">Если прокси-сервер или брандмауэр блокирует анонимный трафик, так как датчик Defender для конечной точки подключается из системного контекста, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="19f12-170">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="19f12-171">Агент мониторинга Майкрософт (MMA) — требования к прокси и брандмауэру для более старых версий клиента Windows или Windows Server</span><span class="sxs-lookup"><span data-stu-id="19f12-171">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="19f12-172">В приведенной ниже информации приведены сведения о конфигурации прокси и брандмауэра, необходимые для связи с агентом Log Analytics (часто именуемой агентом мониторинга Майкрософт) для предыдущих версий Windows, таких как Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="19f12-172">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="19f12-173">Ресурс агента</span><span class="sxs-lookup"><span data-stu-id="19f12-173">Agent Resource</span></span>|<span data-ttu-id="19f12-174">Порты</span><span class="sxs-lookup"><span data-stu-id="19f12-174">Ports</span></span> |<span data-ttu-id="19f12-175">Direction</span><span class="sxs-lookup"><span data-stu-id="19f12-175">Direction</span></span> |<span data-ttu-id="19f12-176">Обход проверки HTTPS</span><span class="sxs-lookup"><span data-stu-id="19f12-176">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="19f12-177">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="19f12-177">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="19f12-178">Порт 443</span><span class="sxs-lookup"><span data-stu-id="19f12-178">Port 443</span></span> |<span data-ttu-id="19f12-179">Исходящие</span><span class="sxs-lookup"><span data-stu-id="19f12-179">Outbound</span></span>|<span data-ttu-id="19f12-180">Да</span><span class="sxs-lookup"><span data-stu-id="19f12-180">Yes</span></span> |  
|<span data-ttu-id="19f12-181">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="19f12-181">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="19f12-182">Порт 443</span><span class="sxs-lookup"><span data-stu-id="19f12-182">Port 443</span></span> |<span data-ttu-id="19f12-183">Исходящие</span><span class="sxs-lookup"><span data-stu-id="19f12-183">Outbound</span></span>|<span data-ttu-id="19f12-184">Да</span><span class="sxs-lookup"><span data-stu-id="19f12-184">Yes</span></span> |  
|<span data-ttu-id="19f12-185">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="19f12-185">\*.blob.core.windows.net</span></span> |<span data-ttu-id="19f12-186">Порт 443</span><span class="sxs-lookup"><span data-stu-id="19f12-186">Port 443</span></span> |<span data-ttu-id="19f12-187">Исходящие</span><span class="sxs-lookup"><span data-stu-id="19f12-187">Outbound</span></span>|<span data-ttu-id="19f12-188">Да</span><span class="sxs-lookup"><span data-stu-id="19f12-188">Yes</span></span> |
|<span data-ttu-id="19f12-189">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="19f12-189">\*.azure-automation.net</span></span> |<span data-ttu-id="19f12-190">Порт 443</span><span class="sxs-lookup"><span data-stu-id="19f12-190">Port 443</span></span> |<span data-ttu-id="19f12-191">Исходящие</span><span class="sxs-lookup"><span data-stu-id="19f12-191">Outbound</span></span>|<span data-ttu-id="19f12-192">Да</span><span class="sxs-lookup"><span data-stu-id="19f12-192">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="19f12-193">В качестве облачного решения диапазон IP может изменяться.</span><span class="sxs-lookup"><span data-stu-id="19f12-193">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="19f12-194">Рекомендуется перейти к параметру разрешения DNS.</span><span class="sxs-lookup"><span data-stu-id="19f12-194">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="19f12-195">Подтверждение требований к URL-адресу службы агента мониторинга Майкрософт (MMA)</span><span class="sxs-lookup"><span data-stu-id="19f12-195">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="19f12-196">См. следующие инструкции по устранению требования под диктовки (\*) для конкретной среды при использовании агента мониторинга Microsoft (MMA) для предыдущих версий Windows.</span><span class="sxs-lookup"><span data-stu-id="19f12-196">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="19f12-197">На борту предыдущей операционной системы с агентом мониторинга Microsoft (MMA) в Defender for Endpoint (дополнительные сведения см. в предыдущих версиях [Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) и [onboard Windows servers).](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="19f12-197">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="19f12-198">Убедитесь, что машина успешно сообщается на портале Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="19f12-198">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="19f12-199">Запустите TestCloudConnection.exe из "C:\Program Files\Microsoft Monitoring Agent\Agent", чтобы проверить подключение и увидеть необходимые URL-адреса для конкретного рабочего пространства.</span><span class="sxs-lookup"><span data-stu-id="19f12-199">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="19f12-200">Проверьте список URL-адресов Microsoft Defender для конечных точек для полного списка требований к вашему региону (см. в таблице URL-адресов [службы).](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)</span><span class="sxs-lookup"><span data-stu-id="19f12-200">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![Изображение администратора в Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="19f12-202">Конечные точки URL-адресов (\*), используемые в \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com и \*.agentsvc.azure-automation.net URL-адреса, могут быть заменены вашим конкретным ИД рабочего пространства.</span><span class="sxs-lookup"><span data-stu-id="19f12-202">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="19f12-203">ID рабочего пространства имеет особый характер для среды и рабочего пространства и может быть найден в разделе Onboarding клиента на портале Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="19f12-203">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="19f12-204">Конечная точка URL blob.core.windows.net \*.blob.core.windows.net может быть заменена URL-адресами, показанными в разделе "Правило брандмауэра: \*.blob.core.windows.net" результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="19f12-204">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="19f12-205">В случае висячего использования через Azure Defender может использоваться несколько пространств работы.</span><span class="sxs-lookup"><span data-stu-id="19f12-205">In the case of onboarding via Azure Defender, multiple workspaces maybe used.</span></span> <span data-ttu-id="19f12-206">Вам потребуется выполнить процедуру TestCloudConnection.exe на бортовом компьютере из каждого рабочего пространства (чтобы определить, есть ли какие-либо изменения url-адресов \*.blob.core.windows.net между рабочей областью).</span><span class="sxs-lookup"><span data-stu-id="19f12-206">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls"></a><span data-ttu-id="19f12-207">Проверка подключения клиента к URL-адресам службы Microsoft Defender для конечных точек</span><span class="sxs-lookup"><span data-stu-id="19f12-207">Verify client connectivity to Microsoft Defender for Endpoint service URLs</span></span>

<span data-ttu-id="19f12-208">Убедитесь в том, что настройка прокси-сервера выполнена успешно, служба WinHTTP может обнаружить и передать данные через прокси-сервер в вашей среде, а прокси-сервер разрешает трафик на URL-адреса службы Защитника для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="19f12-208">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="19f12-209">Скачайте средство клиентского анализатора [MDATP](https://aka.ms/mdatpanalyzer) на компьютер, на котором работает датчик Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="19f12-209">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="19f12-210">Извлеките содержимое MDATPClientAnalyzer.zip на устройство.</span><span class="sxs-lookup"><span data-stu-id="19f12-210">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="19f12-211">Откройте командную строку с повышенными правами:</span><span class="sxs-lookup"><span data-stu-id="19f12-211">Open an elevated command-line:</span></span>

    <span data-ttu-id="19f12-212">а.</span><span class="sxs-lookup"><span data-stu-id="19f12-212">a.</span></span> <span data-ttu-id="19f12-213">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="19f12-213">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="19f12-214">б.</span><span class="sxs-lookup"><span data-stu-id="19f12-214">b.</span></span>  <span data-ttu-id="19f12-215">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="19f12-215">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="19f12-216">Введите следующую команду и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="19f12-216">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="19f12-217">Замените *HardDrivePath* на путь, по которому был загружен инструмент MDATPClientAnalyzer, например</span><span class="sxs-lookup"><span data-stu-id="19f12-217">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="19f12-218">*ИзвлечениеMDATPClientAnalyzerResult.zip,* созданного инструментом в папке, используемой в *HardDrivePath.*</span><span class="sxs-lookup"><span data-stu-id="19f12-218">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="19f12-219">Откройте *MDATPClientAnalyzerResult.txt* и убедитесь в том, что вы выполнили действия по настройке прокси-сервера, чтобы включить обнаружение сервера и доступ к URL-адресам службы.</span><span class="sxs-lookup"><span data-stu-id="19f12-219">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="19f12-220">Средство проверяет возможность подключения URL-адресов службы Защитника для конечной точки, которые настроены для работы службы Защитника для конечной точки с клиентом.</span><span class="sxs-lookup"><span data-stu-id="19f12-220">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="19f12-221">Затем результаты выводятся в файл *MDATPClientAnalyzerResult.txt* для каждого URL-адреса, который потенциально можно использоваться для общения с Защитником для служб конечных точек.</span><span class="sxs-lookup"><span data-stu-id="19f12-221">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="19f12-222">Пример:</span><span class="sxs-lookup"><span data-stu-id="19f12-222">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="19f12-223">Если по крайней мере один из вариантов подключения возвращает состояние (200), то клиент Defender для конечной точки может правильно взаимодействовать с проверенным URL-адресом, используя этот метод подключения.</span><span class="sxs-lookup"><span data-stu-id="19f12-223">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="19f12-224">Однако, если результаты проверки подключения указывают на сбой, отображается ошибка HTTP (см. Коды состояния HTTP).</span><span class="sxs-lookup"><span data-stu-id="19f12-224">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="19f12-225">Затем можно использовать URL-адреса в таблице, показанной в Таблице Включить доступ к URL-адресам службы Defender для конечных точек [на прокси-сервере.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="19f12-225">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="19f12-226">Url-адреса, которые вы будете использовать, будут зависеть от региона, выбранного во время процедуры бортовой работы.</span><span class="sxs-lookup"><span data-stu-id="19f12-226">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="19f12-227"> Анализатор подключений не совместим с правилом ASR — [Блокировка создания процессов, исходящих от команд PSExec и WMI](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="19f12-227">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="19f12-228">Необходимо временно отключить это правило, чтобы запустить средство подключения.</span><span class="sxs-lookup"><span data-stu-id="19f12-228">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="19f12-229">При наборе TelemetryProxyServer в реестре или через групповую политику защитник для конечной точки отпадет на прямую, если не может получить доступ к определенному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="19f12-229">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="19f12-230">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="19f12-230">Related topics</span></span>

- [<span data-ttu-id="19f12-231">Подключение устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="19f12-231">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="19f12-232">Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки</span><span class="sxs-lookup"><span data-stu-id="19f12-232">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
