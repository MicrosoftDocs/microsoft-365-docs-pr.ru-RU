---
title: Устранение неполадок с интеграцией средств SIEM в Microsoft Defender для конечной точки
description: Устранение неполадок, которые могут возникнуть при использовании средств SIEM с Помощью Microsoft Defender для конечной точки.
keywords: устранение неполадок, siem, секрет клиента, секрет
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
ms.topic: troubleshooting
ms.technology: mde
ms.openlocfilehash: 60220d00ca1b612564b72103b9206e3d6d89dc60
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689453"
---
# <a name="troubleshoot-siem-tool-integration-issues"></a><span data-ttu-id="c34af-104">Устранение неполадок с интеграцией средства SIEM</span><span class="sxs-lookup"><span data-stu-id="c34af-104">Troubleshoot SIEM tool integration issues</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="c34af-105">**Область применения:**</span><span class="sxs-lookup"><span data-stu-id="c34af-105">**Applies to:**</span></span>
- [<span data-ttu-id="c34af-106">Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c34af-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="c34af-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="c34af-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="c34af-108">Хотите испытать Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c34af-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="c34af-109">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c34af-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-pullalerts-abovefoldlink) 

<span data-ttu-id="c34af-110">Возможно, вам потребуется устранить неполадки при обнаружении обнаружения в средствах SIEM.</span><span class="sxs-lookup"><span data-stu-id="c34af-110">You might need to troubleshoot issues while pulling detections in your SIEM tools.</span></span>

<span data-ttu-id="c34af-111">На этой странице подробно описаны действия по устранению проблем, с которыми вы можете столкнуться.</span><span class="sxs-lookup"><span data-stu-id="c34af-111">This page provides detailed steps to troubleshoot issues you might encounter.</span></span>


## <a name="learn-how-to-get-a-new-client-secret"></a><span data-ttu-id="c34af-112">Узнайте, как получить новый секрет клиента</span><span class="sxs-lookup"><span data-stu-id="c34af-112">Learn how to get a new client secret</span></span>
<span data-ttu-id="c34af-113">Если срок действия секрета клиента истекает или если вы неправильно предоставили копию при включите приложение-инструмент SIEM, вам потребуется получить новый секрет.</span><span class="sxs-lookup"><span data-stu-id="c34af-113">If your client secret expires or if you've misplaced the copy provided when you were enabling the SIEM tool application,  you'll need to get a new secret.</span></span>

1. <span data-ttu-id="c34af-114">Вход на портал [управления Azure.](https://portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="c34af-114">Login to the [Azure management portal](https://portal.azure.com).</span></span>

2. <span data-ttu-id="c34af-115">Выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c34af-115">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="c34af-116">Выберите клиента.</span><span class="sxs-lookup"><span data-stu-id="c34af-116">Select your tenant.</span></span>

4. <span data-ttu-id="c34af-117">Нажмите **кнопку Регистрация приложений**.</span><span class="sxs-lookup"><span data-stu-id="c34af-117">Click **App registrations**.</span></span> <span data-ttu-id="c34af-118">Затем в списке приложений выберите приложение.</span><span class="sxs-lookup"><span data-stu-id="c34af-118">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="c34af-119">Выберите **раздел Клавиши,** затем укажите описание ключа и укажите длительность действия ключа.</span><span class="sxs-lookup"><span data-stu-id="c34af-119">Select **Keys** section, then provide a key description and specify the key validity duration.</span></span>

6. <span data-ttu-id="c34af-120">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c34af-120">Click **Save**.</span></span> <span data-ttu-id="c34af-121">Отображается ключевое значение.</span><span class="sxs-lookup"><span data-stu-id="c34af-121">The key value is displayed.</span></span>

7. <span data-ttu-id="c34af-122">Скопируйте значение и сохраните его в безопасном месте.</span><span class="sxs-lookup"><span data-stu-id="c34af-122">Copy the value and save it in a safe place.</span></span>


## <a name="error-when-getting-a-refresh-access-token"></a><span data-ttu-id="c34af-123">Ошибка при получении маркера доступа к обновлению</span><span class="sxs-lookup"><span data-stu-id="c34af-123">Error when getting a refresh access token</span></span>
<span data-ttu-id="c34af-124">Если вы столкнулись с ошибкой при попытке получить маркер обновления при использовании API-API или средств SIEM-аналитики, необходимо добавить URL-адрес ответа для соответствующего приложения в Azure Active Directory.</span><span class="sxs-lookup"><span data-stu-id="c34af-124">If you encounter an error when trying to get a refresh token when using the threat intelligence API or SIEM tools, you'll need to add reply URL for relevant application in Azure Active Directory.</span></span>

1. <span data-ttu-id="c34af-125">Вход на портал [управления Azure.](https://ms.portal.azure.com)</span><span class="sxs-lookup"><span data-stu-id="c34af-125">Login to the [Azure management portal](https://ms.portal.azure.com).</span></span>

2. <span data-ttu-id="c34af-126">Выберите **Azure Active Directory**.</span><span class="sxs-lookup"><span data-stu-id="c34af-126">Select **Azure Active Directory**.</span></span>

3. <span data-ttu-id="c34af-127">Выберите клиента.</span><span class="sxs-lookup"><span data-stu-id="c34af-127">Select your tenant.</span></span>

4. <span data-ttu-id="c34af-128">Нажмите **кнопку Регистрация приложений**.</span><span class="sxs-lookup"><span data-stu-id="c34af-128">Click **App Registrations**.</span></span> <span data-ttu-id="c34af-129">Затем в списке приложений выберите приложение.</span><span class="sxs-lookup"><span data-stu-id="c34af-129">Then in the applications list, select the application.</span></span>

5. <span data-ttu-id="c34af-130">Добавьте следующий URL-адрес:</span><span class="sxs-lookup"><span data-stu-id="c34af-130">Add the following URL:</span></span>
   - <span data-ttu-id="c34af-131">Для Европейского Союза: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="c34af-131">For the European Union: `https://winatpmanagement-eu.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="c34af-132">Для Соединенного Королевства: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span><span class="sxs-lookup"><span data-stu-id="c34af-132">For the United Kingdom: `https://winatpmanagement-uk.securitycenter.windows.com/UserAuthenticationCallback`</span></span>
   - <span data-ttu-id="c34af-133">Для Соединенных Штатов:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback` .</span><span class="sxs-lookup"><span data-stu-id="c34af-133">For the United States:  `https://winatpmanagement-us.securitycenter.windows.com/UserAuthenticationCallback`.</span></span>
 
6. <span data-ttu-id="c34af-134">Щелкните **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="c34af-134">Click **Save**.</span></span>

## <a name="error-while-enabling-the-siem-connector-application"></a><span data-ttu-id="c34af-135">Ошибка при включении приложения соединиттеля SIEM</span><span class="sxs-lookup"><span data-stu-id="c34af-135">Error while enabling the SIEM connector application</span></span>
<span data-ttu-id="c34af-136">Если вы столкнулись с ошибкой при попытке включить соединителем SIEM-приложение, проверьте параметры блокатора всплывающее окна в браузере.</span><span class="sxs-lookup"><span data-stu-id="c34af-136">If you encounter an error when trying to enable the SIEM connector application, check the pop-up blocker settings of your browser.</span></span> <span data-ttu-id="c34af-137">Это может быть блокировка открываемого окна при вскрывии возможности.</span><span class="sxs-lookup"><span data-stu-id="c34af-137">It might be blocking the new window being opened when you enable the capability.</span></span>




><span data-ttu-id="c34af-138">Хотите испытать Microsoft Defender для конечной точки?</span><span class="sxs-lookup"><span data-stu-id="c34af-138">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="c34af-139">Зарегистрився для бесплатной пробной.</span><span class="sxs-lookup"><span data-stu-id="c34af-139">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-troubleshootsiem-belowfoldlink) 

## <a name="related-topics"></a><span data-ttu-id="c34af-140">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="c34af-140">Related topics</span></span>
- [<span data-ttu-id="c34af-141">Включение интеграции SIEM в Microsoft Defender для конечной точки</span><span class="sxs-lookup"><span data-stu-id="c34af-141">Enable SIEM integration in Microsoft Defender for Endpoint</span></span>](enable-siem-integration.md)
- [<span data-ttu-id="c34af-142">Настройте ArcSight, чтобы вытащить Microsoft Defender для обнаружения конечных точек</span><span class="sxs-lookup"><span data-stu-id="c34af-142">Configure ArcSight to pull Microsoft Defender for Endpoint detections</span></span>](configure-arcsight.md)
- [<span data-ttu-id="c34af-143">Притягивать обнаружения к средствам SIEM</span><span class="sxs-lookup"><span data-stu-id="c34af-143">Pull detections to your SIEM tools</span></span>](configure-siem.md)
- [<span data-ttu-id="c34af-144">Microsoft Defender для полей обнаружения конечных точек</span><span class="sxs-lookup"><span data-stu-id="c34af-144">Microsoft Defender for Endpoint Detection fields</span></span>](api-portal-mapping.md)
- [<span data-ttu-id="c34af-145">Pull Microsoft Defender для обнаружения конечных точек с помощью API REST</span><span class="sxs-lookup"><span data-stu-id="c34af-145">Pull Microsoft Defender for Endpoint detections using REST API</span></span>](pull-alerts-using-rest-api.md)
