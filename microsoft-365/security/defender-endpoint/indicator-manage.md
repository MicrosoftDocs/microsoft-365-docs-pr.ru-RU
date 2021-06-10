---
title: Управление индикаторами
ms.reviewer: ''
description: Управление индикаторами для хеш-файлов, IP-адресов, URL-адресов или доменов, определяющих обнаружение, предотвращение и исключение сущностями.
keywords: импорт, индикатор, список, мок, csv, управление, разрешено, заблокировано, блок, чистый, вредоносный, файл hash, IP-адрес, URL-адреса, домен
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9fd36f63450335247bf57c4cc1f98d6f0d32a9d5
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185949"
---
# <a name="manage-indicators"></a><span data-ttu-id="52070-104">Управление индикаторами</span><span class="sxs-lookup"><span data-stu-id="52070-104">Manage indicators</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="52070-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="52070-105">**Applies to:**</span></span>
- [<span data-ttu-id="52070-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="52070-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="52070-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="52070-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="52070-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="52070-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="52070-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="52070-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/en-us/WindowsForBusiness/windows-atp?ocid=docs-wdatp-automationexclusionlist-abovefoldlink)


1. <span data-ttu-id="52070-110">В области навигации выберите **Параметры**  >  **Индикаторы**.</span><span class="sxs-lookup"><span data-stu-id="52070-110">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="52070-111">Выберите вкладку типа сущности, которая будет управляться.</span><span class="sxs-lookup"><span data-stu-id="52070-111">Select the tab of the entity type you'd like to manage.</span></span>  

3. <span data-ttu-id="52070-112">Обновите сведения о индикаторе и нажмите кнопку **Сохранить** или нажмите кнопку **Удалить,** если вы хотите удалить объект из списка.</span><span class="sxs-lookup"><span data-stu-id="52070-112">Update the details of the indicator and click **Save** or click the **Delete** button if you'd like to remove the entity from the list.</span></span>

## <a name="import-a-list-of-iocs"></a><span data-ttu-id="52070-113">Импорт списка IoCs</span><span class="sxs-lookup"><span data-stu-id="52070-113">Import a list of IoCs</span></span>

<span data-ttu-id="52070-114">Вы также можете загрузить CSV-файл, который определяет атрибуты индикаторов, действия, которые необходимо принять, и другие сведения.</span><span class="sxs-lookup"><span data-stu-id="52070-114">You can also choose to upload a CSV file that defines the attributes of indicators, the action to be taken, and other details.</span></span>

<span data-ttu-id="52070-115">Скачайте пример CSV, чтобы узнать поддерживаемые атрибуты столбца.</span><span class="sxs-lookup"><span data-stu-id="52070-115">Download the sample CSV to know the supported column attributes.</span></span>

1. <span data-ttu-id="52070-116">В области навигации выберите **Параметры**  >  **Индикаторы**.</span><span class="sxs-lookup"><span data-stu-id="52070-116">In the navigation pane, select **Settings** > **Indicators**.</span></span>

2. <span data-ttu-id="52070-117">Выберите вкладку типа сущности, для нее необходимо импортировать индикаторы.</span><span class="sxs-lookup"><span data-stu-id="52070-117">Select the tab of the entity type you'd like to import indicators for.</span></span>

3. <span data-ttu-id="52070-118">Выберите **файл Import**  >  **Choose**.</span><span class="sxs-lookup"><span data-stu-id="52070-118">Select **Import** > **Choose file**.</span></span> 

4. <span data-ttu-id="52070-119">Нажмите **Импорт**.</span><span class="sxs-lookup"><span data-stu-id="52070-119">Select **Import**.</span></span> <span data-ttu-id="52070-120">Сделайте это для всех файлов, которые необходимо импортировать.</span><span class="sxs-lookup"><span data-stu-id="52070-120">Do this for all the files you'd like to import.</span></span> 

5. <span data-ttu-id="52070-121">Нажмите кнопку **Готово**.</span><span class="sxs-lookup"><span data-stu-id="52070-121">Select **Done**.</span></span>

<span data-ttu-id="52070-122">В следующей таблице показаны поддерживаемые параметры.</span><span class="sxs-lookup"><span data-stu-id="52070-122">The following table shows the supported parameters.</span></span>

<span data-ttu-id="52070-123">Параметр</span><span class="sxs-lookup"><span data-stu-id="52070-123">Parameter</span></span> | <span data-ttu-id="52070-124">Тип</span><span class="sxs-lookup"><span data-stu-id="52070-124">Type</span></span>    |   <span data-ttu-id="52070-125">Описание</span><span class="sxs-lookup"><span data-stu-id="52070-125">Description</span></span>
:---|:---|:---
<span data-ttu-id="52070-126">indicatorType</span><span class="sxs-lookup"><span data-stu-id="52070-126">indicatorType</span></span> | <span data-ttu-id="52070-127">Перечисление</span><span class="sxs-lookup"><span data-stu-id="52070-127">Enum</span></span> | <span data-ttu-id="52070-128">Тип индикатора.</span><span class="sxs-lookup"><span data-stu-id="52070-128">Type of the indicator.</span></span> <span data-ttu-id="52070-129">Возможные значения: "FileSha1", "FileSha256", "IpAddress", "DomainName" и "URL".</span><span class="sxs-lookup"><span data-stu-id="52070-129">Possible values are: "FileSha1", "FileSha256", "IpAddress", "DomainName" and "Url".</span></span> <span data-ttu-id="52070-130">**Required**</span><span class="sxs-lookup"><span data-stu-id="52070-130">**Required**</span></span>
<span data-ttu-id="52070-131">indicatorValue</span><span class="sxs-lookup"><span data-stu-id="52070-131">indicatorValue</span></span> | <span data-ttu-id="52070-132">String</span><span class="sxs-lookup"><span data-stu-id="52070-132">String</span></span> | <span data-ttu-id="52070-133">Удостоверение сущности [индикатора.](ti-indicator.md)</span><span class="sxs-lookup"><span data-stu-id="52070-133">Identity of the [Indicator](ti-indicator.md) entity.</span></span> <span data-ttu-id="52070-134">**Required**</span><span class="sxs-lookup"><span data-stu-id="52070-134">**Required**</span></span>
<span data-ttu-id="52070-135">action</span><span class="sxs-lookup"><span data-stu-id="52070-135">action</span></span> | <span data-ttu-id="52070-136">Перечисление</span><span class="sxs-lookup"><span data-stu-id="52070-136">Enum</span></span> | <span data-ttu-id="52070-137">Действие, которое будет принято, если индикатор будет обнаружен в организации.</span><span class="sxs-lookup"><span data-stu-id="52070-137">The action that will be taken if the indicator will be discovered in the organization.</span></span> <span data-ttu-id="52070-138">Возможные значения: "Alert", "AlertAndBlock" и "Allowed".</span><span class="sxs-lookup"><span data-stu-id="52070-138">Possible values are: "Alert", "AlertAndBlock", and "Allowed".</span></span> <span data-ttu-id="52070-139">**Required**</span><span class="sxs-lookup"><span data-stu-id="52070-139">**Required**</span></span>
<span data-ttu-id="52070-140">title</span><span class="sxs-lookup"><span data-stu-id="52070-140">title</span></span> | <span data-ttu-id="52070-141">String</span><span class="sxs-lookup"><span data-stu-id="52070-141">String</span></span> | <span data-ttu-id="52070-142">Название оповещений индикатора.</span><span class="sxs-lookup"><span data-stu-id="52070-142">Indicator alert title.</span></span> <span data-ttu-id="52070-143">**Required**</span><span class="sxs-lookup"><span data-stu-id="52070-143">**Required**</span></span>
<span data-ttu-id="52070-144">description</span><span class="sxs-lookup"><span data-stu-id="52070-144">description</span></span> | <span data-ttu-id="52070-145">String</span><span class="sxs-lookup"><span data-stu-id="52070-145">String</span></span> |  <span data-ttu-id="52070-146">Описание индикатора.</span><span class="sxs-lookup"><span data-stu-id="52070-146">Description of the indicator.</span></span> <span data-ttu-id="52070-147">**Required**</span><span class="sxs-lookup"><span data-stu-id="52070-147">**Required**</span></span>
<span data-ttu-id="52070-148">expirationTime</span><span class="sxs-lookup"><span data-stu-id="52070-148">expirationTime</span></span> | <span data-ttu-id="52070-149">DateTimeOffset</span><span class="sxs-lookup"><span data-stu-id="52070-149">DateTimeOffset</span></span> | <span data-ttu-id="52070-150">Срок действия индикатора в следующем формате YYYY-MM-DDTHH:MM:SS.0Z.</span><span class="sxs-lookup"><span data-stu-id="52070-150">The expiration time of the indicator in the following format YYYY-MM-DDTHH:MM:SS.0Z.</span></span> <span data-ttu-id="52070-151">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="52070-151">**Optional**</span></span>
<span data-ttu-id="52070-152">severity</span><span class="sxs-lookup"><span data-stu-id="52070-152">severity</span></span> | <span data-ttu-id="52070-153">Перечисление</span><span class="sxs-lookup"><span data-stu-id="52070-153">Enum</span></span> | <span data-ttu-id="52070-154">Серьезность индикатора.</span><span class="sxs-lookup"><span data-stu-id="52070-154">The severity of the indicator.</span></span> <span data-ttu-id="52070-155">Возможные значения: "Информационная", "Низкая", "Средняя" и "Высокая".</span><span class="sxs-lookup"><span data-stu-id="52070-155">Possible values are: "Informational", "Low", "Medium" and "High".</span></span> <span data-ttu-id="52070-156">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="52070-156">**Optional**</span></span>
<span data-ttu-id="52070-157">recommendedActions</span><span class="sxs-lookup"><span data-stu-id="52070-157">recommendedActions</span></span> | <span data-ttu-id="52070-158">String</span><span class="sxs-lookup"><span data-stu-id="52070-158">String</span></span> | <span data-ttu-id="52070-159">Предупреждение индикатора TI рекомендуемые действия.</span><span class="sxs-lookup"><span data-stu-id="52070-159">TI indicator alert recommended actions.</span></span> <span data-ttu-id="52070-160">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="52070-160">**Optional**</span></span>
<span data-ttu-id="52070-161">rbacGroupNames</span><span class="sxs-lookup"><span data-stu-id="52070-161">rbacGroupNames</span></span> | <span data-ttu-id="52070-162">String</span><span class="sxs-lookup"><span data-stu-id="52070-162">String</span></span> | <span data-ttu-id="52070-163">Разделенный запятой список имен групп RBAC, к который будет применен индикатор.</span><span class="sxs-lookup"><span data-stu-id="52070-163">Comma-separated list of RBAC group names the indicator would be applied to.</span></span> <span data-ttu-id="52070-164">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="52070-164">**Optional**</span></span>
<span data-ttu-id="52070-165">category</span><span class="sxs-lookup"><span data-stu-id="52070-165">category</span></span> | <span data-ttu-id="52070-166">String</span><span class="sxs-lookup"><span data-stu-id="52070-166">String</span></span> | <span data-ttu-id="52070-167">Категория оповещения.</span><span class="sxs-lookup"><span data-stu-id="52070-167">Category of the alert.</span></span> <span data-ttu-id="52070-168">Примеры: выполнение и доступ к учетным данным.</span><span class="sxs-lookup"><span data-stu-id="52070-168">Examples include: Execution and credential access.</span></span> <span data-ttu-id="52070-169">**Необязательное**</span><span class="sxs-lookup"><span data-stu-id="52070-169">**Optional**</span></span>
<span data-ttu-id="52070-170">mitretechniques</span><span class="sxs-lookup"><span data-stu-id="52070-170">mitretechniques</span></span>| <span data-ttu-id="52070-171">String</span><span class="sxs-lookup"><span data-stu-id="52070-171">String</span></span> | <span data-ttu-id="52070-172">Методы MITRE code/id (разделенная запятая).</span><span class="sxs-lookup"><span data-stu-id="52070-172">MITRE techniques code/id (comma separated).</span></span> <span data-ttu-id="52070-173">Дополнительные сведения см. [в Enterprise тактике.](https://attack.mitre.org/tactics/enterprise/)</span><span class="sxs-lookup"><span data-stu-id="52070-173">For more information, see [Enterprise tactics](https://attack.mitre.org/tactics/enterprise/).</span></span> <span data-ttu-id="52070-174">**Необязательный** Рекомендуется добавлять значение в категории при приеме MITRE.</span><span class="sxs-lookup"><span data-stu-id="52070-174">**Optional** It is recommended to add a value in category when a MITRE technique.</span></span>

<span data-ttu-id="52070-175">Дополнительные сведения см. в [рубрике Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!.](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748)</span><span class="sxs-lookup"><span data-stu-id="52070-175">For more information, see [Microsoft Defender for Endpoint alert categories are now aligned with MITRE ATT&CK!](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/microsoft-defender-atp-alert-categories-are-now-aligned-with/ba-p/732748).</span></span>


## <a name="see-also"></a><span data-ttu-id="52070-176">См. также</span><span class="sxs-lookup"><span data-stu-id="52070-176">See also</span></span>
- [<span data-ttu-id="52070-177">Создание индикаторов</span><span class="sxs-lookup"><span data-stu-id="52070-177">Create indicators</span></span>](manage-indicators.md)
- [<span data-ttu-id="52070-178">Создание индикаторов для файлов</span><span class="sxs-lookup"><span data-stu-id="52070-178">Create indicators for files</span></span>](indicator-file.md)
- [<span data-ttu-id="52070-179">Создание индикаторов для протоколов IP и URL-адресов или доменов</span><span class="sxs-lookup"><span data-stu-id="52070-179">Create indicators for IPs and URLs/domains</span></span>](indicator-ip-domain.md)
- [<span data-ttu-id="52070-180">Создание индикаторов на основе сертификатов</span><span class="sxs-lookup"><span data-stu-id="52070-180">Create indicators based on certificates</span></span>](indicator-certificates.md)
