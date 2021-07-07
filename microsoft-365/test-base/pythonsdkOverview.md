---
title: Тестовый базовый SDK для Python
description: Сведения о понимании SDK тестовой базы для Python
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/07/2021
ms.locfileid: "53323124"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="5a140-103">Тестовый базовый SDK для Python</span><span class="sxs-lookup"><span data-stu-id="5a140-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="5a140-104">Обзор</span><span class="sxs-lookup"><span data-stu-id="5a140-104">Overview</span></span>
<span data-ttu-id="5a140-105">SDK тестовой базы можно использовать для взаимодействия с ресурсом тестовой базы Azure.</span><span class="sxs-lookup"><span data-stu-id="5a140-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="5a140-106">(например, управление пакетом приложений, включите создание пакета, изменение пакета и удаление пакета)</span><span class="sxs-lookup"><span data-stu-id="5a140-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="5a140-107">С помощью SDK можно получить сводку тестов и результаты анализа, которые можно получить: scriptExecution, надежность, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span><span class="sxs-lookup"><span data-stu-id="5a140-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="5a140-108">С помощью SDK тестовой базы можно интегрировать тестовую базу в конвейер ci/CD.</span><span class="sxs-lookup"><span data-stu-id="5a140-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="5a140-109">Клиентская библиотека</span><span class="sxs-lookup"><span data-stu-id="5a140-109">Client Library</span></span>

<span data-ttu-id="5a140-110">Установите тестовый базовый пакет с пунктом.</span><span class="sxs-lookup"><span data-stu-id="5a140-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="5a140-111">Пример</span><span class="sxs-lookup"><span data-stu-id="5a140-111">Example</span></span>
