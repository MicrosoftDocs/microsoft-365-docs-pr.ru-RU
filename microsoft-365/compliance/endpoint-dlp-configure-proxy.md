---
title: Настройка параметров прокси-сервера и подключения к Интернету для DLP в конечной точке
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Узнайте как настроить параметры прокси-сервера и подключения к Интернету для DLP в конечной точке
ms.openlocfilehash: f2a62b5c7913b6f41c414310a97ab5f072f59642
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538619"
---
# <a name="configure-device-proxy-and-internet-connection-settings-for-endpoint-dlp"></a><span data-ttu-id="a9d80-103">Настройка параметров прокси-сервера и подключения к Интернету для DLP в конечной точке</span><span class="sxs-lookup"><span data-stu-id="a9d80-103">Configure device proxy and internet connection settings for Endpoint DLP</span></span>

<span data-ttu-id="a9d80-104">Microsoft Endpoint DLP использует Microsoft Windows HTTP (WinHTTP) для создания отчетов данных и обмена данными с облачной службой конечных точек Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a9d80-104">Microsoft Endpoint DLP uses Microsoft Windows HTTP (WinHTTP) to report data and communicate with the Microsoft endpoint cloud service.</span></span> <span data-ttu-id="a9d80-105">Внедренная защита от потери данных в конечной точке в контексте системы работает с учетной записью LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="a9d80-105">The embedded Endpoint DLP runs in system context using the LocalSystem account.</span></span>

> [!TIP]
> <span data-ttu-id="a9d80-106">В организациях, в которых прокси-серверы переадресации используются в качестве шлюза в Интернет, можно использовать защиту сети для изучения прокси-сервера.</span><span class="sxs-lookup"><span data-stu-id="a9d80-106">For organizations that use forward proxies as a gateway to the Internet, you can use network protection to investigate behind a proxy.</span></span> <span data-ttu-id="a9d80-107">Дополнительные сведения см. в статье [Исследование событий подключения, происходящих за прокси-серверами переадресации](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span><span class="sxs-lookup"><span data-stu-id="a9d80-107">For more information, see [Investigate connection events that occur behind forward proxies](/windows/security/threat-protection/microsoft-defender-atp/investigate-behind-proxy).</span></span>

<span data-ttu-id="a9d80-108">Параметр конфигурации WinHTTP не зависит от параметров прокси-сервера Интернет-браузера Windows (WinINet) и может обнаруживать прокси-сервер только с использованием следующих методов автоматического обнаружения:</span><span class="sxs-lookup"><span data-stu-id="a9d80-108">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) Internet browsing proxy settings and can only discover a proxy server by using the following auto discovery methods:</span></span>

- <span data-ttu-id="a9d80-109">Прозрачный прокси</span><span class="sxs-lookup"><span data-stu-id="a9d80-109">Transparent proxy</span></span>
- <span data-ttu-id="a9d80-110">Протокол автоматического обнаружения веб-прокси (WPAD)</span><span class="sxs-lookup"><span data-stu-id="a9d80-110">Web Proxy Auto-discovery Protocol (WPAD)</span></span>

> [!NOTE]
> <span data-ttu-id="a9d80-111">При использовании прозрачного прокси или WPAD в топологии сети, не нужно использовать специальные параметры конфигурации.</span><span class="sxs-lookup"><span data-stu-id="a9d80-111">If you’re using Transparent proxy or WPAD in your network topology, you don’t need special configuration settings.</span></span> <span data-ttu-id="a9d80-112">Дополнительные сведения об исключениях URL-адресов Защитника для конечных точек в прокси-сервере см. в статье [Разрешение доступа к URL-адресам облачной службы Endpoint DLP на прокси-сервере](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="a9d80-112">For more information on Defender for Endpoint URL exclusions in the proxy, see [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span>

- <span data-ttu-id="a9d80-113">Конфигурация статического прокси вручную:</span><span class="sxs-lookup"><span data-stu-id="a9d80-113">Manual static proxy configuration:</span></span>
    - <span data-ttu-id="a9d80-114">Конфигурация на основе реестра</span><span class="sxs-lookup"><span data-stu-id="a9d80-114">Registry-based configuration</span></span>
    - <span data-ttu-id="a9d80-115">WinHTTP, настроенный с помощью команды netsh, подходит только для настольных компьютеров в стабильной топологии (например: настольный компьютер в корпоративной сети за тем же прокси-сервером)</span><span class="sxs-lookup"><span data-stu-id="a9d80-115">WinHTTP configured using netsh command – Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

## <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="a9d80-116">Настройка прокси-сервера вручную с использованием статического прокси-сервера на основе реестра</span><span class="sxs-lookup"><span data-stu-id="a9d80-116">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="a9d80-117">Для устройств конечных точек, которым не разрешено подключаться к Интернету, необходимо настроить статический прокси на основе реестра.</span><span class="sxs-lookup"><span data-stu-id="a9d80-117">For endpoint devices that aren't permitted to connect to the Internet, you need to configure a registry-based static proxy.</span></span> <span data-ttu-id="a9d80-118">Необходимо настроить этот параметр, чтобы разрешить только Microsoft Endpoint DLP создавать отчеты о диагностических данных и обмениваться сообщениями с облачной службой конечных точек Microsoft.</span><span class="sxs-lookup"><span data-stu-id="a9d80-118">You need to configure this to allow only Microsoft Endpoint DLP to report diagnostic data and communicate with Microsoft endpoint cloud service.</span></span>

<span data-ttu-id="a9d80-119">Статический прокси-сервер можно настроить с помощью групповой политики (GP).</span><span class="sxs-lookup"><span data-stu-id="a9d80-119">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="a9d80-120">Групповые политики можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="a9d80-120">The group policy can be found under:</span></span>

1. <span data-ttu-id="a9d80-121">Откройте **Административные шаблоны > Компоненты Windows > Сборки для сбора данных и предварительные сборки > Настройка использования прокси-службы для подключенных пользователей и службы телеметрии**</span><span class="sxs-lookup"><span data-stu-id="a9d80-121">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**</span></span>

2. <span data-ttu-id="a9d80-122">Установите для этого параметра значение **Включено** и выберите пункт **Отключить использование прокси с проверкой подлинности**:</span><span class="sxs-lookup"><span data-stu-id="a9d80-122">Set it to **Enabled** and select **Disable Authenticated Proxy usage**:</span></span> 

![Изображение параметров групповой политики 1](../media/atp-gpo-proxy1.png)
 
3. <span data-ttu-id="a9d80-124">Откройте **Административные шаблоны > Компоненты Windows > Сборки для сбора данных и предварительные сборки > Настройка телеметрии и функциональных возможностей подключенных пользователей**:</span><span class="sxs-lookup"><span data-stu-id="a9d80-124">Open **Administrative Templates > Windows Components > Data Collection and Preview Builds > Configure connected user experiences and telemetry**:</span></span>

 <span data-ttu-id="a9d80-125">Настройка прокси-сервера</span><span class="sxs-lookup"><span data-stu-id="a9d80-125">Configure the proxy</span></span>

![Изображение параметров групповой политики 2](../media/atp-gpo-proxy2.png)

<span data-ttu-id="a9d80-127">Политика устанавливает два значения реестра: `TelemetryProxyServer` как REG_SZ и `DisableEnterpriseAuthProxy` как REG_DWORD в разделе реестра `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="a9d80-127">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="a9d80-128">Значение реестра TelemetryProxyServer имеет формат \<server name or ip\>:\<port\>.</span><span class="sxs-lookup"><span data-stu-id="a9d80-128">The registry value TelemetryProxyServer is in this format \<server name or ip\>:\<port\>.</span></span> <span data-ttu-id="a9d80-129">Например, **10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="a9d80-129">For example: **10.0.0.6:8080**</span></span>

<span data-ttu-id="a9d80-130">Следует назначить значение реестра `DisableEnterpriseAuthProxy` — 1.</span><span class="sxs-lookup"><span data-stu-id="a9d80-130">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

## <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="a9d80-131">Настройка прокси-сервера вручную с помощью команды "netsh"</span><span class="sxs-lookup"><span data-stu-id="a9d80-131">Configure the proxy server manually using "netsh" command</span></span>

<span data-ttu-id="a9d80-132">Используйте команду netsh для настройки статического прокси на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="a9d80-132">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> <span data-ttu-id="a9d80-133">Это повлияет на все приложения, в том числе службы Windows, которые используют WinHTTP с прокси по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="a9d80-133">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span> <span data-ttu-id="a9d80-134">— Ноутбуки, которые изменяют топологию (например, с офисной на домашнюю), не будут работать при использовании команды netsh.</span><span class="sxs-lookup"><span data-stu-id="a9d80-134">- Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="a9d80-135">Используйте настройку статических прокси-серверов на основе реестра.</span><span class="sxs-lookup"><span data-stu-id="a9d80-135">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="a9d80-136">Откройте командную строку с повышенными правами:</span><span class="sxs-lookup"><span data-stu-id="a9d80-136">Open an elevated command line:</span></span>
    1. <span data-ttu-id="a9d80-137">В меню **Пуск** введите **cmd**</span><span class="sxs-lookup"><span data-stu-id="a9d80-137">Go to **Start** and type **cmd**</span></span>
    1. <span data-ttu-id="a9d80-138">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="a9d80-138">Right-click **Command prompt** and select **Run as administrator**.</span></span>
2.  <span data-ttu-id="a9d80-139">Введите следующую команду и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="a9d80-139">Enter the following command and press **Enter**:</span></span>

    `netsh winhttp set proxy <proxy>:<port>`

    <span data-ttu-id="a9d80-140">Например, **netsh winhttp set proxy 10.0.0.6:8080**</span><span class="sxs-lookup"><span data-stu-id="a9d80-140">For example: **netsh winhttp set proxy 10.0.0.6:8080**</span></span>

3. <span data-ttu-id="a9d80-141">Чтобы сбросить прокси winhttp, введите следующую команду и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="a9d80-141">To reset the winhttp proxy, enter the following command and press **Enter**:</span></span>

     `netsh winhttp reset proxy`

<span data-ttu-id="a9d80-142">Дополнительные сведения см. в статье [Синтаксис команд, контексты и форматирование Netsh](/windows-server/networking/technologies/netsh/netsh-contexts).</span><span class="sxs-lookup"><span data-stu-id="a9d80-142">See [Netsh Command Syntax, Contexts, and Formatting](/windows-server/networking/technologies/netsh/netsh-contexts) to learn more.</span></span>


## <a name="enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server"></a><span data-ttu-id="a9d80-143">Разрешение доступа к URL-адресам облачной службы Endpoint DLP на прокси-сервере</span><span class="sxs-lookup"><span data-stu-id="a9d80-143">Enable access to Endpoint DLP cloud service URLs in the proxy server</span></span>

<span data-ttu-id="a9d80-144">Если прокси-сервер или брандмауэр блокирует весь трафик по умолчанию и пропускает только определенные домены, добавьте домены, перечисленные в загружаемой электронной таблице, в список разрешенных доменов.</span><span class="sxs-lookup"><span data-stu-id="a9d80-144">If a proxy or firewall is blocking all traffic by default and allowing only specific domains through, add the domains listed in the downloadable sheet to the allowed domains list.</span></span>

<span data-ttu-id="a9d80-145">Эта [загружаемая электронная таблица](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) содержит список служб и связанных с ними URL-адресов, которые должны быть доступны вашей сети.</span><span class="sxs-lookup"><span data-stu-id="a9d80-145">This [downloadable spreadsheet](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="a9d80-146">Убедитесь, что правила брандмауэра или сетевой фильтрации, которые запрещали бы доступ к этим URL-адресам, отсутствуют, или вам может потребоваться создать разрешающее правило специально для них.</span><span class="sxs-lookup"><span data-stu-id="a9d80-146">You should ensure that there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an allow rule specifically for them.</span></span>

<span data-ttu-id="a9d80-147">Если на прокси-сервере или брандмауэре включено сканирование HTTPS (проверка SSL), исключите домены, перечисленные в приведенной выше таблице, из сканирования HTTPS.</span><span class="sxs-lookup"><span data-stu-id="a9d80-147">If a proxy or firewall has HTTPS scanning (SSL inspection) enabled, exclude the domains listed in the above table from HTTPS scanning.</span></span>
<span data-ttu-id="a9d80-148">Если прокси-сервер или брандмауэр блокирует анонимный трафик, поскольку DLP конечной точки подключается из системного контекста, убедитесь, что анонимный трафик разрешен в ранее перечисленных URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="a9d80-148">If a proxy or firewall is blocking anonymous traffic, as Endpoint DLP is connecting from system context, make sure anonymous traffic is permitted in the previously listed URLs.</span></span>

## <a name="verify-client-connectivity-to-microsoft-cloud-service-urls"></a><span data-ttu-id="a9d80-149">Проверка подключения клиента к URL-адресам облачных служб Майкрософт</span><span class="sxs-lookup"><span data-stu-id="a9d80-149">Verify client connectivity to Microsoft cloud service URLs</span></span>

<span data-ttu-id="a9d80-150">Убедитесь в том, что настройка прокси-сервера выполнена успешно, служба WinHTTP может обнаружить и передать данные через прокси-сервер в вашей среде, а прокси-сервер разрешает трафик на URL-адреса службы Защитника для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a9d80-150">Verify the proxy configuration completed successfully, that WinHTTP can discover and communicate through the proxy server in your environment, and that the proxy server allows traffic to the Defender for Endpoint service URLs.</span></span>

1. <span data-ttu-id="a9d80-151">Скачайте [средство MDATP Client Analyzer](https://aka.ms/mdatpanalyzer) на компьютер, на котором запущена защита от потери данных в конечной точке.</span><span class="sxs-lookup"><span data-stu-id="a9d80-151">Download the [MDATP Client Analyzer tool](https://aka.ms/mdatpanalyzer) to the PC where Endpoint DLP is running on.</span></span>
2. <span data-ttu-id="a9d80-152">Извлеките содержимое MDATPClientAnalyzer.zip на устройство.</span><span class="sxs-lookup"><span data-stu-id="a9d80-152">Extract the contents of MDATPClientAnalyzer.zip on the device.</span></span>
3. <span data-ttu-id="a9d80-153">Откройте командную строку с повышенными правами:</span><span class="sxs-lookup"><span data-stu-id="a9d80-153">Open an elevated command line:</span></span>
    1. <span data-ttu-id="a9d80-154">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="a9d80-154">Go to **Start** and type **cmd**.</span></span>
    1. <span data-ttu-id="a9d80-155">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="a9d80-155">Right-click **Command prompt** and select **Run as administrator**.</span></span>
4.  <span data-ttu-id="a9d80-156">Введите следующую команду и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="a9d80-156">Enter the following command and press **Enter**:</span></span>
    
`HardDrivePath\MDATPClientAnalyzer.cmd`

<span data-ttu-id="a9d80-157">Замените *HardDrivePath* на путь, по которому был загружен инструмент MDATPClientAnalyzer, например</span><span class="sxs-lookup"><span data-stu-id="a9d80-157">Replace *HardDrivePath* with the path where the MDATPClientAnalyzer tool was downloaded to, for example</span></span>
    
<span data-ttu-id="a9d80-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span><span class="sxs-lookup"><span data-stu-id="a9d80-158">**C:\Work\tools\MDATPClientAnalyzer\MDATPClientAnalyzer.cmd**</span></span>


5.  <span data-ttu-id="a9d80-159">Извлеките файл **MDATPClientAnalyzerResult.zip** _, созданный с помощью средства, в папку, используемую в _HardDrivePath\*.</span><span class="sxs-lookup"><span data-stu-id="a9d80-159">Extract the **MDATPClientAnalyzerResult.zip** _ file created by tool in the folder used in the _HardDrivePath\*.</span></span>

6.  <span data-ttu-id="a9d80-160">Откройте **MDATPClientAnalyzerResult.txt** и убедитесь в том, что вы выполнили действия по настройке прокси-сервера, чтобы включить обнаружение сервера и доступ к URL-адресам службы.</span><span class="sxs-lookup"><span data-stu-id="a9d80-160">Open **MDATPClientAnalyzerResult.txt** and verify that you have performed the proxy configuration steps to enable server discovery and access to the service URLs.</span></span>  <span data-ttu-id="a9d80-161">Средство проверяет возможность подключения URL-адресов службы Защитника для конечной точки, которые настроены для работы службы Защитника для конечной точки с клиентом.</span><span class="sxs-lookup"><span data-stu-id="a9d80-161">The tool checks the connectivity of Defender for Endpoint service URLs that Defender for Endpoint client is configured to interact with.</span></span> <span data-ttu-id="a9d80-162">Затем результаты выводятся в файл **MDATPClientAnalyzerResult.txt** для каждого URL-адреса, который потенциально можно использоваться для общения с Защитником для служб конечных точек.</span><span class="sxs-lookup"><span data-stu-id="a9d80-162">It then prints the results into the **MDATPClientAnalyzerResult.txt** file for each URL that can potentially be used to communicate with the Defender for Endpoint services.</span></span> <span data-ttu-id="a9d80-163">Пример:</span><span class="sxs-lookup"><span data-stu-id="a9d80-163">For example:</span></span>

    <span data-ttu-id="a9d80-164">**Проверочный URL-адрес: https://xxx.microsoft.com/xxx </br> 1 — прокси-сервер по умолчанию: успешно (200) </br> 2 — автоматическое обнаружение прокси (WPAD): успешно (200)</br> 3 — прокси отключен: успешно (200)</br> 4 — именованный прокси: не существует</br> 5 — прокси-сервер командной строки: не существует**</span><span class="sxs-lookup"><span data-stu-id="a9d80-164">**Testing URL: https://xxx.microsoft.com/xxx </br> 1 - Default proxy: Succeeded (200) </br> 2 - Proxy auto discovery (WPAD): Succeeded (200)</br> 3 - Proxy disabled: Succeeded (200)</br> 4 - Named proxy: Doesn't exist</br> 5 - Command-line proxy: Doesn't exist**</span></span></br>


<span data-ttu-id="a9d80-165">Если по крайней мере один из вариантов подключения возвращает состояние (200), то клиент Defender для конечной точки может правильно взаимодействовать с проверенным URL-адресом, используя этот метод подключения.</span><span class="sxs-lookup"><span data-stu-id="a9d80-165">If at least one of the connectivity options returns a (200) status, then the Defender for Endpoint client can communicate with the tested URL properly using this connectivity method.</span></span> 

<span data-ttu-id="a9d80-166">Однако, если результаты проверки подключения указывают на сбой, отображается ошибка HTTP (см. Коды состояния HTTP).</span><span class="sxs-lookup"><span data-stu-id="a9d80-166">However, if the connectivity check results indicate a failure, an HTTP error is displayed (see HTTP Status Codes).</span></span> <span data-ttu-id="a9d80-167">Затем вы можете использовать URL-адреса в таблице, приведенной в статья [Разрешение доступа к URL-адресам облачной службы Endpoint DLP на прокси-сервере](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span><span class="sxs-lookup"><span data-stu-id="a9d80-167">You can then use the URLs in the table shown in [Enable access to Endpoint DLP cloud service URLs in the proxy server](#enable-access-to-endpoint-dlp-cloud-service-urls-in-the-proxy-server).</span></span> <span data-ttu-id="a9d80-168">Используемые URL будут зависеть от региона, выбранного во время процедуры подключения.</span><span class="sxs-lookup"><span data-stu-id="a9d80-168">The URLs you’ll use will depend on the region selected during the onboarding procedure.</span></span>
[!NOTE]<span data-ttu-id="a9d80-169"> Анализатор подключений не совместим с правилом ASR — [Блокировка создания процессов, исходящих от команд PSExec и WMI](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span><span class="sxs-lookup"><span data-stu-id="a9d80-169"> The Connectivity Analyzer tool is not compatible with ASR rule [Block process creations originating from PSExec and WMI commands](/windows/security/threat-protection/windows-defender-exploit-guard/attack-surface-reduction#attack-surface-reduction-rules).</span></span> <span data-ttu-id="a9d80-170">Необходимо временно отключить это правило, чтобы запустить средство подключения.</span><span class="sxs-lookup"><span data-stu-id="a9d80-170">You will need to temporarily disable this rule to run the connectivity tool.</span></span>

[!NOTE] <span data-ttu-id="a9d80-171">Если задано значение TelemetryProxyServer, в реестре или с помощью групповой политики, Защитник для конечной точки вернется, если не сможет получить доступ к определенному прокси.</span><span class="sxs-lookup"><span data-stu-id="a9d80-171">When the TelemetryProxyServer is set, in Registry or via Group Policy, Defender for Endpoint will fall back to direct if it can’t access the defined proxy.</span></span>
<span data-ttu-id="a9d80-172">Статьи по теме •   Встроенные устройства с Windows 10  •   Устранение неполадок с подключением к Microsoft Endpoint DLP</span><span class="sxs-lookup"><span data-stu-id="a9d80-172">Related topics •   Onboard Windows 10 devices •   Troubleshoot Microsoft Endpoint DLP onboarding issues</span></span>





## <a name="see-also"></a><span data-ttu-id="a9d80-173">См. также</span><span class="sxs-lookup"><span data-stu-id="a9d80-173">See also</span></span>

- [<span data-ttu-id="a9d80-174">Сведения о защите от потери данных в конечной точке </span><span class="sxs-lookup"><span data-stu-id="a9d80-174">Learn about Endpoint data loss prevention </span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="a9d80-175">Использование защиты от потери данных в конечной точке </span><span class="sxs-lookup"><span data-stu-id="a9d80-175">Using Endpoint data loss prevention </span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="a9d80-176">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="a9d80-176">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="a9d80-177">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="a9d80-177">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="a9d80-178">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="a9d80-178">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="a9d80-179">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="a9d80-179">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="a9d80-180">Средства и методы подключения для компьютеров с Windows 10</span><span class="sxs-lookup"><span data-stu-id="a9d80-180">Onboarding tools and methods for Windows 10 machines</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)
- [<span data-ttu-id="a9d80-181">Подписка на Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="a9d80-181">Microsoft 365 subscription</span></span>](https://www.microsoft.com/microsoft-365/compare-microsoft-365-enterprise-plans?rtc=1)
- [<span data-ttu-id="a9d80-182">Устройства, подключенные к Azure AD</span><span class="sxs-lookup"><span data-stu-id="a9d80-182">Azure AD joined devices</span></span>](/azure/active-directory/devices/concept-azure-ad-join)
- [<span data-ttu-id="a9d80-183">Загрузка нового браузера Microsoft Edge на основе Chromium</span><span class="sxs-lookup"><span data-stu-id="a9d80-183">Download the new Microsoft Edge based on Chromium</span></span>](https://support.microsoft.com/help/4501095/download-the-new-microsoft-edge-based-on-chromium)