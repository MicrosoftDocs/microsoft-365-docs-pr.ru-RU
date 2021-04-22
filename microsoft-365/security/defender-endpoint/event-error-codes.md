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
# <a name="review-events-and-errors-using-event-viewer"></a><span data-ttu-id="2b721-104">Просмотр событий и ошибок с помощью viewer событий</span><span class="sxs-lookup"><span data-stu-id="2b721-104">Review events and errors using Event Viewer</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="2b721-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="2b721-105">**Applies to:**</span></span>
- <span data-ttu-id="2b721-106">Средство просмотра событий</span><span class="sxs-lookup"><span data-stu-id="2b721-106">Event Viewer</span></span>
- [<span data-ttu-id="2b721-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2b721-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/?linkid=2154037)
- [<span data-ttu-id="2b721-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2b721-108">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="2b721-109">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="2b721-109">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2b721-110">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="2b721-110">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-enablesiem-abovefoldlink)

<span data-ttu-id="2b721-111">Вы можете просмотреть ID событий в [средстве просмотра событий](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) на отдельных устройствах.</span><span class="sxs-lookup"><span data-stu-id="2b721-111">You can review event IDs in the [Event Viewer](https://msdn.microsoft.com/library/aa745633(v=bts.10).aspx) on individual devices.</span></span>

<span data-ttu-id="2b721-112">Например, если устройства не отображаются в списке **Устройств,** может потребоваться искать ИД событий на устройствах.</span><span class="sxs-lookup"><span data-stu-id="2b721-112">For example, if devices aren't appearing in the **Devices list**, you might need to look for event IDs on the devices.</span></span> <span data-ttu-id="2b721-113">Затем можно использовать эту таблицу для определения дальнейших действий по устранению неполадок.</span><span class="sxs-lookup"><span data-stu-id="2b721-113">You can then use this table to determine further troubleshooting steps.</span></span>

<span data-ttu-id="2b721-114">**Откройте для просмотра событий и найдите журнал событий службы Microsoft Defender для конечных точек:**</span><span class="sxs-lookup"><span data-stu-id="2b721-114">**Open Event Viewer and find the Microsoft Defender for Endpoint service event log:**</span></span>

1. <span data-ttu-id="2b721-115">Нажмите **кнопку Пуск** в меню Windows, введите **viewer событий** и нажмите **кнопку Ввод**.</span><span class="sxs-lookup"><span data-stu-id="2b721-115">Click **Start** on the Windows menu, type **Event Viewer**, and press **Enter**.</span></span>

2. <span data-ttu-id="2b721-116">В списке журнала в **статье Сводка журнала** прокрутите до тех пор, пока не увидите **Microsoft-Windows-SENSE/Operational.**</span><span class="sxs-lookup"><span data-stu-id="2b721-116">In the log list, under **Log Summary**, scroll until you see **Microsoft-Windows-SENSE/Operational**.</span></span> <span data-ttu-id="2b721-117">Дважды щелкните элемент, чтобы открыть журнал.</span><span class="sxs-lookup"><span data-stu-id="2b721-117">Double-click the item to open the log.</span></span>

   <span data-ttu-id="2b721-118">а.</span><span class="sxs-lookup"><span data-stu-id="2b721-118">a.</span></span>  <span data-ttu-id="2b721-119">Вы также можете получить доступ к журналу, расширяя журналы приложений и служб Microsoft Windows SENSE и нажмите  >    >    >   кнопку **Оперативный**.</span><span class="sxs-lookup"><span data-stu-id="2b721-119">You can also access the log by expanding **Applications and Services Logs** > **Microsoft** > **Windows** > **SENSE** and click on **Operational**.</span></span>

   > [!NOTE]
   > <span data-ttu-id="2b721-120">SENSE — это внутреннее имя, используемое для обозначения поведенческого датчика, который работает с Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2b721-120">SENSE is the internal name used to refer to the behavioral sensor that powers Microsoft Defender for Endpoint.</span></span>

3. <span data-ttu-id="2b721-121">События, записанные службой, будут отображаться в журнале.</span><span class="sxs-lookup"><span data-stu-id="2b721-121">Events recorded by the service will appear in the log.</span></span> <span data-ttu-id="2b721-122">Список событий, записанных службой, см. в следующей таблице.</span><span class="sxs-lookup"><span data-stu-id="2b721-122">See the following table for a list of events recorded by the service.</span></span>

<table>
<tbody style="vertical-align:top;">
<tr>
<th><span data-ttu-id="2b721-123">Идентификатор события</span><span class="sxs-lookup"><span data-stu-id="2b721-123">Event ID</span></span></th>
<th><span data-ttu-id="2b721-124">Сообщение</span><span class="sxs-lookup"><span data-stu-id="2b721-124">Message</span></span></th>
<th><span data-ttu-id="2b721-125">Описание</span><span class="sxs-lookup"><span data-stu-id="2b721-125">Description</span></span></th>
<th><span data-ttu-id="2b721-126">Action</span><span class="sxs-lookup"><span data-stu-id="2b721-126">Action</span></span></th>
</tr>
<tr>
<td><span data-ttu-id="2b721-127">1</span><span class="sxs-lookup"><span data-stu-id="2b721-127">1</span></span></td>
<td><span data-ttu-id="2b721-128">Запущена служба Microsoft Defender для конечной точки <code>variable</code> (Версия).</span><span class="sxs-lookup"><span data-stu-id="2b721-128">Microsoft Defender for Endpoint service started (Version <code>variable</code>).</span></span></td>
<td><span data-ttu-id="2b721-129">Происходит во время запуска системы, отключения и во время включаемой.</span><span class="sxs-lookup"><span data-stu-id="2b721-129">Occurs during system startup, shut down, and during onboarding.</span></span></td>
<td><span data-ttu-id="2b721-130">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-130">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-131">2</span><span class="sxs-lookup"><span data-stu-id="2b721-131">2</span></span></td>
<td><span data-ttu-id="2b721-132">Отключение службы Microsoft Defender для конечных точек.</span><span class="sxs-lookup"><span data-stu-id="2b721-132">Microsoft Defender for Endpoint service shutdown.</span></span></td>
<td><span data-ttu-id="2b721-133">Происходит, когда устройство отключено или отключено.</span><span class="sxs-lookup"><span data-stu-id="2b721-133">Occurs when the device is shut down or offboarded.</span></span></td>
<td><span data-ttu-id="2b721-134">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-134">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-135">3</span><span class="sxs-lookup"><span data-stu-id="2b721-135">3</span></span></td>
<td><span data-ttu-id="2b721-136">Не удалось запустить службу Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2b721-136">Microsoft Defender for Endpoint service failed to start.</span></span> <span data-ttu-id="2b721-137">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-137">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-138">Служба не началась.</span><span class="sxs-lookup"><span data-stu-id="2b721-138">Service didn't start.</span></span></td>
<td><span data-ttu-id="2b721-139">Просмотрите другие сообщения, чтобы определить возможные действия по устранению причин и неполадок.</span><span class="sxs-lookup"><span data-stu-id="2b721-139">Review other messages to determine possible cause and troubleshooting steps.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-140">4 </span><span class="sxs-lookup"><span data-stu-id="2b721-140">4</span></span></td>
<td><span data-ttu-id="2b721-141">Служба Microsoft Defender для конечной точки связалась с сервером в <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-141">Microsoft Defender for Endpoint service contacted the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-142">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="2b721-142">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="2b721-143">Этот URL-адрес будет совпадать с тем, что видно в брандмауэре или сетевой активности.</span><span class="sxs-lookup"><span data-stu-id="2b721-143">This URL will match that seen in the Firewall or network activity.</span></span></td>
<td><span data-ttu-id="2b721-144">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-144">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-145">5 </span><span class="sxs-lookup"><span data-stu-id="2b721-145">5</span></span></td>
<td><span data-ttu-id="2b721-146">Служба Microsoft Defender для конечных точек не смогла подключиться к серверу по <code>variable</code> данным .</span><span class="sxs-lookup"><span data-stu-id="2b721-146">Microsoft Defender for Endpoint service failed to connect to the server at <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-147">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="2b721-147">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="2b721-148">Служба не смогла связаться с внешними серверами обработки по этому URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="2b721-148">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="2b721-149">Проверьте подключение к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="2b721-149">Check the connection to the URL.</span></span> <span data-ttu-id="2b721-150">См. <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">в перенастройке прокси-серверов и подключения к Интернету.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-150">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-151">6 </span><span class="sxs-lookup"><span data-stu-id="2b721-151">6</span></span></td>
<td><span data-ttu-id="2b721-152">Служба Microsoft Defender для конечной точки не установлена на борт, и параметры бортового параметров не найдены.</span><span class="sxs-lookup"><span data-stu-id="2b721-152">Microsoft Defender for Endpoint service is not onboarded and no onboarding parameters were found.</span></span></td>
<td><span data-ttu-id="2b721-153">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="2b721-153">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="2b721-154">Перед запуском службы необходимо запустить бортовую службу.</span><span class="sxs-lookup"><span data-stu-id="2b721-154">Onboarding must be run before starting the service.</span></span><br>
<span data-ttu-id="2b721-155">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-155">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-156">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-156">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-157">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-157">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-158">7 </span><span class="sxs-lookup"><span data-stu-id="2b721-158">7</span></span></td>
<td><span data-ttu-id="2b721-159">Служба Microsoft Defender для конечной точки не считыла параметры бортовой записи.</span><span class="sxs-lookup"><span data-stu-id="2b721-159">Microsoft Defender for Endpoint service failed to read the onboarding parameters.</span></span> <span data-ttu-id="2b721-160">Сбой: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-160">Failure: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-161">Переменная = подробное описание ошибки.</span><span class="sxs-lookup"><span data-stu-id="2b721-161">Variable = detailed error description.</span></span> <span data-ttu-id="2b721-162">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="2b721-162">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="2b721-163">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-163">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-164">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-164">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-165">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-165">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-166">8 </span><span class="sxs-lookup"><span data-stu-id="2b721-166">8</span></span></td>
<td><span data-ttu-id="2b721-167">Служба Microsoft Defender для конечной точки не смогла очистить конфигурацию.</span><span class="sxs-lookup"><span data-stu-id="2b721-167">Microsoft Defender for Endpoint service failed to clean its configuration.</span></span> <span data-ttu-id="2b721-168">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-168">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-169"><b>Во время бортового октагона:</b> Службе не удалось очистить конфигурацию во время бортовой работы.</span><span class="sxs-lookup"><span data-stu-id="2b721-169"><b>During onboarding:</b> The service failed to clean its configuration during the onboarding.</span></span> <span data-ttu-id="2b721-170">Процесс вмеяния продолжается.</span><span class="sxs-lookup"><span data-stu-id="2b721-170">The onboarding process continues.</span></span> <br><br> <span data-ttu-id="2b721-171"><b>Во время offboarding:</b> Служба не смогла очистить конфигурацию во время отключения.</span><span class="sxs-lookup"><span data-stu-id="2b721-171"><b>During offboarding:</b> The service failed to clean its configuration during the offboarding.</span></span> <span data-ttu-id="2b721-172">Процесс offboarding завершен, но служба продолжает работать.</span><span class="sxs-lookup"><span data-stu-id="2b721-172">The offboarding process finished but the service keeps running.</span></span>
 </td>
<td><span data-ttu-id="2b721-173"><b>Onboarding:</b> Никаких действий не требуется.</span><span class="sxs-lookup"><span data-stu-id="2b721-173"><b>Onboarding:</b> No action required.</span></span> <br><br> <span data-ttu-id="2b721-174"><b>Offboarding:</b> Перезагрузка системы.</span><span class="sxs-lookup"><span data-stu-id="2b721-174"><b>Offboarding:</b> Reboot the system.</span></span><br>
<span data-ttu-id="2b721-175">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-175">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-176">9 </span><span class="sxs-lookup"><span data-stu-id="2b721-176">9</span></span></td>
<td><span data-ttu-id="2b721-177">Служба Microsoft Defender для конечной точки не смогла изменить тип запуска.</span><span class="sxs-lookup"><span data-stu-id="2b721-177">Microsoft Defender for Endpoint service failed to change its start type.</span></span> <span data-ttu-id="2b721-178">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-178">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-179"><b>Во время бортового октагона:</b> Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="2b721-179"><b>During onboarding:</b> The device didn't onboard correctly and won't be reporting to the portal.</span></span> <br><br><span data-ttu-id="2b721-180"><b>Во время offboarding:</b> Не удалось изменить тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-180"><b>During offboarding:</b> Failed to change the service start type.</span></span> <span data-ttu-id="2b721-181">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="2b721-181">The offboarding process continues.</span></span> </td>
<td><span data-ttu-id="2b721-182">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-182">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-183">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-183">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-184">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-184">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-185">10 </span><span class="sxs-lookup"><span data-stu-id="2b721-185">10</span></span></td>
<td><span data-ttu-id="2b721-186">Служба Microsoft Defender для конечных точек не смогла сохранить сведения о взимаемой информации.</span><span class="sxs-lookup"><span data-stu-id="2b721-186">Microsoft Defender for Endpoint service failed to persist the onboarding information.</span></span> <span data-ttu-id="2b721-187">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-187">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-188">Устройство не было правильно на борту и не будет сообщать на портал.</span><span class="sxs-lookup"><span data-stu-id="2b721-188">The device didn't onboard correctly and won't be reporting to the portal.</span></span></td>
<td><span data-ttu-id="2b721-189">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-189">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-190">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-190">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-191">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-191">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-192">11</span><span class="sxs-lookup"><span data-stu-id="2b721-192">11</span></span></td>
<td><span data-ttu-id="2b721-193">Заполнена или выполнена перенастройка службы Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2b721-193">Onboarding or re-onboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="2b721-194">Устройство правильно вошел в борт.</span><span class="sxs-lookup"><span data-stu-id="2b721-194">The device onboarded correctly.</span></span></td>
<td><span data-ttu-id="2b721-195">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-195">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="2b721-196">Для появления устройства на портале может потребоваться несколько часов.</span><span class="sxs-lookup"><span data-stu-id="2b721-196">It may take several hours for the device to appear in the portal.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-197">12 </span><span class="sxs-lookup"><span data-stu-id="2b721-197">12</span></span></td>
<td><span data-ttu-id="2b721-198">Microsoft Defender для конечной точки не смог применить конфигурацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2b721-198">Microsoft Defender for Endpoint failed to apply the default configuration.</span></span></td>
<td><span data-ttu-id="2b721-199">Служба не смогла применить конфигурацию по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2b721-199">Service was unable to apply the default configuration.</span></span></td>
<td><span data-ttu-id="2b721-200">Эта ошибка должна устраниться после короткого периода времени.</span><span class="sxs-lookup"><span data-stu-id="2b721-200">This error should resolve after a short period of time.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-201">13</span><span class="sxs-lookup"><span data-stu-id="2b721-201">13</span></span></td>
<td><span data-ttu-id="2b721-202">Вычисляется ID устройства Microsoft Defender для конечных точек: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-202">Microsoft Defender for Endpoint device ID calculated: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-203">Нормальный операционный процесс.</span><span class="sxs-lookup"><span data-stu-id="2b721-203">Normal operating process.</span></span></td>
<td><span data-ttu-id="2b721-204">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-204">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-205">15 </span><span class="sxs-lookup"><span data-stu-id="2b721-205">15</span></span></td>
<td><span data-ttu-id="2b721-206">Microsoft Defender для конечной точки не может запустить командный канал с URL-адресом: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-206">Microsoft Defender for Endpoint cannot start command channel with URL: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-207">Переменная = URL-адрес серверов обработки конечных точек Defender.</span><span class="sxs-lookup"><span data-stu-id="2b721-207">Variable = URL of the Defender for Endpoint processing servers.</span></span><br>
<span data-ttu-id="2b721-208">Служба не смогла связаться с внешними серверами обработки по этому URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="2b721-208">The service couldn't contact the external processing servers at that URL.</span></span></td>
<td><span data-ttu-id="2b721-209">Проверьте подключение к URL-адресу.</span><span class="sxs-lookup"><span data-stu-id="2b721-209">Check the connection to the URL.</span></span> <span data-ttu-id="2b721-210">См. <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">в перенастройке прокси-серверов и подключения к Интернету.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-210">See <a href="configure-proxy-internet.md" data-raw-source="[Configure proxy and Internet connectivity](configure-proxy-internet.md)">Configure proxy and Internet connectivity</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-211">17 </span><span class="sxs-lookup"><span data-stu-id="2b721-211">17</span></span></td>
<td><span data-ttu-id="2b721-212">Служба Microsoft Defender для конечных точек не смогла изменить расположение службы подключенных пользователей и службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="2b721-212">Microsoft Defender for Endpoint service failed to change the Connected User Experiences and Telemetry service location.</span></span> <span data-ttu-id="2b721-213">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-213">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-214">Ошибка произошла в службе телеметрии Windows.</span><span class="sxs-lookup"><span data-stu-id="2b721-214">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="2b721-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-215"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="2b721-216">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-216">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-217">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-217">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-218">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-218">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-219">18 </span><span class="sxs-lookup"><span data-stu-id="2b721-219">18</span></span></td>
<td><span data-ttu-id="2b721-220">OOBE (Добро пожаловать в Windows) завершено.</span><span class="sxs-lookup"><span data-stu-id="2b721-220">OOBE (Windows Welcome) is completed.</span></span></td>
<td><span data-ttu-id="2b721-221">Служба начнется только после завершения установки обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="2b721-221">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="2b721-222">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-222">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-223">19</span><span class="sxs-lookup"><span data-stu-id="2b721-223">19</span></span></td>
<td><span data-ttu-id="2b721-224">OOBE (Windows Welcome) еще не завершена.</span><span class="sxs-lookup"><span data-stu-id="2b721-224">OOBE (Windows Welcome) has not yet completed.</span></span></td>
<td><span data-ttu-id="2b721-225">Служба начнется только после завершения установки обновлений Windows.</span><span class="sxs-lookup"><span data-stu-id="2b721-225">Service will only start after any Windows updates have finished installing.</span></span></td>
<td><span data-ttu-id="2b721-226">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-226">Normal operating notification; no action required.</span></span><br>
<span data-ttu-id="2b721-227">Если эта ошибка сохраняется после перезапуска системы, убедитесь, что все обновления Windows установлены полностью.</span><span class="sxs-lookup"><span data-stu-id="2b721-227">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-228">20</span><span class="sxs-lookup"><span data-stu-id="2b721-228">20</span></span></td>
<td><span data-ttu-id="2b721-229">Не удается дождаться завершения OOBE (Windows Welcome).</span><span class="sxs-lookup"><span data-stu-id="2b721-229">Cannot wait for OOBE (Windows Welcome) to complete.</span></span> <span data-ttu-id="2b721-230">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-230">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-231">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="2b721-231">Internal error.</span></span></td>
<td><span data-ttu-id="2b721-232">Если эта ошибка сохраняется после перезапуска системы, убедитесь, что все обновления Windows установлены полностью.</span><span class="sxs-lookup"><span data-stu-id="2b721-232">If this error persists after a system restart, ensure all Windows updates have full installed.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-233">25</span><span class="sxs-lookup"><span data-stu-id="2b721-233">25</span></span></td>
<td><span data-ttu-id="2b721-234">Службе Microsoft Defender для конечных точек не удалось сбросить состояние здоровья в реестре.</span><span class="sxs-lookup"><span data-stu-id="2b721-234">Microsoft Defender for Endpoint service failed to reset health status in the registry.</span></span> <span data-ttu-id="2b721-235">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-235">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-236">Устройство не было правильно на борту.</span><span class="sxs-lookup"><span data-stu-id="2b721-236">The device didn't onboard correctly.</span></span>
<span data-ttu-id="2b721-237">Он будет сообщать на портал, однако служба не может отображаться как зарегистрированная в SCCM или реестре.</span><span class="sxs-lookup"><span data-stu-id="2b721-237">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="2b721-238">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-238">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-239">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-239">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-240">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-240">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-241">26</span><span class="sxs-lookup"><span data-stu-id="2b721-241">26</span></span></td>
<td><span data-ttu-id="2b721-242">Службе Microsoft Defender для конечных точек не удалось установить в реестре состояние onboarding.</span><span class="sxs-lookup"><span data-stu-id="2b721-242">Microsoft Defender for Endpoint service failed to set the onboarding status in the registry.</span></span> <span data-ttu-id="2b721-243">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-243">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-244">Устройство не было правильно на борту.</span><span class="sxs-lookup"><span data-stu-id="2b721-244">The device didn't onboard correctly.</span></span><br>
<span data-ttu-id="2b721-245">Он будет сообщать на портал, однако служба не может отображаться как зарегистрированная в SCCM или реестре.</span><span class="sxs-lookup"><span data-stu-id="2b721-245">It will report to the portal, however the service may not appear as registered in SCCM or the registry.</span></span></td>
<td><span data-ttu-id="2b721-246">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-246">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-247">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-247">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-248">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-248">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-249">27</span><span class="sxs-lookup"><span data-stu-id="2b721-249">27</span></span></td>
<td><span data-ttu-id="2b721-250">Служба Microsoft Defender для конечной точки не смогла включить режим sense в антивирусе Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2b721-250">Microsoft Defender for Endpoint service failed to enable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="2b721-251">Сбой в процессе onboarding.</span><span class="sxs-lookup"><span data-stu-id="2b721-251">Onboarding process failed.</span></span> <span data-ttu-id="2b721-252">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-252">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-253">Обычно антивирус Microsoft Defender вступает в специальное пассивное состояние, если на устройстве правильно работает другой антивирусный продукт в режиме реального времени, а устройство сообщается в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2b721-253">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="2b721-254">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-254">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-255">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-255">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-256">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-256">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span><br>
<span data-ttu-id="2b721-257">Убедитесь, что защита от антивирусных программ в режиме реального времени работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-257">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-258">28</span><span class="sxs-lookup"><span data-stu-id="2b721-258">28</span></span></td>
<td><span data-ttu-id="2b721-259">В Microsoft Defender для подключенных к конечной точке пользовательских интерфейсов и регистрации службы телеметрии не удалось.</span><span class="sxs-lookup"><span data-stu-id="2b721-259">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration failed.</span></span> <span data-ttu-id="2b721-260">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-260">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-261">Ошибка произошла в службе телеметрии Windows.</span><span class="sxs-lookup"><span data-stu-id="2b721-261">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="2b721-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-262"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="2b721-263">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-263">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-264">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-264">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-265">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-265">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-266">29</span><span class="sxs-lookup"><span data-stu-id="2b721-266">29</span></span></td>
<td><span data-ttu-id="2b721-267">Не удалось прочитать параметры offboarding.</span><span class="sxs-lookup"><span data-stu-id="2b721-267">Failed to read the offboarding parameters.</span></span> <span data-ttu-id="2b721-268">Тип ошибки: %1, код ошибки: %2, Описание: %3</span><span class="sxs-lookup"><span data-stu-id="2b721-268">Error type: %1, Error code: %2, Description: %3</span></span> </td>
<td><span data-ttu-id="2b721-269">Это событие происходит, когда система может&#39;не читать параметры offboarding.</span><span class="sxs-lookup"><span data-stu-id="2b721-269">This event occurs when the system can&#39;t read the offboarding parameters.</span></span></td>
<td><span data-ttu-id="2b721-270">Убедитесь, что устройство имеет доступ к Интернету, затем запустите весь процесс offboarding снова.</span><span class="sxs-lookup"><span data-stu-id="2b721-270">Ensure the device has Internet access, then run the entire offboarding process again.</span></span> <span data-ttu-id="2b721-271">Убедитесь, что срок действия пакета offboarding не истек.</span><span class="sxs-lookup"><span data-stu-id="2b721-271">Ensure the offboarding package hasn't expired.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-272">30</span><span class="sxs-lookup"><span data-stu-id="2b721-272">30</span></span></td>
<td><span data-ttu-id="2b721-273">Службе Microsoft Defender для конечных точек не удалось отключить режим зная SENSE в антивирусе Microsoft Defender.</span><span class="sxs-lookup"><span data-stu-id="2b721-273">Microsoft Defender for Endpoint service failed to disable SENSE aware mode in Microsoft Defender Antivirus.</span></span> <span data-ttu-id="2b721-274">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-274">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-275">Обычно антивирус Microsoft Defender вступает в специальное пассивное состояние, если на устройстве правильно работает другой антивирусный продукт в режиме реального времени, а устройство сообщается в Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="2b721-275">Normally, Microsoft Defender Antivirus will enter a special passive state if another real-time antimalware product is running properly on the device, and the device is reporting to Defender for Endpoint.</span></span></td>
<td><span data-ttu-id="2b721-276">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-276">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-277">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-277">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-278">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте устройств с Windows 10</a></span><span class="sxs-lookup"><span data-stu-id="2b721-278">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a></span></span><br>
<span data-ttu-id="2b721-279">Убедитесь, что защита от антивирусных программ в режиме реального времени работает должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-279">Ensure real-time antimalware protection is running properly.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-280">31</span><span class="sxs-lookup"><span data-stu-id="2b721-280">31</span></span></td>
<td><span data-ttu-id="2b721-281">Сбой в работе Microsoft Defender для подключенных к конечным точкам пользователей и регистрации службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="2b721-281">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service unregistration failed.</span></span> <span data-ttu-id="2b721-282">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-282">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-283">Ошибка произошла в службе телеметрии Windows во время бортовой работы.</span><span class="sxs-lookup"><span data-stu-id="2b721-283">An error occurred with the Windows telemetry service during onboarding.</span></span> <span data-ttu-id="2b721-284">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="2b721-284">The offboarding process continues.</span></span></td>
<td><span data-ttu-id="2b721-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Проверьте ошибки в службе телеметрии Windows.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-285"><a href="troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled" data-raw-source="[Check for errors with the Windows telemetry service](troubleshoot-onboarding.md#ensure-the-diagnostic-data-service-is-enabled)">Check for errors with the Windows telemetry service</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-286">32</span><span class="sxs-lookup"><span data-stu-id="2b721-286">32</span></span></td>
<td><span data-ttu-id="2b721-287">Служба Microsoft Defender для конечных точек не смогла попросить остановиться после процесса offboarding.</span><span class="sxs-lookup"><span data-stu-id="2b721-287">Microsoft Defender for Endpoint service failed to request to stop itself after offboarding process.</span></span> <span data-ttu-id="2b721-288">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-288">Failure code: %1</span></span></td>
<td><span data-ttu-id="2b721-289">Ошибка произошла во время offboarding.</span><span class="sxs-lookup"><span data-stu-id="2b721-289">An error occurred during offboarding.</span></span></td>
<td><span data-ttu-id="2b721-290">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="2b721-290">Reboot the device.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-291">33</span><span class="sxs-lookup"><span data-stu-id="2b721-291">33</span></span></td>
<td><span data-ttu-id="2b721-292">Служба Microsoft Defender для конечной точки не смогла сохранить GUID SENSE.</span><span class="sxs-lookup"><span data-stu-id="2b721-292">Microsoft Defender for Endpoint service failed to persist SENSE GUID.</span></span> <span data-ttu-id="2b721-293">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-293">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-294">Уникальный идентификатор используется для представления каждого устройства, отчитывающееся на портале.</span><span class="sxs-lookup"><span data-stu-id="2b721-294">A unique identifier is used to represent each device that is reporting to the portal.</span></span><br>
<span data-ttu-id="2b721-295">Если идентификатор не сохраняется, одно и то же устройство может дважды отображаться на портале.</span><span class="sxs-lookup"><span data-stu-id="2b721-295">If the identifier doesn't persist, the same device might appear twice in the portal.</span></span></td>
<td><span data-ttu-id="2b721-296">Проверьте разрешения реестра на устройстве, чтобы убедиться, что служба может обновлять реестр.</span><span class="sxs-lookup"><span data-stu-id="2b721-296">Check registry permissions on the device to ensure the service can update the registry.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-297">34</span><span class="sxs-lookup"><span data-stu-id="2b721-297">34</span></span></td>
<td><span data-ttu-id="2b721-298">Служба Microsoft Defender для конечных точек не смогла добавить себя в зависимость от службы подключенных пользователей и службы телеметрии, из-за чего процесс подключения не удалось.</span><span class="sxs-lookup"><span data-stu-id="2b721-298">Microsoft Defender for Endpoint service failed to add itself as a dependency on the Connected User Experiences and Telemetry service, causing onboarding process to fail.</span></span> <span data-ttu-id="2b721-299">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-299">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-300">Ошибка произошла в службе телеметрии Windows.</span><span class="sxs-lookup"><span data-stu-id="2b721-300">An error occurred with the Windows telemetry service.</span></span></td>
<td><span data-ttu-id="2b721-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Убедитесь, что служба диагностических данных включена.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-301"><a href="troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy" data-raw-source="[Ensure the diagnostic data service is enabled](troubleshoot-onboarding.md#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)">Ensure the diagnostic data service is enabled</a>.</span></span><br>
<span data-ttu-id="2b721-302">Убедитесь, что параметры и сценарии бортовой установки были развернуты должным образом.</span><span class="sxs-lookup"><span data-stu-id="2b721-302">Check that the onboarding settings and scripts were deployed properly.</span></span> <span data-ttu-id="2b721-303">Попробуйте передиплоять пакеты конфигурации.</span><span class="sxs-lookup"><span data-stu-id="2b721-303">Try to redeploy the configuration packages.</span></span><br>
<span data-ttu-id="2b721-304">См. <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">на сайте onboard Windows 10 devices.</a></span><span class="sxs-lookup"><span data-stu-id="2b721-304">See <a href="configure-endpoints.md" data-raw-source="[Onboard Windows 10 devices](configure-endpoints.md)">Onboard Windows 10 devices</a>.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-305">35</span><span class="sxs-lookup"><span data-stu-id="2b721-305">35</span></span></td>
<td><span data-ttu-id="2b721-306">Служба Microsoft Defender для конечных точек не смогла удалить себя в качестве зависимости от службы подключенных пользователей и службы телеметрии.</span><span class="sxs-lookup"><span data-stu-id="2b721-306">Microsoft Defender for Endpoint service failed to remove itself as a dependency on the Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="2b721-307">Код отказа: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-307">Failure code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-308">В службе телеметрии Windows во время отключения произошла ошибка.</span><span class="sxs-lookup"><span data-stu-id="2b721-308">An error occurred with the Windows telemetry service during offboarding.</span></span> <span data-ttu-id="2b721-309">Процесс offboarding продолжается.</span><span class="sxs-lookup"><span data-stu-id="2b721-309">The offboarding process continues.</span></span>
</td>
<td><span data-ttu-id="2b721-310">Проверьте ошибки в службе диагностических данных Windows.</span><span class="sxs-lookup"><span data-stu-id="2b721-310">Check for errors with the Windows diagnostic data service.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-311">36</span><span class="sxs-lookup"><span data-stu-id="2b721-311">36</span></span></td>
<td><span data-ttu-id="2b721-312">Microsoft Defender для подключенных к конечной точке пользователей и регистрации службы телеметрии успешно.</span><span class="sxs-lookup"><span data-stu-id="2b721-312">Microsoft Defender for Endpoint Connected User Experiences and Telemetry service registration succeeded.</span></span> <span data-ttu-id="2b721-313">Код завершения: <code>variable</code> .</span><span class="sxs-lookup"><span data-stu-id="2b721-313">Completion code: <code>variable</code>.</span></span></td>
<td><span data-ttu-id="2b721-314">Успешно завершена регистрация Defender для конечной точки с помощью службы подключенных пользователей и телеметрии.</span><span class="sxs-lookup"><span data-stu-id="2b721-314">Registering Defender for Endpoint with the Connected User Experiences and Telemetry service completed successfully.</span></span></td>
<td><span data-ttu-id="2b721-315">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-315">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-316">37</span><span class="sxs-lookup"><span data-stu-id="2b721-316">37</span></span></td>
<td><span data-ttu-id="2b721-317">Модуль Microsoft Defender для конечной точки A будет превышать квоту.</span><span class="sxs-lookup"><span data-stu-id="2b721-317">Microsoft Defender for Endpoint A module is about to exceed its quota.</span></span> <span data-ttu-id="2b721-318">Модуль: %1, Квота: {%2} {%3}, Процент использования квот: %4.</span><span class="sxs-lookup"><span data-stu-id="2b721-318">Module: %1, Quota: {%2} {%3}, Percentage of quota utilization: %4.</span></span></td>
<td><span data-ttu-id="2b721-319">Устройство почти использовало выделенную квоту текущего 24-часового окна.</span><span class="sxs-lookup"><span data-stu-id="2b721-319">The device has almost used its allocated quota of the current 24-hour window.</span></span> <span data-ttu-id="2b721-320">Его вот-вот перенабьют.</span><span class="sxs-lookup"><span data-stu-id="2b721-320">It’s about to be throttled.</span></span></td>
<td><span data-ttu-id="2b721-321">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-321">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-322">38</span><span class="sxs-lookup"><span data-stu-id="2b721-322">38</span></span></td>
<td><span data-ttu-id="2b721-323">Подключение к сети определено как низкое.</span><span class="sxs-lookup"><span data-stu-id="2b721-323">Network connection is identified as low.</span></span> <span data-ttu-id="2b721-324">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="2b721-324">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="2b721-325">Дозное подключение: %2, доступ к Интернету: %3, доступная бесплатная сеть: %4.</span><span class="sxs-lookup"><span data-stu-id="2b721-325">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="2b721-326">Устройство использует дозную/платную сеть и будет реже обращаться к серверу.</span><span class="sxs-lookup"><span data-stu-id="2b721-326">The device is using a metered/paid network and will be contacting the server less frequently.</span></span></td>
<td><span data-ttu-id="2b721-327">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-327">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-328">39</span><span class="sxs-lookup"><span data-stu-id="2b721-328">39</span></span></td>
<td><span data-ttu-id="2b721-329">Подключение к сети определено как обычное.</span><span class="sxs-lookup"><span data-stu-id="2b721-329">Network connection is identified as normal.</span></span> <span data-ttu-id="2b721-330">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="2b721-330">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="2b721-331">Дозное подключение: %2, доступ к Интернету: %3, доступная бесплатная сеть: %4.</span><span class="sxs-lookup"><span data-stu-id="2b721-331">Metered connection: %2, internet available: %3, free network available: %4.</span></span></td>
<td><span data-ttu-id="2b721-332">Устройство не использует дозное/платное подключение и будет связываться с сервером в обычном режиме.</span><span class="sxs-lookup"><span data-stu-id="2b721-332">The device isn't using a metered/paid connection and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="2b721-333">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-333">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-334">40</span><span class="sxs-lookup"><span data-stu-id="2b721-334">40</span></span></td>
<td><span data-ttu-id="2b721-335">Состояние батареи определено как низкое.</span><span class="sxs-lookup"><span data-stu-id="2b721-335">Battery state is identified as low.</span></span> <span data-ttu-id="2b721-336">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="2b721-336">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="2b721-337">Состояние батареи: %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-337">Battery state: %2.</span></span></td>
<td><span data-ttu-id="2b721-338">Устройство имеет низкий уровень батареи и реже контактировать с сервером.</span><span class="sxs-lookup"><span data-stu-id="2b721-338">The device has low battery level and will contact the server less frequently.</span></span></td>
<td><span data-ttu-id="2b721-339">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-339">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-340">41</span><span class="sxs-lookup"><span data-stu-id="2b721-340">41</span></span></td>
<td><span data-ttu-id="2b721-341">Состояние батареи определено как нормальное.</span><span class="sxs-lookup"><span data-stu-id="2b721-341">Battery state is identified as normal.</span></span> <span data-ttu-id="2b721-342">Microsoft Defender для конечной точки будет связываться с сервером каждые 1 минуту.</span><span class="sxs-lookup"><span data-stu-id="2b721-342">Microsoft Defender for Endpoint will contact the server every %1 minutes.</span></span> <span data-ttu-id="2b721-343">Состояние батареи: %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-343">Battery state: %2.</span></span></td>
<td><span data-ttu-id="2b721-344">Устройство не имеет низкого уровня батареи и будет связываться с сервером, как обычно.</span><span class="sxs-lookup"><span data-stu-id="2b721-344">The device doesn’t have low battery level and will contact the server as usual.</span></span></td>
<td><span data-ttu-id="2b721-345">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-345">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-346">42</span><span class="sxs-lookup"><span data-stu-id="2b721-346">42</span></span></td>
<td><span data-ttu-id="2b721-347">Компонент Microsoft Defender для конечной точки не выполнил действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-347">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="2b721-348">Компонент: %1, Действие: %2, Тип исключения: %3, Сообщение об исключении: %4</span><span class="sxs-lookup"><span data-stu-id="2b721-348">Component: %1, Action: %2, Exception Type: %3, Exception message: %4</span></span></td>
<td><span data-ttu-id="2b721-349">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="2b721-349">Internal error.</span></span> <span data-ttu-id="2b721-350">Не удалось запустить службу.</span><span class="sxs-lookup"><span data-stu-id="2b721-350">The service failed to start.</span></span></td>
<td><span data-ttu-id="2b721-351">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-351">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-352">43</span><span class="sxs-lookup"><span data-stu-id="2b721-352">43</span></span></td>
<td><span data-ttu-id="2b721-353">Компонент Microsoft Defender для конечной точки не выполнил действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-353">Microsoft Defender for Endpoint component failed to perform action.</span></span> <span data-ttu-id="2b721-354">Компонент: %1, Действие: %2, Тип исключения: %3, Ошибка исключения: %4, Сообщение об исключении: %5</span><span class="sxs-lookup"><span data-stu-id="2b721-354">Component: %1, Action: %2, Exception Type: %3, Exception Error: %4, Exception message: %5</span></span></td>
<td><span data-ttu-id="2b721-355">Внутренняя ошибка.</span><span class="sxs-lookup"><span data-stu-id="2b721-355">Internal error.</span></span> <span data-ttu-id="2b721-356">Не удалось запустить службу.</span><span class="sxs-lookup"><span data-stu-id="2b721-356">The service failed to start.</span></span></td>
<td><span data-ttu-id="2b721-357">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-357">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-358">44</span><span class="sxs-lookup"><span data-stu-id="2b721-358">44</span></span></td>
<td><span data-ttu-id="2b721-359">Отключение службы Defender для конечной точки завершено.</span><span class="sxs-lookup"><span data-stu-id="2b721-359">Offboarding of Defender for Endpoint service completed.</span></span></td>
<td><span data-ttu-id="2b721-360">Служба была отключена.</span><span class="sxs-lookup"><span data-stu-id="2b721-360">The service was offboarded.</span></span></td>
<td><span data-ttu-id="2b721-361">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-361">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-362">45</span><span class="sxs-lookup"><span data-stu-id="2b721-362">45</span></span></td>
<td><span data-ttu-id="2b721-363">Не удалось зарегистрировать и запустить сеанс трассировки событий [%1].</span><span class="sxs-lookup"><span data-stu-id="2b721-363">Failed to register and to start the event trace session [%1].</span></span> <span data-ttu-id="2b721-364">Код ошибки: %2</span><span class="sxs-lookup"><span data-stu-id="2b721-364">Error code: %2</span></span></td>
<td><span data-ttu-id="2b721-365">Ошибка произошла при запуске службы при создании сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-365">An error occurred on service startup while creating ETW session.</span></span> <span data-ttu-id="2b721-366">Это привело к сбою запуска службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-366">This caused service start-up failure.</span></span></td>
<td><span data-ttu-id="2b721-367">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-367">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-368">46</span><span class="sxs-lookup"><span data-stu-id="2b721-368">46</span></span></td>
<td><span data-ttu-id="2b721-369">Не удалось зарегистрировать и запустить сеанс трассировки событий [%1] из-за нехватки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2b721-369">Failed to register and start the event trace session [%1] due to lack of resources.</span></span> <span data-ttu-id="2b721-370">Код ошибки: %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-370">Error code: %2.</span></span> <span data-ttu-id="2b721-371">Это, скорее всего, потому, что существует слишком много активных сеансов трассировки событий.</span><span class="sxs-lookup"><span data-stu-id="2b721-371">This is most likely because there are too many active event trace sessions.</span></span> <span data-ttu-id="2b721-372">Служба будет повторить в течение 1 минуты.</span><span class="sxs-lookup"><span data-stu-id="2b721-372">The service will retry in 1 minute.</span></span></td>
<td><span data-ttu-id="2b721-373">Ошибка произошла при запуске службы при создании сеанса ETW из-за нехватки ресурсов.</span><span class="sxs-lookup"><span data-stu-id="2b721-373">An error occurred on service startup while creating ETW session due to lack of resources.</span></span> <span data-ttu-id="2b721-374">Служба запущена и запущена, но не будет сообщать о событии датчика до запуска сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-374">The service started and is running, but won't report any sensor event until the ETW session is started.</span></span></td>
<td><span data-ttu-id="2b721-375">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-375">Normal operating notification; no action required.</span></span> <span data-ttu-id="2b721-376">Служба будет пытаться начинать сеанс каждую минуту.</span><span class="sxs-lookup"><span data-stu-id="2b721-376">The service will try to start the session every minute.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-377">47</span><span class="sxs-lookup"><span data-stu-id="2b721-377">47</span></span></td>
<td><span data-ttu-id="2b721-378">Успешно зарегистрировался и начал сеанс трассировки событий , восстановленный после предыдущих неудачных попыток.</span><span class="sxs-lookup"><span data-stu-id="2b721-378">Successfully registered and started the event trace session - recovered after previous failed attempts.</span></span></td>
<td><span data-ttu-id="2b721-379">Это событие следует за предыдущим событием после успешного начала сеанса ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-379">This event follows the previous event after successfully starting of the ETW session.</span></span></td>
<td><span data-ttu-id="2b721-380">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-380">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
<td><span data-ttu-id="2b721-381">48</span><span class="sxs-lookup"><span data-stu-id="2b721-381">48</span></span></td>
<td><span data-ttu-id="2b721-382">Не удалось добавить поставщика [%1] в сеанс трассировки событий [%2].</span><span class="sxs-lookup"><span data-stu-id="2b721-382">Failed to add a provider [%1] to event trace session [%2].</span></span> <span data-ttu-id="2b721-383">Код ошибки: %3.</span><span class="sxs-lookup"><span data-stu-id="2b721-383">Error code: %3.</span></span> <span data-ttu-id="2b721-384">Это означает, что события от этого поставщика не будут отчитаться.</span><span class="sxs-lookup"><span data-stu-id="2b721-384">This means that events from this provider will not be reported.</span></span></td>
<td><span data-ttu-id="2b721-385">Не удалось добавить поставщика в сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-385">Failed to add a provider to ETW session.</span></span> <span data-ttu-id="2b721-386">В результате события поставщика не сообщаются.</span><span class="sxs-lookup"><span data-stu-id="2b721-386">As a result, the provider events aren’t reported.</span></span></td>
<td><span data-ttu-id="2b721-387">Проверьте код ошибки.</span><span class="sxs-lookup"><span data-stu-id="2b721-387">Check the error code.</span></span> <span data-ttu-id="2b721-388">Если ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-388">If the error persists contact Support.</span></span></td>
</tr>
</tr>
<tr>
   <td><span data-ttu-id="2b721-389">49</span><span class="sxs-lookup"><span data-stu-id="2b721-389">49</span></span></td>
   <td><span data-ttu-id="2b721-390">Команда конфигурации недействительных облаков получена и проигнорирована.</span><span class="sxs-lookup"><span data-stu-id="2b721-390">Invalid cloud configuration command received and ignored.</span></span> <span data-ttu-id="2b721-391">Версия: %1, состояние: %2, код ошибки: %3, сообщение: %4</span><span class="sxs-lookup"><span data-stu-id="2b721-391">Version: %1, status: %2, error code: %3, message: %4</span></span></td>
   <td><span data-ttu-id="2b721-392">Получил недействительный файл конфигурации из облачной службы, которая была проигнорирована.</span><span class="sxs-lookup"><span data-stu-id="2b721-392">Received an invalid configuration file from the cloud service that was ignored.</span></span></td>
   <td><span data-ttu-id="2b721-393">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-393">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-394">50</span><span class="sxs-lookup"><span data-stu-id="2b721-394">50</span></span></td>
   <td><span data-ttu-id="2b721-395">Новая конфигурация облака успешно применяется.</span><span class="sxs-lookup"><span data-stu-id="2b721-395">New cloud configuration applied successfully.</span></span> <span data-ttu-id="2b721-396">Версия: %1.</span><span class="sxs-lookup"><span data-stu-id="2b721-396">Version: %1.</span></span></td>
   <td><span data-ttu-id="2b721-397">Успешно применена новая конфигурация облачной службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-397">Successfully applied a new configuration from the cloud service.</span></span></td>
   <td><span data-ttu-id="2b721-398">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-398">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-399">51</span><span class="sxs-lookup"><span data-stu-id="2b721-399">51</span></span></td>
   <td><span data-ttu-id="2b721-400">Новая конфигурация облака не применялась, версия: %1.</span><span class="sxs-lookup"><span data-stu-id="2b721-400">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="2b721-401">Успешно применена последняя известная хорошая конфигурация версии %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-401">Successfully applied the last known good configuration, version %2.</span></span></td>
   <td><span data-ttu-id="2b721-402">Получен плохой файл конфигурации из облачной службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-402">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="2b721-403">Последняя известная хорошая конфигурация была применена успешно.</span><span class="sxs-lookup"><span data-stu-id="2b721-403">Last known good configuration was applied successfully.</span></span></td>
   <td><span data-ttu-id="2b721-404">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-404">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-405">52</span><span class="sxs-lookup"><span data-stu-id="2b721-405">52</span></span></td>
   <td><span data-ttu-id="2b721-406">Новая конфигурация облака не применялась, версия: %1.</span><span class="sxs-lookup"><span data-stu-id="2b721-406">New cloud configuration failed to apply, version: %1.</span></span> <span data-ttu-id="2b721-407">Также не удалось применить последнюю хорошую конфигурацию версии %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-407">Also failed to apply last known good configuration, version %2.</span></span> <span data-ttu-id="2b721-408">Успешно применена конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2b721-408">Successfully applied the default configuration.</span></span></td>
   <td><span data-ttu-id="2b721-409">Получен плохой файл конфигурации из облачной службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-409">Received a bad configuration file from the cloud service.</span></span> <span data-ttu-id="2b721-410">Не удалось применить последнюю хорошую конфигурацию , и была применена конфигурация по умолчанию.</span><span class="sxs-lookup"><span data-stu-id="2b721-410">Failed to apply the last known good configuration - and the default configuration was applied.</span></span></td>
   <td><span data-ttu-id="2b721-411">Служба попытается скачать новый файл конфигурации в течение 5 минут.</span><span class="sxs-lookup"><span data-stu-id="2b721-411">The service will attempt to download a new configuration file within 5 minutes.</span></span> <span data-ttu-id="2b721-412">Если вы не видите события #50 - обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-412">If you don't see event #50 - contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-413">53</span><span class="sxs-lookup"><span data-stu-id="2b721-413">53</span></span></td>
   <td><span data-ttu-id="2b721-414">Облачная конфигурация, загруженная из сохраняемого хранилища, версия: %1.</span><span class="sxs-lookup"><span data-stu-id="2b721-414">Cloud configuration loaded from persistent storage, version: %1.</span></span></td>
   <td><span data-ttu-id="2b721-415">Конфигурация загружалась из сохраняемого хранилища при запуске службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-415">The configuration was loaded from persistent storage on service startup.</span></span></td>
   <td><span data-ttu-id="2b721-416">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-416">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-417">55</span><span class="sxs-lookup"><span data-stu-id="2b721-417">55</span></span></td>
   <td><span data-ttu-id="2b721-418">Не удалось создать автологгер Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-418">Failed to create the Secure ETW autologger.</span></span> <span data-ttu-id="2b721-419">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-419">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-420">Не удалось создать безопасный регистратор ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-420">Failed to create the secure ETW logger.</span></span></td>
   <td><span data-ttu-id="2b721-421">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="2b721-421">Reboot the device.</span></span> <span data-ttu-id="2b721-422">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-422">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-423">56</span><span class="sxs-lookup"><span data-stu-id="2b721-423">56</span></span></td>
   <td><span data-ttu-id="2b721-424">Не удалось удалить автологгер Secure ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-424">Failed to remove the Secure ETW autologger.</span></span> <span data-ttu-id="2b721-425">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-425">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-426">Не удалось удалить безопасный сеанс ETW при отключении.</span><span class="sxs-lookup"><span data-stu-id="2b721-426">Failed to remove the secure ETW session on offboarding.</span></span></td>
   <td><span data-ttu-id="2b721-427">Поддержка контактов.</span><span class="sxs-lookup"><span data-stu-id="2b721-427">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-428">57</span><span class="sxs-lookup"><span data-stu-id="2b721-428">57</span></span></td>
   <td><span data-ttu-id="2b721-429">Захват снимка компьютера для устранения неполадок.</span><span class="sxs-lookup"><span data-stu-id="2b721-429">Capturing a snapshot of the machine for troubleshooting purposes.</span></span></td>
   <td><span data-ttu-id="2b721-430">В настоящее время собираются пакеты расследований, также известные как пакет судебно-медицинской экспертизы.</span><span class="sxs-lookup"><span data-stu-id="2b721-430">An investigation package, also known as forensics package, is being collected.</span></span></td>
   <td><span data-ttu-id="2b721-431">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-431">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-432">59</span><span class="sxs-lookup"><span data-stu-id="2b721-432">59</span></span></td>
   <td><span data-ttu-id="2b721-433">Начальная команда: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-433">Starting command: %1</span></span></td>
   <td><span data-ttu-id="2b721-434">Запуск выполнения командной команды ответа.</span><span class="sxs-lookup"><span data-stu-id="2b721-434">Starting response command execution.</span></span></td>
   <td><span data-ttu-id="2b721-435">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-435">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-436">60</span><span class="sxs-lookup"><span data-stu-id="2b721-436">60</span></span></td>
   <td><span data-ttu-id="2b721-437">Не удалось выполнить команду %1, ошибка: %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-437">Failed to run command %1, error: %2.</span></span></td>
   <td><span data-ttu-id="2b721-438">Не удалось выполнить команду ответа.</span><span class="sxs-lookup"><span data-stu-id="2b721-438">Failed to execute response command.</span></span></td>
   <td><span data-ttu-id="2b721-439">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-439">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-440">61</span><span class="sxs-lookup"><span data-stu-id="2b721-440">61</span></span></td>
   <td><span data-ttu-id="2b721-441">Параметры командного сбора данных недействительны: SasUri: %1, compressionLevel: %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-441">Data collection command parameters are invalid: SasUri: %1, compressionLevel: %2.</span></span></td>
   <td><span data-ttu-id="2b721-442">Не удалось прочитать или размыть аргументы команд сбора данных (недействительные аргументы).</span><span class="sxs-lookup"><span data-stu-id="2b721-442">Failed to read or parse the data collection command arguments (invalid arguments).</span></span></td>
   <td><span data-ttu-id="2b721-443">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-443">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-444">62</span><span class="sxs-lookup"><span data-stu-id="2b721-444">62</span></span></td>
   <td><span data-ttu-id="2b721-445">Не удалось запустить службу подключенных пользователей и телеметрии.</span><span class="sxs-lookup"><span data-stu-id="2b721-445">Failed to start Connected User Experiences and Telemetry service.</span></span> <span data-ttu-id="2b721-446">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-446">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-447">Не удалось запустить службу подключенных пользовательских интерфейсов и телеметрии (diagtrack).</span><span class="sxs-lookup"><span data-stu-id="2b721-447">Connected User Experiences and Telemetry (diagtrack) service failed to start.</span></span> <span data-ttu-id="2b721-448">Телеметрия не microsoft Defender для конечной точки не будет отправлена с этого компьютера.</span><span class="sxs-lookup"><span data-stu-id="2b721-448">Non-Microsoft Defender for Endpoint telemetry won't be sent from this machine.</span></span></td>
   <td><span data-ttu-id="2b721-449">Дополнительные подсказки по устранению неполадок в журнале событий: Microsoft-Windows-UniversalTelemetryClient/Operational.</span><span class="sxs-lookup"><span data-stu-id="2b721-449">Look for more troubleshooting hints in the event log: Microsoft-Windows-UniversalTelemetryClient/Operational.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-450">63</span><span class="sxs-lookup"><span data-stu-id="2b721-450">63</span></span></td>
   <td><span data-ttu-id="2b721-451">Обновление типа запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-451">Updating the start type of external service.</span></span> <span data-ttu-id="2b721-452">Имя: %1, фактический тип запуска: %2, ожидаемый тип запуска: %3, код выхода: %4</span><span class="sxs-lookup"><span data-stu-id="2b721-452">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="2b721-453">Обновленный тип запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-453">Updated start type of the external service.</span></span></td>
   <td><span data-ttu-id="2b721-454">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-454">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-455">64</span><span class="sxs-lookup"><span data-stu-id="2b721-455">64</span></span></td>
   <td><span data-ttu-id="2b721-456">Запуск остановленной внешней службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-456">Starting stopped external service.</span></span> <span data-ttu-id="2b721-457">Имя: %1, код выхода: %2</span><span class="sxs-lookup"><span data-stu-id="2b721-457">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="2b721-458">Запуск внешней службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-458">Starting an external service.</span></span></td>
   <td><span data-ttu-id="2b721-459">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-459">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-460">65</span><span class="sxs-lookup"><span data-stu-id="2b721-460">65</span></span></td>
   <td><span data-ttu-id="2b721-461">Не удалось загрузить драйвер компонента событий microsoft Security Component Minifilter.</span><span class="sxs-lookup"><span data-stu-id="2b721-461">Failed to load Microsoft Security Events Component Minifilter driver.</span></span> <span data-ttu-id="2b721-462">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-462">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-463">Не удалось загрузить MsSecFlt.sys файлосистемы.</span><span class="sxs-lookup"><span data-stu-id="2b721-463">Failed to load MsSecFlt.sys filesystem minifilter.</span></span></td>
   <td><span data-ttu-id="2b721-464">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="2b721-464">Reboot the device.</span></span> <span data-ttu-id="2b721-465">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-465">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-466">66</span><span class="sxs-lookup"><span data-stu-id="2b721-466">66</span></span></td>
   <td><span data-ttu-id="2b721-467">Обновление политики: режим задержки - %1</span><span class="sxs-lookup"><span data-stu-id="2b721-467">Policy update: Latency mode - %1</span></span></td>
   <td><span data-ttu-id="2b721-468">Политика частоты C&C была обновлена.</span><span class="sxs-lookup"><span data-stu-id="2b721-468">The C&C connection frequency policy was updated.</span></span></td>
   <td><span data-ttu-id="2b721-469">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-469">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-470">68</span><span class="sxs-lookup"><span data-stu-id="2b721-470">68</span></span></td>
   <td><span data-ttu-id="2b721-471">Тип запуска службы является неожиданным.</span><span class="sxs-lookup"><span data-stu-id="2b721-471">The start type of the service is unexpected.</span></span> <span data-ttu-id="2b721-472">Имя службы: %1, фактический тип запуска: %2, ожидаемый тип запуска: %3</span><span class="sxs-lookup"><span data-stu-id="2b721-472">Service name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="2b721-473">Неожиданный внешний тип запуска службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-473">Unexpected external service start type.</span></span></td>
   <td><span data-ttu-id="2b721-474">Исправление внешнего типа запуска службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-474">Fix the external service start type.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-475">69</span><span class="sxs-lookup"><span data-stu-id="2b721-475">69</span></span></td>
   <td><span data-ttu-id="2b721-476">Служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="2b721-476">The service is stopped.</span></span> <span data-ttu-id="2b721-477">Имя службы: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-477">Service name: %1</span></span></td>
   <td><span data-ttu-id="2b721-478">Внешняя служба остановлена.</span><span class="sxs-lookup"><span data-stu-id="2b721-478">The external service is stopped.</span></span></td>
   <td><span data-ttu-id="2b721-479">Запустите внешнюю службу.</span><span class="sxs-lookup"><span data-stu-id="2b721-479">Start the external service.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-480">70</span><span class="sxs-lookup"><span data-stu-id="2b721-480">70</span></span></td>
   <td><span data-ttu-id="2b721-481">Обновление политики: Разрешить выборку коллекции - %1</span><span class="sxs-lookup"><span data-stu-id="2b721-481">Policy update: Allow sample collection - %1</span></span></td>
   <td><span data-ttu-id="2b721-482">Обновлена политика сбора образцов.</span><span class="sxs-lookup"><span data-stu-id="2b721-482">The sample collection policy was updated.</span></span></td>
   <td><span data-ttu-id="2b721-483">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-483">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-484">71</span><span class="sxs-lookup"><span data-stu-id="2b721-484">71</span></span></td>
   <td><span data-ttu-id="2b721-485">Успешное запуск команды: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-485">Succeeded to run command: %1</span></span></td>
   <td><span data-ttu-id="2b721-486">Команда выполнена успешно.</span><span class="sxs-lookup"><span data-stu-id="2b721-486">The command was executed successfully.</span></span></td>
   <td><span data-ttu-id="2b721-487">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-487">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-488">72</span><span class="sxs-lookup"><span data-stu-id="2b721-488">72</span></span></td>
   <td><span data-ttu-id="2b721-489">Попытался отправить первый полный отчет профиля машины.</span><span class="sxs-lookup"><span data-stu-id="2b721-489">Tried to send first full machine profile report.</span></span> <span data-ttu-id="2b721-490">Код результата: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-490">Result code: %1</span></span></td>
   <td><span data-ttu-id="2b721-491">Только информационная.</span><span class="sxs-lookup"><span data-stu-id="2b721-491">Informational only.</span></span></td>
   <td><span data-ttu-id="2b721-492">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-492">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-493">73</span><span class="sxs-lookup"><span data-stu-id="2b721-493">73</span></span></td>
   <td><span data-ttu-id="2b721-494">Чувство, начиная с платформы: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-494">Sense starting for platform: %1</span></span></td>
   <td><span data-ttu-id="2b721-495">Только информационная.</span><span class="sxs-lookup"><span data-stu-id="2b721-495">Informational only.</span></span></td>
   <td><span data-ttu-id="2b721-496">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-496">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-497">74</span><span class="sxs-lookup"><span data-stu-id="2b721-497">74</span></span></td>
   <td><span data-ttu-id="2b721-498">Тег устройства в реестре превышает ограничение длины.</span><span class="sxs-lookup"><span data-stu-id="2b721-498">Device tag in registry exceeds length limit.</span></span> <span data-ttu-id="2b721-499">Имя тега: %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-499">Tag name: %2.</span></span> <span data-ttu-id="2b721-500">Ограничение длины: %1.</span><span class="sxs-lookup"><span data-stu-id="2b721-500">Length limit: %1.</span></span></td>
   <td><span data-ttu-id="2b721-501">Тег устройства превышает ограничение длины.</span><span class="sxs-lookup"><span data-stu-id="2b721-501">The device tag exceeds the length limit.</span></span></td>
   <td><span data-ttu-id="2b721-502">Используйте более короткий тег устройства.</span><span class="sxs-lookup"><span data-stu-id="2b721-502">Use a shorter device tag.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-503">81</span><span class="sxs-lookup"><span data-stu-id="2b721-503">81</span></span></td>
   <td><span data-ttu-id="2b721-504">Не удалось создать автологгер Microsoft Defender для конечной точки ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-504">Failed to create Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="2b721-505">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-505">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-506">Не удалось создать сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-506">Failed to create the ETW session.</span></span></td>
   <td><span data-ttu-id="2b721-507">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="2b721-507">Reboot the device.</span></span> <span data-ttu-id="2b721-508">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-508">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-509">82</span><span class="sxs-lookup"><span data-stu-id="2b721-509">82</span></span></td>
   <td><span data-ttu-id="2b721-510">Не удалось удалить автологгер Microsoft Defender для конечной точки ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-510">Failed to remove Microsoft Defender for Endpoint ETW autologger.</span></span> <span data-ttu-id="2b721-511">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-511">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-512">Не удалось удалить сеанс ETW.</span><span class="sxs-lookup"><span data-stu-id="2b721-512">Failed to delete the ETW session.</span></span></td>
   <td><span data-ttu-id="2b721-513">Поддержка контактов.</span><span class="sxs-lookup"><span data-stu-id="2b721-513">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-514">84</span><span class="sxs-lookup"><span data-stu-id="2b721-514">84</span></span></td>
   <td><span data-ttu-id="2b721-515">Установите Защитник Windows режим работы антивируса.</span><span class="sxs-lookup"><span data-stu-id="2b721-515">Set Windows Defender Antivirus running mode.</span></span> <span data-ttu-id="2b721-516">Пассивный режим force: %1, код результатов: %2.</span><span class="sxs-lookup"><span data-stu-id="2b721-516">Force passive mode: %1, result code: %2.</span></span></td>
   <td><span data-ttu-id="2b721-517">Установите режим работы защитника (активный или пассивный).</span><span class="sxs-lookup"><span data-stu-id="2b721-517">Set defender running mode (active or passive).</span></span></td>
   <td><span data-ttu-id="2b721-518">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-518">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-519">85</span><span class="sxs-lookup"><span data-stu-id="2b721-519">85</span></span></td>
   <td><span data-ttu-id="2b721-520">Не удалось вызвать Microsoft Defender для конечной точки, исполняемой.</span><span class="sxs-lookup"><span data-stu-id="2b721-520">Failed to trigger Microsoft Defender for Endpoint executable.</span></span> <span data-ttu-id="2b721-521">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-521">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-522">Выполнение SenseIR в главной роли не удалось.</span><span class="sxs-lookup"><span data-stu-id="2b721-522">Starring SenseIR executable failed.</span></span></td>
   <td><span data-ttu-id="2b721-523">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="2b721-523">Reboot the device.</span></span> <span data-ttu-id="2b721-524">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-524">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-525">86</span><span class="sxs-lookup"><span data-stu-id="2b721-525">86</span></span></td>
   <td><span data-ttu-id="2b721-526">При запуске снова остановлена внешняя служба, которая должна быть вверх.</span><span class="sxs-lookup"><span data-stu-id="2b721-526">Starting again stopped external service that should be up.</span></span> <span data-ttu-id="2b721-527">Имя: %1, код выхода: %2</span><span class="sxs-lookup"><span data-stu-id="2b721-527">Name: %1, exit code: %2</span></span></td>
   <td><span data-ttu-id="2b721-528">Запуск внешней службы снова.</span><span class="sxs-lookup"><span data-stu-id="2b721-528">Starting the external service again.</span></span></td>
   <td><span data-ttu-id="2b721-529">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-529">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-530">87</span><span class="sxs-lookup"><span data-stu-id="2b721-530">87</span></span></td>
   <td><span data-ttu-id="2b721-531">Не удается запустить внешнюю службу.</span><span class="sxs-lookup"><span data-stu-id="2b721-531">Cannot start the external service.</span></span> <span data-ttu-id="2b721-532">Имя: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-532">Name: %1</span></span></td>
   <td><span data-ttu-id="2b721-533">Не удалось запустить внешнюю службу.</span><span class="sxs-lookup"><span data-stu-id="2b721-533">Failed to start the external service.</span></span></td>
   <td><span data-ttu-id="2b721-534">Поддержка контактов.</span><span class="sxs-lookup"><span data-stu-id="2b721-534">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-535">88</span><span class="sxs-lookup"><span data-stu-id="2b721-535">88</span></span></td>
   <td><span data-ttu-id="2b721-536">Повторное обновление типа запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-536">Updating the start type of external service again.</span></span> <span data-ttu-id="2b721-537">Имя: %1, фактический тип запуска: %2, ожидаемый тип запуска: %3, код выхода: %4</span><span class="sxs-lookup"><span data-stu-id="2b721-537">Name: %1, actual start type: %2, expected start type: %3, exit code: %4</span></span></td>
   <td><span data-ttu-id="2b721-538">Обновлен тип запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-538">Updated the start type of the external service.</span></span></td>
   <td><span data-ttu-id="2b721-539">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-539">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-540">89</span><span class="sxs-lookup"><span data-stu-id="2b721-540">89</span></span></td>
   <td><span data-ttu-id="2b721-541">Не удается обновить начните тип внешней службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-541">Cannot update the start type of external service.</span></span> <span data-ttu-id="2b721-542">Имя: %1, фактический тип запуска: %2, ожидаемый тип запуска: %3</span><span class="sxs-lookup"><span data-stu-id="2b721-542">Name: %1, actual start type: %2, expected start type: %3</span></span></td>
   <td><span data-ttu-id="2b721-543">Не может обновить тип запуска внешней службы.</span><span class="sxs-lookup"><span data-stu-id="2b721-543">Can't update the start type of the external service.</span></span></td>
   <td><span data-ttu-id="2b721-544">Поддержка контактов.</span><span class="sxs-lookup"><span data-stu-id="2b721-544">Contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-545">90</span><span class="sxs-lookup"><span data-stu-id="2b721-545">90</span></span></td>
   <td><span data-ttu-id="2b721-546">Не удалось настроить system Guard Runtime Monitor для подключения к облачной службе в geo-region %1.</span><span class="sxs-lookup"><span data-stu-id="2b721-546">Failed to configure System Guard Runtime Monitor to connect to cloud service in geo-region %1.</span></span> <span data-ttu-id="2b721-547">Код отказа: %2</span><span class="sxs-lookup"><span data-stu-id="2b721-547">Failure code: %2</span></span></td>
   <td><span data-ttu-id="2b721-548">System Guard Runtime Monitor не будет отправлять данные проверки в облачную службу.</span><span class="sxs-lookup"><span data-stu-id="2b721-548">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="2b721-549">Проверьте разрешения на пути регистрации: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="2b721-549">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="2b721-550">Если проблем не обнаружено, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-550">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-551">91</span><span class="sxs-lookup"><span data-stu-id="2b721-551">91</span></span></td>
   <td><span data-ttu-id="2b721-552">Не удалось удалить сведения о георегиране System Guard Runtime Monitor.</span><span class="sxs-lookup"><span data-stu-id="2b721-552">Failed to remove System Guard Runtime Monitor geo-region information.</span></span> <span data-ttu-id="2b721-553">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-553">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-554">System Guard Runtime Monitor не будет отправлять данные проверки в облачную службу.</span><span class="sxs-lookup"><span data-stu-id="2b721-554">System Guard Runtime Monitor won't send attestation data to the cloud service.</span></span></td>
   <td><span data-ttu-id="2b721-555">Проверьте разрешения на пути регистрации: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span><span class="sxs-lookup"><span data-stu-id="2b721-555">Check the permissions on register path: "HKLM\Software\Microsoft\Windows\CurrentVersion\Sgrm".</span></span> <span data-ttu-id="2b721-556">Если проблем не обнаружено, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-556">If no issues spotted, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-557">92</span><span class="sxs-lookup"><span data-stu-id="2b721-557">92</span></span></td>
   <td><span data-ttu-id="2b721-558">Прекращение отправки квоты кибер-данных датчика из-за превышения квоты данных.</span><span class="sxs-lookup"><span data-stu-id="2b721-558">Stopping sending sensor cyber data quota because data quota is exceeded.</span></span> <span data-ttu-id="2b721-559">Возобновит отправку после того, как пройдет период квоты.</span><span class="sxs-lookup"><span data-stu-id="2b721-559">Will resume sending once quota period passes.</span></span> <span data-ttu-id="2b721-560">Маска состояния: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-560">State Mask: %1</span></span></td>
   <td><span data-ttu-id="2b721-561">Превышение лимита регулирования.</span><span class="sxs-lookup"><span data-stu-id="2b721-561">Exceed throttling limit.</span></span></td>
   <td><span data-ttu-id="2b721-562">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-562">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-563">93</span><span class="sxs-lookup"><span data-stu-id="2b721-563">93</span></span></td>
   <td><span data-ttu-id="2b721-564">Повторное отправка данных кибер-датчика.</span><span class="sxs-lookup"><span data-stu-id="2b721-564">Resuming sending sensor cyber data.</span></span> <span data-ttu-id="2b721-565">Маска состояния: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-565">State Mask: %1</span></span></td>
   <td><span data-ttu-id="2b721-566">Возобновление отправки кибер-данных.</span><span class="sxs-lookup"><span data-stu-id="2b721-566">Resume cyber data submission.</span></span></td>
   <td><span data-ttu-id="2b721-567">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-567">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-568">94</span><span class="sxs-lookup"><span data-stu-id="2b721-568">94</span></span></td>
   <td><span data-ttu-id="2b721-569">Начался microsoft Defender для исполняемой конечной точки</span><span class="sxs-lookup"><span data-stu-id="2b721-569">Microsoft Defender for Endpoint executable has started</span></span></td>
   <td><span data-ttu-id="2b721-570">Начался исполняемый SenseCE.</span><span class="sxs-lookup"><span data-stu-id="2b721-570">The SenseCE executable has started.</span></span></td>
   <td><span data-ttu-id="2b721-571">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-571">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-572">95</span><span class="sxs-lookup"><span data-stu-id="2b721-572">95</span></span></td>
   <td><span data-ttu-id="2b721-573">Microsoft Defender для исполняемой конечной точки завершилась</span><span class="sxs-lookup"><span data-stu-id="2b721-573">Microsoft Defender for Endpoint executable has ended</span></span></td>
   <td><span data-ttu-id="2b721-574">Исполняемый SenseCE завершился.</span><span class="sxs-lookup"><span data-stu-id="2b721-574">The SenseCE executable has ended.</span></span></td>
   <td><span data-ttu-id="2b721-575">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-575">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-576">96</span><span class="sxs-lookup"><span data-stu-id="2b721-576">96</span></span></td>
   <td><span data-ttu-id="2b721-577">Microsoft Defender для endpoint Init вызвал.</span><span class="sxs-lookup"><span data-stu-id="2b721-577">Microsoft Defender for Endpoint Init has called.</span></span> <span data-ttu-id="2b721-578">Код результата: %2</span><span class="sxs-lookup"><span data-stu-id="2b721-578">Result code: %2</span></span></td>
   <td><span data-ttu-id="2b721-579">Исполняемый SenseCE вызвал инициализацию MCE.</span><span class="sxs-lookup"><span data-stu-id="2b721-579">The SenseCE executable has called MCE initialization.</span></span></td>
   <td><span data-ttu-id="2b721-580">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-580">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-581">97</span><span class="sxs-lookup"><span data-stu-id="2b721-581">97</span></span></td>
   <td><span data-ttu-id="2b721-582">Существуют проблемы с подключением к облаку для сценария DLP</span><span class="sxs-lookup"><span data-stu-id="2b721-582">There are connectivity issues to the Cloud for the DLP scenario</span></span></td>
   <td><span data-ttu-id="2b721-583">Существуют проблемы сетевого подключения, влияющие на поток классификации DLP.</span><span class="sxs-lookup"><span data-stu-id="2b721-583">There are network connectivity issues that affect the DLP classification flow.</span></span></td>
   <td><span data-ttu-id="2b721-584">Проверьте подключение к сети.</span><span class="sxs-lookup"><span data-stu-id="2b721-584">Check the network connectivity.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-585">98</span><span class="sxs-lookup"><span data-stu-id="2b721-585">98</span></span></td>
   <td><span data-ttu-id="2b721-586">Подключение к облаку для сценария DLP восстановлено</span><span class="sxs-lookup"><span data-stu-id="2b721-586">The connectivity to the Cloud for the DLP scenario has been restored</span></span></td>
   <td><span data-ttu-id="2b721-587">Подключение к сети восстановлено, и поток классификации DLP может продолжаться.</span><span class="sxs-lookup"><span data-stu-id="2b721-587">The connectivity to the network was restored and the DLP classification flow can continue.</span></span></td>
   <td><span data-ttu-id="2b721-588">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-588">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-589">99</span><span class="sxs-lookup"><span data-stu-id="2b721-589">99</span></span></td>
   <td><span data-ttu-id="2b721-590">Sense столкнулась со следующей ошибкой при общении с сервером: (%1).</span><span class="sxs-lookup"><span data-stu-id="2b721-590">Sense has encountered the following error while communicating with server: (%1).</span></span> <span data-ttu-id="2b721-591">Результат: (%2)</span><span class="sxs-lookup"><span data-stu-id="2b721-591">Result: (%2)</span></span></td>
   <td><span data-ttu-id="2b721-592">Произошла ошибка связи.</span><span class="sxs-lookup"><span data-stu-id="2b721-592">A communication error occurred.</span></span></td>
   <td><span data-ttu-id="2b721-593">Дополнительные сведения о следующих событиях в журнале событий.</span><span class="sxs-lookup"><span data-stu-id="2b721-593">Check the following events in the event log for further details.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-594">100</span><span class="sxs-lookup"><span data-stu-id="2b721-594">100</span></span></td>
   <td><span data-ttu-id="2b721-595">Не удалось запустить Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="2b721-595">Microsoft Defender for Endpoint executable failed to start.</span></span> <span data-ttu-id="2b721-596">Код отказа: %1</span><span class="sxs-lookup"><span data-stu-id="2b721-596">Failure code: %1</span></span></td>
   <td><span data-ttu-id="2b721-597">Не удалось запустить исполняемый SenseCE.</span><span class="sxs-lookup"><span data-stu-id="2b721-597">The SenseCE executable has failed to start.</span></span></td>
   <td><span data-ttu-id="2b721-598">Перезагрузка устройства.</span><span class="sxs-lookup"><span data-stu-id="2b721-598">Reboot the device.</span></span> <span data-ttu-id="2b721-599">Если эта ошибка сохраняется, обратитесь в службу поддержки.</span><span class="sxs-lookup"><span data-stu-id="2b721-599">If this error persists, contact Support.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-600">102</span><span class="sxs-lookup"><span data-stu-id="2b721-600">102</span></span></td>
   <td><span data-ttu-id="2b721-601">Начался microsoft Defender для обнаружения конечных точек сети и выполнения ответных действий</span><span class="sxs-lookup"><span data-stu-id="2b721-601">Microsoft Defender for Endpoint Network Detection and Response executable has started</span></span></td>
   <td><span data-ttu-id="2b721-602">Начался исполняемый SenseNdr.</span><span class="sxs-lookup"><span data-stu-id="2b721-602">The SenseNdr executable has started.</span></span></td>
   <td><span data-ttu-id="2b721-603">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-603">Normal operating notification; no action required.</span></span></td>
</tr>
<tr>
   <td><span data-ttu-id="2b721-604">103</span><span class="sxs-lookup"><span data-stu-id="2b721-604">103</span></span></td>
   <td><span data-ttu-id="2b721-605">Microsoft Defender для обнаружения конечных точек сети и выполнения ответов завершен</span><span class="sxs-lookup"><span data-stu-id="2b721-605">Microsoft Defender for Endpoint Network Detection and Response executable has ended</span></span></td>
   <td><span data-ttu-id="2b721-606">Выполнение SenseNdr завершено.</span><span class="sxs-lookup"><span data-stu-id="2b721-606">The SenseNdr executable has ended.</span></span></td>
   <td><span data-ttu-id="2b721-607">Нормальное операционное уведомление; никаких действий.</span><span class="sxs-lookup"><span data-stu-id="2b721-607">Normal operating notification; no action required.</span></span></td>
</tr>
</tbody>
</table>

><span data-ttu-id="2b721-608">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="2b721-608">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="2b721-609">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="2b721-609">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-eventerrorcodes-belowfoldlink)

## <a name="related-topics"></a><span data-ttu-id="2b721-610">Похожие темы</span><span class="sxs-lookup"><span data-stu-id="2b721-610">Related topics</span></span>
- [<span data-ttu-id="2b721-611">Подключение устройств Windows 10</span><span class="sxs-lookup"><span data-stu-id="2b721-611">Onboard Windows 10 devices</span></span>](configure-endpoints.md)
- [<span data-ttu-id="2b721-612">Настройка параметров прокси-сервера устройства и подключения к Интернету</span><span class="sxs-lookup"><span data-stu-id="2b721-612">Configure device proxy and Internet connectivity settings</span></span>](configure-proxy-internet.md)
- [<span data-ttu-id="2b721-613">Устранение неполадок Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="2b721-613">Troubleshoot Microsoft Defender for Endpoint</span></span>](troubleshoot-onboarding.md)
