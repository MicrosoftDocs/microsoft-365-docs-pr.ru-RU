---
title: Оценка антивирусной программы в Microsoft Defender
description: Предприятия всех размеров могут использовать это руководство для оценки и тестирования защиты, антивирусная программа в Microsoft Defender в Windows 10.
keywords: антивирусная программа в Microsoft Defender, облачная защита, облако, антивирусное программное обеспечение, безопасность, защита, оценка, тестирование, защита, сравнение, защита в режиме реального времени
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 4f789ab80d48966d4cf922811d05d74882d728fe
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/07/2021
ms.locfileid: "52274740"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="b5fed-104">Оценка антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5fed-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="b5fed-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="b5fed-105">**Applies to:**</span></span>

- [<span data-ttu-id="b5fed-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="b5fed-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="b5fed-107">Используйте это руководство, чтобы определить, насколько антивирусная программа в Microsoft Defender защищает вас от вирусов, вредоносных программ и потенциально нежелательных приложений.</span><span class="sxs-lookup"><span data-stu-id="b5fed-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="b5fed-108">Вы также можете посетить веб-сайт демонстрации Microsoft Defender для конечной точки в [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить работу следующих функций и посмотреть, как они работают:</span><span class="sxs-lookup"><span data-stu-id="b5fed-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="b5fed-109">Облачная защита</span><span class="sxs-lookup"><span data-stu-id="b5fed-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="b5fed-110">Быстрое обучение (включая блок с первого взгляда)</span><span class="sxs-lookup"><span data-stu-id="b5fed-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="b5fed-111">Блокировка потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="b5fed-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="b5fed-112">В нем рассказывается о важных средствах защиты нового поколения антивирусная программа в Microsoft Defender для малых и крупных предприятий, а также о том, как они увеличивают обнаружение и защиту вредоносных программ в сети.</span><span class="sxs-lookup"><span data-stu-id="b5fed-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="b5fed-113">Вы можете настроить и оценить каждый параметр самостоятельно или все сразу.</span><span class="sxs-lookup"><span data-stu-id="b5fed-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="b5fed-114">Мы сгруппировали аналогичные параметры на основе типичных сценариев оценки и включили инструкции по использованию PowerShell для параметров.</span><span class="sxs-lookup"><span data-stu-id="b5fed-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="b5fed-115">Руководство доступно в формате PDF для автономного просмотра:</span><span class="sxs-lookup"><span data-stu-id="b5fed-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="b5fed-116">Скачайте руководство в формате PDF</span><span class="sxs-lookup"><span data-stu-id="b5fed-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="b5fed-117">Вы также можете скачать PowerShell, который автоматически включает все параметры, описанные в руководстве.</span><span class="sxs-lookup"><span data-stu-id="b5fed-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="b5fed-118">Сценарий можно получить вместе с загрузкой PDF выше или отдельно из PowerShell Gallery:</span><span class="sxs-lookup"><span data-stu-id="b5fed-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="b5fed-119">Скачайте скрипт PowerShell, чтобы автоматически настроить параметры</span><span class="sxs-lookup"><span data-stu-id="b5fed-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="b5fed-120">Руководство в настоящее время предназначено для одноаммийной оценки антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="b5fed-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="b5fed-121">Включение всех параметров в этом руководстве может оказаться неподходящим для развертывания в реальном мире.</span><span class="sxs-lookup"><span data-stu-id="b5fed-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="b5fed-122">Последние рекомендации по развертыванию и мониторингу антивирусная программа в Microsoft Defender в сети см. в [антивирусная программа в Microsoft Defender.](deploy-manage-report-microsoft-defender-antivirus.md)</span><span class="sxs-lookup"><span data-stu-id="b5fed-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="b5fed-123">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="b5fed-123">Related topics</span></span>

- [<span data-ttu-id="b5fed-124">Антивирусная программа в Microsoft Defender (Windows 10)</span><span class="sxs-lookup"><span data-stu-id="b5fed-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="b5fed-125">Развертывание антивирусная программа в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="b5fed-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)