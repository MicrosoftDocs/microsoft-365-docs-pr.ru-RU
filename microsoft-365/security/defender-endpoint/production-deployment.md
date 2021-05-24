---
title: Настройка microsoft Defender для развертывания конечных точек
description: Узнайте, как настроить развертывание для Microsoft Defender для конечной точки
keywords: развертывание, настройка, проверка лицензирования, конфигурация клиента, конфигурация сети
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
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-scenario
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b49565c45c1f38d0d2ce71b097af079782ba4de
ms.sourcegitcommit: 17f0aada83627d9defa0acf4db03a2d58e46842f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/24/2021
ms.locfileid: "52636198"
---
# <a name="set-up-microsoft-defender-for-endpoint-deployment"></a><span data-ttu-id="b528a-104">Настройка microsoft Defender для развертывания конечных точек</span><span class="sxs-lookup"><span data-stu-id="b528a-104">Set up Microsoft Defender for Endpoint deployment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b528a-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b528a-105">**Applies to:**</span></span>
- [<span data-ttu-id="b528a-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b528a-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b528a-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b528a-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="b528a-108">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="b528a-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="b528a-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="b528a-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="b528a-110">Развертывание Defender для конечной точки — это трех этапный процесс:</span><span class="sxs-lookup"><span data-stu-id="b528a-110">Deploying Defender for Endpoint is a three-phase process:</span></span>

| <span data-ttu-id="b528a-111">[![этап развертывания — подготовка](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span><span class="sxs-lookup"><span data-stu-id="b528a-111">[![deployment phase - prepare](images/phase-diagrams/prepare.png)](prepare-deployment.md)</span></span><br>[<span data-ttu-id="b528a-112">Этап 1. Подготовка</span><span class="sxs-lookup"><span data-stu-id="b528a-112">Phase 1: Prepare</span></span>](prepare-deployment.md) | ![этап развертывания — установка](images/phase-diagrams/setup.png)<br><span data-ttu-id="b528a-114">Этап 2. Настройка</span><span class="sxs-lookup"><span data-stu-id="b528a-114">Phase 2: Setup</span></span> | <span data-ttu-id="b528a-115">[![этап развертывания — на борту](images/phase-diagrams/onboard.png)](onboarding.md)</span><span class="sxs-lookup"><span data-stu-id="b528a-115">[![deployment phase - onboard](images/phase-diagrams/onboard.png)](onboarding.md)</span></span><br>[<span data-ttu-id="b528a-116">Этап 3. Подключение</span><span class="sxs-lookup"><span data-stu-id="b528a-116">Phase 3: Onboard</span></span>](onboarding.md) |
| ----- | ----- | ----- |
| | <span data-ttu-id="b528a-117">*Вы здесь!*</span><span class="sxs-lookup"><span data-stu-id="b528a-117">*You are here!*</span></span>||

<span data-ttu-id="b528a-118">В настоящее время вы находитесь на этапе настройка.</span><span class="sxs-lookup"><span data-stu-id="b528a-118">You are currently in the set-up phase.</span></span>

<span data-ttu-id="b528a-119">В этом сценарии развертывания вы будете руководствоваться действиями по:</span><span class="sxs-lookup"><span data-stu-id="b528a-119">In this deployment scenario, you'll be guided through the steps on:</span></span>
- <span data-ttu-id="b528a-120">Проверка лицензирования</span><span class="sxs-lookup"><span data-stu-id="b528a-120">Licensing validation</span></span>
- <span data-ttu-id="b528a-121">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="b528a-121">Tenant configuration</span></span>
- <span data-ttu-id="b528a-122">Конфигурация сети</span><span class="sxs-lookup"><span data-stu-id="b528a-122">Network configuration</span></span>


>[!NOTE]
><span data-ttu-id="b528a-123">Для того, чтобы направлять вас через типичное развертывание, этот сценарий будет охватывать только использование Microsoft Endpoint Configuration Manager.</span><span class="sxs-lookup"><span data-stu-id="b528a-123">For the purpose of guiding you through a typical deployment, this scenario will only cover the use of Microsoft Endpoint Configuration Manager.</span></span> <span data-ttu-id="b528a-124">Defender for Endpoint поддерживает использование других средств бортового использования, но не покрывает эти сценарии в руководстве по развертыванию.</span><span class="sxs-lookup"><span data-stu-id="b528a-124">Defender for Endpoint supports the use of other onboarding tools but won't cover those scenarios in the deployment guide.</span></span> <span data-ttu-id="b528a-125">Дополнительные сведения см. в таблице [Onboard devices to Microsoft Defender for Endpoint.](onboard-configure.md)</span><span class="sxs-lookup"><span data-stu-id="b528a-125">For more information, see [Onboard devices to Microsoft Defender for Endpoint](onboard-configure.md).</span></span>

## <a name="check-license-state"></a><span data-ttu-id="b528a-126">Проверка состояния лицензии</span><span class="sxs-lookup"><span data-stu-id="b528a-126">Check license state</span></span>

<span data-ttu-id="b528a-127">Проверка состояния лицензии и правильного ее состояния можно сделать через центр администрирования или на **портале Microsoft Azure.**</span><span class="sxs-lookup"><span data-stu-id="b528a-127">Checking for the license state and whether it got properly provisioned, can be done through the admin center or through the **Microsoft Azure portal**.</span></span>

1. <span data-ttu-id="b528a-128">Чтобы просмотреть лицензии, перейдите на портал **Microsoft Azure и** перейдите в раздел лицензии Microsoft Azure [портала](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span><span class="sxs-lookup"><span data-stu-id="b528a-128">To view your licenses, go to the **Microsoft Azure portal** and navigate to the [Microsoft Azure portal license section](https://portal.azure.com/#blade/Microsoft_AAD_IAM/LicensesMenuBlade/Products).</span></span>

   ![Изображение страницы лицензирования Azure](images/atp-licensing-azure-portal.png)

1. <span data-ttu-id="b528a-130">Поочередно в центре администрирования перейдите к **подпискам на**  >  **биллинг.**</span><span class="sxs-lookup"><span data-stu-id="b528a-130">Alternately, in the admin center, navigate to **Billing** > **Subscriptions**.</span></span>

    <span data-ttu-id="b528a-131">На экране вы увидите все предварительные лицензии и их текущее **состояние.**</span><span class="sxs-lookup"><span data-stu-id="b528a-131">On the screen, you'll see all the provisioned licenses and their current **Status**.</span></span>

    ![Изображение лицензий на выставление счета](images/atp-billing-subscriptions.png)


## <a name="cloud-service-provider-validation"></a><span data-ttu-id="b528a-133">Проверка поставщика облачных услуг</span><span class="sxs-lookup"><span data-stu-id="b528a-133">Cloud Service Provider validation</span></span>

<span data-ttu-id="b528a-134">Чтобы получить доступ к лицензиям вашей компании и проверить состояние лицензий, перейдите в центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="b528a-134">To gain access into which licenses are provisioned to your company, and to check the state of the licenses, go to the admin center.</span></span>

1. <span data-ttu-id="b528a-135">На **портале Partner** выберите **администрирование > Office 365.**</span><span class="sxs-lookup"><span data-stu-id="b528a-135">From the **Partner portal**, select **Administer services > Office 365**.</span></span>

2. <span data-ttu-id="b528a-136">Щелкнув ссылку **на портал Партнер,** вы откроете параметр **Admin** от имени и откроет доступ к центру администрирования клиентов.</span><span class="sxs-lookup"><span data-stu-id="b528a-136">Clicking on the **Partner portal** link will open the **Admin on behalf** option and will give you access to the customer admin center.</span></span>

   ![Изображение портала администрирования O365](images/atp-O365-admin-portal-customer.png)



## <a name="tenant-configuration"></a><span data-ttu-id="b528a-138">Конфигурация клиента</span><span class="sxs-lookup"><span data-stu-id="b528a-138">Tenant Configuration</span></span>
<span data-ttu-id="b528a-139">Простота в microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b528a-139">Onboarding to Microsoft Defender for Endpoint is easy.</span></span> <span data-ttu-id="b528a-140">В меню навигации выберите любой элемент в разделе Endpoints или любую функцию Microsoft 365 Defender, такие как Incidents, Hunting, Action Center или Threat Analytics, чтобы инициировать процесс взбора.</span><span class="sxs-lookup"><span data-stu-id="b528a-140">From the navigation menu, select any item under the Endpoints section, or any Microsoft 365 Defender feature such as Incidents, Hunting, Action center, or Threat analytics to initiate the onboarding process.</span></span>

<span data-ttu-id="b528a-141">Из веб-браузера перейдите [в центр Microsoft 365 безопасности](https://security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="b528a-141">From a web browser, navigate to the [Microsoft 365 Security Center](https://security.microsoft.com).</span></span>

## <a name="network-configuration"></a><span data-ttu-id="b528a-142">Конфигурация сети</span><span class="sxs-lookup"><span data-stu-id="b528a-142">Network configuration</span></span>
<span data-ttu-id="b528a-143">Если организации не требуется, чтобы конечные точки использовали прокси для доступа к Интернету, пропустите этот раздел.</span><span class="sxs-lookup"><span data-stu-id="b528a-143">If the organization doesn't require the endpoints to use a Proxy to access the Internet, skip this section.</span></span>

<span data-ttu-id="b528a-144">Для использования датчика Microsoft Defender для конечной точки требуется Microsoft Windows HTTP (WinHTTP), чтобы передавать данные датчика и общаться со службой Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b528a-144">The Microsoft Defender for Endpoint sensor requires Microsoft Windows HTTP (WinHTTP) to report sensor data and communicate with the Microsoft Defender for Endpoint service.</span></span> <span data-ttu-id="b528a-145">Встроенный датчик Microsoft Defender для конечной точки запускается в системном контексте с помощью учетной записи LocalSystem.</span><span class="sxs-lookup"><span data-stu-id="b528a-145">The embedded Microsoft Defender for Endpoint sensor runs in the system context using the LocalSystem account.</span></span> <span data-ttu-id="b528a-146">Датчик использует Microsoft Windows HTTP Services (WinHTTP), чтобы обеспечить взаимодействие с облачной службой Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="b528a-146">The sensor uses Microsoft Windows HTTP Services (WinHTTP) to enable communication with the Microsoft Defender for Endpoint cloud service.</span></span> <span data-ttu-id="b528a-147">Параметр конфигурации WinHTTP не зависит от параметров прокси Windows Интернета (WinINet) и может обнаружить прокси-сервер только с помощью следующих методов обнаружения:</span><span class="sxs-lookup"><span data-stu-id="b528a-147">The WinHTTP configuration setting is independent of the Windows Internet (WinINet) internet browsing proxy settings and can only discover a proxy server by using the following discovery methods:</span></span>

<span data-ttu-id="b528a-148">**Методы автооткрытия:**</span><span class="sxs-lookup"><span data-stu-id="b528a-148">**Autodiscovery methods:**</span></span>

-   <span data-ttu-id="b528a-149">Прозрачный прокси</span><span class="sxs-lookup"><span data-stu-id="b528a-149">Transparent proxy</span></span>

-   <span data-ttu-id="b528a-150">Протокол автообнаружия веб-прокси (WPAD)</span><span class="sxs-lookup"><span data-stu-id="b528a-150">Web Proxy Autodiscovery Protocol (WPAD)</span></span>

<span data-ttu-id="b528a-151">Если в топологии сети реализован прозрачный прокси или WPAD, нет необходимости в специальных параметрах конфигурации.</span><span class="sxs-lookup"><span data-stu-id="b528a-151">If a Transparent proxy or WPAD has been implemented in the network topology, there is no need for special configuration settings.</span></span> <span data-ttu-id="b528a-152">Дополнительные сведения об исключениях URL-адресов Microsoft Defender [](production-deployment.md#proxy-service-urls) для конечной точки в прокси-сервере см. в разделе URL-адреса прокси-службы в этом документе для url-адресов, разрешаемых URL-адресами, или в настройках параметров прокси-сервера и подключения к [Интернету.](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)</span><span class="sxs-lookup"><span data-stu-id="b528a-152">For more information on Microsoft Defender for Endpoint URL exclusions in the proxy, see the [Proxy Service URLs](production-deployment.md#proxy-service-urls) section in this document for the URLs allow list or on [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server).</span></span>

<span data-ttu-id="b528a-153">**Конфигурация статического прокси вручную:**</span><span class="sxs-lookup"><span data-stu-id="b528a-153">**Manual static proxy configuration:**</span></span>

-   <span data-ttu-id="b528a-154">Конфигурация на основе реестра</span><span class="sxs-lookup"><span data-stu-id="b528a-154">Registry-based configuration</span></span>

-   <span data-ttu-id="b528a-155">WinHTTP, настроенный с помощью команды netsh</span><span class="sxs-lookup"><span data-stu-id="b528a-155">WinHTTP configured using netsh command</span></span> <br> <span data-ttu-id="b528a-156">Подходит только для настольных компьютеров в стабильной топологии (например: рабочий стол в корпоративной сети за одним прокси-сервером)</span><span class="sxs-lookup"><span data-stu-id="b528a-156">Suitable only for desktops in a stable topology (for example: a desktop in a corporate network behind the same proxy)</span></span>

### <a name="configure-the-proxy-server-manually-using-a-registry-based-static-proxy"></a><span data-ttu-id="b528a-157">Настройка прокси-сервера вручную с использованием статического прокси-сервера на основе реестра</span><span class="sxs-lookup"><span data-stu-id="b528a-157">Configure the proxy server manually using a registry-based static proxy</span></span>

<span data-ttu-id="b528a-158">Настройка статического прокси-сервера на основе реестра, чтобы разрешить только датчику Microsoft Defender для конечных точек сообщать диагностические данные и общаться с службами Microsoft Defender для конечных точек, если компьютеру не разрешено подключение к Интернету.</span><span class="sxs-lookup"><span data-stu-id="b528a-158">Configure a registry-based static proxy to allow only Microsoft Defender for Endpoint sensor to report diagnostic data and communicate with Microsoft Defender for Endpoint services if a computer isn't permitted to connect to the Internet.</span></span> <span data-ttu-id="b528a-159">Статический прокси-сервер можно настроить с помощью групповой политики (GP).</span><span class="sxs-lookup"><span data-stu-id="b528a-159">The static proxy is configurable through Group Policy (GP).</span></span> <span data-ttu-id="b528a-160">Групповые политики можно найти в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="b528a-160">The group policy can be found under:</span></span>

 - <span data-ttu-id="b528a-161">Административные шаблоны Windows сбор данных компонентов и сборки предварительного просмотра Настраивают использование прокси-серверов для службы подключенных пользователей и \> \> \> телеметрии</span><span class="sxs-lookup"><span data-stu-id="b528a-161">Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service</span></span>
     - <span data-ttu-id="b528a-162">Установите его для **включения и** выберите отключение использования **прокси-сервера с проверкой подлинности**</span><span class="sxs-lookup"><span data-stu-id="b528a-162">Set it to **Enabled** and select **Disable Authenticated Proxy usage**</span></span>

1. <span data-ttu-id="b528a-163">Откройте консоль управления групповыми политиками.</span><span class="sxs-lookup"><span data-stu-id="b528a-163">Open the Group Policy Management Console.</span></span>
2. <span data-ttu-id="b528a-164">Создайте политику или отредактировать существующую политику, основанную на организационных практиках.</span><span class="sxs-lookup"><span data-stu-id="b528a-164">Create a policy or edit an existing policy based off the organizational practices.</span></span>
3. <span data-ttu-id="b528a-165">Изменение групповой политики и переход к административным шаблонам Windows сбор данных компонентов и сборки предварительного просмотра Настройка использования прокси-серверов для подключенных пользователей и службы **\> \> \> телеметрии**.</span><span class="sxs-lookup"><span data-stu-id="b528a-165">Edit the Group Policy and navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure Authenticated Proxy usage for the Connected User Experience and Telemetry Service**.</span></span> 
    <span data-ttu-id="b528a-166">![Изображение конфигурации групповой политики](images/atp-gpo-proxy1.png)</span><span class="sxs-lookup"><span data-stu-id="b528a-166">![Image of Group Policy configuration](images/atp-gpo-proxy1.png)</span></span>

4. <span data-ttu-id="b528a-167">Щелкните **Включено**.</span><span class="sxs-lookup"><span data-stu-id="b528a-167">Select **Enabled**.</span></span>
5. <span data-ttu-id="b528a-168">Выберите **отключение использования прокси-сервера с проверкой подлинности.**</span><span class="sxs-lookup"><span data-stu-id="b528a-168">Select **Disable Authenticated Proxy usage**.</span></span>
   
6. <span data-ttu-id="b528a-169">Перейдите к административным шаблонам Windows сбору данных компонентов и сборкам предварительного просмотра Настройка подключенных пользовательских интерфейсов **\> и \> \> телеметрии.**</span><span class="sxs-lookup"><span data-stu-id="b528a-169">Navigate to **Administrative Templates \> Windows Components \> Data Collection and Preview Builds \> Configure connected user experiences and telemetry**.</span></span>
    <span data-ttu-id="b528a-170">![Изображение параметра конфигурации групповой политики](images/atp-gpo-proxy2.png)</span><span class="sxs-lookup"><span data-stu-id="b528a-170">![Image of Group Policy configuration setting](images/atp-gpo-proxy2.png)</span></span>
7. <span data-ttu-id="b528a-171">Щелкните **Включено**.</span><span class="sxs-lookup"><span data-stu-id="b528a-171">Select **Enabled**.</span></span>
8. <span data-ttu-id="b528a-172">Введите **имя прокси-сервера**.</span><span class="sxs-lookup"><span data-stu-id="b528a-172">Enter the **Proxy Server Name**.</span></span>

<span data-ttu-id="b528a-173">Политика устанавливает два значения реестра: `TelemetryProxyServer` как REG_SZ и `DisableEnterpriseAuthProxy` как REG_DWORD в разделе реестра `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span><span class="sxs-lookup"><span data-stu-id="b528a-173">The policy sets two registry values `TelemetryProxyServer` as REG_SZ and `DisableEnterpriseAuthProxy` as REG_DWORD under the registry key `HKLM\Software\Policies\Microsoft\Windows\DataCollection`.</span></span>

<span data-ttu-id="b528a-174">Значение реестра принимает `TelemetryProxyServer` следующий формат строки:</span><span class="sxs-lookup"><span data-stu-id="b528a-174">The registry value `TelemetryProxyServer` takes the following string format:</span></span>

```text
<server name or ip>:<port>
```

<span data-ttu-id="b528a-175">Например, 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="b528a-175">For example: 10.0.0.6:8080</span></span>

<span data-ttu-id="b528a-176">Следует назначить значение реестра `DisableEnterpriseAuthProxy` — 1.</span><span class="sxs-lookup"><span data-stu-id="b528a-176">The registry value `DisableEnterpriseAuthProxy` should be set to 1.</span></span>

###  <a name="configure-the-proxy-server-manually-using-netsh-command"></a><span data-ttu-id="b528a-177">Настройка прокси-сервера вручную с помощью команды netsh</span><span class="sxs-lookup"><span data-stu-id="b528a-177">Configure the proxy server manually using netsh command</span></span>

<span data-ttu-id="b528a-178">Используйте команду netsh для настройки статического прокси на уровне системы.</span><span class="sxs-lookup"><span data-stu-id="b528a-178">Use netsh to configure a system-wide static proxy.</span></span>

> [!NOTE]
> - <span data-ttu-id="b528a-179">Это повлияет на все приложения, в том числе службы Windows, которые используют WinHTTP с прокси по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="b528a-179">This will affect all applications including Windows services which use WinHTTP with default proxy.</span></span></br>
> - <span data-ttu-id="b528a-180">Ноутбуки, которые меняют топологию (например, из офиса в дом), будут неисправными с сеткой.</span><span class="sxs-lookup"><span data-stu-id="b528a-180">Laptops that are changing topology (for example: from office to home) will malfunction with netsh.</span></span> <span data-ttu-id="b528a-181">Используйте настройку статических прокси-серверов на основе реестра.</span><span class="sxs-lookup"><span data-stu-id="b528a-181">Use the registry-based static proxy configuration.</span></span>

1. <span data-ttu-id="b528a-182">Откройте командную строку с повышенными правами:</span><span class="sxs-lookup"><span data-stu-id="b528a-182">Open an elevated command line:</span></span>

    1. <span data-ttu-id="b528a-183">В меню **Пуск** введите **cmd**.</span><span class="sxs-lookup"><span data-stu-id="b528a-183">Go to **Start** and type **cmd**.</span></span>

    1. <span data-ttu-id="b528a-184">Щелкните правой кнопкой мыши пункт **Командная строка** и выберите команду **Запуск от имени администратора**.</span><span class="sxs-lookup"><span data-stu-id="b528a-184">Right-click **Command prompt** and select **Run as administrator**.</span></span>

2. <span data-ttu-id="b528a-185">Введите следующую команду и нажмите клавишу **ВВОД**:</span><span class="sxs-lookup"><span data-stu-id="b528a-185">Enter the following command and press **Enter**:</span></span>

   ```PowerShell
   netsh winhttp set proxy <proxy>:<port>
   ```

   <span data-ttu-id="b528a-186">Например, netsh winhttp set proxy 10.0.0.6:8080</span><span class="sxs-lookup"><span data-stu-id="b528a-186">For example: netsh winhttp set proxy 10.0.0.6:8080</span></span>


###  <a name="proxy-configuration-for-down-level-devices"></a><span data-ttu-id="b528a-187">Конфигурация прокси для устройств с уровнем ниже уровня</span><span class="sxs-lookup"><span data-stu-id="b528a-187">Proxy Configuration for down-level devices</span></span>

<span data-ttu-id="b528a-188">Down-Level устройства включают Windows 7 рабочих станций SP1 и Windows 8.1, а также Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2 и версии Windows Server 2016 до Windows Server CB 1803.</span><span class="sxs-lookup"><span data-stu-id="b528a-188">Down-Level devices include Windows 7 SP1 and Windows 8.1 workstations as well as Windows Server 2008 R2, Windows Server 2012, Windows Server 2012 R2, and versions of Windows Server 2016 prior to Windows Server CB 1803.</span></span> <span data-ttu-id="b528a-189">Эти операционные системы будут иметь прокси-сервер, настроенный в составе агента управления Майкрософт для обработки связи с конечной точки до Azure.</span><span class="sxs-lookup"><span data-stu-id="b528a-189">These operating systems will have the proxy configured as part of the Microsoft Management Agent to handle communication from the endpoint to Azure.</span></span> <span data-ttu-id="b528a-190">Сведения о настройке прокси-сервера на этих устройствах можно найти в руководстве по быстрому развертыванию агента Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="b528a-190">Refer to the Microsoft Management Agent Fast Deployment Guide for information on how a proxy is configured on these devices.</span></span>

### <a name="proxy-service-urls"></a><span data-ttu-id="b528a-191">URL-адреса службы прокси</span><span class="sxs-lookup"><span data-stu-id="b528a-191">Proxy Service URLs</span></span>
<span data-ttu-id="b528a-192">URL-адреса, которые включают в них v20, необходимы только при Windows 10, версии 1803 или более поздних устройствах.</span><span class="sxs-lookup"><span data-stu-id="b528a-192">URLs that include v20 in them are only needed if you have Windows 10, version 1803 or later devices.</span></span> <span data-ttu-id="b528a-193">Например, требуется только если устройство находится на Windows 10 ```us-v20.events.data.microsoft.com``` версии 1803 или более поздней версии.</span><span class="sxs-lookup"><span data-stu-id="b528a-193">For example, ```us-v20.events.data.microsoft.com``` is only needed if the device is on Windows 10, version 1803 or later.</span></span>
 

<span data-ttu-id="b528a-194">Если прокси-сервер или брандмауэр блокирует анонимный трафик, так как датчик Microsoft Defender для конечных точек подключается из системного контекста, убедитесь, что анонимный трафик разрешен в указанных URL-адресах.</span><span class="sxs-lookup"><span data-stu-id="b528a-194">If a proxy or firewall is blocking anonymous traffic, as Microsoft Defender for Endpoint sensor is connecting from system context, make sure anonymous traffic is permitted in the listed URLs.</span></span>

<span data-ttu-id="b528a-195">В следующей загружаемой таблице перечислены службы и связанные с ними URL-адреса, к которые должна подключаться ваша сеть.</span><span class="sxs-lookup"><span data-stu-id="b528a-195">The following downloadable spreadsheet lists the services and their associated URLs that your network must be able to connect to.</span></span> <span data-ttu-id="b528a-196">Убедитесь, что нет брандмауэра или правил фильтрации сети, которые бы  отказывали в доступе к этим URL-адресам, или вам может потребоваться создать правило разрешить специально для них.</span><span class="sxs-lookup"><span data-stu-id="b528a-196">Ensure there are no firewall or network filtering rules that would deny access to these URLs, or you may need to create an *allow* rule specifically for them.</span></span>

|<span data-ttu-id="b528a-197">**Таблица списка доменов**</span><span class="sxs-lookup"><span data-stu-id="b528a-197">**Spreadsheet of domains list**</span></span>|<span data-ttu-id="b528a-198">**Описание**</span><span class="sxs-lookup"><span data-stu-id="b528a-198">**Description**</span></span>|
|:-----|:-----|
|![Изображение пальца для таблицы URL-адресов Microsoft Defender для конечных точек](images/mdatp-urls.png)<br/>  | <span data-ttu-id="b528a-200">Таблица определенных DNS-записей для расположения служб, географических местоположений и ОС.</span><span class="sxs-lookup"><span data-stu-id="b528a-200">Spreadsheet of specific DNS records for service locations, geographic locations, and OS.</span></span> <br><br>[<span data-ttu-id="b528a-201">Скачайте таблицу здесь.</span><span class="sxs-lookup"><span data-stu-id="b528a-201">Download the spreadsheet here.</span></span>](https://download.microsoft.com/download/8/a/5/8a51eee5-cd02-431c-9d78-a58b7f77c070/mde-urls.xlsx) 


###  <a name="microsoft-defender-for-endpoint-service-backend-ip-ranges"></a><span data-ttu-id="b528a-202">Защитник Microsoft для конечных диапазонов IP-адресов службы конечных точек</span><span class="sxs-lookup"><span data-stu-id="b528a-202">Microsoft Defender for Endpoint service backend IP ranges</span></span>

<span data-ttu-id="b528a-203">Если сетевые устройства не поддерживают правила на основе DNS, используйте ip-диапазоны.</span><span class="sxs-lookup"><span data-stu-id="b528a-203">If your network devices don't support DNS-based rules, use IP ranges instead.</span></span>

<span data-ttu-id="b528a-204">Defender for Endpoint построен в облаке Azure, развернутом в следующих регионах:</span><span class="sxs-lookup"><span data-stu-id="b528a-204">Defender for Endpoint is built in Azure cloud, deployed in the following regions:</span></span>

- <span data-ttu-id="b528a-205">AzureCloud.eastus</span><span class="sxs-lookup"><span data-stu-id="b528a-205">AzureCloud.eastus</span></span>
- <span data-ttu-id="b528a-206">AzureCloud.eastus2</span><span class="sxs-lookup"><span data-stu-id="b528a-206">AzureCloud.eastus2</span></span>
- <span data-ttu-id="b528a-207">AzureCloud.westcentralus</span><span class="sxs-lookup"><span data-stu-id="b528a-207">AzureCloud.westcentralus</span></span>
- <span data-ttu-id="b528a-208">AzureCloud.northeurope</span><span class="sxs-lookup"><span data-stu-id="b528a-208">AzureCloud.northeurope</span></span>
- <span data-ttu-id="b528a-209">AzureCloud.westeurope</span><span class="sxs-lookup"><span data-stu-id="b528a-209">AzureCloud.westeurope</span></span>
- <span data-ttu-id="b528a-210">AzureCloud.uksouth</span><span class="sxs-lookup"><span data-stu-id="b528a-210">AzureCloud.uksouth</span></span>
- <span data-ttu-id="b528a-211">AzureCloud.ukwest</span><span class="sxs-lookup"><span data-stu-id="b528a-211">AzureCloud.ukwest</span></span>

<span data-ttu-id="b528a-212">Диапазоны IP-адресов Azure можно найти в [диапазонах IP-адресов Azure](https://www.microsoft.com/download/details.aspx?id=56519)и тегах service Tags — Public Cloud.</span><span class="sxs-lookup"><span data-stu-id="b528a-212">You can find the Azure IP ranges in [Azure IP Ranges and Service Tags – Public Cloud](https://www.microsoft.com/download/details.aspx?id=56519).</span></span>

> [!NOTE]
> <span data-ttu-id="b528a-213">В качестве облачного решения диапазоны IP-адресов могут изменяться.</span><span class="sxs-lookup"><span data-stu-id="b528a-213">As a cloud-based solution, the IP address ranges can change.</span></span> <span data-ttu-id="b528a-214">Рекомендуется перейти к правилам, основанным на DNS.</span><span class="sxs-lookup"><span data-stu-id="b528a-214">It's recommended you move to DNS-based rules.</span></span>

> [!NOTE]
> <span data-ttu-id="b528a-215">Если вы клиент правительства США, см. соответствующий раздел на странице [Защитник для конечной](gov.md#service-backend-ip-ranges) точки для правительства США.</span><span class="sxs-lookup"><span data-stu-id="b528a-215">If you are a US Government customer, please see the corresponding section in the [Defender for Endpoint for US Government](gov.md#service-backend-ip-ranges) page.</span></span>

## <a name="next-step"></a><span data-ttu-id="b528a-216">Следующий шаг</span><span class="sxs-lookup"><span data-stu-id="b528a-216">Next step</span></span>

<span data-ttu-id="b528a-217">![**Фаза 3. На борту**](images/onboard.png)</span><span class="sxs-lookup"><span data-stu-id="b528a-217">![**Phase 3: Onboard**](images/onboard.png)</span></span> <br><span data-ttu-id="b528a-218">[Этап 3. На](onboarding.md)борту: бортовые устройства для службы, чтобы служба Microsoft Defender для конечных точек может получать данные датчиков от них.</span><span class="sxs-lookup"><span data-stu-id="b528a-218">[Phase 3: Onboard](onboarding.md): Onboard devices to the service so that the Microsoft Defender for Endpoint service can get sensor data from them.</span></span> 
