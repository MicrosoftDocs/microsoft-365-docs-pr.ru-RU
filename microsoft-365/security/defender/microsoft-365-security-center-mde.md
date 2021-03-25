---
title: Защитник Microsoft для конечной точки в центре безопасности Microsoft 365
description: Узнайте об изменениях из Центра безопасности Защитника Майкрософт в центр безопасности Microsoft 365
keywords: Начало работы с центром безопасности Microsoft 365, OATP, MDATP, MDO, MDE, единой области стекла, конвергентного портала, портала безопасности, портала безопасности защитника
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.openlocfilehash: b580c6f20ed3b242fc0bc239a49fe89ccc09d013
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199199"
---
# <a name="microsoft-defender-for-endpoint-in-the-microsoft-365-security-center"></a><span data-ttu-id="f3181-104">Защитник Microsoft для конечной точки в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f3181-104">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="f3181-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="f3181-105">**Applies to:**</span></span>

- [<span data-ttu-id="f3181-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="f3181-106">Microsoft 365 Defender</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="f3181-107">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="f3181-107">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="f3181-108">Microsoft Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="f3181-108">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)

<span data-ttu-id="f3181-109">Улучшенный [центр безопасности Microsoft 365](overview-security-center.md) объединяет возможности безопасности, которые защищают, обнаруживают, исследуют и реагируют на угрозы электронной почты, совместной работы, удостоверений и [https://security.microsoft.com](https://security.microsoft.com) устройств.</span><span class="sxs-lookup"><span data-stu-id="f3181-109">The improved [Microsoft 365 security center](overview-security-center.md) at [https://security.microsoft.com](https://security.microsoft.com) combines security capabilities that protect, detect, investigate, and respond to email, collaboration, identity, and device threats.</span></span> <span data-ttu-id="f3181-110">Этот центр безопасности объединяет функциональные возможности существующих порталов безопасности Майкрософт, включая Центр безопасности Защитника Майкрософт и Центр безопасности Office 365 & соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="f3181-110">This security center brings together functionality from existing Microsoft security portals, including Microsoft Defender Security Center and the Office 365 Security & Compliance center.</span></span>

<span data-ttu-id="f3181-111">Если вы знакомы с Центром безопасности Защитника Майкрософт, в этой статье описаны некоторые изменения и улучшения в улучшенном центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3181-111">If you're familiar with the Microsoft Defender Security Center, this article helps describe some of the changes and improvements in the improved Microsoft 365 security center.</span></span> <span data-ttu-id="f3181-112">Однако необходимо помнить о некоторых новых и обновленных элементах.</span><span class="sxs-lookup"><span data-stu-id="f3181-112">However there are some new and updated elements to be aware of.</span></span>

<span data-ttu-id="f3181-113">Исторически центр безопасности [Microsoft Defender](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) был домом для Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f3181-113">Historically, the [Microsoft Defender Security Center](/windows/security/threat-protection/microsoft-defender-atp/portal-overview) has been the home for Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="f3181-114">Группы безопасности предприятия использовали его для мониторинга и реагирования на оповещения о потенциальной постоянной активности угроз или нарушениях данных.</span><span class="sxs-lookup"><span data-stu-id="f3181-114">Enterprise security teams have used it to monitor and help responding to alerts of potential advanced persistent threat activity or data breaches.</span></span> <span data-ttu-id="f3181-115">Чтобы уменьшить число порталов, центр безопасности Microsoft 365 станет домом для мониторинга и управления безопасностью в вашей microsoft identities, data, devices, apps и infrastructure.</span><span class="sxs-lookup"><span data-stu-id="f3181-115">To help reduce the number of portals, the Microsoft 365 security center will be the home for monitoring and managing security across your Microsoft identities, data, devices, apps, and infrastructure.</span></span>

<span data-ttu-id="f3181-116">Microsoft Defender для конечной точки в центре безопасности Microsoft 365 поддерживает предоставление доступа к управляемым поставщикам служб безопасности [(MSSP)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) таким же образом, как и доступ к центру безопасности [Microsoft Defender.](mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="f3181-116">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same way [access is granted in the Microsoft Defender security center](mssp-access.md).</span></span>


> [!IMPORTANT]
> <span data-ttu-id="f3181-117">То, что вы видите в центре безопасности Microsoft 365, зависит от текущих подписок.</span><span class="sxs-lookup"><span data-stu-id="f3181-117">What you see in the Microsoft 365 security center depends on your current subscriptions.</span></span> <span data-ttu-id="f3181-118">Например, если у вас нет лицензии на Microsoft Defender для Office 365, то раздел & совместной работы не будет показан.</span><span class="sxs-lookup"><span data-stu-id="f3181-118">For example, if you don't have a license for Microsoft Defender for Office 365, then the Email & Collaboration section will not be shown.</span></span>

>[!Note]
><span data-ttu-id="f3181-119">Новый единый портал не доступен для:</span><span class="sxs-lookup"><span data-stu-id="f3181-119">The new unified portal is not available for:</span></span>
>- <span data-ttu-id="f3181-120">Облако сообщества правительства США (GCC)</span><span class="sxs-lookup"><span data-stu-id="f3181-120">US Government Community Cloud (GCC)</span></span>
>- <span data-ttu-id="f3181-121">Облачное облако государственного сообщества США (GCC High)</span><span class="sxs-lookup"><span data-stu-id="f3181-121">US Government Community Cloud High (GCC High)</span></span>
>- <span data-ttu-id="f3181-122">Министерство обороны США</span><span class="sxs-lookup"><span data-stu-id="f3181-122">US Department of Defense</span></span>
>- <span data-ttu-id="f3181-123">Все государственные учреждения США с коммерческими лицензиями</span><span class="sxs-lookup"><span data-stu-id="f3181-123">All US government institutions with commercial licenses</span></span>

<span data-ttu-id="f3181-124">Взгляните на улучшенный центр безопасности Microsoft 365: [https://security.microsoft.com](https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="f3181-124">Take a look at the improved Microsoft 365 security center: [https://security.microsoft.com](https://security.microsoft.com).</span></span>

<span data-ttu-id="f3181-125">Дополнительные сведения о преимуществах: [Обзор центра безопасности Microsoft 365](overview-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="f3181-125">Learn more about the benefits: [Overview of the Microsoft 365 security center](overview-security-center.md)</span></span>

## <a name="whats-changed"></a><span data-ttu-id="f3181-126">Что изменилось</span><span class="sxs-lookup"><span data-stu-id="f3181-126">What's changed</span></span>

<span data-ttu-id="f3181-127">Эта таблица является краткой ссылкой на изменения между Центром безопасности Защитника Майкрософт и центром безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3181-127">This table is a quick reference of the changes between the Microsoft Defender Security Center and the Microsoft 365 security center.</span></span>

### <a name="alerts-and-actions"></a><span data-ttu-id="f3181-128">Оповещений и действий</span><span class="sxs-lookup"><span data-stu-id="f3181-128">Alerts and actions</span></span>

|<span data-ttu-id="f3181-129">**Область**</span><span class="sxs-lookup"><span data-stu-id="f3181-129">**Area**</span></span>  |<span data-ttu-id="f3181-130">**Описание изменения**</span><span class="sxs-lookup"><span data-stu-id="f3181-130">**Description of change**</span></span> |
|---------|---------|
| [<span data-ttu-id="f3181-131">Оповещений & инцидентов</span><span class="sxs-lookup"><span data-stu-id="f3181-131">Incidents & alerts</span></span>](incidents-overview.md)  | <span data-ttu-id="f3181-132">В центре безопасности Microsoft 365 вы можете управлять инцидентами и оповещениями во всех конечных точках, электронной почте и удостоверениях.</span><span class="sxs-lookup"><span data-stu-id="f3181-132">In the Microsoft 365 security center, you can manage incidents and alerts across all of your endpoints, email, and identities.</span></span> <span data-ttu-id="f3181-133">Мы сближались с опытом, чтобы легче находить связанные события.</span><span class="sxs-lookup"><span data-stu-id="f3181-133">We've converged the experience to help you find related events more easily.</span></span> <span data-ttu-id="f3181-134">Дополнительные сведения см. в [обзоре инцидентов.](incidents-overview.md)</span><span class="sxs-lookup"><span data-stu-id="f3181-134">For more information, see [Incidents Overview](incidents-overview.md).</span></span>   |
| [<span data-ttu-id="f3181-135">Охота</span><span class="sxs-lookup"><span data-stu-id="f3181-135">Hunting</span></span>](advanced-hunting-overview.md)  |  <span data-ttu-id="f3181-136">Изменение пользовательских правил обнаружения, созданных в Microsoft Defender для конечной точки, чтобы включить таблицы удостоверений и электронной почты, автоматически перемещает их в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f3181-136">Modifying custom detection rules created in Microsoft Defender for Endpoint to include identity and email tables automatically moves them to Microsoft 365 Defender.</span></span> <span data-ttu-id="f3181-137">Соответствующие оповещения также будут отображаться в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f3181-137">Their corresponding alerts will also appear in Microsoft 365 Defender.</span></span> <span data-ttu-id="f3181-138">Дополнительные сведения об этих изменениях читайте в публикации ["Миграция пользовательских правил обнаружения".](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules)</span><span class="sxs-lookup"><span data-stu-id="f3181-138">For more details about these changes, read [Migrate custom detection rules](advanced-hunting-migrate-from-mde.md#migrate-custom-detection-rules).</span></span> <br><br><span data-ttu-id="f3181-139">Таблица `DeviceAlertEvents` для продвинутой охоты недоступна в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="f3181-139">The `DeviceAlertEvents` table for advanced hunting isn't available in Microsoft 365 Defender.</span></span> <span data-ttu-id="f3181-140">Чтобы запрашивать сведения о оповещениях, определенных для устройств в Microsoft 365 Defender, можно использовать таблицы и таблицы для размещения дополнительных сведений из различных `AlertInfo` `AlertEvidence` источников.</span><span class="sxs-lookup"><span data-stu-id="f3181-140">To query device-specific alert information in Microsoft 365 Defender, you can use the `AlertInfo` and `AlertEvidence` tables to accommodate even more information from a diverse set of sources.</span></span> <span data-ttu-id="f3181-141">Создайте следующий запрос, связанный с устройством, [следуя запросам Write без DeviceAlertEvents.](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents)</span><span class="sxs-lookup"><span data-stu-id="f3181-141">Craft your next device-related query by following [Write queries without DeviceAlertEvents](advanced-hunting-migrate-from-mde.md#write-queries-without-devicealertevents).</span></span>|
|[<span data-ttu-id="f3181-142">Центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="f3181-142">Action center</span></span>](m365d-action-center.md)    | <span data-ttu-id="f3181-143">Списки ожидающих и завершенных действий, принятых после автоматических расследований и действий по исправлению.</span><span class="sxs-lookup"><span data-stu-id="f3181-143">Lists pending and completed actions that were taken following automated investigations and remediation actions.</span></span> <span data-ttu-id="f3181-144">Ранее центр действий Центра безопасности Microsoft Defender перечислил ожидающих и завершенных действий по исправлению действий, принятых только на устройствах, в то время как автоматические расследования перечислены оповещения и состояние.</span><span class="sxs-lookup"><span data-stu-id="f3181-144">Formerly, the Action center in the Microsoft Defender Security Center listed pending and completed actions for remediation actions taken on devices only, while Automated investigations listed alerts and status.</span></span> <span data-ttu-id="f3181-145">В улучшенном центре безопасности Microsoft 365 Центр действий объединяет действия по исправлению и расследования по электронной почте, устройствам и пользователям — все в одном расположении.</span><span class="sxs-lookup"><span data-stu-id="f3181-145">In the  improved Microsoft 365 security center, the Action center brings together remediation actions and investigations across email, devices, and users—all in one location.</span></span>  |
| [<span data-ttu-id="f3181-146">Аналитика угроз</span><span class="sxs-lookup"><span data-stu-id="f3181-146">Threat analytics</span></span>](threat-analytics.md) |  <span data-ttu-id="f3181-147">Перемещается в верхнюю часть панели навигации для упростить обнаружение и использование.</span><span class="sxs-lookup"><span data-stu-id="f3181-147">Moved to the top of the navigation bar for easier discovery and use.</span></span> <span data-ttu-id="f3181-148">Теперь включает сведения об угрозах как для конечных точек, так и для электронной почты и совместной работы.</span><span class="sxs-lookup"><span data-stu-id="f3181-148">Now includes threat information for both endpoints and email and collaboration.</span></span>    |

### <a name="endpoints"></a><span data-ttu-id="f3181-149">Конечные точки</span><span class="sxs-lookup"><span data-stu-id="f3181-149">Endpoints</span></span>

|<span data-ttu-id="f3181-150">**Область**</span><span class="sxs-lookup"><span data-stu-id="f3181-150">**Area**</span></span>  |<span data-ttu-id="f3181-151">**Описание изменения**</span><span class="sxs-lookup"><span data-stu-id="f3181-151">**Description of change**</span></span>  |
|---------|---------|
|<span data-ttu-id="f3181-152">Поиск</span><span class="sxs-lookup"><span data-stu-id="f3181-152">Search</span></span>   |  <span data-ttu-id="f3181-153">Вместо того, чтобы быть в заголовке, в разделе Конечные точки перемещается панели поиска Microsoft Defender for Endpoint.</span><span class="sxs-lookup"><span data-stu-id="f3181-153">Instead of being in the heading, Microsoft Defender for Endpoint search bar is moving under the Endpoints section.</span></span> <span data-ttu-id="f3181-154">Вы можете продолжать поиск устройств, файлов, пользователей, URL-адресов, IPs, уязвимостей, программного обеспечения и рекомендаций.</span><span class="sxs-lookup"><span data-stu-id="f3181-154">You can continue to search for devices, files, users, URLs, IPs, vulnerabilities, software, and recommendations.</span></span>  |
|[<span data-ttu-id="f3181-155">Панель мониторинга</span><span class="sxs-lookup"><span data-stu-id="f3181-155">Dashboard</span></span>](/windows/security/threat-protection/microsoft-defender-atp/security-operations-dashboard)   |  <span data-ttu-id="f3181-156">Это панель мониторинга операций безопасности.</span><span class="sxs-lookup"><span data-stu-id="f3181-156">This is your security operations dashboard.</span></span> <span data-ttu-id="f3181-157">Сведения о том, сколько активных оповещений было срабатывает, какие устройства находятся под угрозой, какие пользователи находятся в опасности, и уровень серьезности для оповещений, устройств и пользователей.</span><span class="sxs-lookup"><span data-stu-id="f3181-157">See an overview of how many active alerts were triggered, which devices are at risk, which users are at risk, and severity level for alerts, devices, and users.</span></span> <span data-ttu-id="f3181-158">Вы также можете узнать, есть ли у устройств проблемы с датчиками, общее состояние службы и как были обнаружены все неурегулированные оповещения.</span><span class="sxs-lookup"><span data-stu-id="f3181-158">You can also see if any devices have sensor issues, your overall service health, and how any unresolved alerts were detected.</span></span> |
|<span data-ttu-id="f3181-159">Инвентаризация устройств</span><span class="sxs-lookup"><span data-stu-id="f3181-159">Device inventory</span></span> | <span data-ttu-id="f3181-160">Никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="f3181-160">No changes.</span></span> |
|[<span data-ttu-id="f3181-161">Управление уязвимостями</span><span class="sxs-lookup"><span data-stu-id="f3181-161">Vulnerability management</span></span>](/windows/security/threat-protection/microsoft-defender-atp/next-gen-threat-and-vuln-mgt)    |    <span data-ttu-id="f3181-162">Имя было сокращено, чтобы поместиться в области навигации.</span><span class="sxs-lookup"><span data-stu-id="f3181-162">Name was shortened to fit in the navigation pane.</span></span> <span data-ttu-id="f3181-163">Это то же самое, что и раздел управления угрозами и уязвимостями со всеми страницами под ними.</span><span class="sxs-lookup"><span data-stu-id="f3181-163">It's the same as the threat and vulnerability management section, with all the pages underneath.</span></span>     |
| <span data-ttu-id="f3181-164">Партнеры и API</span><span class="sxs-lookup"><span data-stu-id="f3181-164">Partners and APIs</span></span> | <span data-ttu-id="f3181-165">Никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="f3181-165">No changes.</span></span> |
| <span data-ttu-id="f3181-166">Оценки & руководства</span><span class="sxs-lookup"><span data-stu-id="f3181-166">Evaluations & tutorials</span></span>    |     <span data-ttu-id="f3181-167">Новые возможности тестирования и обучения.</span><span class="sxs-lookup"><span data-stu-id="f3181-167">New testing and learning capabilities.</span></span>     |
| <span data-ttu-id="f3181-168">среда управления конфигурацией;</span><span class="sxs-lookup"><span data-stu-id="f3181-168">Configuration management</span></span>   |  <span data-ttu-id="f3181-169">Никаких изменений.</span><span class="sxs-lookup"><span data-stu-id="f3181-169">No changes.</span></span>  |

> [!NOTE]
> <span data-ttu-id="f3181-170">**Автоматическое расследование и исправление** теперь являются частью инцидентов.</span><span class="sxs-lookup"><span data-stu-id="f3181-170">**Automatic investigation and remediation** is now a part of  incidents.</span></span> <span data-ttu-id="f3181-171">События автоматического расследования и исправлений можно увидеть **на вкладке Incident > Investigation.**</span><span class="sxs-lookup"><span data-stu-id="f3181-171">You can see Automated  investigation and remediation events in the **Incident > Investigation** tab.</span></span>

### <a name="access-and-reporting"></a><span data-ttu-id="f3181-172">Доступ и отчеты</span><span class="sxs-lookup"><span data-stu-id="f3181-172">Access and reporting</span></span>

|<span data-ttu-id="f3181-173">**Область**</span><span class="sxs-lookup"><span data-stu-id="f3181-173">**Area**</span></span>  |<span data-ttu-id="f3181-174">**Описание изменения**</span><span class="sxs-lookup"><span data-stu-id="f3181-174">**Description of change**</span></span>  |
|---------|---------|
| <span data-ttu-id="f3181-175">Отчеты</span><span class="sxs-lookup"><span data-stu-id="f3181-175">Reports</span></span>  | <span data-ttu-id="f3181-176">См. отчеты о конечных точках и &, включая защиту от угроз, здоровье и соответствие требованиям устройств, а также уязвимые устройства.</span><span class="sxs-lookup"><span data-stu-id="f3181-176">See reports for endpoints and email & collaboration, including Threat protection, Device health and compliance, and Vulnerable devices.</span></span> |
| <span data-ttu-id="f3181-177">Здравоохранение</span><span class="sxs-lookup"><span data-stu-id="f3181-177">Health</span></span>  |  <span data-ttu-id="f3181-178">В настоящее время ссылки на страницу "Здоровье службы" в центре администрирования [Microsoft 365.](https://admin.microsoft.com/)</span><span class="sxs-lookup"><span data-stu-id="f3181-178">Currently links out to the "Service health" page in the [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> |
| <span data-ttu-id="f3181-179">Settings</span><span class="sxs-lookup"><span data-stu-id="f3181-179">Settings</span></span> |  <span data-ttu-id="f3181-180">Управление настройками центра безопасности Microsoft 365, Защитника Microsoft 365, конечных точек, электронной почты & совместной работы, удостоверений и обнаружения устройств.</span><span class="sxs-lookup"><span data-stu-id="f3181-180">Manage your settings for the Microsoft 365 security center, Microsoft 365 Defender, Endpoints, Email & collaboration, Identities, and Device discovery.</span></span>   |

## <a name="microsoft-365-security-navigation-and-capabilities"></a><span data-ttu-id="f3181-181">Навигация и возможности безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f3181-181">Microsoft 365 security navigation and capabilities</span></span>

<span data-ttu-id="f3181-182">Область навигации слева или панель быстрого запуска будет выглядеть по-прежнему.</span><span class="sxs-lookup"><span data-stu-id="f3181-182">The left navigation, or quick launch bar, will look familiar.</span></span> <span data-ttu-id="f3181-183">Однако в центре безопасности есть новые и обновленные элементы.</span><span class="sxs-lookup"><span data-stu-id="f3181-183">However, there are some new and updated elements in this security center.</span></span>

### <a name="incidents-and-alerts"></a><span data-ttu-id="f3181-184">Инциденты и оповещения</span><span class="sxs-lookup"><span data-stu-id="f3181-184">Incidents and alerts</span></span>

<span data-ttu-id="f3181-185">Объединяет управление инцидентами и оповещениями в электронной почте, устройствах и удостоверениях.</span><span class="sxs-lookup"><span data-stu-id="f3181-185">Brings together incident and alert management across your email, devices, and identities.</span></span> <span data-ttu-id="f3181-186">Страница оповещений предоставляет полный контекст оповещения, объединяя сигналы атаки для создания подробной истории.</span><span class="sxs-lookup"><span data-stu-id="f3181-186">The alert page provides full context to the alert by combining attack signals to construct a detailed story.</span></span> <span data-ttu-id="f3181-187">Новый единый интерфейс теперь позволяет получить единое представление оповещений в рабочих нагрузках.</span><span class="sxs-lookup"><span data-stu-id="f3181-187">A new, unified experience now brings together a consistent view of alerts across workloads.</span></span> <span data-ttu-id="f3181-188">Вы можете быстро рассмотреть, изучить и предпринять эффективные действия.</span><span class="sxs-lookup"><span data-stu-id="f3181-188">You can quickly triage, investigate, and take effective action.</span></span>

- [<span data-ttu-id="f3181-189">Дополнительные сведения об инцидентах</span><span class="sxs-lookup"><span data-stu-id="f3181-189">Learn more about incidents</span></span>](incidents-overview.md)
- [<span data-ttu-id="f3181-190">Узнайте больше об управлении оповещениями</span><span class="sxs-lookup"><span data-stu-id="f3181-190">Learn more about managing alerts</span></span>](investigate-alerts.md)

![Панель быстрого запуска оповещений и действий](../../media/converge-1-alerts-and-actions.png)

### <a name="hunting"></a><span data-ttu-id="f3181-192">Охота</span><span class="sxs-lookup"><span data-stu-id="f3181-192">Hunting</span></span>

<span data-ttu-id="f3181-193">Профилактический поиск угроз, вредоносных программ и вредоносных действий в конечных точках, почтовых ящиках Office 365 и других службах с помощью [запросов на расширенный поиск](advanced-hunting-overview.md).</span><span class="sxs-lookup"><span data-stu-id="f3181-193">Proactively search for threats, malware, and malicious activity across your endpoints, Office 365 mailboxes, and more by using [advanced hunting queries](advanced-hunting-overview.md).</span></span> <span data-ttu-id="f3181-194">Эти мощные запросы можно использовать для поиска и анализа индикаторов и сущностями угроз как для известных, так и для потенциальных угроз.</span><span class="sxs-lookup"><span data-stu-id="f3181-194">These powerful queries can be used to locate and review threat indicators and entities for both known and potential threats.</span></span>

<span data-ttu-id="f3181-195">[Настраиваемые правила](custom-detection-rules.md) обнаружения могут быть построены из расширенных запросов на охоту, чтобы помочь вам активно следить за событиями, которые могут свидетельствовать о нарушении и неправильной настройки устройств.</span><span class="sxs-lookup"><span data-stu-id="f3181-195">[Custom detection rules](custom-detection-rules.md) can be built from advanced hunting queries to help you proactively watch for events that might be indicative of breach activity and misconfigured devices.</span></span>


### <a name="action-center"></a><span data-ttu-id="f3181-196">Центр уведомлений</span><span class="sxs-lookup"><span data-stu-id="f3181-196">Action center</span></span>

<span data-ttu-id="f3181-197">В центре уведомлений отображаются исследования, созданные средствами автоматического исследования и реагирования.</span><span class="sxs-lookup"><span data-stu-id="f3181-197">Action center shows you the investigations created by automated investigation and response capabilities.</span></span> <span data-ttu-id="f3181-198">Это автоматическое самовосстановление в Microsoft 365 Defender может помочь группам по обеспечению безопасности благодаря автоматическому реагированию на определенные события.</span><span class="sxs-lookup"><span data-stu-id="f3181-198">This automated, self-healing in Microsoft 365 Defender can help security teams by automatically responding to specific events.</span></span>

[<span data-ttu-id="f3181-199">Дополнительные сведения о центре уведомлений</span><span class="sxs-lookup"><span data-stu-id="f3181-199">Learn more about the Action center</span></span>](m365d-action-center.md)

### <a name="threat-analytics"></a><span data-ttu-id="f3181-200">Аналитика угроз</span><span class="sxs-lookup"><span data-stu-id="f3181-200">Threat Analytics</span></span>

<span data-ttu-id="f3181-201">Получите аналитику угроз от исследователей по безопасности Майкрософт</span><span class="sxs-lookup"><span data-stu-id="f3181-201">Get threat intelligence from expert Microsoft security researchers.</span></span> <span data-ttu-id="f3181-202">Аналитика угроз помогает группам по обеспечению безопасности эффективнее выявлять возникающие угрозы.</span><span class="sxs-lookup"><span data-stu-id="f3181-202">Threat Analytics helps security teams be more efficient when facing emerging threats.</span></span> <span data-ttu-id="f3181-203">Что включено в аналитику угроз</span><span class="sxs-lookup"><span data-stu-id="f3181-203">Threat Analytics includes:</span></span>

- <span data-ttu-id="f3181-204">Обнаружения и меры, связанные с электронной почтой, в Microsoft Defender для Office 365.</span><span class="sxs-lookup"><span data-stu-id="f3181-204">Email-related detections and mitigations from Microsoft Defender for Office 365.</span></span> <span data-ttu-id="f3181-205">Это дополнение к данным конечной точки, уже доступным в Microsoft Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f3181-205">This is in addition to the endpoint data already available from Microsoft Defender for Endpoint.</span></span>
- <span data-ttu-id="f3181-206">Просмотр инцидентов, связанных с угрозами.</span><span class="sxs-lookup"><span data-stu-id="f3181-206">Incidents view related to the threats.</span></span>
- <span data-ttu-id="f3181-207">Улучшенные возможности для оперативного определения и использования информации о том, как действовать, в отчетах.</span><span class="sxs-lookup"><span data-stu-id="f3181-207">Enhanced experience for quickly identifying and using actionable information in the reports.</span></span>

<span data-ttu-id="f3181-208">Вы можете получить доступ к аналитике угроз либо из верхней левой панели навигации в центре безопасности Microsoft 365, либо из выделенной карты мониторинга, которая отображает главные угрозы для организации.</span><span class="sxs-lookup"><span data-stu-id="f3181-208">You can access threat analytics either from the upper left navigation bar in the Microsoft 365 security center, or from a dedicated dashboard card that shows the top threats for your organization.</span></span>

<span data-ttu-id="f3181-209">Подробнее о том, как [отслеживать возникающие угрозы и реагировать на них с помощью аналитики угроз](./threat-analytics.md)</span><span class="sxs-lookup"><span data-stu-id="f3181-209">Learn more about how to [track and respond to emerging threats with threat analytics](./threat-analytics.md)</span></span>

### <a name="endpoints-section"></a><span data-ttu-id="f3181-210">Раздел Конечные точки</span><span class="sxs-lookup"><span data-stu-id="f3181-210">Endpoints section</span></span>

<span data-ttu-id="f3181-211">Просмотр и управление безопасностью конечных точек в организации.</span><span class="sxs-lookup"><span data-stu-id="f3181-211">View and manage the security of endpoints in your organization.</span></span> <span data-ttu-id="f3181-212">Если вы использовали Центр безопасности Защитника Майкрософт, он будет выглядеть знакомым.</span><span class="sxs-lookup"><span data-stu-id="f3181-212">If you've used the Microsoft Defender Security Center, it will look familiar.</span></span>

![Планка быстрого запуска Конечные точки](../../media/converge-2-endpoints.png)

### <a name="access-and-reports"></a><span data-ttu-id="f3181-214">Доступ и отчеты</span><span class="sxs-lookup"><span data-stu-id="f3181-214">Access and reports</span></span>

<span data-ttu-id="f3181-215">Просмотр отчетов, изменение параметров и ролей пользователей.</span><span class="sxs-lookup"><span data-stu-id="f3181-215">View reports, change your settings, and modify user roles.</span></span>

![Панели быстрого запусков доступа и отчетности](../../media/converge-4-access-and-reporting-new.png)

### <a name="siem-api-connections"></a><span data-ttu-id="f3181-217">Подключения API SIEM</span><span class="sxs-lookup"><span data-stu-id="f3181-217">SIEM API connections</span></span>

<span data-ttu-id="f3181-218">Если вы используете [API SIEM Defender для конечной](../defender-endpoint/enable-siem-integration.md)точки, вы можете продолжать это делать.</span><span class="sxs-lookup"><span data-stu-id="f3181-218">If you use the [Defender for Endpoint SIEM API](../defender-endpoint/enable-siem-integration.md), you can continue to do so.</span></span> <span data-ttu-id="f3181-219">Добавлены новые ссылки на полезной нагрузке API, которые указывают на страницу оповещения или страницу инцидента на портале безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3181-219">We’ve added new links on the API payload that point to the alert page or the incident page in the Microsoft 365 security portal.</span></span> <span data-ttu-id="f3181-220">Новые поля API включают LinkToMTP и IncidentLinkToMTP.</span><span class="sxs-lookup"><span data-stu-id="f3181-220">New API fields include LinkToMTP and IncidentLinkToMTP.</span></span> <span data-ttu-id="f3181-221">Дополнительные сведения см. в перенаправлении учетных записей из Microsoft Defender для конечной точки в центр безопасности [Microsoft 365.](./microsoft-365-security-mde-redirection.md)</span><span class="sxs-lookup"><span data-stu-id="f3181-221">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

### <a name="email-alerts"></a><span data-ttu-id="f3181-222">Оповещения электронной почты</span><span class="sxs-lookup"><span data-stu-id="f3181-222">Email alerts</span></span>

<span data-ttu-id="f3181-223">Вы можете продолжить использование оповещений электронной почты для Defender для конечной точки.</span><span class="sxs-lookup"><span data-stu-id="f3181-223">You can continue to use email alerts for Defender for Endpoint.</span></span> <span data-ttu-id="f3181-224">Мы добавили новые ссылки в сообщениях электронной почты, которые указывают на страницу оповещений или на страницу инцидента в центре безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f3181-224">We've added new links in the emails that point to the alert page or the incident page in the Microsoft 365 security center.</span></span> <span data-ttu-id="f3181-225">Дополнительные сведения см. в перенаправлении учетных записей из Microsoft Defender для конечной точки в центр безопасности [Microsoft 365.](./microsoft-365-security-mde-redirection.md)</span><span class="sxs-lookup"><span data-stu-id="f3181-225">For more information, see [Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center](./microsoft-365-security-mde-redirection.md).</span></span>

## <a name="related-information"></a><span data-ttu-id="f3181-226">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="f3181-226">Related information</span></span>

- [<span data-ttu-id="f3181-227">Центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f3181-227">Microsoft 365 security center</span></span>](overview-security-center.md)
- [<span data-ttu-id="f3181-228">Защитник Microsoft для конечной точки в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f3181-228">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="f3181-229">Перенаправление учетных записей из Microsoft Defender для конечной точки в центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f3181-229">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>](microsoft-365-security-mde-redirection.md)