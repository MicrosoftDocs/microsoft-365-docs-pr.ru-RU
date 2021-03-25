---
title: Настройка уменьшения поверхности атаки
description: Чтобы настроить сокращение поверхности атаки, используйте Microsoft Intune, Microsoft Endpoint Configuration Manager, команды PowerShell и групповую политику.
keywords: asr, уменьшение поверхности атаки, защитник Windows, защитник Microsoft, антивирус, av
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 6129fb889e2bd42f177c4e3be30f676854119f91
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51166171"
---
# <a name="configure-attack-surface-reduction"></a><span data-ttu-id="5cd8b-104">Настройка уменьшения поверхности атаки</span><span class="sxs-lookup"><span data-stu-id="5cd8b-104">Configure attack surface reduction</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="5cd8b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="5cd8b-105">**Applies to:**</span></span>
- [<span data-ttu-id="5cd8b-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="5cd8b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="5cd8b-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="5cd8b-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="5cd8b-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="5cd8b-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="5cd8b-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="5cd8b-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="5cd8b-110">Вы можете настроить уменьшение поверхности атаки с помощью множества средств, включая:</span><span class="sxs-lookup"><span data-stu-id="5cd8b-110">You can configure attack surface reduction with many tools, including:</span></span>

* <span data-ttu-id="5cd8b-111">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="5cd8b-111">Microsoft Intune</span></span>
* <span data-ttu-id="5cd8b-112">Microsoft Endpoint Configuration Manager</span><span class="sxs-lookup"><span data-stu-id="5cd8b-112">Microsoft Endpoint Configuration Manager</span></span>
* <span data-ttu-id="5cd8b-113">Групповая политика</span><span class="sxs-lookup"><span data-stu-id="5cd8b-113">Group Policy</span></span>
* <span data-ttu-id="5cd8b-114">Командлеты PowerShell</span><span class="sxs-lookup"><span data-stu-id="5cd8b-114">PowerShell cmdlets</span></span>

<span data-ttu-id="5cd8b-115">Статья</span><span class="sxs-lookup"><span data-stu-id="5cd8b-115">Article</span></span> | <span data-ttu-id="5cd8b-116">Описание</span><span class="sxs-lookup"><span data-stu-id="5cd8b-116">Description</span></span>
-|-
[<span data-ttu-id="5cd8b-117">Включить аппаратную изоляцию для Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="5cd8b-117">Enable hardware-based isolation for Microsoft Edge</span></span>](/windows/security/threat-protection/microsoft-defender-application-guard/install-md-app-guard) | <span data-ttu-id="5cd8b-118">Подготовка и установка Application Guard, включая требования к оборудованию и программному обеспечению</span><span class="sxs-lookup"><span data-stu-id="5cd8b-118">How to prepare for and install Application Guard, including hardware and software requirements</span></span>
[<span data-ttu-id="5cd8b-119">Включить управление приложениями</span><span class="sxs-lookup"><span data-stu-id="5cd8b-119">Enable application control</span></span>](/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)|<span data-ttu-id="5cd8b-120">Управление приложениями, запускаемой пользователями, и защита процессов режима ядра</span><span class="sxs-lookup"><span data-stu-id="5cd8b-120">How to control applications run by users and protect kernel mode processes</span></span>
[<span data-ttu-id="5cd8b-121">Защита от эксплойтов</span><span class="sxs-lookup"><span data-stu-id="5cd8b-121">Exploit protection</span></span>](./enable-exploit-protection.md)|<span data-ttu-id="5cd8b-122">Автоматическое применение методов смягчения эксплойтов как в операционных системах, так и в отдельных приложениях</span><span class="sxs-lookup"><span data-stu-id="5cd8b-122">How to automatically apply exploit mitigation techniques on both operating system processes and on individual apps</span></span>
[<span data-ttu-id="5cd8b-123">Защита сети</span><span class="sxs-lookup"><span data-stu-id="5cd8b-123">Network protection</span></span>](./enable-network-protection.md)|<span data-ttu-id="5cd8b-124">Как запретить пользователям использовать приложения для доступа к опасным доменам</span><span class="sxs-lookup"><span data-stu-id="5cd8b-124">How to prevent users from using any apps to access dangerous domains</span></span>
[<span data-ttu-id="5cd8b-125">Управляемый доступ к папкам</span><span class="sxs-lookup"><span data-stu-id="5cd8b-125">Controlled folder access</span></span>](./enable-controlled-folders.md)|<span data-ttu-id="5cd8b-126">Защита ценных данных от вредоносных приложений</span><span class="sxs-lookup"><span data-stu-id="5cd8b-126">How to protect valuable data from malicious apps</span></span>
[<span data-ttu-id="5cd8b-127">Сокращение направлений атак</span><span class="sxs-lookup"><span data-stu-id="5cd8b-127">Attack surface reduction</span></span>](./enable-attack-surface-reduction.md)|<span data-ttu-id="5cd8b-128">Предотвращение действий и приложений, которые обычно используются при поиске вредоносных программ для эксплойтов</span><span class="sxs-lookup"><span data-stu-id="5cd8b-128">How to prevent actions and apps that are typically used by exploit-seeking malware</span></span>
[<span data-ttu-id="5cd8b-129">Брандмауэр сети</span><span class="sxs-lookup"><span data-stu-id="5cd8b-129">Network firewall</span></span>](/windows/security/threat-protection/windows-firewall/windows-firewall-with-advanced-security-deployment-guide)|<span data-ttu-id="5cd8b-130">Защита устройств и данных в сети</span><span class="sxs-lookup"><span data-stu-id="5cd8b-130">How to protect devices and data across a network</span></span>

