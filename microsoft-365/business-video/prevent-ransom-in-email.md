---
title: Создание правил электронной почты для программ-вымогателей
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
description: Узнайте, как создавать правила электронной почты для предотвращения программ-вымогателей.
ms.openlocfilehash: 85898480438225848fc09db9a9c507045f8a182c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49702448"
---
# <a name="create-email-rules-to-prevent-ransomware"></a><span data-ttu-id="04301-103">Создание правил электронной почты для предотвращения программ-вымогателей</span><span class="sxs-lookup"><span data-stu-id="04301-103">Create email rules to prevent ransomware</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RWrWGt?autoplay=false]

<span data-ttu-id="04301-104">Microsoft 365 помогает защитить ваш бизнес от программ-вымогателей, предотвращая открытие потенциально опасных файлов, таких как JavaScript, пакетные файлы и исполняемые файлы, в Outlook.</span><span class="sxs-lookup"><span data-stu-id="04301-104">Microsoft 365 helps protect your business against ransomware by preventing potentially dangerous files, like JavaScript, batch, and executables, from being opened in Outlook.</span></span> <span data-ttu-id="04301-105">Чтобы повысить этот уровень защиты путем добавления правил, блокируют или предупреждают о дополнительных типах файлов, выполните следующие действия.</span><span class="sxs-lookup"><span data-stu-id="04301-105">To increase this level of protection by adding rules that block or warn you of additional types of files, follow these steps.</span></span>

## <a name="try-it"></a><span data-ttu-id="04301-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="04301-106">Try it!</span></span>

1. <span data-ttu-id="04301-107">В Центре администрирования выберите [https://admin.microsoft.com](https://admin.microsoft.com) **Exchange** в центре **администрирования.**</span><span class="sxs-lookup"><span data-stu-id="04301-107">From the admin center at [https://admin.microsoft.com](https://admin.microsoft.com), choose **Exchange** under **Admin centers**.</span></span>
1. <span data-ttu-id="04301-108">В меню слева выберите поток **почты.**</span><span class="sxs-lookup"><span data-stu-id="04301-108">From the menu on the left, choose **mail flow**.</span></span>
1. <span data-ttu-id="04301-109">На вкладке "Правила" выберите стрелку рядом с символом "плюс" (+) и выберите **"Создать новое правило".**</span><span class="sxs-lookup"><span data-stu-id="04301-109">On the rules tab, choose the arrow next to the plus (+) symbol, and then choose **Create a new rule**.</span></span>
1. <span data-ttu-id="04301-110">На странице **нового правила** введите имя правила, прокрутите вниз и выберите "Дополнительные **параметры".**</span><span class="sxs-lookup"><span data-stu-id="04301-110">On the **new rule** page, enter a name for your rule, scroll to the bottom, and then choose **More options**.</span></span>
1. <span data-ttu-id="04301-111">В **области "Применить это правило" выберите**"Любое вложение", а затем выберите расширение  **файла, включив эти слова.**</span><span class="sxs-lookup"><span data-stu-id="04301-111">Under **Apply this rule if**, select **Any attachment**, and then select **file extension includes these words**.</span></span>
1. <span data-ttu-id="04301-112">В поле под полем **укажите** слова или фразы, введите расширения файлов, к которые должно применяться правило, например расширения файлов, которые могут содержать макрос.</span><span class="sxs-lookup"><span data-stu-id="04301-112">In the box under **specify words or phrases**, enter the file extensions that you want the rule to be applied to, such as file extensions that can contain macros.</span></span> <span data-ttu-id="04301-113">Используйте символ плюса (+), чтобы добавить их по одному за раз.</span><span class="sxs-lookup"><span data-stu-id="04301-113">Use the plus (+) symbol to add them one at a time.</span></span>

    <span data-ttu-id="04301-114">Узнайте больше о типах файлов, прочитав [статью "Защита от программ-вымогателей".](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware)</span><span class="sxs-lookup"><span data-stu-id="04301-114">Learn more about file types by reading [Protect against ransomware](https://docs.microsoft.com/microsoft-365/admin/security-and-compliance/secure-your-business-data#ransomware).</span></span>

1. <span data-ttu-id="04301-115">Прокрутите вниз, чтобы просмотреть список, и выберите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="04301-115">Scroll down to review your list, and then choose **OK**.</span></span>
1. <span data-ttu-id="04301-116">На странице **нового правила** выберите **"Добавить условие",** а затем выберите условие в области **"Сделать следующее".**</span><span class="sxs-lookup"><span data-stu-id="04301-116">On the **new rule** page, choose **add condition**, and then choose a condition under **Do the following**.</span></span>
1. <span data-ttu-id="04301-117">У вас есть множество параметров правил, но в этом примере мы решили уведомить получателя **с помощью сообщения.**</span><span class="sxs-lookup"><span data-stu-id="04301-117">You have many rule options to choose from, but in this example we'll choose to **Notify the recipient with a message**.</span></span>
1. <span data-ttu-id="04301-118">Введите текст сообщения для уведомления и найдите **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="04301-118">Enter message text for your notification, and then chose **OK**.</span></span>
1. <span data-ttu-id="04301-119">Необязательно: на странице **нового** правила выберите "Добавить исключение" и введите любые сведения об исключениях из правила, например сообщения от надежных отправителей.</span><span class="sxs-lookup"><span data-stu-id="04301-119">Optional: On the **new rule** page, choose **add exception**, and enter any details for exceptions to your rule, such as messages from trusted senders.</span></span>
1. <span data-ttu-id="04301-120">На странице нового правила выберите "Сохранить" и просмотрите предоставленную сводную информацию о правиле.</span><span class="sxs-lookup"><span data-stu-id="04301-120">On the new rule page, choose **Save**, and review the rule summary information provided.</span></span>