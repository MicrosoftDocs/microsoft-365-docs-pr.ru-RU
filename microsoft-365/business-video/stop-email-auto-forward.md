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
ms.openlocfilehash: f8bd599c7c8bca8d4789188acbcd3574b7473dcb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/20/2021
ms.locfileid: "51903686"
---
# <a name="stop-email-auto-forward"></a><span data-ttu-id="3b6d0-103">Остановка автопродажа электронной почты</span><span class="sxs-lookup"><span data-stu-id="3b6d0-103">Stop email auto-forward</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2W6kS?autoplay=false]

<span data-ttu-id="3b6d0-104">Если хакер получает доступ к почтовому ящику пользователя, он может автоматически пересылать электронную почту пользователя на внешний адрес и украсть несвободные сведения.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-104">If a hacker gains access to a user's mailbox, they can auto-forward the user's email to an outside address and steal proprietary information.</span></span> <span data-ttu-id="3b6d0-105">Это можно остановить, создав правило потока почты.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-105">You can stop this by creating a mail flow rule.</span></span>

## <a name="try-it"></a><span data-ttu-id="3b6d0-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="3b6d0-106">Try it!</span></span>

1. <span data-ttu-id="3b6d0-107">В центре администрирования Microsoft 365 выберите **Exchange,**  поток почты **и** на вкладке правила выберите знак плюс и создайте **новое правило.**</span><span class="sxs-lookup"><span data-stu-id="3b6d0-107">From the Microsoft 365 admin center, select **Exchange**, **mail flow**, and on the **rules** tab, select the plus sign and choose **create a new rule**.</span></span>
1. <span data-ttu-id="3b6d0-108">Выберите **дополнительные параметры**.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-108">Select **More options**.</span></span> <span data-ttu-id="3b6d0-109">Назови новое правило.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-109">Name your new rule.</span></span>
1. <span data-ttu-id="3b6d0-110">Затем откройте выпадаю для **применения этого правила,** если , выберите **отправитель**, а затем **внешний внутренний**.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-110">Then open the drop-down for **apply this rule if**, select **the sender**, and then **is external internal**.</span></span>
1. <span data-ttu-id="3b6d0-111">Выберите **Внутри организации,** а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-111">Select **Inside the organization**, and then **OK**.</span></span>
1. <span data-ttu-id="3b6d0-112">Выберите **условие добавить,** откройте выпадаемую, **выберите** свойства сообщения, а затем **включите тип сообщения.**</span><span class="sxs-lookup"><span data-stu-id="3b6d0-112">Choose **add condition**, open the drop-down, select **The message properties**, then **include the message type**.</span></span>
1. <span data-ttu-id="3b6d0-113">Откройте **выпадающего** типа сообщения, выберите **Авто-вперед**, а затем **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-113">Open the **select message type** drop-down, choose **Auto-forward**, then **OK**.</span></span>
1. <span data-ttu-id="3b6d0-114">Откройте сообщение **Do the Following** drop-down, выберите **Блок** сообщения, а затем отклонить сообщение и **включить объяснение.**</span><span class="sxs-lookup"><span data-stu-id="3b6d0-114">Open the **Do the following** drop-down, select **Block the message**, then **reject the message and include an explanation**.</span></span>
1. <span data-ttu-id="3b6d0-115">Введите текст сообщения для объяснения, а затем выберите **ОК**.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-115">Enter the message text for your explanation, then select **OK**.</span></span>
1. <span data-ttu-id="3b6d0-116">Прокрутите вниз и выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-116">Scroll to the bottom and select **Save**.</span></span>

    <span data-ttu-id="3b6d0-117">Ваше правило создано, и хакеры больше не смогут автоматически отправлять сообщения.</span><span class="sxs-lookup"><span data-stu-id="3b6d0-117">Your rule has been created, and hackers will no longer be able to auto-forward messages.</span></span>

## <a name="related-content"></a><span data-ttu-id="3b6d0-118">См. также:</span><span class="sxs-lookup"><span data-stu-id="3b6d0-118">Related content</span></span>

<span data-ttu-id="3b6d0-119">[Добавьте еще один](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) псевдоним электронной почты для пользователя (статья) Настройка переададки электронной почты в [Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (статья) Поиск и устранение проблем с доставкой электронной почты в [качестве Office 365](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) для администратора бизнеса (статья)</span><span class="sxs-lookup"><span data-stu-id="3b6d0-119">[Add another email alias for a user](https://docs.microsoft.com/microsoft-365/admin/email/add-another-email-alias-for-a-user) (article) [Configure email forwarding in Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding) (article) [Find and fix email delivery issues as an Office 365 for business admin](https://docs.microsoft.com/exchange/troubleshoot/email-delivery/email-delivery-issues) (article)</span></span>