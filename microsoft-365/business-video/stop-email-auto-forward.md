---
title: Отмена автоматической переадресации электронной почты
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
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как остановить автоматическую переададку сообщений электронной почты.
ms.openlocfilehash: ebbe37ab5c4a60c6ac4b6ebf8877247199460fa1
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925890"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="772ba-103">Остановка автоматической переададки электронной почты</span><span class="sxs-lookup"><span data-stu-id="772ba-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="772ba-104">Если злоумышленник получает доступ к почтовому ящику пользователя, он может автоматически пересылать электронную почту пользователя на внешний адрес и украсть проприетарную информацию.</span><span class="sxs-lookup"><span data-stu-id="772ba-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="772ba-105">Это можно остановить, создав правило потока почты.</span><span class="sxs-lookup"><span data-stu-id="772ba-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="772ba-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="772ba-106">Try it!</span></span>

1. <span data-ttu-id="772ba-107">В Центре администрирования Microsoft 365 выберите **Exchange,**  поток обработки почты **и** на вкладке "Правила" выберите знак "плюс" и создайте **новое правило.**</span><span class="sxs-lookup"><span data-stu-id="772ba-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="772ba-108">Выберите **дополнительные параметры.**</span><span class="sxs-lookup"><span data-stu-id="772ba-108">Select **More options**.</span></span> <span data-ttu-id="772ba-109">Назовите новое правило.</span><span class="sxs-lookup"><span data-stu-id="772ba-109">Name your new rule.</span></span>
1. <span data-ttu-id="772ba-110">Затем откройте drop-down для **применения этого правила,** если , выберите **отправитель**, а затем **внешний внутренний**.</span><span class="sxs-lookup"><span data-stu-id="772ba-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="772ba-111">Выберите **внутри организации,** а затем **ОК.**</span><span class="sxs-lookup"><span data-stu-id="772ba-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="772ba-112">Choose **add condition,** open the drop-down, select **The message properties**, then **include the message type**.</span><span class="sxs-lookup"><span data-stu-id="772ba-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="772ba-113">Откройте **выпадающего типа сообщения** выберите автоадран, а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="772ba-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="772ba-114">Откройте в **следующем выпадаемом** окнове "Сделать", выберите "Заблокировать сообщение", а затем отклонить сообщение и **включите объяснение.**</span><span class="sxs-lookup"><span data-stu-id="772ba-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="772ba-115">Введите текст сообщения для пояснения и выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="772ba-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="772ba-116">Прокрутите вниз и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="772ba-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="772ba-117">Правило создано, и злоумышленники больше не смогут автоматически переададать сообщения.</span><span class="sxs-lookup"><span data-stu-id="772ba-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>