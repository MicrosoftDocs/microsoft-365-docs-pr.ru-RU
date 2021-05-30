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
description: Узнайте, как остановить автонападение электронных писем, создав правило потока почты, чтобы избежать кражи несвободных данных.
ms.openlocfilehash: 82e4c80b0edc501889e0fc4dc28f1ec1ad703568
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706478"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="bfbef-103">Остановка автопродажа электронной почты</span><span class="sxs-lookup"><span data-stu-id="bfbef-103">Stop email auto-forward</span></span>

## <a name="watch-stop-auto-forwarding-emails"></a><span data-ttu-id="bfbef-104">Watch: Stop auto-forwarding emails</span><span class="sxs-lookup"><span data-stu-id="bfbef-104">Watch: Stop auto-forwarding emails</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="bfbef-105">Если хакер получает доступ к почтовому ящику пользователя, он может автоматически пересылать электронную почту пользователя на внешний адрес и украсть несвободные сведения.</span><span class="sxs-lookup"><span data-stu-id="bfbef-105">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="bfbef-106">Это можно остановить, создав правило потока почты.</span><span class="sxs-lookup"><span data-stu-id="bfbef-106">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="bfbef-107">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="bfbef-107">Try it!</span></span>

1. <span data-ttu-id="bfbef-108">В центре Microsoft 365 выберите **Exchange,** поток почты **и** на  вкладке правила выберите знак плюс и создайте **новое правило.**</span><span class="sxs-lookup"><span data-stu-id="bfbef-108">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="bfbef-109">Выберите **дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="bfbef-109">Select **More options**.</span></span> <span data-ttu-id="bfbef-110">Назови новое правило.</span><span class="sxs-lookup"><span data-stu-id="bfbef-110">Name your new rule.</span></span>
1. <span data-ttu-id="bfbef-111">Затем откройте выпадаю для **применения этого правила,** если , выберите **отправитель**, а затем **внешний внутренний**.</span><span class="sxs-lookup"><span data-stu-id="bfbef-111">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="bfbef-112">Выберите **Внутри организации,** а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bfbef-112">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="bfbef-113">Выберите **условие добавить,** откройте выпадаемую, **выберите** свойства сообщения, а затем **включите тип сообщения.**</span><span class="sxs-lookup"><span data-stu-id="bfbef-113">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="bfbef-114">Откройте **выпадающего** типа сообщения, выберите **Авто-вперед**, а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bfbef-114">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="bfbef-115">Откройте сообщение **Do the Following** drop-down, выберите **Блок** сообщения, а затем отклонить сообщение и **включить объяснение.**</span><span class="sxs-lookup"><span data-stu-id="bfbef-115">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="bfbef-116">Введите текст сообщения для объяснения, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="bfbef-116">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="bfbef-117">Прокрутите вниз и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="bfbef-117">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="bfbef-118">Ваше правило создано, и хакеры больше не смогут автоматически отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="bfbef-118">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="bfbef-119">См. также:</span><span class="sxs-lookup"><span data-stu-id="bfbef-119">Related content</span></span>

<span data-ttu-id="bfbef-120">[Добавление дополнительных псевдонимов электронной почты для пользователя](../admin/email/add-another-email-alias-for-a-user.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="bfbef-120">[Add another email alias for a user](../admin/email/add-another-email-alias-for-a-user.md) (article)</span></span>\
<span data-ttu-id="bfbef-121">[Настройка переадресации электронной почты в Microsoft 365](../admin/email/configure-email-forwarding.md) (статья)</span><span class="sxs-lookup"><span data-stu-id="bfbef-121">[Configure email forwarding in Microsoft 365](../admin/email/configure-email-forwarding.md) (article)</span></span>\
<span data-ttu-id="bfbef-122">Поиск и устранение проблем с доставкой электронной [почты в качестве Office 365 для бизнес-администратора](/exchange/troubleshoot/email-delivery/email-delivery-issues) (статья)</span><span class="sxs-lookup"><span data-stu-id="bfbef-122">[Find and fix email delivery issues as an Office 365 for business admin](/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>