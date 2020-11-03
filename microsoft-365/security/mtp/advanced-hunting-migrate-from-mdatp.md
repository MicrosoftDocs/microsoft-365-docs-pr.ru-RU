---
title: Перенос дополнительных запросов на Поиск от защитника Майкрософт для конечной точки
description: Узнайте, как настроить защитник Майкрософт для запросов к конечным точкам, чтобы их можно было использовать в защитнике Microsoft 365.
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, пакет ATP ATP, мдатп, поиск, запрос, телеметрии, пользовательские обнаружения, схема, Кусто, Microsoft 365, сопоставление
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
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8b69dff94cc5d3ba3331fd6d13b1d7de1402ac47
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846860"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-for-endpoint"></a><span data-ttu-id="cbcb3-104">Перенос дополнительных запросов на Поиск от защитника Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cbcb3-104">Migrate advanced hunting queries from Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="cbcb3-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="cbcb3-105">**Applies to:**</span></span>
- <span data-ttu-id="cbcb3-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cbcb3-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="cbcb3-107">Перемещение расширенных рабочих процессов поиска из защитника Майкрософт для конечной точки для профилактического поиска угроз с помощью более широкого набора данных.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-107">Move your advanced hunting workflows from Microsoft Defender for Endpoint to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="cbcb3-108">В защитнике Microsoft 365 вы получаете доступ к данным из других решений для обеспечения безопасности Microsoft 365, в том числе:</span><span class="sxs-lookup"><span data-stu-id="cbcb3-108">In Microsoft 365 Defender, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="cbcb3-109">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cbcb3-109">Microsoft Defender for Endpoint</span></span>
- <span data-ttu-id="cbcb3-110">Защитник Майкрософт для Office 365</span><span class="sxs-lookup"><span data-stu-id="cbcb3-110">Microsoft Defender for Office 365</span></span>
- <span data-ttu-id="cbcb3-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="cbcb3-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="cbcb3-112">Microsoft Defender для удостоверений</span><span class="sxs-lookup"><span data-stu-id="cbcb3-112">Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="cbcb3-113">Большинство защитника Майкрософт для конечных пользователей могут [использовать защитник microsoft 365 без дополнительных лицензий](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="cbcb3-113">Most Microsoft Defender for Endpoint customers can [use Microsoft 365 Defender without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="cbcb3-114">Чтобы начать переводить расширенные рабочие процессы подпоиска из защитника для конечной точки, [включите Защитник Microsoft 365](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="cbcb3-114">To start transitioning your advanced hunting workflows from Defender for Endpoint, [turn on Microsoft 365 Defender](mtp-enable.md).</span></span>

<span data-ttu-id="cbcb3-115">Вы можете выполнить переход, не затрагивая существующий защитник для рабочих процессов конечной точки.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-115">You can transition without affecting your existing Defender for Endpoint workflows.</span></span> <span data-ttu-id="cbcb3-116">Сохраненные запросы остаются без изменений, а пользовательские правила обнаружения продолжают выполняться и создавать оповещения.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="cbcb3-117">Однако они будут отображаться в защитнике Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-117">They will, however, be visible in Microsoft 365 Defender.</span></span> 

## <a name="schema-tables-in-microsoft-365-defender-only"></a><span data-ttu-id="cbcb3-118">Таблицы схем только для защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cbcb3-118">Schema tables in Microsoft 365 Defender only</span></span>
<span data-ttu-id="cbcb3-119">[Схема расширенного контроля за защитником microsoft 365](advanced-hunting-schema-tables.md) содержит дополнительные таблицы, содержащие данные из различных решений по безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-119">The [Microsoft 365 Defender advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="cbcb3-120">Следующие таблицы доступны только в защитнике Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="cbcb3-120">The following tables are available only in Microsoft 365 Defender:</span></span>

| <span data-ttu-id="cbcb3-121">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="cbcb3-121">Table name</span></span> | <span data-ttu-id="cbcb3-122">Описание</span><span class="sxs-lookup"><span data-stu-id="cbcb3-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="cbcb3-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="cbcb3-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="cbcb3-124">Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями</span><span class="sxs-lookup"><span data-stu-id="cbcb3-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="cbcb3-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="cbcb3-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="cbcb3-126">Оповещения от защитника Майкрософт для конечной точки, защитник Майкрософт для Office 365, Microsoft Cloud App Security и защитник Майкрософт для удостоверения, в том числе сведения о степени серьезности и категории угроз</span><span class="sxs-lookup"><span data-stu-id="cbcb3-126">Alerts from Microsoft Defender for Endpoint, Microsoft Defender for Office 365, Microsoft Cloud App Security, and Microsoft Defender for Identity, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="cbcb3-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="cbcb3-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="cbcb3-128">Действия, связанные с файлами, в облачных приложениях и службах</span><span class="sxs-lookup"><span data-stu-id="cbcb3-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="cbcb3-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="cbcb3-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="cbcb3-130">Сведения о файлах, вложенных в сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="cbcb3-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="cbcb3-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="cbcb3-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="cbcb3-132">События электронной почты Microsoft 365, в том числе события доставки и блокировки электронной почты</span><span class="sxs-lookup"><span data-stu-id="cbcb3-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="cbcb3-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="cbcb3-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="cbcb3-134">События безопасности, происходящие после доставки, после того как Microsoft 365 доставляет сообщения в почтовый ящик получателя.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="cbcb3-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="cbcb3-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="cbcb3-136">Сведения об URL-адресах в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="cbcb3-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="cbcb3-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="cbcb3-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="cbcb3-138">События, связанные с локальным контроллером домена, на котором работает Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="cbcb3-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="cbcb3-139">В этой таблице описываются события, связанные с удостоверениями, и системные события на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="cbcb3-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="cbcb3-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="cbcb3-141">Сведения об учетных записях из различных источников, в том числе Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="cbcb3-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="cbcb3-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="cbcb3-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="cbcb3-143">События проверки подлинности в Active Directory и Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="cbcb3-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="cbcb3-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="cbcb3-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="cbcb3-145">Запросы для объектов Active Directory, таких как пользователи, группы, устройства и домены</span><span class="sxs-lookup"><span data-stu-id="cbcb3-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="cbcb3-146">Таблица Девицеалертевентс карты</span><span class="sxs-lookup"><span data-stu-id="cbcb3-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="cbcb3-147">Таблицы `AlertInfo` и `AlertEvidence` таблицы заменяют `DeviceAlertEvents` таблицу в схеме "защитник Майкрософт для конечной точки".</span><span class="sxs-lookup"><span data-stu-id="cbcb3-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender for Endpoint schema.</span></span> <span data-ttu-id="cbcb3-148">В дополнение к данным о предупреждениях устройств эти две таблицы содержат сведения об оповещениях для удостоверений, приложений и сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="cbcb3-149">Используйте приведенную ниже таблицу, чтобы проверить `DeviceAlertEvents` , как столбцы сопоставляются со столбцами в `AlertInfo` `AlertEvidence` таблицах и.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="cbcb3-150">Помимо столбцов, приведенных в следующей таблице, `AlertEvidence` таблица включает многие другие столбцы, которые обеспечивают более целостное изображение оповещений из различных источников.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="cbcb3-151">Просмотр всех столбцов Алертевиденце</span><span class="sxs-lookup"><span data-stu-id="cbcb3-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="cbcb3-152">Столбец Девицеалертевентс</span><span class="sxs-lookup"><span data-stu-id="cbcb3-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="cbcb3-153">Где найти те же данные в защитнике Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cbcb3-153">Where to find the same data in Microsoft 365 Defender</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="cbcb3-154">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="cbcb3-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="cbcb3-155">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="cbcb3-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="cbcb3-156">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="cbcb3-157">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="cbcb3-158">`AlertInfo` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="cbcb3-159">`AlertInfo` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="cbcb3-160">`AlertInfo` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="cbcb3-161">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="cbcb3-162">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="cbcb3-163">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="cbcb3-164">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="cbcb3-165">`AlertInfo` приведен</span><span class="sxs-lookup"><span data-stu-id="cbcb3-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="cbcb3-166">Этот столбец обычно используется в защитнике Майкрософт для конечной точки для обнаружения связанных записей в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-166">This column is typically used in Microsoft Defender for Endpoint to locate related records in other tables.</span></span> <span data-ttu-id="cbcb3-167">В защитнике Microsoft 365 можно получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-167">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="cbcb3-168">Этот столбец обычно используется в защитнике Майкрософт для конечной точки для дополнительных сведений о событиях в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-168">This column is typically used in Microsoft Defender for Endpoint for additional event information in other tables.</span></span> <span data-ttu-id="cbcb3-169">В защитнике Microsoft 365 можно получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-169">In Microsoft 365 Defender, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-for-endpoint-queries"></a><span data-ttu-id="cbcb3-170">Настройка существующего защитника Майкрософт для запросов к конечным точкам</span><span class="sxs-lookup"><span data-stu-id="cbcb3-170">Adjust existing Microsoft Defender for Endpoint queries</span></span>
<span data-ttu-id="cbcb3-171">Защитник Майкрософт для запросов к конечным точкам будет работать как есть, если они не ссылаются на `DeviceAlertEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-171">Microsoft Defender for Endpoint queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="cbcb3-172">Чтобы использовать эти запросы в защитнике Microsoft 365, примените следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="cbcb3-172">To use these queries in Microsoft 365 Defender, apply these changes:</span></span>

- <span data-ttu-id="cbcb3-173">Замените `DeviceAlertEvents` на `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="cbcb3-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="cbcb3-174">Присоединитесь к `AlertInfo` `AlertEvidence` таблицам, `AlertId` чтобы получить эквивалентные данные.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="cbcb3-175">Исходный запрос</span><span class="sxs-lookup"><span data-stu-id="cbcb3-175">Original query</span></span>
<span data-ttu-id="cbcb3-176">Следующий запрос использует `DeviceAlertEvents` в защитнике Майкрософт для конечной точки, чтобы получать оповещения, включающие _powershell.exe_ :</span><span class="sxs-lookup"><span data-stu-id="cbcb3-176">The following query uses `DeviceAlertEvents` in Microsoft Defender for Endpoint to get the alerts that involve _powershell.exe_ :</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="cbcb3-177">Измененный запрос</span><span class="sxs-lookup"><span data-stu-id="cbcb3-177">Modified query</span></span>
<span data-ttu-id="cbcb3-178">Следующий запрос был настроен для использования в защитнике Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-178">The following query has been adjusted for use in Microsoft 365 Defender.</span></span> <span data-ttu-id="cbcb3-179">Вместо того чтобы проверять имя файла непосредственно из `DeviceAlertEvents` , он присоединяется `AlertEvidence` и проверяет имя файла в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="cbcb3-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="cbcb3-180">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="cbcb3-180">Related topics</span></span>
- [<span data-ttu-id="cbcb3-181">Включение защитника Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="cbcb3-181">Turn on Microsoft 365 Defender</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="cbcb3-182">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="cbcb3-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="cbcb3-183">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="cbcb3-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="cbcb3-184">Расширенный поиск в защитнике Майкрософт для конечной точки</span><span class="sxs-lookup"><span data-stu-id="cbcb3-184">Advanced hunting in Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)