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
description: Узнайте, как устранять проблемы с приложением шаблона аналитики использования Microsoft 365.
ms.openlocfilehash: bf8e4ece7b1e310d91f418f5388cae9aa27f2aa7
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841439"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="f1039-103">Устранение неполадок аналитики использования Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="f1039-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="f1039-104">Просмотрите приведенный ниже список сообщений об ошибках, чтобы получить справку по наиболее распространенным проблемам с аналитикой использования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="f1039-105">We are unable to process your request.</span><span class="sxs-lookup"><span data-stu-id="f1039-105">We are unable to process your request.</span></span> <span data-ttu-id="f1039-106">Сначала необходимо подписаться на эти данные из центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="f1039-107">**Код ошибки:** 422</span><span class="sxs-lookup"><span data-stu-id="f1039-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="f1039-108">**Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f1039-109">**Причина:** Перед подключением к приложению необходимо подписаться на данные из центра администрирования Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="f1039-110">Если это действие не выполняется, вы не сможете подключиться к приложению шаблона, даже если вы задаете идентификатор клиента Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="f1039-111">**Чтобы устранить эту ошибку, выполните указанные ниже действия.** Чтобы подписаться на данные, перейдите в центр администрирования, чтобы получить сведения \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">об использовании</a> и найти плитку аналитики использования Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f1039-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f1039-112">Нажмите кнопку " **получить Начало работы** ", а затем в открывшейся области **отчетов** , **чтобы сделать данные доступными для аналитики использования Microsoft 365 для Power BI** , на и **сохранить** .</span><span class="sxs-lookup"><span data-stu-id="f1039-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save** .</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="f1039-113">We are processing your data</span><span class="sxs-lookup"><span data-stu-id="f1039-113">We are processing your data</span></span>

 <span data-ttu-id="f1039-114">**Где отображается следующее сообщение:** На плитке **аналитика использования microsoft 365** на панели мониторинга **использования** в центре администрирования Майкрософт 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="f1039-115">**Причина:** Когда вы выдаете запрос [на просмотр данных в приложении шаблона](enable-usage-analytics.md) из центра администрирования Microsoft 365, система Microsoft 365 начинает создавать данные предыстории использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="f1039-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="f1039-116">В зависимости от размера клиента это действие может занять от 2 до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="f1039-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="f1039-117">**Чтобы устранить эту проблему, выполните указанные ниже действия.** Подождите, но если сообщение не будет изменено, **оно будет готово** через 3 дня, обратитесь в службу [поддержки Microsoft 365 для бизнеса](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f1039-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="f1039-118">We are unable to process your request at this time.</span><span class="sxs-lookup"><span data-stu-id="f1039-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="f1039-119">We are still preparing the data for your organization</span><span class="sxs-lookup"><span data-stu-id="f1039-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="f1039-120">**Код ошибки** : 423</span><span class="sxs-lookup"><span data-stu-id="f1039-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="f1039-121">**Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f1039-122">**Причина:** Когда вы выдаете запрос [на просмотр данных в приложении шаблона](enable-usage-analytics.md) из центра администрирования, система Microsoft 365 начинает создавать исторические данные об использовании в Организации.</span><span class="sxs-lookup"><span data-stu-id="f1039-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="f1039-123">В зависимости от размера клиента этот шаг может занять от двух до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="f1039-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="f1039-124">**Чтобы устранить эту проблему, выполните указанные ниже действия.** Подождите, но если сообщение не **переводится на свои данные** в течение еще 3 дней с момента запуска, обратитесь в службу [поддержки Microsoft 365 для бизнеса](../contact-support-for-business-products.md).</span><span class="sxs-lookup"><span data-stu-id="f1039-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="f1039-125">The tenant ID you provided is not in the correct format</span><span class="sxs-lookup"><span data-stu-id="f1039-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="f1039-126">**Код ошибки** : 400</span><span class="sxs-lookup"><span data-stu-id="f1039-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="f1039-127">**Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f1039-128">**Причина:** Идентификатор клиента является идентификатором GUID и должен быть в формате XXXXXXXX-XXXX-XXXX-XXXX-XXXXXXXXXXXX.</span><span class="sxs-lookup"><span data-stu-id="f1039-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="f1039-129">Если ввести другую строку в поле ввода клиента, возникнет эта ошибка.</span><span class="sxs-lookup"><span data-stu-id="f1039-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="f1039-130">**Чтобы устранить эту ошибку, выполните указанные ниже действия.** В центре администрирования отправляются \> **отчеты** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">об использовании</a> и поиске плитки аналитики использования Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f1039-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f1039-131">Идентификатор клиента отображается на плитке.</span><span class="sxs-lookup"><span data-stu-id="f1039-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="f1039-132">Вы можете скопировать его отсюда и вставить в диалоговое окно для подключения к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="f1039-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="f1039-133">The tenant ID you provided is not recognized by our system</span><span class="sxs-lookup"><span data-stu-id="f1039-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="f1039-134">**Код ошибки** : 404</span><span class="sxs-lookup"><span data-stu-id="f1039-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="f1039-135">**Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f1039-136">**Причина:** Указан недопустимый или несуществующий идентификатор клиента.</span><span class="sxs-lookup"><span data-stu-id="f1039-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="f1039-137">**Чтобы устранить эту ошибку, выполните указанные ниже действия.** В центре администрирования отправляются \> **отчеты** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">об использовании</a> и поиске плитки аналитики использования Microsoft 365 на главной странице панели мониторинга.</span><span class="sxs-lookup"><span data-stu-id="f1039-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="f1039-138">Идентификатор клиента отображается на плитке.</span><span class="sxs-lookup"><span data-stu-id="f1039-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="f1039-139">Вы можете скопировать его отсюда и вставить в диалоговое окно для подключения к приложению шаблона.</span><span class="sxs-lookup"><span data-stu-id="f1039-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="f1039-140">Please re-enter your credentials to sign in to Power BI again</span><span class="sxs-lookup"><span data-stu-id="f1039-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="f1039-141">Код ошибки: 302</span><span class="sxs-lookup"><span data-stu-id="f1039-141">Error Code: 302</span></span>
  
 <span data-ttu-id="f1039-142">**Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f1039-143">**Причина:** код авторизации не сработал; возможно, вам потребуется повторно ввести учетные данные.</span><span class="sxs-lookup"><span data-stu-id="f1039-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="f1039-144">**Как исправить ошибку** : выйдите из Power BI, а затем войдите еще раз.</span><span class="sxs-lookup"><span data-stu-id="f1039-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="f1039-145">You do not have the right authorization to access to this data.</span><span class="sxs-lookup"><span data-stu-id="f1039-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="f1039-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span><span class="sxs-lookup"><span data-stu-id="f1039-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="f1039-147">**Код ошибки** : 403</span><span class="sxs-lookup"><span data-stu-id="f1039-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="f1039-148">**Где отображается следующее сообщение:** В Power BI при подключении к приложению шаблона аналитики использования Microsoft 365 или при непосредственном вызове API-интерфейсов отчетов Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="f1039-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="f1039-149">**Причина:** Не удалось выполнить проверку подлинности, так как пользователь, который пытался подключиться к приложению-шаблону, не имеет правого уровня авторизации для доступа к этим данным.</span><span class="sxs-lookup"><span data-stu-id="f1039-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="f1039-150">**Чтобы устранить эту ошибку, выполните указанные ниже действия.** Предоставьте учетные данные пользователя, который является **глобальным администратором** , администратором **Exchange** , администратором **Skype для бизнеса** , администратором **SharePoint** , **глобальным читателям** или **читателями отчетов** для подключения к приложению-шаблону.</span><span class="sxs-lookup"><span data-stu-id="f1039-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin** , **Exchange admin** , **Skype for Business admin** , **SharePoint admin** , **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="f1039-151">Более подробную информацию можно узнать в статье [сведения о ролях администратора](../add-users/about-admin-roles.md) .</span><span class="sxs-lookup"><span data-stu-id="f1039-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="f1039-152">Refresh failed</span><span class="sxs-lookup"><span data-stu-id="f1039-152">Refresh failed</span></span>

 <span data-ttu-id="f1039-153">**Где выводится это сообщение:** в сообщениях электронной почты от Power BI или в сообщениях о сбоях в журнале обновления.</span><span class="sxs-lookup"><span data-stu-id="f1039-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="f1039-154">**Причина:** Иногда учетные данные пользователя, который подключился к приложению шаблона, сбрасываются и не обновляются в параметрах подключения приложения шаблона, в результате чего пользователь видит ошибки обновления.</span><span class="sxs-lookup"><span data-stu-id="f1039-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="f1039-155">**Чтобы устранить эту ошибку, выполните указанные ниже действия.** В Power BI Найдите набор данных, соответствующий приложению шаблона аналитики использования Microsoft 365, выберите пункт **расписание обновления** и укажите учетные данные администратора.</span><span class="sxs-lookup"><span data-stu-id="f1039-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="f1039-156">Если это не поможет, очистите кэш и повторно создайте приложение шаблона.</span><span class="sxs-lookup"><span data-stu-id="f1039-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
