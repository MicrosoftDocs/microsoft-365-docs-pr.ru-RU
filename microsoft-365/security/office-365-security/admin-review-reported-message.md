---
title: Административная проверка сообщений, на которые получены жалобы
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
ms.collection:
- M365-security-compliance
description: Узнайте, как просмотреть сообщения, которые сообщаются, и дать отзывы пользователям.
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 217f5ebb1692d68b5dc70988888bf78d4bd36a0c
ms.sourcegitcommit: d0c160e89e17f451199bc4a85699effd2d935213
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/11/2021
ms.locfileid: "52893732"
---
# <a name="admin-review-for-reported-messages"></a><span data-ttu-id="aa420-103">Административная проверка сообщений, на которые получены жалобы</span><span class="sxs-lookup"><span data-stu-id="aa420-103">Admin review for reported messages</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!NOTE]
> <span data-ttu-id="aa420-104">Сведения в этой статье относятся к продукту предварительного просмотра, который может быть существенно изменен до его коммерческого выпуска.</span><span class="sxs-lookup"><span data-stu-id="aa420-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="aa420-105">Этот документ предоставляется только для целей оценки и разведки.</span><span class="sxs-lookup"><span data-stu-id="aa420-105">This document is provided for evaluation and exploration purposes only.</span></span>

<span data-ttu-id="aa420-106">**Область применения**</span><span class="sxs-lookup"><span data-stu-id="aa420-106">**Applies to**</span></span>
- [<span data-ttu-id="aa420-107">Microsoft Defender для Office 365 (план 1 и план 2)</span><span class="sxs-lookup"><span data-stu-id="aa420-107">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="aa420-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="aa420-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="aa420-109">В Microsoft 365 организациях с Exchange Online почтовыми ящиками и Microsoft Defender для Office 365 администраторы теперь могут отправлять шаблонные сообщения конечным пользователям после проверки сообщений.</span><span class="sxs-lookup"><span data-stu-id="aa420-109">In Microsoft 365 organizations with Exchange Online mailboxes and Microsoft Defender for Office 365, admins can now send templated messages back to end users after they review reported messages.</span></span> <span data-ttu-id="aa420-110">Это может быть настроено для вашей организации и на основе вердикта администратора, а также.</span><span class="sxs-lookup"><span data-stu-id="aa420-110">This can be customized for your organization and based on your admin's verdict as well.</span></span>

<span data-ttu-id="aa420-111">Эта функция предназначена для обратной связи с пользователями, но не меняет вердикты сообщений в системе.</span><span class="sxs-lookup"><span data-stu-id="aa420-111">This feature is designed to give feedback to your users but does not change the verdicts of messages in the system.</span></span> <span data-ttu-id="aa420-112">Чтобы помочь Корпорации Майкрософт обновить и улучшить фильтры, необходимо отправить сообщения для анализа с помощью [отправки администратора.](admin-submission.md)</span><span class="sxs-lookup"><span data-stu-id="aa420-112">To help Microsoft update and improve its filters, you will need to submit messages for analysis using [Admin submission](admin-submission.md).</span></span>

<span data-ttu-id="aa420-113">Вы сможете отмечать и уведомлять пользователей о результатах проверки только в том случае, если сообщение было отчитано как ложное срабатывание или [ложный негатив.](report-false-positives-and-false-negatives.md)</span><span class="sxs-lookup"><span data-stu-id="aa420-113">You will only be able to mark and notify users of review results if the message was reported as a [false positives or false negatives](report-false-positives-and-false-negatives.md).</span></span>

## <a name="what-do-you-need-to-know-before-you-begin"></a><span data-ttu-id="aa420-114">Что нужно знать перед началом работы</span><span class="sxs-lookup"><span data-stu-id="aa420-114">What do you need to know before you begin?</span></span>

- <span data-ttu-id="aa420-115">Вы открываете портал Microsoft 365 Defender по <https://security.microsoft.com/> ссылке .</span><span class="sxs-lookup"><span data-stu-id="aa420-115">You open the Microsoft 365 Defender portal at <https://security.microsoft.com/>.</span></span> <span data-ttu-id="aa420-116">Чтобы перейти непосредственно на **страницу Отправки,** используйте <https://security.microsoft.com/reportsubmission> .</span><span class="sxs-lookup"><span data-stu-id="aa420-116">To go directly to the **Submissions** page, use <https://security.microsoft.com/reportsubmission>.</span></span>

- <span data-ttu-id="aa420-117">Чтобы изменить конфигурацию для пользовательских представлений, необходимо быть членом одной из следующих групп ролей:</span><span class="sxs-lookup"><span data-stu-id="aa420-117">To modify the configuration for User submissions, you need to be a member of one of the following role groups:</span></span>
  - <span data-ttu-id="aa420-118">Управление организацией или администратор безопасности [на портале Microsoft 365 Defender.](permissions-microsoft-365-security-center.md)</span><span class="sxs-lookup"><span data-stu-id="aa420-118">Organization Management or Security Administrator in the [Microsoft 365 Defender portal](permissions-microsoft-365-security-center.md).</span></span>
  - <span data-ttu-id="aa420-119">Управление организацией [в Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span><span class="sxs-lookup"><span data-stu-id="aa420-119">Organization Management in [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups).</span></span>

- <span data-ttu-id="aa420-120">Вам также потребуется доступ к Exchange Online PowerShell.</span><span class="sxs-lookup"><span data-stu-id="aa420-120">You'll also need access to Exchange Online PowerShell.</span></span> <span data-ttu-id="aa420-121">Если учетная запись, которую вы пытаетесь использовать, не имеет доступа к Exchange Online PowerShell, вы получите ошибку с указанием адреса электронной почты в *домене.*</span><span class="sxs-lookup"><span data-stu-id="aa420-121">If the account that you're trying to use doesn't have access to Exchange Online PowerShell, you'll receive an error that says *Specify an email address in your domain*.</span></span> <span data-ttu-id="aa420-122">Дополнительные сведения о включив или отключив доступ к Exchange Online PowerShell, см. в следующих темах:</span><span class="sxs-lookup"><span data-stu-id="aa420-122">For more information about enabling or disabling access to Exchange Online PowerShell, see the following topics:</span></span>
  - [<span data-ttu-id="aa420-123">Включить или отключить доступ к Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="aa420-123">Enable or disable access to Exchange Online PowerShell</span></span>](/powershell/exchange/disable-access-to-exchange-online-powershell)
  - [<span data-ttu-id="aa420-124">Правила клиентского доступа в Exchange Online</span><span class="sxs-lookup"><span data-stu-id="aa420-124">Client Access Rules in Exchange Online</span></span>](/exchange/clients-and-mobile-in-exchange-online/client-access-rules/client-access-rules)

## <a name="configure-the-messages-used-to-notify-users"></a><span data-ttu-id="aa420-125">Настройка сообщений, используемых для уведомления пользователей</span><span class="sxs-lookup"><span data-stu-id="aa420-125">Configure the messages used to notify users</span></span>

1. <span data-ttu-id="aa420-126">На портале Microsoft 365 Defender перейдите  на электронную почту & политики совместной работы & политики угрозы Другие раздел \>  \>  \>  \> **Параметры** сообщений пользователя.</span><span class="sxs-lookup"><span data-stu-id="aa420-126">In the Microsoft 365 Defender portal, go to **Email & collaboration** \> **Policies & rules** \> **Threat policies** \> **Others** section \> **User reported message settings**.</span></span>

2. <span data-ttu-id="aa420-127">На  странице Отправки пользователей, если необходимо указать имя отображения отправитель, проверьте поле Для указания **Office 365**  адрес электронной почты, чтобы использовать в качестве отправщика в разделе Уведомления электронной почты для раздела Результаты проверки администратора, и введите имя, которое вы хотите использовать.</span><span class="sxs-lookup"><span data-stu-id="aa420-127">On the **User submissions** page, if you want to specify the sender display name, check the box for **Specify Office 365 email address to use as sender** under the **Email notifications for admin review results** section, and enter in the name you wish to use.</span></span> <span data-ttu-id="aa420-128">Это адрес электронной почты, который будет виден в Outlook и на который будут отправляться ответы.</span><span class="sxs-lookup"><span data-stu-id="aa420-128">This is the email address that will be visible in Outlook and where replies will go to.</span></span>

3. <span data-ttu-id="aa420-129">Если вы хотите настроить любой из шаблонов, нажмите **кнопку Настройка уведомления электронной почты**.</span><span class="sxs-lookup"><span data-stu-id="aa420-129">If you want to customize any of the templates, click **Customize email notification**.</span></span> <span data-ttu-id="aa420-130">В этом вылете вы сможете настроить только следующее:</span><span class="sxs-lookup"><span data-stu-id="aa420-130">In this flyout, you will be able to customize only the following:</span></span>
    - <span data-ttu-id="aa420-131">Фишинговое</span><span class="sxs-lookup"><span data-stu-id="aa420-131">Phishing</span></span>
    - <span data-ttu-id="aa420-132">Нежелательное</span><span class="sxs-lookup"><span data-stu-id="aa420-132">Junk</span></span>
    - <span data-ttu-id="aa420-133">Угрозы не найдены</span><span class="sxs-lookup"><span data-stu-id="aa420-133">No threats found</span></span>
    - <span data-ttu-id="aa420-134">Обучение осведомленности</span><span class="sxs-lookup"><span data-stu-id="aa420-134">Awareness training</span></span>
    - <span data-ttu-id="aa420-135">Нижний колонтитул</span><span class="sxs-lookup"><span data-stu-id="aa420-135">Footer</span></span>

4. <span data-ttu-id="aa420-136">Выполнив необходимые действия, нажмите кнопку **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="aa420-136">When you're finished, click **Save**.</span></span> <span data-ttu-id="aa420-137">Чтобы очистить эти значения, нажмите **кнопку Отменить** на странице Отправки пользователей.</span><span class="sxs-lookup"><span data-stu-id="aa420-137">To clear these values, click **Discard** on the User submissions page.</span></span>
