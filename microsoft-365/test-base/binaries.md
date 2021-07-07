---
title: Upload Разнонабные приложения
description: Как начать работу с помощью тестовой базы для M365
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 1c4ff6ac03989cc9be70e18a1b8634f2da11e721
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323167"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a><span data-ttu-id="36434-103">Шаг 3. Upload, зависимостей и сценариев</span><span class="sxs-lookup"><span data-stu-id="36434-103">Step 3: Upload your binaries, dependencies, and scripts</span></span>

<span data-ttu-id="36434-104">На этой вкладке будет загружен один почтовый пакет, содержащий ваши сеяния, зависимости и скрипты, используемые для запуска тестового пакета.</span><span class="sxs-lookup"><span data-stu-id="36434-104">On this tab, you will upload a single zip package containing your binaries, dependencies and scripts used to run your test suite.</span></span>

## <a name="upload-package-zip-file"></a><span data-ttu-id="36434-105">Upload почтовый файл пакета</span><span class="sxs-lookup"><span data-stu-id="36434-105">Upload package zip file</span></span>

![Upload ваших бинарей](Media/AddBinaries.png)

  - <span data-ttu-id="36434-107">Загруженные зависимости могут включать тестовые фреймворки, механизмы сценариев или данные, которые будут доступны для запуска приложений или тестовых случаев.</span><span class="sxs-lookup"><span data-stu-id="36434-107">Uploaded dependencies can include test frameworks, scripting engines or data that will be accessed to run your application or test cases.</span></span> <span data-ttu-id="36434-108">Например, вы можете загрузить selenium и установщик веб-драйвера для запуска тестов на основе браузера.</span><span class="sxs-lookup"><span data-stu-id="36434-108">For example, you can upload Selenium and a webdriver installer to help run browser-based tests.</span></span>
  - <span data-ttu-id="36434-109">Лучше всего обеспечить, чтобы действия скрипта были модульными, то есть.</span><span class="sxs-lookup"><span data-stu-id="36434-109">It is best practice to ensure your script activities are kept modular i.e.</span></span> 
    - <span data-ttu-id="36434-110">Скрипт ```Install``` выполняет только операции установки.</span><span class="sxs-lookup"><span data-stu-id="36434-110">The ```Install``` script only performs install operations.</span></span>
    - <span data-ttu-id="36434-111">Скрипт ```Launch``` запускает только приложение.</span><span class="sxs-lookup"><span data-stu-id="36434-111">The ```Launch``` script only launches the application.</span></span>
    - <span data-ttu-id="36434-112">Скрипт ```Close``` закрывает только приложение.</span><span class="sxs-lookup"><span data-stu-id="36434-112">The ```Close``` script only closes the application.</span></span>
    - <span data-ttu-id="36434-113">```Uninstall```Необязательный скрипт только анинсталирует приложение.</span><span class="sxs-lookup"><span data-stu-id="36434-113">The optional ```Uninstall``` script only uninstalls the application.</span></span>

<span data-ttu-id="36434-114">**В настоящее время портал поддерживает только скрипты PowerShell.**</span><span class="sxs-lookup"><span data-stu-id="36434-114">**Currently, the portal only supports PowerShell scripts.**</span></span>


## <a name="next-steps"></a><span data-ttu-id="36434-115">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="36434-115">Next steps</span></span> 

<span data-ttu-id="36434-116">Перейти к следующей статье, чтобы перейти на шаг 4: **Установите тестовые задачи**.</span><span class="sxs-lookup"><span data-stu-id="36434-116">Advance to the next article to go onto Step 4: **Set your Test Tasks**.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="36434-117">Вернуться</span><span class="sxs-lookup"><span data-stu-id="36434-117">Go back</span></span>](uploadApplication.md)
> [!div class="nextstepaction"]
> [<span data-ttu-id="36434-118">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="36434-118">Next step</span></span>](testtask.md)

