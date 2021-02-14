---
title: Использование средства экспорта для eDiscovery в Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Необходимо включить поддержку ClickOnce использовать новую версию Microsoft Edge для скачивания результатов поиска контента и eDiscovery в Центре безопасности и соответствия требованиям.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546823"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="bc4fc-103">Использование средства экспорта для eDiscovery в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bc4fc-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="bc4fc-104">В результате последних изменений последней версии Microsoft Edge поддержка ClickOnce больше не включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="bc4fc-105">Чтобы продолжить использование средства экспорта eDiscovery для скачивания результатов поиска контента или eDiscovery, необходимо либо использовать [Microsoft Internet Explorer,](https://support.microsoft.com/help/17621/internet-explorer-downloads) либо включить поддержку ClickOnce в самой новой версии Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="bc4fc-106">Включить поддержку ClickOnce в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bc4fc-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="bc4fc-107">В Microsoft Edge перейдите **к edge://flags/#edge-click-once.**</span><span class="sxs-lookup"><span data-stu-id="bc4fc-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="bc4fc-108">Если в списке **выпаданий** установлено значение Default или **Disabled,** измените его на **"Включено".**</span><span class="sxs-lookup"><span data-stu-id="bc4fc-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Выберите "Включено" в выпадаемом списке](../media/ClickOnceimage1.png)

3. <span data-ttu-id="bc4fc-110">Прокрутите страницу вниз до нижней части окна браузера и нажмите кнопку **"Перезапустить",** чтобы перезапустить Edge.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Нажмите кнопку "Перезапустить"](../media/ClickOnceimage2.png)

<span data-ttu-id="bc4fc-112">**Примечание.** Организации могут использовать групповую политику для отключения ClickOnce поддержки.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="bc4fc-113">Чтобы проверить, существует ли политика организации для поддержки ClickOnce, перейдите **по edge://policy.**</span><span class="sxs-lookup"><span data-stu-id="bc4fc-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="bc4fc-114">На следующем снимке экрана показано ClickOnce включено во всей организации.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="bc4fc-115">Если для этого значения политики установлено **значение false,** вам потребуется связаться с администратором в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Список политик организации edge](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="bc4fc-117">Установка и запуск средства экспорта для eDiscovery</span><span class="sxs-lookup"><span data-stu-id="bc4fc-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="bc4fc-118">Нажмите **кнопку "Скачать** результаты" на странице "Экспорт" в запросе "Поиск контента" или в деле eDiscovery.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Щелкните "Скачать результаты" на странице "Скачать" для скачивания результатов поиска](../media/ClickOnceExport1.png)

2. <span data-ttu-id="bc4fc-120">Вам будет предложено подтвердить запуск средства, нажмите кнопку **"Открыть".**</span><span class="sxs-lookup"><span data-stu-id="bc4fc-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Нажмите кнопку "Открыть", чтобы запустить средство экспорта eDiscovery](../media/ClickOnceimage4.png)

   <span data-ttu-id="bc4fc-122">Если средство экспорта для eDiscovery не установлено, вам будет предложено предупреждение системы безопасности.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Click Install to install the eDiscovery Export Tool](../media/ClickOnceimage5.png)

3. <span data-ttu-id="bc4fc-124">Нажмите **Установить**.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-124">Click **Install**.</span></span> <span data-ttu-id="bc4fc-125">После установки средство экспорта запустится автоматически.</span><span class="sxs-lookup"><span data-stu-id="bc4fc-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="bc4fc-126">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="bc4fc-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="bc4fc-127">Экспорт результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="bc4fc-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="bc4fc-128">Как включить флаги экспериментов в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="bc4fc-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
