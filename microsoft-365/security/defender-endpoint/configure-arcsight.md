---
title: Настройте Micro Focus ArcSight, чтобы вытащить Microsoft Defender для обнаружения конечных точек
description: Настройте Micro Focus ArcSight для получения и обнаружения с Центр безопасности в Microsoft Defender
keywords: настройка средств управления micro Focus ArcSight, средств управления сведениями о безопасности и событиями, arcsight
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a52f810647c387c5a5726b9d31998c34add4092e
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166189"
---
# <a name="configure-micro-focus-arcsight-to-pull-defender-for-endpoint-detections"></a><span data-ttu-id="c47aa-104">Настройте Micro Focus ArcSight, чтобы вытащить Defender для обнаружения конечных точек</span><span class="sxs-lookup"><span data-stu-id="c47aa-104">Configure Micro Focus ArcSight to pull Defender for Endpoint detections</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="c47aa-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c47aa-105">**Applies to:**</span></span>
- [<span data-ttu-id="c47aa-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c47aa-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c47aa-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c47aa-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="c47aa-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c47aa-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c47aa-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c47aa-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-configurearcsight-abovefoldlink) 

<span data-ttu-id="c47aa-110">Вам потребуется установить и настроить некоторые файлы и средства для использования Micro Focus ArcSight, чтобы он может вытащить Defender для обнаружения конечных точек.</span><span class="sxs-lookup"><span data-stu-id="c47aa-110">You'll need to install and configure some files and tools to use Micro Focus ArcSight so that it can pull Defender for Endpoint detections.</span></span>

>[!Note]
>- <span data-ttu-id="c47aa-111">[Defender for Endpoint Alert](alerts.md) состоит из одного или нескольких обнаружений</span><span class="sxs-lookup"><span data-stu-id="c47aa-111">[Defender for Endpoint Alert](alerts.md) is composed from one or more detections</span></span>
>- <span data-ttu-id="c47aa-112">[Defender for Endpoint Detection](api-portal-mapping.md) состоит из подозрительного события, произошедшего на устройстве, и связанных с ним сведений оповещения.</span><span class="sxs-lookup"><span data-stu-id="c47aa-112">[Defender for Endpoint Detection](api-portal-mapping.md) is composed from the suspicious event occurred on the Device and its related Alert details.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="c47aa-113">Прежде чем начать</span><span class="sxs-lookup"><span data-stu-id="c47aa-113">Before you begin</span></span>

<span data-ttu-id="c47aa-114">Настройка средства подключения к micro Focus ArcSight требует нескольких файлов конфигурации, чтобы вытащить и разбор обнаружения из приложения Azure Active Directory (AAD).</span><span class="sxs-lookup"><span data-stu-id="c47aa-114">Configuring the Micro Focus ArcSight Connector tool requires several configuration files for it to pull and parse detections from your Azure Active Directory (AAD) application.</span></span>

<span data-ttu-id="c47aa-115">В этом разделе вы можете получить необходимую информацию, чтобы правильно настроить и использовать необходимые файлы конфигурации.</span><span class="sxs-lookup"><span data-stu-id="c47aa-115">This section guides you in getting the necessary information to set and use the required configuration files correctly.</span></span>

- <span data-ttu-id="c47aa-116">Убедитесь, что вы включили функцию интеграции SIEM из **Параметры** меню.</span><span class="sxs-lookup"><span data-stu-id="c47aa-116">Make sure you have enabled the SIEM integration feature from the **Settings** menu.</span></span> <span data-ttu-id="c47aa-117">Дополнительные сведения см. в [дополнительных сведениях: Включение интеграции SIEM в Defender для конечной точки.](enable-siem-integration.md)</span><span class="sxs-lookup"><span data-stu-id="c47aa-117">For more information, see [Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md).</span></span>

- <span data-ttu-id="c47aa-118">Готовый файл, сохраненный при включительно функции интеграции SIEM.</span><span class="sxs-lookup"><span data-stu-id="c47aa-118">Have the file you saved from enabling the SIEM integration feature ready.</span></span> <span data-ttu-id="c47aa-119">Необходимо получить следующие значения:</span><span class="sxs-lookup"><span data-stu-id="c47aa-119">You'll need to get the following values:</span></span>
  - <span data-ttu-id="c47aa-120">URL-адрес обновления маркера OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="c47aa-120">OAuth 2.0 Token refresh URL</span></span>
  - <span data-ttu-id="c47aa-121">ID клиента OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="c47aa-121">OAuth 2.0 Client ID</span></span>
  - <span data-ttu-id="c47aa-122">Секрет клиента OAuth 2.0</span><span class="sxs-lookup"><span data-stu-id="c47aa-122">OAuth 2.0 Client secret</span></span>

- <span data-ttu-id="c47aa-123">Готовы следующие файлы конфигурации:</span><span class="sxs-lookup"><span data-stu-id="c47aa-123">Have the following configuration files ready:</span></span>
  - <span data-ttu-id="c47aa-124">WDATP-connector.properties</span><span class="sxs-lookup"><span data-stu-id="c47aa-124">WDATP-connector.properties</span></span>
  - <span data-ttu-id="c47aa-125">WDATP-connector.jsonparser.properties</span><span class="sxs-lookup"><span data-stu-id="c47aa-125">WDATP-connector.jsonparser.properties</span></span>

    <span data-ttu-id="c47aa-126">Вы сохранили бы файл .zip, который содержит эти два файла при использовании Micro Focus ArcSight в качестве типа SIEM, используемого в организации.</span><span class="sxs-lookup"><span data-stu-id="c47aa-126">You would have saved a .zip file which contains these two files when you chose Micro Focus ArcSight as the SIEM type you use in your organization.</span></span>

- <span data-ttu-id="c47aa-127">Убедитесь, что вы создаете следующие маркеры и готовы:</span><span class="sxs-lookup"><span data-stu-id="c47aa-127">Make sure you generate the following tokens and have them ready:</span></span>
  - <span data-ttu-id="c47aa-128">Маркер доступа</span><span class="sxs-lookup"><span data-stu-id="c47aa-128">Access token</span></span>
  - <span data-ttu-id="c47aa-129">Маркер обновления</span><span class="sxs-lookup"><span data-stu-id="c47aa-129">Refresh token</span></span>

  <span data-ttu-id="c47aa-130">Эти маркеры можно создавать из раздела **установки интеграции SIEM** портала.</span><span class="sxs-lookup"><span data-stu-id="c47aa-130">You can generate these tokens from the **SIEM integration** setup section of the portal.</span></span>

## <a name="install-and-configure-micro-focus-arcsight-flexconnector"></a><span data-ttu-id="c47aa-131">Установка и настройка Micro Focus ArcSight FlexConnector</span><span class="sxs-lookup"><span data-stu-id="c47aa-131">Install and configure Micro Focus ArcSight FlexConnector</span></span>

<span data-ttu-id="c47aa-132">Следующие действия предполагают, что вы выполнили все необходимые действия перед [началом.](#before-you-begin)</span><span class="sxs-lookup"><span data-stu-id="c47aa-132">The following steps assume that you have completed all the required steps in [Before you begin](#before-you-begin).</span></span>

1. <span data-ttu-id="c47aa-133">Установите последний 32-Windows установщик FlexConnector.</span><span class="sxs-lookup"><span data-stu-id="c47aa-133">Install the latest 32-bit Windows FlexConnector installer.</span></span> <span data-ttu-id="c47aa-134">Это можно найти в центре программного обеспечения HPE.</span><span class="sxs-lookup"><span data-stu-id="c47aa-134">You can find this in the HPE Software center.</span></span> <span data-ttu-id="c47aa-135">Обычно средство устанавливается в следующем расположении по умолчанию: `C:\Program Files\ArcSightFlexConnectors\current\bin` .</span><span class="sxs-lookup"><span data-stu-id="c47aa-135">The tool is typically installed in the following default location: `C:\Program Files\ArcSightFlexConnectors\current\bin`.</span></span></br></br><span data-ttu-id="c47aa-136">Вы можете выбрать, где сохранить средство, например \\ *C: folder_location*\current\bin, *folder_location* представляет расположение установки.</span><span class="sxs-lookup"><span data-stu-id="c47aa-136">You can choose where to save the tool, for example C:\\*folder_location*\current\bin where *folder_location* represents the installation location.</span></span>

2. <span data-ttu-id="c47aa-137">Выполните следующие задачи мастера установки:</span><span class="sxs-lookup"><span data-stu-id="c47aa-137">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="c47aa-138">Введение</span><span class="sxs-lookup"><span data-stu-id="c47aa-138">Introduction</span></span>
   - <span data-ttu-id="c47aa-139">Выбор папки установки</span><span class="sxs-lookup"><span data-stu-id="c47aa-139">Choose Install Folder</span></span>
   - <span data-ttu-id="c47aa-140">Выбор набора установки</span><span class="sxs-lookup"><span data-stu-id="c47aa-140">Choose Install Set</span></span>
   - <span data-ttu-id="c47aa-141">Выберите папку ярлыков</span><span class="sxs-lookup"><span data-stu-id="c47aa-141">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="c47aa-142">Сводка предварительной установки</span><span class="sxs-lookup"><span data-stu-id="c47aa-142">Pre-Installation Summary</span></span>
   - <span data-ttu-id="c47aa-143">Установка...</span><span class="sxs-lookup"><span data-stu-id="c47aa-143">Installing...</span></span>

   <span data-ttu-id="c47aa-144">Вы можете сохранить значения по умолчанию для каждой из этих задач или изменить выбор в соответствии с вашими требованиями.</span><span class="sxs-lookup"><span data-stu-id="c47aa-144">You can keep the default values for each of these tasks or modify the selection to suit your requirements.</span></span>

3. <span data-ttu-id="c47aa-145">Откройте проводник файлов и найдите два файла конфигурации, сохраненных при включенной функции интеграции SIEM.</span><span class="sxs-lookup"><span data-stu-id="c47aa-145">Open File Explorer and locate the two configuration files you saved when you enabled the SIEM integration feature.</span></span> <span data-ttu-id="c47aa-146">Поместите два файла в расположение установки FlexConnector, например:</span><span class="sxs-lookup"><span data-stu-id="c47aa-146">Put the two files in the FlexConnector installation location, for example:</span></span>

   - <span data-ttu-id="c47aa-147">WDATP-connector.jsonparser.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="c47aa-147">WDATP-connector.jsonparser.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   - <span data-ttu-id="c47aa-148">WDATP-connector.properties: C: \\ *folder_location*\current\user\agent\flexagent</span><span class="sxs-lookup"><span data-stu-id="c47aa-148">WDATP-connector.properties: C:\\*folder_location*\current\user\agent\flexagent</span></span>\

   > [!NOTE]
   > 
   > <span data-ttu-id="c47aa-149">Необходимо поместить файлы конфигурации в этом расположении, *folder_location* представляет расположение, в котором установлено средство.</span><span class="sxs-lookup"><span data-stu-id="c47aa-149">You must put the configuration files in this location, where *folder_location* represents the location where you installed the tool.</span></span>

4. <span data-ttu-id="c47aa-150">После завершения установки основного соединителя открывается окно установки соединителя.</span><span class="sxs-lookup"><span data-stu-id="c47aa-150">After the installation of the core connector completes, the Connector Setup window opens.</span></span> <span data-ttu-id="c47aa-151">В окне Настройка соединителю выберите **Добавить соединителю**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-151">In the Connector Setup window, select **Add a Connector**.</span></span>

5. <span data-ttu-id="c47aa-152">Выберите тип: **ArcSight FlexConnector REST и** нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-152">Select Type: **ArcSight FlexConnector REST** and click **Next**.</span></span>

6. <span data-ttu-id="c47aa-153">Введите следующую информацию в форме сведений о параметре.</span><span class="sxs-lookup"><span data-stu-id="c47aa-153">Type the following information in the parameter details form.</span></span> <span data-ttu-id="c47aa-154">Все остальные значения в форме необязательны и могут быть оставлены пустыми.</span><span class="sxs-lookup"><span data-stu-id="c47aa-154">All other values in the form are optional and can be left blank.</span></span>

   <table>
    <tbody style="vertical-align:top;">
    <tr>
    <th><span data-ttu-id="c47aa-155">Поле</span><span class="sxs-lookup"><span data-stu-id="c47aa-155">Field</span></span></th>
    <th><span data-ttu-id="c47aa-156">Значение</span><span class="sxs-lookup"><span data-stu-id="c47aa-156">Value</span></span></th>
    </tr>
    <tr>
    <td><span data-ttu-id="c47aa-157">Файл конфигурации</span><span class="sxs-lookup"><span data-stu-id="c47aa-157">Configuration File</span></span></td>
    <td><span data-ttu-id="c47aa-158">Введите имя файла свойств клиента.</span><span class="sxs-lookup"><span data-stu-id="c47aa-158">Type in the name of the client property file.</span></span> <span data-ttu-id="c47aa-159">Имя должно совпадать с файлом, предоставленным в .zip, который вы скачали.</span><span class="sxs-lookup"><span data-stu-id="c47aa-159">The name must match the file provided in the .zip that you downloaded.</span></span>
<span data-ttu-id="c47aa-160">Например, если файл конфигурации в каталоге &quot; flexagentWDATP-Connector.js&quot; &quot; onparser.properties, необходимо ввести &quot; &quot; WDATP-Connector в качестве имени файла свойств &quot; клиента.</span><span class="sxs-lookup"><span data-stu-id="c47aa-160">For example, if the configuration file in &quot;flexagent&quot; directory is named &quot;WDATP-Connector.jsonparser.properties&quot;, you must type &quot;WDATP-Connector&quot; as the name of the client property file.</span></span></td>
    </tr>
    <td><span data-ttu-id="c47aa-161">URL-адрес событий</span><span class="sxs-lookup"><span data-stu-id="c47aa-161">Events URL</span></span></td>
    <td><span data-ttu-id="c47aa-162">В зависимости от расположения центра обработки данных выберите ЕС или URL-адрес США:</span><span class="sxs-lookup"><span data-stu-id="c47aa-162">Depending on the location of your datacenter, select either the EU or the US URL:</span></span> </br></br> <span data-ttu-id="c47aa-163"><b>Для ЕС:</b>https:// <i></i> wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="c47aa-163"><b>For EU</b>:  https://<i></i>wdatp-alertexporter-eu.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br>
   </br><span data-ttu-id="c47aa-164"><b>Для США:</b> https:// <i></i> wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="c47aa-164"><b>For US:</b> https://<i></i>wdatp-alertexporter-us.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span> <br> <br> <span data-ttu-id="c47aa-165"><b>Для Великобритании</b>: https:// <i></i> wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span><span class="sxs-lookup"><span data-stu-id="c47aa-165"><b>For UK</b>:  https://<i></i>wdatp-alertexporter-uk.windows.com/api/alerts/?sinceTimeUtc=$START_AT_TIME</span></span></td>
    <tr>
    <td><span data-ttu-id="c47aa-166">Тип проверки подлинности</span><span class="sxs-lookup"><span data-stu-id="c47aa-166">Authentication Type</span></span></td>
    <td><span data-ttu-id="c47aa-167">OAuth 2</span><span class="sxs-lookup"><span data-stu-id="c47aa-167">OAuth 2</span></span></td>
    </tr>
    <td><span data-ttu-id="c47aa-168">Файл OAuth 2 Client Properties</span><span class="sxs-lookup"><span data-stu-id="c47aa-168">OAuth 2 Client Properties file</span></span></td>
    <td><span data-ttu-id="c47aa-169">Просмотрите расположение <em>файла wdatp-connector.properties.</em></span><span class="sxs-lookup"><span data-stu-id="c47aa-169">Browse to the location of the <em>wdatp-connector.properties</em> file.</span></span> <span data-ttu-id="c47aa-170">Имя должно совпадать с файлом, предоставленным в .zip, который вы скачали.</span><span class="sxs-lookup"><span data-stu-id="c47aa-170">The name must match the file provided in the .zip that you downloaded.</span></span></td>
    <tr>
    <td><span data-ttu-id="c47aa-171">Маркер обновления</span><span class="sxs-lookup"><span data-stu-id="c47aa-171">Refresh Token</span></span></td>
    <td><span data-ttu-id="c47aa-172">Маркер обновления можно получить двумя способами: путем создания маркера обновления на странице <b>параметров SIEM</b> или с помощью инструмента restutil.</span><span class="sxs-lookup"><span data-stu-id="c47aa-172">You can obtain a refresh token in two ways: by generating a refresh token from the <b>SIEM settings</b> page or using the restutil tool.</span></span> <br><br> <span data-ttu-id="c47aa-173">Дополнительные сведения о создании маркера обновления из настройки <b>"Настройки"</b> см. в руб. Включить интеграцию <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">SIEM в Defender for Endpoint.</a></span><span class="sxs-lookup"><span data-stu-id="c47aa-173">For more information on generating a refresh token from the <b>Preferences setup</b> , see <a href="enable-siem-integration.md" data-raw-source="[Enable SIEM integration in Defender for Endpoint](enable-siem-integration.md)">Enable SIEM integration in Defender for Endpoint</a>.</span></span> </br> </br><span data-ttu-id="c47aa-174"><b>Получите маркер обновления с помощью средства restutil:</b> </span><span class="sxs-lookup"><span data-stu-id="c47aa-174"><b>Get your refresh token using the restutil tool:</b> </span></span></br> <span data-ttu-id="c47aa-175">а.</span><span class="sxs-lookup"><span data-stu-id="c47aa-175">a.</span></span> <span data-ttu-id="c47aa-176">Откройте окно командной строки.</span><span class="sxs-lookup"><span data-stu-id="c47aa-176">Open a command prompt.</span></span> <span data-ttu-id="c47aa-177">Перейдите к C:\<em>folder_location</em>\current\bin, <em>folder_location</em> представляет расположение, где установлено средство.</span><span class="sxs-lookup"><span data-stu-id="c47aa-177">Navigate to C:\<em>folder_location</em>\current\bin where <em>folder_location</em> represents the location where you installed the tool.</span></span> </br></br> <span data-ttu-id="c47aa-178">б.</span><span class="sxs-lookup"><span data-stu-id="c47aa-178">b.</span></span> <span data-ttu-id="c47aa-179">Тип: <code>arcsight restutil token -config</code> из каталога бина. Например: <b>arcsight restutil boxtoken-proxy proxy.location.hp.com:8080</b> откроется окно веб-браузера.</span><span class="sxs-lookup"><span data-stu-id="c47aa-179">Type: <code>arcsight restutil token -config</code> from the bin directory.For example: <b>arcsight restutil boxtoken -proxy proxy.location.hp.com:8080</b> A Web browser window will open.</span></span> </br> </br><span data-ttu-id="c47aa-180">в.</span><span class="sxs-lookup"><span data-stu-id="c47aa-180">c.</span></span> <span data-ttu-id="c47aa-181">Введите учетные данные, а затем щелкните поле паролей, чтобы перенаправить страницу.</span><span class="sxs-lookup"><span data-stu-id="c47aa-181">Type in your credentials then click on the password field to let the page redirect.</span></span> <span data-ttu-id="c47aa-182">В запросе входа введите учетные данные.</span><span class="sxs-lookup"><span data-stu-id="c47aa-182">In the login prompt, enter your credentials.</span></span> </br> </br><span data-ttu-id="c47aa-183">г.</span><span class="sxs-lookup"><span data-stu-id="c47aa-183">d.</span></span> <span data-ttu-id="c47aa-184">Маркер обновления отображается в командной подсказке.</span><span class="sxs-lookup"><span data-stu-id="c47aa-184">A refresh token is shown in the command prompt.</span></span> </br></br> <span data-ttu-id="c47aa-185">д.</span><span class="sxs-lookup"><span data-stu-id="c47aa-185">e.</span></span> <span data-ttu-id="c47aa-186">Скопируйте и вклеите его в поле <b>Маркер обновления.</b></span><span class="sxs-lookup"><span data-stu-id="c47aa-186">Copy and paste it into the <b>Refresh Token</b> field.</span></span>
    </td>
    </tr>
    </tr>
    </table><br/>
    
7. <span data-ttu-id="c47aa-187">Соединитетелем открывается окно браузера.</span><span class="sxs-lookup"><span data-stu-id="c47aa-187">A browser window is opened by the connector.</span></span> <span data-ttu-id="c47aa-188">Войдите в систему с учетными данными приложения.</span><span class="sxs-lookup"><span data-stu-id="c47aa-188">Login with your application credentials.</span></span> <span data-ttu-id="c47aa-189">После входа вам будет предложено предоставить разрешение клиенту OAuth2.</span><span class="sxs-lookup"><span data-stu-id="c47aa-189">After you log in, you'll be asked to give permission to your OAuth2 Client.</span></span> <span data-ttu-id="c47aa-190">Необходимо предоставить разрешение клиенту OAuth 2 для проверки подлинности конфигурации соединители.</span><span class="sxs-lookup"><span data-stu-id="c47aa-190">You must give permission to your OAuth 2 Client so that the connector configuration can authenticate.</span></span>

   <span data-ttu-id="c47aa-191">Если <code>redirect_uri</code> url-адрес https, вы будете перенаправлены на URL-адрес локального хоста.</span><span class="sxs-lookup"><span data-stu-id="c47aa-191">If the <code>redirect_uri</code> is a https URL, you'll be redirected to a URL on the local host.</span></span> <span data-ttu-id="c47aa-192">Вы увидите страницу, на которую требуется доверять сертификату, предоставленного соединитетелем, работающим на локальном хосте.</span><span class="sxs-lookup"><span data-stu-id="c47aa-192">You'll see a page that requests for you to trust the certificate supplied by the connector running on the local host.</span></span> <span data-ttu-id="c47aa-193">Вам необходимо доверять этому сертификату, если redirect_uri является https.</span><span class="sxs-lookup"><span data-stu-id="c47aa-193">You'll need to trust this certificate if the redirect_uri is a https.</span></span>
   
   <span data-ttu-id="c47aa-194">Если же вы указываете URL-адрес http для redirect_uri, вам не нужно предоставлять согласие на доверие сертификату.</span><span class="sxs-lookup"><span data-stu-id="c47aa-194">If however you specify a http URL for the redirect_uri, you do not need to provide consent in trusting the certificate.</span></span>

8. <span data-ttu-id="c47aa-195">Продолжить установку соединиттеля, возвращаясь к окну Установки соединиттеля ArcSight Micro Focus.</span><span class="sxs-lookup"><span data-stu-id="c47aa-195">Continue with the connector setup by returning to the Micro Focus ArcSight Connector Setup window.</span></span>

9. <span data-ttu-id="c47aa-196">Выберите **диспетчер ArcSight (зашифрованный)** в качестве назначения и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-196">Select the **ArcSight Manager (encrypted)** as the destination and click **Next**.</span></span>

10. <span data-ttu-id="c47aa-197">Введите ip/hostname назначения в **имени hostname** диспетчера и учетные данные в форме параметров.</span><span class="sxs-lookup"><span data-stu-id="c47aa-197">Type in the destination IP/hostname in **Manager Hostname** and your credentials in the parameters form.</span></span> <span data-ttu-id="c47aa-198">Все остальные значения в форме должны сохраняться со значениями по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c47aa-198">All other values in the form should be retained with the default values.</span></span> <span data-ttu-id="c47aa-199">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-199">Click **Next**.</span></span>

11. <span data-ttu-id="c47aa-200">Введите имя соединитетеля в форме сведений о соединители.</span><span class="sxs-lookup"><span data-stu-id="c47aa-200">Type in a name for the connector in the connector details form.</span></span> <span data-ttu-id="c47aa-201">Все остальные значения в форме необязательны и могут быть оставлены пустыми.</span><span class="sxs-lookup"><span data-stu-id="c47aa-201">All other values in the form are optional and can be left blank.</span></span> <span data-ttu-id="c47aa-202">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-202">Click **Next**.</span></span>

12. <span data-ttu-id="c47aa-203">Отображается окно сертификата импорта ESM Manager.</span><span class="sxs-lookup"><span data-stu-id="c47aa-203">The ESM Manager import certificate window is shown.</span></span> <span data-ttu-id="c47aa-204">Выберите **импорт сертификата для соединитетеля из пункта назначения** и нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-204">Select **Import the certificate to connector from destination** and click **Next**.</span></span> <span data-ttu-id="c47aa-205">Отображается **окно Сводки соединителю** Добавить и импортируется сертификат.</span><span class="sxs-lookup"><span data-stu-id="c47aa-205">The **Add connector Summary** window is displayed and the certificate is imported.</span></span>

13. <span data-ttu-id="c47aa-206">Убедитесь, что сведения в окне **Сводка** добавить соединителю правильные, нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-206">Verify that the details in the **Add connector Summary** window is correct, then click **Next**.</span></span>

14. <span data-ttu-id="c47aa-207">Выберите **Установите в качестве службы и** нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-207">Select **Install as a service** and click **Next**.</span></span>

15. <span data-ttu-id="c47aa-208">Введите имя в **поле "Внутреннее имя** службы".</span><span class="sxs-lookup"><span data-stu-id="c47aa-208">Type a name in the **Service Internal Name** field.</span></span> <span data-ttu-id="c47aa-209">Все остальные значения в форме можно сохранить со значениями по умолчанию или оставить пустыми.</span><span class="sxs-lookup"><span data-stu-id="c47aa-209">All other values in the form can be retained with the default values or left blank .</span></span> <span data-ttu-id="c47aa-210">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-210">Click **Next**.</span></span>

16. <span data-ttu-id="c47aa-211">Введите параметры службы и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-211">Type in the service parameters and click **Next**.</span></span> <span data-ttu-id="c47aa-212">Отображается окно с **сводка** службы установки.</span><span class="sxs-lookup"><span data-stu-id="c47aa-212">A window with the **Install Service Summary** is shown.</span></span> <span data-ttu-id="c47aa-213">Нажмите **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-213">Click **Next**.</span></span>

17. <span data-ttu-id="c47aa-214">Завершите установку, выбрав **Exit** и **Далее.**</span><span class="sxs-lookup"><span data-stu-id="c47aa-214">Finish the installation by selecting **Exit** and **Next**.</span></span>

## <a name="install-and-configure-the-micro-focus-arcsight-console"></a><span data-ttu-id="c47aa-215">Установка и настройка консоли ArcSight Micro Focus</span><span class="sxs-lookup"><span data-stu-id="c47aa-215">Install and configure the Micro Focus ArcSight console</span></span>

1. <span data-ttu-id="c47aa-216">Выполните следующие задачи мастера установки:</span><span class="sxs-lookup"><span data-stu-id="c47aa-216">Follow the installation wizard through the following tasks:</span></span>
   - <span data-ttu-id="c47aa-217">Введение</span><span class="sxs-lookup"><span data-stu-id="c47aa-217">Introduction</span></span>
   - <span data-ttu-id="c47aa-218">Лицензионный договор</span><span class="sxs-lookup"><span data-stu-id="c47aa-218">License Agreement</span></span>
   - <span data-ttu-id="c47aa-219">Специальное уведомление</span><span class="sxs-lookup"><span data-stu-id="c47aa-219">Special Notice</span></span>
   - <span data-ttu-id="c47aa-220">Выбор каталога установки ArcSight</span><span class="sxs-lookup"><span data-stu-id="c47aa-220">Choose ArcSight installation directory</span></span>
   - <span data-ttu-id="c47aa-221">Выберите папку ярлыков</span><span class="sxs-lookup"><span data-stu-id="c47aa-221">Choose Shortcut Folder</span></span>
   - <span data-ttu-id="c47aa-222">Сводка предварительной установки</span><span class="sxs-lookup"><span data-stu-id="c47aa-222">Pre-Installation Summary</span></span>

2. <span data-ttu-id="c47aa-223">Нажать кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-223">Click **Install**.</span></span> <span data-ttu-id="c47aa-224">После завершения установки откроется мастер конфигурации консоли ArcSight.</span><span class="sxs-lookup"><span data-stu-id="c47aa-224">After the installation completes, the ArcSight Console Configuration Wizard opens.</span></span>

3. <span data-ttu-id="c47aa-225">Введите localhost в **имени хозяина диспетчера** и 8443 в **диспетчерском порту,** а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-225">Type localhost in **Manager Host Name** and 8443 in **Manager Port** then click **Next**.</span></span>

4. <span data-ttu-id="c47aa-226">Выберите **Использование прямого подключения,** а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-226">Select **Use direct connection**, then click **Next**.</span></span>

5. <span data-ttu-id="c47aa-227">Выберите **проверку подлинности на основе пароля,** а затем нажмите **кнопку Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-227">Select **Password Based Authentication**, then click **Next**.</span></span>

6. <span data-ttu-id="c47aa-228">Выберите **Это установка одного пользователя. (Рекомендуется)** и нажмите кнопку **Далее**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-228">Select **This is a single user installation. (Recommended)**, then click **Next**.</span></span>

7. <span data-ttu-id="c47aa-229">Щелкните **Кнопку Готово,** чтобы выйти из установки.</span><span class="sxs-lookup"><span data-stu-id="c47aa-229">Click **Done** to quit the installer.</span></span>

8. <span data-ttu-id="c47aa-230">Вход на консоль Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="c47aa-230">Login to the Micro Focus ArcSight console.</span></span>

9. <span data-ttu-id="c47aa-231">Перейдите к **набору active channel**  >  **New Condition**  >    >  **Device Device Product**.</span><span class="sxs-lookup"><span data-stu-id="c47aa-231">Navigate to **Active channel set** > **New Condition** > **Device** > **Device Product**.</span></span>

10. <span data-ttu-id="c47aa-232">Set **Device Product = ATP в Защитнике Microsoft.**</span><span class="sxs-lookup"><span data-stu-id="c47aa-232">Set **Device Product = Microsoft Defender ATP**.</span></span> <span data-ttu-id="c47aa-233">Когда вы убедились, что события течет в инструмент, остановите процесс снова и перейдите в службы Windows и запустите rest FlexConnector ArcSight.</span><span class="sxs-lookup"><span data-stu-id="c47aa-233">When you've verified that events are flowing to the tool, stop the process again and go to Windows Services and start the ArcSight FlexConnector REST.</span></span>

<span data-ttu-id="c47aa-234">Теперь можно запускать запросы в консоли Micro Focus ArcSight.</span><span class="sxs-lookup"><span data-stu-id="c47aa-234">You can now run queries in the Micro Focus ArcSight console.</span></span>

<span data-ttu-id="c47aa-235">Обнаружение Defender для конечных точек будет отображаться в качестве дискретных событий, а имя устройства — "Microsoft" в качестве поставщика Защитник Windows ATP.</span><span class="sxs-lookup"><span data-stu-id="c47aa-235">Defender for Endpoint detections will appear as discrete events, with "Microsoft” as the vendor and “Windows Defender ATP” as the device name.</span></span>


## <a name="troubleshooting-micro-focus-arcsight-connection"></a><span data-ttu-id="c47aa-236">Устранение неполадок подключение к Micro Focus ArcSight</span><span class="sxs-lookup"><span data-stu-id="c47aa-236">Troubleshooting Micro Focus ArcSight connection</span></span>

<span data-ttu-id="c47aa-237">**Проблема:** Не удалось обновить маркер.</span><span class="sxs-lookup"><span data-stu-id="c47aa-237">**Problem:** Failed to refresh the token.</span></span> <span data-ttu-id="c47aa-238">Вы можете найти журнал, расположенный в \\ *C: folder_location*\current\logs, folder_location представляет расположение, где установлено средство. </span><span class="sxs-lookup"><span data-stu-id="c47aa-238">You can find the log located in C:\\*folder_location*\current\logs where *folder_location* represents the location where you installed the tool.</span></span> <span data-ttu-id="c47aa-239">Откройте _agent.log_ и найдите `ERROR/FATAL/WARN` .</span><span class="sxs-lookup"><span data-stu-id="c47aa-239">Open _agent.log_ and look for `ERROR/FATAL/WARN`.</span></span>

<span data-ttu-id="c47aa-240">**Симптом:** Вы получите следующее сообщение об ошибке:</span><span class="sxs-lookup"><span data-stu-id="c47aa-240">**Symptom:** You get the following error message:</span></span>

`Failed to refresh the token. Set reauthenticate to true: com.arcsight.common.al.e: Failed to refresh access token: status=HTTP/1.1 400 Bad Request FATAL EXCEPTION: Could not refresh the access token`

<span data-ttu-id="c47aa-241">**Решение:**</span><span class="sxs-lookup"><span data-stu-id="c47aa-241">**Solution:**</span></span>

1. <span data-ttu-id="c47aa-242">Остановите процесс, щелкнув Ctrl + C в окне Соединителя.</span><span class="sxs-lookup"><span data-stu-id="c47aa-242">Stop the process by clicking Ctrl + C on the Connector window.</span></span> <span data-ttu-id="c47aa-243">Нажмите **кнопку Y** при запросе "Завершить пакетное задание Y/N?".</span><span class="sxs-lookup"><span data-stu-id="c47aa-243">Click **Y** when asked "Terminate batch job Y/N?".</span></span>

2. <span data-ttu-id="c47aa-244">Перейдите к папке, в которой хранится файл WDATP-connector.properties, и отредактировать его, чтобы добавить следующее значение: `reauthenticate=true` .</span><span class="sxs-lookup"><span data-stu-id="c47aa-244">Navigate to the folder where you stored the WDATP-connector.properties file and edit it to add the following value: `reauthenticate=true`.</span></span>

3. <span data-ttu-id="c47aa-245">Перезапустите соединитектор, запустив следующую команду: `arcsight.bat connectors` .</span><span class="sxs-lookup"><span data-stu-id="c47aa-245">Restart the connector by running the following command: `arcsight.bat connectors`.</span></span>

   <span data-ttu-id="c47aa-246">Появляется окно браузера.</span><span class="sxs-lookup"><span data-stu-id="c47aa-246">A browser window appears.</span></span> <span data-ttu-id="c47aa-247">Разрешить его запуск, он должен исчезнуть, и соединители должны быть запущены.</span><span class="sxs-lookup"><span data-stu-id="c47aa-247">Allow it to run, it should disappear, and the connector should now be running.</span></span>

> [!NOTE]
> <span data-ttu-id="c47aa-248">Убедитесь, что соединитатель запущен, остановив процесс снова.</span><span class="sxs-lookup"><span data-stu-id="c47aa-248">Verify that the connector is running by stopping the process again.</span></span> <span data-ttu-id="c47aa-249">Затем запустите соединители снова, и окно браузера не должно отображаться.</span><span class="sxs-lookup"><span data-stu-id="c47aa-249">Then start the connector again, and no browser window should appear.</span></span>

## <a name="related-topics"></a><span data-ttu-id="c47aa-250">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c47aa-250">Related topics</span></span>
- [<span data-ttu-id="c47aa-251">Включение интеграции SIEM в Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c47aa-251">Enable SIEM integration in Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="c47aa-252">Притягивать обнаружения к средствам SIEM</span><span class="sxs-lookup"><span data-stu-id="c47aa-252">Pull detections to your SIEM tools</span></span>](/windows/security/threat-protection/microsoft-defender-atp/configure-siem)
- [<span data-ttu-id="c47aa-253">Pull Defender для обнаружения конечных точек с помощью API REST</span><span class="sxs-lookup"><span data-stu-id="c47aa-253">Pull Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
- [<span data-ttu-id="c47aa-254">Устранение неполадок с интеграцией средства SIEM</span><span class="sxs-lookup"><span data-stu-id="c47aa-254">Troubleshoot SIEM tool integration issues</span></span>](troubleshoot-siem.md)
