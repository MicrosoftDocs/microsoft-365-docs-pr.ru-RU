---
title: Настройка стандартного доступа или выпуска Targeted в Office 365
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
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
- GEA150
ms.assetid: 3b3adfa4-1777-4ff0-b606-fb8732101f47
description: Узнайте, как настроить выпуск для новых обновлений продуктов и компонентов в центре администрирования Microsoft 365.
ms.openlocfilehash: 2d4940003c791e50926eff46aaf6a299e60fb9aa
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/24/2020
ms.locfileid: "42254927"
---
# <a name="set-up-the-standard-or-targeted-release-options-in-office-365"></a><span data-ttu-id="c5e63-103">Настройка стандартного доступа или выпуска Targeted в Office 365</span><span class="sxs-lookup"><span data-stu-id="c5e63-103">Set up the Standard or Targeted release options in Office 365</span></span>

<span data-ttu-id="c5e63-p101">С Office 365 вы получаете регулярные обновления продуктов и функций сразу же после их появления. Таким образом, вам не нужно проводить дорогостоящие обновления каждые несколько лет. Вы можете выбрать, как ваша организация будет их получать. Например, вы можете подписаться на программу раннего доступа, чтобы ваша организация получала обновления одной из первых, а также сделать так, чтобы они были доступны только определенным людям. Вы также можете оставить расписание выпусков по умолчанию и получать обновления позже. В этой статье описываются различные программы доступа и их использование в организации.</span><span class="sxs-lookup"><span data-stu-id="c5e63-p101">With Office 365, you receive new product updates and features as they become available instead of doing costly updates every few years. You can manage how your organization receives these updates. For example, you can sign up for an early release so that your organization receives updates first. You can designate that only certain individuals receive the updates. Or, you can remain on the default release schedule and receive the updates later. This article explain the different release options and how you can use them for your organization.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c5e63-p102">обновления Office 365, описанные в этой статье, относятся к Office 365, SharePoint Online и Exchange Online. Они не затрагивают Skype для бизнеса и связанные с ним службы. Описанные программы доступа являются целевыми и наилучшим образом подходят для выпуска изменений Office 365, но могут использоваться не всегда и не для всех обновлений.</span><span class="sxs-lookup"><span data-stu-id="c5e63-p102">The Office 365 updates described in this article apply to Office 365, SharePoint Online, and Exchange Online. They do not apply to Skype for Business and related services. These release options are targeted, best effort ways to release changes to Office 365 but cannot be guaranteed at all times or for all updates.</span></span> 
  
## <a name="how-it-works---release-validation"></a><span data-ttu-id="c5e63-113">Принцип действия проверки выпуска</span><span class="sxs-lookup"><span data-stu-id="c5e63-113">How it works - release validation</span></span>

<span data-ttu-id="c5e63-114">Любой новый выпуск сначала тестируется и проверяется группой компонентов, а затем группой компонентов Office 365 целиком, а затем всеми Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c5e63-114">Any new release is first tested and validated by the feature team, then by the entire Office 365 feature team, followed by all of Microsoft.</span></span> <span data-ttu-id="c5e63-115">Следующий этап после внутреннего испытания и проверки  **выпуск Targeted** (прежнее название  "Первый выпуск" или "Программа раннего доступа") для пользователей с такой программой доступа.</span><span class="sxs-lookup"><span data-stu-id="c5e63-115">After internal testing and validation, the next step is a **Targeted release** (formerly known as First release) to customers who opt in.</span></span> <span data-ttu-id="c5e63-116">На каждом круге выпуска Майкрософт собирает отзывы и проверяет качество на основании главных показателей использования.</span><span class="sxs-lookup"><span data-stu-id="c5e63-116">At each release ring, Microsoft collects feedback and further validates quality by monitoring key usage metrics.</span></span> <span data-ttu-id="c5e63-117">Такая прогрессивная проверка используется для обеспечения надежности всемирного выпуска.</span><span class="sxs-lookup"><span data-stu-id="c5e63-117">This series of progressive validation is in place to make sure the worldwide-release is as robust as possible.</span></span> <span data-ttu-id="c5e63-118">Эти выпуски отображены на приведенном ниже рисунке.</span><span class="sxs-lookup"><span data-stu-id="c5e63-118">The releases are pictured in the following figure.</span></span> 
  
![Освобождение звонков проверки для Office 365](../media/73611ed3-2d8c-4e7b-8074-9f03b239f9ed.png)
  
<span data-ttu-id="c5e63-120">Для получения значительных обновлений клиенты Office изначально уведомляются о [планах Microsoft 365](https://products.office.com/business/office-365-roadmap).</span><span class="sxs-lookup"><span data-stu-id="c5e63-120">For significant updates, Office customers are initially notified by the [Microsoft 365 Roadmap](https://products.office.com/business/office-365-roadmap).</span></span> <span data-ttu-id="c5e63-121">Поскольку обновление ближе к развертыванию, оно передается через [Центр сообщений Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span><span class="sxs-lookup"><span data-stu-id="c5e63-121">As an update gets closer to rolling out, it is communicated through your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter).</span></span>

> [!NOTE]
> <span data-ttu-id="c5e63-122">Чтобы получить доступ к центру сообщений через [центр администрирования](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center), вам нужна учетная запись Office 365 или Azure AD.</span><span class="sxs-lookup"><span data-stu-id="c5e63-122">You need an Office 365 or Azure AD account to access your Message center through the [admin center](https://docs.microsoft.com/office365/admin/admin-overview/about-the-admin-center).</span></span> <span data-ttu-id="c5e63-123">Пользователи Office 365 Home Plan не имеют центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="c5e63-123">Office 365 home plan users do not have an admin center.</span></span>


## <a name="standard-release"></a><span data-ttu-id="c5e63-124">Программа "Стандартный выпуск"</span><span class="sxs-lookup"><span data-stu-id="c5e63-124">Standard release</span></span>

<span data-ttu-id="c5e63-125">Это параметр по умолчанию, в котором пользователи и пользователи получают последние обновления при широком выпуске всех клиентов.</span><span class="sxs-lookup"><span data-stu-id="c5e63-125">This is the default option where you and your users receive the latest updates when they're released broadly to all customers.</span></span>
  
<span data-ttu-id="c5e63-126">Рекомендуется не допустить большинства пользователей в **стандартном выпуске** , ИТ-специалистах и опытных пользователей в **целевом выпуске** для оценки новых функций и подготовки Teams к поддержке бизнес-пользователей и руководителей.</span><span class="sxs-lookup"><span data-stu-id="c5e63-126">A good practice is to leave the majority of users in **Standard release** and IT Pros and power users in **Targeted release** to evaluate new features and prepare teams to support business users and executives.</span></span> 
  
> [!NOTE]
> <span data-ttu-id="c5e63-127">при переходе от стандартного выпуска к выпуску Targeted существует вероятность того, что ваши пользователи не смогут работать с некоторыми функциями, если они еще не представлены в стандартном выпуске.</span><span class="sxs-lookup"><span data-stu-id="c5e63-127">If you switch from targeted release back to standard release track, your users may lose access to features that haven't reached standard release yet.</span></span> 
  
## <a name="targeted-release"></a><span data-ttu-id="c5e63-128">Выпуск Targeted</span><span class="sxs-lookup"><span data-stu-id="c5e63-128">Targeted release</span></span>

<span data-ttu-id="c5e63-p106">Выбрав этот вариант, вы и ваши пользователи одними из первых увидите последние обновления и сможете помочь улучшить продукт, отправив нам отзывы. Вы можете выбрать, будет ли получать обновления вся организация, или только некоторые люди.</span><span class="sxs-lookup"><span data-stu-id="c5e63-p106">With this option, you and your users can be the first to see the latest updates and help shape the product by providing early feedback. You can choose to have individuals or the entire organization receive updates early.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c5e63-p107">выпуск масштабных и сложных обновлений занимает больше времени, чем требуется на выпуск более мелких изменений. Это необходимо, чтобы пользователи не столкнулись ни с какими проблемами. Сроки выпусков могут меняться.</span><span class="sxs-lookup"><span data-stu-id="c5e63-p107">Large or complex updates may take longer than others so that no users are adversely affected. There is no guarantee on the exact timeline of a release.</span></span> 
  
### <a name="targeted-release-for-entire-organization"></a><span data-ttu-id="c5e63-133">Выпуск Targeted для всей организации</span><span class="sxs-lookup"><span data-stu-id="c5e63-133">Targeted release for entire organization</span></span>

<span data-ttu-id="c5e63-134">Если вы [настроили параметр Release в центре администрирования](#set-up-the-release-option-in-the-admin-center) для этого параметра, все ваши пользователи будут получать доступ к целевому выпуску.</span><span class="sxs-lookup"><span data-stu-id="c5e63-134">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, all your users will get the Targeted release experience.</span></span> <span data-ttu-id="c5e63-135">Для организаций, в которых насчитывается больше 300 пользователей, рекомендуем попробовать тестовую подписку на эту программу доступа.</span><span class="sxs-lookup"><span data-stu-id="c5e63-135">For organizations with more than 300 users, we recommend using a test subscription for this option.</span></span> <span data-ttu-id="c5e63-136">Чтобы получить сведения о тестовой подписке, обратитесь к представителю Майкрософт.</span><span class="sxs-lookup"><span data-stu-id="c5e63-136">For test subscription information, please reach out to your Microsoft contact.</span></span> 
  
### <a name="targeted-release-for-selected-users"></a><span data-ttu-id="c5e63-137">Выпуск Targeted для выбранных пользователей</span><span class="sxs-lookup"><span data-stu-id="c5e63-137">Targeted release for selected users</span></span>

<span data-ttu-id="c5e63-138">Если вы [настроили параметр Release в центре администрирования](#set-up-the-release-option-in-the-admin-center) для этого параметра, вы можете определить определенных пользователей, обычно опытных пользователей, получать ранний доступ к функциям и функциям.</span><span class="sxs-lookup"><span data-stu-id="c5e63-138">If you [Set up the release option in the admin center](#set-up-the-release-option-in-the-admin-center) for this option, you can define specific users, usually power users, to receive early access to features and functionality.</span></span> 
  
## <a name="benefits-of-targeted-release"></a><span data-ttu-id="c5e63-139">Преимущества выпуска Targeted</span><span class="sxs-lookup"><span data-stu-id="c5e63-139">Benefits of Targeted release</span></span>

<span data-ttu-id="c5e63-140">Выпуск Targeted позволяет администраторам, менеджерам изменений или всем лицам, ответственным за обновления Office 365, подготовиться к предстоящим изменениям, предоставляя им возможность:</span><span class="sxs-lookup"><span data-stu-id="c5e63-140">Targeted release allows admins, change managers, or anyone else responsible for Office 365 updates to prepare for the upcoming changes by letting them:</span></span>
  
- <span data-ttu-id="c5e63-141">испытать и проверить новые обновления, прежде чем они станут доступны для всех пользователей в организации;</span><span class="sxs-lookup"><span data-stu-id="c5e63-141">Test and validate new updates before they are released to all the users in the organization.</span></span>
    
- <span data-ttu-id="c5e63-142">подготовить уведомление для пользователей и документацию до всемирного выпуска обновлений;</span><span class="sxs-lookup"><span data-stu-id="c5e63-142">Prepare user notification and documentation before updates are released worldwide.</span></span>
    
- <span data-ttu-id="c5e63-143">подготовить внутреннюю службу технической поддержки к предстоящим изменениям;</span><span class="sxs-lookup"><span data-stu-id="c5e63-143">Prepare internal help-desk for upcoming changes.</span></span>
    
- <span data-ttu-id="c5e63-144">выполнить проверку на предмет соответствия требованиям и безопасности;</span><span class="sxs-lookup"><span data-stu-id="c5e63-144">Go through compliance and security reviews.</span></span>
    
- <span data-ttu-id="c5e63-145">воспользоваться средствами управления функциями, где это применимо, для контроля за выпуском обновлений для пользователей.</span><span class="sxs-lookup"><span data-stu-id="c5e63-145">Use feature controls, where applicable, to control the release of updates to end users.</span></span>
    
## <a name="set-up-the-release-option-in-the-admin-center"></a><span data-ttu-id="c5e63-146">Настройка функции выпуска в центре администрирования</span><span class="sxs-lookup"><span data-stu-id="c5e63-146">Set up the release option in the admin center</span></span>

<span data-ttu-id="c5e63-p109">Чтобы указать, как ваша организация будет получать обновления Office 365, следуйте инструкциям ниже. Подписаться на программу доступа может только глобальный администратор Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5e63-p109">You can change how your organization receives Office 365 updates by following these steps. You have to be a global admin in Office 365 to opt in.</span></span>
  
> [!IMPORTANT]
> <span data-ttu-id="c5e63-p110">для вступления в силу изменений в Office 365 может потребоваться до 24 часов. Если вы выберете выпуск обновлений на канале Targeted, а затем откажетесь от него, ваши пользователи потеряют доступ к тем возможностям, которые еще не вошли в стандартный выпуск.</span><span class="sxs-lookup"><span data-stu-id="c5e63-p110">It can take up to 24 hours for the below changes to take effect in Office 365. If you opt out of targeted release after enabling it, your users may lose access to features that haven't reached the scheduled release yet.</span></span> 
  
1. <span data-ttu-id="c5e63-151">В центре администрирования перейдите к**параметру** **Параметры** > и на вкладке **профиль организации** выберите **параметры выпуска**.</span><span class="sxs-lookup"><span data-stu-id="c5e63-151">In the admin center, go to the **Settings** > **Setting**, and under the **Organization profile** tab, choose **Release preferences**.</span></span>

5. <span data-ttu-id="c5e63-152">Чтобы отключить целевой выпуск, выберите **стандартный выпуск**, а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="c5e63-152">To disable targeted release, select **Standard release**, then select **Save changes**.</span></span> 
    
6. <span data-ttu-id="c5e63-153">Чтобы включить целевой выпуск для всех пользователей в Организации, выберите вариант **выпуск Targeted для**всех пользователей, а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="c5e63-153">To enable targeted release for all users in your organization, select **Targeted release for everyone**, then select **Save changes**.</span></span> 
    
7. <span data-ttu-id="c5e63-154">Чтобы включить целевой выпуск для некоторых пользователей в Организации, установите флажок **нацеленный выпуск для выбранных пользователей**, а затем нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="c5e63-154">To enable targeted release for some people in your organization, select **Targeted release for selected users**, then select **Save changes**.</span></span> 
    
8. <span data-ttu-id="c5e63-155">Нажмите кнопку **выбрать пользователей** , чтобы добавлять пользователей по одному, или **отправьте пользователей** , чтобы добавить их в пакетном режиме.</span><span class="sxs-lookup"><span data-stu-id="c5e63-155">Choose **Select users** to add users one at a time, or **Upload users** to add them in bulk.</span></span>
    
9. <span data-ttu-id="c5e63-156">Завершив добавление пользователей, нажмите кнопку **сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="c5e63-156">When you're done adding users, select **Save changes**.</span></span>



## <a name="get-the-targeted-release-version-of-office"></a><span data-ttu-id="c5e63-157">Получение целевой версии выпуска Office</span><span class="sxs-lookup"><span data-stu-id="c5e63-157">Get the Targeted release version of Office</span></span>

<span data-ttu-id="c5e63-p111">Чтобы установить сборку Office, предоставляемую в рамках выпуска Targeted, следуйте [этим инструкциям](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). Вы получите ранний доступ к новым возможностям классической версии Office 2016 для Windows.</span><span class="sxs-lookup"><span data-stu-id="c5e63-p111">To install a targeted release build of Office, [follow these steps](https://support.office.com/article/4dd8ba40-73c0-4468-b778-c7b744d03ead). This gives you early access to the new features of Office 2016 for Windows desktops.</span></span>
  
## <a name="learn-more"></a><span data-ttu-id="c5e63-160">Подробнее</span><span class="sxs-lookup"><span data-stu-id="c5e63-160">Learn more</span></span>

<span data-ttu-id="c5e63-161">Узнайте, как [управлять сообщениями](https://docs.microsoft.com/office365/admin/manage/message-center) в [центре сообщений Office 365](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) , чтобы получать уведомления о предстоящих обновлениях и выпусках Office 365.</span><span class="sxs-lookup"><span data-stu-id="c5e63-161">Discover how to [manage messages](https://docs.microsoft.com/office365/admin/manage/message-center) in your [Office 365 Message center](https://admin.microsoft.com/Adminportal/Home?source=applauncher#/MessageCenter) to get notifications about upcoming Office 365 updates and releases.</span></span>
