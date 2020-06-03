---
title: Обзор пользовательских обнаружений в защите от угроз Майкрософт
description: Сведения об использовании расширенного поиска для создания пользовательских обнаружений и создания оповещений
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, Microsoft 365, защита от угроз Майкрософт
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: cdbaf9cfd2172656ed75cb3c0a1a9e361070f25b
ms.sourcegitcommit: 7bb3d8a93a85246172e2499d6c58c390e46f5bb9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/02/2020
ms.locfileid: "44498355"
---
# <a name="custom-detections-overview"></a><span data-ttu-id="8323b-104">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="8323b-104">Custom detections overview</span></span>

<span data-ttu-id="8323b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8323b-105">**Applies to:**</span></span>
- <span data-ttu-id="8323b-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8323b-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8323b-107">С помощью пользовательских обнаружений можно отслеживать различные события и состояния системы и отвечать на них, в том числе подозреваемые и неправильно настроенные конечные точки.</span><span class="sxs-lookup"><span data-stu-id="8323b-107">With custom detections, you can proactively monitor for and respond to various events and system states, including suspected breach activity and misconfigured endpoints.</span></span> <span data-ttu-id="8323b-108">Это можно сделать с помощью настраиваемых правил обнаружения, которые автоматически запускают оповещения и действия ответа.</span><span class="sxs-lookup"><span data-stu-id="8323b-108">This is made possible by customizable detection rules that automatically trigger alerts as well as response actions.</span></span>

<span data-ttu-id="8323b-109">Пользовательские проверки работают с [расширенным](advanced-hunting-overview.md)поиском, который предоставляет мощный, гибкий язык запросов, охватывающий широкий набор событий и системных сведений в сети.</span><span class="sxs-lookup"><span data-stu-id="8323b-109">Custom detections work with [advanced hunting](advanced-hunting-overview.md), which provides a powerful, flexible query language that covers a broad set of event and system information from your network.</span></span> <span data-ttu-id="8323b-110">Вы можете настроить их для запуска через определенные интервалы, создавая оповещения и отменяя действия ответа при обнаружении совпадений.</span><span class="sxs-lookup"><span data-stu-id="8323b-110">You can set them to run at regular intervals, generating alerts and taking response actions whenever there are matches.</span></span>

<span data-ttu-id="8323b-111">Пользовательские обнаружения предоставляют:</span><span class="sxs-lookup"><span data-stu-id="8323b-111">Custom detections provide:</span></span>
- <span data-ttu-id="8323b-112">Оповещения об определениях, основанных на правилах, основанных на расширенных запросах поиска</span><span class="sxs-lookup"><span data-stu-id="8323b-112">Alerts for rule-based detections built from advanced hunting queries</span></span>
- <span data-ttu-id="8323b-113">Действия при автоматическом отклике</span><span class="sxs-lookup"><span data-stu-id="8323b-113">Automatic response actions</span></span>

## <a name="related-topic"></a><span data-ttu-id="8323b-114">Связанная тема</span><span class="sxs-lookup"><span data-stu-id="8323b-114">Related topic</span></span>
- [<span data-ttu-id="8323b-115">Создание настраиваемых правил обнаружения и управление ими</span><span class="sxs-lookup"><span data-stu-id="8323b-115">Create and manage custom detection rules</span></span>](custom-detection-rules.md)
- [<span data-ttu-id="8323b-116">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="8323b-116">Advanced hunting overview</span></span>](advanced-hunting-overview.md)