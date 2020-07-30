---
title: Настройка стандартных или целевых вариантов выпуска
f1.keywords:
- CSH
ms.author: sirkkuw
author: sirkkuw
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
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Узнайте, как настроить выпуск для новых обновлений продуктов и компонентов в центре администрирования Microsoft 365.
ms.openlocfilehash: 3baec050f33893357b25c832552643cf3a6d10d0
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502883"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="ba5c3-103">Настройка стандартных или целевых вариантов выпуска</span><span class="sxs-lookup"><span data-stu-id="ba5c3-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="ba5c3-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-104">The admin center is changing.</span></span> <span data-ttu-id="ba5c3-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span><span class="sxs-lookup"><span data-stu-id="ba5c3-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="ba5c3-106">С помощью Microsoft 365 вы получаете новые обновления и функции продуктов, когда они становятся доступны, а не ежедневное обновление в течение нескольких лет.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-106">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="ba5c3-107">Таким образом, вам не нужно проводить дорогостоящие обновления каждые несколько лет.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-107">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="ba5c3-108">Вы можете выбрать, как ваша организация будет их получать.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-108">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="ba5c3-109">Например, вы можете подписаться на программу раннего доступа, чтобы ваша организация получала обновления одной из первых, а также сделать так, чтобы они были доступны только определенным людям.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-109">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="ba5c3-110">Вы также можете оставить расписание выпусков по умолчанию и получать обновления позже.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-110">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="ba5c3-111">В этой статье описываются различные варианты выпуска и способы их использования в Организации.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-111">This article explains the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ba5c3-112">Обновления Microsoft 365, описанные в этой статье, относятся к Microsoft 365, SharePoint Online и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-112">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="ba5c3-113">Они не затрагивают Skype для бизнеса и связанные с ним службы.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-113">They do not apply to Skype for Business and related services.</span></span> <span data-ttu-id="ba5c3-114">Эти варианты выпуска предназначены для достижения наилучших усилий при выпуске изменений в Microsoft 365, но не всегда и не поддерживаются ни для каких обновлений.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-114">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> 

> [!NOTE]
> <span data-ttu-id="ba5c3-115">Сведения о каналах обновления для приложений приведены в разделе [Обзор каналов обновления для приложений Microsoft 365](https://docs.microsoft.com/deployoffice/overview-update-channels).</span><span class="sxs-lookup"><span data-stu-id="ba5c3-115">For information about update channels for applications, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="ba5c3-116">Принцип действия проверки выпуска</span><span class="sxs-lookup"><span data-stu-id="ba5c3-116">How it works - release validation</span></span>

<span data-ttu-id="ba5c3-117">Любой новый выпуск сначала тестируется и проверяется группой компонентов, а затем целиком группой компонентов Microsoft 365, а затем всеми Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="ba5c3-118">Следующий этап после внутреннего испытания и проверки  **выпуск Targeted** (прежнее название  "Первый выпуск" или "Программа раннего доступа") для пользователей с такой программой доступа.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="ba5c3-119">На каждом круге выпуска Майкрософт собирает отзывы и проверяет качество на основании главных показателей использования.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="ba5c3-120">Такая прогрессивная проверка используется для обеспечения надежности всемирного выпуска.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="ba5c3-121">Эти выпуски отображены на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-121">The releases are pictured in the following figure.</span></span> 
  
![Освобождение звонков проверки для Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="ba5c3-123">Для получения существенных обновлений клиенты изначально уведомляются о [планах Microsoft 365](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="ba5c3-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="ba5c3-124">Поскольку обновление ближе к развертыванию, оно передается через [Центр сообщений Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="ba5c3-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="ba5c3-125">Чтобы получить доступ к центру сообщений через [центр администрирования](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center), вам нужна учетная запись Microsoft 365 или Azure AD.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="ba5c3-126">У пользователей Microsoft 365 Home Plan нет центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="ba5c3-127">Программа "Стандартный выпуск"</span><span class="sxs-lookup"><span data-stu-id="ba5c3-127">Standard release</span></span>

<span data-ttu-id="ba5c3-128">Это параметр по умолчанию, в котором пользователи и пользователи получают последние обновления при широком выпуске всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="ba5c3-129">Рекомендуется не допустить большинства пользователей в **стандартном выпуске** , ИТ-специалистах и опытных пользователей в **целевом выпуске** для оценки новых функций и подготовки Teams к поддержке бизнес-пользователей и руководителей.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="ba5c3-130">при переходе от стандартного выпуска к выпуску Targeted существует вероятность того, что ваши пользователи не смогут работать с некоторыми функциями, если они еще не представлены в стандартном выпуске.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="ba5c3-131">Выпуск Targeted</span><span class="sxs-lookup"><span data-stu-id="ba5c3-131">Targeted release</span></span>

<span data-ttu-id="ba5c3-p107">Выбрав этот вариант, вы и ваши пользователи одними из первых увидите последние обновления и сможете помочь улучшить продукт, отправив нам отзывы. Вы можете выбрать, будет ли получать обновления вся организация, или только некоторые люди.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ba5c3-p108">выпуск масштабных и сложных обновлений занимает больше времени, чем требуется на выпуск более мелких изменений. Это необходимо, чтобы пользователи не столкнулись ни с какими проблемами. Сроки выпусков могут меняться.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="ba5c3-136">Выпуск Targeted для всей организации</span><span class="sxs-lookup"><span data-stu-id="ba5c3-136">Targeted release for entire organization</span></span>

<span data-ttu-id="ba5c3-137">Если вы [настроили параметр Release в центре администрирования](#set-up-the-release-option-in-the-admin-center) для этого параметра, все ваши пользователи будут получать доступ к целевому выпуску.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="ba5c3-138">Для организаций, в которых насчитывается больше 300 пользователей, рекомендуем попробовать тестовую подписку на эту программу доступа.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="ba5c3-139">Чтобы получить сведения о тестовой подписке, обратитесь к представителю Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="ba5c3-140">Выпуск Targeted для выбранных пользователей</span><span class="sxs-lookup"><span data-stu-id="ba5c3-140">Targeted release for selected users</span></span>

<span data-ttu-id="ba5c3-141">Если вы [настроили параметр Release в центре администрирования](#set-up-the-release-option-in-the-admin-center) для этого параметра, вы можете определить определенных пользователей, обычно опытных пользователей, получать ранний доступ к функциям и функциям.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="ba5c3-142">Преимущества выпуска Targeted</span><span class="sxs-lookup"><span data-stu-id="ba5c3-142">Benefits of Targeted release</span></span>

<span data-ttu-id="ba5c3-143">Целевой выпуск позволяет администраторам, руководителям и другим лицам, ответственным за обновления Microsoft 365, подготовится к выполнению изменений, предоставляя им следующие возможности:</span><span class="sxs-lookup"><span data-stu-id="ba5c3-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="ba5c3-144">испытать и проверить новые обновления, прежде чем они станут доступны для всех пользователей в организации;</span><span class="sxs-lookup"><span data-stu-id="ba5c3-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="ba5c3-145">подготовить уведомление для пользователей и документацию до всемирного выпуска обновлений;</span><span class="sxs-lookup"><span data-stu-id="ba5c3-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="ba5c3-146">подготовить внутреннюю службу технической поддержки к предстоящим изменениям;</span><span class="sxs-lookup"><span data-stu-id="ba5c3-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="ba5c3-147">выполнить проверку на предмет соответствия требованиям и безопасности;</span><span class="sxs-lookup"><span data-stu-id="ba5c3-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="ba5c3-148">воспользоваться средствами управления функциями, где это применимо, для контроля за выпуском обновлений для пользователей.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="ba5c3-149">Настройка функции выпуска в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="ba5c3-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="ba5c3-150">Вы можете изменить способ получения обновлений Microsoft 365, выполнив указанные ниже действия.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="ba5c3-151">Для участия в этой функции необходимо быть глобальным администратором Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="ba5c3-152">Для вступления изменений в силу в Microsoft 365 может потребоваться до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="ba5c3-153">Если вы выберете выпуск обновлений на канале Targeted, а затем откажетесь от него, ваши пользователи потеряют доступ к тем возможностям, которые еще не вошли в стандартный выпуск.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="ba5c3-154">В центре администрирования выберите параметр **Параметры**  >  **Организации**, а затем на вкладке **профиль организации** выберите **параметры выпуска**.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="ba5c3-155">Чтобы отключить целевой выпуск, выберите **стандартный выпуск**, а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="ba5c3-156">Чтобы включить целевой выпуск для всех пользователей в Организации, выберите вариант **выпуск Targeted для**всех пользователей, а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="ba5c3-157">Чтобы включить целевой выпуск для некоторых пользователей в Организации, установите флажок **нацеленный выпуск для выбранных пользователей**, а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="ba5c3-158">Нажмите кнопку **выбрать пользователей** , чтобы добавлять пользователей по одному, или **отправьте пользователей** , чтобы добавить их в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="ba5c3-159">Завершив добавление пользователей, нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="ba5c3-160">Дополнительные сведения</span><span class="sxs-lookup"><span data-stu-id="ba5c3-160">Learn more</span></span>

<span data-ttu-id="ba5c3-161">Узнайте, как [управлять сообщениями](https://docs.microsoft.com/office365/admin/manage/message-center) в [центре сообщений Microsoft 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) , чтобы получать уведомления о предстоящих обновлениях и выпусках Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="ba5c3-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
