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
ms.openlocfilehash: 50e7bc6d84714411c89f014bb0018a3102617cb7
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51074094"
---
# <a name="collect-support-logs-in-microsoft-defender-for-endpoint-using-live-response"></a><span data-ttu-id="7b1f3-104">Сбор журналов поддержки в Microsoft Defender для конечной точки с помощью живого ответа</span><span class="sxs-lookup"><span data-stu-id="7b1f3-104">Collect support logs in Microsoft Defender for Endpoint using live response</span></span> 


<span data-ttu-id="7b1f3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="7b1f3-105">**Applies to:**</span></span>
- [<span data-ttu-id="7b1f3-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="7b1f3-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [<span data-ttu-id="7b1f3-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="7b1f3-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

> <span data-ttu-id="7b1f3-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="7b1f3-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="7b1f3-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="7b1f3-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 


<span data-ttu-id="7b1f3-110">При контакте с поддержкой может потребоваться предоставить пакет вывода средства клиентского анализатора Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="7b1f3-110">When contacting support, you may be asked to provide the output package of the Microsoft Defender for Endpoint Client Analyzer tool.</span></span>

<span data-ttu-id="7b1f3-111">В этом разделе указаны инструкции по запуску средства с помощью Live Response.</span><span class="sxs-lookup"><span data-stu-id="7b1f3-111">This topic provides instructions on how to run the tool via Live Response.</span></span>

1. <span data-ttu-id="7b1f3-112">Скачайте соответствующий скрипт</span><span class="sxs-lookup"><span data-stu-id="7b1f3-112">Download the appropriate script</span></span>
    * <span data-ttu-id="7b1f3-113">Только журналы датчиков клиентских датчиков Microsoft Defender [ для конечных](https://aka.ms/MDELiveAnalyzer)точек:LiveAnalyzer.ps1 скрипт .</span><span class="sxs-lookup"><span data-stu-id="7b1f3-113">Microsoft Defender for Endpoint client sensor logs only: [LiveAnalyzer.ps1 script](https://aka.ms/MDELiveAnalyzer).</span></span>
      - <span data-ttu-id="7b1f3-114">Примерный размер пакета результатов: ~100Kb</span><span class="sxs-lookup"><span data-stu-id="7b1f3-114">Result package approximate size: ~100Kb</span></span> 
    *  <span data-ttu-id="7b1f3-115">Microsoft Defender для клиентского датчика конечных точек и журналов антивирусов: [сценарий LiveAnalyzer+MDAV.ps1](https://aka.ms/MDELiveAnalyzerAV).</span><span class="sxs-lookup"><span data-stu-id="7b1f3-115">Microsoft Defender for Endpoint client sensor and Antivirus logs: [LiveAnalyzer+MDAV.ps1 script](https://aka.ms/MDELiveAnalyzerAV).</span></span>
       - <span data-ttu-id="7b1f3-116">Примерный размер пакета результатов: ~10Mb</span><span class="sxs-lookup"><span data-stu-id="7b1f3-116">Result package approximate size: ~10Mb</span></span> 
 
2.  <span data-ttu-id="7b1f3-117">[Инициировать сеанс живого ответа](live-response.md#initiate-a-live-response-session-on-a-device) на компьютере, который необходимо исследовать.</span><span class="sxs-lookup"><span data-stu-id="7b1f3-117">Initiate a [Live Response session](live-response.md#initiate-a-live-response-session-on-a-device) on the machine you need to investigate.</span></span>

3.  <span data-ttu-id="7b1f3-118">Выберите **Файл Отправка в библиотеку.**</span><span class="sxs-lookup"><span data-stu-id="7b1f3-118">Select **Upload file to library**.</span></span>

    ![Изображение файла загрузки](images/upload-file.png)

4. <span data-ttu-id="7b1f3-120">Выберите **файл Выбор**.</span><span class="sxs-lookup"><span data-stu-id="7b1f3-120">Select **Choose file**.</span></span>

    ![Изображение кнопки выбрать файл1](images/choose-file.png)

5. <span data-ttu-id="7b1f3-122">Выберите загруженный файл с именем MDELiveAnalyzer.ps1 и нажмите кнопку **Подтвердить**</span><span class="sxs-lookup"><span data-stu-id="7b1f3-122">Select the downloaded file named MDELiveAnalyzer.ps1 and then click on **Confirm**</span></span>


   ![Изображение кнопки выбрать файл2](images/analyzer-file.png)


6. <span data-ttu-id="7b1f3-124">В сеансе LiveResponse используйте команды ниже, чтобы запустить анализатор и собрать файл результатов:</span><span class="sxs-lookup"><span data-stu-id="7b1f3-124">While still in the LiveResponse session, use the commands below to run the analyzer and collect the result file:</span></span>

    ```console
    Run MDELiveAnalyzer.ps1
    GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
    ```

    ![Изображение команд](images/analyzer-commands.png)


>[!NOTE]
> - <span data-ttu-id="7b1f3-126">Последнюю версию предварительного просмотра MDEClientAnalyzer можно скачать здесь: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer) .</span><span class="sxs-lookup"><span data-stu-id="7b1f3-126">The latest preview version of MDEClientAnalyzer can be downloaded here: [https://aka.ms/Betamdeanalyzer](https://aka.ms/Betamdeanalyzer).</span></span>
> 
> - <span data-ttu-id="7b1f3-127">Скрипт LiveAnalyzer загружает пакет устранения неполадок на машине назначения из: https://mdatpclientanalyzer.blob.core.windows.net .</span><span class="sxs-lookup"><span data-stu-id="7b1f3-127">The LiveAnalyzer script downloads the troubleshooting package on the destination machine from: https://mdatpclientanalyzer.blob.core.windows.net.</span></span>
> 
>   <span data-ttu-id="7b1f3-128">Если вы не можете разрешить компьютеру достичь вышеуказанного URL-адреса, MDEClientAnalyzerPreview.zip файл в библиотеку перед запуском сценария LiveAnalyzer:</span><span class="sxs-lookup"><span data-stu-id="7b1f3-128">If you cannot allow the machine to reach the above URL, then upload MDEClientAnalyzerPreview.zip file to the library before running the LiveAnalyzer script:</span></span>
>
>   ```console
>   PutFile MDEClientAnalyzerPreview.zip -overwrite
>   Run MDELiveAnalyzer.ps1
>   GetFile "C:\ProgramData\Microsoft\Windows Defender Advanced Threat Protection\Downloads\MDEClientAnalyzerResult.zip" -auto
>   ```
> 
> - <span data-ttu-id="7b1f3-129">Дополнительные сведения о локальном сборе данных на компьютере в том случае, если машина не общается с облачными службами Microsoft Defender для конечных точек или не появляется на портале Microsoft Defender для конечных точек, как ожидалось, см. в примере [Verify client connectivity to Microsoft Defender for Endpoint service](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls)URL-адреса.</span><span class="sxs-lookup"><span data-stu-id="7b1f3-129">For more information on gathering data locally on a machine in case the machine isn't communicating with Microsoft Defender for Endpoint cloud services, or does not appear in Microsoft Defender for Endpoint portal as expected, see [Verify client connectivity to Microsoft Defender for Endpoint service URLs](configure-proxy-internet.md#verify-client-connectivity-to-microsoft-defender-atp-service-urls).</span></span>
