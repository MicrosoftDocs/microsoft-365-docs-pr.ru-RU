---
title: Создание подписи для всей компании
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
description: Узнайте, как создать подпись электронной почты для всей компании.
ms.openlocfilehash: 64c269abd25cab74ec5b0836975902e46a611c8c
ms.sourcegitcommit: f231eece2927f0d01072fd092db1eab15525bbc2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/17/2020
ms.locfileid: "49703030"
---
# <a name="create-a-company-wide-email-signature"></a><span data-ttu-id="ba456-103">Создание подписи электронной почты для всей компании</span><span class="sxs-lookup"><span data-stu-id="ba456-103">Create a company-wide email signature</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1IEWf?autoplay=false]

<span data-ttu-id="ba456-104">Подпись электронной почты всей компании отображается в каждом сообщении электронной почты, от отправленного людьми в вашей организации.</span><span class="sxs-lookup"><span data-stu-id="ba456-104">A company-wide email signature appears on every email sent by people in your organization.</span></span> <span data-ttu-id="ba456-105">Его можно использовать для отображения важных сведений, таких как контактные данные компании или юридическое заявление об отказе.</span><span class="sxs-lookup"><span data-stu-id="ba456-105">You can use it to display important details, like your company contact information or a legal disclaimer.</span></span> 

## <a name="try-it"></a><span data-ttu-id="ba456-106">Проверьте, как это работает!</span><span class="sxs-lookup"><span data-stu-id="ba456-106">Try it!</span></span>

1. <span data-ttu-id="ba456-107">В Центре администрирования Microsoft 365 выберите **Exchange.**</span><span class="sxs-lookup"><span data-stu-id="ba456-107">In the Microsoft 365 admin center, select **Exchange**.</span></span>
1. <span data-ttu-id="ba456-108">Выберите **поток почты.**</span><span class="sxs-lookup"><span data-stu-id="ba456-108">Select **Mail flow**.</span></span>
1. <span data-ttu-id="ba456-109">Выберите **"Добавить+"** и **"Применить заявления об отказе".**</span><span class="sxs-lookup"><span data-stu-id="ba456-109">Select **Add +**, and then select **Apply disclaimers**.</span></span>
1. <span data-ttu-id="ba456-110">На странице **"Новое правило":**</span><span class="sxs-lookup"><span data-stu-id="ba456-110">On the **New rule** page:</span></span>
    1. <span data-ttu-id="ba456-111">Введите имя правила.</span><span class="sxs-lookup"><span data-stu-id="ba456-111">Enter a name for the rule.</span></span>
    1. <span data-ttu-id="ba456-112">В **списке "Применить это правило при** выпадаемом списке" выберите **"Применить для всех сообщений".**</span><span class="sxs-lookup"><span data-stu-id="ba456-112">From the **Apply this rule if** drop-down list, select **Apply to all messages**.</span></span>
    1. <span data-ttu-id="ba456-113">В следующем **выпадаемом** списке убедитесь, что отображается заявление **об** отказе.</span><span class="sxs-lookup"><span data-stu-id="ba456-113">In the **Do the following** drop-down list, verify that **Append the disclaimer** is displayed.</span></span>
    1. <span data-ttu-id="ba456-114">В правой части страницы выберите "Введите текст", а затем введите текст подписи электронной почты в текстовом поле "Укажите заявление об отказе". </span><span class="sxs-lookup"><span data-stu-id="ba456-114">On the right side of the page, select **Enter text**, and then enter the text for your email signature in the **Specify disclaimer** text box.</span></span> <span data-ttu-id="ba456-115">Вы можете улучшить внешний вид подписи, отформатирование текста с помощью HTML.</span><span class="sxs-lookup"><span data-stu-id="ba456-115">You can improve the look of your signature by formatting the text with HTML.</span></span>
    1. <span data-ttu-id="ba456-116">Если вы хотите, чтобы изображение появлялись в подписи, необходимо использовать общедоступный URL-адрес для этого изображения.</span><span class="sxs-lookup"><span data-stu-id="ba456-116">If you want an image to appear in your signature, you'll need to use a publicly available URL for that image.</span></span> <span data-ttu-id="ba456-117">Перейдите к изображению в Интернете, щелкните его правой кнопкой мыши и выберите **"Копировать адрес изображения".**</span><span class="sxs-lookup"><span data-stu-id="ba456-117">Browse to the image on the web, right-click it, and select **Copy image address**.</span></span> <span data-ttu-id="ba456-118">Вкажите адрес в **текстовое поле "Укажите заявление об** отказе".</span><span class="sxs-lookup"><span data-stu-id="ba456-118">Paste the address into the **Specify disclaimer** text box.</span></span> <span data-ttu-id="ba456-119">Выберите **"ОК"** и прокрутите вниз.</span><span class="sxs-lookup"><span data-stu-id="ba456-119">Select **OK**, then scroll down.</span></span>
    1. <span data-ttu-id="ba456-120">Чтобы убедиться, что подпись работает с зашифрованными электронными письмами, добавьте параметр отката.</span><span class="sxs-lookup"><span data-stu-id="ba456-120">To make sure the signature works with encrypted emails, add a fallback option.</span></span> <span data-ttu-id="ba456-121">Справа от страницы выберите "Выбрать **один",** **"Перенос"** и **"ОК".**</span><span class="sxs-lookup"><span data-stu-id="ba456-121">On the right of the page, choose **Select one**, choose **Wrap**, and then select **OK**.</span></span>
    1. <span data-ttu-id="ba456-122">Прокрутите вниз и оставьте режим **"Принудительно"** и выберите **"Сохранить".**</span><span class="sxs-lookup"><span data-stu-id="ba456-122">Scroll down and leave the mode set to **Enforce**, and then select **Save**.</span></span>
1. <span data-ttu-id="ba456-123">Появится предупреждение.</span><span class="sxs-lookup"><span data-stu-id="ba456-123">A warning message will appear.</span></span> <span data-ttu-id="ba456-124">Выберите **"Да",** чтобы применить правило для всех будущих сообщений.</span><span class="sxs-lookup"><span data-stu-id="ba456-124">Select **Yes** to apply the rule to all future messages.</span></span>

    <span data-ttu-id="ba456-125">Ваша подпись создана.</span><span class="sxs-lookup"><span data-stu-id="ba456-125">Your signature has been created.</span></span> <span data-ttu-id="ba456-126">При отправке следующего сообщения электронной почты вы не увидите только что созданную подпись, но получатели электронной почты увидят ее.</span><span class="sxs-lookup"><span data-stu-id="ba456-126">When you send your next email, you won't see the signature you just created, but the email recipients will see it.</span></span>