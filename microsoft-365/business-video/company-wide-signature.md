---
title: Создание подписи для всей организации
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
description: Узнайте, как создать подписи электронной почты в масштабе всей компании.
ms.openlocfilehash: 22676ef6464e15e63efbe77d6dd6e88b4e494896
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422811"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="f4f8e-103">Создание подписи электронной почты для всей компании</span><span class="sxs-lookup"><span data-stu-id="f4f8e-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="f4f8e-104">В каждой электронной почте, отправленной людьми в вашей организации, отображается подпись электронной почты всей компании.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="f4f8e-105">Вы можете использовать его для отображения важных сведений, таких как контактные данные вашей компании или юридический отказ.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="f4f8e-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="f4f8e-106">Try it!</span></span>

1. <span data-ttu-id="f4f8e-107">В центре администрирования Microsoft 365 выберите **Exchange**.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="f4f8e-108">Выберите **поток почты.**</span><span class="sxs-lookup"><span data-stu-id="f4f8e-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="f4f8e-109">Выберите **Добавить +,** а затем выберите Применить отказ от **ответственности**.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="f4f8e-110">На странице **Новое правило:**</span><span class="sxs-lookup"><span data-stu-id="f4f8e-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="f4f8e-111">Введите имя правила.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="f4f8e-112">Из правила **Применить это правило, если** выпадаем список, выберите Применить для всех **сообщений**.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="f4f8e-113">В **списке Do the Do** ниже  проверьте, отображается ли приложение об отказе от ответственности.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="f4f8e-114">На правой стороне страницы выберите **Ввод** текста, а затем введите текст для подписи электронной почты в текстовом окне **Укажите** отказ от ответственности.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="f4f8e-115">Вы можете улучшить внешний вид подписи, форматирование текста с помощью HTML.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="f4f8e-116">Если вы хотите, чтобы изображение появлялись в подписи, для этого изображения необходимо использовать общедоступный URL-адрес.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="f4f8e-117">Просмотрите изображение в Интернете, щелкните его правой кнопкой мыши и выберите **адрес изображения Copy.**</span><span class="sxs-lookup"><span data-stu-id="f4f8e-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="f4f8e-118">Вклеить адрес в текстовое поле **указать** отказ.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="f4f8e-119">Выберите **ОК,** затем прокрутите вниз.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="f4f8e-120">Чтобы убедиться, что подпись работает с зашифрованными электронными письмами, добавьте вариант отката.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="f4f8e-121">Справа от страницы выберите **Выберите один,** выберите **Wrap** и выберите **ОК.**</span><span class="sxs-lookup"><span data-stu-id="f4f8e-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="f4f8e-122">Прокрутите вниз и оставьте режим, установленный для **обеспечения выполнения,** а затем выберите **Сохранить**.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="f4f8e-123">Появится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-123">A warning message will appear.</span></span> <span data-ttu-id="f4f8e-124">Выберите **Да,** чтобы применить правило для всех будущих сообщений.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="f4f8e-125">Ваша подпись создана.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-125">Your signature has been created.</span></span> <span data-ttu-id="f4f8e-126">При отправке следующей электронной почты вы не увидите только что созданную подпись, но получатели электронной почты увидят ее.</span><span class="sxs-lookup"><span data-stu-id="f4f8e-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>