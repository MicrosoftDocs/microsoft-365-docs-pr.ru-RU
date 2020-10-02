---
title: Перенос расширенных запросов на поиск из пакета ATP для защитника Майкрософт
description: Узнайте, как настроить запросы ATP для защитника Майкрософт, чтобы их можно было использовать в защите от угроз Майкрософт.
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
ms.collection: M365-security-compliance
ms.topic: article
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: daa89ebf39f8fc6d2110720f61b8d02c074fb484
ms.sourcegitcommit: 0f48beaca3afa4df12d41847014975d50a4ebe7d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/02/2020
ms.locfileid: "48338724"
---
# <a name="migrate-advanced-hunting-queries-from-microsoft-defender-atp"></a><span data-ttu-id="868b5-104">Перенос расширенных запросов на поиск из пакета ATP для защитника Майкрософт</span><span class="sxs-lookup"><span data-stu-id="868b5-104">Migrate advanced hunting queries from Microsoft Defender ATP</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="868b5-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="868b5-105">**Applies to:**</span></span>
- <span data-ttu-id="868b5-106">Защита от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="868b5-106">Microsoft Threat Protection</span></span>

<span data-ttu-id="868b5-107">Перемещение расширенных рабочих процессов поиска из пакета ATP для защитника Майкрософт в профилактическое слежение за угрозами с помощью более широкого набора данных.</span><span class="sxs-lookup"><span data-stu-id="868b5-107">Move your advanced hunting workflows from Microsoft Defender ATP to proactively hunt for threats using a broader set of data.</span></span> <span data-ttu-id="868b5-108">В целях защиты от угроз Майкрософт вы получаете доступ к данным из других решений Microsoft 365 для обеспечения безопасности, в том числе:</span><span class="sxs-lookup"><span data-stu-id="868b5-108">In Microsoft Threat Protection, you get access to data from other Microsoft 365 security solutions, including:</span></span>

- <span data-ttu-id="868b5-109">Advanced Threat Protection в Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="868b5-109">Microsoft Defender Advanced Threat Protection</span></span>
- <span data-ttu-id="868b5-110">Office 365 Advanced Threat Protection</span><span class="sxs-lookup"><span data-stu-id="868b5-110">Office 365 Advanced Threat Protection</span></span>
- <span data-ttu-id="868b5-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="868b5-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="868b5-112">Расширенная защита от угроз Azure</span><span class="sxs-lookup"><span data-stu-id="868b5-112">Azure Advanced Threat Protection</span></span>

>[!NOTE]
><span data-ttu-id="868b5-113">Большинство клиентов пакета ATP для защитника Майкрософт могут [использовать защиту от угроз Майкрософт без дополнительных лицензий](prerequisites.md#licensing-requirements).</span><span class="sxs-lookup"><span data-stu-id="868b5-113">Most Microsoft Defender ATP customers can [use Microsoft Threat Protection without additional licenses](prerequisites.md#licensing-requirements).</span></span> <span data-ttu-id="868b5-114">Чтобы начать перевод расширенных рабочих процессов с помощью средства Microsoft Defender ATP, [включите защиту от угроз Майкрософт](mtp-enable.md).</span><span class="sxs-lookup"><span data-stu-id="868b5-114">To start transitioning your advanced hunting workflows from Microsoft Defender ATP, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

<span data-ttu-id="868b5-115">Вы можете выполнить переход, не затрагивая существующие рабочие процессы Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="868b5-115">You can transition without affecting your existing Microsoft Defender ATP workflows.</span></span> <span data-ttu-id="868b5-116">Сохраненные запросы остаются без изменений, а пользовательские правила обнаружения продолжают выполняться и создавать оповещения.</span><span class="sxs-lookup"><span data-stu-id="868b5-116">Saved queries remain intact, and custom detection rules continue to run and generate alerts.</span></span> <span data-ttu-id="868b5-117">Однако они будут отображаться в защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="868b5-117">They will, however, be visible in Microsoft Threat Protection.</span></span> 

## <a name="schema-tables-in-microsoft-threat-protection-only"></a><span data-ttu-id="868b5-118">Таблицы схем только в Microsoft Threat protection</span><span class="sxs-lookup"><span data-stu-id="868b5-118">Schema tables in Microsoft Threat Protection only</span></span>
<span data-ttu-id="868b5-119">[Расширенная схема подсистемы защиты от угроз Майкрософт](advanced-hunting-schema-tables.md) предоставляет дополнительные таблицы, содержащие данные из различных решений по безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="868b5-119">The [Microsoft Threat Protection advanced hunting schema](advanced-hunting-schema-tables.md) provides additional tables containing data from various Microsoft 365 security solutions.</span></span> <span data-ttu-id="868b5-120">Следующие таблицы доступны только в Microsoft Threat protection:</span><span class="sxs-lookup"><span data-stu-id="868b5-120">The following tables are available only in Microsoft Threat Protection:</span></span>

| <span data-ttu-id="868b5-121">Имя таблицы</span><span class="sxs-lookup"><span data-stu-id="868b5-121">Table name</span></span> | <span data-ttu-id="868b5-122">Описание</span><span class="sxs-lookup"><span data-stu-id="868b5-122">Description</span></span> |
|------------|-------------|
| [<span data-ttu-id="868b5-123">AlertEvidence</span><span class="sxs-lookup"><span data-stu-id="868b5-123">AlertEvidence</span></span>](advanced-hunting-alertevidence-table.md) | <span data-ttu-id="868b5-124">Файлы, IP-адреса, URL-адреса, пользователи или устройства, связанные с оповещениями</span><span class="sxs-lookup"><span data-stu-id="868b5-124">Files, IP addresses, URLs, users, or devices associated with alerts</span></span> |
| [<span data-ttu-id="868b5-125">AlertInfo</span><span class="sxs-lookup"><span data-stu-id="868b5-125">AlertInfo</span></span>](advanced-hunting-alertinfo-table.md) | <span data-ttu-id="868b5-126">Оповещения из пакета ATP, Office 365 ATP, Microsoft Cloud App Security и Azure ATP, в том числе сведения о степени серьезности и категории угроз</span><span class="sxs-lookup"><span data-stu-id="868b5-126">Alerts from Microsoft Defender ATP, Office 365 ATP, Microsoft Cloud App Security, and Azure ATP, including severity information and threat categories</span></span>  |
| [<span data-ttu-id="868b5-127">AppFileEvents</span><span class="sxs-lookup"><span data-stu-id="868b5-127">AppFileEvents</span></span>](advanced-hunting-appfileevents-table.md) | <span data-ttu-id="868b5-128">Действия, связанные с файлами, в облачных приложениях и службах</span><span class="sxs-lookup"><span data-stu-id="868b5-128">File-related activities in cloud apps and services</span></span> |
| [<span data-ttu-id="868b5-129">EmailAttachmentInfo</span><span class="sxs-lookup"><span data-stu-id="868b5-129">EmailAttachmentInfo</span></span>](advanced-hunting-emailattachmentinfo-table.md) | <span data-ttu-id="868b5-130">Сведения о файлах, вложенных в сообщения электронной почты</span><span class="sxs-lookup"><span data-stu-id="868b5-130">Information about files attached to emails</span></span> |
| [<span data-ttu-id="868b5-131">EmailEvents</span><span class="sxs-lookup"><span data-stu-id="868b5-131">EmailEvents</span></span>](advanced-hunting-emailevents-table.md) | <span data-ttu-id="868b5-132">События электронной почты Microsoft 365, в том числе события доставки и блокировки электронной почты</span><span class="sxs-lookup"><span data-stu-id="868b5-132">Microsoft 365 email events, including email delivery and blocking events</span></span> |
| [<span data-ttu-id="868b5-133">EmailPostDeliveryEvents</span><span class="sxs-lookup"><span data-stu-id="868b5-133">EmailPostDeliveryEvents</span></span>](advanced-hunting-emailpostdeliveryevents-table.md) | <span data-ttu-id="868b5-134">События безопасности, происходящие после доставки, после того как Microsoft 365 доставляет сообщения в почтовый ящик получателя.</span><span class="sxs-lookup"><span data-stu-id="868b5-134">Security events that occur post-delivery, after Microsoft 365 has delivered the emails to the recipient mailbox</span></span> |
| [<span data-ttu-id="868b5-135">EmailUrlInfo</span><span class="sxs-lookup"><span data-stu-id="868b5-135">EmailUrlInfo</span></span>](advanced-hunting-emailurlinfo-table.md) | <span data-ttu-id="868b5-136">Сведения об URL-адресах в сообщениях электронной почты</span><span class="sxs-lookup"><span data-stu-id="868b5-136">Information about URLs on emails</span></span> |
| [<span data-ttu-id="868b5-137">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="868b5-137">IdentityDirectoryEvents</span></span>](advanced-hunting-identitydirectoryevents-table.md) | <span data-ttu-id="868b5-138">События, связанные с локальным контроллером домена, на котором работает Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="868b5-138">Events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="868b5-139">В этой таблице описываются события, связанные с удостоверениями, и системные события на контроллере домена.</span><span class="sxs-lookup"><span data-stu-id="868b5-139">This table covers a range of identity-related events and system events on the domain controller.</span></span> |
| [<span data-ttu-id="868b5-140">IdentityInfo</span><span class="sxs-lookup"><span data-stu-id="868b5-140">IdentityInfo</span></span>](advanced-hunting-identityinfo-table.md) | <span data-ttu-id="868b5-141">Сведения об учетных записях из различных источников, в том числе Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="868b5-141">Account information from various sources, including Azure Active Directory</span></span> |
| [<span data-ttu-id="868b5-142">IdentityLogonEvents</span><span class="sxs-lookup"><span data-stu-id="868b5-142">IdentityLogonEvents</span></span>](advanced-hunting-identitylogonevents-table.md) | <span data-ttu-id="868b5-143">События проверки подлинности в Active Directory и Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="868b5-143">Authentication events on Active Directory and Microsoft online services</span></span> |
| [<span data-ttu-id="868b5-144">IdentityQueryEvents</span><span class="sxs-lookup"><span data-stu-id="868b5-144">IdentityQueryEvents</span></span>](advanced-hunting-identityqueryevents-table.md) | <span data-ttu-id="868b5-145">Запросы для объектов Active Directory, таких как пользователи, группы, устройства и домены</span><span class="sxs-lookup"><span data-stu-id="868b5-145">Queries for Active Directory objects, such as users, groups, devices, and domains</span></span> |

## <a name="map-devicealertevents-table"></a><span data-ttu-id="868b5-146">Таблица Девицеалертевентс карты</span><span class="sxs-lookup"><span data-stu-id="868b5-146">Map DeviceAlertEvents table</span></span>
<span data-ttu-id="868b5-147">Таблицы `AlertInfo` и `AlertEvidence` таблицы заменяют `DeviceAlertEvents` таблицу в схеме Microsoft Defender ATP.</span><span class="sxs-lookup"><span data-stu-id="868b5-147">The `AlertInfo` and `AlertEvidence` tables replace the `DeviceAlertEvents` table in the Microsoft Defender ATP schema.</span></span> <span data-ttu-id="868b5-148">В дополнение к данным о предупреждениях устройств эти две таблицы содержат сведения об оповещениях для удостоверений, приложений и сообщений электронной почты.</span><span class="sxs-lookup"><span data-stu-id="868b5-148">In addition to data about device alerts, these two tables include data about alerts for identities, apps, and emails.</span></span>

<span data-ttu-id="868b5-149">Используйте приведенную ниже таблицу, чтобы проверить `DeviceAlertEvents` , как столбцы сопоставляются со столбцами в `AlertInfo` `AlertEvidence` таблицах и.</span><span class="sxs-lookup"><span data-stu-id="868b5-149">Use the following table to check how `DeviceAlertEvents` columns map to columns in the `AlertInfo` and `AlertEvidence` tables.</span></span>

>[!TIP]
><span data-ttu-id="868b5-150">Помимо столбцов, приведенных в следующей таблице, `AlertEvidence` таблица включает многие другие столбцы, которые обеспечивают более целостное изображение оповещений из различных источников.</span><span class="sxs-lookup"><span data-stu-id="868b5-150">In addition to the columns the following table, the `AlertEvidence` table includes many other columns that provide a more holistic picture of alerts from various sources.</span></span> [<span data-ttu-id="868b5-151">Просмотр всех столбцов Алертевиденце</span><span class="sxs-lookup"><span data-stu-id="868b5-151">See all AlertEvidence columns</span></span>](advanced-hunting-alertevidence-table.md) 

| <span data-ttu-id="868b5-152">Столбец Девицеалертевентс</span><span class="sxs-lookup"><span data-stu-id="868b5-152">DeviceAlertEvents column</span></span> | <span data-ttu-id="868b5-153">Где найти те же данные в защите от угроз Майкрософт</span><span class="sxs-lookup"><span data-stu-id="868b5-153">Where to find the same data in Microsoft Threat Protection</span></span> |
|-------------|-----------|-------------|-------------|
| `AlertId` | <span data-ttu-id="868b5-154">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="868b5-154">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `Timestamp` | <span data-ttu-id="868b5-155">`AlertInfo` и  `AlertEvidence` таблицы</span><span class="sxs-lookup"><span data-stu-id="868b5-155">`AlertInfo` and  `AlertEvidence` tables</span></span> |
| `DeviceId` | <span data-ttu-id="868b5-156">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-156">`AlertEvidence` table</span></span> |
| `DeviceName` | <span data-ttu-id="868b5-157">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-157">`AlertEvidence` table</span></span> |
| `Severity` | <span data-ttu-id="868b5-158">`AlertInfo` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-158">`AlertInfo` table</span></span> |
| `Category` | <span data-ttu-id="868b5-159">`AlertInfo` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-159">`AlertInfo` table</span></span> |
| `Title` | <span data-ttu-id="868b5-160">`AlertInfo` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-160">`AlertInfo` table</span></span> |
| `FileName` | <span data-ttu-id="868b5-161">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-161">`AlertEvidence` table</span></span> |
| `SHA1` | <span data-ttu-id="868b5-162">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-162">`AlertEvidence` table</span></span> |
| `RemoteUrl` | <span data-ttu-id="868b5-163">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-163">`AlertEvidence` table</span></span> |
| `RemoteIP` | <span data-ttu-id="868b5-164">`AlertEvidence` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-164">`AlertEvidence` table</span></span> |
| `AttackTechniques` | <span data-ttu-id="868b5-165">`AlertInfo` приведен</span><span class="sxs-lookup"><span data-stu-id="868b5-165">`AlertInfo` table</span></span> |
| `ReportId` | <span data-ttu-id="868b5-166">Этот столбец, как правило, используется в Microsoft Defender ATP для обнаружения связанных записей в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="868b5-166">This column is typically used in Microsoft Defender ATP to locate related records in other tables.</span></span> <span data-ttu-id="868b5-167">В целях защиты от угроз Майкрософт можно получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="868b5-167">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |
| `Table` | <span data-ttu-id="868b5-168">Этот столбец, как правило, используется в журнале Microsoft Defender ATP для получения дополнительных сведений о событиях в других таблицах.</span><span class="sxs-lookup"><span data-stu-id="868b5-168">This column is typically used in Microsoft Defender ATP for additional event information in other tables.</span></span> <span data-ttu-id="868b5-169">В целях защиты от угроз Майкрософт можно получить связанные данные непосредственно из `AlertEvidence` таблицы.</span><span class="sxs-lookup"><span data-stu-id="868b5-169">In Microsoft Threat Protection, you can get related data directly from the `AlertEvidence` table.</span></span> |

## <a name="adjust-existing-microsoft-defender-atp-queries"></a><span data-ttu-id="868b5-170">Настройка существующих запросов ATP для защитника Microsoft</span><span class="sxs-lookup"><span data-stu-id="868b5-170">Adjust existing Microsoft Defender ATP queries</span></span>
<span data-ttu-id="868b5-171">Запросы ATP для защитника Майкрософт будут работать как есть, если они не ссылаются на `DeviceAlertEvents` таблицу.</span><span class="sxs-lookup"><span data-stu-id="868b5-171">Microsoft Defender ATP queries will work as-is unless they reference the `DeviceAlertEvents` table.</span></span> <span data-ttu-id="868b5-172">Чтобы использовать эти запросы в защите от угроз Майкрософт, примените следующие изменения:</span><span class="sxs-lookup"><span data-stu-id="868b5-172">To use these queries in Microsoft Threat Protection, apply these changes:</span></span>

- <span data-ttu-id="868b5-173">Замените `DeviceAlertEvents` на `AlertInfo` .</span><span class="sxs-lookup"><span data-stu-id="868b5-173">Replace `DeviceAlertEvents` with `AlertInfo`.</span></span>
- <span data-ttu-id="868b5-174">Присоединитесь к `AlertInfo` `AlertEvidence` таблицам, `AlertId` чтобы получить эквивалентные данные.</span><span class="sxs-lookup"><span data-stu-id="868b5-174">Join the `AlertInfo` and the `AlertEvidence` tables on `AlertId` to get equivalent data.</span></span>

### <a name="original-query"></a><span data-ttu-id="868b5-175">Исходный запрос</span><span class="sxs-lookup"><span data-stu-id="868b5-175">Original query</span></span>
<span data-ttu-id="868b5-176">В следующем запросе `DeviceAlertEvents` для получения оповещений, включающих _powershell.exe_, используется пакет ATP для защитника:</span><span class="sxs-lookup"><span data-stu-id="868b5-176">The following query uses `DeviceAlertEvents` in Microsoft Defender ATP to get the alerts that involve _powershell.exe_:</span></span>

```kusto
DeviceAlertEvents
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" and FileName == "powershell.exe"
```
### <a name="modified-query"></a><span data-ttu-id="868b5-177">Измененный запрос</span><span class="sxs-lookup"><span data-stu-id="868b5-177">Modified query</span></span>
<span data-ttu-id="868b5-178">Приведенный ниже запрос был скорректирован для использования в защите от угроз Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="868b5-178">The following query has been adjusted for use in Microsoft Threat Protection.</span></span> <span data-ttu-id="868b5-179">Вместо того чтобы проверять имя файла непосредственно из `DeviceAlertEvents` , он присоединяется `AlertEvidence` и проверяет имя файла в этой таблице.</span><span class="sxs-lookup"><span data-stu-id="868b5-179">Instead of checking the file name directly from `DeviceAlertEvents`, it joins `AlertEvidence` and checks for the file name in that table.</span></span>

```kusto
AlertInfo 
| where Timestamp > ago(7d) 
| where AttackTechniques has "PowerShell (T1086)" 
| join AlertEvidence on AlertId
| where FileName == "powershell.exe"
```

## <a name="related-topics"></a><span data-ttu-id="868b5-180">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="868b5-180">Related topics</span></span>
- [<span data-ttu-id="868b5-181">Включение Защиты от угроз (Майкрософт)</span><span class="sxs-lookup"><span data-stu-id="868b5-181">Turn on Microsoft Threat Protection</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="868b5-182">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="868b5-182">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="868b5-183">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="868b5-183">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="868b5-184">Расширенные функции Поиск в защитнике Майкрософт ATP</span><span class="sxs-lookup"><span data-stu-id="868b5-184">Advanced hunting in Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)