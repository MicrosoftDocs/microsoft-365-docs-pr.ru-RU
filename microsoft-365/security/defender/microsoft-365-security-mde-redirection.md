---
title: Перенаправление учетных записей из Microsoft Defender для конечной точки в Microsoft 365 Defender
description: Перенаправление учетных записей и сеансов из защитника для конечной точки в Microsoft 365 Defender.
keywords: Microsoft 365 Defender, начало работы с Microsoft 365 Defender, перенаправление центра безопасности
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
ms.openlocfilehash: c678cb8d9eece9ff3a900a7d2b0c6bf95ad8eda9
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842570"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-endpoint-to-microsoft-365-defender"></a><span data-ttu-id="8b10d-104">Перенаправление учетных записей из Microsoft Defender для конечной точки в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b10d-104">Redirecting accounts from Microsoft Defender for Endpoint to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="8b10d-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="8b10d-105">**Applies to:**</span></span>
- <span data-ttu-id="8b10d-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b10d-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="8b10d-107">Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="8b10d-107">Defender for Endpoint</span></span>

<span data-ttu-id="8b10d-108">В соответствии с меж доменным подходом Корпорации Майкрософт к защите от угроз с помощью SIEM и расширенного обнаружения и ответа (XDR), мы ребрендинг Расширенная защита от угроз в Microsoft Defender в качестве Защитника Microsoft для конечной точки и унифицированы в единый интегрированный портал — Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8b10d-108">In alignment with Microsoft’s cross-domain approach to threat protection with SIEM and Extended detection and response (XDR), we’ve rebranded Microsoft Defender Advanced Threat Protection as Microsoft Defender for Endpoint and unified it into a single integrated portal - Microsoft 365 Defender.</span></span>

<span data-ttu-id="8b10d-109">В этом руководстве объясняется, как перенаправлять учетные записи в Microsoft 365 Defender, включив автоматическое перенаправление с бывшего портала Microsoft Defender для конечных точек (securitycenter.windows.com или securitycenter.microsoft.com), на портал Microsoft 365 Defender (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="8b10d-109">This guide explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Microsoft Defender for Endpoint portal (securitycenter.windows.com or securitycenter.microsoft.com), to Microsoft 365 Defender portal (security.microsoft.com).</span></span>

> [!NOTE]
> <span data-ttu-id="8b10d-110">Microsoft Defender для конечной точки в Microsoft 365 Defender поддерживает предоставление доступа к управляемым поставщикам служб безопасности [(MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) таким же образом, как доступ предоставляется в центре безопасности [Microsoft Defender.](./mssp-access.md)</span><span class="sxs-lookup"><span data-stu-id="8b10d-110">Microsoft Defender for Endpoint in Microsoft 365 Defender supports [granting access to managed security service providers (MSSPs)](/windows/security/threat-protection/microsoft-defender-atp/grant-mssp-access) in the same that way access is [granted in the Microsoft Defender security center](./mssp-access.md).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="8b10d-111">Чего ожидать</span><span class="sxs-lookup"><span data-stu-id="8b10d-111">What to expect</span></span>
<span data-ttu-id="8b10d-112">После включения автоматического перенаправления учетные записи, которые получают доступ к бывшему порталу Microsoft Defender для конечных точек в securitycenter.windows.com или securitycenter.microsoft.com, будут автоматически перенаправлены на портал Microsoft 365 Defender в security.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8b10d-112">Once automatic redirection is enabled, accounts accessing the former Microsoft Defender for Endpoint portal at securitycenter.windows.com or securitycenter.microsoft.com, will be automatically routed to Microsoft 365 Defender portal at security.microsoft.com.</span></span>
 
<span data-ttu-id="8b10d-113">Узнайте больше о том, что изменилось: [Microsoft Defender для конечной точки в Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span><span class="sxs-lookup"><span data-stu-id="8b10d-113">Learn more about what’s changed: [Microsoft Defender for Endpoint in Microsoft 365 Defender](microsoft-365-security-center-mde.md).</span></span>

<span data-ttu-id="8b10d-114">Это включает перенаправление для прямого доступа к бывшему порталу через браузер, включая ссылки, указывающие на прежний портал securitycenter.windows.com , такие как ссылки в уведомлениях электронной почты и ссылки, возвращаемые вызовами API SIEM.</span><span class="sxs-lookup"><span data-stu-id="8b10d-114">This includes redirection for direct access to the former portal via browser, including links pointing towards the former securitycenter.windows.com portal - such as links in email notifications, and links returned by SIEM API calls.</span></span>  

 <span data-ttu-id="8b10d-115">Внешние ссылки из уведомлений электронной почты или API SIEM в настоящее время содержат ссылки на оба портала.</span><span class="sxs-lookup"><span data-stu-id="8b10d-115">External links from email notifications or SIEM APIs currently contain links to both portals.</span></span> <span data-ttu-id="8b10d-116">После включения перенаправления обе ссылки будут Microsoft 365 Defender до удаления старой ссылки.</span><span class="sxs-lookup"><span data-stu-id="8b10d-116">Once redirection is enabled, both links will point to Microsoft 365 Defender until the old link is eventually removed.</span></span> <span data-ttu-id="8b10d-117">Мы рекомендуем вам принять новую ссылку, указывав на Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8b10d-117">We encourage you to adopt the new link pointing to Microsoft 365 Defender.</span></span>

<span data-ttu-id="8b10d-118">Дополнительные ссылки на ссылки и маршруты см. в таблице ниже.</span><span class="sxs-lookup"><span data-stu-id="8b10d-118">Refer to the table below for more on links and routing.</span></span>
## <a name="siem-api-routing"></a><span data-ttu-id="8b10d-119">Маршрутия API SIEM</span><span class="sxs-lookup"><span data-stu-id="8b10d-119">SIEM API routing</span></span>

|<span data-ttu-id="8b10d-120">**Property**</span><span class="sxs-lookup"><span data-stu-id="8b10d-120">**Property**</span></span>  |<span data-ttu-id="8b10d-121">**Назначение, когда перенаправление отключено**</span><span class="sxs-lookup"><span data-stu-id="8b10d-121">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="8b10d-122">**Назначение при перенаправлении**</span><span class="sxs-lookup"><span data-stu-id="8b10d-122">**Destination when redirection is ON**</span></span> | 
|---------|---------|---------|
| <span data-ttu-id="8b10d-123">LinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="8b10d-123">LinkToWDATP</span></span> | <span data-ttu-id="8b10d-124">Страница оповещения в securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-124">Alert page in securitycenter.windows.com</span></span> | <span data-ttu-id="8b10d-125">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-125">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="8b10d-126">IncidentLinkToWDATP</span><span class="sxs-lookup"><span data-stu-id="8b10d-126">IncidentLinkToWDATP</span></span> | <span data-ttu-id="8b10d-127">Страница инцидента в securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-127">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="8b10d-128">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-128">Incident page in security.microsoft.com</span></span>  |
| <span data-ttu-id="8b10d-129">LinkToMTP</span><span class="sxs-lookup"><span data-stu-id="8b10d-129">LinkToMTP</span></span> | <span data-ttu-id="8b10d-130">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-130">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="8b10d-131">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-131">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="8b10d-132">IncidentLinkToMTP</span><span class="sxs-lookup"><span data-stu-id="8b10d-132">IncidentLinkToMTP</span></span> | <span data-ttu-id="8b10d-133">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-133">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="8b10d-134">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-134">Incident page in security.microsoft.com</span></span>  

## <a name="email-alert-notifications"></a><span data-ttu-id="8b10d-135">Уведомления об оповещении по электронной почте</span><span class="sxs-lookup"><span data-stu-id="8b10d-135">Email alert notifications</span></span>

|<span data-ttu-id="8b10d-136">**Property**</span><span class="sxs-lookup"><span data-stu-id="8b10d-136">**Property**</span></span>  |<span data-ttu-id="8b10d-137">**Назначение, когда перенаправление отключено**</span><span class="sxs-lookup"><span data-stu-id="8b10d-137">**Destination when redirection is OFF**</span></span>  |<span data-ttu-id="8b10d-138">**Назначение при перенаправлении**</span><span class="sxs-lookup"><span data-stu-id="8b10d-138">**Destination when redirection is ON**</span></span> |
|---------|---------|---------|
| <span data-ttu-id="8b10d-139">Страница Оповещение</span><span class="sxs-lookup"><span data-stu-id="8b10d-139">Alert page</span></span>  | <span data-ttu-id="8b10d-140">Страница оповещения в securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-140">Alert page in securitycenter.windows.com</span></span>  | <span data-ttu-id="8b10d-141">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-141">Alert page in security.microsoft.com</span></span>  |
| <span data-ttu-id="8b10d-142">Страница инцидентов</span><span class="sxs-lookup"><span data-stu-id="8b10d-142">Incident page</span></span>  |<span data-ttu-id="8b10d-143">Страница инцидента в securitycenter.windows.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-143">Incident page in securitycenter.windows.com</span></span>  | <span data-ttu-id="8b10d-144">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-144">Incident page in security.microsoft.com</span></span>  
| <span data-ttu-id="8b10d-145">Страница оповещения на портале Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="8b10d-145">Alert page in security center portal</span></span> | <span data-ttu-id="8b10d-146">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-146">Alert page in security.microsoft.com</span></span> | <span data-ttu-id="8b10d-147">Страница оповещения в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-147">Alert page in security.microsoft.com</span></span> | 
| <span data-ttu-id="8b10d-148">Страница инцидента на портале Центра безопасности</span><span class="sxs-lookup"><span data-stu-id="8b10d-148">Incident page in security center portal</span></span> | <span data-ttu-id="8b10d-149">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-149">Incident page in security.microsoft.com</span></span>  | <span data-ttu-id="8b10d-150">Страница инцидента в security.microsoft.com</span><span class="sxs-lookup"><span data-stu-id="8b10d-150">Incident page in security.microsoft.com</span></span>  |

## <a name="when-does-this-take-effect"></a><span data-ttu-id="8b10d-151">Когда это вступает в силу?</span><span class="sxs-lookup"><span data-stu-id="8b10d-151">When does this take effect?</span></span> 
<span data-ttu-id="8b10d-152">После включения это обновление может вступает в силу практически сразу для некоторых учетных записей.</span><span class="sxs-lookup"><span data-stu-id="8b10d-152">Once enabled, this update might take effect almost immediately for some accounts.</span></span> <span data-ttu-id="8b10d-153">Но перенаправление может занять больше времени для распространения на каждую учетную запись в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="8b10d-153">But the redirection might take longer to propagate to every account in your organization.</span></span> <span data-ttu-id="8b10d-154">Учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут переналожены в Microsoft 365 Defender после завершения текущего сеанса и повторной регистрации.</span><span class="sxs-lookup"><span data-stu-id="8b10d-154">Accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="8b10d-155">Настройка перенаправления портала</span><span class="sxs-lookup"><span data-stu-id="8b10d-155">Set up portal redirection</span></span>
<span data-ttu-id="8b10d-156">Чтобы приступить к маршрутике учетных записей Microsoft 365 Defender:</span><span class="sxs-lookup"><span data-stu-id="8b10d-156">To start routing accounts to Microsoft 365 Defender:</span></span>
1. <span data-ttu-id="8b10d-157">Убедитесь, что вы глобальный администратор или у вас есть разрешения администратора безопасности в каталоге Azure Active</span><span class="sxs-lookup"><span data-stu-id="8b10d-157">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory</span></span> 

2. <span data-ttu-id="8b10d-158">[Вопишите в](https://security.microsoft.com/) Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8b10d-158">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>

3. <span data-ttu-id="8b10d-159">Перейдите **Параметры**  >  **конечных точек**  >  **общего**  >  **перенаправления портала** или [нажмите здесь](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="8b10d-159">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [click here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

4. <span data-ttu-id="8b10d-160">Переключение параметра Автоматическое перенаправление **в On**.</span><span class="sxs-lookup"><span data-stu-id="8b10d-160">Toggle the Automatic redirection setting to **On**.</span></span>

5. <span data-ttu-id="8b10d-161">Щелкните **Включить** автоматическое перенаправление Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="8b10d-161">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

>[!IMPORTANT]
><span data-ttu-id="8b10d-162">Включение этого параметра не прекращает активные сеансы пользователей.</span><span class="sxs-lookup"><span data-stu-id="8b10d-162">Enabling this setting will not terminate active user sessions.</span></span> <span data-ttu-id="8b10d-163">Учетные записи, которые находятся в активном сеансе при применении этого параметра, будут направлены в Microsoft 365 Defender после завершения текущего сеанса и повторной регистрации.</span><span class="sxs-lookup"><span data-stu-id="8b10d-163">Accounts who are in an active session while this setting is applied will only be directed to Microsoft 365 Defender after ending their current session and signing in again.</span></span>

>[!NOTE]
><span data-ttu-id="8b10d-164">Вы должны быть глобальным администратором или иметь разрешения администратора безопасности в Azure Active Directory, чтобы включить или отключить этот параметр.</span><span class="sxs-lookup"><span data-stu-id="8b10d-164">You must be a global administrator or have security administrator permissions in Azure Active Directory to enable or disable this setting.</span></span>  

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="8b10d-165">Можно ли вернуться к использованию бывшего портала?</span><span class="sxs-lookup"><span data-stu-id="8b10d-165">Can I go back to using the former portal?</span></span>
<span data-ttu-id="8b10d-166">Если что-то не работает для вас или если вы не можете выполнить что-либо через Microsoft 365 Defender, мы хотим узнать об этом.</span><span class="sxs-lookup"><span data-stu-id="8b10d-166">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it.</span></span> <span data-ttu-id="8b10d-167">Если у вас были проблемы с перенаправлением, мы рекомендуем вам предоставить нам информацию с помощью формы отправки отзывов.</span><span class="sxs-lookup"><span data-stu-id="8b10d-167">If you’ve encountered any issues with redirection, we encourage you to let us know by using the Give feedback submission form.</span></span>

<span data-ttu-id="8b10d-168">Чтобы вернуться к бывшему порталу Microsoft Defender для конечных точек:</span><span class="sxs-lookup"><span data-stu-id="8b10d-168">To revert to the former Microsoft Defender for Endpoint portal:</span></span>

1. <span data-ttu-id="8b10d-169">[Ворегистрируйся](https://security.microsoft.com/) Microsoft 365 защитника в качестве глобального администратора или используя и учетную запись с разрешениями администратора безопасности в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="8b10d-169">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="8b10d-170">Перейдите **Параметры**  >  **конечных точек**  >  **общего**  >  **портала перенаправления** или [откройте страницу здесь](https://security.microsoft.com/preferences2/portal_redirection).</span><span class="sxs-lookup"><span data-stu-id="8b10d-170">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection** or [open the page here](https://security.microsoft.com/preferences2/portal_redirection).</span></span>  

3. <span data-ttu-id="8b10d-171">Переключение параметра Автоматическое перенаправление в **Off**.</span><span class="sxs-lookup"><span data-stu-id="8b10d-171">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="8b10d-172">Нажмите **кнопку Отключение** & отзывов о совместной работе при запросе.</span><span class="sxs-lookup"><span data-stu-id="8b10d-172">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="8b10d-173">Этот параметр можно включить снова в любое время.</span><span class="sxs-lookup"><span data-stu-id="8b10d-173">This setting can be enabled again at any time.</span></span> 

<span data-ttu-id="8b10d-174">После отключения учетные записи больше не будут security.microsoft.com, и вы снова будете иметь доступ к бывшему порталу — securitycenter.windows.com или securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="8b10d-174">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span> 

## <a name="related-information"></a><span data-ttu-id="8b10d-175">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="8b10d-175">Related information</span></span>
- [<span data-ttu-id="8b10d-176">Microsoft 365 Обзор defender</span><span class="sxs-lookup"><span data-stu-id="8b10d-176">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="8b10d-177">Microsoft Defender для конечной точки в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b10d-177">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="8b10d-178">Корпорация Майкрософт предоставляет унифицированные SIEM и XDR для модернизации операций безопасности</span><span class="sxs-lookup"><span data-stu-id="8b10d-178">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="8b10d-179">Инфографика XDR и SIEM</span><span class="sxs-lookup"><span data-stu-id="8b10d-179">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="8b10d-180">Новый защитник</span><span class="sxs-lookup"><span data-stu-id="8b10d-180">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="8b10d-181">О Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="8b10d-181">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="8b10d-182">Порталы безопасности Майкрософт и центры администрирования</span><span class="sxs-lookup"><span data-stu-id="8b10d-182">Microsoft security portals and admin centers</span></span>](portals.md)