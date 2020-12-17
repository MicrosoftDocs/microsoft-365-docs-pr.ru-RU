---
title: Остановка автоматической переададки сообщений электронной почты
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
description: Узнайте, как остановить автоматическую переад вперед сообщения электронной почты.
ms.openlocfilehash: 0683e133f6c261dc19cc098b13be298cd8086001
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702593"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="da8e7-103">Остановка автоматической переададки электронной почты</span><span class="sxs-lookup"><span data-stu-id="da8e7-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="da8e7-104">Если злоумышленник получает доступ к почтовому ящику пользователя, он может автоматически пересылать электронную почту пользователя на внешний адрес и украсть проприетарную информацию.</span><span class="sxs-lookup"><span data-stu-id="da8e7-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="da8e7-105">Это можно остановить, создав правило потока почты.</span><span class="sxs-lookup"><span data-stu-id="da8e7-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="da8e7-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="da8e7-106">Try it!</span></span>

1. <span data-ttu-id="da8e7-107">В Центре администрирования Microsoft 365 выберите **Exchange,**  поток обработки почты **и** на вкладке "Правила" выберите знак "плюс" и создайте **новое правило.**</span><span class="sxs-lookup"><span data-stu-id="da8e7-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="da8e7-108">Выберите **дополнительные параметры.**</span><span class="sxs-lookup"><span data-stu-id="da8e7-108">Select **More options**.</span></span> <span data-ttu-id="da8e7-109">Назовите новое правило.</span><span class="sxs-lookup"><span data-stu-id="da8e7-109">Name your new rule.</span></span>
1. <span data-ttu-id="da8e7-110">Затем откройте drop-down для **применения этого правила,** если , выберите **отправитель**, а затем **внешний внутренний**.</span><span class="sxs-lookup"><span data-stu-id="da8e7-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="da8e7-111">Выберите **внутри организации,** а затем **ОК.**</span><span class="sxs-lookup"><span data-stu-id="da8e7-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="da8e7-112">Choose **add condition,** open the drop-down, select **The message properties**, then **include the message type**.</span><span class="sxs-lookup"><span data-stu-id="da8e7-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="da8e7-113">Откройте **выпадающего типа сообщения** выберите автоадран, а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="da8e7-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="da8e7-114">Откройте в **следующем выпадаемом** окнове "Сделать", выберите "Заблокировать сообщение", а затем отклонить сообщение и **включите объяснение.**</span><span class="sxs-lookup"><span data-stu-id="da8e7-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="da8e7-115">Введите текст сообщения для пояснения и выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="da8e7-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="da8e7-116">Прокрутите вниз и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="da8e7-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="da8e7-117">Ваше правило создано, и злоумышленники больше не смогут автоматически перенаправить сообщения.</span><span class="sxs-lookup"><span data-stu-id="da8e7-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>