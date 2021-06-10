---
title: Просмотр событий и ошибок с помощью viewer событий
description: Получите описания и дополнительные действия по устранению неполадок (при необходимости) для всех событий, о чем сообщает служба Microsoft Defender для конечной точки.
keywords: устранение неполадок, просмотр событий, сводка журналов, сбой кода, сбой, служба Microsoft Defender для конечных точек, не может запускаться, не работает, не удается запустить
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
ms.openlocfilehash: a8b7268e89470a85a34015967b69abb1818fe64f
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933845"
---
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="218c4-104">Просмотр событий и ошибок с помощью viewer событий</span><span class="sxs-lookup"><span data-stu-id="218c4-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="218c4-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="218c4-105">**Applies to:**</span></span>
- <span data-ttu-id="218c4-106">Средство просмотра событий</span><span class="sxs-lookup"><span data-stu-id="218c4-106">Event Viewer</span></span>
- [<span data-ttu-id="218c4-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="218c4-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="218c4-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="218c4-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="218c4-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="218c4-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="218c4-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="218c4-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="218c4-111">Вы можете просмотреть ID событий в [средстве просмотра событий](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) на отдельных устройствах.</span><span class="sxs-lookup"><span data-stu-id="218c4-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="218c4-112">Например, если устройства не отображаются в списке **Устройств,** может потребоваться искать ИД событий на устройствах.</span><span class="sxs-lookup"><span data-stu-id="218c4-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="218c4-113">Затем можно использовать эту таблицу для определения дальнейших действий по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="218c4-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="218c4-114">**Откройте для просмотра событий и найдите журнал событий службы Microsoft Defender для конечных точек:**</span><span class="sxs-lookup"><span data-stu-id="218c4-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="218c4-115">Нажмите **кнопку** Пуск в меню Windows, введите **viewer событий** и нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="218c4-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="218c4-116">В списке журнала, в **статье Сводка** журнала, прокрутите до тех пор, пока не увидите **Microsoft-Windows-SENSE/Operational**.</span><span class="sxs-lookup"><span data-stu-id="218c4-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="218c4-117">Дважды щелкните элемент, чтобы открыть журнал.</span><span class="sxs-lookup"><span data-stu-id="218c4-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="218c4-118">а.</span><span class="sxs-lookup"><span data-stu-id="218c4-118">a.</span></span>  <span data-ttu-id="218c4-119">Вы также можете получить доступ к журналу, расширяя журналы приложений и служб Microsoft Windows SENSE и нажмите  >    >    >   кнопку **Оперативный**.</span><span class="sxs-lookup"><span data-stu-id="218c4-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="218c4-120">SENSE — это внутреннее имя, используемое для обозначения поведенческого датчика, который работает с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="218c4-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="218c4-121">События, записанные службой, будут отображаться в журнале.</span><span class="sxs-lookup"><span data-stu-id="218c4-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="218c4-122">Список событий, записанных службой, см. в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="218c4-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="218c4-123">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="218c4-123">Event ID</span></span></th>
<th><span data-ttu-id="218c4-124">Сообщение</span><span class="sxs-lookup"><span data-stu-id="218c4-124">Message</span></span></th>
<th><span data-ttu-id="218c4-125">Описание</span><span class="sxs-lookup"><span data-stu-id="218c4-125">Description</span></span></th>
<th><span data-ttu-id="218c4-126">Action</span><span class="sxs-lookup"><span data-stu-id="218c4-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="218c4-127">1</span><span class="sxs-lookup"><span data-stu-id="218c4-127">1</span></span></td>
<td><span data-ttu-id="218c4-128">Запущена служба Microsoft Defender для конечной точки <code>variable</code> (Версия).</span><span class="sxs-lookup"><span data-stu-id="218c4-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="218c4-129">Происходит во время запуска системы, отключения и во время включаемой.</span><span class="sxs-lookup"><span data-stu-id="218c4-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="218c4-130">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-131">2</span><span class="sxs-lookup"><span data-stu-id="218c4-131">2</span></span></td>
<td><span data-ttu-id="218c4-132">Отключение службы Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="218c4-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="218c4-133">Происходит, когда устройство отключено или отключено.</span><span class="sxs-lookup"><span data-stu-id="218c4-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="218c4-134">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-135">3</span><span class="sxs-lookup"><span data-stu-id="218c4-135">3</span></span></td>
<td><span data-ttu-id="218c4-136">Не удалось запустить службу Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="218c4-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="218c4-137">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-138">Служба не началась.</span><span class="sxs-lookup"><span data-stu-id="218c4-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="218c4-139">Просмотрите другие сообщения, чтобы определить возможные действия по устранению причин и неполадок.</span><span class="sxs-lookup"><span data-stu-id="218c4-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-140">4 </span><span class="sxs-lookup"><span data-stu-id="218c4-140">4</span></span></td>
<td><span data-ttu-id="218c4-141">Служба Microsoft Defender для конечной точки связалась с сервером в <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-142">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="218c4-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="218c4-143">Этот URL-адрес будет совпадать с тем, что видно в брандмауэре или сетевой активности.</span><span class="sxs-lookup"><span data-stu-id="218c4-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="218c4-144">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-145">5 </span><span class="sxs-lookup"><span data-stu-id="218c4-145">5</span></span></td>
<td><span data-ttu-id="218c4-146">Служба Microsoft Defender для конечных точек не смогла подключиться к серверу по <code>variable</code> данным .</span><span class="sxs-lookup"><span data-stu-id="218c4-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-147">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="218c4-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="218c4-148">Служба не смогла связаться с внешними серверами обработки по этому URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="218c4-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="218c4-149">Проверьте подключение к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="218c4-149">Check the connection to the URL.</span></span> <span data-ttu-id="218c4-150">См. <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">в перенастройке прокси-серверов и подключения к Интернету.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-151">6 </span><span class="sxs-lookup"><span data-stu-id="218c4-151">6</span></span></td>
<td><span data-ttu-id="218c4-152">Служба Microsoft Defender для конечной точки не установлена на борт, и параметры бортового параметров не найдены.</span><span class="sxs-lookup"><span data-stu-id="218c4-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="218c4-153">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="218c4-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="218c4-154">Перед запуском службы необходимо запустить бортовую службу.</span><span class="sxs-lookup"><span data-stu-id="218c4-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="218c4-155">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-156">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-157">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-158">7 </span><span class="sxs-lookup"><span data-stu-id="218c4-158">7</span></span></td>
<td><span data-ttu-id="218c4-159">Служба Microsoft Defender для конечной точки не считыла параметры бортовой записи.</span><span class="sxs-lookup"><span data-stu-id="218c4-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="218c4-160">Сбой: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-161">Переменная = подробное описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="218c4-161">Variable = detailed error description.</span></span> <span data-ttu-id="218c4-162">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="218c4-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="218c4-163">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-164">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-165">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-166">8 </span><span class="sxs-lookup"><span data-stu-id="218c4-166">8</span></span></td>
<td><span data-ttu-id="218c4-167">Служба Microsoft Defender для конечной точки не смогла очистить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="218c4-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="218c4-168">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-169"><b>Во время бортового октагона:</b> Службе не удалось очистить конфигурацию во время бортовой работы.</span><span class="sxs-lookup"><span data-stu-id="218c4-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="218c4-170">Процесс вмеяния продолжается.</span><span class="sxs-lookup"><span data-stu-id="218c4-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="218c4-171"><b>Во время offboarding:</b> Служба не смогла очистить конфигурацию во время отключения.</span><span class="sxs-lookup"><span data-stu-id="218c4-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="218c4-172">Процесс offboarding завершен, но служба продолжает работать.</span><span class="sxs-lookup"><span data-stu-id="218c4-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="218c4-173"><b>Onboarding:</b> Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="218c4-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="218c4-174"><b>Offboarding:</b> Перезагрузка системы.</span><span class="sxs-lookup"><span data-stu-id="218c4-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="218c4-175">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-176">9 </span><span class="sxs-lookup"><span data-stu-id="218c4-176">9</span></span></td>
<td><span data-ttu-id="218c4-177">Служба Microsoft Defender для конечной точки не смогла изменить тип запуска.</span><span class="sxs-lookup"><span data-stu-id="218c4-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="218c4-178">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-179"><b>Во время бортового октагона:</b> Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="218c4-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="218c4-180"><b>Во время offboarding:</b> Не удалось изменить тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="218c4-181">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="218c4-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="218c4-182">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-183">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-184">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-185">10 </span><span class="sxs-lookup"><span data-stu-id="218c4-185">10</span></span></td>
<td><span data-ttu-id="218c4-186">Служба Microsoft Defender для конечных точек не смогла сохранить сведения о взимаемой информации.</span><span class="sxs-lookup"><span data-stu-id="218c4-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="218c4-187">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-188">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="218c4-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="218c4-189">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-190">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-191">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-192">11</span><span class="sxs-lookup"><span data-stu-id="218c4-192">11</span></span></td>
<td><span data-ttu-id="218c4-193">Заполнена или выполнена перенастройка службы Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="218c4-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="218c4-194">Устройство правильно вошел в борт.</span><span class="sxs-lookup"><span data-stu-id="218c4-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="218c4-195">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="218c4-196">Для появления устройства на портале может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="218c4-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-197">12 </span><span class="sxs-lookup"><span data-stu-id="218c4-197">12</span></span></td>
<td><span data-ttu-id="218c4-198">Microsoft Defender для конечной точки не смог применить конфигурацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="218c4-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="218c4-199">Служба не смогла применить конфигурацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="218c4-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="218c4-200">Эта ошибка должна устраниться после короткого периода времени.</span><span class="sxs-lookup"><span data-stu-id="218c4-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-201">13</span><span class="sxs-lookup"><span data-stu-id="218c4-201">13</span></span></td>
<td><span data-ttu-id="218c4-202">Вычисляется ID устройства Microsoft Defender для конечных точек: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-203">Нормальный операционный процесс.</span><span class="sxs-lookup"><span data-stu-id="218c4-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="218c4-204">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-205">15</span><span class="sxs-lookup"><span data-stu-id="218c4-205">15</span></span></td>
<td><span data-ttu-id="218c4-206">Microsoft Defender для конечной точки не может запустить командный канал с URL-адресом: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-207">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="218c4-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="218c4-208">Служба не смогла связаться с внешними серверами обработки по этому URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="218c4-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="218c4-209">Проверьте подключение к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="218c4-209">Check the connection to the URL.</span></span> <span data-ttu-id="218c4-210">См. <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">в перенастройке прокси-серверов и подключения к Интернету.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-211">17 </span><span class="sxs-lookup"><span data-stu-id="218c4-211">17</span></span></td>
<td><span data-ttu-id="218c4-212">Служба Microsoft Defender для конечных точек не смогла изменить расположение службы подключенных пользователей и службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="218c4-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="218c4-213">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-214">Ошибка произошла в службе Windows телеметрии.</span><span class="sxs-lookup"><span data-stu-id="218c4-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="218c4-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="218c4-216">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-217">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-218">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-219">18 </span><span class="sxs-lookup"><span data-stu-id="218c4-219">18</span></span></td>
<td><span data-ttu-id="218c4-220">OOBE (Windows Welcome) завершен.</span><span class="sxs-lookup"><span data-stu-id="218c4-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="218c4-221">Служба начнется только после Windows после завершения установки обновлений.</span><span class="sxs-lookup"><span data-stu-id="218c4-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="218c4-222">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-223">19</span><span class="sxs-lookup"><span data-stu-id="218c4-223">19</span></span></td>
<td><span data-ttu-id="218c4-224">OOBE (Windows Welcome) еще не завершен.</span><span class="sxs-lookup"><span data-stu-id="218c4-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="218c4-225">Служба начнется только после Windows после завершения установки обновлений.</span><span class="sxs-lookup"><span data-stu-id="218c4-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="218c4-226">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="218c4-227">Если эта ошибка сохраняется после перезапуска системы, убедитесь, что Windows обновления полностью установлены.</span><span class="sxs-lookup"><span data-stu-id="218c4-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-228">20</span><span class="sxs-lookup"><span data-stu-id="218c4-228">20</span></span></td>
<td><span data-ttu-id="218c4-229">Не удается дождаться завершения OOBE (Windows Welcome).</span><span class="sxs-lookup"><span data-stu-id="218c4-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="218c4-230">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-231">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="218c4-231">Internal error.</span></span></td>
<td><span data-ttu-id="218c4-232">Если эта ошибка сохраняется после перезапуска системы, убедитесь, что Windows обновления полностью установлены.</span><span class="sxs-lookup"><span data-stu-id="218c4-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-233">25</span><span class="sxs-lookup"><span data-stu-id="218c4-233">25</span></span></td>
<td><span data-ttu-id="218c4-234">Службе Microsoft Defender для конечных точек не удалось сбросить состояние здоровья в реестре.</span><span class="sxs-lookup"><span data-stu-id="218c4-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="218c4-235">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-236">Устройство не было правильно на борту.</span><span class="sxs-lookup"><span data-stu-id="218c4-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="218c4-237">Он будет сообщать на портал, однако служба не может отображаться как зарегистрированная в SCCM или реестре.</span><span class="sxs-lookup"><span data-stu-id="218c4-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="218c4-238">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-239">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-240">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-241">26</span><span class="sxs-lookup"><span data-stu-id="218c4-241">26</span></span></td>
<td><span data-ttu-id="218c4-242">Службе Microsoft Defender для конечных точек не удалось установить в реестре состояние onboarding.</span><span class="sxs-lookup"><span data-stu-id="218c4-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="218c4-243">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-244">Устройство не было правильно на борту.</span><span class="sxs-lookup"><span data-stu-id="218c4-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="218c4-245">Он будет сообщать на портал, однако служба не может отображаться как зарегистрированная в SCCM или реестре.</span><span class="sxs-lookup"><span data-stu-id="218c4-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="218c4-246">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-247">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-248">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-249">27</span><span class="sxs-lookup"><span data-stu-id="218c4-249">27</span></span></td>
<td><span data-ttu-id="218c4-250">Служба Microsoft Defender для конечных точек не смогла включить режим sense aware в антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="218c4-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="218c4-251">Сбой в процессе onboarding.</span><span class="sxs-lookup"><span data-stu-id="218c4-251">Onboarding process failed.</span></span> <span data-ttu-id="218c4-252">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-253">Как правило, антивирусная программа в Microsoft Defender вступает в специальное пассивное состояние, если на устройстве правильно работает другой антивирусный продукт в режиме реального времени, и устройство сообщается в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="218c4-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="218c4-254">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-255">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-256">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="218c4-257">Убедитесь, что защита от антивирусных программ в режиме реального времени работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-258">28</span><span class="sxs-lookup"><span data-stu-id="218c4-258">28</span></span></td>
<td><span data-ttu-id="218c4-259">В Microsoft Defender для подключенных к конечной точке пользовательских интерфейсов и регистрации службы телеметрии не удалось.</span><span class="sxs-lookup"><span data-stu-id="218c4-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="218c4-260">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-261">Ошибка произошла в службе Windows телеметрии.</span><span class="sxs-lookup"><span data-stu-id="218c4-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="218c4-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="218c4-263">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-264">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-265">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-266">29</span><span class="sxs-lookup"><span data-stu-id="218c4-266">29</span></span></td>
<td><span data-ttu-id="218c4-267">Не удалось прочитать параметры offboarding.</span><span class="sxs-lookup"><span data-stu-id="218c4-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="218c4-268">Тип ошибки: %1, код ошибки: %2, Описание: %3</span><span class="sxs-lookup"><span data-stu-id="218c4-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="218c4-269">Это событие происходит, когда система может&#39;не читать параметры offboarding.</span><span class="sxs-lookup"><span data-stu-id="218c4-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="218c4-270">Убедитесь, что устройство имеет доступ к Интернету, затем запустите весь процесс offboarding снова.</span><span class="sxs-lookup"><span data-stu-id="218c4-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="218c4-271">Убедитесь, что срок действия пакета offboarding не истек.</span><span class="sxs-lookup"><span data-stu-id="218c4-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-272">30</span><span class="sxs-lookup"><span data-stu-id="218c4-272">30</span></span></td>
<td><span data-ttu-id="218c4-273">Служба Microsoft Defender для конечной точки не смогла отключить режим зная SENSE в антивирусная программа в Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="218c4-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="218c4-274">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-275">Как правило, антивирусная программа в Microsoft Defender вступает в специальное пассивное состояние, если на устройстве правильно работает другой антивирусный продукт в режиме реального времени, и устройство сообщается в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="218c4-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="218c4-276">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-277">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-278">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства</a></span><span class="sxs-lookup"><span data-stu-id="218c4-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="218c4-279">Убедитесь, что защита от антивирусных программ в режиме реального времени работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-280">31</span><span class="sxs-lookup"><span data-stu-id="218c4-280">31</span></span></td>
<td><span data-ttu-id="218c4-281">Сбой в работе Microsoft Defender для подключенных к конечным точкам пользователей и регистрации службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="218c4-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="218c4-282">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-283">Ошибка произошла в службе Windows телеметрии во время бортовой работы.</span><span class="sxs-lookup"><span data-stu-id="218c4-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="218c4-284">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="218c4-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="218c4-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Проверьте ошибки в службе Windows телеметрии.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-286">32</span><span class="sxs-lookup"><span data-stu-id="218c4-286">32</span></span></td>
<td><span data-ttu-id="218c4-287">Служба Microsoft Defender для конечных точек не смогла попросить остановиться после процесса offboarding.</span><span class="sxs-lookup"><span data-stu-id="218c4-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="218c4-288">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="218c4-289">Ошибка произошла во время offboarding.</span><span class="sxs-lookup"><span data-stu-id="218c4-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="218c4-290">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="218c4-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-291">33</span><span class="sxs-lookup"><span data-stu-id="218c4-291">33</span></span></td>
<td><span data-ttu-id="218c4-292">Служба Microsoft Defender для конечной точки не смогла сохранить GUID SENSE.</span><span class="sxs-lookup"><span data-stu-id="218c4-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="218c4-293">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-294">Уникальный идентификатор используется для представления каждого устройства, отчитывающееся на портале.</span><span class="sxs-lookup"><span data-stu-id="218c4-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="218c4-295">Если идентификатор не сохраняется, одно и то же устройство может дважды отображаться на портале.</span><span class="sxs-lookup"><span data-stu-id="218c4-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="218c4-296">Проверьте разрешения реестра на устройстве, чтобы убедиться, что служба может обновлять реестр.</span><span class="sxs-lookup"><span data-stu-id="218c4-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-297">34</span><span class="sxs-lookup"><span data-stu-id="218c4-297">34</span></span></td>
<td><span data-ttu-id="218c4-298">Служба Microsoft Defender для конечных точек не смогла добавить себя в зависимость от службы подключенных пользователей и службы телеметрии, из-за чего процесс подключения не удалось.</span><span class="sxs-lookup"><span data-stu-id="218c4-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="218c4-299">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-300">Ошибка произошла в службе Windows телеметрии.</span><span class="sxs-lookup"><span data-stu-id="218c4-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="218c4-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="218c4-302">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="218c4-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="218c4-303">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="218c4-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="218c4-304">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Windows 10 устройства.</a></span><span class="sxs-lookup"><span data-stu-id="218c4-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-305">35</span><span class="sxs-lookup"><span data-stu-id="218c4-305">35</span></span></td>
<td><span data-ttu-id="218c4-306">Служба Microsoft Defender для конечных точек не смогла удалить себя в качестве зависимости от службы подключенных пользователей и службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="218c4-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="218c4-307">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-308">Во время отключения в службе Windows телеметрии произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="218c4-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="218c4-309">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="218c4-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="218c4-310">Проверьте ошибки в службе диагностических Windows данных.</span><span class="sxs-lookup"><span data-stu-id="218c4-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-311">36</span><span class="sxs-lookup"><span data-stu-id="218c4-311">36</span></span></td>
<td><span data-ttu-id="218c4-312">Microsoft Defender для подключенных к конечной точке пользователей и регистрации службы телеметрии успешно.</span><span class="sxs-lookup"><span data-stu-id="218c4-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="218c4-313">Код завершения: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="218c4-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="218c4-314">Успешно завершена регистрация Defender для конечной точки с помощью службы подключенных пользователей и телеметрии.</span><span class="sxs-lookup"><span data-stu-id="218c4-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="218c4-315">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-316">37</span><span class="sxs-lookup"><span data-stu-id="218c4-316">37</span></span></td>
<td><span data-ttu-id="218c4-317">Модуль Microsoft Defender для конечной точки A будет превышать квоту.</span><span class="sxs-lookup"><span data-stu-id="218c4-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="218c4-318">Модуль: %1, Квота: {%2} {%3}, Процент использования квот: %4.</span><span class="sxs-lookup"><span data-stu-id="218c4-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="218c4-319">Устройство почти использовало выделенную квоту текущего 24-часового окна.</span><span class="sxs-lookup"><span data-stu-id="218c4-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="218c4-320">Его вот-вот перенабьют.</span><span class="sxs-lookup"><span data-stu-id="218c4-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="218c4-321">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-322">38</span><span class="sxs-lookup"><span data-stu-id="218c4-322">38</span></span></td>
<td><span data-ttu-id="218c4-323">Подключение к сети определено как низкое.</span><span class="sxs-lookup"><span data-stu-id="218c4-323">Network connection is identified as low.</span></span> <span data-ttu-id="218c4-324">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="218c4-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="218c4-325">Дозное подключение: %2, доступ к Интернету: %3, доступная бесплатная сеть: %4.</span><span class="sxs-lookup"><span data-stu-id="218c4-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="218c4-326">Устройство использует дозную/платную сеть и будет реже обращаться к серверу.</span><span class="sxs-lookup"><span data-stu-id="218c4-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="218c4-327">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-328">39</span><span class="sxs-lookup"><span data-stu-id="218c4-328">39</span></span></td>
<td><span data-ttu-id="218c4-329">Подключение к сети определено как обычное.</span><span class="sxs-lookup"><span data-stu-id="218c4-329">Network connection is identified as normal.</span></span> <span data-ttu-id="218c4-330">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="218c4-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="218c4-331">Дозное подключение: %2, доступ к Интернету: %3, доступная бесплатная сеть: %4.</span><span class="sxs-lookup"><span data-stu-id="218c4-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="218c4-332">Устройство не использует дозное/платное подключение и будет связываться с сервером в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="218c4-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="218c4-333">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-334">40</span><span class="sxs-lookup"><span data-stu-id="218c4-334">40</span></span></td>
<td><span data-ttu-id="218c4-335">Состояние батареи определено как низкое.</span><span class="sxs-lookup"><span data-stu-id="218c4-335">Battery state is identified as low.</span></span> <span data-ttu-id="218c4-336">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="218c4-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="218c4-337">Состояние батареи: %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="218c4-338">Устройство имеет низкий уровень батареи и реже контактировать с сервером.</span><span class="sxs-lookup"><span data-stu-id="218c4-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="218c4-339">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-340">41</span><span class="sxs-lookup"><span data-stu-id="218c4-340">41</span></span></td>
<td><span data-ttu-id="218c4-341">Состояние батареи определено как нормальное.</span><span class="sxs-lookup"><span data-stu-id="218c4-341">Battery state is identified as normal.</span></span> <span data-ttu-id="218c4-342">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="218c4-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="218c4-343">Состояние батареи: %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="218c4-344">Устройство не имеет низкого уровня батареи и будет связываться с сервером, как обычно.</span><span class="sxs-lookup"><span data-stu-id="218c4-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="218c4-345">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-346">42</span><span class="sxs-lookup"><span data-stu-id="218c4-346">42</span></span></td>
<td><span data-ttu-id="218c4-347">Компонент Microsoft Defender для конечной точки не выполнил действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="218c4-348">Компонент: %1, Действие: %2, Тип исключения: %3, Сообщение об исключении: %4</span><span class="sxs-lookup"><span data-stu-id="218c4-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="218c4-349">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="218c4-349">Internal error.</span></span> <span data-ttu-id="218c4-350">Не удалось запустить службу.</span><span class="sxs-lookup"><span data-stu-id="218c4-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="218c4-351">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-352">43</span><span class="sxs-lookup"><span data-stu-id="218c4-352">43</span></span></td>
<td><span data-ttu-id="218c4-353">Компонент Microsoft Defender для конечной точки не выполнил действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="218c4-354">Компонент: %1, Действие: %2, Тип исключения: %3, Ошибка исключения: %4, Сообщение об исключении: %5</span><span class="sxs-lookup"><span data-stu-id="218c4-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="218c4-355">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="218c4-355">Internal error.</span></span> <span data-ttu-id="218c4-356">Не удалось запустить службу.</span><span class="sxs-lookup"><span data-stu-id="218c4-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="218c4-357">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-358">44</span><span class="sxs-lookup"><span data-stu-id="218c4-358">44</span></span></td>
<td><span data-ttu-id="218c4-359">Отключение службы Defender для конечной точки завершено.</span><span class="sxs-lookup"><span data-stu-id="218c4-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="218c4-360">Служба была отключена.</span><span class="sxs-lookup"><span data-stu-id="218c4-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="218c4-361">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-362">45</span><span class="sxs-lookup"><span data-stu-id="218c4-362">45</span></span></td>
<td><span data-ttu-id="218c4-363">Не удалось зарегистрировать и запустить сеанс трассировки событий [%1].</span><span class="sxs-lookup"><span data-stu-id="218c4-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="218c4-364">Код ошибки: %2</span><span class="sxs-lookup"><span data-stu-id="218c4-364">Error code: %2</span></span></td>
<td><span data-ttu-id="218c4-365">Ошибка произошла при запуске службы при создании сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="218c4-366">Это привело к сбою запуска службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="218c4-367">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-368">46</span><span class="sxs-lookup"><span data-stu-id="218c4-368">46</span></span></td>
<td><span data-ttu-id="218c4-369">Не удалось зарегистрировать и запустить сеанс трассировки событий [%1] из-за нехватки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="218c4-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="218c4-370">Код ошибки: %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-370">Error code: %2.</span></span> <span data-ttu-id="218c4-371">Это, скорее всего, потому, что существует слишком много активных сеансов трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="218c4-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="218c4-372">Служба будет повторить в течение 1 минуты.</span><span class="sxs-lookup"><span data-stu-id="218c4-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="218c4-373">Ошибка произошла при запуске службы при создании сеанса ETW из-за нехватки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="218c4-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="218c4-374">Служба запущена и запущена, но не будет сообщать о событии датчика до запуска сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="218c4-375">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="218c4-376">Служба будет пытаться начинать сеанс каждую минуту.</span><span class="sxs-lookup"><span data-stu-id="218c4-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-377">47</span><span class="sxs-lookup"><span data-stu-id="218c4-377">47</span></span></td>
<td><span data-ttu-id="218c4-378">Успешно зарегистрировался и начал сеанс трассировки событий , восстановленный после предыдущих неудачных попыток.</span><span class="sxs-lookup"><span data-stu-id="218c4-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="218c4-379">Это событие следует за предыдущим событием после успешного начала сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="218c4-380">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="218c4-381">48</span><span class="sxs-lookup"><span data-stu-id="218c4-381">48</span></span></td>
<td><span data-ttu-id="218c4-382">Не удалось добавить поставщика [%1] в сеанс трассировки событий [%2].</span><span class="sxs-lookup"><span data-stu-id="218c4-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="218c4-383">Код ошибки: %3.</span><span class="sxs-lookup"><span data-stu-id="218c4-383">Error code: %3.</span></span> <span data-ttu-id="218c4-384">Это означает, что события от этого поставщика не будут отчитаться.</span><span class="sxs-lookup"><span data-stu-id="218c4-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="218c4-385">Не удалось добавить поставщика в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="218c4-386">В результате события поставщика не сообщаются.</span><span class="sxs-lookup"><span data-stu-id="218c4-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="218c4-387">Проверьте код ошибки.</span><span class="sxs-lookup"><span data-stu-id="218c4-387">Check the error code.</span></span> <span data-ttu-id="218c4-388">Если ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="218c4-389">49</span><span class="sxs-lookup"><span data-stu-id="218c4-389">49</span></span></td>
   <td><span data-ttu-id="218c4-390">Команда конфигурации недействительных облаков получена и проигнорирована.</span><span class="sxs-lookup"><span data-stu-id="218c4-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="218c4-391">Версия: %1, состояние: %2, код ошибки: %3, сообщение: %4</span><span class="sxs-lookup"><span data-stu-id="218c4-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="218c4-392">Получил недействительный файл конфигурации из облачной службы, которая была проигнорирована.</span><span class="sxs-lookup"><span data-stu-id="218c4-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="218c4-393">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-394">50</span><span class="sxs-lookup"><span data-stu-id="218c4-394">50</span></span></td>
   <td><span data-ttu-id="218c4-395">Новая конфигурация облака успешно применяется.</span><span class="sxs-lookup"><span data-stu-id="218c4-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="218c4-396">Версия: %1.</span><span class="sxs-lookup"><span data-stu-id="218c4-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="218c4-397">Успешно применена новая конфигурация облачной службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="218c4-398">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-399">51</span><span class="sxs-lookup"><span data-stu-id="218c4-399">51</span></span></td>
   <td><span data-ttu-id="218c4-400">Новая конфигурация облака не применялась, версия: %1.</span><span class="sxs-lookup"><span data-stu-id="218c4-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="218c4-401">Успешно применена последняя известная хорошая конфигурация версии %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="218c4-402">Получен плохой файл конфигурации из облачной службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="218c4-403">Последняя известная хорошая конфигурация была применена успешно.</span><span class="sxs-lookup"><span data-stu-id="218c4-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="218c4-404">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-405">52</span><span class="sxs-lookup"><span data-stu-id="218c4-405">52</span></span></td>
   <td><span data-ttu-id="218c4-406">Новая конфигурация облака не применялась, версия: %1.</span><span class="sxs-lookup"><span data-stu-id="218c4-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="218c4-407">Также не удалось применить последнюю хорошую конфигурацию версии %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="218c4-408">Успешно применена конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="218c4-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="218c4-409">Получен плохой файл конфигурации из облачной службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="218c4-410">Не удалось применить последнюю хорошую конфигурацию , и была применена конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="218c4-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="218c4-411">Служба попытается скачать новый файл конфигурации в течение 5 минут.</span><span class="sxs-lookup"><span data-stu-id="218c4-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="218c4-412">Если вы не видите события #50 - обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-413">53</span><span class="sxs-lookup"><span data-stu-id="218c4-413">53</span></span></td>
   <td><span data-ttu-id="218c4-414">Облачная конфигурация, загруженная из сохраняемого хранилища, версия: %1.</span><span class="sxs-lookup"><span data-stu-id="218c4-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="218c4-415">Конфигурация загружалась из сохраняемого хранилища при запуске службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="218c4-416">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-417">55</span><span class="sxs-lookup"><span data-stu-id="218c4-417">55</span></span></td>
   <td><span data-ttu-id="218c4-418">Не удалось создать автологгер Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="218c4-419">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-420">Не удалось создать безопасный регистратор ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="218c4-421">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="218c4-421">Reboot the device.</span></span> <span data-ttu-id="218c4-422">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-423">56</span><span class="sxs-lookup"><span data-stu-id="218c4-423">56</span></span></td>
   <td><span data-ttu-id="218c4-424">Не удалось удалить автологгер Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="218c4-425">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-426">Не удалось удалить безопасный сеанс ETW при отключении.</span><span class="sxs-lookup"><span data-stu-id="218c4-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="218c4-427">Поддержка контактов.</span><span class="sxs-lookup"><span data-stu-id="218c4-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-428">57</span><span class="sxs-lookup"><span data-stu-id="218c4-428">57</span></span></td>
   <td><span data-ttu-id="218c4-429">Захват снимка компьютера для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="218c4-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="218c4-430">В настоящее время собираются пакеты расследований, также известные как пакет судебно-медицинской экспертизы.</span><span class="sxs-lookup"><span data-stu-id="218c4-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="218c4-431">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-432">59</span><span class="sxs-lookup"><span data-stu-id="218c4-432">59</span></span></td>
   <td><span data-ttu-id="218c4-433">Начальная команда: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="218c4-434">Запуск выполнения командной команды ответа.</span><span class="sxs-lookup"><span data-stu-id="218c4-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="218c4-435">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-436">60</span><span class="sxs-lookup"><span data-stu-id="218c4-436">60</span></span></td>
   <td><span data-ttu-id="218c4-437">Не удалось выполнить команду %1, ошибка: %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="218c4-438">Не удалось выполнить команду ответа.</span><span class="sxs-lookup"><span data-stu-id="218c4-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="218c4-439">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-440">61</span><span class="sxs-lookup"><span data-stu-id="218c4-440">61</span></span></td>
   <td><span data-ttu-id="218c4-441">Параметры командного сбора данных недействительны: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="218c4-442">Не удалось прочитать или размыть аргументы команд сбора данных (недействительные аргументы).</span><span class="sxs-lookup"><span data-stu-id="218c4-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="218c4-443">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-444">62</span><span class="sxs-lookup"><span data-stu-id="218c4-444">62</span></span></td>
   <td><span data-ttu-id="218c4-445">Не удалось запустить службу подключенных пользователей и телеметрии.</span><span class="sxs-lookup"><span data-stu-id="218c4-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="218c4-446">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-447">Не удалось запустить службу подключенных пользовательских интерфейсов и телеметрии (diagtrack).</span><span class="sxs-lookup"><span data-stu-id="218c4-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="218c4-448">Телеметрия не microsoft Defender для конечной точки не будет отправлена с этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="218c4-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="218c4-449">Дополнительные подсказки по устранению неполадок в журнале событий: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="218c4-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-450">63</span><span class="sxs-lookup"><span data-stu-id="218c4-450">63</span></span></td>
   <td><span data-ttu-id="218c4-451">Обновление типа запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-451">Updating the start type of external service.</span></span> <span data-ttu-id="218c4-452">Имя: %1, фактический тип запуска: %2, ожидаемый тип запуска: %3, код выхода: %4</span><span class="sxs-lookup"><span data-stu-id="218c4-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="218c4-453">Обновленный тип запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="218c4-454">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-455">64</span><span class="sxs-lookup"><span data-stu-id="218c4-455">64</span></span></td>
   <td><span data-ttu-id="218c4-456">Запуск остановленной внешней службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-456">Starting stopped external service.</span></span> <span data-ttu-id="218c4-457">Имя: %1, код выхода: %2</span><span class="sxs-lookup"><span data-stu-id="218c4-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="218c4-458">Запуск внешней службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="218c4-459">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-460">65</span><span class="sxs-lookup"><span data-stu-id="218c4-460">65</span></span></td>
   <td><span data-ttu-id="218c4-461">Не удалось загрузить драйвер компонента событий microsoft Security Component Minifilter.</span><span class="sxs-lookup"><span data-stu-id="218c4-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="218c4-462">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-463">Не удалось загрузить MsSecFlt.sys файлосистемы.</span><span class="sxs-lookup"><span data-stu-id="218c4-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="218c4-464">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="218c4-464">Reboot the device.</span></span> <span data-ttu-id="218c4-465">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-466">66</span><span class="sxs-lookup"><span data-stu-id="218c4-466">66</span></span></td>
   <td><span data-ttu-id="218c4-467">Обновление политики: режим задержки - %1</span><span class="sxs-lookup"><span data-stu-id="218c4-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="218c4-468">Политика частоты C&C была обновлена.</span><span class="sxs-lookup"><span data-stu-id="218c4-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="218c4-469">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-470">68</span><span class="sxs-lookup"><span data-stu-id="218c4-470">68</span></span></td>
   <td><span data-ttu-id="218c4-471">Тип запуска службы является неожиданным.</span><span class="sxs-lookup"><span data-stu-id="218c4-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="218c4-472">Имя службы: %1, фактический тип запуска: %2, ожидаемый тип запуска: %3</span><span class="sxs-lookup"><span data-stu-id="218c4-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="218c4-473">Неожиданный внешний тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="218c4-474">Исправление внешнего типа запуска службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-475">69</span><span class="sxs-lookup"><span data-stu-id="218c4-475">69</span></span></td>
   <td><span data-ttu-id="218c4-476">Служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="218c4-476">The service is stopped.</span></span> <span data-ttu-id="218c4-477">Имя службы: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="218c4-478">Внешняя служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="218c4-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="218c4-479">Запустите внешнюю службу.</span><span class="sxs-lookup"><span data-stu-id="218c4-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-480">70</span><span class="sxs-lookup"><span data-stu-id="218c4-480">70</span></span></td>
   <td><span data-ttu-id="218c4-481">Обновление политики: Разрешить выборку коллекции - %1</span><span class="sxs-lookup"><span data-stu-id="218c4-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="218c4-482">Обновлена политика сбора образцов.</span><span class="sxs-lookup"><span data-stu-id="218c4-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="218c4-483">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-484">71</span><span class="sxs-lookup"><span data-stu-id="218c4-484">71</span></span></td>
   <td><span data-ttu-id="218c4-485">Успешное запуск команды: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="218c4-486">Команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="218c4-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="218c4-487">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-488">72</span><span class="sxs-lookup"><span data-stu-id="218c4-488">72</span></span></td>
   <td><span data-ttu-id="218c4-489">Попытался отправить первый полный отчет профиля машины.</span><span class="sxs-lookup"><span data-stu-id="218c4-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="218c4-490">Код результата: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="218c4-491">Только информационная.</span><span class="sxs-lookup"><span data-stu-id="218c4-491">Informational only.</span></span></td>
   <td><span data-ttu-id="218c4-492">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-493">73</span><span class="sxs-lookup"><span data-stu-id="218c4-493">73</span></span></td>
   <td><span data-ttu-id="218c4-494">Чувство, начиная с платформы: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="218c4-495">Только информационная.</span><span class="sxs-lookup"><span data-stu-id="218c4-495">Informational only.</span></span></td>
   <td><span data-ttu-id="218c4-496">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-497">74</span><span class="sxs-lookup"><span data-stu-id="218c4-497">74</span></span></td>
   <td><span data-ttu-id="218c4-498">Тег устройства в реестре превышает ограничение длины.</span><span class="sxs-lookup"><span data-stu-id="218c4-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="218c4-499">Имя тега: %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-499">Tag name: %2.</span></span> <span data-ttu-id="218c4-500">Ограничение длины: %1.</span><span class="sxs-lookup"><span data-stu-id="218c4-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="218c4-501">Тег устройства превышает ограничение длины.</span><span class="sxs-lookup"><span data-stu-id="218c4-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="218c4-502">Используйте более короткий тег устройства.</span><span class="sxs-lookup"><span data-stu-id="218c4-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-503">81</span><span class="sxs-lookup"><span data-stu-id="218c4-503">81</span></span></td>
   <td><span data-ttu-id="218c4-504">Не удалось создать автологгер Microsoft Defender для конечной точки ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="218c4-505">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-506">Не удалось создать сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="218c4-507">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="218c4-507">Reboot the device.</span></span> <span data-ttu-id="218c4-508">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-509">82</span><span class="sxs-lookup"><span data-stu-id="218c4-509">82</span></span></td>
   <td><span data-ttu-id="218c4-510">Не удалось удалить автологгер Microsoft Defender для конечной точки ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="218c4-511">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-512">Не удалось удалить сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="218c4-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="218c4-513">Поддержка контактов.</span><span class="sxs-lookup"><span data-stu-id="218c4-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-514">84</span><span class="sxs-lookup"><span data-stu-id="218c4-514">84</span></span></td>
   <td><span data-ttu-id="218c4-515">Установите антивирусная программа режим работы.</span><span class="sxs-lookup"><span data-stu-id="218c4-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="218c4-516">Пассивный режим force: %1, код результатов: %2.</span><span class="sxs-lookup"><span data-stu-id="218c4-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="218c4-517">Установите режим работы защитника (активный или пассивный).</span><span class="sxs-lookup"><span data-stu-id="218c4-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="218c4-518">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-519">85</span><span class="sxs-lookup"><span data-stu-id="218c4-519">85</span></span></td>
   <td><span data-ttu-id="218c4-520">Не удалось вызвать Microsoft Defender для конечной точки, исполняемой.</span><span class="sxs-lookup"><span data-stu-id="218c4-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="218c4-521">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-522">Выполнение SenseIR в главной роли не удалось.</span><span class="sxs-lookup"><span data-stu-id="218c4-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="218c4-523">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="218c4-523">Reboot the device.</span></span> <span data-ttu-id="218c4-524">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-525">86</span><span class="sxs-lookup"><span data-stu-id="218c4-525">86</span></span></td>
   <td><span data-ttu-id="218c4-526">При запуске снова остановлена внешняя служба, которая должна быть вверх.</span><span class="sxs-lookup"><span data-stu-id="218c4-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="218c4-527">Имя: %1, код выхода: %2</span><span class="sxs-lookup"><span data-stu-id="218c4-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="218c4-528">Запуск внешней службы снова.</span><span class="sxs-lookup"><span data-stu-id="218c4-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="218c4-529">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-530">87</span><span class="sxs-lookup"><span data-stu-id="218c4-530">87</span></span></td>
   <td><span data-ttu-id="218c4-531">Не удается запустить внешнюю службу.</span><span class="sxs-lookup"><span data-stu-id="218c4-531">Cannot start the external service.</span></span> <span data-ttu-id="218c4-532">Имя: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-532">Name: %1</span></span></td>
   <td><span data-ttu-id="218c4-533">Не удалось запустить внешнюю службу.</span><span class="sxs-lookup"><span data-stu-id="218c4-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="218c4-534">Поддержка контактов.</span><span class="sxs-lookup"><span data-stu-id="218c4-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-535">88</span><span class="sxs-lookup"><span data-stu-id="218c4-535">88</span></span></td>
   <td><span data-ttu-id="218c4-536">Повторное обновление типа запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-536">Updating the start type of external service again.</span></span> <span data-ttu-id="218c4-537">Имя: %1, фактический тип запуска: %2, ожидаемый тип запуска: %3, код выхода: %4</span><span class="sxs-lookup"><span data-stu-id="218c4-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="218c4-538">Обновлен тип запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="218c4-539">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-540">89</span><span class="sxs-lookup"><span data-stu-id="218c4-540">89</span></span></td>
   <td><span data-ttu-id="218c4-541">Не удается обновить начните тип внешней службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="218c4-542">Имя: %1, фактический тип запуска: %2, ожидаемый тип запуска: %3</span><span class="sxs-lookup"><span data-stu-id="218c4-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="218c4-543">Не может обновить тип запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="218c4-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="218c4-544">Поддержка контактов.</span><span class="sxs-lookup"><span data-stu-id="218c4-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-545">90</span><span class="sxs-lookup"><span data-stu-id="218c4-545">90</span></span></td>
   <td><span data-ttu-id="218c4-546">Не удалось настроить system Guard Runtime Monitor для подключения к облачной службе в geo-region %1.</span><span class="sxs-lookup"><span data-stu-id="218c4-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="218c4-547">Код отказа: %2</span><span class="sxs-lookup"><span data-stu-id="218c4-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="218c4-548">System Guard Runtime Monitor не будет отправлять данные проверки в облачную службу.</span><span class="sxs-lookup"><span data-stu-id="218c4-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="218c4-549">Проверьте разрешения на пути регистрации: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="218c4-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="218c4-550">Если проблем не обнаружено, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-551">91</span><span class="sxs-lookup"><span data-stu-id="218c4-551">91</span></span></td>
   <td><span data-ttu-id="218c4-552">Не удалось удалить сведения о георегиране System Guard Runtime Monitor.</span><span class="sxs-lookup"><span data-stu-id="218c4-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="218c4-553">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-554">System Guard Runtime Monitor не будет отправлять данные проверки в облачную службу.</span><span class="sxs-lookup"><span data-stu-id="218c4-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="218c4-555">Проверьте разрешения на пути регистрации: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="218c4-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="218c4-556">Если проблем не обнаружено, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-557">92</span><span class="sxs-lookup"><span data-stu-id="218c4-557">92</span></span></td>
   <td><span data-ttu-id="218c4-558">Прекращение отправки квоты кибер-данных датчика из-за превышения квоты данных.</span><span class="sxs-lookup"><span data-stu-id="218c4-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="218c4-559">Возобновит отправку после того, как пройдет период квоты.</span><span class="sxs-lookup"><span data-stu-id="218c4-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="218c4-560">Маска состояния: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="218c4-561">Превышение лимита регулирования.</span><span class="sxs-lookup"><span data-stu-id="218c4-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="218c4-562">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-563">93</span><span class="sxs-lookup"><span data-stu-id="218c4-563">93</span></span></td>
   <td><span data-ttu-id="218c4-564">Повторное отправка данных кибер-датчика.</span><span class="sxs-lookup"><span data-stu-id="218c4-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="218c4-565">Маска состояния: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="218c4-566">Возобновление отправки кибер-данных.</span><span class="sxs-lookup"><span data-stu-id="218c4-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="218c4-567">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-568">94</span><span class="sxs-lookup"><span data-stu-id="218c4-568">94</span></span></td>
   <td><span data-ttu-id="218c4-569">Начался microsoft Defender для исполняемой конечной точки</span><span class="sxs-lookup"><span data-stu-id="218c4-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="218c4-570">Начался исполняемый SenseCE.</span><span class="sxs-lookup"><span data-stu-id="218c4-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="218c4-571">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-572">95</span><span class="sxs-lookup"><span data-stu-id="218c4-572">95</span></span></td>
   <td><span data-ttu-id="218c4-573">Microsoft Defender для исполняемой конечной точки завершилась</span><span class="sxs-lookup"><span data-stu-id="218c4-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="218c4-574">Исполняемый SenseCE завершился.</span><span class="sxs-lookup"><span data-stu-id="218c4-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="218c4-575">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-576">96</span><span class="sxs-lookup"><span data-stu-id="218c4-576">96</span></span></td>
   <td><span data-ttu-id="218c4-577">Microsoft Defender для endpoint Init вызвал.</span><span class="sxs-lookup"><span data-stu-id="218c4-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="218c4-578">Код результата: %2</span><span class="sxs-lookup"><span data-stu-id="218c4-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="218c4-579">Исполняемый SenseCE вызвал инициализацию MCE.</span><span class="sxs-lookup"><span data-stu-id="218c4-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="218c4-580">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-581">97</span><span class="sxs-lookup"><span data-stu-id="218c4-581">97</span></span></td>
   <td><span data-ttu-id="218c4-582">Существуют проблемы с подключением к облаку для сценария DLP</span><span class="sxs-lookup"><span data-stu-id="218c4-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="218c4-583">Существуют проблемы сетевого подключения, влияющие на поток классификации DLP.</span><span class="sxs-lookup"><span data-stu-id="218c4-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="218c4-584">Проверьте подключение к сети.</span><span class="sxs-lookup"><span data-stu-id="218c4-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-585">98</span><span class="sxs-lookup"><span data-stu-id="218c4-585">98</span></span></td>
   <td><span data-ttu-id="218c4-586">Подключение к облаку для сценария DLP восстановлено</span><span class="sxs-lookup"><span data-stu-id="218c4-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="218c4-587">Подключение к сети восстановлено, и поток классификации DLP может продолжаться.</span><span class="sxs-lookup"><span data-stu-id="218c4-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="218c4-588">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-589">99</span><span class="sxs-lookup"><span data-stu-id="218c4-589">99</span></span></td>
   <td><span data-ttu-id="218c4-590">Sense столкнулась со следующей ошибкой при общении с сервером: (%1).</span><span class="sxs-lookup"><span data-stu-id="218c4-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="218c4-591">Результат: (%2)</span><span class="sxs-lookup"><span data-stu-id="218c4-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="218c4-592">Произошла ошибка связи.</span><span class="sxs-lookup"><span data-stu-id="218c4-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="218c4-593">Дополнительные сведения о следующих событиях в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="218c4-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-594">100</span><span class="sxs-lookup"><span data-stu-id="218c4-594">100</span></span></td>
   <td><span data-ttu-id="218c4-595">Не удалось запустить Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="218c4-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="218c4-596">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="218c4-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="218c4-597">Не удалось запустить исполняемый SenseCE.</span><span class="sxs-lookup"><span data-stu-id="218c4-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="218c4-598">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="218c4-598">Reboot the device.</span></span> <span data-ttu-id="218c4-599">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="218c4-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-600">102</span><span class="sxs-lookup"><span data-stu-id="218c4-600">102</span></span></td>
   <td><span data-ttu-id="218c4-601">Начался microsoft Defender для обнаружения конечных точек сети и выполнения ответных действий</span><span class="sxs-lookup"><span data-stu-id="218c4-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="218c4-602">Начался исполняемый SenseNdr.</span><span class="sxs-lookup"><span data-stu-id="218c4-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="218c4-603">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="218c4-604">103</span><span class="sxs-lookup"><span data-stu-id="218c4-604">103</span></span></td>
   <td><span data-ttu-id="218c4-605">Microsoft Defender для обнаружения конечных точек сети и выполнения ответов завершен</span><span class="sxs-lookup"><span data-stu-id="218c4-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="218c4-606">Выполнение SenseNdr завершено.</span><span class="sxs-lookup"><span data-stu-id="218c4-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="218c4-607">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="218c4-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="218c4-608">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="218c4-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="218c4-609">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="218c4-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="218c4-610">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="218c4-610">Related topics</span></span>
- [<span data-ttu-id="218c4-611">Подключение устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="218c4-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="218c4-612">Настройка параметров прокси-сервера устройства и соединения с Интернетом</span><span class="sxs-lookup"><span data-stu-id="218c4-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="218c4-613">Устранение неполадок Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="218c4-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
