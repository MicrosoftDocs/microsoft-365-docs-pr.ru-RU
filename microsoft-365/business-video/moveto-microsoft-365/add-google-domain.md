---
title: Добавление домена Google Workspace
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как переместить домен из Google Workspace в Microsoft 365 для бизнеса.
ms.openlocfilehash: 1abc05867147d2b52e26804918e8247053b5e1d5
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794749"
---
# <a name="add-your-google-workspace-domain-to-microsoft-365"></a><span data-ttu-id="c4b38-103">Добавление домена Google Workspace в Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="c4b38-103">Add your Google Workspace domain to Microsoft 365</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4LWKT?autoplay=false]

<span data-ttu-id="c4b38-104">Добавьте домен Google Workspace в Microsoft 365 для бизнеса, чтобы вы могли продолжать использовать свой адрес электронной почты.</span><span class="sxs-lookup"><span data-stu-id="c4b38-104">Add your Google Workspace domain to Microsoft 365 for business so you can keep using your business email address.</span></span>

## <a name="try-it"></a><span data-ttu-id="c4b38-105">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="c4b38-105">Try it!</span></span>

1. <span data-ttu-id="c4b38-106">Перейдите в [Центр администрирования Microsoft 365.](https://admin.microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="c4b38-106">Go to the [Microsoft 365 admin center](https://admin.microsoft.com).</span></span>
1. <span data-ttu-id="c4b38-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span><span class="sxs-lookup"><span data-stu-id="c4b38-107">In the Microsoft 365 Admin Center, in the left nav, select **Show all**, **Settings** and then **Domains**.</span></span>
1. <span data-ttu-id="c4b38-108">Choose **Add domain**, enter your domain name then select Use this **domain**.</span><span class="sxs-lookup"><span data-stu-id="c4b38-108">Choose **Add domain**, enter your domain name then select **Use this domain**.</span></span> 
1. <span data-ttu-id="c4b38-109">Choose, **Add a TXT record to the domains DNS records,** select **Continue**, and copy the TXT value.</span><span class="sxs-lookup"><span data-stu-id="c4b38-109">Choose, **Add a TXT record to the domains DNS records**, select **Continue**, and copy the TXT value.</span></span> 
1. <span data-ttu-id="c4b38-110">Go back to the [Google Admin Console,](https://admin.google.com)choose **Domains**, Manage **domains**, **View Details**, **Manage domain**, **DNS**, and then scroll down to **Custom resource records**.</span><span class="sxs-lookup"><span data-stu-id="c4b38-110">Go back to the [Google Admin Console](https://admin.google.com), choose **Domains**, **Manage domains**, **View Details**, **Manage domain**, **DNS**, and  then scroll down to **Custom resource records**.</span></span> 
1. <span data-ttu-id="c4b38-111">Откройте в drop-down тип записи, выберите **TXT,** введите значение TXT, скопированные, а затем выберите **"Добавить".**</span><span class="sxs-lookup"><span data-stu-id="c4b38-111">Open the record type drop-down, choose **TXT**, paste the TXT value you copied then select **Add**.</span></span> 

    <span data-ttu-id="c4b38-112">Обновление обычно занимает несколько минут, но может занять до 48 часов.</span><span class="sxs-lookup"><span data-stu-id="c4b38-112">The update usually takes a fact within a few minutes but may take up to 48 hours.</span></span> 
1. <span data-ttu-id="c4b38-113">Вернись в Центр администрирования Microsoft 365, выберите **"Проверить"** и **"Закрыть".**</span><span class="sxs-lookup"><span data-stu-id="c4b38-113">Return to the Microsoft 365 Admin Center, select **Verify**,and then **Close**.</span></span> 
1. <span data-ttu-id="c4b38-114">Чтобы настроить домен в качестве основного сообщения электронной почты для пользователей, в левой области nav выберите **"Активные**  >  **пользователи".**</span><span class="sxs-lookup"><span data-stu-id="c4b38-114">To set your domain as the primary email for your users, in the left nav, select **Users** > **Active users**.</span></span> 
1. <span data-ttu-id="c4b38-115">Выберите пользователя, выберите **"Управление иным** пользователем" и "Электронная почта", "Изменить", "Выберите свой домен" в выпадаемом окте, а затем выберите "Готово" **и** **"Сохранить изменения".**</span><span class="sxs-lookup"><span data-stu-id="c4b38-115">Choose a user, select **Manage username and email**, **Edit**, select your domain from the dropdown, then select **Done** and **Save changes**.</span></span> 
1. <span data-ttu-id="c4b38-116">Повторите этот процесс для каждого пользователя.</span><span class="sxs-lookup"><span data-stu-id="c4b38-116">Repeat this process for each user.</span></span> 

    <span data-ttu-id="c4b38-117">После завершения вы будете готовы установить приложения Office и перенести элементы электронной почты и календаря в Microsoft 365.</span><span class="sxs-lookup"><span data-stu-id="c4b38-117">When you're finished, you'll be ready to install Office apps and migrate your email and calendar items to Microsoft 365.</span></span> 