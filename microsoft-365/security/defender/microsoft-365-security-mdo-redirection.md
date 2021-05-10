---
title: Перенаправление учетных записей из Microsoft Defender для Office 365 в новый центр Microsoft 365 безопасности
description: Перенаправление с центра Office 365 defender для Microsoft 365 безопасности.
keywords: Microsoft 365 центра безопасности, начало работы с центром Microsoft 365, перенаправление центра безопасности
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
ms.openlocfilehash: 40d86f9f3a4896bbe788f0a9894a7e08efe3a690
ms.sourcegitcommit: 58d74ff60303a879e35d112f10f79724ba41188f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/10/2021
ms.locfileid: "52301732"
---
# <a name="redirecting-accounts-from-microsoft-defender-for-office-365-to-the-microsoft-365-security-center"></a><span data-ttu-id="24b87-104">Перенаправление учетных записей из Microsoft Defender для Office 365 в центр Microsoft 365 безопасности</span><span class="sxs-lookup"><span data-stu-id="24b87-104">Redirecting accounts from Microsoft Defender for Office 365 to the Microsoft 365 security center</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="24b87-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="24b87-105">**Applies to:**</span></span>

- <span data-ttu-id="24b87-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24b87-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="24b87-107">Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="24b87-107">Defender for Office 365</span></span>

<span data-ttu-id="24b87-108">В этой статье рассказывается о маршруте учетных записей в центр безопасности Microsoft 365, включив автоматическое перенаправление из бывшего Центра безопасности и соответствия требованиям Майкрософт (protection.office.com или securitycenter.microsoft.com) в центр безопасности Microsoft 365 (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="24b87-108">This article explains how to route accounts to the Microsoft 365 security center by enabling automatic redirection from the former Microsoft Security and Compliance Center (protection.office.com or securitycenter.microsoft.com), to the Microsoft 365 security center (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="24b87-109">Чего ожидать</span><span class="sxs-lookup"><span data-stu-id="24b87-109">What to expect</span></span>
<span data-ttu-id="24b87-110">После включения и активного автоматического перенаправления пользователи, которые получают доступ к возможностям, связанным с безопасностью в Office 365 безопасности и соответствия требованиям (protection.office.com), будут автоматически перенаправляться в центр безопасности Microsoft 365 ( https://security.microsoft.com) . .</span><span class="sxs-lookup"><span data-stu-id="24b87-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to the Microsoft 365 security center (https://security.microsoft.com).</span></span>  

<span data-ttu-id="24b87-111">Узнайте больше о том, что изменилось: [Microsoft Defender для Office 365 в центре Microsoft 365 безопасности.](microsoft-365-security-center-mdo.md)</span><span class="sxs-lookup"><span data-stu-id="24b87-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in the Microsoft 365 security center](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="24b87-112">При автоматическом перенаправлении пользователи будут перенаправлены в центр Microsoft 365 безопасности при использовании возможностей безопасности в центре Office 365 безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="24b87-112">With automatic redirection turned on, users will be routed to Microsoft 365 security center when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="24b87-113">К ним относятся возможности в разделе Управление угрозами и панель мониторинга управления угрозами и отчеты.</span><span class="sxs-lookup"><span data-stu-id="24b87-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="24b87-114">Элементы центра Office 365 безопасности и соответствия требованиям, не связанные с безопасностью, не перенаправляются в центр Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="24b87-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to the Microsoft 365 security center.</span></span>

<span data-ttu-id="24b87-115">Элементы, связанные с соответствием требованиям, можно найти в центре Microsoft 365, а связанные с потоком почты элементы можно найти в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="24b87-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="24b87-116">Перенаправление не влияет на все другие возможности, связанные с соответствием требованиям или возможности, которые служат обоим.</span><span class="sxs-lookup"><span data-stu-id="24b87-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="24b87-117">Office 365 оповещения о безопасности отображаются как в центре Microsoft 365, так и в центре Office 365 безопасности и соответствия требованиям без перенаправления.</span><span class="sxs-lookup"><span data-stu-id="24b87-117">Office 365 security alerts appear in both the Microsoft 365 security center and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="24b87-118">Настройка перенаправления портала</span><span class="sxs-lookup"><span data-stu-id="24b87-118">Set up portal redirection</span></span>
<span data-ttu-id="24b87-119">Чтобы начать маршрутизать учетные записи в центр Microsoft 365 безопасности в security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="24b87-119">To start routing accounts to the Microsoft 365 security center at security.microsoft.com:</span></span>

1. <span data-ttu-id="24b87-120">Убедитесь, что вы глобальный администратор или имеете разрешения администратора безопасности в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="24b87-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="24b87-121">[Вход в](https://security.microsoft.com/) центр Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="24b87-121">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center.</span></span>
3. <span data-ttu-id="24b87-122">Перейдите **к Параметры**  >  **электронной почты & перенаправление**  >  **портала совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="24b87-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="24b87-123">Переключение параметра Автоматическое перенаправление **в On**.</span><span class="sxs-lookup"><span data-stu-id="24b87-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="24b87-124">Щелкните **Включить** автоматическое перенаправление на портал центра Microsoft 365 безопасности.</span><span class="sxs-lookup"><span data-stu-id="24b87-124">Click **Enable** to apply automatic redirection to the Microsoft 365 security center portal.</span></span>

> [!NOTE]
> <span data-ttu-id="24b87-125">После включения перенаправления учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут перенаправлены в центр безопасности Microsoft 365 после завершения текущего сеанса и повторного входа.</span><span class="sxs-lookup"><span data-stu-id="24b87-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to the Microsoft 365 security center after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="24b87-126">Можно ли вернуться к использованию бывшего портала?</span><span class="sxs-lookup"><span data-stu-id="24b87-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="24b87-127">Если что-то не работает для вас или не удается выполнить что-либо через портал центра Microsoft 365 безопасности, мы хотим узнать об этом с помощью параметра обратной связи портала.</span><span class="sxs-lookup"><span data-stu-id="24b87-127">If something isn’t working for you or if there’s anything you’re unable to complete through the Microsoft 365 security center portal, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="24b87-128">Если вы столкнулись с любыми вопросами с перенаправлением, мы рекомендуем вам обратиться к вашему приятелю pm непосредственно через закрытый предварительный просмотр или дайте нам знать с помощью формы отправки отзывов.</span><span class="sxs-lookup"><span data-stu-id="24b87-128">If you’ve encountered any issues with redirection, we encourage you to reach out to your PM buddy directly through private preview or let us know via the Give feedback submission form.</span></span>

<span data-ttu-id="24b87-129">Чтобы вернуться на прежний портал:</span><span class="sxs-lookup"><span data-stu-id="24b87-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="24b87-130">[Вход в](https://security.microsoft.com/) центр Microsoft 365 в качестве глобального администратора или использование и учетная запись с разрешениями администратора безопасности в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="24b87-130">[Sign in](https://security.microsoft.com/) to the Microsoft 365 security center as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="24b87-131">Перенаправление **Параметры**  >  **конечных точек**  >  **общего**  >  **портала**.</span><span class="sxs-lookup"><span data-stu-id="24b87-131">Navigate to **Settings** > **Endpoints** > **General** > **Portal redirection**.</span></span>  

3. <span data-ttu-id="24b87-132">Переключение параметра Автоматическое перенаправление в **Off**.</span><span class="sxs-lookup"><span data-stu-id="24b87-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="24b87-133">Нажмите **кнопку Отключение** & отзывов о совместной работе при запросе.</span><span class="sxs-lookup"><span data-stu-id="24b87-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="24b87-134">Этот параметр можно включить снова в любое время.</span><span class="sxs-lookup"><span data-stu-id="24b87-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="24b87-135">После отключения учетные записи больше не будут security.microsoft.com, и вы снова будете иметь доступ к бывшему порталу — securitycenter.windows.com или securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="24b87-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal - securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="24b87-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="24b87-136">Related information</span></span>
- [<span data-ttu-id="24b87-137">Обзор Центра безопасности Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="24b87-137">Microsoft 365 security center overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="24b87-138">Microsoft Defender для конечной точки в центре Microsoft 365 безопасности</span><span class="sxs-lookup"><span data-stu-id="24b87-138">Microsoft Defender for Endpoint in the Microsoft 365 security center</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="24b87-139">Корпорация Майкрософт предоставляет унифицированные SIEM и XDR для модернизации операций безопасности</span><span class="sxs-lookup"><span data-stu-id="24b87-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="24b87-140">Инфографика XDR и SIEM</span><span class="sxs-lookup"><span data-stu-id="24b87-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="24b87-141">Новый защитник</span><span class="sxs-lookup"><span data-stu-id="24b87-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="24b87-142">О Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="24b87-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="24b87-143">Порталы безопасности Майкрософт и центры администрирования</span><span class="sxs-lookup"><span data-stu-id="24b87-143">Microsoft security portals and admin centers</span></span>](portals.md)
