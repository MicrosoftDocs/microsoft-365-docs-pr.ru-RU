---
title: Просмотр событий и ошибок с помощью viewer событий
description: Получите описания и дополнительные действия по устранению неполадок (если это необходимо) для всех событий, о чем сообщает служба Microsoft Defender для конечных точек.
keywords: устранение неполадок, просмотр событий, сводка журналов, сбой кода, сбой, служба Microsoft Defender для конечных точек, не может запускаться, нарушаться, не может начаться
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
ms.date: 05/21/2018
ms.technology: mde
ms.openlocfilehash: 98c0f790c228989b261b95f3b87cdc9d18e4fa76
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51076621"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="792a9-104">Просмотр событий и ошибок с помощью viewer событий</span><span class="sxs-lookup"><span data-stu-id="792a9-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="792a9-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="792a9-105">**Applies to:**</span></span>
- <span data-ttu-id="792a9-106">Средство просмотра событий</span><span class="sxs-lookup"><span data-stu-id="792a9-106">Event Viewer</span></span>
- [<span data-ttu-id="792a9-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="792a9-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="792a9-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="792a9-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="792a9-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="792a9-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="792a9-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="792a9-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="792a9-111">Вы можете просмотреть ID событий в [средстве просмотра событий](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) на отдельных устройствах.</span><span class="sxs-lookup"><span data-stu-id="792a9-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="792a9-112">Например, если устройства не отображаются в списке **Устройств,** может потребоваться искать ИД событий на устройствах.</span><span class="sxs-lookup"><span data-stu-id="792a9-112">For example, if devices are not appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="792a9-113">Затем можно использовать эту таблицу для определения дальнейших действий по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="792a9-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="792a9-114">**Откройте для просмотра событий и найдите журнал событий службы Microsoft Defender для конечных точек:**</span><span class="sxs-lookup"><span data-stu-id="792a9-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="792a9-115">Нажмите **кнопку Пуск** в меню Windows, введите **viewer событий** и нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="792a9-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="792a9-116">В списке журнала в **статье Сводка журнала** прокрутите до тех пор, пока не увидите **Microsoft-Windows-SENSE/Operational.**</span><span class="sxs-lookup"><span data-stu-id="792a9-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="792a9-117">Дважды щелкните элемент, чтобы открыть журнал.</span><span class="sxs-lookup"><span data-stu-id="792a9-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="792a9-118">а)</span><span class="sxs-lookup"><span data-stu-id="792a9-118">a.</span></span>  <span data-ttu-id="792a9-119">Вы также можете получить доступ к журналу, расширяя журналы приложений и служб Microsoft Windows SENSE и нажмите  >    >    >   кнопку **Оперативный**.</span><span class="sxs-lookup"><span data-stu-id="792a9-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="792a9-120">SENSE — это внутреннее имя, используемое для обозначения поведенческого датчика, который работает с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="792a9-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="792a9-121">События, записанные службой, будут отображаться в журнале.</span><span class="sxs-lookup"><span data-stu-id="792a9-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="792a9-122">Список событий, записанных службой, см. в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="792a9-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="792a9-123">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="792a9-123">Event ID</span></span></th>
<th><span data-ttu-id="792a9-124">Сообщение</span><span class="sxs-lookup"><span data-stu-id="792a9-124">Message</span></span></th>
<th><span data-ttu-id="792a9-125">Описание</span><span class="sxs-lookup"><span data-stu-id="792a9-125">Description</span></span></th>
<th><span data-ttu-id="792a9-126">Действие</span><span class="sxs-lookup"><span data-stu-id="792a9-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="792a9-127">1</span><span class="sxs-lookup"><span data-stu-id="792a9-127">1</span></span></td>
<td><span data-ttu-id="792a9-128">Запущена служба Microsoft Defender для конечной точки <code>variable</code> (Версия).</span><span class="sxs-lookup"><span data-stu-id="792a9-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="792a9-129">Происходит во время запуска системы, отключения и при включаемом в систему.</span><span class="sxs-lookup"><span data-stu-id="792a9-129">Occurs during system start up, shut down, and during onbboarding.</span></span></td>
<td><span data-ttu-id="792a9-130">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-131">2</span><span class="sxs-lookup"><span data-stu-id="792a9-131">2</span></span></td>
<td><span data-ttu-id="792a9-132">Отключение службы Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="792a9-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="792a9-133">Происходит, когда устройство отключено или отключено.</span><span class="sxs-lookup"><span data-stu-id="792a9-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="792a9-134">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-135">3</span><span class="sxs-lookup"><span data-stu-id="792a9-135">3</span></span></td>
<td><span data-ttu-id="792a9-136">Не удалось запустить службу Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="792a9-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="792a9-137">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-138">Служба не началась.</span><span class="sxs-lookup"><span data-stu-id="792a9-138">Service did not start.</span></span></td>
<td><span data-ttu-id="792a9-139">Просмотрите другие сообщения, чтобы определить возможные действия по устранению причин и неполадок.</span><span class="sxs-lookup"><span data-stu-id="792a9-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-140">4 </span><span class="sxs-lookup"><span data-stu-id="792a9-140">4</span></span></td>
<td><span data-ttu-id="792a9-141">Служба Microsoft Defender для конечной точки связалась с сервером в <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-142">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="792a9-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="792a9-143">Этот URL-адрес будет совпадать с тем, что видно в брандмауэре или сетевой активности.</span><span class="sxs-lookup"><span data-stu-id="792a9-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="792a9-144">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-145">5 </span><span class="sxs-lookup"><span data-stu-id="792a9-145">5</span></span></td>
<td><span data-ttu-id="792a9-146">Служба Microsoft Defender для конечных точек не смогла подключиться к серверу по <code>variable</code> данным .</span><span class="sxs-lookup"><span data-stu-id="792a9-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-147">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="792a9-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="792a9-148">Служба не могла связаться с внешними серверами обработки по этому URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="792a9-148">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="792a9-149">Проверьте подключение к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="792a9-149">Check the connection to the URL.</span></span> <span data-ttu-id="792a9-150">См. <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">в перенастройке прокси-серверов и подключения к Интернету.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-151">6 </span><span class="sxs-lookup"><span data-stu-id="792a9-151">6</span></span></td>
<td><span data-ttu-id="792a9-152">Служба Microsoft Defender для конечной точки не установлена на борт, и параметры бортового параметров не найдены.</span><span class="sxs-lookup"><span data-stu-id="792a9-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="792a9-153">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="792a9-153">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="792a9-154">Перед запуском службы необходимо запустить бортовую службу.</span><span class="sxs-lookup"><span data-stu-id="792a9-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="792a9-155">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-156">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-157">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-158">7 </span><span class="sxs-lookup"><span data-stu-id="792a9-158">7</span></span></td>
<td><span data-ttu-id="792a9-159">Служба Microsoft Defender для конечной точки не считыла параметры бортовой записи.</span><span class="sxs-lookup"><span data-stu-id="792a9-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="792a9-160">Сбой: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-161">Переменная = подробное описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="792a9-161">Variable = detailed error description.</span></span> <span data-ttu-id="792a9-162">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="792a9-162">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="792a9-163">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-164">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-165">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-166">8 </span><span class="sxs-lookup"><span data-stu-id="792a9-166">8</span></span></td>
<td><span data-ttu-id="792a9-167">Служба Microsoft Defender для конечной точки не смогла очистить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="792a9-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="792a9-168">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-169"><b>Во время бортового октагона:</b> Службе не удалось очистить конфигурацию во время бортовой работы.</span><span class="sxs-lookup"><span data-stu-id="792a9-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="792a9-170">Процесс вмеяния продолжается.</span><span class="sxs-lookup"><span data-stu-id="792a9-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="792a9-171"><b>Во время offboarding:</b> Служба не смогла очистить конфигурацию во время отключения.</span><span class="sxs-lookup"><span data-stu-id="792a9-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="792a9-172">Процесс offboarding завершен, но служба продолжает работать.</span><span class="sxs-lookup"><span data-stu-id="792a9-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="792a9-173"><b>Onboarding:</b> Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="792a9-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="792a9-174"><b>Offboarding:</b> Перезагрузка системы.</span><span class="sxs-lookup"><span data-stu-id="792a9-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="792a9-175">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-176">9 </span><span class="sxs-lookup"><span data-stu-id="792a9-176">9</span></span></td>
<td><span data-ttu-id="792a9-177">Служба Microsoft Defender для конечной точки не смогла изменить тип запуска.</span><span class="sxs-lookup"><span data-stu-id="792a9-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="792a9-178">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-179"><b>Во время бортового октагона:</b> Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="792a9-179"><b>During onboarding:</b> The device did not onboard correctly and will not be reporting to the portal.</span></span> <br><br><span data-ttu-id="792a9-180"><b>Во время offboarding:</b> Не удалось изменить тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="792a9-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="792a9-181">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="792a9-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="792a9-182">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-183">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-184">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-185">10 </span><span class="sxs-lookup"><span data-stu-id="792a9-185">10</span></span></td>
<td><span data-ttu-id="792a9-186">Служба Microsoft Defender для конечных точек не смогла сохранить сведения о взимаемой информации.</span><span class="sxs-lookup"><span data-stu-id="792a9-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="792a9-187">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-188">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="792a9-188">The device did not onboard correctly and will not be reporting to the portal.</span></span></td>
<td><span data-ttu-id="792a9-189">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-190">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-191">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-192">11</span><span class="sxs-lookup"><span data-stu-id="792a9-192">11</span></span></td>
<td><span data-ttu-id="792a9-193">Заполнена или выполнена перенастройка службы Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="792a9-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="792a9-194">Устройство правильно вошел в борт.</span><span class="sxs-lookup"><span data-stu-id="792a9-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="792a9-195">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="792a9-196">Для появления устройства на портале может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="792a9-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-197">12 </span><span class="sxs-lookup"><span data-stu-id="792a9-197">12</span></span></td>
<td><span data-ttu-id="792a9-198">Microsoft Defender для конечной точки не смог применить конфигурацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="792a9-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="792a9-199">Служба не смогла применить конфигурацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="792a9-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="792a9-200">Эта ошибка должна устраниться после короткого периода времени.</span><span class="sxs-lookup"><span data-stu-id="792a9-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-201">13</span><span class="sxs-lookup"><span data-stu-id="792a9-201">13</span></span></td>
<td><span data-ttu-id="792a9-202">Вычисляется ID устройства Microsoft Defender для конечных точек: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-203">Нормальный операционный процесс.</span><span class="sxs-lookup"><span data-stu-id="792a9-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="792a9-204">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-205">15 </span><span class="sxs-lookup"><span data-stu-id="792a9-205">15</span></span></td>
<td><span data-ttu-id="792a9-206">Microsoft Defender для конечной точки не может запустить командный канал с URL-адресом: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-207">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="792a9-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="792a9-208">Служба не могла связаться с внешними серверами обработки по этому URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="792a9-208">The service could not contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="792a9-209">Проверьте подключение к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="792a9-209">Check the connection to the URL.</span></span> <span data-ttu-id="792a9-210">См. <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">в перенастройке прокси-серверов и подключения к Интернету.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-211">17 </span><span class="sxs-lookup"><span data-stu-id="792a9-211">17</span></span></td>
<td><span data-ttu-id="792a9-212">Служба Microsoft Defender для конечных точек не смогла изменить расположение службы подключенных пользователей и службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="792a9-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="792a9-213">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-214">Ошибка произошла в службе телеметрии Windows.</span><span class="sxs-lookup"><span data-stu-id="792a9-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="792a9-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="792a9-216">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-217">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-218">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-219">18 </span><span class="sxs-lookup"><span data-stu-id="792a9-219">18</span></span></td>
<td><span data-ttu-id="792a9-220">OOBE (Добро пожаловать в Windows) завершено.</span><span class="sxs-lookup"><span data-stu-id="792a9-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="792a9-221">Служба начнется только после завершения установки обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="792a9-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="792a9-222">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-223">19</span><span class="sxs-lookup"><span data-stu-id="792a9-223">19</span></span></td>
<td><span data-ttu-id="792a9-224">OOBE (Windows Welcome) еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="792a9-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="792a9-225">Служба начнется только после завершения установки обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="792a9-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="792a9-226">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="792a9-227">Если эта ошибка сохраняется после перезапуска системы, убедитесь, что все обновления Windows установлены полностью.</span><span class="sxs-lookup"><span data-stu-id="792a9-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-228">20</span><span class="sxs-lookup"><span data-stu-id="792a9-228">20</span></span></td>
<td><span data-ttu-id="792a9-229">Не удается дождаться завершения OOBE (Windows Welcome).</span><span class="sxs-lookup"><span data-stu-id="792a9-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="792a9-230">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-231">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="792a9-231">Internal error.</span></span></td>
<td><span data-ttu-id="792a9-232">Если эта ошибка сохраняется после перезапуска системы, убедитесь, что все обновления Windows установлены полностью.</span><span class="sxs-lookup"><span data-stu-id="792a9-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-233">25</span><span class="sxs-lookup"><span data-stu-id="792a9-233">25</span></span></td>
<td><span data-ttu-id="792a9-234">Службе Microsoft Defender для конечных точек не удалось сбросить состояние здоровья в реестре.</span><span class="sxs-lookup"><span data-stu-id="792a9-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="792a9-235">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-236">Устройство не было правильно на борту.</span><span class="sxs-lookup"><span data-stu-id="792a9-236">The device did not onboard correctly.</span></span>
<span data-ttu-id="792a9-237">Он будет сообщать на портал, однако служба не может отображаться как зарегистрированная в SCCM или реестре.</span><span class="sxs-lookup"><span data-stu-id="792a9-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="792a9-238">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-239">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-240">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-241">26</span><span class="sxs-lookup"><span data-stu-id="792a9-241">26</span></span></td>
<td><span data-ttu-id="792a9-242">Службе Microsoft Defender для конечных точек не удалось установить в реестре состояние onboarding.</span><span class="sxs-lookup"><span data-stu-id="792a9-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="792a9-243">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-244">Устройство не было правильно на борту.</span><span class="sxs-lookup"><span data-stu-id="792a9-244">The device did not onboard correctly.</span></span><br>
<span data-ttu-id="792a9-245">Он будет сообщать на портал, однако служба не может отображаться как зарегистрированная в SCCM или реестре.</span><span class="sxs-lookup"><span data-stu-id="792a9-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="792a9-246">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-247">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-248">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-249">27</span><span class="sxs-lookup"><span data-stu-id="792a9-249">27</span></span></td>
<td><span data-ttu-id="792a9-250">Служба Microsoft Defender для конечной точки не смогла включить режим sense в антивирусе Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="792a9-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="792a9-251">Сбой в процессе onboarding.</span><span class="sxs-lookup"><span data-stu-id="792a9-251">Onboarding process failed.</span></span> <span data-ttu-id="792a9-252">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-253">Обычно антивирус Microsoft Defender вступает в специальное пассивное состояние, если на устройстве правильно работает другой антивирусный продукт в режиме реального времени, а устройство сообщается в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="792a9-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="792a9-254">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-255">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-256">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="792a9-257">Убедитесь, что защита от антивирусных программ в режиме реального времени работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-258">28</span><span class="sxs-lookup"><span data-stu-id="792a9-258">28</span></span></td>
<td><span data-ttu-id="792a9-259">В Microsoft Defender для подключенных к конечной точке пользовательских интерфейсов и регистрации службы телеметрии не удалось.</span><span class="sxs-lookup"><span data-stu-id="792a9-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="792a9-260">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-261">Ошибка произошла в службе телеметрии Windows.</span><span class="sxs-lookup"><span data-stu-id="792a9-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="792a9-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="792a9-263">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-264">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-265">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-266">29</span><span class="sxs-lookup"><span data-stu-id="792a9-266">29</span></span></td>
<td><span data-ttu-id="792a9-267">Не удалось прочитать параметры offboarding.</span><span class="sxs-lookup"><span data-stu-id="792a9-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="792a9-268">Тип ошибки: %1, код ошибки: %2, Описание: %3</span><span class="sxs-lookup"><span data-stu-id="792a9-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="792a9-269">Это событие происходит, когда система может&#39;не читать параметры offboarding.</span><span class="sxs-lookup"><span data-stu-id="792a9-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="792a9-270">Убедитесь, что устройство имеет доступ к Интернету, затем запустите весь процесс offboarding снова.</span><span class="sxs-lookup"><span data-stu-id="792a9-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="792a9-271">Убедитесь, что срок действия пакета offboarding не истек.</span><span class="sxs-lookup"><span data-stu-id="792a9-271">Ensure the offboarding package has not expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-272">30</span><span class="sxs-lookup"><span data-stu-id="792a9-272">30</span></span></td>
<td><span data-ttu-id="792a9-273">Службе Microsoft Defender для конечных точек не удалось отключить режим зная SENSE в антивирусе Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="792a9-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="792a9-274">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-275">Обычно антивирус Microsoft Defender вступает в специальное пассивное состояние, если на устройстве правильно работает другой антивирусный продукт в режиме реального времени, а устройство сообщается в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="792a9-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="792a9-276">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-277">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-278">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте устройств с Windows 10</a></span><span class="sxs-lookup"><span data-stu-id="792a9-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="792a9-279">Убедитесь, что защита от антивирусных программ в режиме реального времени работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-280">31</span><span class="sxs-lookup"><span data-stu-id="792a9-280">31</span></span></td>
<td><span data-ttu-id="792a9-281">Сбой в работе Microsoft Defender для подключенных к конечным точкам пользователей и регистрации службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="792a9-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="792a9-282">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-283">Ошибка произошла в службе телеметрии Windows во время бортовой работы.</span><span class="sxs-lookup"><span data-stu-id="792a9-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="792a9-284">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="792a9-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="792a9-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Проверьте ошибки в службе телеметрии Windows.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-286">32</span><span class="sxs-lookup"><span data-stu-id="792a9-286">32</span></span></td>
<td><span data-ttu-id="792a9-287">Служба Microsoft Defender для конечных точек не смогла попросить остановиться после процесса offboarding.</span><span class="sxs-lookup"><span data-stu-id="792a9-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="792a9-288">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="792a9-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="792a9-289">Ошибка произошла во время offboarding.</span><span class="sxs-lookup"><span data-stu-id="792a9-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="792a9-290">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="792a9-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-291">33</span><span class="sxs-lookup"><span data-stu-id="792a9-291">33</span></span></td>
<td><span data-ttu-id="792a9-292">Служба Microsoft Defender для конечной точки не смогла сохранить GUID SENSE.</span><span class="sxs-lookup"><span data-stu-id="792a9-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="792a9-293">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-294">Уникальный идентификатор используется для представления каждого устройства, отчитывающееся на портале.</span><span class="sxs-lookup"><span data-stu-id="792a9-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="792a9-295">Если идентификатор не сохраняется, то одно и то же устройство может дважды отображаться на портале.</span><span class="sxs-lookup"><span data-stu-id="792a9-295">If the identifier does not persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="792a9-296">Проверьте разрешения реестра на устройстве, чтобы убедиться, что служба может обновлять реестр.</span><span class="sxs-lookup"><span data-stu-id="792a9-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-297">34</span><span class="sxs-lookup"><span data-stu-id="792a9-297">34</span></span></td>
<td><span data-ttu-id="792a9-298">Служба Microsoft Defender для конечных точек не смогла добавить себя в зависимость от службы подключенных пользователей и службы телеметрии, из-за чего процесс подключения не удалось.</span><span class="sxs-lookup"><span data-stu-id="792a9-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="792a9-299">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-300">Ошибка произошла в службе телеметрии Windows.</span><span class="sxs-lookup"><span data-stu-id="792a9-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="792a9-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="792a9-302">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="792a9-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="792a9-303">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="792a9-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="792a9-304">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="792a9-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-305">35</span><span class="sxs-lookup"><span data-stu-id="792a9-305">35</span></span></td>
<td><span data-ttu-id="792a9-306">Служба Microsoft Defender для конечных точек не смогла удалить себя в качестве зависимости от службы подключенных пользователей и службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="792a9-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="792a9-307">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-308">В службе телеметрии Windows во время отключения произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="792a9-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="792a9-309">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="792a9-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="792a9-310">Проверьте ошибки в службе диагностических данных Windows.</span><span class="sxs-lookup"><span data-stu-id="792a9-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-311">36</span><span class="sxs-lookup"><span data-stu-id="792a9-311">36</span></span></td>
<td><span data-ttu-id="792a9-312">Microsoft Defender для подключенных к конечной точке пользователей и регистрации службы телеметрии успешно.</span><span class="sxs-lookup"><span data-stu-id="792a9-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="792a9-313">Код завершения: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="792a9-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="792a9-314">Успешно завершена регистрация Defender для конечной точки с помощью службы подключенных пользователей и телеметрии.</span><span class="sxs-lookup"><span data-stu-id="792a9-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="792a9-315">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-316">37</span><span class="sxs-lookup"><span data-stu-id="792a9-316">37</span></span></td>
<td><span data-ttu-id="792a9-317">Модуль Microsoft Defender для конечной точки A будет превышать квоту.</span><span class="sxs-lookup"><span data-stu-id="792a9-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="792a9-318">Модуль: %1, Квота: {%2} {%3}, Процент использования квот: %4.</span><span class="sxs-lookup"><span data-stu-id="792a9-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="792a9-319">Устройство почти использовало выделенную квоту текущего 24-часового окна.</span><span class="sxs-lookup"><span data-stu-id="792a9-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="792a9-320">Его вот-вот перенабьют.</span><span class="sxs-lookup"><span data-stu-id="792a9-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="792a9-321">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-322">38</span><span class="sxs-lookup"><span data-stu-id="792a9-322">38</span></span></td>
<td><span data-ttu-id="792a9-323">Подключение к сети определено как низкое.</span><span class="sxs-lookup"><span data-stu-id="792a9-323">Network connection is identified as low.</span></span> <span data-ttu-id="792a9-324">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="792a9-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="792a9-325">Дозное подключение: %2, доступ к Интернету: %3, доступная бесплатная сеть: %4.</span><span class="sxs-lookup"><span data-stu-id="792a9-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="792a9-326">Устройство использует дозную/платную сеть и будет реже обращаться к серверу.</span><span class="sxs-lookup"><span data-stu-id="792a9-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="792a9-327">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-328">39</span><span class="sxs-lookup"><span data-stu-id="792a9-328">39</span></span></td>
<td><span data-ttu-id="792a9-329">Подключение к сети определено как обычное.</span><span class="sxs-lookup"><span data-stu-id="792a9-329">Network connection is identified as normal.</span></span> <span data-ttu-id="792a9-330">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="792a9-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="792a9-331">Дозное подключение: %2, доступ к Интернету: %3, доступная бесплатная сеть: %4.</span><span class="sxs-lookup"><span data-stu-id="792a9-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="792a9-332">Устройство не использует дозное/платное подключение и будет связываться с сервером в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="792a9-332">The device is not using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="792a9-333">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-334">40</span><span class="sxs-lookup"><span data-stu-id="792a9-334">40</span></span></td>
<td><span data-ttu-id="792a9-335">Состояние батареи определено как низкое.</span><span class="sxs-lookup"><span data-stu-id="792a9-335">Battery state is identified as low.</span></span> <span data-ttu-id="792a9-336">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="792a9-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="792a9-337">Состояние батареи: %2.</span><span class="sxs-lookup"><span data-stu-id="792a9-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="792a9-338">Устройство имеет низкий уровень батареи и реже контактировать с сервером.</span><span class="sxs-lookup"><span data-stu-id="792a9-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="792a9-339">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-340">41</span><span class="sxs-lookup"><span data-stu-id="792a9-340">41</span></span></td>
<td><span data-ttu-id="792a9-341">Состояние батареи определено как нормальное.</span><span class="sxs-lookup"><span data-stu-id="792a9-341">Battery state is identified as normal.</span></span> <span data-ttu-id="792a9-342">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="792a9-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="792a9-343">Состояние батареи: %2.</span><span class="sxs-lookup"><span data-stu-id="792a9-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="792a9-344">Устройство не имеет низкого уровня батареи и будет связываться с сервером, как обычно.</span><span class="sxs-lookup"><span data-stu-id="792a9-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="792a9-345">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-346">42</span><span class="sxs-lookup"><span data-stu-id="792a9-346">42</span></span></td>
<td><span data-ttu-id="792a9-347">Компонент Microsoft Defender для конечной точки WDATP не выполнил действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-347">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="792a9-348">Компонент: %1, Действие: %2, Тип исключения: %3, Сообщение об исключении: %4</span><span class="sxs-lookup"><span data-stu-id="792a9-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="792a9-349">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="792a9-349">Internal error.</span></span> <span data-ttu-id="792a9-350">Не удалось запустить службу.</span><span class="sxs-lookup"><span data-stu-id="792a9-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="792a9-351">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="792a9-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-352">43</span><span class="sxs-lookup"><span data-stu-id="792a9-352">43</span></span></td>
<td><span data-ttu-id="792a9-353">Компонент Microsoft Defender для конечной точки WDATP не выполнил действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-353">Microsoft Defender for Endpoint WDATP component failed to perform action.</span></span> <span data-ttu-id="792a9-354">Компонент: %1, Действие: %2, Тип исключения: %3, Ошибка исключения: %4, Сообщение об исключении: %5</span><span class="sxs-lookup"><span data-stu-id="792a9-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="792a9-355">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="792a9-355">Internal error.</span></span> <span data-ttu-id="792a9-356">Не удалось запустить службу.</span><span class="sxs-lookup"><span data-stu-id="792a9-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="792a9-357">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="792a9-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-358">44</span><span class="sxs-lookup"><span data-stu-id="792a9-358">44</span></span></td>
<td><span data-ttu-id="792a9-359">Отключение службы Defender для конечной точки завершено.</span><span class="sxs-lookup"><span data-stu-id="792a9-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="792a9-360">Служба была отключена.</span><span class="sxs-lookup"><span data-stu-id="792a9-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="792a9-361">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-362">45</span><span class="sxs-lookup"><span data-stu-id="792a9-362">45</span></span></td>
<td><span data-ttu-id="792a9-363">Не удалось зарегистрировать и запустить сеанс трассировки событий [%1].</span><span class="sxs-lookup"><span data-stu-id="792a9-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="792a9-364">Код ошибки: %2</span><span class="sxs-lookup"><span data-stu-id="792a9-364">Error code: %2</span></span></td>
<td><span data-ttu-id="792a9-365">Ошибка произошла при запуске службы при создании сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="792a9-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="792a9-366">Это привело к сбою запуска службы.</span><span class="sxs-lookup"><span data-stu-id="792a9-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="792a9-367">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="792a9-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-368">46</span><span class="sxs-lookup"><span data-stu-id="792a9-368">46</span></span></td>
<td><span data-ttu-id="792a9-369">Не удалось зарегистрировать и запустить сеанс трассировки событий [%1] из-за нехватки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="792a9-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="792a9-370">Код ошибки: %2.</span><span class="sxs-lookup"><span data-stu-id="792a9-370">Error code: %2.</span></span> <span data-ttu-id="792a9-371">Это, скорее всего, потому, что существует слишком много активных сеансов трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="792a9-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="792a9-372">Служба будет повторить в течение 1 минуты.</span><span class="sxs-lookup"><span data-stu-id="792a9-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="792a9-373">Ошибка произошла при запуске службы при создании сеанса ETW из-за нехватки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="792a9-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="792a9-374">Служба запущена и запущена, но не будет сообщать о событии датчика до начала сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="792a9-374">The service started and is running, but will not report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="792a9-375">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="792a9-376">Служба будет пытаться начинать сеанс каждую минуту.</span><span class="sxs-lookup"><span data-stu-id="792a9-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-377">47</span><span class="sxs-lookup"><span data-stu-id="792a9-377">47</span></span></td>
<td><span data-ttu-id="792a9-378">Успешно зарегистрировался и начал сеанс трассировки событий , восстановленный после предыдущих неудачных попыток.</span><span class="sxs-lookup"><span data-stu-id="792a9-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="792a9-379">Это событие следует за предыдущим событием после успешного начала сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="792a9-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="792a9-380">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="792a9-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="792a9-381">48</span><span class="sxs-lookup"><span data-stu-id="792a9-381">48</span></span></td>
<td><span data-ttu-id="792a9-382">Не удалось добавить поставщика [%1] в сеанс трассировки событий [%2].</span><span class="sxs-lookup"><span data-stu-id="792a9-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="792a9-383">Код ошибки: %3.</span><span class="sxs-lookup"><span data-stu-id="792a9-383">Error code: %3.</span></span> <span data-ttu-id="792a9-384">Это означает, что события от этого поставщика не будут отчитаться.</span><span class="sxs-lookup"><span data-stu-id="792a9-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="792a9-385">Не удалось добавить поставщика в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="792a9-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="792a9-386">В результате события поставщика не сообщаются.</span><span class="sxs-lookup"><span data-stu-id="792a9-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="792a9-387">Проверьте код ошибки.</span><span class="sxs-lookup"><span data-stu-id="792a9-387">Check the error code.</span></span> <span data-ttu-id="792a9-388">Если ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="792a9-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
</tbody>
</table>

><span data-ttu-id="792a9-389">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="792a9-389">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="792a9-390">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="792a9-390">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="792a9-391">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="792a9-391">Related topics</span></span>
- [<span data-ttu-id="792a9-392">На борту устройств с Windows 10</span><span class="sxs-lookup"><span data-stu-id="792a9-392">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="792a9-393">Настройка параметров прокси-сервера устройства и подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="792a9-393">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="792a9-394">Устранение неполадок Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="792a9-394">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
