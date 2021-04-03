---
title: Добавление домена Google Workspace
f1.keywords:
- NOCSH
ms.author: twerner
author: twernermsft
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
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
description: Узнайте, как переместить домен из Рабочей области Google в Microsoft 365 для бизнеса.
ms.openlocfilehash: 814e714527467bb6e7008ea141989f3117ddcdd8
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578775"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="220f4-103">Добавление домена Google Workspace в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="220f4-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="220f4-104">Добавьте домен Google Workspace в Microsoft 365 для бизнеса, чтобы вы могли использовать бизнес-адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="220f4-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="220f4-105">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="220f4-105">Try it!</span></span>

1. <span data-ttu-id="220f4-106">Перейдите в [центр администрирования Microsoft 365](https://admin.microsoft.com).</span><span class="sxs-lookup"><span data-stu-id="220f4-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="220f4-107">В центре администрирования Microsoft 365 в левом nav выберите **Показать** все **параметры** и **домены.**</span><span class="sxs-lookup"><span data-stu-id="220f4-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="220f4-108">Выберите **Добавить домен,** введите доменное имя, а затем **выберите Используйте этот домен.**</span><span class="sxs-lookup"><span data-stu-id="220f4-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="220f4-109">Выберите, **добавьте запись TXT в** записи DNS доменов, выберите **Продолжить** и скопируйте значение TXT.</span><span class="sxs-lookup"><span data-stu-id="220f4-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="220f4-110">Возвращайся к [консоли администратора Google,](https://admin.google.com)выберите домены, управление доменами, просмотр сведений, управление доменом,  **DNS,** а затем прокрутите до пользовательских **записей ресурсов.** </span><span class="sxs-lookup"><span data-stu-id="220f4-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="220f4-111">Откройте падение типа записи, выберите **TXT,** введите скопированные значения TXT, а затем выберите **Добавить**.</span><span class="sxs-lookup"><span data-stu-id="220f4-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="220f4-112">Обновление обычно принимает факт в течение нескольких минут, но может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="220f4-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="220f4-113">Вернись в Центр администрирования Microsoft 365, выберите **Проверить** и **закрыть**.</span><span class="sxs-lookup"><span data-stu-id="220f4-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="220f4-114">Чтобы настроить домен в качестве основной электронной почты для пользователей, в левом nav выберите **пользователей Users**  >  **Active.**</span><span class="sxs-lookup"><span data-stu-id="220f4-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="220f4-115">Выберите пользователя, выберите **Управление** и имя пользователя и электронную почту, **изменить,** выбрать домен из отсев, а затем выбрать **Сделано** **и сохранить изменения**.</span><span class="sxs-lookup"><span data-stu-id="220f4-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="220f4-116">Повторите этот процесс для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="220f4-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="220f4-117">По завершению вы будете готовы установить приложения Office и перенести элементы электронной почты и календаря в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="220f4-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 