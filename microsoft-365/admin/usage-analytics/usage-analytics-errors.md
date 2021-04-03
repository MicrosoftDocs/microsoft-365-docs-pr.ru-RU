---
title: Устранение неполадок аналитики использования Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: Узнайте, как устранить проблемы с помощью приложения шаблона Microsoft 365 Use Analytics.
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580742"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="4dd08-103">Устранение неполадок аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4dd08-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="4dd08-104">Ознакомьтесь со следующим списком сообщений об ошибках, чтобы получить помощь в наиболее распространенных проблемах с помощью аналитики использования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="4dd08-105">We are unable to process your request.</span><span class="sxs-lookup"><span data-stu-id="4dd08-105">We are unable to process your request.</span></span> <span data-ttu-id="4dd08-106">Сначала необходимо подписаться на эти данные из центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="4dd08-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="4dd08-107">**Код ошибки:** 422</span><span class="sxs-lookup"><span data-stu-id="4dd08-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="4dd08-108">**Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4dd08-109">**Причина:** Прежде чем подключиться к приложению, необходимо подписаться на данные центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="4dd08-110">Если этот шаг не будет сделан первым, вы не сможете подключиться к приложению шаблона, даже если вы предоставите свой ID клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="4dd08-111">**Чтобы устранить эту ошибку:** Чтобы подписаться на данные, перейдите в центр администрирования Отчеты Использования и найти \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> плитку аналитики использования Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4dd08-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="4dd08-112">Выберите кнопку **Начало** работы, а затем в открываемой области **Отчеты** включите параметр Make **data available to Microsoft 365 use analytics for Power BI** setting on and **Save**.</span><span class="sxs-lookup"><span data-stu-id="4dd08-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="4dd08-113">We are processing your data</span><span class="sxs-lookup"><span data-stu-id="4dd08-113">We are processing your data</span></span>

 <span data-ttu-id="4dd08-114">**Где вы увидите это сообщение:** В **плитке аналитики использования Microsoft 365** на **панели** мониторинга использования в центре администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="4dd08-115">**Причина:** Когда вы [решите](enable-usage-analytics.md) увидеть данные в приложении шаблона из центра администрирования Microsoft 365, система Microsoft 365 начинает создавать исторические данные об использовании для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4dd08-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="4dd08-116">В зависимости от размера клиента это действие может занять от 2 до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="4dd08-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="4dd08-117">**Чтобы исправить это:** Просто будьте терпеливы, но если сообщение  не изменится, чтобы ваши данные были готовы через 3 дня, обратитесь в [Корпорацию Майкрософт 365 для поддержки бизнеса.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="4dd08-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="4dd08-118">We are unable to process your request at this time.</span><span class="sxs-lookup"><span data-stu-id="4dd08-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="4dd08-119">We are still preparing the data for your organization</span><span class="sxs-lookup"><span data-stu-id="4dd08-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="4dd08-120">**Код ошибки**: 423</span><span class="sxs-lookup"><span data-stu-id="4dd08-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="4dd08-121">**Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4dd08-122">**Причина:** Когда вы [решите увидеть](enable-usage-analytics.md) данные в приложении шаблона из центра администрирования, система Microsoft 365 начинает создавать исторические данные об использовании для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="4dd08-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="4dd08-123">В зависимости от размера клиента этот шаг может занять от двух часов до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="4dd08-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="4dd08-124">**Чтобы исправить это:** Просто будьте терпеливы, но если сообщение  не меняется на ваши данные готовы даже через 3 дня с момента инициации, свяжитесь с [Microsoft 365 для поддержки бизнеса](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="4dd08-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="4dd08-125">The tenant ID you provided is not in the correct format</span><span class="sxs-lookup"><span data-stu-id="4dd08-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="4dd08-126">**Код ошибки**: 400</span><span class="sxs-lookup"><span data-stu-id="4dd08-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="4dd08-127">**Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4dd08-128">**Причина:** ID клиента — это guid и должен быть в формате xxxxx-xxxx-xxxx-xxxx-xxxx.</span><span class="sxs-lookup"><span data-stu-id="4dd08-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="4dd08-129">Если вы введите любую другую строку в поле ввода клиента, вы получите эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="4dd08-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="4dd08-130">**Чтобы устранить эту ошибку:** Перейдите к центру администрирования Отчеты Использования и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4dd08-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="4dd08-131">ID клиента указан на плитке.</span><span class="sxs-lookup"><span data-stu-id="4dd08-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="4dd08-132">Вы можете скопировать его здесь и вклеить в диалоговое окно для подключения к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="4dd08-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="4dd08-133">The tenant ID you provided is not recognized by our system</span><span class="sxs-lookup"><span data-stu-id="4dd08-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="4dd08-134">**Код ошибки**: 404</span><span class="sxs-lookup"><span data-stu-id="4dd08-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="4dd08-135">**Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4dd08-136">**Причина:** Предоставленный вами удостоверение клиента не является действительным или не существует.</span><span class="sxs-lookup"><span data-stu-id="4dd08-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="4dd08-137">**Чтобы устранить эту ошибку:** Перейдите к центру администрирования Отчеты Использования и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="4dd08-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="4dd08-138">ID клиента указан на плитке.</span><span class="sxs-lookup"><span data-stu-id="4dd08-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="4dd08-139">Вы можете скопировать его здесь и вклеить в диалоговое окно для подключения к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="4dd08-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="4dd08-140">Please re-enter your credentials to sign in to Power BI again</span><span class="sxs-lookup"><span data-stu-id="4dd08-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="4dd08-141">Код ошибки: 302</span><span class="sxs-lookup"><span data-stu-id="4dd08-141">Error Code: 302</span></span>
  
 <span data-ttu-id="4dd08-142">**Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4dd08-143">**Причина:** код авторизации не сработал; возможно, вам потребуется повторно ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="4dd08-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="4dd08-144">**Как исправить ошибку**: выйдите из Power BI, а затем войдите еще раз.</span><span class="sxs-lookup"><span data-stu-id="4dd08-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="4dd08-145">You do not have the right authorization to access to this data.</span><span class="sxs-lookup"><span data-stu-id="4dd08-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="4dd08-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span><span class="sxs-lookup"><span data-stu-id="4dd08-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="4dd08-147">**Код ошибки**: 403</span><span class="sxs-lookup"><span data-stu-id="4dd08-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="4dd08-148">**Где вы увидите это сообщение:** В Power BI при подключении к приложению Microsoft 365 Use Analytics или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4dd08-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="4dd08-149">**Причина:** Код авторизации не удалось, так как пользователь, который пытался подключиться к приложению шаблона, не имеет нужного уровня авторизации для доступа к этим данным.</span><span class="sxs-lookup"><span data-stu-id="4dd08-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="4dd08-150">**Чтобы устранить эту ошибку:** Предоставление учетных данных пользователя, который является глобальным администратором, администратором   **Exchange,** **администратором Skype для** бизнеса, администратором  **SharePoint,** глобальным читателем или читателем отчетов для подключения к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="4dd08-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="4dd08-151">Дополнительные [сведения см. в](../add-users/about-admin-roles.md) дополнительных сведениях о ролях администратора.</span><span class="sxs-lookup"><span data-stu-id="4dd08-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="4dd08-152">Refresh failed</span><span class="sxs-lookup"><span data-stu-id="4dd08-152">Refresh failed</span></span>

 <span data-ttu-id="4dd08-153">**Где выводится это сообщение:** в сообщениях электронной почты от Power BI или в сообщениях о сбоях в журнале обновления.</span><span class="sxs-lookup"><span data-stu-id="4dd08-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="4dd08-154">**Причина:** Иногда учетные данные пользователя, подключенного к приложению шаблона, сбрасываются и не обновляются в параметрах подключения приложения-шаблона, из-за чего пользователь может видеть ошибки сбоя обновления.</span><span class="sxs-lookup"><span data-stu-id="4dd08-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="4dd08-155">**Чтобы устранить эту ошибку:** В Power BI найдите набор данных, соответствующий шаблону Microsoft 365 Use Analytics, выберите обновление расписания и укажи учетные данные администратора. </span><span class="sxs-lookup"><span data-stu-id="4dd08-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="4dd08-156">Если это не работает, очистить кэш и повторно создать приложение шаблона.</span><span class="sxs-lookup"><span data-stu-id="4dd08-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
