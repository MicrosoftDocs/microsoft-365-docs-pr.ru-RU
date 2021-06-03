---
title: Сведения о расширении соответствия требованиям Майкрософт
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Расширение соответствия требованиям Майкрософт дополняет мониторинг и контроль операций с файлами и защитных действий в браузере Google Chrome
ms.openlocfilehash: b8d9be88f42cce736cdbf66a97f4363106fa5820
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730490"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a><span data-ttu-id="6c957-103">Сведения о расширении соответствия требованиям Майкрософт</span><span class="sxs-lookup"><span data-stu-id="6c957-103">Learn about the Microsoft Compliance Extension</span></span>

<span data-ttu-id="6c957-104">[Защита от потери данных в конечной точке (DLP в конечной точке)](endpoint-dlp-learn-about.md) расширяет возможности отслеживания действий и безопасности функции [защиты от потери данных Microsoft 365](dlp-learn-about-dlp.md) для конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6c957-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="6c957-105">После того как устройства будут подключены к решениям по обеспечению соответствия требованиям Microsoft 365, сведения о действиях пользователей с конфиденциальными элементами становятся видимыми в [обозревателе действий](data-classification-activity-explorer.md) и вы можете принудительно применять защитные действия к ним с помощью [политик защиты от потери данных](create-test-tune-dlp-policy.md).</span><span class="sxs-lookup"><span data-stu-id="6c957-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="6c957-106">После установки расширения соответствия требованиям Майкрософт на устройстве с Windows 10 организации могут отслеживать попытки пользователей получить доступ к конфиденциальному элементу или отправить его в облачную службу с помощью Google Chrome, а также применять защитные действия с помощью DLP.</span><span class="sxs-lookup"><span data-stu-id="6c957-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="6c957-107">Действия, доступные для отслеживания и реагирования</span><span class="sxs-lookup"><span data-stu-id="6c957-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="6c957-108">Расширение соответствия требованиям Майкрософт позволяет проверять и контролировать следующие типы действий, выполняемые пользователями в отношении конфиденциальных элементов на устройствах с Windows 10.</span><span class="sxs-lookup"><span data-stu-id="6c957-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="6c957-109">действие</span><span class="sxs-lookup"><span data-stu-id="6c957-109">activity</span></span> |<span data-ttu-id="6c957-110">описание</span><span class="sxs-lookup"><span data-stu-id="6c957-110">description</span></span>  | <span data-ttu-id="6c957-111">поддерживаемые действия политики</span><span class="sxs-lookup"><span data-stu-id="6c957-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="6c957-112">файл скопирован в облако</span><span class="sxs-lookup"><span data-stu-id="6c957-112">file copied to cloud</span></span>  | <span data-ttu-id="6c957-113">Обнаруживает, когда пользователь пытается отправить конфиденциальный элемент в запрещенный домен службы с помощью браузера Chrome</span><span class="sxs-lookup"><span data-stu-id="6c957-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="6c957-114">аудит, блокировка</span><span class="sxs-lookup"><span data-stu-id="6c957-114">audit, block</span></span>|
|<span data-ttu-id="6c957-115">файл распечатан</span><span class="sxs-lookup"><span data-stu-id="6c957-115">file printed</span></span>  |<span data-ttu-id="6c957-116">Определяет, когда пользователь пытается напечатать на локальном или сетевом принтере конфиденциальный элемент, открытый в браузере Chrome</span><span class="sxs-lookup"><span data-stu-id="6c957-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="6c957-117">аудит, блокировка с возможностью переопределения, блокировка</span><span class="sxs-lookup"><span data-stu-id="6c957-117">audit, block with override, block</span></span>|
|<span data-ttu-id="6c957-118">файл скопирован в буфер обмена</span><span class="sxs-lookup"><span data-stu-id="6c957-118">file copied to clipboard</span></span> |<span data-ttu-id="6c957-119">Обнаруживает, когда пользователь пытается скопировать сведения из конфиденциального элемента, просматриваемого в браузере Chrome, а затем вставить их в другое приложение, процесс или элемент.</span><span class="sxs-lookup"><span data-stu-id="6c957-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="6c957-120">аудит, блокировка с возможностью переопределения, блокировка</span><span class="sxs-lookup"><span data-stu-id="6c957-120">audit, block with override, block</span></span>|
|<span data-ttu-id="6c957-121">файл скопирован на съемный носитель</span><span class="sxs-lookup"><span data-stu-id="6c957-121">file copied to removable storage</span></span>    | <span data-ttu-id="6c957-122">Определяет, когда пользователь пытается скопировать конфиденциальный элемент или информацию из конфиденциального элемента, открытого в браузере Chrome, на съемный носитель или USB-устройство</span><span class="sxs-lookup"><span data-stu-id="6c957-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="6c957-123">аудит, блокировка с возможностью переопределения, блокировка</span><span class="sxs-lookup"><span data-stu-id="6c957-123">audit, block with override, block</span></span>|
|<span data-ttu-id="6c957-124">файл скопирован в сетевую папку</span><span class="sxs-lookup"><span data-stu-id="6c957-124">file copied to network share</span></span>  |<span data-ttu-id="6c957-125">Определяет, когда пользователь пытается скопировать конфиденциальный элемент или информацию из конфиденциального элемента, открытого в браузере Chrome, в сетевую папку или сопоставленный сетевой диск.</span><span class="sxs-lookup"><span data-stu-id="6c957-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="6c957-126">аудит, блокировка с возможностью переопределения, блокировка</span><span class="sxs-lookup"><span data-stu-id="6c957-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="6c957-127">Процесс развертывания</span><span class="sxs-lookup"><span data-stu-id="6c957-127">Deployment process</span></span>
1. [<span data-ttu-id="6c957-128">Начало работы с функцией защиты от потери данных в конечной точке</span><span class="sxs-lookup"><span data-stu-id="6c957-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="6c957-129">Средства и методы подключения для устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="6c957-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="6c957-130">Установка расширения на устройствах с Windows 10</span><span class="sxs-lookup"><span data-stu-id="6c957-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="6c957-131">[Создание или изменение политик защиты от потери данных](create-test-tune-dlp-policy.md), ограничивающих отправку в облачную службу или доступ с помощью действий запрещенных браузеров, и их применение к устройствам с Windows 10</span><span class="sxs-lookup"><span data-stu-id="6c957-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="6c957-132">Дальнейшие действия</span><span class="sxs-lookup"><span data-stu-id="6c957-132">Next steps</span></span>

<span data-ttu-id="6c957-133">Полные процедуры и сценарии развертывания см. в статье [Начало работы с расширением соответствия требованиям Майкрософт](dlp-chrome-get-started.md).</span><span class="sxs-lookup"><span data-stu-id="6c957-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="6c957-134">См. также</span><span class="sxs-lookup"><span data-stu-id="6c957-134">See also</span></span>

- [<span data-ttu-id="6c957-135">Начало работы с расширением соответствия требованиям Майкрософт</span><span class="sxs-lookup"><span data-stu-id="6c957-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="6c957-136">Сведения о защите от потери данных в конечной точке Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="6c957-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="6c957-137">Начало работы с защитой от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="6c957-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="6c957-138">Использование защиты от потери данных в конечной точке Майкрософт</span><span class="sxs-lookup"><span data-stu-id="6c957-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="6c957-139">Сведения о защите от потери данных</span><span class="sxs-lookup"><span data-stu-id="6c957-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="6c957-140">Создание, тестирование и настройка политики защиты от потери данных</span><span class="sxs-lookup"><span data-stu-id="6c957-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="6c957-141">Начало работы с обозревателем действий</span><span class="sxs-lookup"><span data-stu-id="6c957-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="6c957-142">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="6c957-142">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="6c957-143">Управление рисками в рамках программы предварительной оценки</span><span class="sxs-lookup"><span data-stu-id="6c957-143">Insider Risk management</span></span>](insider-risk-management.md)
