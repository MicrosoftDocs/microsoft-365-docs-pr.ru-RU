---
title: Удаление бывшего сотрудника — Обзор
f1.keywords:
- NOCSH
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
- SPO_Content
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: Выполните действия в этом решении, чтобы удалить бывшего сотрудника из Microsoft 365 и защитить данные организации.
ms.openlocfilehash: 4b4cf59fdce81b3098ee333095daa8e1af1cd5c5
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/06/2021
ms.locfileid: "52241740"
---
# <a name="overview-remove-a-former-employee-and-secure-data"></a><span data-ttu-id="479bc-103">Обзор. Удаление бывших сотрудников и безопасные данные</span><span class="sxs-lookup"><span data-stu-id="479bc-103">Overview: Remove a former employee and secure data</span></span>

<span data-ttu-id="479bc-104">Часто возникает вопрос: "Что мне делать для защиты данных и защиты доступа, когда сотрудник покидает мою организацию?"</span><span class="sxs-lookup"><span data-stu-id="479bc-104">A question we often get is, "What should I do to secure data and protect access when an employee leaves my organization?"</span></span> <span data-ttu-id="479bc-105">В этой серии статей рассказывается о том, как блокировать доступ к Microsoft 365, какие действия следует предпринять для обеспечения безопасности данных, а также как разрешить другим сотрудникам доступ к данным.</span><span class="sxs-lookup"><span data-stu-id="479bc-105">This article series explains how to block access to Microsoft 365, the steps you should take to secure your data, and how to allow other employees to access the data.</span></span>

<span data-ttu-id="479bc-106">Просмотрите короткое видео об удалении сотрудника.</span><span class="sxs-lookup"><span data-stu-id="479bc-106">Watch a short video about removing an employee.</span></span> <br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FOfR] 

<span data-ttu-id="479bc-107">Если это видео помогло вам, ознакомьтесь с [полным учебным курсом для малых предприятий и новых пользователей Microsoft 365](../../business-video/index.yml).</span><span class="sxs-lookup"><span data-stu-id="479bc-107">If you found this video helpful, check out the [complete training series for small businesses and those new to Microsoft 365](../../business-video/index.yml).</span></span>

<span data-ttu-id="479bc-108">Чтобы предотвратить вход сотрудника в систему:</span><span class="sxs-lookup"><span data-stu-id="479bc-108">To prevent an employee from logging in:</span></span>

1. <span data-ttu-id="479bc-109">В Центре администрирования откройте страницу **Пользователи** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Активные пользователи</a>.</span><span class="sxs-lookup"><span data-stu-id="479bc-109">In the admin center, go to the **Users** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=834822" target="_blank">Active users</a> page.</span></span>
2. <span data-ttu-id="479bc-110">Выберите поле рядом с именем пользователя, а затем выберите **пароль Reset**.</span><span class="sxs-lookup"><span data-stu-id="479bc-110">Select the box next to the user's name, and then select **Reset password**.</span></span>
3. <span data-ttu-id="479bc-111">Введите новый пароль и выберите **Сброс**.</span><span class="sxs-lookup"><span data-stu-id="479bc-111">Enter a new password, and then select **Reset**.</span></span> <span data-ttu-id="479bc-112">(Не отправляйте его им.)</span><span class="sxs-lookup"><span data-stu-id="479bc-112">(Don't send it to them.)</span></span>
4. <span data-ttu-id="479bc-113">Выберите имя пользователя, чтобы перейти к области свойств, а на вкладке **Учетная** запись выберите **инициировать вход.**</span><span class="sxs-lookup"><span data-stu-id="479bc-113">Select the user's name to go to their properties pane, and on the **Account** tab, select **Initiate sign-out**.</span></span>

> [!NOTE]
> <span data-ttu-id="479bc-114">Чтобы инициировать регистрацию, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="479bc-114">You need to be a global administrator to initiate sign-out.</span></span>

<span data-ttu-id="479bc-115">В течение часа или после того, как они покидают текущую страницу Microsoft 365 они находятся на - им предложено войти снова.</span><span class="sxs-lookup"><span data-stu-id="479bc-115">Within an hour - or after they leave the current Microsoft 365 page they are on - they're prompted to sign in again.</span></span> <span data-ttu-id="479bc-116">Маркер доступа хорош в течение часа, поэтому сроки зависят от того, сколько времени осталось на этом маркере, и от того, будут ли они переходить из текущей веб-страницы.</span><span class="sxs-lookup"><span data-stu-id="479bc-116">An access token is good for an hour, so the timeline depends on how much time is left on that token, and whether they navigate out of their current webpage.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="479bc-117">Хотя мы пронумировали действия в этом решении, и вам не нужно завершать решение с помощью точного порядка, мы рекомендуем выполнить действия таким образом.</span><span class="sxs-lookup"><span data-stu-id="479bc-117">Although we've numbered the steps in this solution and you don't have to complete the solution using the exact order, we do recommend doing the steps this way.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="479bc-118">Подготовка к работе</span><span class="sxs-lookup"><span data-stu-id="479bc-118">Before you begin</span></span>

<span data-ttu-id="479bc-119">Чтобы выполнить действия в этом решении, необходимо быть глобальным администратором.</span><span class="sxs-lookup"><span data-stu-id="479bc-119">You need to be a global administrator to complete the steps in this solution.</span></span>

|||
|:-----|:-----|
|<span data-ttu-id="479bc-120">**Шаг**</span><span class="sxs-lookup"><span data-stu-id="479bc-120">**Step**</span></span> <br/> |<span data-ttu-id="479bc-121">**Причина**</span><span class="sxs-lookup"><span data-stu-id="479bc-121">**Why do this**</span></span> <br/> |
|[<span data-ttu-id="479bc-122">Шаг 1 — запретить бывшему сотруднику войти в систему и заблокировать доступ к Microsoft 365 службам</span><span class="sxs-lookup"><span data-stu-id="479bc-122">Step 1 - Prevent a former employee from logging in and block access to Microsoft 365 services</span></span>](remove-former-employee-step-1.md) <br/> |<span data-ttu-id="479bc-123">Это блокирует вход вашего бывшего сотрудника в Microsoft 365 и не позволяет ему получить доступ к Microsoft 365 службам.</span><span class="sxs-lookup"><span data-stu-id="479bc-123">This blocks your former employee from logging in to Microsoft 365 and prevents the person from accessing Microsoft 365 services.</span></span> <br/> |
|[<span data-ttu-id="479bc-124">Шаг 2 . Сохранение содержимого почтового ящика бывшего сотрудника</span><span class="sxs-lookup"><span data-stu-id="479bc-124">Step 2 - Save the contents of a former employee's mailbox</span></span>](remove-former-employee-step-2.md) <br/> |<span data-ttu-id="479bc-125">Это полезно для человека, который собирается взять на себя работу сотрудника, или если есть судебное разбирательство.</span><span class="sxs-lookup"><span data-stu-id="479bc-125">This is useful for the person who is going to take over the employee's work, or if there is litigation.</span></span> <br/> |
|[<span data-ttu-id="479bc-126">Шаг 3 . Переадрентие электронной почты бывшего сотрудника другому сотруднику или преобразование в общий почтовый ящик</span><span class="sxs-lookup"><span data-stu-id="479bc-126">Step 3 - Forward a former employee's email to another employee or convert to a shared mailbox</span></span>](remove-former-employee-step-3.md) <br/> |<span data-ttu-id="479bc-p104">Таким образом вы оставите адрес электронной почты бывшего сотрудника активным. Если клиенты или партнеры будут продолжать отправлять письма на адрес электронной почты бывшего сотрудника, они будут пересылаться новому сотруднику, принимающему должность.</span><span class="sxs-lookup"><span data-stu-id="479bc-p104">This lets you keep the former employee's email address active. If you have customers or partners still sending email to the former employee's address, this gets them to the person taking over the work.</span></span> <br/> |
|[<span data-ttu-id="479bc-129">Шаг 4 . Предоставить другому сотруднику доступ к OneDrive и Outlook данным</span><span class="sxs-lookup"><span data-stu-id="479bc-129">Step 4 - Give another employee access to OneDrive and Outlook data</span></span>](remove-former-employee-step-6.md) <br/> |<span data-ttu-id="479bc-130">Если удалить лицензию пользователя, но не удалять его учетную запись, его содержимое в OneDrive останется доступным для вас даже по истечении 30-дневного периода.</span><span class="sxs-lookup"><span data-stu-id="479bc-130">If you only remove a user's license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.</span></span> <br/><br/> <span data-ttu-id="479bc-131">Перед удалением учетной записи необходимо предоставить доступ к OneDrive и Outlook другому пользователю.</span><span class="sxs-lookup"><span data-stu-id="479bc-131">Before you delete the account, you should give access of their OneDrive and Outlook to another user.</span></span> <span data-ttu-id="479bc-132">После удаления учетной записи сотрудника содержимое в OneDrive и Outlook сохраняется в течение **30** дней.</span><span class="sxs-lookup"><span data-stu-id="479bc-132">After you delete an employee's account, the content in their OneDrive and Outlook is retained for **30** days.</span></span> <span data-ttu-id="479bc-133">Однако в течение этого 30 дней можно восстановить учетную запись пользователя и получить доступ к его содержимому.</span><span class="sxs-lookup"><span data-stu-id="479bc-133">During that 30 days, however, you can restore the user's account, and gain access to their content.</span></span> <span data-ttu-id="479bc-134">При восстановлении учетной записи пользователя содержимое OneDrive и Outlook останется доступным для вас даже через 30 дней.</span><span class="sxs-lookup"><span data-stu-id="479bc-134">If you restore the user's account, the OneDrive and Outlook content will remain accessible to you even after 30 days.</span></span> <br/> |
|[<span data-ttu-id="479bc-135">Шаг 5 — стереть и заблокировать мобильное устройство бывшего сотрудника</span><span class="sxs-lookup"><span data-stu-id="479bc-135">Step 5 - Wipe and block a former employee's mobile device</span></span>](remove-former-employee-step-4.md) <br/> |<span data-ttu-id="479bc-136">Бизнес-данные будут удалены с телефона или планшета.</span><span class="sxs-lookup"><span data-stu-id="479bc-136">Removes your business data from the phone or tablet.</span></span>  <br/> |
|[<span data-ttu-id="479bc-137">Шаг 6 . Удаление и удаление Microsoft 365 лицензии у бывшего сотрудника</span><span class="sxs-lookup"><span data-stu-id="479bc-137">Step 6 - Remove and delete the Microsoft 365 license from a former employee</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="479bc-p106">После освобождения лицензии ее можно назначить другому пользователю. При удалении лицензии плата за нее не начисляется, пока не будет нанят другой сотрудник.  </span><span class="sxs-lookup"><span data-stu-id="479bc-p106">When you remove a license, you can assign it to someone else. Or, you can delete the license so you don't pay for it until you hire another person. </span></span><br/><br/> <span data-ttu-id="479bc-p107">После освобождения или удаления лицензии электронная почта, контакты и календарь бывшего пользователя сохраняются в течение **30 дней**, а затем удаляются без возможности восстановления. Если освободить или удалить лицензию, но не удалять учетную запись, содержимое пользователя в OneDrive останется доступным для вас даже по истечении 30-дневного периода.  </span><span class="sxs-lookup"><span data-stu-id="479bc-p107">When you remove or delete a license, the user's old email, contacts, and calendar are retained for **30 days**, then permanently deleted. If you remove or delete a license but don't delete the account, the content in the user's OneDrive will remain accessible to you even after 30 days.  </span></span><br/> |
|[<span data-ttu-id="479bc-142">Шаг 7 . Удаление учетной записи пользователя бывшего сотрудника</span><span class="sxs-lookup"><span data-stu-id="479bc-142">Step 7 - Delete a former employee's user account</span></span>](remove-former-employee-step-7.md) <br/> |<span data-ttu-id="479bc-143">Это удаляет учетную запись из центра администрирования.</span><span class="sxs-lookup"><span data-stu-id="479bc-143">This removes the account from your admin center.</span></span> <span data-ttu-id="479bc-144">Это помогает поддерживать порядок.</span><span class="sxs-lookup"><span data-stu-id="479bc-144">Keeps things clean.</span></span> <br/> |

## <a name="related-articles"></a><span data-ttu-id="479bc-145">Статьи по теме</span><span class="sxs-lookup"><span data-stu-id="479bc-145">Related articles</span></span>

[<span data-ttu-id="479bc-146">Восстановление пользователя</span><span class="sxs-lookup"><span data-stu-id="479bc-146">Restore a user</span></span>](restore-user.md)
