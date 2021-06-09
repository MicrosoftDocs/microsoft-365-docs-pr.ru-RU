---
title: Обнаружение и управление уязвимостями
description: Рекомендации по безопасности и обнаружение уязвимостей теперь доступны для операционных систем коммутаторов, маршрутизаторов, контроллеров WLAN и брандмауэров.
keywords: обнаружение уязвимостей сетевых устройств, операционных систем коммутаторов, маршрутизаторов, контроллеров WLAN и брандмауэров
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: ellevin
author: levinec
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: da15519211599bfc248c20c36cfab456c1661caa
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/16/2021
ms.locfileid: "51862071"
---
# <a name="network-device-discovery-and-vulnerability-management"></a><span data-ttu-id="f6780-104">Обнаружение и управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="f6780-104">Network device discovery and vulnerability management</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="f6780-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f6780-105">**Applies to:**</span></span>

- [<span data-ttu-id="f6780-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f6780-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="f6780-107">Угроза и управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="f6780-107">Threat and vulnerability management</span></span>](next-gen-threat-and-vuln-mgt.md)
- [<span data-ttu-id="f6780-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f6780-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!IMPORTANT]
> <span data-ttu-id="f6780-109">**Сканирование и управление сетевыми устройствами в настоящее время находятся в общедоступных предварительных просмотрах**</span><span class="sxs-lookup"><span data-stu-id="f6780-109">**Scanning and managing network devices is currently in public preview**</span></span><br>
> <span data-ttu-id="f6780-110">Эта версия предварительного просмотра предоставляется без соглашения об уровне обслуживания и не рекомендуется для рабочих нагрузок.</span><span class="sxs-lookup"><span data-stu-id="f6780-110">This preview version is provided without a service level agreement, and it's not recommended for production workloads.</span></span> <span data-ttu-id="f6780-111">Некоторые функции могут не поддерживаться или иметь ограниченные возможности.</span><span class="sxs-lookup"><span data-stu-id="f6780-111">Certain features might not be supported or might have constrained capabilities.</span></span>
> <span data-ttu-id="f6780-112">Дополнительные сведения см. в [веб-сайте Microsoft Defender для функций предварительного просмотра конечных точек.](preview.md)</span><span class="sxs-lookup"><span data-stu-id="f6780-112">For more information, see [Microsoft Defender for Endpoint preview features](preview.md).</span></span>

><span data-ttu-id="f6780-113">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="f6780-113">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="f6780-114">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="f6780-114">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-portaloverview-abovefoldlink)

> [!NOTE]  
> <span data-ttu-id="f6780-115">Блог [по](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) обнаружению и оценке уязвимостей сетевых устройств, опубликованный \( 04-13-2021, содержит сведения о возможностях обнаружения новых сетевых устройств в \) Defender for Endpoint. </span><span class="sxs-lookup"><span data-stu-id="f6780-115">The [Network device discovery and vulnerability assessments](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/network-device-discovery-and-vulnerability-assessments/ba-p/2267548) Blog \(published 04-13-2021\) provides insights into the new **Network device discovery** capabilities in Defender for Endpoint.</span></span> <span data-ttu-id="f6780-116">В этой статье представлен обзор  проблем, с которыми предназначено решение обнаружения сетевых устройств, и подробные сведения о том, как начать работу с этими новыми возможностями.</span><span class="sxs-lookup"><span data-stu-id="f6780-116">This article provides an overview of the challenge that **Network device discovery** is designed to address, and detailed information about how get started using these new capabilities.</span></span>

<span data-ttu-id="f6780-117">Возможности обнаружения сети доступны в разделе **Инвентаризация** устройств центра Microsoft 365 и Центр безопасности в Microsoft Defender консолей.</span><span class="sxs-lookup"><span data-stu-id="f6780-117">Network discovery capabilities are available in the **Device inventory** section of the Microsoft 365 security center and Microsoft Defender Security Center consoles.</span></span>  

<span data-ttu-id="f6780-118">Назначенное устройство Microsoft Defender для конечных точек будет использоваться в каждом сетевом сегменте для выполнения периодического проверки подлинности предварительно заранее заверяемых сетевых устройств.</span><span class="sxs-lookup"><span data-stu-id="f6780-118">A designated Microsoft Defender for Endpoint device will be used on each network segment to perform periodic authenticated scans of preconfigured network devices.</span></span> <span data-ttu-id="f6780-119">После обнаружения возможности defender for Endpoint контроль угроз и уязвимостей интегрированные рабочий процессы для защиты обнаруженных переключателей, маршрутизаторов, контроллеров WLAN, брандмауэров и шлюзов VPN.</span><span class="sxs-lookup"><span data-stu-id="f6780-119">Once discovered, Defender for Endpoint’s threat and vulnerability management capabilities provide integrated workflows to secure discovered switches, routers, WLAN controllers, firewalls, and VPN gateways.</span></span>  

<span data-ttu-id="f6780-120">После обнаружения и классификации сетевых устройств администраторы безопасности смогут получать последние рекомендации по безопасности и рассматривать обнаруженные недавно уязвимости на сетевых устройствах, развернутых в их организациях.</span><span class="sxs-lookup"><span data-stu-id="f6780-120">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>

## <a name="approach"></a><span data-ttu-id="f6780-121">Способ</span><span class="sxs-lookup"><span data-stu-id="f6780-121">Approach</span></span>

<span data-ttu-id="f6780-122">Сетевые устройства не управляются в качестве стандартных конечных точек, так как в Defender for Endpoint нет датчика, встроенного в сами сетевые устройства.</span><span class="sxs-lookup"><span data-stu-id="f6780-122">Network devices are not managed as standard endpoints since Defender for Endpoint doesn’t have a sensor built into the network devices themselves.</span></span> <span data-ttu-id="f6780-123">Для таких устройств требуется безагентный подход, при котором удаленное сканирование будет получать необходимую информацию с устройств.</span><span class="sxs-lookup"><span data-stu-id="f6780-123">These types of devices require an agentless approach where a remote scan will obtain the necessary information from the devices.</span></span> <span data-ttu-id="f6780-124">В зависимости от топологии и характеристик сети одно устройство или несколько устройств, на борту которых находится Microsoft Defender для конечной точки, будут выполнять проверки подлинности сетевых устройств с помощью SNMP (только для чтения).</span><span class="sxs-lookup"><span data-stu-id="f6780-124">Depending on the network topology and characteristics, a single device or a few devices onboarded to Microsoft Defender for Endpoint will perform authenticated scans of network devices using SNMP (read-only).</span></span>

<span data-ttu-id="f6780-125">Необходимо помнить о двух типах устройств:</span><span class="sxs-lookup"><span data-stu-id="f6780-125">There will be two types of devices to keep in mind:</span></span>

- <span data-ttu-id="f6780-126">**Устройство оценки.** Устройство, которое уже на борту, которое будет использовать для сканирования сетевых устройств.</span><span class="sxs-lookup"><span data-stu-id="f6780-126">**Assessment device**: A device that's already onboarded that you'll use to scan the network devices.</span></span>
- <span data-ttu-id="f6780-127">**Сетевые устройства.** Сетевые устройства, которые планируется сканировать и на борту.</span><span class="sxs-lookup"><span data-stu-id="f6780-127">**Network devices**: The network devices you plan to scan and onboard.</span></span>

### <a name="vulnerability-management-for-network-devices"></a><span data-ttu-id="f6780-128">Управление уязвимостью для сетевых устройств</span><span class="sxs-lookup"><span data-stu-id="f6780-128">Vulnerability management for network devices</span></span> 

<span data-ttu-id="f6780-129">После обнаружения и классификации сетевых устройств администраторы безопасности смогут получать последние рекомендации по безопасности и рассматривать обнаруженные недавно уязвимости на сетевых устройствах, развернутых в их организациях.</span><span class="sxs-lookup"><span data-stu-id="f6780-129">Once the network devices are discovered and classified, security administrators will be able to receive the latest security recommendations and review recently discovered vulnerabilities on network devices deployed across their organizations.</span></span>  

## <a name="operating-systems-that-are-supported"></a><span data-ttu-id="f6780-130">Поддерживаемые операционные системы</span><span class="sxs-lookup"><span data-stu-id="f6780-130">Operating systems that are supported</span></span>

<span data-ttu-id="f6780-131">В настоящее время поддерживаются следующие операционные системы:</span><span class="sxs-lookup"><span data-stu-id="f6780-131">The following operating systems are currently supported:</span></span>

- <span data-ttu-id="f6780-132">Cisco IOS, IOS-XE, NX-OS</span><span class="sxs-lookup"><span data-stu-id="f6780-132">Cisco IOS, IOS-XE, NX-OS</span></span>
- <span data-ttu-id="f6780-133">JuNOS можжевельника</span><span class="sxs-lookup"><span data-stu-id="f6780-133">Juniper JUNOS</span></span>
- <span data-ttu-id="f6780-134">HPE ArubaOS, программное обеспечение для коммутаторов</span><span class="sxs-lookup"><span data-stu-id="f6780-134">HPE ArubaOS, Procurve Switch Software</span></span>
- <span data-ttu-id="f6780-135">Palo Alto Networks PAN-OS</span><span class="sxs-lookup"><span data-stu-id="f6780-135">Palo Alto Networks PAN-OS</span></span>

<span data-ttu-id="f6780-136">Со временем будут добавлены дополнительные поставщики сетевых сетей и ОС на основе данных, собранных из использования клиентов.</span><span class="sxs-lookup"><span data-stu-id="f6780-136">More networking vendors and OS will be added over time, based on data gathered from customer usage.</span></span> <span data-ttu-id="f6780-137">Поэтому рекомендуется настроить все сетевые устройства, даже если они не указаны в этом списке.</span><span class="sxs-lookup"><span data-stu-id="f6780-137">Therefore, you are encouraged to configure all your network devices, even if they’re not specified in this list.</span></span>

## <a name="how-to-get-started"></a><span data-ttu-id="f6780-138">Начало работы</span><span class="sxs-lookup"><span data-stu-id="f6780-138">How to get started</span></span>

<span data-ttu-id="f6780-139">Первым шагом является выбор устройства, которое будет выполнять проверку подлинности сети.</span><span class="sxs-lookup"><span data-stu-id="f6780-139">Your first step is to select a device that will perform the authenticated network scans.</span></span>

1. <span data-ttu-id="f6780-140">Определите бортовой устройство Defender для конечной точки (клиент или сервер), которое имеет сетевое подключение к порту управления для сетевых устройств, которые планируется сканировать.</span><span class="sxs-lookup"><span data-stu-id="f6780-140">Decide on a Defender for Endpoint onboarded device (client or server) that has a network connection to the management port for the network devices you plan on scanning.</span></span> 

2. <span data-ttu-id="f6780-141">Трафик SNMP между устройством оценки Defender для конечных точек и целевыми сетевыми устройствами должен быть разрешен (например, брандмауэром).</span><span class="sxs-lookup"><span data-stu-id="f6780-141">SNMP traffic between the Defender for Endpoint assessment device and the targeted network devices must be allowed (for example, by the Firewall).</span></span>

3. <span data-ttu-id="f6780-142">Определите, какие сетевые устройства будут оцениваться на наличие уязвимостей (например, переключатель Cisco или брандмауэр Palo Alto Networks).</span><span class="sxs-lookup"><span data-stu-id="f6780-142">Decide which network devices will be assessed for vulnerabilities (for example: a Cisco switch or a Palo Alto Networks firewall).</span></span>  

4. <span data-ttu-id="f6780-143">Убедитесь, что только для чтения SNMP включен на всех настроенных сетевых устройствах, чтобы устройство оценки Defender для конечных точек запрашивал настроенные сетевые устройства.</span><span class="sxs-lookup"><span data-stu-id="f6780-143">Make sure SNMP read-only is enabled on all configured network devices to allow the Defender for Endpoint assessment device to query the configured network devices.</span></span> <span data-ttu-id="f6780-144">'SNMP write' не требуется для надлежащей функциональности этой функции.</span><span class="sxs-lookup"><span data-stu-id="f6780-144">‘SNMP write’ isn't needed for the proper functionality of this feature.</span></span>

5. <span data-ttu-id="f6780-145">Получение IP-адресов сканированных сетевых устройств (или подсетей, в которых развернуты эти устройства).</span><span class="sxs-lookup"><span data-stu-id="f6780-145">Obtain the IP addresses of the network devices to be scanned (or the subnets where these devices are deployed).</span></span>

6. <span data-ttu-id="f6780-146">Получение учетных данных SNMP сетевых устройств (например: Community String, noAuthNoPriv, authNoPriv, authPriv).</span><span class="sxs-lookup"><span data-stu-id="f6780-146">Obtain the SNMP credentials of the network devices (for example: Community String, noAuthNoPriv, authNoPriv, authPriv).</span></span> <span data-ttu-id="f6780-147">При настройке нового задания оценки необходимо предоставить учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f6780-147">You’ll be required to provide the credentials when configuring a new assessment job.</span></span>  

7. <span data-ttu-id="f6780-148">Конфигурация прокси-клиента. Не требуется дополнительная конфигурация, кроме требований прокси-сервера Defender для прокси-серверов конечных точек.</span><span class="sxs-lookup"><span data-stu-id="f6780-148">Proxy client configuration: No extra configuration is required other than the Defender for Endpoint device proxy requirements.</span></span>

8. <span data-ttu-id="f6780-149">Чтобы разрешить проверку подлинности сетевого сканера и правильно работать, необходимо добавить следующие домены и URL-адреса:</span><span class="sxs-lookup"><span data-stu-id="f6780-149">To allow the network scanner to be authenticated and work properly, it's essential that you add the following domains/URLs:</span></span>

    - <span data-ttu-id="f6780-150">login.windows.net</span><span class="sxs-lookup"><span data-stu-id="f6780-150">login.windows.net</span></span>  
    - <span data-ttu-id="f6780-151">\*.securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="f6780-151">\*.securitycenter.windows.com</span></span>
    - <span data-ttu-id="f6780-152">login.microsoftonline.com</span><span class="sxs-lookup"><span data-stu-id="f6780-152">login.microsoftonline.com</span></span>
    - <span data-ttu-id="f6780-153">\*.blob.core.windows.net/networkscannerstable/ \*</span><span class="sxs-lookup"><span data-stu-id="f6780-153">\*.blob.core.windows.net/networkscannerstable/ \*</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6780-154">Не все URL-адреса указаны в документированном списке разрешенного сбора данных Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f6780-154">Not all URLs are specified in the Defender for Endpoint documented list of allowed data collection.</span></span>

## <a name="permissions"></a><span data-ttu-id="f6780-155">Разрешения</span><span class="sxs-lookup"><span data-stu-id="f6780-155">Permissions</span></span>

<span data-ttu-id="f6780-156">Для настройки заданий оценки требуется следующий параметр разрешения пользователя: **Управление настройками безопасности в Центре безопасности.**</span><span class="sxs-lookup"><span data-stu-id="f6780-156">To configure assessment jobs, the following user permission option is required: **Manage security settings in Security Center**.</span></span> <span data-ttu-id="f6780-157">Вы можете найти разрешение, Параметры  >  **роли**.</span><span class="sxs-lookup"><span data-stu-id="f6780-157">You can find the permission by going to **Settings** > **Roles**.</span></span> <span data-ttu-id="f6780-158">Дополнительные сведения см. в дополнительных сведениях о создании и [управлении ролями для](user-roles.md)управления доступом на основе ролей.</span><span class="sxs-lookup"><span data-stu-id="f6780-158">For more information, see [Create and manage roles for role-based access control](user-roles.md).</span></span>

## <a name="install-the-network-scanner"></a><span data-ttu-id="f6780-159">Установка сетевого сканера</span><span class="sxs-lookup"><span data-stu-id="f6780-159">Install the network scanner</span></span>

1. <span data-ttu-id="f6780-160">Перейдите **Microsoft 365 задания** Параметры оценки конечных точек  >    >    >   (в соответствии **с сетевыми оценками).**</span><span class="sxs-lookup"><span data-stu-id="f6780-160">Go to **Microsoft 365 security** > **Settings** > **Endpoints** > **Assessment jobs** (under **Network assessments**).</span></span>
    1. <span data-ttu-id="f6780-161">В Центр безопасности в Microsoft Defender перейдите на Параметры > задания оценки.</span><span class="sxs-lookup"><span data-stu-id="f6780-161">In the Microsoft Defender Security Center, go to Settings > Assessment jobs page.</span></span>

2. <span data-ttu-id="f6780-162">Скачайте сетевой сканер и установите его на назначенное устройство оценки Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f6780-162">Download the network scanner and install it on the designated Defender for Endpoint assessment device.</span></span>

    > [!div class="mx-imgBorder"]
    > <span data-ttu-id="f6780-163">![Кнопка загрузки сканера](images/assessment-jobs-download-scanner.png)</span><span class="sxs-lookup"><span data-stu-id="f6780-163">![Download scanner button](images/assessment-jobs-download-scanner.png)</span></span>

## <a name="network-scanner-installation--registration"></a><span data-ttu-id="f6780-164">Установка сетевого сканера & регистрации</span><span class="sxs-lookup"><span data-stu-id="f6780-164">Network scanner installation & registration</span></span>

<span data-ttu-id="f6780-165">Процесс регистрации может быть завершен на назначенном устройстве оценки или любом другом устройстве (например, вашем личном клиенте).</span><span class="sxs-lookup"><span data-stu-id="f6780-165">The signing-in process can be completed on the designated assessment device itself or any other device (for example, your personal client device).</span></span>

<span data-ttu-id="f6780-166">Чтобы завершить процесс регистрации сетевого сканера:</span><span class="sxs-lookup"><span data-stu-id="f6780-166">To complete the network scanner registration process:</span></span>

1. <span data-ttu-id="f6780-167">Скопируйте и выполните URL-адрес, который отображается в командной строке, и используйте предоставленный код установки для завершения процесса регистрации.</span><span class="sxs-lookup"><span data-stu-id="f6780-167">Copy and follow the URL that appears on the command line and use the provided installation code to complete the registration process.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f6780-168">Возможно, потребуется изменить параметры командной подсказки, чтобы можно было скопировать URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f6780-168">You may need to change Command Prompt settings to be able to copy the URL.</span></span>

2. <span data-ttu-id="f6780-169">Введите код и войдите в учетную запись Майкрософт с разрешением Defender for Endpoint под названием "Управление настройками безопасности в Центре безопасности".</span><span class="sxs-lookup"><span data-stu-id="f6780-169">Enter the code and sign in using a Microsoft account that has the Defender for Endpoint permission called "Manage security settings in Security Center."</span></span>

3. <span data-ttu-id="f6780-170">По завершению следует увидеть сообщение, подтверждаее, что вы вписались.</span><span class="sxs-lookup"><span data-stu-id="f6780-170">When finished, you should see a message confirming you have signed in.</span></span>

## <a name="configure-a-new-assessment-job"></a><span data-ttu-id="f6780-171">Настройка новой задания оценки</span><span class="sxs-lookup"><span data-stu-id="f6780-171">Configure a new assessment job</span></span>  

<span data-ttu-id="f6780-172">На странице Задания оценки в **Параметры** выберите **задание Добавить работу по оценке сети.**</span><span class="sxs-lookup"><span data-stu-id="f6780-172">In the Assessment jobs page in **Settings**, select **Add network assessment job**.</span></span> <span data-ttu-id="f6780-173">Выполните процедуру настройка, чтобы выбрать сетевые устройства, которые будут регулярно сканироваться и добавляться в инвентарь устройств.</span><span class="sxs-lookup"><span data-stu-id="f6780-173">Follow the set-up process to choose network devices to be scanned regularly and added to the device inventory.</span></span>

<span data-ttu-id="f6780-174">Чтобы предотвратить дублирование устройств в инвентаризации сетевых устройств, убедитесь, что каждый IP-адрес настраивается только один раз на нескольких устройствах оценки.</span><span class="sxs-lookup"><span data-stu-id="f6780-174">To prevent device duplication in the network device inventory, make sure each IP address is configured only once across multiple assessment devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f6780-175">![Добавление кнопки задания оценки сети](images/assessment-jobs-add.png)</span><span class="sxs-lookup"><span data-stu-id="f6780-175">![Add network assessment job button](images/assessment-jobs-add.png)</span></span>

<span data-ttu-id="f6780-176">Добавление действий по оценке сети:</span><span class="sxs-lookup"><span data-stu-id="f6780-176">Adding a network assessment job steps:</span></span>

1. <span data-ttu-id="f6780-177">Выберите имя "Задание оценки" и "Устройство оценки", на котором установлен сетевой сканер.</span><span class="sxs-lookup"><span data-stu-id="f6780-177">Choose an ‘Assessment job’ name and the ‘Assessment device’ on which the network scanner was installed.</span></span> <span data-ttu-id="f6780-178">Это устройство выполняет периодические проверки подлинности.</span><span class="sxs-lookup"><span data-stu-id="f6780-178">This device will perform the periodic authenticated scans.</span></span>

2. <span data-ttu-id="f6780-179">Добавьте IP-адреса целевых сетевых устройств для сканирования (или подсети, в которых развернуты эти устройства).</span><span class="sxs-lookup"><span data-stu-id="f6780-179">Add IP addresses of target network devices to be scanned (or the subnets where these devices are deployed).</span></span> 

3. <span data-ttu-id="f6780-180">Добавление необходимых учетных данных SNMP целевых сетевых устройств.</span><span class="sxs-lookup"><span data-stu-id="f6780-180">Add required SNMP credentials of the target network devices.</span></span> 

4. <span data-ttu-id="f6780-181">Сохраните вновь настроенную работу по оценке сети, чтобы начать периодическое сканирование сети.</span><span class="sxs-lookup"><span data-stu-id="f6780-181">Save the newly configured network assessment job to start the periodic network scan.</span></span> 

### <a name="scan-and-add-network-devices"></a><span data-ttu-id="f6780-182">Сканирование и добавление сетевых устройств</span><span class="sxs-lookup"><span data-stu-id="f6780-182">Scan and add network devices</span></span>

<span data-ttu-id="f6780-183">Во время процесса создания можно выполнить одно время проверки, чтобы убедиться, что:</span><span class="sxs-lookup"><span data-stu-id="f6780-183">During the set-up process, you can perform a one time test scan to verify that:</span></span>

- <span data-ttu-id="f6780-184">Существует подключение между устройством оценки Defender для конечной точки и настроенными целевыми сетевыми устройствами.</span><span class="sxs-lookup"><span data-stu-id="f6780-184">There is connectivity between the Defender for Endpoint assessment device and the configured target network devices.</span></span>
- <span data-ttu-id="f6780-185">Настроенные учетные данные SNMP являются правильными.</span><span class="sxs-lookup"><span data-stu-id="f6780-185">The configured SNMP credentials are correct.</span></span>

<span data-ttu-id="f6780-186">Каждое устройство оценки может поддерживать до 1500 успешных ip-адресов.</span><span class="sxs-lookup"><span data-stu-id="f6780-186">Each assessment device can support up to 1,500 successful IP addresses scan.</span></span> <span data-ttu-id="f6780-187">Например, если вы сканируете 10 различных подсетей, в которых только 100 IP-адресов возвращают успешные результаты, вы сможете сканировать 1400 IP-адресов из других подсетей на том же устройстве оценки.</span><span class="sxs-lookup"><span data-stu-id="f6780-187">For example, if you scan 10 different subnets where only 100 IP addresses return successful results, you will be able to scan 1,400 IP additional addresses from other subnets on the same assessment device.</span></span>  

<span data-ttu-id="f6780-188">Если для сканирования необходимо просмотреть несколько диапазонов IP-адресов и подсетей, результаты проверки будут показываться в течение нескольких минут.</span><span class="sxs-lookup"><span data-stu-id="f6780-188">If there are multiple IP address ranges/subnets to scan, the test scan results will take several minutes to show up.</span></span> <span data-ttu-id="f6780-189">Тестовая проверка будет доступна для 1024 адресов.</span><span class="sxs-lookup"><span data-stu-id="f6780-189">A test scan will be available for up to 1,024 addresses.</span></span>

<span data-ttu-id="f6780-190">Как только результаты покажут, можно выбрать, какие устройства будут включены в периодическое сканирование.</span><span class="sxs-lookup"><span data-stu-id="f6780-190">Once the results show up, you can choose which devices will be included in the periodic scan.</span></span> <span data-ttu-id="f6780-191">Если пропустить просмотр результатов сканирования, все настроенные IP-адреса будут добавлены в задание по оценке сети (независимо от ответа устройства).</span><span class="sxs-lookup"><span data-stu-id="f6780-191">If you skip viewing the scan results, all configured IP addresses will be added to the network assessment job (regardless of the device’s response).</span></span> <span data-ttu-id="f6780-192">Результаты сканирования также можно экспортировать.</span><span class="sxs-lookup"><span data-stu-id="f6780-192">The scan results can also be exported.</span></span>

## <a name="device-inventory"></a><span data-ttu-id="f6780-193">Инвентаризация устройств</span><span class="sxs-lookup"><span data-stu-id="f6780-193">Device inventory</span></span>

<span data-ttu-id="f6780-194">Новые обнаруженные устройства будут показаны на вкладке **новые сетевые** устройства на странице **инвентаризации** устройств.</span><span class="sxs-lookup"><span data-stu-id="f6780-194">Newly discovered devices will be shown under the new **Network devices** tab in the **Device inventory** page.</span></span> <span data-ttu-id="f6780-195">После добавления задания оценки до обновления устройств может потребоваться до двух часов.</span><span class="sxs-lookup"><span data-stu-id="f6780-195">It may take up to two hours after adding an assessment job until the devices are updated.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="f6780-196">![Раздел Сетевые устройства в инвентаризации устройств](images/assessment-jobs-device-inventory.png)</span><span class="sxs-lookup"><span data-stu-id="f6780-196">![Network devices section in the Device inventory](images/assessment-jobs-device-inventory.png)</span></span>

## <a name="troubleshooting"></a><span data-ttu-id="f6780-197">Устранение неполадок</span><span class="sxs-lookup"><span data-stu-id="f6780-197">Troubleshooting</span></span>

### <a name="network-scanner-installation-has-failed"></a><span data-ttu-id="f6780-198">Сбой установки сетевого сканера</span><span class="sxs-lookup"><span data-stu-id="f6780-198">Network scanner installation has failed</span></span>

<span data-ttu-id="f6780-199">Убедитесь, что необходимые URL-адреса добавляются в разрешенные домены в настройках брандмауэра.</span><span class="sxs-lookup"><span data-stu-id="f6780-199">Verify that the required URLs are added to the allowed domains in your firewall settings.</span></span> <span data-ttu-id="f6780-200">Кроме того, убедитесь, что параметры прокси настроены так, как описано в Настройка прокси-сервера устройства и параметров подключения [к Интернету.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="f6780-200">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="the-microsoftcomdevicelogin-web-page-did-not-show-up"></a><span data-ttu-id="f6780-201">Веб Microsoft.com/devicelogin страница не была</span><span class="sxs-lookup"><span data-stu-id="f6780-201">The Microsoft.com/devicelogin web page did not show up</span></span>

<span data-ttu-id="f6780-202">Убедитесь, что в разрешенные домены брандмауэра добавлены необходимые URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="f6780-202">Verify that the required URLs are added to the allowed domains in your firewall.</span></span> <span data-ttu-id="f6780-203">Кроме того, убедитесь, что параметры прокси настроены так, как описано в Настройка прокси-сервера устройства и параметров подключения [к Интернету.](configure-proxy-internet.md)</span><span class="sxs-lookup"><span data-stu-id="f6780-203">Also, make sure proxy settings are configured as described in [Configure device proxy and Internet connectivity settings](configure-proxy-internet.md).</span></span>

### <a name="network-devices-are-not-shown-in-the-device-inventory-after-several-hours"></a><span data-ttu-id="f6780-204">Сетевые устройства не показаны в инвентаризации устройств через несколько часов</span><span class="sxs-lookup"><span data-stu-id="f6780-204">Network devices are not shown in the device inventory after several hours</span></span>

<span data-ttu-id="f6780-205">Результаты сканирования должны обновляться через несколько часов после первоначального сканирования, проведенного после завершения конфигурации задания оценки.</span><span class="sxs-lookup"><span data-stu-id="f6780-205">The scan results should be updated a few hours after the initial scan that took place after completing the assessment job configuration.</span></span>

<span data-ttu-id="f6780-206">Если устройства еще не показаны, убедитесь, что служба MdatpNetworkScanService запущена на устройствах оценки, на которых установлен сетевой сканер, и выполните "Сканирование выполнения" в соответствующей конфигурации задания оценки.</span><span class="sxs-lookup"><span data-stu-id="f6780-206">If devices are still not shown, verify that the service ‘MdatpNetworkScanService’ is running on your assessment devices, on which you installed the network scanner, and perform a “Run scan” in the relevant assessment job configuration.</span></span>  

<span data-ttu-id="f6780-207">Если вы все еще не получите результат через 5 минут, перезапустите службу.</span><span class="sxs-lookup"><span data-stu-id="f6780-207">If you still don’t get results after 5 minutes, restart the service.</span></span>  

### <a name="devices-last-seen-time-is-longer-than-24-hours"></a><span data-ttu-id="f6780-208">Время последнего увиденного устройства превышает 24 часа</span><span class="sxs-lookup"><span data-stu-id="f6780-208">Devices last seen time is longer than 24 hours</span></span>

<span data-ttu-id="f6780-209">Проверьте правильность работы сканера.</span><span class="sxs-lookup"><span data-stu-id="f6780-209">Validate that the scanner is running properly.</span></span> <span data-ttu-id="f6780-210">Затем перейдите к определению сканирования и выберите "Выполнить тест".</span><span class="sxs-lookup"><span data-stu-id="f6780-210">Then go to the scan definition and select “Run test.”</span></span> <span data-ttu-id="f6780-211">Проверьте, какие сообщения об ошибках возвращаются с соответствующих IP-адресов.</span><span class="sxs-lookup"><span data-stu-id="f6780-211">Check what error messages are returning from the relevant IP addresses.</span></span>

### <a name="required-threat-and-vulnerability-management-user-permission"></a><span data-ttu-id="f6780-212">Обязательное контроль угроз и уязвимостей разрешения пользователя</span><span class="sxs-lookup"><span data-stu-id="f6780-212">Required threat and vulnerability management user permission</span></span>

<span data-ttu-id="f6780-213">Регистрация завершилась ошибкой: "Похоже, у вас нет достаточных разрешений для добавления нового агента.</span><span class="sxs-lookup"><span data-stu-id="f6780-213">Registration finished with an error: "It looks like you don't have sufficient permissions for adding a new agent.</span></span> <span data-ttu-id="f6780-214">Необходимое разрешение — "Управление настройками безопасности в Центре безопасности".</span><span class="sxs-lookup"><span data-stu-id="f6780-214">The required permission is 'Manage security settings in Security Center'."</span></span>

<span data-ttu-id="f6780-215">Нажмите любой ключ, чтобы выйти.</span><span class="sxs-lookup"><span data-stu-id="f6780-215">Press any key to exit.</span></span>

<span data-ttu-id="f6780-216">Попросите системного администратора назначить вам необходимые разрешения.</span><span class="sxs-lookup"><span data-stu-id="f6780-216">Ask your system administrator to assign you the required permissions.</span></span> <span data-ttu-id="f6780-217">Поочередно попросите другого соответствующего участника помочь вам в процессе регистрации, предоставив им код и ссылку для регистрации.</span><span class="sxs-lookup"><span data-stu-id="f6780-217">Alternately, ask another relevant member to help you with the sign-in process by providing them with the sign-in code and link.</span></span>

### <a name="registration-process-fails-using-provided-link-in-the-command-line-in-registration-process"></a><span data-ttu-id="f6780-218">Процесс регистрации не удается с помощью предоставленной ссылки в командной строке в процессе регистрации</span><span class="sxs-lookup"><span data-stu-id="f6780-218">Registration process fails using provided link in the command line in registration process</span></span>

<span data-ttu-id="f6780-219">Попробуйте другой браузер или скопируйте входную ссылку и код на другое устройство.</span><span class="sxs-lookup"><span data-stu-id="f6780-219">Try a different browser or copy the sign-in link and code to a different device.</span></span>

### <a name="text-too-small-or-cant-copy-text-from-command-line"></a><span data-ttu-id="f6780-220">Текст слишком маленький или не может копировать текст из командной строки</span><span class="sxs-lookup"><span data-stu-id="f6780-220">Text too small or can’t copy text from command line</span></span>

<span data-ttu-id="f6780-221">Измените параметры командной строки на устройстве, чтобы разрешить копирование и изменение размера текста.</span><span class="sxs-lookup"><span data-stu-id="f6780-221">Change command-line settings on your device to allow copying and change text size.</span></span>

## <a name="related-articles"></a><span data-ttu-id="f6780-222">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="f6780-222">Related articles</span></span>

- [<span data-ttu-id="f6780-223">Инвентаризация устройств</span><span class="sxs-lookup"><span data-stu-id="f6780-223">Device inventory</span></span>](machines-view-overview.md)
- [<span data-ttu-id="f6780-224">Настройка дополнительных функций</span><span class="sxs-lookup"><span data-stu-id="f6780-224">Configure advanced features</span></span>](advanced-features.md)
