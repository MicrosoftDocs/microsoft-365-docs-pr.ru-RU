---
title: Расширение расширенного охвата охоты с помощью правильных параметров
description: Проверьте параметры аудита на устройствах Windows и другие параметры, чтобы убедиться в том, что вы получаете самые исчерпывающие данные в ходе предварительной охоты
keywords: advanced hunting, incident, pivot, entity, audit settings, user account management, security group management, threat hunting, cyber threat hunting, search, query, telemetry, mdatp, Microsoft Defender ATP, Microsoft Defender for Endpoint, Защитник Windows, Защитник Windows ATP, Защитник Windows Advanced Threat Protection
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.date: 10/10/2020
ms.technology: mde
ms.openlocfilehash: 60e8710415e328d06fac4c02e428094e5e4bcc92
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51075501"
---
# <a name="extend-advanced-hunting-coverage-with-the-right-settings"></a><span data-ttu-id="ea9ed-104">Расширение расширенного охвата охоты с помощью правильных параметров</span><span class="sxs-lookup"><span data-stu-id="ea9ed-104">Extend advanced hunting coverage with the right settings</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="ea9ed-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="ea9ed-105">**Applies to:**</span></span>
- [<span data-ttu-id="ea9ed-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="ea9ed-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)

<span data-ttu-id="ea9ed-107">[Расширенный поиск](advanced-hunting-overview.md) зависит от данных, исходя из всей организации.</span><span class="sxs-lookup"><span data-stu-id="ea9ed-107">[Advanced hunting](advanced-hunting-overview.md) relies on data coming from across your organization.</span></span> <span data-ttu-id="ea9ed-108">Чтобы получить наиболее исчерпывающие данные, убедитесь, что у вас есть правильные параметры в соответствующих источниках данных.</span><span class="sxs-lookup"><span data-stu-id="ea9ed-108">To get the most comprehensive data possible, ensure that you have the correct settings in the corresponding data sources.</span></span>

## <a name="advanced-security-auditing-on-windows-devices"></a><span data-ttu-id="ea9ed-109">Расширенный аудит безопасности на устройствах Windows</span><span class="sxs-lookup"><span data-stu-id="ea9ed-109">Advanced security auditing on Windows devices</span></span>

<span data-ttu-id="ea9ed-110">Включите эти расширенные параметры аудита, чтобы получить данные о действиях на устройствах, включая локальное управление учетной записью, локальное управление группой безопасности и создание службы.</span><span class="sxs-lookup"><span data-stu-id="ea9ed-110">Turn on these advanced auditing settings to ensure you get data about activities on your devices, including local account management, local security group management, and service creation.</span></span>

<span data-ttu-id="ea9ed-111">Data</span><span class="sxs-lookup"><span data-stu-id="ea9ed-111">Data</span></span> | <span data-ttu-id="ea9ed-112">Описание</span><span class="sxs-lookup"><span data-stu-id="ea9ed-112">Description</span></span> | <span data-ttu-id="ea9ed-113">Таблица схемы</span><span class="sxs-lookup"><span data-stu-id="ea9ed-113">Schema table</span></span> | <span data-ttu-id="ea9ed-114">Способ настройки</span><span class="sxs-lookup"><span data-stu-id="ea9ed-114">How to configure</span></span>
-|-|-|-
<span data-ttu-id="ea9ed-115">Управление учетными записями</span><span class="sxs-lookup"><span data-stu-id="ea9ed-115">Account management</span></span> | <span data-ttu-id="ea9ed-116">События, запечатленные в качестве различных значений, указывающих на локальное создание учетной записи, удаление и другие действия, связанные `ActionType` с учетной записью</span><span class="sxs-lookup"><span data-stu-id="ea9ed-116">Events captured as various `ActionType` values indicating local account creation, deletion, and other account-related activities</span></span> | [<span data-ttu-id="ea9ed-117">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="ea9ed-117">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="ea9ed-118">- Развертывание усовершенствованой политики аудита безопасности: [управление учетной записью пользователей аудита](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span><span class="sxs-lookup"><span data-stu-id="ea9ed-118">- Deploy an advanced security audit policy: [Audit User Account Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-user-account-management)</span></span><br> <span data-ttu-id="ea9ed-119">- [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="ea9ed-119">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="ea9ed-120">Управление группой безопасности</span><span class="sxs-lookup"><span data-stu-id="ea9ed-120">Security group management</span></span> | <span data-ttu-id="ea9ed-121">События, запечатленные в качестве различных значений, указывающих на создание локальной группы безопасности и другие локальные действия `ActionType` по управлению группой</span><span class="sxs-lookup"><span data-stu-id="ea9ed-121">Events captured as various `ActionType` values indicating local security group creation and other local group management activities</span></span> | [<span data-ttu-id="ea9ed-122">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="ea9ed-122">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="ea9ed-123">- Развертывание усовершенствованой политики аудита безопасности: [управление группой аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span><span class="sxs-lookup"><span data-stu-id="ea9ed-123">- Deploy an advanced security audit policy: [Audit Security Group Management](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-group-management)</span></span><br> <span data-ttu-id="ea9ed-124">- [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="ea9ed-124">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>
<span data-ttu-id="ea9ed-125">Установка службы</span><span class="sxs-lookup"><span data-stu-id="ea9ed-125">Service installation</span></span> | <span data-ttu-id="ea9ed-126">События, захваченные со `ActionType` значением, указывающие на то, что `ServiceInstalled` была создана служба</span><span class="sxs-lookup"><span data-stu-id="ea9ed-126">Events captured with the `ActionType` value `ServiceInstalled`, indicating that a service has been created</span></span> | [<span data-ttu-id="ea9ed-127">DeviceEvents</span><span class="sxs-lookup"><span data-stu-id="ea9ed-127">DeviceEvents</span></span>](advanced-hunting-deviceevents-table.md) | <span data-ttu-id="ea9ed-128">- Развертывание усовершенствованой политики аудита безопасности: [расширение системы безопасности аудита](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span><span class="sxs-lookup"><span data-stu-id="ea9ed-128">- Deploy an advanced security audit policy: [Audit Security System Extension](https://docs.microsoft.com/windows/security/threat-protection/auditing/audit-security-system-extension)</span></span><br> <span data-ttu-id="ea9ed-129">- [Дополнительные политики аудита безопасности](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span><span class="sxs-lookup"><span data-stu-id="ea9ed-129">- [Learn about advanced security audit policies](https://docs.microsoft.com/windows/security/threat-protection/auditing/advanced-security-auditing)</span></span>

## <a name="related-topics"></a><span data-ttu-id="ea9ed-130">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="ea9ed-130">Related topics</span></span>

- [<span data-ttu-id="ea9ed-131">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="ea9ed-131">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="ea9ed-132">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="ea9ed-132">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="ea9ed-133">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="ea9ed-133">Understand the schema</span></span>](advanced-hunting-schema-reference.md)
- [<span data-ttu-id="ea9ed-134">Работа с результатами запросов</span><span class="sxs-lookup"><span data-stu-id="ea9ed-134">Work with query results</span></span>](advanced-hunting-query-results.md)
- [<span data-ttu-id="ea9ed-135">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="ea9ed-135">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
- [<span data-ttu-id="ea9ed-136">Обзор настраиваемых обнаружений</span><span class="sxs-lookup"><span data-stu-id="ea9ed-136">Custom detections overview</span></span>](overview-custom-detections.md)
