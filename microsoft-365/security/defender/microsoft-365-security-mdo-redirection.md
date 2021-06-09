---
title: Перенаправление учетных записей из центра Office 365 безопасности и соответствия требованиям в новый Microsoft 365 Defender
description: Перенаправление с defender для Office 365 на Microsoft 365 Defender.
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
ms.openlocfilehash: f13e8235eb5f70e2d851b9b8b7600913d4e4023f
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/08/2021
ms.locfileid: "52842526"
---
# <a name="redirecting-accounts-from-office-365-security-and-compliance-center-to-microsoft-365-defender"></a><span data-ttu-id="d5454-104">Перенаправление учетных записей из центра Office 365 безопасности и соответствия требованиям в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5454-104">Redirecting accounts from Office 365 Security and Compliance Center to Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="d5454-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="d5454-105">**Applies to:**</span></span>

- <span data-ttu-id="d5454-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5454-106">Microsoft 365 Defender</span></span>
- <span data-ttu-id="d5454-107">Defender для Office 365</span><span class="sxs-lookup"><span data-stu-id="d5454-107">Defender for Office 365</span></span>

<span data-ttu-id="d5454-108">В этой статье рассказывается, как перенаправлять учетные записи в Microsoft 365 Defender, включив автоматическое перенаправление из бывшего центра Office 365 безопасности и соответствия требованиям (protection.office.com) в Microsoft 365 Defender (security.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="d5454-108">This article explains how to route accounts to Microsoft 365 Defender by enabling automatic redirection from the former Office 365 Security and Compliance Center (protection.office.com), to Microsoft 365 Defender (security.microsoft.com).</span></span>

## <a name="what-to-expect"></a><span data-ttu-id="d5454-109">Чего ожидать</span><span class="sxs-lookup"><span data-stu-id="d5454-109">What to expect</span></span>
<span data-ttu-id="d5454-110">После включения и активного автоматического перенаправления пользователи, которые получают доступ к возможностям, связанным с безопасностью в Office 365 безопасности и соответствия требованиям (protection.office.com), будут автоматически перенаправлены в Microsoft 365 Defender ( https://security.microsoft.com) . .</span><span class="sxs-lookup"><span data-stu-id="d5454-110">Once automatic redirection is enabled and active, users accessing the security-related capabilities in  Office 365 Security and Compliance (protection.office.com), will be automatically routed to Microsoft 365 Defender (https://security.microsoft.com).</span></span>  

<span data-ttu-id="d5454-111">Узнайте больше о том, что изменилось: [Microsoft Defender для Office 365 в Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span><span class="sxs-lookup"><span data-stu-id="d5454-111">Learn more about what’s changed: [Microsoft Defender for Office 365 in Microsoft 365 Defender](microsoft-365-security-center-mdo.md).</span></span>

<span data-ttu-id="d5454-112">При автоматическом перенаправлении пользователи будут перенаправлены в Microsoft 365 Defender при использовании возможностей безопасности в центре Office 365 безопасности и соответствия требованиям.</span><span class="sxs-lookup"><span data-stu-id="d5454-112">With automatic redirection turned on, users will be routed to Microsoft 365 Defender when they use security capabilities in the Office 365 Security and Compliance Center.</span></span>

<span data-ttu-id="d5454-113">К ним относятся возможности в разделе Управление угрозами и панель мониторинга управления угрозами и отчеты.</span><span class="sxs-lookup"><span data-stu-id="d5454-113">These include capabilities in the Threat Management section and the Threat Management dashboard and reports.</span></span> <span data-ttu-id="d5454-114">Элементы в центре Office 365 безопасности и соответствия требованиям, не связанные с безопасностью, не перенаправляются в Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d5454-114">Items in the Office 365 Security and Compliance Center that are not related to security are not redirected to Microsoft 365 Defender.</span></span>

<span data-ttu-id="d5454-115">Элементы, связанные с соответствием требованиям, можно найти в центре Microsoft 365, а связанные с потоком почты элементы можно найти в центре администрирования Exchange.</span><span class="sxs-lookup"><span data-stu-id="d5454-115">Compliance-related items can be found in the Microsoft 365 compliance center, and mail-flow related items can be found in the Exchange admin center.</span></span>

<span data-ttu-id="d5454-116">Перенаправление не влияет на все другие возможности, связанные с соответствием требованиям или возможности, которые служат обоим.</span><span class="sxs-lookup"><span data-stu-id="d5454-116">All other capabilities, whether compliance-related or capabilities that serve both are not affected by redirection.</span></span> <span data-ttu-id="d5454-117">Office 365 оповещения о безопасности отображаются как в Microsoft 365 Defender, так и в центре Office 365 безопасности и соответствия требованиям без перенаправления.</span><span class="sxs-lookup"><span data-stu-id="d5454-117">Office 365 security alerts appear in both Microsoft 365 Defender and the Office 365 Security and Compliance center, without redirection.</span></span>  

### <a name="set-up-portal-redirection"></a><span data-ttu-id="d5454-118">Настройка перенаправления портала</span><span class="sxs-lookup"><span data-stu-id="d5454-118">Set up portal redirection</span></span>
<span data-ttu-id="d5454-119">Чтобы начать маршрутику учетных записей Microsoft 365 Defender в security.microsoft.com:</span><span class="sxs-lookup"><span data-stu-id="d5454-119">To start routing accounts to Microsoft 365 Defender at security.microsoft.com:</span></span>

1. <span data-ttu-id="d5454-120">Убедитесь, что вы глобальный администратор или имеете разрешения администратора безопасности в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="d5454-120">Make sure you’re a global administrator or have security administrator permissions in Azure Active directory.</span></span>
2. <span data-ttu-id="d5454-121">[Вопишите в](https://security.microsoft.com/) Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d5454-121">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender.</span></span>
3. <span data-ttu-id="d5454-122">Перейдите **к Параметры**  >  **электронной почты & перенаправление**  >  **портала совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="d5454-122">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>  
4. <span data-ttu-id="d5454-123">Переключение параметра Автоматическое перенаправление **в On**.</span><span class="sxs-lookup"><span data-stu-id="d5454-123">Toggle the Automatic redirection setting to **On**.</span></span>
5. <span data-ttu-id="d5454-124">Щелкните **Включить** автоматическое перенаправление Microsoft 365 Defender.</span><span class="sxs-lookup"><span data-stu-id="d5454-124">Click **Enable** to apply automatic redirection to Microsoft 365 Defender.</span></span>

> [!NOTE]
> <span data-ttu-id="d5454-125">После включения перенаправления учетные записи в активных сеансах при применении этого параметра не будут извлечены из сеанса и будут перенаправлены в Microsoft 365 Defender после завершения текущего сеанса и повторного входа.</span><span class="sxs-lookup"><span data-stu-id="d5454-125">After redirection is enabled, accounts in active sessions while this setting is applied will not be ejected from their session and will only be routed to Microsoft 365 Defender after ending their current session and signing back in again.</span></span>

## <a name="can-i-go-back-to-using-the-former-portal"></a><span data-ttu-id="d5454-126">Можно ли вернуться к использованию бывшего портала?</span><span class="sxs-lookup"><span data-stu-id="d5454-126">Can I go back to using the former portal?</span></span>
<span data-ttu-id="d5454-127">Если что-то не работает для вас или если вы не можете выполнить что-либо через Microsoft 365 Defender, мы хотим узнать об этом с помощью параметра обратной связи портала.</span><span class="sxs-lookup"><span data-stu-id="d5454-127">If something isn’t working for you or if there’s anything you’re unable to complete through Microsoft 365 Defender, we want to hear about it using the portal feedback option.</span></span> <span data-ttu-id="d5454-128">Если у вас были проблемы с перенаправлением, сообщите нам об этом.</span><span class="sxs-lookup"><span data-stu-id="d5454-128">If you’ve encountered any issues with redirection, please let us know.</span></span>

<span data-ttu-id="d5454-129">Чтобы вернуться на прежний портал:</span><span class="sxs-lookup"><span data-stu-id="d5454-129">To revert to the former portal:</span></span>

1. <span data-ttu-id="d5454-130">[Ворегистрируйся](https://security.microsoft.com/) Microsoft 365 защитника в качестве глобального администратора или используя и учетную запись с разрешениями администратора безопасности в каталоге Azure Active.</span><span class="sxs-lookup"><span data-stu-id="d5454-130">[Sign in](https://security.microsoft.com/) to Microsoft 365 Defender as a global administrator or using and account with security administrator permissions in Azure Active directory.</span></span>

2. <span data-ttu-id="d5454-131">Перейдите **к Параметры**  >  **электронной почты & перенаправление**  >  **портала совместной работы.**</span><span class="sxs-lookup"><span data-stu-id="d5454-131">Navigate to **Settings** > **Email & collaboration** > **Portal redirection**.</span></span>   

3. <span data-ttu-id="d5454-132">Переключение параметра Автоматическое перенаправление в **Off**.</span><span class="sxs-lookup"><span data-stu-id="d5454-132">Toggle the Automatic redirection setting to **Off**.</span></span>

4. <span data-ttu-id="d5454-133">Нажмите **кнопку Отключение** & отзывов о совместной работе при запросе.</span><span class="sxs-lookup"><span data-stu-id="d5454-133">Click **Disable** & share feedback when prompted.</span></span>

<span data-ttu-id="d5454-134">Этот параметр можно включить снова в любое время.</span><span class="sxs-lookup"><span data-stu-id="d5454-134">This setting can be enabled again at any time.</span></span>

<span data-ttu-id="d5454-135">После отключения учетные записи больше не будут security.microsoft.com, и вы снова будете иметь доступ к бывшему порталу securitycenter.windows.com или securitycenter.microsoft.com.</span><span class="sxs-lookup"><span data-stu-id="d5454-135">Once disabled, accounts will no longer be routed to security.microsoft.com, and you will once again have access to the former portal—securitycenter.windows.com or securitycenter.microsoft.com.</span></span>

## <a name="related-information"></a><span data-ttu-id="d5454-136">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="d5454-136">Related information</span></span>
- [<span data-ttu-id="d5454-137">Microsoft 365 Обзор defender</span><span class="sxs-lookup"><span data-stu-id="d5454-137">Microsoft 365 Defender overview</span></span>](overview-security-center.md)
- [<span data-ttu-id="d5454-138">Microsoft Defender для конечной точки в Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5454-138">Microsoft Defender for Endpoint in Microsoft 365 Defender</span></span>](microsoft-365-security-center-mde.md)
- [<span data-ttu-id="d5454-139">Корпорация Майкрософт предоставляет унифицированные SIEM и XDR для модернизации операций безопасности</span><span class="sxs-lookup"><span data-stu-id="d5454-139">Microsoft delivers unified SIEM and XDR to modernize security operations</span></span>](https://www.microsoft.com/security/blog/?p=91813) 
- [<span data-ttu-id="d5454-140">Инфографика XDR и SIEM</span><span class="sxs-lookup"><span data-stu-id="d5454-140">XDR versus SIEM infographic</span></span>](https://afrait.com/blog/xdr-versus-siem/) 
- [<span data-ttu-id="d5454-141">Новый защитник</span><span class="sxs-lookup"><span data-stu-id="d5454-141">The New Defender</span></span>](https://afrait.com/blog/the-new-defender/) 
- [<span data-ttu-id="d5454-142">О Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d5454-142">About Microsoft 365 Defender</span></span>](https://www.microsoft.com/microsoft-365/security/microsoft-365-defender) 
- [<span data-ttu-id="d5454-143">Порталы безопасности Майкрософт и центры администрирования</span><span class="sxs-lookup"><span data-stu-id="d5454-143">Microsoft security portals and admin centers</span></span>](portals.md)
