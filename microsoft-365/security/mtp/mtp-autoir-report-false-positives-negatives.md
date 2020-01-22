---
title: Как сообщить о ложном срабатывании или ложных негативах в AIR в Microsoft Threat protection
description: Было ли что-то пошло не так, как было обнаружено ВОЗДУХом в защите от угроз Майкрософт? Сведения о том, как передавать ложные срабатывания или ложные отрицательные результаты в корпорацию Майкрософт для анализа.
keywords: автоматические, исследование, оповещение, триггер, действие, исправление, ложное срабатывание, ложные отрицательные значения
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: d62f10cdf9805cdcfae7ba5bd5381ca589d1297c
ms.sourcegitcommit: 3dca80f268006658a0b721aa4f6df1224c7964dc
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2020
ms.locfileid: "41260197"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="f273c-105">Составление отчетов о ложных положительных и отрицательных значениях при автоматическом расследовании и возможностях реагирования</span><span class="sxs-lookup"><span data-stu-id="f273c-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="f273c-106">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f273c-106">**Applies to:**</span></span>
- <span data-ttu-id="f273c-107">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="f273c-107">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f273c-108">Выполнялось ли [автоматизированное исследование и возможности реагирования](mtp-autoir.md) в целях защиты от угроз Майкрософт или неправильно обнаруживают что-либо?</span><span class="sxs-lookup"><span data-stu-id="f273c-108">Did [automated investigation and response capabilities](mtp-autoir.md) in Microsoft Threat Protection miss or wrongly detect something?</span></span> <span data-ttu-id="f273c-109">Вы можете сообщить об этом в корпорацию Майкрософт или настроить оповещения (при необходимости).</span><span class="sxs-lookup"><span data-stu-id="f273c-109">You can report it to Microsoft or adjust your alerts (if needed).</span></span> <span data-ttu-id="f273c-110">В качестве руководства используйте следующую таблицу:</span><span class="sxs-lookup"><span data-stu-id="f273c-110">Use the following table as a guide:</span></span> 


|<span data-ttu-id="f273c-111">Item</span><span class="sxs-lookup"><span data-stu-id="f273c-111">Item</span></span>  |<span data-ttu-id="f273c-112">Определяется</span><span class="sxs-lookup"><span data-stu-id="f273c-112">Detected by</span></span>  |<span data-ttu-id="f273c-113">Как сообщить об этом</span><span class="sxs-lookup"><span data-stu-id="f273c-113">How to report it</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="f273c-114">Сообщение электронной почты</span><span class="sxs-lookup"><span data-stu-id="f273c-114">Email message</span></span> <br/><span data-ttu-id="f273c-115">Вложение электронной почты</span><span class="sxs-lookup"><span data-stu-id="f273c-115">Email attachment</span></span> <br/><span data-ttu-id="f273c-116">URL-адрес в сообщении электронной почты или файле Office</span><span class="sxs-lookup"><span data-stu-id="f273c-116">URL in an email message or Office file</span></span>      |[<span data-ttu-id="f273c-117">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="f273c-117">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)        |[<span data-ttu-id="f273c-118">Отправляются сообщения об обнаружении нежелательной почты, фишинга, URL-адреса и файлов в Майкрософт для сканирования Office 365</span><span class="sxs-lookup"><span data-stu-id="f273c-118">Submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)         |
|<span data-ttu-id="f273c-119">Файл или приложение на устройстве</span><span class="sxs-lookup"><span data-stu-id="f273c-119">File or app on a device</span></span>    |[<span data-ttu-id="f273c-120">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="f273c-120">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection)         |[<span data-ttu-id="f273c-121">Передача файла в корпорацию Майкрософт для анализа вредоносных программ</span><span class="sxs-lookup"><span data-stu-id="f273c-121">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |
|<span data-ttu-id="f273c-122">Оповещение, инициированное законным использованием</span><span class="sxs-lookup"><span data-stu-id="f273c-122">Alert triggered by legitimate use</span></span> <br/><span data-ttu-id="f273c-123">Неточное оповещение</span><span class="sxs-lookup"><span data-stu-id="f273c-123">Inaccurate alert</span></span>    |[<span data-ttu-id="f273c-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f273c-124">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security)<br/> <span data-ttu-id="f273c-125">или</span><span class="sxs-lookup"><span data-stu-id="f273c-125">or</span></span> <br/>[<span data-ttu-id="f273c-126">Расширенная угроза обнаружения угроз Azure</span><span class="sxs-lookup"><span data-stu-id="f273c-126">Azure Advanced Threat Detection</span></span>](https://docs.microsoft.com/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="f273c-127">Управление оповещениями на портале Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f273c-127">Manage alerts in the Cloud App Security portal</span></span>](https://docs.microsoft.com/cloud-app-security/managing-alerts)         |


## <a name="next-steps"></a><span data-ttu-id="f273c-128">Дальнейшие действия:</span><span class="sxs-lookup"><span data-stu-id="f273c-128">Next steps</span></span>

- [<span data-ttu-id="f273c-129">Утверждение или отклонение действий, относящихся к автоматизированному анализу угроз и реакции на угрозы</span><span class="sxs-lookup"><span data-stu-id="f273c-129">Approve or reject actions related to automated investigation and response</span></span>](mtp-autoir-actions.md)
- [<span data-ttu-id="f273c-130">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="f273c-130">Learn more about the Action center</span></span>](mtp-action-center.md)
- [<span data-ttu-id="f273c-131">Защита от угроз (Майкрософт) позволяет осуществлять их расширенное выслеживание на профилактической основе</span><span class="sxs-lookup"><span data-stu-id="f273c-131">Proactively hunt for threats with advanced hunting in Microsoft Threat Protection</span></span>](advanced-hunting-overview.md)
