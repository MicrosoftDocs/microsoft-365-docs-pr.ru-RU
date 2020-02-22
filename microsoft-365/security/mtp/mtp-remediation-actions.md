---
title: Действия по исправлению в автоматическом расследовании и возможностях реагирования в защите от угроз Майкрософт
description: Ознакомьтесь с возможностями автоматизированного анализа угроз и реакции на угрозы в службе защиты от угроз (Майкрософт)
keywords: автоматизированный, анализ, оповещение, триггер, действие, исправление
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 65ace4bda091b3e000d25a984b706f26fe9c8696
ms.sourcegitcommit: 48b69caf6550e68cb14472ea8cfc76b53e7ae9c6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/21/2020
ms.locfileid: "42225487"
---
# <a name="remediation-actions-in-automated-investigation-and-response-capabilities-in-microsoft-threat-protection"></a><span data-ttu-id="8836c-104">Действия по исправлению в автоматическом расследовании и возможностях реагирования в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="8836c-104">Remediation actions in automated investigation and response capabilities in Microsoft Threat Protection</span></span>

<span data-ttu-id="8836c-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8836c-105">**Applies to:**</span></span>
- <span data-ttu-id="8836c-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="8836c-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="8836c-107">Автоматизированные функции расследования и реагирования в защите от угроз Майкрософт включают некоторые действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="8836c-107">Automated investigation and response capabilities in Microsoft Threat Protection include certain remediation actions.</span></span> <span data-ttu-id="8836c-108">Некоторые виды действий по исправлению выполняются на устройствах, которые также называются конечными точками.</span><span class="sxs-lookup"><span data-stu-id="8836c-108">Some kinds of remediation actions are taken on devices, also referred to as endpoints.</span></span> <span data-ttu-id="8836c-109">Для содержимого электронной почты применяются другие действия по исправлению.</span><span class="sxs-lookup"><span data-stu-id="8836c-109">Other remediation actions are taken on email content.</span></span>

<span data-ttu-id="8836c-110">В следующей таблице приведены действия по исправлению, которые в настоящее время поддерживаются в Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="8836c-110">The following table summarizes remediation actions that are currently supported in Microsoft Threat Protection:</span></span> 

|<span data-ttu-id="8836c-111">Действия по исправлению для конечных точек</span><span class="sxs-lookup"><span data-stu-id="8836c-111">Endpoints remediation actions</span></span>  |<span data-ttu-id="8836c-112">Действия по исправления для электронной почты</span><span class="sxs-lookup"><span data-stu-id="8836c-112">Email remediation actions</span></span>  |
|---------|---------|
|<span data-ttu-id="8836c-113">Файл карантина</span><span class="sxs-lookup"><span data-stu-id="8836c-113">Quarantine file</span></span><br/><span data-ttu-id="8836c-114">Удаление раздела реестра</span><span class="sxs-lookup"><span data-stu-id="8836c-114">Remove registry key</span></span><br/><span data-ttu-id="8836c-115">Прекращение процесса</span><span class="sxs-lookup"><span data-stu-id="8836c-115">Kill process</span></span> <br/><span data-ttu-id="8836c-116">Остановка службы</span><span class="sxs-lookup"><span data-stu-id="8836c-116">Stop service</span></span> <br/><span data-ttu-id="8836c-117">Отключение драйвера</span><span class="sxs-lookup"><span data-stu-id="8836c-117">Disable driver</span></span> <br/><span data-ttu-id="8836c-118">Удаление запланированной задачи</span><span class="sxs-lookup"><span data-stu-id="8836c-118">Remove scheduled task</span></span>      |<span data-ttu-id="8836c-119">Обратимое удаление сообщений электронной почты или кластеров</span><span class="sxs-lookup"><span data-stu-id="8836c-119">Soft delete email messages or clusters</span></span><br/><span data-ttu-id="8836c-120">Блокирование URL-адреса (во время щелчка)</span><span class="sxs-lookup"><span data-stu-id="8836c-120">Block URL (time-of-click)</span></span><br/><span data-ttu-id="8836c-121">Отключение внешней переадресации почты</span><span class="sxs-lookup"><span data-stu-id="8836c-121">Turn off external mail forwarding</span></span>          |

<span data-ttu-id="8836c-122">Действия по исправлению, которые ожидают утверждения или уже завершены, можно просмотреть в [центре уведомлений](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span><span class="sxs-lookup"><span data-stu-id="8836c-122">Remediation actions, whether they're pending approval or are already complete, can be viewed in the [Action Center](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center).</span></span>

## <a name="next-steps"></a><span data-ttu-id="8836c-123">Дальнейшие действия:</span><span class="sxs-lookup"><span data-stu-id="8836c-123">Next steps</span></span>

- [<span data-ttu-id="8836c-124">Утверждение или отклонение действий, относящихся к автоматизированному анализу угроз и реакции на угрозы</span><span class="sxs-lookup"><span data-stu-id="8836c-124">Approve or reject actions related to automated investigation and response</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-autoir-actions)
- [<span data-ttu-id="8836c-125">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="8836c-125">Learn more about the Action center</span></span>](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-action-center)
