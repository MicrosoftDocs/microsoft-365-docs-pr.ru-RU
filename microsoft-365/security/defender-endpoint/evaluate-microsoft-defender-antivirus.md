---
title: Оценка антивирусной программы в Microsoft Defender
description: Предприятия всех размеров могут использовать это руководство для оценки и тестирования защиты, предложенной антивирусом Microsoft Defender в Windows 10.
keywords: Антивирус Microsoft Defender, облачная защита, облачные, антивирусные программы, безопасность, защита, оценка, тестирование, защита, сравнение, защита в режиме реального времени
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 7f3fa1ca854a75025f850c85637cd3e08678bdbc
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764835"
---
# <a name="evaluate-microsoft-defender-antivirus"></a><span data-ttu-id="e21a8-104">Оценка антивирусной программы в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e21a8-104">Evaluate Microsoft Defender Antivirus</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e21a8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e21a8-105">**Applies to:**</span></span>

- [<span data-ttu-id="e21a8-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="e21a8-106">Microsoft Defender for Endpoint</span></span>](/microsoft-365/security/defender-endpoint/)

<span data-ttu-id="e21a8-107">Используйте это руководство, чтобы определить, насколько хорошо антивирус Microsoft Defender защищает вас от вирусов, вредоносных программ и потенциально нежелательных приложений.</span><span class="sxs-lookup"><span data-stu-id="e21a8-107">Use this guide to determine how well Microsoft Defender Antivirus protects you from viruses, malware, and potentially unwanted applications.</span></span>

>[!TIP]
><span data-ttu-id="e21a8-108">Вы также можете посетить веб-сайт демонстрации Microsoft Defender для конечной точки в [demo.wd.microsoft.com,](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) чтобы подтвердить работу следующих функций и посмотреть, как они работают:</span><span class="sxs-lookup"><span data-stu-id="e21a8-108">You can also visit the Microsoft Defender for Endpoint demo website at [demo.wd.microsoft.com](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) to confirm the following features are working and see how they work:</span></span>
>- <span data-ttu-id="e21a8-109">Защита с облачным доставкой</span><span class="sxs-lookup"><span data-stu-id="e21a8-109">Cloud-delivered protection</span></span>
>- <span data-ttu-id="e21a8-110">Быстрое обучение (включая блок с первого взгляда)</span><span class="sxs-lookup"><span data-stu-id="e21a8-110">Fast learning (including Block at first sight)</span></span>
>- <span data-ttu-id="e21a8-111">Блокировка потенциально нежелательных приложений</span><span class="sxs-lookup"><span data-stu-id="e21a8-111">Potentially unwanted application blocking</span></span>

<span data-ttu-id="e21a8-112">В нем рассказывается о важных средствах защиты нового поколения антивируса Microsoft Defender, доступных как для малых, так и для крупных предприятий, а также о том, как они увеличивают обнаружение и защиту вредоносных программ по всей сети.</span><span class="sxs-lookup"><span data-stu-id="e21a8-112">It explains the important next-generation protection features of Microsoft Defender Antivirus available for both small and large enterprises, and how they increase malware detection and protection across your network.</span></span>

<span data-ttu-id="e21a8-113">Вы можете настроить и оценить каждый параметр самостоятельно или все сразу.</span><span class="sxs-lookup"><span data-stu-id="e21a8-113">You can choose to configure and evaluate each setting independently, or all at once.</span></span> <span data-ttu-id="e21a8-114">Мы сгруппировали аналогичные параметры на основе типичных сценариев оценки и включили инструкции по использованию PowerShell для параметров.</span><span class="sxs-lookup"><span data-stu-id="e21a8-114">We have grouped similar settings based upon typical evaluation scenarios, and include instructions for using PowerShell to enable the settings.</span></span>

<span data-ttu-id="e21a8-115">Руководство доступно в формате PDF для автономного просмотра:</span><span class="sxs-lookup"><span data-stu-id="e21a8-115">The guide is available in PDF format for offline viewing:</span></span>

- [<span data-ttu-id="e21a8-116">Скачайте руководство в формате PDF</span><span class="sxs-lookup"><span data-stu-id="e21a8-116">Download the guide in PDF format</span></span>](https://www.microsoft.com/download/details.aspx?id=54795)

<span data-ttu-id="e21a8-117">Вы также можете скачать PowerShell, который автоматически включает все параметры, описанные в руководстве.</span><span class="sxs-lookup"><span data-stu-id="e21a8-117">You can also download a PowerShell that will enable all the settings described in the guide automatically.</span></span> <span data-ttu-id="e21a8-118">Сценарий можно получить вместе с загрузкой PDF выше или отдельно из PowerShell Gallery:</span><span class="sxs-lookup"><span data-stu-id="e21a8-118">You can obtain the script alongside the PDF download above, or individually from PowerShell Gallery:</span></span>

- [<span data-ttu-id="e21a8-119">Скачайте скрипт PowerShell, чтобы автоматически настроить параметры</span><span class="sxs-lookup"><span data-stu-id="e21a8-119">Download the PowerShell script to automatically configure the settings</span></span>](https://www.powershellgallery.com/packages/WindowsDefender_InternalEvaluationSettings)

> [!IMPORTANT]
> <span data-ttu-id="e21a8-120">Руководство в настоящее время предназначено для одноамперной оценки антивируса Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="e21a8-120">The guide is currently intended for single-machine evaluation of Microsoft Defender Antivirus.</span></span> <span data-ttu-id="e21a8-121">Включение всех параметров в этом руководстве может оказаться неподходящим для развертывания в реальном мире.</span><span class="sxs-lookup"><span data-stu-id="e21a8-121">Enabling all of the settings in this guide may not be suitable for real-world deployment.</span></span>
>
> <span data-ttu-id="e21a8-122">Последние рекомендации по развертыванию и мониторингу антивируса Microsoft Defender в сети см. в выпуске [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span><span class="sxs-lookup"><span data-stu-id="e21a8-122">For the latest recommendations for real-world deployment and monitoring of Microsoft Defender Antivirus across a network, see [Deploy Microsoft Defender Antivirus](deploy-manage-report-microsoft-defender-antivirus.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="e21a8-123">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="e21a8-123">Related topics</span></span>

- [<span data-ttu-id="e21a8-124">Антивирус Microsoft Defender в Windows 10</span><span class="sxs-lookup"><span data-stu-id="e21a8-124">Microsoft Defender Antivirus in Windows 10</span></span>](microsoft-defender-antivirus-in-windows-10.md)
- [<span data-ttu-id="e21a8-125">Развертывание антивируса Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="e21a8-125">Deploy Microsoft Defender Antivirus</span></span>](deploy-manage-report-microsoft-defender-antivirus.md)