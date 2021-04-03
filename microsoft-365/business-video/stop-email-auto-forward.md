---
title: Отмена автоматической переадресации электронной почты
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
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: Узнайте, как остановить автопродажа электронных писем.
ms.openlocfilehash: b6715cfdf8622521d977e0746cb9a340a8f70a5c
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578607"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="bfb75-103">Остановка автопродажа электронной почты</span><span class="sxs-lookup"><span data-stu-id="bfb75-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="bfb75-104">Если хакер получает доступ к почтовому ящику пользователя, он может автоматически пересылать электронную почту пользователя на внешний адрес и украсть несвободные сведения.</span><span class="sxs-lookup"><span data-stu-id="bfb75-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="bfb75-105">Это можно остановить, создав правило потока почты.</span><span class="sxs-lookup"><span data-stu-id="bfb75-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="bfb75-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="bfb75-106">Try it!</span></span>

1. <span data-ttu-id="bfb75-107">В центре администрирования Microsoft 365 выберите **Exchange,**  поток почты **и** на вкладке правила выберите знак плюс и создайте **новое правило.**</span><span class="sxs-lookup"><span data-stu-id="bfb75-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="bfb75-108">Выберите **дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="bfb75-108">Select **More options**.</span></span> <span data-ttu-id="bfb75-109">Назови новое правило.</span><span class="sxs-lookup"><span data-stu-id="bfb75-109">Name your new rule.</span></span>
1. <span data-ttu-id="bfb75-110">Затем откройте выпадаю для **применения этого правила,** если , выберите **отправитель**, а затем **внешний внутренний**.</span><span class="sxs-lookup"><span data-stu-id="bfb75-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="bfb75-111">Выберите **Внутри организации,** а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bfb75-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="bfb75-112">Выберите **условие добавить,** откройте выпадаемую, **выберите** свойства сообщения, а затем **включите тип сообщения.**</span><span class="sxs-lookup"><span data-stu-id="bfb75-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="bfb75-113">Откройте **выпадающего** типа сообщения, выберите **Авто-вперед**, а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bfb75-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="bfb75-114">Откройте сообщение **Do the Following** drop-down, выберите **Блок** сообщения, а затем отклонить сообщение и **включить объяснение.**</span><span class="sxs-lookup"><span data-stu-id="bfb75-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="bfb75-115">Введите текст сообщения для объяснения, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bfb75-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="bfb75-116">Прокрутите вниз и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bfb75-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="bfb75-117">Ваше правило создано, и хакеры больше не смогут автоматически отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="bfb75-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>