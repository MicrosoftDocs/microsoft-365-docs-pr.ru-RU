---
title: Сбор журналов поддержки в Microsoft Defender для конечных точек с помощью живого ответа
description: Узнайте, как собирать журналы с помощью живой реакции на устранение неполадок Microsoft Defender для конечных точек
keywords: поддержка, журнал, сбор, устранение неполадок, живой ответ, liveanalyzer, анализатор, live, ответ
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 07593fac6ed9a3fbc00d904718380b386f31dba3
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893417"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="cb25f-104">Сбор журналов поддержки в Microsoft Defender для конечной точки с помощью живого ответа</span><span class="sxs-lookup"><span data-stu-id="cb25f-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="cb25f-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cb25f-105">**Applies to:**</span></span>
- [<span data-ttu-id="cb25f-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cb25f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="cb25f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="cb25f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="cb25f-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="cb25f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="cb25f-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="cb25f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="cb25f-110">При контакте с поддержкой может потребоваться предоставить пакет вывода средства клиентского анализатора Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="cb25f-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="cb25f-111">В этом разделе указаны инструкции по запуску средства с помощью Live Response.</span><span class="sxs-lookup"><span data-stu-id="cb25f-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="cb25f-112">Скачайте соответствующий скрипт</span><span class="sxs-lookup"><span data-stu-id="cb25f-112">Download the appropriate script</span></span>
    * <span data-ttu-id="cb25f-113">Только журналы датчиков клиентских датчиков Microsoft Defender [ для конечных](https://aka.ms/MDELiveAnalyzer)точек:LiveAnalyzer.ps1 скрипт .</span><span class="sxs-lookup"><span data-stu-id="cb25f-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="cb25f-114">Примерный размер пакета результатов: ~100Kb</span><span class="sxs-lookup"><span data-stu-id="cb25f-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="cb25f-115">Microsoft Defender для клиентского датчика конечных точек и журналов антивирусов: [сценарий LiveAnalyzer+MDAV.ps1](https://aka.ms/MDELiveAnalyzerAV).</span><span class="sxs-lookup"><span data-stu-id="cb25f-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="cb25f-116">Примерный размер пакета результатов: ~10Mb</span><span class="sxs-lookup"><span data-stu-id="cb25f-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="cb25f-117">[Инициировать сеанс живого ответа](live-response.md#initiate-a-live-response-session-on-a-device) на компьютере, который необходимо исследовать.</span><span class="sxs-lookup"><span data-stu-id="cb25f-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="cb25f-118">Выберите **Файл Отправка в библиотеку.**</span><span class="sxs-lookup"><span data-stu-id="cb25f-118">Select **Upload file to library**.</span></span>

    ![Изображение файла загрузки](images/upload-file.png)

4. <span data-ttu-id="cb25f-120">Выберите **файл Выбор**.</span><span class="sxs-lookup"><span data-stu-id="cb25f-120">Select **Choose file**.</span></span>

    ![Изображение кнопки выбрать файл1](images/choose-file.png)

5. <span data-ttu-id="cb25f-122">Выберите загруженный файл с именем MDELiveAnalyzer.ps1 и нажмите кнопку **Подтвердить**</span><span class="sxs-lookup"><span data-stu-id="cb25f-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![Изображение кнопки выбрать файл2](images/analyzer-file.png)


6. <span data-ttu-id="cb25f-124">В сеансе LiveResponse используйте команды ниже, чтобы запустить анализатор и собрать файл результатов:</span><span class="sxs-lookup"><span data-stu-id="cb25f-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    <span data-ttu-id="cb25f-125">[![Изображение команд ](images/analyzer-commands.png)](images/analyzer-commands.png#lightbox)</span><span class="sxs-lookup"><span data-stu-id="cb25f-125">[ ![Image of commands](images/analyzer-commands.png) ](images/analyzer-commands.png#lightbox)</span></span>


>[!NOTE]
> - <span data-ttu-id="cb25f-126">Последнюю версию предварительного просмотра MDEClientAnalyzer можно скачать здесь: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .</span><span class="sxs-lookup"><span data-stu-id="cb25f-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="cb25f-127">Скрипт LiveAnalyzer загружает пакет устранения неполадок на машине назначения из: https://mdatpclientanalyzer.blob.core.windows.net .</span><span class="sxs-lookup"><span data-stu-id="cb25f-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="cb25f-128">Если вы не можете разрешить компьютеру достичь вышеуказанного URL-адреса, MDEClientAnalyzerPreview.zip файл в библиотеку перед запуском сценария LiveAnalyzer:</span><span class="sxs-lookup"><span data-stu-id="cb25f-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - <span data-ttu-id="cb25f-129">Дополнительные сведения о локальном сборе данных на компьютере в том случае, если машина не общается с облачными службами Microsoft Defender для конечных точек или не появляется на портале Microsoft Defender для конечных точек, как ожидалось, см. в примере [Verify client connectivity to Microsoft Defender for Endpoint service](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls)URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="cb25f-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-for-endpoint-service-urls).</span></span>
