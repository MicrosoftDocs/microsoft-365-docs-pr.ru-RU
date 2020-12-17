---
title: Добавление домена
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как добавить в подписку другой домен.
ms.openlocfilehash: 16f6c4e416ede560d69014e320eb32c4453fd3f5
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702788"
---
# <a name="add-another-domain"></a><span data-ttu-id="3fe51-103">Добавление другого домена</span><span class="sxs-lookup"><span data-stu-id="3fe51-103">Add another domain</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4dN8c?autoplay=false]

<span data-ttu-id="3fe51-104">Вашей компании может потребоваться несколько доменных имен для различных целей.</span><span class="sxs-lookup"><span data-stu-id="3fe51-104">Your company might need multiple domain names for different purposes.</span></span> <span data-ttu-id="3fe51-105">Например, может потребоваться добавить другое написание названия компании, так как клиенты уже используют его, а их сообщения не удалось связаться с вами.</span><span class="sxs-lookup"><span data-stu-id="3fe51-105">For example, you might want to add a different spelling of your company name because customers are already using it and their communications have failed to reach you.</span></span>

## <a name="try-it"></a><span data-ttu-id="3fe51-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="3fe51-106">Try it!</span></span>

1. <span data-ttu-id="3fe51-107">В Центре администрирования Microsoft 365 выберите **"Программа установки".**</span><span class="sxs-lookup"><span data-stu-id="3fe51-107">In the Microsoft 365 admin center, choose **Setup**.</span></span>
1. <span data-ttu-id="3fe51-108">Under **Get your custom domain set up,** select **View**.</span><span class="sxs-lookup"><span data-stu-id="3fe51-108">Under **Get your custom domain set up**, select **View**.</span></span>
1. <span data-ttu-id="3fe51-109">Choose **Manage**, and then **Add domain**.</span><span class="sxs-lookup"><span data-stu-id="3fe51-109">Choose **Manage**, and then **Add domain**.</span></span>
1. <span data-ttu-id="3fe51-110">Введите новое доменное имя, которое нужно добавить, и выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="3fe51-110">Enter the new domain name that you want to add, and then select **Next**.</span></span>
1. <span data-ttu-id="3fe51-111">Войдите в регистратор доменных имен, в данном случае GoDaddy, а затем выберите **"Далее".**</span><span class="sxs-lookup"><span data-stu-id="3fe51-111">Sign in to your domain registrar, in this case GoDaddy, and then select **Next**.</span></span>
1. <span data-ttu-id="3fe51-112">При запросе во sign in to your registrar, and then choose **Authorize**.</span><span class="sxs-lookup"><span data-stu-id="3fe51-112">If prompted, sign in to your registrar, and then choose **Authorize**.</span></span>
1. <span data-ttu-id="3fe51-113">Choose **Add the DNS records for me,** and then select **Next**.</span><span class="sxs-lookup"><span data-stu-id="3fe51-113">Choose **Add the DNS records for me**, and then select **Next**.</span></span>
1. <span data-ttu-id="3fe51-114">Выберите службы для нового домена и сберите флажки для всех служб, которые будут обрабатываться другим доменом.</span><span class="sxs-lookup"><span data-stu-id="3fe51-114">Choose the services for your new domain and clear the check boxes for any services that will be handled by a different domain.</span></span> <span data-ttu-id="3fe51-115">Например, если вы просто хотите использовать новый домен для электронной почты, выберите **Exchange** и спишите флажки для **Skype** для бизнеса и управления мобильными устройствами **для Office 365.**</span><span class="sxs-lookup"><span data-stu-id="3fe51-115">For example, if you just want to use the new domain for email, choose **Exchange**, and clear the check boxes for **Skype for Business** and **Mobile Device Management for Office 365**.</span></span>
1. <span data-ttu-id="3fe51-116">Выберите **"Далее",** **"Авторизировать", "Далее"** и **"Готово".** </span><span class="sxs-lookup"><span data-stu-id="3fe51-116">Select **Next**, **Authorize**, **Next**,and then **Finish**.</span></span> <span data-ttu-id="3fe51-117">Добавлен новый домен.</span><span class="sxs-lookup"><span data-stu-id="3fe51-117">Your new domain has been added.</span></span>

<span data-ttu-id="3fe51-118">Чтобы получать электронную почту на новом домене, необходимо добавить новый псевдоним электронной почты для каждого пользователя:</span><span class="sxs-lookup"><span data-stu-id="3fe51-118">To receive email at your new domain, you'll need to add a new email alias for each user:</span></span>

1. <span data-ttu-id="3fe51-119">Выберите **пользователей,** **активных** пользователей, а затем выберите пользователя, которому будет назначен новый псевдоним.</span><span class="sxs-lookup"><span data-stu-id="3fe51-119">Select **Users**, **Active users**, and then select the user who will be assigned the new alias.</span></span>
1. <span data-ttu-id="3fe51-120">Выберите **"Управление псевдонимами электронной** почты" и **"Добавить псевдоним".**</span><span class="sxs-lookup"><span data-stu-id="3fe51-120">Choose **Manage email aliases**, and then **Add an alias**.</span></span>
1. <span data-ttu-id="3fe51-121">Введите имя пользователя и выберите новый домен в выпадаемом списке.</span><span class="sxs-lookup"><span data-stu-id="3fe51-121">Enter the username, and then choose the new domain from the drop-down list.</span></span>
1. <span data-ttu-id="3fe51-122">Выберите **"Сохранить изменения"** и закрой окно.</span><span class="sxs-lookup"><span data-stu-id="3fe51-122">Select **Save changes**, and then close the window.</span></span>
1. <span data-ttu-id="3fe51-123">Повторите эти действия для каждого пользователя, который должен получать электронную почту в новом домене.</span><span class="sxs-lookup"><span data-stu-id="3fe51-123">Repeat these steps for each user who should receive email at the new domain.</span></span>