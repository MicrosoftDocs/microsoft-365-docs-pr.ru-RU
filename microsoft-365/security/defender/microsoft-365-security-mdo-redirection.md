---
title: Перенаправление учетных записей из Microsoft Defender для Office 365 в новый центр безопасности Microsoft 365
description: Перенаправление из Defender для Office 365 в центр безопасности Microsoft 365.
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
ms.openlocfilehash: ce8c178b4c46a00b83833f008080b776f4dc7e60
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/23/2021
ms.locfileid: "51072678"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="e785b-104">Перенаправление учетных записей из Microsoft Defender для Office 365 в центр безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e785b-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="e785b-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="e785b-105">**Applies to:**</span></span>

- <span data-ttu-id="e785b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e785b-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="e785b-107">Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="e785b-107">Defender for Office 365</span></span>

<span data-ttu-id="e785b-108">В этой статье рассказывается о маршруте учетных записей в центр безопасности Microsoft 365, включив автоматическое перенаправление из бывшего Центра безопасности и соответствия требованиям Майкрософт (protection.office.com или securitycenter.microsoft.com) в центр безопасности Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="e785b-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

>[!NOTE]
> <span data-ttu-id="e785b-109">Возможность перенаправления портала доступна только для клиентов Office 365 E5 и Microsoft Defender для office P2</span><span class="sxs-lookup"><span data-stu-id="e785b-109">Portal redirection capability is available for Office 365 E5 and Microsoft Defender for Office P2 customers only</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="e785b-110">Чего ожидать</span><span class="sxs-lookup"><span data-stu-id="e785b-110">What to expect</span></span>
<span data-ttu-id="e785b-111">После включения и активного автоматического перенаправления пользователи, которые получают доступ к возможностям, связанным с безопасностью в Office 365 Security and Compliance (protection.office.com), будут автоматически перенаправлены в центр безопасности Microsoft 365 ( https://security.microsoft.com) .</span><span class="sxs-lookup"><span data-stu-id="e785b-111">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="e785b-112">Узнайте больше о том, что изменилось: [Microsoft Defender для Office 365 в центре безопасности Microsoft 365.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="e785b-112">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="e785b-113">При автоматическом перенаправлении пользователи будут перенаправлены в центр безопасности Microsoft 365 при использовании возможностей безопасности в Центре безопасности и соответствия требованиям Office 365.</span><span class="sxs-lookup"><span data-stu-id="e785b-113">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="e785b-114">К ним относятся возможности в разделе Управление угрозами и панель мониторинга управления угрозами и отчеты.</span><span class="sxs-lookup"><span data-stu-id="e785b-114">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="e785b-115">Элементы Центра безопасности и соответствия требованиям Office 365, не связанные с безопасностью, не перенаправляются в центр безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e785b-115">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="e785b-116">Элементы, связанные с соответствием требованиям, можно найти в центре соответствия требованиям Microsoft 365, а элементы, связанные с потоком почты, можно найти в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="e785b-116">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="e785b-117">Перенаправление не влияет на все другие возможности, связанные с соответствием требованиям или возможности, которые служат обоим.</span><span class="sxs-lookup"><span data-stu-id="e785b-117">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="e785b-118">Оповещения о безопасности Office 365 отображаются в центре безопасности Microsoft 365 и Центре безопасности и соответствия требованиям Office 365 без перенаправления.</span><span class="sxs-lookup"><span data-stu-id="e785b-118">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="e785b-119">Настройка перенаправления портала</span><span class="sxs-lookup"><span data-stu-id="e785b-119">Set up portal redirection</span></span>
<span data-ttu-id="e785b-120">Чтобы начать маршрутить учетные записи в центр безопасности Microsoft 365 в security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="e785b-120">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="e785b-121">Убедитесь, что вы глобальный администратор или имеете разрешения администратора безопасности в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="e785b-121">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="e785b-122">[Во входе](https://security.microsoft.com/) в центр безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e785b-122">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="e785b-123">Перейдите **к настройкам**  >  **перенаправления & на**  >  **портале совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="e785b-123">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="e785b-124">Переключение параметра Автоматическое перенаправление **в On**.</span><span class="sxs-lookup"><span data-stu-id="e785b-124">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="e785b-125">Щелкните **Включить** автоматическое перенаправление на портал Центра безопасности Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="e785b-125">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="e785b-126">После включения перенаправления учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут перенаправлены в центр безопасности Microsoft 365 только после завершения текущего сеанса и повторного входа.</span><span class="sxs-lookup"><span data-stu-id="e785b-126">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="e785b-127">Можно ли вернуться к использованию бывшего портала?</span><span class="sxs-lookup"><span data-stu-id="e785b-127">Can I go back to using the former portal?</span></span>
<span data-ttu-id="e785b-128">Если что-то не работает для вас или вы не можете выполнить что-либо через портал Центра безопасности Microsoft 365, мы хотим узнать об этом с помощью варианта обратной связи портала.</span><span class="sxs-lookup"><span data-stu-id="e785b-128">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="e785b-129">Если вы столкнулись с любыми вопросами с перенаправлением, мы рекомендуем вам обратиться к вашему приятелю pm непосредственно через закрытый предварительный просмотр или дайте нам знать с помощью формы отправки отзывов.</span><span class="sxs-lookup"><span data-stu-id="e785b-129">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="e785b-130">Чтобы вернуться на прежний портал:</span><span class="sxs-lookup"><span data-stu-id="e785b-130">To revert to the former portal:</span></span>

1. <span data-ttu-id="e785b-131">[Во входе](https://security.microsoft.com/) в центр безопасности Microsoft 365 в качестве глобального администратора или использования и учетной записи с разрешениями администратора безопасности в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="e785b-131">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="e785b-132">Перейдите **к перенаправлению** конечных  >  **точек**  >  **параметров общего**  >  **портала.**</span><span class="sxs-lookup"><span data-stu-id="e785b-132">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="e785b-133">Переключение параметра Автоматическое перенаправление в **Off**.</span><span class="sxs-lookup"><span data-stu-id="e785b-133">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="e785b-134">Нажмите **кнопку Отключение** & отзывов о совместной работе при запросе.</span><span class="sxs-lookup"><span data-stu-id="e785b-134">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="e785b-135">Этот параметр можно включить снова в любое время.</span><span class="sxs-lookup"><span data-stu-id="e785b-135">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="e785b-136">После отключения учетные записи больше не будут security.microsoft.com, и вы снова будете иметь доступ к бывшему порталу — securitycenter.windows.com или securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="e785b-136">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="e785b-137">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="e785b-137">Related information</span></span>
- [<span data-ttu-id="e785b-138">Обзор Центра безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e785b-138">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="e785b-139">Защитник Microsoft для конечной точки в центре безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="e785b-139">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="e785b-140">Корпорация Майкрософт предоставляет унифицированные SIEM и XDR для модернизации операций безопасности</span><span class="sxs-lookup"><span data-stu-id="e785b-140">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="e785b-141">Инфографика XDR и SIEM</span><span class="sxs-lookup"><span data-stu-id="e785b-141">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="e785b-142">Новый защитник</span><span class="sxs-lookup"><span data-stu-id="e785b-142">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="e785b-143">О Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e785b-143">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="e785b-144">Порталы безопасности Майкрософт и центры администрирования</span><span class="sxs-lookup"><span data-stu-id="e785b-144">Microsoft security portals and admin centers</span></span>](portals.md)