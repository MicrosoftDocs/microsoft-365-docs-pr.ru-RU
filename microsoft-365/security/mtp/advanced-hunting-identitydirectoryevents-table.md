---
title: Таблица идентитидиректоревентс в схеме расширенного поискового окна
description: Сведения о контроллере домена и событиях Active Directory в таблице Идентитидиректоревентс расширенной схемы подпоиска
keywords: Расширенный поиск, Поиск угроз, Поиск угроз кибератак, защита от угроз Майкрософт, Microsoft 365, MTP, m365, поиск, запрос, телеметрии, Справка по схеме, Кусто, таблица, столбец, тип данных, описание, Идентитидиректоревентс, контроллер домена, Active Directory, Azure ATP, удостоверения
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
ms.openlocfilehash: 41b429e32122d6cc58a746649c8a0428f0a90b0f
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847432"
---
# <a name="identitydirectoryevents"></a><span data-ttu-id="3acba-104">IdentityDirectoryEvents</span><span class="sxs-lookup"><span data-stu-id="3acba-104">IdentityDirectoryEvents</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="3acba-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="3acba-105">**Applies to:**</span></span>
- <span data-ttu-id="3acba-106">Защитник Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3acba-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="3acba-107">`IdentityDirectoryEvents`Таблица в [расширенной](advanced-hunting-overview.md) схеме Поиск содержит события, связанные с локальным контроллером домена, на котором работает Active Directory (AD).</span><span class="sxs-lookup"><span data-stu-id="3acba-107">The `IdentityDirectoryEvents` table in the [advanced hunting](advanced-hunting-overview.md) schema contains events involving an on-premises domain controller running Active Directory (AD).</span></span> <span data-ttu-id="3acba-108">В этой таблице записаны различные события, связанные с удостоверениями, такие как изменение паролей, срок действия пароля и имя участника-пользователя (UPN).</span><span class="sxs-lookup"><span data-stu-id="3acba-108">This table captures various identity-related events, like password changes, password expiration, and user principal name (UPN) changes.</span></span> <span data-ttu-id="3acba-109">Он также захватывает системные события на контроллере домена, например планирование задач и действий PowerShell.</span><span class="sxs-lookup"><span data-stu-id="3acba-109">It also captures system events on the domain controller, like scheduling of tasks and PowerShell activity.</span></span> <span data-ttu-id="3acba-110">Используйте этот справочник для создания запросов, возвращающих данные из этой таблицы.</span><span class="sxs-lookup"><span data-stu-id="3acba-110">Use this reference to construct queries that return information from this table.</span></span>

>[!TIP]
> <span data-ttu-id="3acba-111">Для получения подробных сведений о типах событий ( `ActionType` значений), поддерживаемых таблицей, используйте [встроенную справочную](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) информацию о схеме, доступную в центре обеспечения безопасности.</span><span class="sxs-lookup"><span data-stu-id="3acba-111">For detailed information about the events types (`ActionType` values) supported by a table, use the [built-in schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) available in the security center.</span></span>

<span data-ttu-id="3acba-112">Сведения о других таблицах в схеме расширенного поиска см. в [справочнике по расширенному поиску](advanced-hunting-schema-tables.md).</span><span class="sxs-lookup"><span data-stu-id="3acba-112">For information on other tables in the advanced hunting schema, [see the advanced hunting reference](advanced-hunting-schema-tables.md).</span></span>

| <span data-ttu-id="3acba-113">Имя столбца</span><span class="sxs-lookup"><span data-stu-id="3acba-113">Column name</span></span> | <span data-ttu-id="3acba-114">Тип данных</span><span class="sxs-lookup"><span data-stu-id="3acba-114">Data type</span></span> | <span data-ttu-id="3acba-115">Описание</span><span class="sxs-lookup"><span data-stu-id="3acba-115">Description</span></span> |
|-------------|-----------|-------------|
| `Timestamp` | <span data-ttu-id="3acba-116">datetime</span><span class="sxs-lookup"><span data-stu-id="3acba-116">datetime</span></span> | <span data-ttu-id="3acba-117">Дата и время записи события</span><span class="sxs-lookup"><span data-stu-id="3acba-117">Date and time when the event was recorded</span></span> |
| `ActionType` | <span data-ttu-id="3acba-118">string</span><span class="sxs-lookup"><span data-stu-id="3acba-118">string</span></span> | <span data-ttu-id="3acba-119">Тип действия, вызвавшего событие.</span><span class="sxs-lookup"><span data-stu-id="3acba-119">Type of activity that triggered the event.</span></span> <span data-ttu-id="3acba-120">Дополнительные сведения см. [в справочнике по схемам на портале](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center)</span><span class="sxs-lookup"><span data-stu-id="3acba-120">See the [in-portal schema reference](advanced-hunting-schema-tables.md?#get-schema-information-in-the-security-center) for details</span></span> |
| `Application` | <span data-ttu-id="3acba-121">string</span><span class="sxs-lookup"><span data-stu-id="3acba-121">string</span></span> | <span data-ttu-id="3acba-122">Приложение, которое выполнило записанное действие</span><span class="sxs-lookup"><span data-stu-id="3acba-122">Application that performed the recorded action</span></span> |
| `TargetAccountUpn` | <span data-ttu-id="3acba-123">string</span><span class="sxs-lookup"><span data-stu-id="3acba-123">string</span></span> | <span data-ttu-id="3acba-124">Имя участника-пользователя (UPN) учетной записи, к которой было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="3acba-124">User principal name (UPN) of the account that the recorded action was applied to</span></span> |
| `TargetAccountDisplayName` | <span data-ttu-id="3acba-125">string</span><span class="sxs-lookup"><span data-stu-id="3acba-125">string</span></span> | <span data-ttu-id="3acba-126">Отображаемое имя учетной записи, к которой было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="3acba-126">Display name of the account that the recorded action was applied to</span></span> |
| `TargetDeviceName` | <span data-ttu-id="3acba-127">string</span><span class="sxs-lookup"><span data-stu-id="3acba-127">string</span></span> | <span data-ttu-id="3acba-128">Полное доменное имя (FQDN) устройства, к которому было применено записанное действие</span><span class="sxs-lookup"><span data-stu-id="3acba-128">Fully qualified domain name (FQDN) of the device that the recorded action was applied to</span></span> |
| `DestinationDeviceName` | <span data-ttu-id="3acba-129">string</span><span class="sxs-lookup"><span data-stu-id="3acba-129">string</span></span> | <span data-ttu-id="3acba-130">Имя устройства, на котором работает серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="3acba-130">Name of the device running the server application that processed the recorded action</span></span> |
| `DestinationIPAddress` | <span data-ttu-id="3acba-131">string</span><span class="sxs-lookup"><span data-stu-id="3acba-131">string</span></span> | <span data-ttu-id="3acba-132">IP-адрес устройства, на котором запущено серверное приложение, которое обработало записанное действие</span><span class="sxs-lookup"><span data-stu-id="3acba-132">IP address of the device running the server application that processed the recorded action</span></span> |
| `DestinationPort` | <span data-ttu-id="3acba-133">string</span><span class="sxs-lookup"><span data-stu-id="3acba-133">string</span></span> | <span data-ttu-id="3acba-134">Конечный порт действия</span><span class="sxs-lookup"><span data-stu-id="3acba-134">Destination port of the activity</span></span> |
| `Protocol` | <span data-ttu-id="3acba-135">string</span><span class="sxs-lookup"><span data-stu-id="3acba-135">string</span></span> | <span data-ttu-id="3acba-136">Протокол, используемый при обмене данными</span><span class="sxs-lookup"><span data-stu-id="3acba-136">Protocol used during the communication</span></span> |
| `AccountName` | <span data-ttu-id="3acba-137">string</span><span class="sxs-lookup"><span data-stu-id="3acba-137">string</span></span> | <span data-ttu-id="3acba-138">Имя пользователя учетной записи</span><span class="sxs-lookup"><span data-stu-id="3acba-138">User name of the account</span></span> |
| `AccountDomain` | <span data-ttu-id="3acba-139">string</span><span class="sxs-lookup"><span data-stu-id="3acba-139">string</span></span> | <span data-ttu-id="3acba-140">Домен учетной записи</span><span class="sxs-lookup"><span data-stu-id="3acba-140">Domain of the account</span></span> |
| `AccountUpn` | <span data-ttu-id="3acba-141">string</span><span class="sxs-lookup"><span data-stu-id="3acba-141">string</span></span> | <span data-ttu-id="3acba-142">Имя участника-пользователя (UPN) учетной записи</span><span class="sxs-lookup"><span data-stu-id="3acba-142">User principal name (UPN) of the account</span></span> |
| `AccountSid` | <span data-ttu-id="3acba-143">string</span><span class="sxs-lookup"><span data-stu-id="3acba-143">string</span></span> | <span data-ttu-id="3acba-144">Идентификатор безопасности (SID) учетной записи</span><span class="sxs-lookup"><span data-stu-id="3acba-144">Security Identifier (SID) of the account</span></span> |
| `AccountObjectId` | <span data-ttu-id="3acba-145">string</span><span class="sxs-lookup"><span data-stu-id="3acba-145">string</span></span> | <span data-ttu-id="3acba-146">Уникальный идентификатор учетной записи в Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="3acba-146">Unique identifier for the account in Azure Active Directory</span></span> |
| `AccountDisplayName` | <span data-ttu-id="3acba-147">string</span><span class="sxs-lookup"><span data-stu-id="3acba-147">string</span></span> | <span data-ttu-id="3acba-148">Имя пользователя учетной записи, отображаемое в адресной книге.</span><span class="sxs-lookup"><span data-stu-id="3acba-148">Name of the account user displayed in the address book.</span></span> <span data-ttu-id="3acba-149">Как правило, это сочетание определенного или имени, посрединное инициирование, фамилия или фамилия.</span><span class="sxs-lookup"><span data-stu-id="3acba-149">Typically a combination of a given or first name, a middle initiation, and a last name or surname.</span></span> |
| `DeviceName` | <span data-ttu-id="3acba-150">string</span><span class="sxs-lookup"><span data-stu-id="3acba-150">string</span></span> | <span data-ttu-id="3acba-151">Полное доменное имя (FQDN) устройства</span><span class="sxs-lookup"><span data-stu-id="3acba-151">Fully qualified domain name (FQDN) of the device</span></span> |
| `IPAddress` | <span data-ttu-id="3acba-152">string</span><span class="sxs-lookup"><span data-stu-id="3acba-152">string</span></span> | <span data-ttu-id="3acba-153">IP-адрес, назначенный устройству при обмене данными</span><span class="sxs-lookup"><span data-stu-id="3acba-153">IP address assigned to the device during communication</span></span> |
| `Port` | <span data-ttu-id="3acba-154">string</span><span class="sxs-lookup"><span data-stu-id="3acba-154">string</span></span> | <span data-ttu-id="3acba-155">TCP-порт, используемый при обмене данными</span><span class="sxs-lookup"><span data-stu-id="3acba-155">TCP port used during communication</span></span> |
| `Location` | <span data-ttu-id="3acba-156">string</span><span class="sxs-lookup"><span data-stu-id="3acba-156">string</span></span> | <span data-ttu-id="3acba-157">Город, страна или другое географическое расположение, связанное с событием</span><span class="sxs-lookup"><span data-stu-id="3acba-157">City, country, or other geographic location associated with the event</span></span> |
| `ISP` | <span data-ttu-id="3acba-158">string</span><span class="sxs-lookup"><span data-stu-id="3acba-158">string</span></span> | <span data-ttu-id="3acba-159">Поставщик услуг Интернета, связанный с IP-адресом</span><span class="sxs-lookup"><span data-stu-id="3acba-159">Internet service provider associated with the IP address</span></span> |
| `ReportId` | <span data-ttu-id="3acba-160">long</span><span class="sxs-lookup"><span data-stu-id="3acba-160">long</span></span> | <span data-ttu-id="3acba-161">Уникальный идентификатор для события</span><span class="sxs-lookup"><span data-stu-id="3acba-161">Unique identifier for the event</span></span> |
| `AdditionalFields` | <span data-ttu-id="3acba-162">string</span><span class="sxs-lookup"><span data-stu-id="3acba-162">string</span></span> | <span data-ttu-id="3acba-163">Дополнительные сведения о сущности или событии</span><span class="sxs-lookup"><span data-stu-id="3acba-163">Additional information about the entity or event</span></span> |

## <a name="related-topics"></a><span data-ttu-id="3acba-164">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="3acba-164">Related topics</span></span>
- [<span data-ttu-id="3acba-165">Обзор расширенной охоты на угрозы</span><span class="sxs-lookup"><span data-stu-id="3acba-165">Advanced hunting overview</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="3acba-166">Изучение языка запросов</span><span class="sxs-lookup"><span data-stu-id="3acba-166">Learn the query language</span></span>](advanced-hunting-query-language.md)
- [<span data-ttu-id="3acba-167">Использование общих запросов</span><span class="sxs-lookup"><span data-stu-id="3acba-167">Use shared queries</span></span>](advanced-hunting-shared-queries.md)
- [<span data-ttu-id="3acba-168">Охота на различных устройствах, в письмах, приложениях и удостоверениях</span><span class="sxs-lookup"><span data-stu-id="3acba-168">Hunt across devices, emails, apps, and identities</span></span>](advanced-hunting-query-emails-devices.md)
- [<span data-ttu-id="3acba-169">Сведения о схеме</span><span class="sxs-lookup"><span data-stu-id="3acba-169">Understand the schema</span></span>](advanced-hunting-schema-tables.md)
- [<span data-ttu-id="3acba-170">Рекомендации по применению запросов</span><span class="sxs-lookup"><span data-stu-id="3acba-170">Apply query best practices</span></span>](advanced-hunting-best-practices.md)
