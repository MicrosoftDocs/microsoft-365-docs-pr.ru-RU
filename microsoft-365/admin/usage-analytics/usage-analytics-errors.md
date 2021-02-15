---
title: Устранение неполадок аналитики использования Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
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
description: Узнайте, как устранять проблемы с шаблоном приложения Microsoft 365 Usage Analytics.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841439"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="f99a4-103">Устранение неполадок аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f99a4-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="f99a4-104">Изучите следующий список сообщений об ошибках, чтобы получить помощь по наиболее распространенным вопросам аналитики использования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="f99a4-105">We are unable to process your request.</span><span class="sxs-lookup"><span data-stu-id="f99a4-105">We are unable to process your request.</span></span> <span data-ttu-id="f99a4-106">Сначала необходимо подписаться на эти данные из Центра администрирования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f99a4-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="f99a4-107">**Код ошибки:** 422</span><span class="sxs-lookup"><span data-stu-id="f99a4-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="f99a4-108">**Где вы увидите это сообщение:** В Power BI при подключении к приложению "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f99a4-109">**Причина:** Перед подключением к приложению необходимо подписаться на данные из Центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="f99a4-110">Если это не сделать сначала, вы не сможете подключиться к приложению шаблона, даже если укажете свой ИД клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="f99a4-111">**Чтобы устранить эту ошибку:** Чтобы подписаться на данные, перейдите в Центр администрирования "Использование отчетов" и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f99a4-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f99a4-112">Выберите **кнопку "Начало** работы", а затем в открывскойся области "Отчеты" включите параметр "Сделать данные доступными для аналитики использования **Microsoft 365"** и "Сохранить" **в** Power BI. </span><span class="sxs-lookup"><span data-stu-id="f99a4-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="f99a4-113">We are processing your data</span><span class="sxs-lookup"><span data-stu-id="f99a4-113">We are processing your data</span></span>

 <span data-ttu-id="f99a4-114">**Где вы увидите это сообщение:** На **плитке аналитики использования Microsoft 365** на информационной панели "Использование" в Центре администрирования Microsoft 365. </span><span class="sxs-lookup"><span data-stu-id="f99a4-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="f99a4-115">**Причина:** Если вы [решите](enable-usage-analytics.md) увидеть данные в приложении шаблона из Центра администрирования Microsoft 365, система Microsoft 365 начнет создавать исторические данные об использовании для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f99a4-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="f99a4-116">В зависимости от размера клиента это действие может занять от 2 до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="f99a4-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="f99a4-117">**Чтобы устранить эту проблему:** Просто помялись, но если сообщение не изменится на Ваши данные, готово **через** 3 дня, обратитесь в службу поддержки [Microsoft 365 для бизнеса.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="f99a4-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="f99a4-118">We are unable to process your request at this time.</span><span class="sxs-lookup"><span data-stu-id="f99a4-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="f99a4-119">We are still preparing the data for your organization</span><span class="sxs-lookup"><span data-stu-id="f99a4-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="f99a4-120">**Код ошибки**: 423</span><span class="sxs-lookup"><span data-stu-id="f99a4-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="f99a4-121">**Где вы увидите это сообщение:** В Power BI при подключении к шаблону "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f99a4-122">**Причина:** Если вы [решите увидеть](enable-usage-analytics.md) данные в приложении шаблона из Центра администрирования, система Microsoft 365 начнет создавать исторические данные об использовании для вашей организации.</span><span class="sxs-lookup"><span data-stu-id="f99a4-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="f99a4-123">В зависимости от размера клиента этот шаг может занять от двух до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="f99a4-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="f99a4-124">**Чтобы устранить эту проблему:** Просто помялись, но если  сообщение не изменится на Ваши данные, оно будет готово даже через 3 дня с момента инициации, обратитесь в службу поддержки [Microsoft 365 для бизнеса.](../contact-support-for-business-products.md)</span><span class="sxs-lookup"><span data-stu-id="f99a4-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="f99a4-125">The tenant ID you provided is not in the correct format</span><span class="sxs-lookup"><span data-stu-id="f99a4-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="f99a4-126">**Код ошибки**: 400</span><span class="sxs-lookup"><span data-stu-id="f99a4-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="f99a4-127">**Где вы увидите это сообщение:** В Power BI при подключении к шаблону "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f99a4-128">**Причина:** ИД клиента — это guid, который должен иметь формат xxxxxxxxx-xxxx-xxxx-xxxx-xxxxxx.</span><span class="sxs-lookup"><span data-stu-id="f99a4-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="f99a4-129">Если ввести любую другую строку в поле ввода клиента, вы получите эту ошибку.</span><span class="sxs-lookup"><span data-stu-id="f99a4-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="f99a4-130">**Чтобы устранить эту ошибку:** Перейдите в центр администрирования "Отчеты об использовании" и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f99a4-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f99a4-131">На плитке указан ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="f99a4-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="f99a4-132">Вы можете скопировать его здесь и вкопировать в диалоговое окно для подключения к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="f99a4-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="f99a4-133">The tenant ID you provided is not recognized by our system</span><span class="sxs-lookup"><span data-stu-id="f99a4-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="f99a4-134">**Код ошибки**: 404</span><span class="sxs-lookup"><span data-stu-id="f99a4-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="f99a4-135">**Где вы увидите это сообщение:** В Power BI при подключении к приложению "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f99a4-136">**Причина:** Предоставленный вами ИД клиента не является допустимым или не существует.</span><span class="sxs-lookup"><span data-stu-id="f99a4-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="f99a4-137">**Чтобы устранить эту ошибку:** Перейдите в центр администрирования "Отчеты об использовании" и найдите плитку аналитики использования \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a> Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f99a4-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f99a4-138">На плитке указан ИД клиента.</span><span class="sxs-lookup"><span data-stu-id="f99a4-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="f99a4-139">Вы можете скопировать его здесь и вкопировать в диалоговое окно для подключения к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="f99a4-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="f99a4-140">Please re-enter your credentials to sign in to Power BI again</span><span class="sxs-lookup"><span data-stu-id="f99a4-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="f99a4-141">Код ошибки: 302</span><span class="sxs-lookup"><span data-stu-id="f99a4-141">Error Code: 302</span></span>
  
 <span data-ttu-id="f99a4-142">**Где вы увидите это сообщение:** В Power BI при подключении к приложению "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f99a4-143">**Причина:** код авторизации не сработал; возможно, вам потребуется повторно ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f99a4-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="f99a4-144">**Как исправить ошибку**: выйдите из Power BI, а затем войдите еще раз.</span><span class="sxs-lookup"><span data-stu-id="f99a4-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="f99a4-145">You do not have the right authorization to access to this data.</span><span class="sxs-lookup"><span data-stu-id="f99a4-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="f99a4-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span><span class="sxs-lookup"><span data-stu-id="f99a4-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="f99a4-147">**Код ошибки**: 403</span><span class="sxs-lookup"><span data-stu-id="f99a4-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="f99a4-148">**Где вы увидите это сообщение:** В Power BI при подключении к приложению "Аналитика использования Microsoft 365" или при непосредственном вызове API отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f99a4-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f99a4-149">**Причина:** Сбой кода авторизации, так как пользователь, пытающийся подключиться к приложению шаблона, не имеет нужного уровня авторизации для доступа к этим данным.</span><span class="sxs-lookup"><span data-stu-id="f99a4-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="f99a4-150">**Чтобы устранить эту ошибку:** Укажете учетные  данные глобального администратора, **администратора Exchange,** **администратора Skype** для  бизнеса,  **администратора SharePoint,** глобального читателя или читателя отчетов, чтобы подключиться к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="f99a4-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="f99a4-151">Дополнительные [сведения см. в](../add-users/about-admin-roles.md) сведениях о ролях администраторов.</span><span class="sxs-lookup"><span data-stu-id="f99a4-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="f99a4-152">Refresh failed</span><span class="sxs-lookup"><span data-stu-id="f99a4-152">Refresh failed</span></span>

 <span data-ttu-id="f99a4-153">**Где выводится это сообщение:** в сообщениях электронной почты от Power BI или в сообщениях о сбоях в журнале обновления.</span><span class="sxs-lookup"><span data-stu-id="f99a4-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="f99a4-154">**Причина:** Иногда учетные данные пользователя, подключенного к приложению шаблона, сбрасываются и не обновляются в параметрах подключения приложения шаблона, что приводит к ошибкам обновления.</span><span class="sxs-lookup"><span data-stu-id="f99a4-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="f99a4-155">**Чтобы устранить эту ошибку:** В Power BI найдите набор данных, соответствующий шаблону приложения "Аналитика использования Microsoft 365", выберите обновление расписания и укажийте учетные данные администратора. </span><span class="sxs-lookup"><span data-stu-id="f99a4-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="f99a4-156">Если это не работает, очищайте кэш и повторно создайте приложение шаблона.</span><span class="sxs-lookup"><span data-stu-id="f99a4-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
