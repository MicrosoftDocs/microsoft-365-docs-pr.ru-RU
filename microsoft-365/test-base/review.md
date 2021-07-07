---
title: Проверка
description: Обзор раздела после висят.
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
ms.openlocfilehash: 3bbd4959dd2f595e6e33e7967a719cf64072c06f
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323287"
---
# <a name="step-6-review-your-selections-to-create-your-package"></a><span data-ttu-id="3d6d9-103">Шаг 6. Просмотрите выбор, чтобы создать пакет.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-103">Step 6: Review your selections to create your package.</span></span>

1.  <span data-ttu-id="3d6d9-104">На этой вкладке служба отображает сведения о тесте и выполняет быструю проверку полноты.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-104">On this tab, the service displays your test details and runs a quick completeness check.</span></span> 

    <span data-ttu-id="3d6d9-105">A ```Validation passed``` или message shows ```Validation failed``` whether you can proceed to next steps or not.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-105">A ```Validation passed``` or ```Validation failed``` message shows whether you can proceed to next steps or not.</span></span>

2.  <span data-ttu-id="3d6d9-106">Просмотрите сведения о тесте, и если вы удовлетворены, нажмите ```Create``` кнопку.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-106">Review your test details and if satisfied, click on the ```Create``` button.</span></span> 

![Проверка просмотра](Media/validation.png)

3.  <span data-ttu-id="3d6d9-108">Это будет на борту пакета в среде тестовой базы.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-108">This will onboard your package to the Test Base environment.</span></span> <span data-ttu-id="3d6d9-109">Если пакет успешно создан, запускается автоматический тест, который проверяет, можно ли успешно выполнять пакет в Azure.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-109">If your package is successfully created, an automated test which verifys whether your package can be successfully executed on Azure will be triggered.</span></span>

![Успешный результат](Media/successful.png)

> [!Note]
> <span data-ttu-id="3d6d9-111">Вы получите уведомление с портала Azure, чтобы уведомить вас об успешности или сбое проверки пакета.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-111">You will get a notification from the Azure portal to notify you on the success or failure of the package verification.</span></span> 
>
> <span data-ttu-id="3d6d9-112">Обратите внимание, что процесс может занять до 24 часов, поэтому, скорее всего, ваш веб-сайт будет времявыполнения времени, если вы не активны на нем и, следовательно, уведомление не будет информировать вас о завершении этого по требованию выполнения.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-112">Please note that the process can take up to 24 hours, so it is likely your webpage will timeout if you are not active on it and hence, the notification will not inform you of the completion of this on-demand run.</span></span> 

  - <span data-ttu-id="3d6d9-113">Peradventure это происходит, вы можете просмотреть состояние пакета на ```Manage packages``` вкладке.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-113">Peradventure this happens, you can view the status of your package on the ```Manage packages``` tab.</span></span>

![Изображение для управления пакетами](Media/managepackages.png)

  - <span data-ttu-id="3d6d9-115">Для результативных тестов их результаты можно увидеть через запланированные интервалы и страницы, которые часто начинаются через несколько дней после ```Test Summary``` ```Security Updates Results``` ```Feature Updates Results``` отправки.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-115">For succesful tests, their results can be seen via the ```Test Summary```, ```Security Updates Results``` and ```Feature Updates Results``` pages at scheduled intervals, often starting a few days after your upload.</span></span>
  
  - <span data-ttu-id="3d6d9-116">Несмотря на сбой тестов, необходимо загрузить новый пакет.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-116">While failed tests, require you to upload a new package.</span></span> 
  
    <span data-ttu-id="3d6d9-117">Вы можете скачать ```test logs``` для дальнейшего анализа с ```Security update results``` "и ```Feature updates results``` страниц.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-117">You can download the ```test logs``` for further analysis from the ‘```Security update results``` and ```Feature updates results``` pages.</span></span>

  - <span data-ttu-id="3d6d9-118">При повторных сбоях тестирования обратитесь к testbasepreview@microsoft.com с подробными сведениями об ошибке.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-118">If you experience repeated test failures, please reach out to testbasepreview@microsoft.com with details of your error.</span></span> 

## <a name="next-steps"></a><span data-ttu-id="3d6d9-119">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="3d6d9-119">Next steps</span></span>

<span data-ttu-id="3d6d9-120">Откройте для себя рекомендации по контенту по ссылке ниже.</span><span class="sxs-lookup"><span data-stu-id="3d6d9-120">Discover our Content Guidelines via the link below.</span></span>
> [!div class="nextstepaction"]
> [<span data-ttu-id="3d6d9-121">Следующий этап</span><span class="sxs-lookup"><span data-stu-id="3d6d9-121">Next step</span></span>](contentguideline.md)
