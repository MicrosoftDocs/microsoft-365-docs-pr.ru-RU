---
title: Настройка параметров прокси-сервера устройства и подключения к Интернету
description: Настройте прокси-сервер и параметры AtP Защитника Майкрософт, чтобы включить связь с облачной службой.
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
- m365initiative-defender-endpoint
ms.topic: article
ms.technology: mde
ms.openlocfilehash: ce8599556b1d0c8efbd020d525b30ed2cedaa9cb
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165469"
---
# <a name="configure-device-proxy-and-internet-connectivity-settings"></a><span data-ttu-id="28226-104">Настройка параметров прокси-сервера устройства и подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="28226-104">Configure device proxy and Internet connectivity settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="28226-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="28226-105">**Applies to:**</span></span>
- [<span data-ttu-id="28226-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="28226-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="28226-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="28226-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="28226-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="28226-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="28226-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="28226-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)

<span data-ttu-id="28226-110">Датчик Defender для конечной точки требует от Microsoft Windows HTTP (WinHTTP) отчета о данных датчиков и связи со службой Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="28226-110">The Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Defender for Endpoint service.</span></span>

<span data-ttu-id="28226-111">Встроенный датчик Defender for Endpoint работает в системном контексте с помощью учетной записи LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="28226-111">The embedded Defender for Endpoint sensor runs in system context using the LocalSystem account.</span></span> <span data-ttu-id="28226-112">Датчик использует службы MICROSOFT Windows HTTP (WinHTTP), чтобы включить связь с облачной службой Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="28226-112">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Defender for Endpoint cloud service.</span></span>

>[!TIP]
><span data-ttu-id="28226-113">В организациях, в которых прокси-серверы переадресации используются в качестве шлюза в Интернет, можно использовать защиту сети для изучения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="28226-113">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="28226-114">Дополнительные сведения см. в статье [Исследование событий подключения, происходящих за прокси-серверами переадресации](investigate-behind-proxy.md).</span><span class="sxs-lookup"><span data-stu-id="28226-114">For more information, see [Investigate connection events that occur behind forward proxies](investigate-behind-proxy.md).</span></span>

<span data-ttu-id="28226-115">Параметр конфигурации WinHTTP не зависит от параметров прокси-сервера Для просмотра прокси-серверов Windows Internet (WinINet) и может открыть прокси-сервер только с помощью следующих методов обнаружения:</span><span class="sxs-lookup"><span data-stu-id="28226-115">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

- <span data-ttu-id="28226-116">Методы автоматического обнаружения:</span><span class="sxs-lookup"><span data-stu-id="28226-116">Auto-discovery methods:</span></span>
  - <span data-ttu-id="28226-117">Прозрачный прокси</span><span class="sxs-lookup"><span data-stu-id="28226-117">Transparent proxy</span></span>
  - <span data-ttu-id="28226-118">Протокол автоматического обнаружения веб-прокси (WPAD)</span><span class="sxs-lookup"><span data-stu-id="28226-118">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

    > [!NOTE]
    > <span data-ttu-id="28226-119">Если вы используете прозрачный прокси или WPAD в сетевой топологии, вам не нужны специальные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="28226-119">If you're using Transparent proxy or WPAD in your network topology, you don't need special configuration settings.</span></span> <span data-ttu-id="28226-120">Дополнительные сведения об исключениях URL-адресов Defender для конечной точки в прокси-сервере см. в ссылке Включить доступ к URL-адресам службы Defender для конечных точек на [прокси-сервере.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="28226-120">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="28226-121">Конфигурация статического прокси вручную:</span><span class="sxs-lookup"><span data-stu-id="28226-121">Manual static proxy configuration:</span></span>
  - <span data-ttu-id="28226-122">Конфигурация на основе реестра</span><span class="sxs-lookup"><span data-stu-id="28226-122">Registry based configuration</span></span>
  - <span data-ttu-id="28226-123">WinHTTP, настроенный с помощью команды netsh, подходит только для настольных компьютеров в стабильной топологии (например: настольный компьютер в корпоративной сети за тем же прокси-сервером)</span><span class="sxs-lookup"><span data-stu-id="28226-123">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="28226-124">Настройка прокси-сервера вручную с использованием статического прокси-сервера на основе реестра</span><span class="sxs-lookup"><span data-stu-id="28226-124">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="28226-125">Настройка статического прокси-сервера на основе реестра, чтобы позволить только датчику Defender для конечных точек сообщать диагностические данные и общаться с службами Defender для конечных точек, если компьютеру не разрешено подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="28226-125">Configure a registry-based static proxy to allow only Defender for Endpoint sensor to report diagnostic data and communicate with Defender for Endpoint services if a computer is not be permitted to connect to the Internet.</span></span>

<span data-ttu-id="28226-126">Статический прокси-сервер можно настроить с помощью групповой политики (GP).</span><span class="sxs-lookup"><span data-stu-id="28226-126">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="28226-127">Групповые политики можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="28226-127">The group policy can be found under:</span></span>

- <span data-ttu-id="28226-128">Административные шаблоны > компоненты Windows > сбор данных и сборки предварительного просмотра > Настройка использования аутентификации прокси для службы подключенных пользователей и телеметрии</span><span class="sxs-lookup"><span data-stu-id="28226-128">Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
  - <span data-ttu-id="28226-129">Установите его для **включения и** выбора **отключения использования** прокси-сервера с проверкой подлинности: ![ изображение параметра групповой политики1](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="28226-129">Set it to **Enabled** and select **Disable Authenticated Proxy usage**: ![Image of Group Policy setting1](images/atp-gpo-proxy1.png)</span></span>
- <span data-ttu-id="28226-130">**Административные шаблоны > компоненты Windows >** сбор данных и предварительные сборки > настройка подключенных пользовательских интерфейсов и телеметрии:</span><span class="sxs-lookup"><span data-stu-id="28226-130">**Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>
  - <span data-ttu-id="28226-131">Настройка прокси-сервера:</span><span class="sxs-lookup"><span data-stu-id="28226-131">Configure the proxy:</span></span><br>
    <span data-ttu-id="28226-132">![Изображение параметра групповой политики2](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="28226-132">![Image of Group Policy setting2](images/atp-gpo-proxy2.png)</span></span>

    <span data-ttu-id="28226-133">Политика устанавливает два значения реестра: `TelemetryProxyServer` как REG_SZ и `DisableEnterpriseAuthProxy` как REG_DWORD в разделе реестра `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="28226-133">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

    <span data-ttu-id="28226-134">Значение реестра принимает `TelemetryProxyServer` следующий формат строки:</span><span class="sxs-lookup"><span data-stu-id="28226-134">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

    ```text
    <server name or ip>:<port>
    ```

    <span data-ttu-id="28226-135">Например, 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="28226-135">For example: 10.0.0.6:8080</span></span>

    <span data-ttu-id="28226-136">Следует назначить значение реестра `DisableEnterpriseAuthProxy` — 1.</span><span class="sxs-lookup"><span data-stu-id="28226-136">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="28226-137">Настройка прокси-сервера вручную с помощью команды netsh</span><span class="sxs-lookup"><span data-stu-id="28226-137">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="28226-138">Используйте команду netsh для настройки статического прокси на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="28226-138">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="28226-139">Это повлияет на все приложения, в том числе службы Windows, которые используют WinHTTP с прокси по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="28226-139">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="28226-140">Ноутбуки, которые меняют топологию (например, из офиса в дом), будут неисправными с сеткой.</span><span class="sxs-lookup"><span data-stu-id="28226-140">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="28226-141">Используйте настройку статических прокси-серверов на основе реестра.</span><span class="sxs-lookup"><span data-stu-id="28226-141">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="28226-142">Откройте командную строку с повышенными правами:</span><span class="sxs-lookup"><span data-stu-id="28226-142">Open an elevated command-line:</span></span>

    <span data-ttu-id="28226-143">а)</span><span class="sxs-lookup"><span data-stu-id="28226-143">a.</span></span> <span data-ttu-id="28226-144">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="28226-144">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="28226-145">б)</span><span class="sxs-lookup"><span data-stu-id="28226-145">b.</span></span> <span data-ttu-id="28226-146">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="28226-146">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="28226-147">Введите следующую команду и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="28226-147">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="28226-148">Например, netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="28226-148">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>

<span data-ttu-id="28226-149">Чтобы сбросить прокси winhttp, введите следующую команду и нажмите **кнопку Ввод**</span><span class="sxs-lookup"><span data-stu-id="28226-149">To reset the winhttp proxy, enter the following command and press **Enter**</span></span>

```PowerShell
netsh winhttp reset proxy
```

<span data-ttu-id="28226-150">Дополнительные сведения см. в статье [Синтаксис команд, контексты и форматирование Netsh](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="28226-150">See [Netsh Command Syntax, Contexts, and Formatting](https://docs.microsoft.com/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>

## <a name="enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server"></a><span data-ttu-id="28226-151">Включить доступ к URL-адресам службы "Защитник Майкрософт для конечных точек" на прокси-сервере</span><span class="sxs-lookup"><span data-stu-id="28226-151">Enable access to Microsoft Defender for Endpoint service URLs in the proxy server</span></span>

<span data-ttu-id="28226-152">Если прокси-сервер или брандмауэр блокирует весь трафик по умолчанию и пропускает только определенные домены, добавьте домены, перечисленные в загружаемой электронной таблице, в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="28226-152">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="28226-153">В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть.</span><span class="sxs-lookup"><span data-stu-id="28226-153">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="28226-154">Необходимо убедиться, что нет правил фильтрации брандмауэра или сети, которые бы  отказывали в доступе к этим URL-адресам, или вам может потребоваться создать правило разрешить специально для них.</span><span class="sxs-lookup"><span data-stu-id="28226-154">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>


|<span data-ttu-id="28226-155">**Таблица списка доменов**</span><span class="sxs-lookup"><span data-stu-id="28226-155">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="28226-156">**Описание**</span><span class="sxs-lookup"><span data-stu-id="28226-156">**Description**</span></span>|
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | <span data-ttu-id="28226-158">Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС.</span><span class="sxs-lookup"><span data-stu-id="28226-158">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="28226-159">Скачайте таблицу здесь.</span><span class="sxs-lookup"><span data-stu-id="28226-159">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


<span data-ttu-id="28226-160">Если на прокси-сервере или брандмауэре включено сканирование HTTPS (проверка SSL), исключите домены, перечисленные в приведенной выше таблице, из сканирования HTTPS.</span><span class="sxs-lookup"><span data-stu-id="28226-160">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>

> [!NOTE]
> <span data-ttu-id="28226-161">settings-win.data.microsoft.com требуется только в том случае, если у вас есть устройства с Windows 10 с версией 1803 или более ранней версии.</span><span class="sxs-lookup"><span data-stu-id="28226-161">settings-win.data.microsoft.com is only needed if you have Windows 10 devices running version 1803 or earlier.</span></span><br>


> [!NOTE]
> <span data-ttu-id="28226-162">URL-адреса, которые включают в них v20, необходимы только в том случае, если у вас есть устройства с Windows 10 с версией 1803 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="28226-162">URLs that include v20 in them are only needed if you have Windows 10 devices running version 1803 or later.</span></span> <span data-ttu-id="28226-163">Например, необходимо для устройства с Windows 10 с версией 1803 или более поздней версии и с бортовой версией в регион хранения ```us-v20.events.data.microsoft.com``` данных США.</span><span class="sxs-lookup"><span data-stu-id="28226-163">For example, ```us-v20.events.data.microsoft.com``` is needed for a Windows 10 device running version 1803 or later and onboarded to US Data Storage region.</span></span>


> [!NOTE]
> <span data-ttu-id="28226-164">Если вы используете антивирус Microsoft Defender в своей среде, см. в руб. Настройка сетевых подключений к облачной службе антивирусных программ [Microsoft Defender.](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus)</span><span class="sxs-lookup"><span data-stu-id="28226-164">If you are using Microsoft Defender Antivirus in your environment, see [Configure network connections to the Microsoft Defender Antivirus cloud service](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-network-connections-microsoft-defender-antivirus).</span></span>

<span data-ttu-id="28226-165">Если прокси-сервер или брандмауэр блокирует анонимный трафик, так как датчик Defender для конечной точки подключается из системного контекста, убедитесь, что анонимный трафик разрешен в указанных ранее URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="28226-165">If a proxy or firewall is blocking anonymous traffic, as Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

### <a name="microsoft-monitoring-agent-mma---proxy-and-firewall-requirements-for-older-versions-of-windows-client-or-windows-server"></a><span data-ttu-id="28226-166">Агент мониторинга Майкрософт (MMA) — требования к прокси и брандмауэру для более старых версий клиента Windows или Windows Server</span><span class="sxs-lookup"><span data-stu-id="28226-166">Microsoft Monitoring Agent (MMA) - proxy and firewall requirements for older versions of Windows client or Windows Server</span></span>

<span data-ttu-id="28226-167">В приведенной ниже информации приведены сведения о конфигурации прокси и брандмауэра, необходимые для связи с агентом Log Analytics (часто именуемой агентом мониторинга Майкрософт) для предыдущих версий Windows, таких как Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2 и Windows Server 2016.</span><span class="sxs-lookup"><span data-stu-id="28226-167">The information below list the proxy and firewall configuration information required to communicate with Log Analytics agent (often referred to as Microsoft Monitoring Agent) for the previous versions of Windows such as Windows 7 SP1, Windows 8.1, Windows Server 2008 R2, Windows Server 2012 R2, and Windows Server 2016.</span></span>

|<span data-ttu-id="28226-168">Ресурс агента</span><span class="sxs-lookup"><span data-stu-id="28226-168">Agent Resource</span></span>|<span data-ttu-id="28226-169">Порты</span><span class="sxs-lookup"><span data-stu-id="28226-169">Ports</span></span> |<span data-ttu-id="28226-170">Direction</span><span class="sxs-lookup"><span data-stu-id="28226-170">Direction</span></span> |<span data-ttu-id="28226-171">Обход проверки HTTPS</span><span class="sxs-lookup"><span data-stu-id="28226-171">Bypass HTTPS inspection</span></span>|
|------|---------|--------|--------|   
|<span data-ttu-id="28226-172">\*.ods.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="28226-172">\*.ods.opinsights.azure.com</span></span> |<span data-ttu-id="28226-173">Порт 443</span><span class="sxs-lookup"><span data-stu-id="28226-173">Port 443</span></span> |<span data-ttu-id="28226-174">Исходящие</span><span class="sxs-lookup"><span data-stu-id="28226-174">Outbound</span></span>|<span data-ttu-id="28226-175">Да</span><span class="sxs-lookup"><span data-stu-id="28226-175">Yes</span></span> |  
|<span data-ttu-id="28226-176">\*.oms.opinsights.azure.com</span><span class="sxs-lookup"><span data-stu-id="28226-176">\*.oms.opinsights.azure.com</span></span> |<span data-ttu-id="28226-177">Порт 443</span><span class="sxs-lookup"><span data-stu-id="28226-177">Port 443</span></span> |<span data-ttu-id="28226-178">Исходящие</span><span class="sxs-lookup"><span data-stu-id="28226-178">Outbound</span></span>|<span data-ttu-id="28226-179">Да</span><span class="sxs-lookup"><span data-stu-id="28226-179">Yes</span></span> |  
|<span data-ttu-id="28226-180">\*.blob.core.windows.net</span><span class="sxs-lookup"><span data-stu-id="28226-180">\*.blob.core.windows.net</span></span> |<span data-ttu-id="28226-181">Порт 443</span><span class="sxs-lookup"><span data-stu-id="28226-181">Port 443</span></span> |<span data-ttu-id="28226-182">Исходящие</span><span class="sxs-lookup"><span data-stu-id="28226-182">Outbound</span></span>|<span data-ttu-id="28226-183">Да</span><span class="sxs-lookup"><span data-stu-id="28226-183">Yes</span></span> |
|<span data-ttu-id="28226-184">\*.azure-automation.net</span><span class="sxs-lookup"><span data-stu-id="28226-184">\*.azure-automation.net</span></span> |<span data-ttu-id="28226-185">Порт 443</span><span class="sxs-lookup"><span data-stu-id="28226-185">Port 443</span></span> |<span data-ttu-id="28226-186">Исходящие</span><span class="sxs-lookup"><span data-stu-id="28226-186">Outbound</span></span>|<span data-ttu-id="28226-187">Да</span><span class="sxs-lookup"><span data-stu-id="28226-187">Yes</span></span> |  


> [!NOTE]
> <span data-ttu-id="28226-188">В качестве облачного решения диапазон IP может изменяться.</span><span class="sxs-lookup"><span data-stu-id="28226-188">As a cloud-based solution, the IP range can change.</span></span> <span data-ttu-id="28226-189">Рекомендуется перейти к параметру разрешения DNS.</span><span class="sxs-lookup"><span data-stu-id="28226-189">It's recommended you move to DNS resolving setting.</span></span>

## <a name="confirm-microsoft-monitoring-agent-mma-service-url-requirements"></a><span data-ttu-id="28226-190">Подтверждение требований к URL-адресу службы агента мониторинга Майкрософт (MMA)</span><span class="sxs-lookup"><span data-stu-id="28226-190">Confirm Microsoft Monitoring Agent (MMA) Service URL Requirements</span></span> 

<span data-ttu-id="28226-191">См. следующие инструкции по устранению требования под диктовки (\*) для конкретной среды при использовании агента мониторинга Microsoft (MMA) для предыдущих версий Windows.</span><span class="sxs-lookup"><span data-stu-id="28226-191">Please see the following guidance to eliminate the wildcard (\*) requirement for your specific environment when using the Microsoft Monitoring Agent (MMA) for previous versions of Windows.</span></span>

1.  <span data-ttu-id="28226-192">На борту предыдущей операционной системы с агентом мониторинга Microsoft (MMA) в Defender for Endpoint (дополнительные сведения см. в предыдущих версиях [Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) и [onboard Windows servers).](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016)</span><span class="sxs-lookup"><span data-stu-id="28226-192">Onboard a previous operating system with the Microsoft Monitoring Agent (MMA) into Defender for Endpoint (for more information, see [Onboard previous versions of Windows on Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2010326) and [Onboard Windows servers](configure-server-endpoints.md#windows-server-2008-r2-sp1-windows-server-2012-r2-and-windows-server-2016).</span></span>

2.  <span data-ttu-id="28226-193">Убедитесь, что машина успешно сообщается на портале Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="28226-193">Ensure the machine is successfully reporting into the Microsoft Defender Security Center portal.</span></span>

3.  <span data-ttu-id="28226-194">Запустите TestCloudConnection.exe из "C:\Program Files\Microsoft Monitoring Agent\Agent", чтобы проверить подключение и увидеть необходимые URL-адреса для конкретного рабочего пространства.</span><span class="sxs-lookup"><span data-stu-id="28226-194">Run the TestCloudConnection.exe tool from “C:\Program Files\Microsoft Monitoring Agent\Agent” to validate the connectivity and to see the required URLs for your specific workspace.</span></span>

4.  <span data-ttu-id="28226-195">Проверьте список URL-адресов Microsoft Defender для конечных точек для полного списка требований к вашему региону (см. в таблице URL-адресов [службы).](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)</span><span class="sxs-lookup"><span data-stu-id="28226-195">Check the Microsoft Defender for Endpoint URLs list for the complete list of requirements for your region (please refer to the Service URLs [Spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx)).</span></span>

![Изображение администратора в Windows PowerShell](images/admin-powershell.png)

<span data-ttu-id="28226-197">Конечные точки URL-адресов (\*), используемые в \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com и \*.agentsvc.azure-automation.net URL-адреса, могут быть заменены вашим конкретным ИД рабочего пространства.</span><span class="sxs-lookup"><span data-stu-id="28226-197">The wildcards (\*) used in \*.ods.opinsights.azure.com, \*.oms.opinsights.azure.com, and \*.agentsvc.azure-automation.net URL endpoints can be replaced with your specific Workspace ID.</span></span> <span data-ttu-id="28226-198">ID рабочего пространства имеет особый характер для среды и рабочего пространства и может быть найден в разделе Onboarding клиента на портале Центра безопасности Защитника Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="28226-198">The Workspace ID is specific to your environment and workspace and can be found in the Onboarding section of your tenant within the Microsoft Defender Security Center portal.</span></span>

<span data-ttu-id="28226-199">Конечная точка URL blob.core.windows.net \*.blob.core.windows.net может быть заменена URL-адресами, показанными в разделе "Правило брандмауэра: \*.blob.core.windows.net" результатов тестирования.</span><span class="sxs-lookup"><span data-stu-id="28226-199">The \*.blob.core.windows.net URL endpoint can be replaced with the URLs shown in the “Firewall Rule: \*.blob.core.windows.net” section of the test results.</span></span> 

> [!NOTE]
> <span data-ttu-id="28226-200">В случае использования в центре безопасности Azure (ASC) может использоваться несколько областей работы.</span><span class="sxs-lookup"><span data-stu-id="28226-200">In the case of onboarding via Azure Security Center (ASC), multiple workspaces maybe used.</span></span> <span data-ttu-id="28226-201">Вам потребуется выполнить процедуру TestCloudConnection.exe на бортовом компьютере из каждого рабочего пространства (чтобы определить, есть ли какие-либо изменения url-адресов \*.blob.core.windows.net между рабочей областью).</span><span class="sxs-lookup"><span data-stu-id="28226-201">You will need to perform the TestCloudConnection.exe procedure above on an onboarded machine from each workspace (to determine if there are any changes to the \*.blob.core.windows.net URLs between the workspaces).</span></span>

## <a name="verify-client-connectivity-to-microsoft-defender-atp-service-urls"></a><span data-ttu-id="28226-202">Проверка подключения клиента к URL-адресам службы ATP Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="28226-202">Verify client connectivity to Microsoft Defender ATP service URLs</span></span>

<span data-ttu-id="28226-203">Убедитесь в том, что настройка прокси-сервера выполнена успешно, служба WinHTTP может обнаружить и передать данные через прокси-сервер в вашей среде, а прокси-сервер разрешает трафик на URL-адреса службы Защитника для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="28226-203">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="28226-204">Скачайте средство клиентского анализатора [MDATP](https://aka.ms/mdatpanalyzer) на компьютер, на котором работает датчик Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="28226-204">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Defender for Endpoint sensor is running on.</span></span>

2. <span data-ttu-id="28226-205">Извлеките содержимое MDATPClientAnalyzer.zip на устройство.</span><span class="sxs-lookup"><span data-stu-id="28226-205">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>

3. <span data-ttu-id="28226-206">Откройте командную строку с повышенными правами:</span><span class="sxs-lookup"><span data-stu-id="28226-206">Open an elevated command-line:</span></span>

    <span data-ttu-id="28226-207">а)</span><span class="sxs-lookup"><span data-stu-id="28226-207">a.</span></span> <span data-ttu-id="28226-208">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="28226-208">Go to **Start** and type **cmd**.</span></span>

    <span data-ttu-id="28226-209">б)</span><span class="sxs-lookup"><span data-stu-id="28226-209">b.</span></span>  <span data-ttu-id="28226-210">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="28226-210">Right-click **Command prompt** and select **Run as administrator**.</span></span>

4. <span data-ttu-id="28226-211">Введите следующую команду и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="28226-211">Enter the following command and press **Enter**:</span></span>

    ```PowerShell
    HardDrivePath\MDATPClientAnalyzer.cmd
    ```

    <span data-ttu-id="28226-212">Замените *HardDrivePath* на путь, по которому был загружен инструмент MDATPClientAnalyzer, например</span><span class="sxs-lookup"><span data-stu-id="28226-212">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>

    ```PowerShell
    C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd
    ```

5. <span data-ttu-id="28226-213">*ИзвлечениеMDATPClientAnalyzerResult.zip,* созданного инструментом в папке, используемой в *HardDrivePath.*</span><span class="sxs-lookup"><span data-stu-id="28226-213">Extract the *MDATPClientAnalyzerResult.zip* file created by tool in the folder used in the *HardDrivePath*.</span></span>

6. <span data-ttu-id="28226-214">Откройте *MDATPClientAnalyzerResult.txt* и убедитесь в том, что вы выполнили действия по настройке прокси-сервера, чтобы включить обнаружение сервера и доступ к URL-адресам службы.</span><span class="sxs-lookup"><span data-stu-id="28226-214">Open *MDATPClientAnalyzerResult.txt* and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span> <br><br>
   <span data-ttu-id="28226-215">Средство проверяет возможность подключения URL-адресов службы Защитника для конечной точки, которые настроены для работы службы Защитника для конечной точки с клиентом.</span><span class="sxs-lookup"><span data-stu-id="28226-215">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="28226-216">Затем результаты выводятся в файл *MDATPClientAnalyzerResult.txt* для каждого URL-адреса, который потенциально можно использоваться для общения с Защитником для служб конечных точек.</span><span class="sxs-lookup"><span data-stu-id="28226-216">It then prints the results into the *MDATPClientAnalyzerResult.txt* file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="28226-217">Пример:</span><span class="sxs-lookup"><span data-stu-id="28226-217">For example:</span></span>

   ```text
   Testing URL : https://xxx.microsoft.com/xxx
   1 - Default proxy: Succeeded (200)
   2 - Proxy auto discovery (WPAD): Succeeded (200)
   3 - Proxy disabled: Succeeded (200)
   4 - Named proxy: Doesn't exist
   5 - Command line proxy: Doesn't exist
   ```

<span data-ttu-id="28226-218">Если по крайней мере один из вариантов подключения возвращает состояние (200), то клиент Defender для конечной точки может правильно взаимодействовать с проверенным URL-адресом, используя этот метод подключения.</span><span class="sxs-lookup"><span data-stu-id="28226-218">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> <br><br>

<span data-ttu-id="28226-219">Однако, если результаты проверки подключения указывают на сбой, отображается ошибка HTTP (см. Коды состояния HTTP).</span><span class="sxs-lookup"><span data-stu-id="28226-219">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="28226-220">Затем можно использовать URL-адреса в таблице, показанной в Таблице Включить доступ к URL-адресам службы Defender для конечных точек [на прокси-сервере.](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="28226-220">You can then use the URLs in the table shown in [Enable access to Defender for Endpoint service URLs in the proxy server](#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="28226-221">Url-адреса, которые вы будете использовать, будут зависеть от региона, выбранного во время процедуры бортовой работы.</span><span class="sxs-lookup"><span data-stu-id="28226-221">The URLs you'll use will depend on the region selected during the onboarding procedure.</span></span>

> [!NOTE]
> <span data-ttu-id="28226-222"> Анализатор подключений не совместим с правилом ASR — [Блокировка создания процессов, исходящих от команд PSExec и WMI](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="28226-222">The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="28226-223">Необходимо временно отключить это правило, чтобы запустить средство подключения.</span><span class="sxs-lookup"><span data-stu-id="28226-223">You will need to temporarily disable this rule to run the connectivity tool.</span></span>


> [!NOTE]
> <span data-ttu-id="28226-224">При наборе TelemetryProxyServer в реестре или через групповую политику защитник для конечной точки отпадет на прямую, если не может получить доступ к определенному прокси-серверу.</span><span class="sxs-lookup"><span data-stu-id="28226-224">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can't access the defined proxy.</span></span>

## <a name="related-topics"></a><span data-ttu-id="28226-225">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="28226-225">Related topics</span></span>

- [<span data-ttu-id="28226-226">На борту устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="28226-226">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="28226-227">Устранение неполадок в Microsoft Defender для проблем с бортовой точкой конечной точки</span><span class="sxs-lookup"><span data-stu-id="28226-227">Troubleshoot Microsoft Defender for Endpoint onboarding issues</span></span>](troubleshoot-onboarding.md)
