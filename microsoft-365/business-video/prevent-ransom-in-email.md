---
title: Создание правил электронной почты для программ-шантажистов
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
description: Узнайте, как создать правила электронной почты для предотвращения программ-вымогателей.
ms.openlocfilehash: 96822916753f2f70d481c213e7e31046f7081446
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580502"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="aeb81-103">Создание правил электронной почты для предотвращения программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="aeb81-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="aeb81-104">Microsoft 365 помогает защитить бизнес от программ-вымогателей, предотвращая открытие потенциально опасных файлов, таких как JavaScript, пакеты и исполняемые файлы в Outlook.</span><span class="sxs-lookup"><span data-stu-id="aeb81-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="aeb81-105">Чтобы повысить этот уровень защиты, добавив правила, которые блокируют или предупреждают вас о дополнительных типах файлов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="aeb81-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="aeb81-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="aeb81-106">Try it!</span></span>

1. <span data-ttu-id="aeb81-107">В центре администрирования выберите [https://admin.microsoft.com](https://admin.microsoft.com) Exchange **центрах администрирования.** </span><span class="sxs-lookup"><span data-stu-id="aeb81-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="aeb81-108">Из меню слева выберите поток **почты.**</span><span class="sxs-lookup"><span data-stu-id="aeb81-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="aeb81-109">На вкладке Правила выберите стрелку рядом с символом плюс (+) и выберите **Создать новое правило.**</span><span class="sxs-lookup"><span data-stu-id="aeb81-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="aeb81-110">На странице **новое правило** введите имя правила, прокрутите его в нижней части, а затем выберите **дополнительные параметры.**</span><span class="sxs-lookup"><span data-stu-id="aeb81-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="aeb81-111">В **соответствии с этим правилом,** если выберите **любое** вложение, а затем выберите расширение файла включает в себя **эти слова**.</span><span class="sxs-lookup"><span data-stu-id="aeb81-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="aeb81-112">В поле под указанием слов или фраз введите расширения файлов, к которые необходимо применить правило, например расширения файлов, которые могут содержать макрос.</span><span class="sxs-lookup"><span data-stu-id="aeb81-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="aeb81-113">Используйте символ плюс (+) для добавления их по одному.</span><span class="sxs-lookup"><span data-stu-id="aeb81-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="aeb81-114">Узнайте больше о типах файлов, прочитав [статью Protect against ransomware.](../admin/security-and-compliance/secure-your-business-data.md#ransomware)</span><span class="sxs-lookup"><span data-stu-id="aeb81-114">Learn more about file types by reading [Protect against ransomware](../admin/security-and-compliance/secure-your-business-data.md#ransomware).</span></span>

1. <span data-ttu-id="aeb81-115">Прокрутите вниз, чтобы просмотреть список, а затем выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="aeb81-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="aeb81-116">На странице **новое правило** выберите **условие добавить,** а затем выбрать условие **в соответствии Сделайте следующее**.</span><span class="sxs-lookup"><span data-stu-id="aeb81-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="aeb81-117">У вас есть много вариантов правил, но в этом примере мы будем выбирать, чтобы уведомить получателя **с сообщением**.</span><span class="sxs-lookup"><span data-stu-id="aeb81-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="aeb81-118">Введите текст сообщения для уведомления, а затем выбрали **ОК.**</span><span class="sxs-lookup"><span data-stu-id="aeb81-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="aeb81-119">Необязательный. На новой странице правила выберите добавить исключение и введите все сведения для исключений из правила, например сообщений от доверенных отправителей. </span><span class="sxs-lookup"><span data-stu-id="aeb81-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="aeb81-120">На странице новое правило выберите **Сохранить** и просмотреть предоставленные сводные сведения о правилах.</span><span class="sxs-lookup"><span data-stu-id="aeb81-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>