---
title: Использование средства экспорта eDiscovery в Microsoft Edge
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: how-to
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
description: Для загрузки результатов поиска из поиска контента и обнаружения электронных данных в центре безопасности и соответствия требованиям необходимо включить поддержку ClickOnce, чтобы использовать последнюю версию Microsoft Edge.
ms.openlocfilehash: 317e19c81a606565fcb18f3256fd5bac007747e1
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357579"
---
# <a name="use-the-ediscovery-export-tool-in-microsoft-edge"></a><span data-ttu-id="c25b8-103">Использование средства экспорта eDiscovery в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c25b8-103">Use the eDiscovery Export Tool in Microsoft Edge</span></span>

<span data-ttu-id="c25b8-104">В результате последних изменений, внесенных в последнюю версию Microsoft EDGE, поддержка ClickOnce больше не включена по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="c25b8-104">As a result of recent changes to the newest version of Microsoft Edge, ClickOnce support is no longer enabled by default.</span></span> <span data-ttu-id="c25b8-105">Чтобы продолжить использование средства экспорта eDiscovery для загрузки результатов поиска или обнаружения электронных данных, необходимо использовать [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) или включить поддержку ClickOnce в последней версии Microsoft Edge.</span><span class="sxs-lookup"><span data-stu-id="c25b8-105">To continue using the eDiscovery Export Tool to download Content Search or eDiscovery search results, you either need to use [Microsoft Internet Explorer](https://support.microsoft.com/help/17621/internet-explorer-downloads) or enable ClickOnce support in the newest version of Microsoft Edge.</span></span>

## <a name="enable-clickonce-support-in-microsoft-edge"></a><span data-ttu-id="c25b8-106">Включение поддержки ClickOnce в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c25b8-106">Enable ClickOnce support in Microsoft Edge</span></span>

1. <span data-ttu-id="c25b8-107">В Microsoft Edge последовательно выберите пункты **edge://flags/#edge — один раз**.</span><span class="sxs-lookup"><span data-stu-id="c25b8-107">In Microsoft Edge, go to **edge://flags/#edge-click-once**.</span></span>

2. <span data-ttu-id="c25b8-108">Если в раскрывающемся списке существующее значение установлено **по умолчанию** или **отключено** , измените его на **Enabled**.</span><span class="sxs-lookup"><span data-stu-id="c25b8-108">If the existing value is set to **Default** or **Disabled** in the dropdown list, change it to **Enabled**.</span></span>

   ![Выберите элемент включено из раскрывающегося списка](../media/ClickOnceimage1.png)

3. <span data-ttu-id="c25b8-110">Прокрутите окно вниз до конца окна браузера и выберите команду **перезапустить** , чтобы перезапустить пограничный сервер.</span><span class="sxs-lookup"><span data-stu-id="c25b8-110">Scroll down to the bottom of the browser window and click **Restart** to restart Edge.</span></span>

   ![Нажмите кнопку перезапустить](../media/ClickOnceimage2.png)

<span data-ttu-id="c25b8-112">**Примечание:** Для отключения поддержки ClickOnce в организациях можно использовать групповую политику.</span><span class="sxs-lookup"><span data-stu-id="c25b8-112">**Note:** Organizations can use Group Policy to disable ClickOnce support.</span></span> <span data-ttu-id="c25b8-113">Чтобы проверить, существует ли политика Организации для поддержки ClickOnce, перейдите в **Edge://Policy**.</span><span class="sxs-lookup"><span data-stu-id="c25b8-113">To check if there is an organizational policy for ClickOnce support, go to **edge://policy**.</span></span> <span data-ttu-id="c25b8-114">На следующем снимке экрана показано, что технология ClickOnce включена во всей Организации.</span><span class="sxs-lookup"><span data-stu-id="c25b8-114">The following screenshot shows that ClickOnce is enabled across the entire organization.</span></span> <span data-ttu-id="c25b8-115">Если для этого параметра политики задано значение **false**, необходимо обратиться к администратору в Организации.</span><span class="sxs-lookup"><span data-stu-id="c25b8-115">If this policy value is set to **false**, you will need to contact an admin in your organization.</span></span>

![Список политик пограничных организационных организаций](../media/ClickOnceimage3.png)

## <a name="install-and-run-the-ediscovery-export-tool"></a><span data-ttu-id="c25b8-117">Установка и запуск средства экспорта eDiscovery</span><span class="sxs-lookup"><span data-stu-id="c25b8-117">Install and run the eDiscovery Export Tool</span></span>

1. <span data-ttu-id="c25b8-118">Нажмите кнопку **скачать результаты** на всплывающей странице экспорта в поиске контента или в случае обнаружения электронных данных.</span><span class="sxs-lookup"><span data-stu-id="c25b8-118">Click **Download results** on the flyout page of an export in Content Search or an eDiscovery case.</span></span>

   ![Нажмите кнопку Скачать результаты на всплывающей странице, чтобы скачать результаты поиска.](../media/ClickOnceExport1.png)

2. <span data-ttu-id="c25b8-120">Появится запрос на подтверждение запуска средства, нажмите кнопку **Открыть**.</span><span class="sxs-lookup"><span data-stu-id="c25b8-120">You will be prompted with a confirmation to launch the tool, Click **Open**.</span></span>

   ![Нажмите кнопку Открыть, чтобы запустить средство экспорта eDiscovery](../media/ClickOnceimage4.png)

   <span data-ttu-id="c25b8-122">Если средство экспорта eDiscovery не установлено, появится предупреждение системы безопасности,</span><span class="sxs-lookup"><span data-stu-id="c25b8-122">If the eDiscovery Export Tool isn't installed, you will be prompted with a Security Warning,</span></span> 

   ![Нажмите кнопку установить, чтобы установить средство экспорта обнаружения электронных данных](../media/ClickOnceimage5.png)

3. <span data-ttu-id="c25b8-124">Нажать кнопку **Установить**.</span><span class="sxs-lookup"><span data-stu-id="c25b8-124">Click **Install**.</span></span> <span data-ttu-id="c25b8-125">После установки средство экспорта будет запущено автоматически.</span><span class="sxs-lookup"><span data-stu-id="c25b8-125">After it's installed, the export tool will launch automatically.</span></span>

<span data-ttu-id="c25b8-126">Дополнительную информацию см. в следующих статьях:</span><span class="sxs-lookup"><span data-stu-id="c25b8-126">For more information, see the following topics:</span></span>

- [<span data-ttu-id="c25b8-127">Экспорт результатов поиска контента</span><span class="sxs-lookup"><span data-stu-id="c25b8-127">Export Content Search results</span></span>](export-search-results.md)

- [<span data-ttu-id="c25b8-128">Включение поэкспериментических флагов в Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="c25b8-128">How to enable experiment flags in Microsoft Edge</span></span>](https://microsoftedgesupport.microsoft.com/hc/articles/360034075294-How-to-enable-experiment-flags-in-Microsoft-Edge-Insider-channels)
