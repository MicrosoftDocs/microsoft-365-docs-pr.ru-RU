---
title: Настройка стандартных или целевых выпусков
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
description: Узнайте, как настроить выпуск обновлений новых продуктов и компонентов в Центре администрирования Microsoft 365.
ms.openlocfilehash: 99a2660af9d8756bf4faf1cf3eddfe142a7c87bf
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114493"
---
# <a name="set-up-the-standard-or-targeted-release-options"></a><span data-ttu-id="4e7f7-103">Настройка стандартных или целевых выпусков</span><span class="sxs-lookup"><span data-stu-id="4e7f7-103">Set up the Standard or Targeted release options</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="4e7f7-104">Изменяется Центр администрирования.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-104">The admin center is changing.</span></span> <span data-ttu-id="4e7f7-105">Если ваш интерфейс не соответствует приведенным здесь сведениям, см. раздел [О новом Центре администрирования Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span><span class="sxs-lookup"><span data-stu-id="4e7f7-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

> [!IMPORTANT]
> <span data-ttu-id="4e7f7-106">Обновления Microsoft 365, описанные в этой статье, применимы к Microsoft 365, SharePoint Online и Exchange Online.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-106">The Microsoft 365 updates described in this article apply to Microsoft 365, SharePoint Online, and Exchange Online.</span></span> <span data-ttu-id="4e7f7-107">Эти параметры выпуска являются целевыми и наилучшими способами выпуска изменений в Microsoft 365, но не могут быть гарантированы всегда или для всех обновлений.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-107">These release options are targeted, best effort ways to release changes to Microsoft 365 but cannot be guaranteed at all times or for all updates.</span></span> <span data-ttu-id="4e7f7-108">Они не применяются к приложениям Microsoft 365, Skype для бизнеса, Microsoft Teams и связанным службам.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-108">They do not apply to Microsoft 365 Apps, Skype for Business, Microsoft Teams, and related services.</span></span> <span data-ttu-id="4e7f7-109">Сведения о вариантах выпуска приложений Microsoft 365 см. в обзоре каналов обновления для [приложений Microsoft 365.](https://docs.microsoft.com/deployoffice/overview-update-channels)</span><span class="sxs-lookup"><span data-stu-id="4e7f7-109">For information about release options for Microsoft 365 Apps, see [Overview of update channels for Microsoft 365 Apps](https://docs.microsoft.com/deployoffice/overview-update-channels).</span></span>

<span data-ttu-id="4e7f7-110">В Microsoft 365 вы получаете новые обновления продуктов и функции по мере их получения, а не делаете дорогостоящие обновления каждые несколько лет.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-110">With Microsoft 365, you receive new product updates and features as they become available instead of doing costly updates every few years.</span></span> <span data-ttu-id="4e7f7-111">Таким образом, вам не нужно проводить дорогостоящие обновления каждые несколько лет.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-111">You can manage how your organization receives these updates.</span></span> <span data-ttu-id="4e7f7-112">Вы можете выбрать, как ваша организация будет их получать.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-112">For example, you can sign up for an early release so that your organization receives updates first.</span></span> <span data-ttu-id="4e7f7-113">Например, вы можете подписаться на программу раннего доступа, чтобы ваша организация получала обновления одной из первых, а также сделать так, чтобы они были доступны только определенным людям.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-113">You can designate that only certain individuals receive the updates.</span></span> <span data-ttu-id="4e7f7-114">Вы также можете оставить расписание выпусков по умолчанию и получать обновления позже.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-114">Or, you can remain on the default release schedule and receive the updates later.</span></span> <span data-ttu-id="4e7f7-115">В этой статье рассказывается о различных вариантах выпуска и о том, как их можно использовать для своей организации.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-115">This article explains the different release options and how you can use them for your organization.</span></span>

## <a name="how-it-works---release-validation"></a><span data-ttu-id="4e7f7-116">Принцип действия проверки выпуска</span><span class="sxs-lookup"><span data-stu-id="4e7f7-116">How it works - release validation</span></span>

<span data-ttu-id="4e7f7-117">Любой новый выпуск сначала проверяется и проверяется командой функций, а затем всей командой функций Microsoft 365, а затем — всей корпорацией Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-117">Any new release is first tested and validated by the feature team, then by the entire Microsoft 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="4e7f7-118">Следующий этап после внутреннего испытания и проверки  **выпуск Targeted** (прежнее название  "Первый выпуск" или "Программа раннего доступа") для пользователей с такой программой доступа.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-118">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="4e7f7-119">На каждом круге выпуска Майкрософт собирает отзывы и проверяет качество на основании главных показателей использования.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-119">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="4e7f7-120">Такая прогрессивная проверка используется для обеспечения надежности всемирного выпуска.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-120">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="4e7f7-121">Эти выпуски отображены на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-121">The releases are pictured in the following figure.</span></span> 
  
![Круги проверки выпуска для Microsoft 365](../../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="4e7f7-123">Для значительных обновлений клиенты изначально уведомлены с помощью [плана развития Microsoft 365.](https://products.office.com/business/office-365-roadmap)</span><span class="sxs-lookup"><span data-stu-id="4e7f7-123">For significant updates, customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="4e7f7-124">По мере того как обновление ближе к развертыванию, оно передается через центр сообщений [Microsoft 365.](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter)</span><span class="sxs-lookup"><span data-stu-id="4e7f7-124">As an update gets closer to rolling out, it is communicated through your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="4e7f7-125">Для доступа к Центру сообщений через Центр администрирования необходима учетная запись Microsoft 365 или Azure [AD.](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center)</span><span class="sxs-lookup"><span data-stu-id="4e7f7-125">You need a Microsoft 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="4e7f7-126">У пользователей домашнего плана Microsoft 365 нет центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-126">Microsoft 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="4e7f7-127">Программа "Стандартный выпуск"</span><span class="sxs-lookup"><span data-stu-id="4e7f7-127">Standard release</span></span>

<span data-ttu-id="4e7f7-128">Это вариант по умолчанию, при котором вы и ваши пользователи будете получать последние обновления, когда они будут выпущены для всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-128">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="4e7f7-129">Для оценки новых функций и подготовки групп для поддержки бизнес-пользователей и руководителей большинство пользователей выпуска **Standard** и ИТ-специалистов и опытных пользователей в выпуске **Targeted** следует оставить для большинства пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-129">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="4e7f7-130">при переходе от стандартного выпуска к выпуску Targeted существует вероятность того, что ваши пользователи не смогут работать с некоторыми функциями, если они еще не представлены в стандартном выпуске.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-130">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="4e7f7-131">Выпуск Targeted</span><span class="sxs-lookup"><span data-stu-id="4e7f7-131">Targeted release</span></span>

<span data-ttu-id="4e7f7-p107">Выбрав этот вариант, вы и ваши пользователи одними из первых увидите последние обновления и сможете помочь улучшить продукт, отправив нам отзывы. Вы можете выбрать, будет ли получать обновления вся организация, или только некоторые люди.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-p107">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e7f7-p108">выпуск масштабных и сложных обновлений занимает больше времени, чем требуется на выпуск более мелких изменений. Это необходимо, чтобы пользователи не столкнулись ни с какими проблемами. Сроки выпусков могут меняться.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-p108">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="4e7f7-136">Выпуск Targeted для всей организации</span><span class="sxs-lookup"><span data-stu-id="4e7f7-136">Targeted release for entire organization</span></span>

<span data-ttu-id="4e7f7-137">Если вы [настроите выпуск](#set-up-the-release-option-in-the-admin-center) в Центре администрирования для этого параметра, все пользователи получат доступ к выпуску Targeted.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-137">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="4e7f7-138">Для организаций, в которых насчитывается больше 300 пользователей, рекомендуем попробовать тестовую подписку на эту программу доступа.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-138">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="4e7f7-139">Чтобы получить сведения о тестовой подписке, обратитесь к представителю Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-139">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="4e7f7-140">Выпуск Targeted для выбранных пользователей</span><span class="sxs-lookup"><span data-stu-id="4e7f7-140">Targeted release for selected users</span></span>

<span data-ttu-id="4e7f7-141">Если вы [настроили](#set-up-the-release-option-in-the-admin-center) выпуск в Центре администрирования для этого параметра, вы можете определить определенных пользователей, как правило, питание пользователей, для получения раннего доступа к функциям и функциям.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-141">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="4e7f7-142">Преимущества выпуска Targeted</span><span class="sxs-lookup"><span data-stu-id="4e7f7-142">Benefits of Targeted release</span></span>

<span data-ttu-id="4e7f7-143">Выпуск Targeted позволяет администраторам, менеджерам изменений или другим пользователям, ответственным за обновления Microsoft 365, подготовиться к предстоящим изменениям, позволяя им:</span><span class="sxs-lookup"><span data-stu-id="4e7f7-143">Targeted release allows admins, change managers, or anyone else responsible for Microsoft 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="4e7f7-144">испытать и проверить новые обновления, прежде чем они станут доступны для всех пользователей в организации;</span><span class="sxs-lookup"><span data-stu-id="4e7f7-144">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="4e7f7-145">подготовить уведомление для пользователей и документацию до всемирного выпуска обновлений;</span><span class="sxs-lookup"><span data-stu-id="4e7f7-145">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="4e7f7-146">подготовить внутреннюю службу технической поддержки к предстоящим изменениям;</span><span class="sxs-lookup"><span data-stu-id="4e7f7-146">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="4e7f7-147">выполнить проверку на предмет соответствия требованиям и безопасности;</span><span class="sxs-lookup"><span data-stu-id="4e7f7-147">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="4e7f7-148">воспользоваться средствами управления функциями, где это применимо, для контроля за выпуском обновлений для пользователей.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-148">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="4e7f7-149">Настройка параметра выпуска в Центре администрирования</span><span class="sxs-lookup"><span data-stu-id="4e7f7-149">Set up the release option in the admin center</span></span>

<span data-ttu-id="4e7f7-150">Чтобы изменить то, как ваша организация получает обновления Microsoft 365, с помощью указанных ниже действий.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-150">You can change how your organization receives Microsoft 365 updates by following these steps.</span></span> <span data-ttu-id="4e7f7-151">Для этого необходимо быть глобальным администратором Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-151">You have to be a global admin in Microsoft 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="4e7f7-152">Чтобы изменения, внесенные ниже, вступили в силу в Microsoft 365, может занять до 24 часов.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-152">It can take up to 24 hours for the below changes to take effect in Microsoft 365.</span></span> <span data-ttu-id="4e7f7-153">Если вы выберете выпуск обновлений на канале Targeted, а затем откажетесь от него, ваши пользователи потеряют доступ к тем возможностям, которые еще не вошли в стандартный выпуск.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-153">If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="4e7f7-154">В Центре администрирования перейдите к параметру "Параметры организации" и на вкладке "Профиль организации" выберите "Параметры  >   **выпуска".** </span><span class="sxs-lookup"><span data-stu-id="4e7f7-154">In the admin center, go to the **Settings** > **Org Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="4e7f7-155">Чтобы отключить выпуск Targeted, выберите **выпуск Standard,** а затем выберите **"Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="4e7f7-155">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="4e7f7-156">Чтобы включить выпуск targeted для всех пользователей в организации, выберите выпуск **Targeted для всех,** а затем выберите "Сохранить **изменения".**</span><span class="sxs-lookup"><span data-stu-id="4e7f7-156">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="4e7f7-157">Чтобы включить выпуск targeted для некоторых пользователей в организации, выберите выпуск **Targeted** для выбранных пользователей, а затем выберите "Сохранить **изменения".**</span><span class="sxs-lookup"><span data-stu-id="4e7f7-157">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="4e7f7-158">Выберите **"Выбор пользователей** для добавления пользователей по одному" или **"Отправить пользователей"** для их массовой отправки.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-158">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="4e7f7-159">После добавления пользователей выберите "Сохранить **изменения".**</span><span class="sxs-lookup"><span data-stu-id="4e7f7-159">When you're done adding users, select **Save changes**.</span></span>


  
## <a name="learn-more"></a><span data-ttu-id="4e7f7-160">Подробнее</span><span class="sxs-lookup"><span data-stu-id="4e7f7-160">Learn more</span></span>

<span data-ttu-id="4e7f7-161">Узнайте, как [управлять](https://docs.microsoft.com/office365/admin/manage/message-center) сообщениями в центре сообщений [Microsoft 365,](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) чтобы получать уведомления о предстоящих обновлениях и выпусках Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="4e7f7-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Microsoft 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Microsoft 365 updates and releases.</span></span>
