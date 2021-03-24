---
title: Перенаправление учетных записей из Microsoft Defender для конечной точки в центр безопасности Microsoft 365
description: Перенаправление учетных записей и сеансов из Центра безопасности Defender для конечной точки в центр безопасности Microsoft 365.
keywords: Центр безопасности Microsoft 365, начало работы с центром безопасности Microsoft 365, перенаправление центра безопасности
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: c993977e0f052a7dc2e7827ff5bdefacee19ac2d
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072685"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-the-microsoft-365-security-center"></a><span data-ttu-id="d98a8-104">Перенаправление учетных записей из Microsoft Defender для конечной точки в центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d98a8-104">Redirecting accounts from Microsoft Defender for Endpoint to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

[!INCLUDE [Prerelease](../includes/prerelease.md)]

<span data-ttu-id="d98a8-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d98a8-105">**Applies to:**</span></span>
- <span data-ttu-id="d98a8-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d98a8-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d98a8-107">Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="d98a8-107">Defender for Endpoint</span></span>

<span data-ttu-id="d98a8-108">В соответствии с меж доменным подходом Корпорации Майкрософт к защите от угроз с помощью SIEM и расширенного обнаружения и реагирования (XDR) мы ребрендинг microsoft Defender Advanced Threat Protection в microsoft Defender для конечной точки и унифицированы в единый интегрированный портал — центр безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d98a8-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - the Microsoft 365 security center.</span></span>

<span data-ttu-id="d98a8-109">В этом руководстве рассказывается, как перенаправлять учетные записи в центр безопасности Microsoft 365 путем автоматического перенаправления с бывшего портала Microsoft Defender для конечных точек (securitycenter.windows.com или securitycenter.microsoft.com) на портал Центра безопасности Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d98a8-109">This guide explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to the Microsoft 365 security center portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="d98a8-110">Microsoft Defender для конечной точки в центре безопасности Microsoft 365 поддерживает предоставление доступа к управляемым поставщикам служб безопасности [(MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) таким же образом, как доступ предоставляется в центре безопасности [Microsoft Defender.](./mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="d98a8-110">Microsoft Defender for Endpoint in the Microsoft 365 security center supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="d98a8-111">Чего ожидать</span><span class="sxs-lookup"><span data-stu-id="d98a8-111">What to expect</span></span>
<span data-ttu-id="d98a8-112">После включения автоматического перенаправления учетные записи, которые получают доступ к бывшему порталу Microsoft Defender для конечных точек в securitycenter.windows.com или securitycenter.microsoft.com, будут автоматически перенаправлены на портал Центра безопасности Microsoft 365 в security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d98a8-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to the Microsoft 365 security center portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="d98a8-113">Узнайте больше о том, что изменилось: Microsoft Defender для конечной точки в центре безопасности [Microsoft 365.](microsoft-365-security-center-mde.md)</span><span class="sxs-lookup"><span data-stu-id="d98a8-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in the Microsoft 365 security center](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="d98a8-114">Это включает перенаправление для прямого доступа к бывшему порталу через браузер, включая ссылки, указывающие на прежний портал securitycenter.windows.com , такие как ссылки в уведомлениях электронной почты и ссылки, возвращаемые вызовами API SIEM.</span><span class="sxs-lookup"><span data-stu-id="d98a8-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="d98a8-115">Внешние ссылки из уведомлений электронной почты или API SIEM в настоящее время содержат ссылки на оба портала.</span><span class="sxs-lookup"><span data-stu-id="d98a8-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="d98a8-116">После включения перенаправления обе ссылки будут указать на центр безопасности Microsoft 365, пока старая ссылка не будет удалена.</span><span class="sxs-lookup"><span data-stu-id="d98a8-116">Once redirection is enabled, both links will point to the Microsoft 365 security center until the old link is eventually removed.</span></span> <span data-ttu-id="d98a8-117">Мы рекомендуем вам принять новую ссылку, указав на центр безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d98a8-117">We encourage you to adopt the new link pointing to the Microsoft 365 security center.</span></span>

<span data-ttu-id="d98a8-118">Дополнительные ссылки на ссылки и маршруты см. в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="d98a8-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="d98a8-119">Маршрутия API SIEM</span><span class="sxs-lookup"><span data-stu-id="d98a8-119">SIEM API routing</span></span>

|<span data-ttu-id="d98a8-120">**Property**</span><span class="sxs-lookup"><span data-stu-id="d98a8-120">**Property**</span></span>  |<span data-ttu-id="d98a8-121">**Назначение, когда перенаправление отключено**</span><span class="sxs-lookup"><span data-stu-id="d98a8-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="d98a8-122">**Назначение при перенаправлении**</span><span class="sxs-lookup"><span data-stu-id="d98a8-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="d98a8-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="d98a8-123">LinkToWDATP</span></span> | <span data-ttu-id="d98a8-124">Страница оповещения в securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="d98a8-125">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="d98a8-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="d98a8-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="d98a8-127">Страница инцидента в securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="d98a8-128">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="d98a8-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="d98a8-129">LinkToMTP</span></span> | <span data-ttu-id="d98a8-130">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="d98a8-131">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="d98a8-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="d98a8-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="d98a8-133">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="d98a8-134">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="d98a8-135">Уведомления об оповещении по электронной почте</span><span class="sxs-lookup"><span data-stu-id="d98a8-135">Email alert notifications</span></span>

|<span data-ttu-id="d98a8-136">**Property**</span><span class="sxs-lookup"><span data-stu-id="d98a8-136">**Property**</span></span>  |<span data-ttu-id="d98a8-137">**Назначение, когда перенаправление отключено**</span><span class="sxs-lookup"><span data-stu-id="d98a8-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="d98a8-138">**Назначение при перенаправлении**</span><span class="sxs-lookup"><span data-stu-id="d98a8-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="d98a8-139">Страница Оповещение</span><span class="sxs-lookup"><span data-stu-id="d98a8-139">Alert page</span></span>  | <span data-ttu-id="d98a8-140">Страница оповещения в securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="d98a8-141">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="d98a8-142">Страница инцидентов</span><span class="sxs-lookup"><span data-stu-id="d98a8-142">Incident page</span></span>  |<span data-ttu-id="d98a8-143">Страница инцидента в securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="d98a8-144">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="d98a8-145">Страница оповещения на портале Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="d98a8-145">Alert page in security center portal</span></span> | <span data-ttu-id="d98a8-146">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="d98a8-147">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="d98a8-148">Страница инцидента на портале Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="d98a8-148">Incident page in security center portal</span></span> | <span data-ttu-id="d98a8-149">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="d98a8-150">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="d98a8-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="d98a8-151">Когда это вступает в силу?</span><span class="sxs-lookup"><span data-stu-id="d98a8-151">When does this take effect?</span></span> 
<span data-ttu-id="d98a8-152">После включения это обновление может вступает в силу практически сразу для некоторых учетных записей.</span><span class="sxs-lookup"><span data-stu-id="d98a8-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="d98a8-153">Но перенаправление может занять больше времени для распространения на каждую учетную запись в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="d98a8-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="d98a8-154">Учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут перенаходить в центр безопасности Microsoft 365 только после завершения текущего сеанса и повторной регистрации.</span><span class="sxs-lookup"><span data-stu-id="d98a8-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="d98a8-155">Настройка перенаправления портала</span><span class="sxs-lookup"><span data-stu-id="d98a8-155">Set up portal redirection</span></span>
<span data-ttu-id="d98a8-156">Чтобы начать маршрутить учетные записи в центр безопасности Microsoft 365:</span><span class="sxs-lookup"><span data-stu-id="d98a8-156">To start routing accounts to the Microsoft 365 security center:</span></span>
1. <span data-ttu-id="d98a8-157">Убедитесь, что вы глобальный администратор или у вас есть разрешения администратора безопасности в каталоге Azure Active</span><span class="sxs-lookup"><span data-stu-id="d98a8-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="d98a8-158">[Во входе](https://security.microsoft.com/) в центр безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d98a8-158">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>

3. <span data-ttu-id="d98a8-159">Перейдите **по ссылке**  >  **Параметры Конечные точки**  >  **Общего**  >  **портала перенаправления** или [нажмите здесь](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="d98a8-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="d98a8-160">Переключение параметра Автоматическое перенаправление **в On**.</span><span class="sxs-lookup"><span data-stu-id="d98a8-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="d98a8-161">Щелкните **Включить** автоматическое перенаправление на портал Центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="d98a8-161">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

>[!IMPORTANT]
><span data-ttu-id="d98a8-162">Включение этого параметра не прекращает активные сеансы пользователей.</span><span class="sxs-lookup"><span data-stu-id="d98a8-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="d98a8-163">Учетные записи, которые находятся в активном сеансе при применении этого параметра, будут направлены в центр безопасности Microsoft 365 только после завершения текущего сеанса и повторной регистрации.</span><span class="sxs-lookup"><span data-stu-id="d98a8-163">Accounts who are in an active session while this setting is applied will only be directed to the Microsoft 365 security center after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="d98a8-164">Вы должны быть глобальным администратором или иметь разрешения администратора безопасности в Azure Active Directory, чтобы включить или отключить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="d98a8-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="d98a8-165">Можно ли вернуться к использованию бывшего портала?</span><span class="sxs-lookup"><span data-stu-id="d98a8-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="d98a8-166">Если что-то не работает для вас или если вы не можете выполнить что-либо через портал Центра безопасности Microsoft 365, мы хотим узнать об этом.</span><span class="sxs-lookup"><span data-stu-id="d98a8-166">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it.</span></span> <span data-ttu-id="d98a8-167">Если у вас были проблемы с перенаправлением, мы рекомендуем вам предоставить нам информацию с помощью формы отправки отзывов.</span><span class="sxs-lookup"><span data-stu-id="d98a8-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="d98a8-168">Чтобы вернуться к бывшему порталу Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="d98a8-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="d98a8-169">[Во входе](https://security.microsoft.com/) в центр безопасности Microsoft 365 в качестве глобального администратора или использования и учетной записи с разрешениями администратора безопасности в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="d98a8-169">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="d98a8-170">Перейдите **к перенаправлению** параметров  >  конечных **точек**  >  **общего**  >  **портала** или [откройте страницу здесь.](https://security.microsoft.com/preferences2/portal_redirection)</span><span class="sxs-lookup"><span data-stu-id="d98a8-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="d98a8-171">Переключение параметра Автоматическое перенаправление в **Off**.</span><span class="sxs-lookup"><span data-stu-id="d98a8-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="d98a8-172">Нажмите **кнопку Отключение** & отзывов о совместной работе при запросе.</span><span class="sxs-lookup"><span data-stu-id="d98a8-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="d98a8-173">Этот параметр можно включить снова в любое время.</span><span class="sxs-lookup"><span data-stu-id="d98a8-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="d98a8-174">После отключения учетные записи больше не будут security.microsoft.com, и вы снова будете иметь доступ к бывшему порталу — securitycenter.windows.com или securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d98a8-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="d98a8-175">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d98a8-175">Related information</span></span>
- [<span data-ttu-id="d98a8-176">Обзор Центра безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d98a8-176">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="d98a8-177">Защитник Microsoft для конечной точки в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="d98a8-177">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="d98a8-178">Корпорация Майкрософт предоставляет унифицированные SIEM и XDR для модернизации операций безопасности</span><span class="sxs-lookup"><span data-stu-id="d98a8-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="d98a8-179">Инфографика XDR и SIEM</span><span class="sxs-lookup"><span data-stu-id="d98a8-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="d98a8-180">Новый защитник</span><span class="sxs-lookup"><span data-stu-id="d98a8-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="d98a8-181">О Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d98a8-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="d98a8-182">Порталы безопасности Майкрософт и центры администрирования</span><span class="sxs-lookup"><span data-stu-id="d98a8-182">Microsoft security portals and admin centers</span></span>](portals.md)