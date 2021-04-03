---
title: Настройка стандартных или целевых параметров выпуска
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
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
description: Узнайте, как настроить параметр выпуска для новых продуктов и обновлений компонентов в центре администрирования Microsoft 365.
ms.openlocfilehash: d3692f2e1cca58fec81f2ad492b9232d5576f99b
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579258"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="35c4f-103">Настройка стандартных или целевых параметров выпуска</span><span class="sxs-lookup"><span data-stu-id="35c4f-103">Set up the Standard or Targeted release options</span></span>

> [!IMPORTANT]
> <span data-ttu-id="35c4f-104">Обновления Microsoft 365, описанные в этой статье, применяются к Microsoft 365, SharePoint Online и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="35c4f-104">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="35c4f-105">Эти параметры выпуска являются целевыми, наилучшими способами для выпуска изменений в Microsoft 365, но не могут быть гарантированы во все времена или для всех обновлений.</span><span class="sxs-lookup"><span data-stu-id="35c4f-105">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="35c4f-106">Они не применяются к приложениям Microsoft 365, Skype для бизнеса, Microsoft Teams и связанным службам.</span><span class="sxs-lookup"><span data-stu-id="35c4f-106">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="35c4f-107">Сведения о вариантах выпуска приложений Microsoft 365 см. в обзоре каналов обновления [для приложений Microsoft 365.](/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="35c4f-107">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="35c4f-108">С Помощью Microsoft 365 вы получаете новые обновления и функции продукта по мере их получения, а не дорогостоящие обновления каждые несколько лет.</span><span class="sxs-lookup"><span data-stu-id="35c4f-108">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="35c4f-109">Таким образом, вам не нужно проводить дорогостоящие обновления каждые несколько лет.</span><span class="sxs-lookup"><span data-stu-id="35c4f-109">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="35c4f-110">Вы можете выбрать, как ваша организация будет их получать.</span><span class="sxs-lookup"><span data-stu-id="35c4f-110">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="35c4f-111">Например, вы можете подписаться на программу раннего доступа, чтобы ваша организация получала обновления одной из первых, а также сделать так, чтобы они были доступны только определенным людям.</span><span class="sxs-lookup"><span data-stu-id="35c4f-111">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="35c4f-112">Вы также можете оставить расписание выпусков по умолчанию и получать обновления позже.</span><span class="sxs-lookup"><span data-stu-id="35c4f-112">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="35c4f-113">В этой статье рассказывается о различных вариантах выпуска и о том, как их можно использовать для организации.</span><span class="sxs-lookup"><span data-stu-id="35c4f-113">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="35c4f-114">Принцип действия проверки выпуска</span><span class="sxs-lookup"><span data-stu-id="35c4f-114">How it works - release validation</span></span>

<span data-ttu-id="35c4f-115">Любой новый выпуск сначала проверяется и проверяется командой функций, а затем всей командой функций Microsoft 365, а затем всей корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35c4f-115">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="35c4f-116">Следующий этап после внутреннего испытания и проверки  **выпуск Targeted** (прежнее название  "Первый выпуск" или "Программа раннего доступа") для пользователей с такой программой доступа.</span><span class="sxs-lookup"><span data-stu-id="35c4f-116">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="35c4f-117">На каждом круге выпуска Майкрософт собирает отзывы и проверяет качество на основании главных показателей использования.</span><span class="sxs-lookup"><span data-stu-id="35c4f-117">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="35c4f-118">Такая прогрессивная проверка используется для обеспечения надежности всемирного выпуска.</span><span class="sxs-lookup"><span data-stu-id="35c4f-118">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="35c4f-119">Эти выпуски отображены на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="35c4f-119">The releases are pictured in the following figure.</span></span> 
  
![Кольца проверки выпуска для Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="35c4f-121">Для значительных обновлений клиенты сначала уведомлены дорожной картой [Microsoft 365.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="35c4f-121">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="35c4f-122">По мере того как обновление становится ближе к развертыванию, оно передается через [центр сообщений Microsoft 365.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="35c4f-122">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="35c4f-123">Чтобы получить доступ к центру сообщений через центр администрирования, нужна учетная запись Microsoft 365 или Azure [AD.](/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="35c4f-123">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="35c4f-124">У пользователей домашнего плана Microsoft 365 нет центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="35c4f-124">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="35c4f-125">Программа "Стандартный выпуск"</span><span class="sxs-lookup"><span data-stu-id="35c4f-125">Standard release</span></span>

<span data-ttu-id="35c4f-126">Это вариант по умолчанию, когда вы и ваши пользователи получают последние обновления, когда они будут выпущены широко для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="35c4f-126">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="35c4f-127">Хорошая практика состоит в том, чтобы оставить большинство пользователей в  выпуске **Standard** и ИТ-специалистов и пользователей питания в целевом выпуске для оценки новых функций и подготовки групп для поддержки бизнес-пользователей и руководителей.</span><span class="sxs-lookup"><span data-stu-id="35c4f-127">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="35c4f-128">при переходе от стандартного выпуска к выпуску Targeted существует вероятность того, что ваши пользователи не смогут работать с некоторыми функциями, если они еще не представлены в стандартном выпуске.</span><span class="sxs-lookup"><span data-stu-id="35c4f-128">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="35c4f-129">Выпуск Targeted</span><span class="sxs-lookup"><span data-stu-id="35c4f-129">Targeted release</span></span>

<span data-ttu-id="35c4f-p106">Выбрав этот вариант, вы и ваши пользователи одними из первых увидите последние обновления и сможете помочь улучшить продукт, отправив нам отзывы. Вы можете выбрать, будет ли получать обновления вся организация, или только некоторые люди.</span><span class="sxs-lookup"><span data-stu-id="35c4f-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="35c4f-p107">выпуск масштабных и сложных обновлений занимает больше времени, чем требуется на выпуск более мелких изменений. Это необходимо, чтобы пользователи не столкнулись ни с какими проблемами. Сроки выпусков могут меняться.</span><span class="sxs-lookup"><span data-stu-id="35c4f-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="35c4f-134">Выпуск Targeted для всей организации</span><span class="sxs-lookup"><span data-stu-id="35c4f-134">Targeted release for entire organization</span></span>

<span data-ttu-id="35c4f-135">Если вы [настроите параметр выпуска](#set-up-the-release-option-in-the-admin-center) в центре администрирования для этого параметра, все пользователи получат целевой доступ к выпуску.</span><span class="sxs-lookup"><span data-stu-id="35c4f-135">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="35c4f-136">Для организаций, в которых насчитывается больше 300 пользователей, рекомендуем попробовать тестовую подписку на эту программу доступа.</span><span class="sxs-lookup"><span data-stu-id="35c4f-136">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="35c4f-137">Чтобы получить сведения о тестовой подписке, обратитесь к представителю Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="35c4f-137">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="35c4f-138">Выпуск Targeted для выбранных пользователей</span><span class="sxs-lookup"><span data-stu-id="35c4f-138">Targeted release for selected users</span></span>

<span data-ttu-id="35c4f-139">При [настройках](#set-up-the-release-option-in-the-admin-center) параметра выпуска в центре администрирования для этого параметра можно определить конкретных пользователей, как правило, power users, для получения раннего доступа к функциям и функциональным возможностям.</span><span class="sxs-lookup"><span data-stu-id="35c4f-139">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="35c4f-140">Преимущества выпуска Targeted</span><span class="sxs-lookup"><span data-stu-id="35c4f-140">Benefits of Targeted release</span></span>

<span data-ttu-id="35c4f-141">Целевой выпуск позволяет администраторам, менеджерам изменений или любому другому ответственному за обновления Microsoft 365 подготовиться к предстоящим изменениям, разрешив им:</span><span class="sxs-lookup"><span data-stu-id="35c4f-141">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="35c4f-142">испытать и проверить новые обновления, прежде чем они станут доступны для всех пользователей в организации;</span><span class="sxs-lookup"><span data-stu-id="35c4f-142">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="35c4f-143">подготовить уведомление для пользователей и документацию до всемирного выпуска обновлений;</span><span class="sxs-lookup"><span data-stu-id="35c4f-143">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="35c4f-144">подготовить внутреннюю службу технической поддержки к предстоящим изменениям;</span><span class="sxs-lookup"><span data-stu-id="35c4f-144">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="35c4f-145">выполнить проверку на предмет соответствия требованиям и безопасности;</span><span class="sxs-lookup"><span data-stu-id="35c4f-145">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="35c4f-146">воспользоваться средствами управления функциями, где это применимо, для контроля за выпуском обновлений для пользователей.</span><span class="sxs-lookup"><span data-stu-id="35c4f-146">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="35c4f-147">Настройка параметра выпуска в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="35c4f-147">Set up the release option in the admin center</span></span>

<span data-ttu-id="35c4f-148">Вы можете изменить, как ваша организация получает обновления Microsoft 365, следуя этим шагам.</span><span class="sxs-lookup"><span data-stu-id="35c4f-148">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="35c4f-149">Вы должны быть глобальным администратором в Microsoft 365, чтобы выбрать.</span><span class="sxs-lookup"><span data-stu-id="35c4f-149">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="35c4f-150">Для внесения изменений в Microsoft 365 может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="35c4f-150">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="35c4f-151">Если вы выберете выпуск обновлений на канале Targeted, а затем откажетесь от него, ваши пользователи потеряют доступ к тем возможностям, которые еще не вошли в стандартный выпуск.</span><span class="sxs-lookup"><span data-stu-id="35c4f-151">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="35c4f-152">В центре администрирования перейдите к параметру **Settings** Org Setting , а на вкладке  >   **профилей** Организации выберите **параметры выпуска.**</span><span class="sxs-lookup"><span data-stu-id="35c4f-152">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="35c4f-153">Чтобы отключить целевой выпуск, выберите **стандартный выпуск,** а затем выберите **сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="35c4f-153">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="35c4f-154">Чтобы включить целевой выпуск для всех пользователей в организации, выберите целевой выпуск для **всех,** а затем **выберите сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="35c4f-154">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="35c4f-155">Чтобы включить целевой выпуск для некоторых людей в организации, выберите целевой выпуск для выбранных **пользователей,** а затем **выберите Сохранить изменения.**</span><span class="sxs-lookup"><span data-stu-id="35c4f-155">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="35c4f-156">Выберите **Выберите пользователей,** чтобы добавить пользователей по одному за раз, или **Загрузите** пользователей, чтобы добавить их оптом.</span><span class="sxs-lookup"><span data-stu-id="35c4f-156">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="35c4f-157">После добавления пользователей выберите Сохранить **изменения.**</span><span class="sxs-lookup"><span data-stu-id="35c4f-157">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="35c4f-158">Подробнее</span><span class="sxs-lookup"><span data-stu-id="35c4f-158">Learn more</span></span>

<span data-ttu-id="35c4f-159">Узнайте, как [управлять сообщениями](/office365/admin/manage/message-center) в центре [сообщений Microsoft 365,](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) чтобы получать уведомления о предстоящих обновлениях и выпусках Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="35c4f-159">Discover how to [manage messages](/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>

## <a name="related-articles"></a><span data-ttu-id="35c4f-160">Связанные статьи</span><span class="sxs-lookup"><span data-stu-id="35c4f-160">Related Articles</span></span>

[<span data-ttu-id="35c4f-161">Программа предварительной оценки Office</span><span class="sxs-lookup"><span data-stu-id="35c4f-161">Office Insider</span></span>](https://insider.office.com/join/windows)
