---
title: Используйте средство экспорта электронных открытий в Microsoft Edge
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
description: Вы должны включить ClickOnce для использования самой новой версии Microsoft Edge для загрузки результатов поиска из центра поиска контента и поиска электронных данных в центре безопасности и соответствия требованиям.
ms.openlocfilehash: 60f42d2884c56aaff40bc0a6a979e99698a3cd2e
ms.sourcegitcommit: 27daadad9ca0f02a833ff3cff8a574551b9581da
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2020
ms.locfileid: "47546823"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="0a7c7-103">Используйте средство экспорта электронных открытий в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0a7c7-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="0a7c7-104">В результате недавних изменений в новейшей версии Microsoft Edge поддержка ClickOnce больше не включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="0a7c7-105">Чтобы продолжить использование экспортного средства eDiscovery для загрузки результатов поиска контента или поиска по электронной информации, необходимо либо использовать [Microsoft Internet Explorer,](https://support.microsoft.com/help/17621/internet-explorer-downloads) либо включить ClickOnce поддержку в самой новой версии Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="0a7c7-106">Включить ClickOnce в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0a7c7-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="0a7c7-107">В Microsoft Edge перейдите **в edge://flags/#edge-click-once**.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="0a7c7-108">Если существующее значение за установлено по **умолчанию** или **отключено** в списке выпаданий, измените его на **Включено.**</span><span class="sxs-lookup"><span data-stu-id="0a7c7-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Выберите Включено из списка выпаданий](../media/ClickOnceimage1.png)

3. <span data-ttu-id="0a7c7-110">Прокрутите вниз в нижней части окна браузера и нажмите **кнопку Перезапустить,** чтобы перезапустить Edge.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Щелкните Перезапуск](../media/ClickOnceimage2.png)

<span data-ttu-id="0a7c7-112">**Примечание:** Организации могут использовать групповую политику для отключения ClickOnce поддержки.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="0a7c7-113">Чтобы проверить, существует ли организационной политики ClickOnce поддержки, перейдите в **edge://policy**.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="0a7c7-114">На следующем скриншоте показано ClickOnce включена вся организация.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="0a7c7-115">Если это значение политики установлено как **ложное,** необходимо обратиться к администратору в организации.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Список организационных политик Edge](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="0a7c7-117">Установка и запуск экспортного средства eDiscovery</span><span class="sxs-lookup"><span data-stu-id="0a7c7-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="0a7c7-118">Нажмите **кнопку Скачать** результаты на странице вылет экспорта в поиске контента или случае поиска электронной информации.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Нажмите кнопку Скачать результаты на странице вылет, чтобы скачать результаты поиска](../media/ClickOnceExport1.png)

2. <span data-ttu-id="0a7c7-120">Вам будет предложено подтверждение о запуске средства Нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Нажмите кнопку Открыть, чтобы запустить средство экспорта электронных обнаружений](../media/ClickOnceimage4.png)

   <span data-ttu-id="0a7c7-122">Если средство экспорта электронных данных не установлено, вам будет предложено предупреждение о безопасности,</span><span class="sxs-lookup"><span data-stu-id="0a7c7-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Щелкните Установите, чтобы установить средство экспорта электронных обнаружений](../media/ClickOnceimage5.png)

3. <span data-ttu-id="0a7c7-124">Нажать кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-124">Click **Install**.</span></span> <span data-ttu-id="0a7c7-125">После установки средство экспорта запускается автоматически.</span><span class="sxs-lookup"><span data-stu-id="0a7c7-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="0a7c7-126">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="0a7c7-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="0a7c7-127">Экспорт результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="0a7c7-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="0a7c7-128">Как включить флаги эксперимента в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="0a7c7-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
